---
title: Realización de operaciones asincrónicas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- initialization [SQL Server Native Client]
- database connections [SQL Server Native Client]
- data access [SQL Server Native Client], asynchronous operations
- connections [SQL Server Native Client]
- asynchronous operations [SQL Server Native Client]
- rowsets [SQL Server], initializing
- SQLNCLI, asynchronous operations
- SQL Server Native Client, asynchronous operations
ms.assetid: 8fbd84b4-69cb-4708-9f0f-bbdf69029bcc
author: rothja
ms.author: jroth
ms.openlocfilehash: 4f7e8f4481923cd7da537f921248865d4fff7280
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745249"
---
# <a name="performing-asynchronous-operations"></a><span data-ttu-id="f68a8-102">Realizar operaciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="f68a8-102">Performing Asynchronous Operations</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="f68a8-103">permite a las aplicaciones realizar operaciones de base de datos asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="f68a8-103">allows applications to perform asynchronous database operations.</span></span> <span data-ttu-id="f68a8-104">El procesamiento asincrónico permite a los métodos devolver resultados inmediatamente sin bloquear el subproceso que hace la llamada.</span><span class="sxs-lookup"><span data-stu-id="f68a8-104">Asynchronous processing enables methods to return immediately without blocking on the calling thread.</span></span> <span data-ttu-id="f68a8-105">Esto hace posible gran parte de la potencia y la flexibilidad del subprocesamiento múltiple, sin que el programador tenga que crear explícitamente subprocesos o administrar la sincronización.</span><span class="sxs-lookup"><span data-stu-id="f68a8-105">This allows much of the power and flexibility of multithreading, without requiring the developer to explicitly create threads or handle synchronization.</span></span> <span data-ttu-id="f68a8-106">Las aplicaciones solicitan el procesamiento asincrónico al inicializar una conexión a la base de datos, o al inicializar el resultado de la ejecución de un comando.</span><span class="sxs-lookup"><span data-stu-id="f68a8-106">Applications request asynchronous processing when initializing a database connection, or when initializing the result from the execution of a command.</span></span>  
  
## <a name="opening-and-closing-a-database-connection"></a><span data-ttu-id="f68a8-107">Abrir y cerrar una conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="f68a8-107">Opening and Closing a Database Connection</span></span>  
 <span data-ttu-id="f68a8-108">Cuando se usa el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client, las aplicaciones diseñadas para inicializar de forma asincrónica un objeto de origen de datos pueden establecer el bit de DBPROPVAL_ASYNCH_INITIALIZE en la propiedad DBPROP_INIT_ASYNCH antes de llamar a **IDBInitialize:: Initialize**.</span><span class="sxs-lookup"><span data-stu-id="f68a8-108">When using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, applications designed to initialize a data source object asynchronously can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_INIT_ASYNCH property prior to calling **IDBInitialize::Initialize**.</span></span> <span data-ttu-id="f68a8-109">Cuando se establece esta propiedad, el resultado de la llamada del proveedor a **Initialize** es S_OK si la operación se ha completado inmediatamente, o bien DB_S_ASYNCHRONOUS si la inicialización continúa de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="f68a8-109">When this property is set, the provider returns immediately from the call to **Initialize** with either S_OK, if the operation has completed immediately, or DB_S_ASYNCHRONOUS, if the initialization is continuing asynchronously.</span></span> <span data-ttu-id="f68a8-110">Las aplicaciones pueden consultar la interfaz **IDBAsynchStatus** o [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)en el objeto de origen de datos y, a continuación, llamar a **IDBAsynchStatus:: getStatus** o[ISSAsynchStatus:: WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) para obtener el estado de la inicialización.</span><span class="sxs-lookup"><span data-stu-id="f68a8-110">Applications can query for the **IDBAsynchStatus** or [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)interface on the data source object, and then call **IDBAsynchStatus::GetStatus** or[ISSAsynchStatus::WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) to get the status of the initialization.</span></span>  
  
 <span data-ttu-id="f68a8-111">Además, se ha agregado la propiedad SSPROP_ISSAsynchStatus al conjunto de propiedades DBPROPSET_SQLSERVERROWSET.</span><span class="sxs-lookup"><span data-stu-id="f68a8-111">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="f68a8-112">Los proveedores que admiten la interfaz **ISSAsynchStatus** deben implementar esta propiedad con un valor de VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="f68a8-112">Providers that support the **ISSAsynchStatus** interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="f68a8-113">Se puede llamar a **IDBAsynchStatus::Abort** o [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) para cancelar la llamada asincrónica a **Initialize**.</span><span class="sxs-lookup"><span data-stu-id="f68a8-113">**IDBAsynchStatus::Abort** or [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) can be called to cancel the asynchronous **Initialize** call.</span></span> <span data-ttu-id="f68a8-114">El consumidor debe solicitar explícitamente la inicialización de origen de datos asincrónica.</span><span class="sxs-lookup"><span data-stu-id="f68a8-114">The consumer must explicitly request Asynchronous Data Source Initialization.</span></span> <span data-ttu-id="f68a8-115">De lo contrario, **IDBInitialize::Initialize** no devuelve resultados hasta que se inicializa completamente el objeto de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f68a8-115">Otherwise, **IDBInitialize::Initialize** does not return until the data source object is completely initialized.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f68a8-116">Los objetos de origen de datos usados para la agrupación de conexiones no pueden llamar a la interfaz **ISSAsynchStatus** en el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="f68a8-116">Data source objects used for connection pooling cannot call the **ISSAsynchStatus** interface in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="f68a8-117">La interfaz **ISSAsynchStatus** no se expone para objetos de origen de datos agrupados.</span><span class="sxs-lookup"><span data-stu-id="f68a8-117">The **ISSAsynchStatus** interface is not exposed for pooled data source objects.</span></span>  
