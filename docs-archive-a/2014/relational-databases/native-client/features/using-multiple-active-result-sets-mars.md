---
title: Uso de conjuntos de resultados activos múltiples (MARS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, MARS
- SQLNCLI, MARS
- data access [SQL Server Native Client], MARS
- Multiple Active Result Sets
- SQL Server Native Client, MARS
- MARS [SQL Server]
- SQL Server Native Client ODBC driver, MARS
ms.assetid: ecfd9c6b-7d29-41d8-af2e-89d7fb9a1d83
author: rothja
ms.author: jroth
ms.openlocfilehash: 7119048df3de23b1cfc5d6c8fb41672d82be14f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675313"
---
# <a name="using-multiple-active-result-sets-mars"></a><span data-ttu-id="d1b4e-102">Utilizar conjuntos de resultados activos múltiples (MARS)</span><span class="sxs-lookup"><span data-stu-id="d1b4e-102">Using Multiple Active Result Sets (MARS)</span></span>
  <span data-ttu-id="d1b4e-103">En [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], se ha introducido la compatibilidad con los conjuntos de resultados activos múltiples (MARS) para las aplicaciones que acceden a [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1b4e-103">[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] introduced support for multiple active result sets (MARS) in applications accessing the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="d1b4e-104">En versiones anteriores de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], las aplicaciones de base de datos no podían mantener varias instrucciones activas en una conexión.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-104">In earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], database applications could not maintain multiple active statements on a connection.</span></span> <span data-ttu-id="d1b4e-105">La aplicación, cuando utilizaba conjuntos de resultados predeterminados de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], tenía que procesar o cancelar todos los conjuntos de resultados de un lote para poder ejecutar cualquier otro lote en esa conexión.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-105">When using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result sets, the application had to process or cancel all result sets from one batch before it could execute any other batch on that connection.</span></span> <span data-ttu-id="d1b4e-106">En [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] se introdujo un nuevo atributo de conexión que permite a las aplicaciones tener más de una solicitud pendiente por conexión y, en particular, tener más de un conjunto de resultados predeterminado activo por conexión.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-106">[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] introduced a new connection attribute that allows applications to have more than one pending request per connection, and in particular, to have more than one active default result set per connection.</span></span>  
  
 <span data-ttu-id="d1b4e-107">MARS simplifica el diseño de aplicaciones con una serie de capacidades nuevas que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="d1b4e-107">MARS simplifies application design with the following new capabilities:</span></span>  
  
-   <span data-ttu-id="d1b4e-108">Las aplicaciones pueden tener varios conjuntos de resultados predeterminados abiertos e intercalar la lectura de los mismos.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-108">Applications can have multiple default result sets open and can interleave reading from them.</span></span>  
  
-   <span data-ttu-id="d1b4e-109">Las aplicaciones pueden ejecutar otras instrucciones (por ejemplo, INSERT, UPDATE, DELETE y llamadas a procedimientos almacenados) mientras los conjuntos de resultados predeterminados están abiertos.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-109">Applications can execute other statements (for example, INSERT, UPDATE, DELETE, and stored procedure calls) while default result sets are open.</span></span>  
  
 <span data-ttu-id="d1b4e-110">Las aplicaciones que usan MARS encontrarán útiles las siguientes directrices:</span><span class="sxs-lookup"><span data-stu-id="d1b4e-110">Applications using MARS will find the following guidelines beneficial:</span></span>  
  
-   <span data-ttu-id="d1b4e-111">Los conjuntos de resultados predeterminados deben usarse para conjuntos de resultados cortos o de corta duración generados por instrucciones SQL únicas (SELECT, DML con OUTPUT, RECEIVE, READ TEXT, etc.).</span><span class="sxs-lookup"><span data-stu-id="d1b4e-111">Default results sets should be used for short lived or short result sets generated by single SQL statements (SELECT, DML with OUTPUT, RECEIVE, READ TEXT, and so on).</span></span>  
  
-   <span data-ttu-id="d1b4e-112">Los cursores de servidor deben usarse para conjuntos de resultados mayores o de mayor duración generados por instrucciones SQL únicas.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-112">Server cursors should be used for longer lived or large result sets generated by single SQL statements.</span></span>  
  
-   <span data-ttu-id="d1b4e-113">Lea siempre los resultados hasta el final para las solicitudes de procedimientos, independientemente de que devuelvan o no resultados, y para los lotes que devuelven varios resultados.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-113">Always read to the end of results for procedural requests regardless of whether they return results or not, and for batches that return multiple results.</span></span>  
  