>   
>  <span data-ttu-id="f68a8-118">Si una aplicación obliga explícitamente a usar el motor de cursor, **IOpenRowset::OpenRowset** e **IMultipleResults::GetResult** no admitirán el procesamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="f68a8-118">If an application explicitly forces use of the cursor engine, **IOpenRowset::OpenRowset** and **IMultipleResults::GetResult** will not support asynchronous processing.</span></span>  
>   
>  <span data-ttu-id="f68a8-119">Además, la dll de código auxiliar/proxy de comunicación remota (en MDAC 2,8) no puede llamar a la interfaz **ISSAsynchStatus** en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="f68a8-119">In addition, the remoting proxy/stub dll (in MDAC 2.8) cannot call the **ISSAsynchStatus** interface in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="f68a8-120">La interfaz **ISSAsynchStatus** no se expone a través de la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="f68a8-120">The **ISSAsynchStatus** interface is not exposed through remoting.</span></span>  
>   
>  <span data-ttu-id="f68a8-121">Los componentes de servicio no admiten **ISSAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="f68a8-121">Service Components do not support **ISSAsynchStatus**.</span></span>  
  
## <a name="execution-and-rowset-initialization"></a><span data-ttu-id="f68a8-122">Ejecución e inicialización de conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="f68a8-122">Execution and Rowset Initialization</span></span>  
 <span data-ttu-id="f68a8-123">Las aplicaciones diseñadas para abrir de forma asincrónica el resultado de la ejecución de un comando pueden establecer el bit DBPROPVAL_ASYNCH_INITIALIZE en la propiedad DBPROP_ROWSET_ASYNCH.</span><span class="sxs-lookup"><span data-stu-id="f68a8-123">Applications designed to asynchronously open the result from the execution of a command can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_ROWSET_ASYNCH property.</span></span> <span data-ttu-id="f68a8-124">Si se establece este bit antes de llamar a **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** o **IMultipleResults::GetResult**, el argumento *riid* debe establecerse en IID_IDBAsynchStatus, IID_ISSAsynchStatus o IID_IUnknown.</span><span class="sxs-lookup"><span data-stu-id="f68a8-124">When setting this bit prior to calling **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** or **IMultipleResults::GetResult**, the *riid* argument must be set to IID_IDBAsynchStatus, IID_ISSAsynchStatus, or IID_IUnknown.</span></span>  
  
 <span data-ttu-id="f68a8-125">El método devuelve inmediatamente S_OK si la inicialización del conjunto de filas se completa de forma inmediata, o DB_S_ASYNCHRONOUS si el conjunto de filas sigue inicializándose de forma asincrónica, con *ppRowset* establecido en la interfaz solicitada en el conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="f68a8-125">The method returns immediately with S_OK if the rowset initialization completes immediately, or with DB_S_ASYNCHRONOUS if the rowset continues initializing asynchronously, with *ppRowset* set to the requested interface on the rowset.</span></span> <span data-ttu-id="f68a8-126">Para el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client, esta interfaz solo puede ser **IDBAsynchStatus** o **ISSAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="f68a8-126">For the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, this interface can only be **IDBAsynchStatus** or **ISSAsynchStatus**.</span></span> <span data-ttu-id="f68a8-127">Hasta que el conjunto de filas está totalmente inicializado, esta interfaz se comporta como si estuviera en estado suspendido y las llamadas a **QueryInterface** para interfaces distintas de **IID_IDBAsynchStatus** o **IID_ISSAsynchStatus** pueden devolver E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="f68a8-127">Until the rowset is fully initialized, this interface behaves as if it were in a suspended state, and calling **QueryInterface** for interfaces other than **IID_IDBAsynchStatus** or **IID_ISSAsynchStatus** may return E_NOINTERFACE.</span></span> <span data-ttu-id="f68a8-128">A menos que el consumidor solicite explícitamente el procesamiento asincrónico, el conjunto de filas se inicializa de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="f68a8-128">Unless the consumer explicitly requests asynchronous processing, the rowset is initialized synchronously.</span></span> <span data-ttu-id="f68a8-129">Todos las interfaces solicitadas están disponibles cuando **IDBAsynchStaus::GetStatus** o **ISSAsynchStatus::WaitForAsynchCompletion** devuelven la indicación de que se ha completado la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="f68a8-129">All requested interfaces are available when **IDBAsynchStaus::GetStatus** or **ISSAsynchStatus::WaitForAsynchCompletion** returns with the indication that asynchronous operation is complete.</span></span> <span data-ttu-id="f68a8-130">Esto no significa necesariamente que el conjunto de filas esté totalmente rellenado, pero está completo y es totalmente funcional.</span><span class="sxs-lookup"><span data-stu-id="f68a8-130">This does not necessarily mean that the rowset is fully populated, but it is complete and fully functional.</span></span>  
  
 <span data-ttu-id="f68a8-131">Si el comando ejecutado no devuelve un conjunto de filas, sigue devolviendo inmediatamente un objeto que admite **IDBAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="f68a8-131">If the executed command does not return a rowset, it still returns immediately with an object that supports **IDBAsynchStatus**.</span></span>  
  
 <span data-ttu-id="f68a8-132">Si necesita recibir varios resultados de la ejecución de comandos asincrónica, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f68a8-132">If you need to get multiple results from asynchronous command execution, you should:</span></span>  
  