-   <span data-ttu-id="d1b4e-114">Siempre que sea posible, use llamadas a la API para cambiar las propiedades de conexión y administrar las transacciones con prioridad con respecto a las instrucciones [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1b4e-114">Wherever possible, use API calls to change connection properties and manage transactions in preference to [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span>  
  
-   <span data-ttu-id="d1b4e-115">En MARS, está prohibida la suplantación de ámbito de sesión mientras se ejecutan lotes simultáneos.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-115">In MARS, session-scoped impersonation is prohibited while concurrent batches are running.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d1b4e-116">De forma predeterminada, no está habilitada la funcionalidad de MARS.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-116">By default, MARS functionality is not enabled.</span></span> <span data-ttu-id="d1b4e-117">Para usar MARS al conectarse a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, debe habilitarlo específicamente dentro de una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-117">To use MARS when connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, you must specifically enable it within a connection string.</span></span> <span data-ttu-id="d1b4e-118">Para obtener más información, vea las secciones sobre el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client y el controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-118">For more information, see the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver sections, later in this topic.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="d1b4e-119">Native Client no limita el número de instrucciones activas en una conexión.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-119">Native Client does not limit the number of active statements on a connection.</span></span>  
  
 <span data-ttu-id="d1b4e-120">Las aplicaciones típicas que no necesitan tener más de un único lote de varias instrucciones o un único procedimiento almacenado que se ejecute al mismo tiempo podrán beneficiarse de MARS sin necesidad de entender cómo se implementa MARS.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-120">Typical applications which do not need to have more than a single multistatement batch or stored procedure executing at the same time will benefit from MARS without having to understand how MARS is implemented.</span></span> <span data-ttu-id="d1b4e-121">No obstante, las aplicaciones con requisitos más complejos necesitan tener estas consideraciones en cuenta.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-121">However, applications with more complex requirements do need to take account of this.</span></span>  
  
 <span data-ttu-id="d1b4e-122">MARS habilita la ejecución intercalada de varias solicitudes dentro de una única conexión.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-122">MARS enables the interleaved execution of multiple requests within a single connection.</span></span> <span data-ttu-id="d1b4e-123">Es decir, permite la ejecución de un lote y, dentro de su ejecución, permite que se ejecuten otras solicitudes.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-123">That is, it allows a batch to run, and within its execution, it allows other requests to execute.</span></span> <span data-ttu-id="d1b4e-124">Tenga en cuenta, no obstante, que MARS se define en términos de intercalación, no de ejecución en paralelo.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-124">Note, however, that MARS is defined in terms of interleaving, not in terms of parallel execution.</span></span>  
  
 <span data-ttu-id="d1b4e-125">La infraestructura de MARS permite la ejecución de varios lotes en modo intercalado, aunque la ejecución solo puede intercambiarse en puntos bien definidos.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-125">The MARS infrastructure allows multiple batches to execute in an interleaved fashion, though execution can only be switched at well defined points.</span></span> <span data-ttu-id="d1b4e-126">Además, la mayoría de las instrucciones deben ejecutarse de forma atómica dentro de un lote.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-126">In addition, most statements must run atomically within a batch.</span></span> <span data-ttu-id="d1b4e-127">Las instrucciones que devuelven filas al cliente, que a veces se denominan *puntos de rendimiento*, pueden intercalar la ejecución antes de la finalización mientras se envían filas al cliente, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d1b4e-127">Statements which return rows to the client, which are sometimes referred to as *yield points*, are allowed to interleave execution before completion while rows are being sent to the client, for example:</span></span>  
  
-   <span data-ttu-id="d1b4e-128">SELECT</span><span class="sxs-lookup"><span data-stu-id="d1b4e-128">SELECT</span></span>  
  
-   <span data-ttu-id="d1b4e-129">FETCH</span><span class="sxs-lookup"><span data-stu-id="d1b4e-129">FETCH</span></span>  
  
-   <span data-ttu-id="d1b4e-130">RECEIVE</span><span class="sxs-lookup"><span data-stu-id="d1b4e-130">RECEIVE</span></span>  
  
 <span data-ttu-id="d1b4e-131">Cualquier otra instrucción que se ejecute como parte de un procedimiento almacenado o de un lote deberá ejecutarse hasta completarse para poder cambiar la ejecución a otras solicitudes MARS.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-131">Any other statements that are executed as part of a stored procedure or batch must run to completion before execution can be switched to other MARS requests.</span></span>  
  
 <span data-ttu-id="d1b4e-132">La manera exacta en la que los lotes intercalan la ejecución se ve afectada por diversos factores, y es difícil predecir la secuencia exacta en la que se ejecutarán los comandos procedentes de varios lotes que contengan puntos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-132">The exact manner in which batches interleave execution is influenced by a number of factors, and it is difficult to predict the exact sequence in which commands from multiple batches that contain yield points will be executed.</span></span> <span data-ttu-id="d1b4e-133">Tenga cuidado para evitar efectos secundarios no deseados debidos a la ejecución intercalada de esos lotes complejos.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-133">Be careful to avoid unwanted side effects due to interleaved execution of such complex batches.</span></span>  
  
 <span data-ttu-id="d1b4e-134">Evite problemas utilizando llamadas a la API en lugar de instrucciones [!INCLUDE[tsql](../../../includes/tsql-md.md)] para administrar el estado de conexión (SET, USE) y las transacciones (BEGIN TRAN, COMMIT, ROLLBACK) no incluyendo estas instrucciones en lotes de varias instrucciones que también contengan puntos de rendimiento y serializando la ejecución de dichos lotes mediante el consumo o la cancelación de todos los resultados.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-134">Avoid problems by using API calls rather than [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements to manage connection state (SET, USE) and transactions (BEGIN TRAN, COMMIT, ROLLBACK) by not including these statements in multi-statement batches that also contain yield points, and by serializing execution of such batches by consuming or canceling all results.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d1b4e-135">Un lote o un procedimiento almacenado que inicie una transacción manual o implícita cuando MARS esté habilitado debe completar la transacción antes de salir del lote.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-135">A batch or stored procedure which starts a manual or implicit transaction when MARS is enabled must complete the transaction before the batch exits.</span></span> <span data-ttu-id="d1b4e-136">Si no lo hace, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] revierte todos los cambios realizados por la transacción cuando finaliza el lote.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-136">If it does not, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] rolls back all changes made by the transaction when the batch finishes.</span></span> <span data-ttu-id="d1b4e-137">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administra este tipo de transacción como una transacción de ámbito de lote.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-137">Such a transaction is managed by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a batch-scoped transaction.</span></span> <span data-ttu-id="d1b4e-138">Se trata de un nuevo tipo de transacción que se introdujo en [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] para permitir el uso de procedimientos almacenados con comportamiento correcto cuando MARS está habilitado.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-138">This is a new type of transaction introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] to enable existing well-behaved stored procedures to be used when MARS is enabled.</span></span> <span data-ttu-id="d1b4e-139">Para más información acerca de las transacciones de ámbito de lote, consulte [Instrucciones de transacciones &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transactions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d1b4e-139">For more information about batch-scoped transactions, see [Transaction Statements &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transactions-transact-sql).</span></span>  
  
 <span data-ttu-id="d1b4e-140">Para obtener un ejemplo del uso de MARS desde ADO, vea [usar ado con SQL Server Native Client](../applications/using-ado-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="d1b4e-140">For an example of using MARS from ADO, see [Using ADO with SQL Server Native Client](../applications/using-ado-with-sql-server-native-client.md).</span></span>  
  
## <a name="sql-server-native-client-ole-db-provider"></a><span data-ttu-id="d1b4e-141">Proveedor OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b4e-141">SQL Server Native Client OLE DB Provider</span></span>  
 <span data-ttu-id="d1b4e-142">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client admite Mars a través de la adición de la propiedad de inicialización de origen de datos SSPROP_INIT_MARSCONNECTION, que se implementa en el conjunto de propiedades DBPROPSET_SQLSERVERDBINIT.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-142">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports MARS through the addition of the SSPROP_INIT_MARSCONNECTION data source initialization property, which is implemented in the DBPROPSET_SQLSERVERDBINIT property set.</span></span> <span data-ttu-id="d1b4e-143">Además, se ha agregado una nueva palabra clave de cadena de conexión, `MarsConn`.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-143">In addition, a new connection string keyword, `MarsConn`, as been added.</span></span> <span data-ttu-id="d1b4e-144">Acepta valores `true` o `false`; `false` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-144">It accepts `true` or `false` values; `false` is the default.</span></span>  
  
 <span data-ttu-id="d1b4e-145">El valor predeterminado de la propiedad de origen de datos DBPROP_MULTIPLECONNECTIONS es VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-145">The data source property DBPROP_MULTIPLECONNECTIONS defaults to VARIANT_TRUE.</span></span> <span data-ttu-id="d1b4e-146">Esto significa que el proveedor generará varias conexiones para admitir varios comandos y objetos de conjunto de filas simultáneos.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-146">This means the provider will spawn multiple connections in order to support multiple concurrent command and rowset objects.</span></span> <span data-ttu-id="d1b4e-147">Cuando MARS está habilitado, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client puede admitir varios objetos de comando y conjunto de filas en una única conexión, por lo que MULTIPLE_CONNECTIONS se establece en VARIANT_FALSE de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-147">When MARS is enabled, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client can support multiple command and rowset objects on a single connection, so MULTIPLE_CONNECTIONS is set to VARIANT_FALSE by default.</span></span>  
  
 <span data-ttu-id="d1b4e-148">Para más información sobre las mejoras realizadas en el conjunto de propiedades DBPROPSET_SQLSERVERDBINIT, consulte [Propiedades de inicialización y autorización](../../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d1b4e-148">For more information about enhancements made to the DBPROPSET_SQLSERVERDBINIT property set, see [Initialization and Authorization Properties](../../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span></span>  
  
### <a name="sql-server-native-client-ole-db-provider-example"></a><span data-ttu-id="d1b4e-149">Ejemplo del proveedor OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b4e-149">SQL Server Native Client OLE DB Provider Example</span></span>  
 <span data-ttu-id="d1b4e-150">En este ejemplo, se crea un objeto de origen de datos mediante el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB nativo y Mars se habilita mediante la propiedad DBPROPSET_SQLSERVERDBINIT establecida antes de que se cree el objeto de sesión.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-150">In this example, a data source object is created using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native OLE DB provider, and MARS is enabled using the DBPROPSET_SQLSERVERDBINIT property set before the session object is created.</span></span>  
  
```  
#include <sqlncli.h>  
  
IDBInitialize *pIDBInitialize = NULL;  
IDBCreateSession *pIDBCreateSession = NULL;  
IDBProperties *pIDBProperties = NULL;  
  
// Create the data source object.  
hr = CoCreateInstance(CLSID_SQLNCLI10, NULL,  
   CLSCTX_INPROC_SERVER,  
   IID_IDBInitialize,   
    (void**)&pIDBInitialize);  
  
hr = pIDBInitialize->QueryInterface(IID_IDBProperties, (void**)&pIDBProperties);  
  
// Set the MARS property.  
DBPROP rgPropMARS;  
  
// The following is necessary since MARS is off by default.  
rgPropMARS.dwPropertyID = SSPROP_INIT_MARSCONNECTION;  
rgPropMARS.dwOptions = DBPROPOPTIONS_REQUIRED;  
rgPropMARS.dwStatus = DBPROPSTATUS_OK;  
rgPropMARS.colid = DB_NULLID;  
V_VT(&(rgPropMARS.vValue)) = VT_BOOL;  
V_BOOL(&(rgPropMARS.vValue)) = VARIANT_TRUE;  
  
// Create the structure containing the properties.  
DBPROPSET PropSet;  
PropSet.rgProperties = &rgPropMARS;  
PropSet.cProperties = 1;  
PropSet.guidPropertySet = DBPROPSET_SQLSERVERDBINIT;  
  
// Get an IDBProperties pointer and set the initialization properties.  
pIDBProperties->SetProperties(1, &PropSet);  
pIDBProperties->Release();  
  
// Initialize the data source object.  
hr = pIDBInitialize->Initialize();  
  
//Create a session object from a data source object.  
IOpenRowset * pIOpenRowset = NULL;  
hr = IDBInitialize->QueryInterface(IID_IDBCreateSession, (void**)&pIDBCreateSession));  
hr = pIDBCreateSession->CreateSession(  
   NULL,             // pUnkOuter  
   IID_IOpenRowset,  // riid  
  &pIOpenRowset ));  // ppSession  
  
// Create a rowset with a firehose mode cursor.  
IRowset *pIRowset = NULL;  
DBPROP rgRowsetProperties[2];  
  
// To get a firehose mode cursor request a   
// forward only read only rowset.  
rgRowsetProperties[0].dwPropertyID = DBPROP_IRowsetLocate;  
rgRowsetProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
rgRowsetProperties[0].dwStatus = DBPROPSTATUS_OK;  
rgRowsetProperties[0].colid = DB_NULLID;  
VariantInit(&(rgRowsetProperties[0].vValue));  
rgRowsetProperties[0].vValue.vt = VARIANT_BOOL;  
rgRowsetProperties[0].vValue.boolVal = VARIANT_FALSE;  
  
rgRowsetProperties[1].dwPropertyID = DBPROP_IRowsetChange;  
rgRowsetProperties[1].dwOptions = DBPROPOPTIONS_REQUIRED;  
rgRowsetProperties[1].dwStatus = DBPROPSTATUS_OK;  
rgRowsetProperties[1].colid = DB_NULLID;  
VariantInit(&(rgRowsetProperties[1].vValue));  
rgRowsetProperties[1].vValue.vt = VARIANT_BOOL;  
rgRowsetProperties[1].vValue.boolVal = VARIANT_FALSE;  
  
DBPROPSET rgRowsetPropSet[1];  
rgRowsetPropSet[0].rgProperties = rgRowsetProperties  
rgRowsetPropSet[0].cProperties = 2  
rgRowsetPropSet[0].guidPropertySet = DBPROPSET_ROWSET;  
  
hr = pIOpenRowset->OpenRowset (NULL,  
   &TableID,  
   NULL,  
   IID_IRowset,  
   1,  
   rgRowsetPropSet  
   (IUnknown**)&pIRowset);  
```  
  
## <a name="sql-server-native-client-odbc-driver"></a><span data-ttu-id="d1b4e-151">Controlador ODBC de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b4e-151">SQL Server Native Client ODBC Driver</span></span>  
 <span data-ttu-id="d1b4e-152">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client admite Mars a través de adiciones a las funciones [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) y [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md) .</span><span class="sxs-lookup"><span data-stu-id="d1b4e-152">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports MARS through additions to the [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) and [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md) functions.</span></span> <span data-ttu-id="d1b4e-153">SQL_COPT_SS_MARS_ENABLED se ha agregado para aceptar SQL_MARS_ENABLED_YES o SQL_MARS_ENABLED_NO, siendo SQL_MARS_ENABLED_NO el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-153">SQL_COPT_SS_MARS_ENABLED has been added to accept either SQL_MARS_ENABLED_YES or SQL_MARS_ENABLED_NO, with SQL_MARS_ENABLED_NO being the default.</span></span> <span data-ttu-id="d1b4e-154">Además, se ha agregado una nueva palabra clave de cadena de conexión, `Mars_Connection`.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-154">In addition, a new connection string keyword, `Mars_Connection`, as been added.</span></span> <span data-ttu-id="d1b4e-155">Acepta valores "yes" o "no"; "no" es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-155">It accepts "yes" or "no" values; "no" is the default.</span></span>  
  
### <a name="sql-server-native-client-odbc-driver-example"></a><span data-ttu-id="d1b4e-156">Ejemplo del controlador ODBC de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b4e-156">SQL Server Native Client ODBC Driver Example</span></span>  
 <span data-ttu-id="d1b4e-157">En este ejemplo, la función **SQLSetConnectAttr** se usa para habilitar Mars antes de llamar a la función **SQLDriverConnect** para conectar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-157">In this example, the **SQLSetConnectAttr** function is used to enable MARS before calling the **SQLDriverConnect** function to connect the database.</span></span> <span data-ttu-id="d1b4e-158">Una vez realizada la conexión, se llama a dos funciones **SQLExecDirect** para crear dos conjuntos de resultados independientes en la misma conexión.</span><span class="sxs-lookup"><span data-stu-id="d1b4e-158">Once the connection is made, two **SQLExecDirect** functions are called to create two separate result sets on the same connection.</span></span>  
  
```  
#include <sqlncli.h>  
  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_MARS_ENABLED, SQL_MARS_ENABLED_YES, SQL_IS_UINTEGER);  
SQLDriverConnect(hdbc, hwnd,   
   "DRIVER=SQL Server Native Client 10.0;  
   SERVER=(local);trusted_connection=yes;", SQL_NTS, szOutConn,   
   MAX_CONN_OUT, &cbOutConn, SQL_DRIVER_COMPLETE);  
  
SQLAllocHandle(SQL_HANDLE_STMT, hdbc, &hstmt1);  
SQLAllocHandle(SQL_HANDLE_STMT, hdbc, &hstmt2);  
  
// The 2nd execute would have failed with connection busy error if  
// MARS were not enabled.  
SQLExecDirect(hstmt1, L"SELECT * FROM Authors", SQL_NTS);  
SQLExecDirect(hstmt2, L"SELECT * FROM Titles", SQL_NTS);  
  
// Result set processing can interleave.  
SQLFetch(hstmt1);  
SQLFetch(hstmt2);  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1b4e-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1b4e-159">See Also</span></span>  
 <span data-ttu-id="d1b4e-160">[Características de SQL Server Native Client](sql-server-native-client-features.md) </span><span class="sxs-lookup"><span data-stu-id="d1b4e-160">[SQL Server Native Client Features](sql-server-native-client-features.md) </span></span>  
 [<span data-ttu-id="d1b4e-161">Utilizar conjuntos de resultados predeterminados de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1b4e-161">Using SQL Server Default Result Sets</span></span>](../../native-client-odbc-cursors/implementation/using-sql-server-default-result-sets.md)  
  
  