-   <span data-ttu-id="f68a8-133">Establezca el bit DBPROPVAL_ASYNCH_INITIALIZE de la propiedad DBPROP_ROWSET_ASYNCH antes de ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="f68a8-133">Set the DBPROPVAL_ASYNCH_INITIALIZE bit of the DBPROP_ROWSET_ASYNCH property, before executing the command.</span></span>  
  
-   <span data-ttu-id="f68a8-134">Llame a **ICommand::Execute** y solicite **IMultipleResults**.</span><span class="sxs-lookup"><span data-stu-id="f68a8-134">Call **ICommand::Execute**, and request **IMultipleResults**.</span></span>  
  
 <span data-ttu-id="f68a8-135">Las interfaces **ISSAsynchStatus** e **IDBAsynchStatus** se pueden obtener al consultar la interfaz de varios resultados mediante **QueryInterface**.</span><span class="sxs-lookup"><span data-stu-id="f68a8-135">The **IDBAsynchStatus** and **ISSAsynchStatus** interfaces can then be obtained by querying the multiple results interface using **QueryInterface**.</span></span>  
  
 <span data-ttu-id="f68a8-136">Una vez completada la ejecución del comando, **IMultipleResults** se puede usar de forma normal, con una excepción del caso sincrónico: se puede devolver DB_S_ASYNCHRONOUS, en cuyo caso se puede usar **IDBAsynchStatus** o **ISSAsynchStatus** para determinar cuándo se ha completado la operación.</span><span class="sxs-lookup"><span data-stu-id="f68a8-136">When the command has finished executing, **IMultipleResults** can be used as normal, with one exception from the synchronous case: DB_S_ASYNCHRONOUS may be returned, in which case **IDBAsynchStatus** or **ISSAsynchStatus** can be used to determine when the operation is complete.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f68a8-137">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f68a8-137">Examples</span></span>  
 <span data-ttu-id="f68a8-138">En el ejemplo siguiente, la aplicación llama a un método de no bloqueo, realiza algún otro procesamiento y, después, vuelve a procesar los resultados.</span><span class="sxs-lookup"><span data-stu-id="f68a8-138">In the following example, the application calls a non-blocking method, does some other processing, and then returns to process the results.</span></span> <span data-ttu-id="f68a8-139">**ISSAsynchStatus::WaitForAsynchCompletion** espera en el objeto de evento interno hasta que se completa la operación de ejecución asincrónica o transcurre el tiempo especificado por *dwMilisecTimeOut*.</span><span class="sxs-lookup"><span data-stu-id="f68a8-139">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the amount of time specified by *dwMilisecTimeOut* is passed.</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
  
DBPROPSET CmdPropset[1];  
DBPROP CmdProperties[1];  
  
CmdPropset[0].rgProperties = CmdProperties;  
CmdPropset[0].cProperties = 1;  
CmdPropset[0].guidPropertySet = DBPROPSET_ROWSET;  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
CmdProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
  
hr = pICommandProps->SetProperties(1, CmdPropset);  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if ( hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="f68a8-140">**ISSAsynchStatus::WaitForAsynchCompletion** espera en el objeto de evento interno hasta que se completa la operación de ejecución asincrónica o transcurre el valor de *dwMilisecTimeOut*.</span><span class="sxs-lookup"><span data-stu-id="f68a8-140">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the *dwMilisecTimeOut* value is passed.</span></span>  
  
 <span data-ttu-id="f68a8-141">En el ejemplo siguiente se muestra el procesamiento asincrónico con varios conjuntos de resultados:</span><span class="sxs-lookup"><span data-stu-id="f68a8-141">The following example shows asynchronous processing with multiple result sets:</span></span>  
  
```  
DBPROP CmdProperties[1];  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_IMultipleResults,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pIMultipleResults);  
  
// Use GetResults for ISSAsynchStatus.  
hr = pIMultipleResults->GetResult(IID_ISSAsynchStatus, (void **) &pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if (hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="f68a8-142">Para evitar bloqueos, el cliente puede comprobar el estado de una operación asincrónica en ejecución, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f68a8-142">To prevent blocking, the client can check the status of a running asynchronous operation, as in the following example:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);   
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   do{  
      // Do some work...  
      hr = pISSAsynchStatus->GetStatus(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN, NULL, NULL, &ulAsynchPhase, NULL);  
   }while (DBASYNCHPHASE_COMPLETE != ulAsynchPhase)  
   if SUCCEEDED(hr)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
   }  
   pIDBAsynchStatus->Release();  
}  
```  
  
 <span data-ttu-id="f68a8-143">El ejemplo siguiente muestra cómo puede cancelar la operación asincrónica que se está ejecutando en este momento:</span><span class="sxs-lookup"><span data-stu-id="f68a8-143">The following example demonstrates how you can cancel the currently running asynchronous operation:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work...  
   hr = pISSAsynchStatus->Abort(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f68a8-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f68a8-144">See Also</span></span>  
 <span data-ttu-id="f68a8-145">[Características de SQL Server Native Client](sql-server-native-client-features.md) </span><span class="sxs-lookup"><span data-stu-id="f68a8-145">[SQL Server Native Client Features](sql-server-native-client-features.md) </span></span>  
 <span data-ttu-id="f68a8-146">[Propiedades y comportamientos de conjuntos de filas](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="f68a8-146">[Rowset Properties and Behaviors](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 [<span data-ttu-id="f68a8-147">ISSAsynchStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f68a8-147">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)  
  
  
