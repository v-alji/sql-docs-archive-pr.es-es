---
title: Establecimiento de una conexión a un origen de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [SQL Server Native Client]
- connections [SQL Server Native Client]
- SQL Server Native Client OLE DB provider, data source connections
- CoCreateInstance method
- OLE DB data sources [SQL Server Native Client]
ms.assetid: 7ebd1394-cc8d-4bcf-92f3-c374a26e7ba0
author: rothja
ms.author: jroth
ms.openlocfilehash: f88454339ee932c38655819cce475ab52d79975f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675829"
---
# <a name="establishing-a-connection-to-a-data-source"></a><span data-ttu-id="df864-102">Establecer una conexión con un origen de datos</span><span class="sxs-lookup"><span data-stu-id="df864-102">Establishing a Connection to a Data Source</span></span>
  <span data-ttu-id="df864-103">Para tener acceso al [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client, el consumidor debe crear primero una instancia de un objeto de origen de datos llamando al método **CoCreateInstance** .</span><span class="sxs-lookup"><span data-stu-id="df864-103">To access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer must first create an instance of a data source object by calling the **CoCreateInstance** method.</span></span> <span data-ttu-id="df864-104">Un identificador de clase único (CLSID) identifica cada proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="df864-104">A unique class identifier (CLSID) identifies each OLE DB provider.</span></span> <span data-ttu-id="df864-105">Para el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client, el identificador de clase es CLSID_SQLNCLI10.</span><span class="sxs-lookup"><span data-stu-id="df864-105">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the class identifier is CLSID_SQLNCLI10.</span></span> <span data-ttu-id="df864-106">También puede usar el símbolo SQLNCLI_CLSID que se resolverá en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client que se usa en SQLNCLI. h al que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="df864-106">You can also use the symbol SQLNCLI_CLSID that will resolve to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider that is used in the sqlncli.h that you reference.</span></span>  
  
 <span data-ttu-id="df864-107">El objeto de origen de datos expone la interfaz **IDBProperties**, que el consumidor usa para proporcionar información de autenticación básica como el nombre del servidor, el nombre de la base de datos, el identificador de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="df864-107">The data source object exposes the **IDBProperties** interface, which the consumer uses to provide basic authentication information such as server name, database name, user ID, and password.</span></span> <span data-ttu-id="df864-108">Se llama al método **IDBProperties::SetProperties** para establecer estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="df864-108">The **IDBProperties::SetProperties** method is called to set these properties.</span></span>  
  
 <span data-ttu-id="df864-109">Si hay varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ejecutándose en el equipo, el nombre de servidor se especifica como ServerName\InstanceName.</span><span class="sxs-lookup"><span data-stu-id="df864-109">If there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer, the server name is specified as ServerName\InstanceName.</span></span>  
  
 <span data-ttu-id="df864-110">El objeto de origen de datos también expone la interfaz **IDBInitialize**.</span><span class="sxs-lookup"><span data-stu-id="df864-110">The data source object also exposes the **IDBInitialize** interface.</span></span> <span data-ttu-id="df864-111">Una vez establecidas las propiedades, se establece la conexión al origen de datos mediante una llamada al método **IDBInitialize::Initialize**.</span><span class="sxs-lookup"><span data-stu-id="df864-111">After the properties are set, connection to the data source is established by calling the **IDBInitialize::Initialize** method.</span></span> <span data-ttu-id="df864-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="df864-112">For example:</span></span>  
  
```  
CoCreateInstance(CLSID_SQLNCLI10,   
                 NULL,   
                 CLSCTX_INPROC_SERVER,  
                 IID_IDBInitialize,   
                 (void **) &pIDBInitialize)  
```  
  
 <span data-ttu-id="df864-113">Esta llamada a **CoCreateInstance** crea un único objeto de la clase asociada a CLSID_SQLNCLI10 (CSLID asociada a los datos y el código que se usarán para crear el objeto).</span><span class="sxs-lookup"><span data-stu-id="df864-113">This call to **CoCreateInstance** creates a single object of the class associated with CLSID_SQLNCLI10 (CSLID associated with the data and code that will be used to create the object).</span></span> <span data-ttu-id="df864-114">IID_IDBInitialize es una referencia al identificador de la interfaz (**IDBInitialize**) que se va a usar para comunicarse con el objeto.</span><span class="sxs-lookup"><span data-stu-id="df864-114">IID_IDBInitialize is a reference to the identifier of the interface (**IDBInitialize**) to be used to communicate with the object.</span></span>  
  
 <span data-ttu-id="df864-115">La siguiente es una función de ejemplo que inicializa y establece una conexión al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="df864-115">The following is a sample function that initializes and establishes a connection to the data source.</span></span>  
  
```  
void InitializeAndEstablishConnection() {  
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQL Server Native Client OLE DB provider.  
   hr = CoCreateInstance(CLSID_SQLNCLI10,   
                         NULL,   
                         CLSCTX_INPROC_SERVER,  
                         IID_IDBInitialize,   
                         (void **) &pIDBInitialize);  
   // Initialize property values needed to establish connection.  
   for (i = 0 ; i < 4 ; i++)   
      VariantInit(&InitProperties[i].vValue);  
  
   // Server name.  
   // See DBPROP structure for more information on InitProperties  
   InitProperties[0].dwPropertyID  = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt    = VT_BSTR;  
   InitProperties[0].vValue.bstrVal=   
                     SysAllocString(L"Server");  
   InitProperties[0].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid       = DB_NULLID;  
  
   // Database.  
   InitProperties[1].dwPropertyID  = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt    = VT_BSTR;  
   InitProperties[1].vValue.bstrVal= SysAllocString(L"database");  
   InitProperties[1].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid       = DB_NULLID;  
  
   // Username (login).  
   InitProperties[2].dwPropertyID  = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt    = VT_BSTR;  
   InitProperties[2].vValue.bstrVal= SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid       = DB_NULLID;  
   InitProperties[3].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[3].colid       = DB_NULLID;  
  
   // Construct the DBPROPSET structure(rgInitPropSet). The   
   // DBPROPSET structure is used to pass an array of DBPROP   
   // structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties   = 4;  
   rgInitPropSet[0].rgProperties   = InitProperties;  
  
   // Set initialization properties.  
   hr = pIDBInitialize->QueryInterface(IID_IDBProperties,   
                           (void **)&pIDBProperties);  
   hr = pIDBProperties->SetProperties(1, rgInitPropSet);   
   pIDBProperties->Release();  
  
   // Now establish the connection to the data source.  
   pIDBInitialize->Initialize();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="df864-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df864-116">See Also</span></span>  
 [<span data-ttu-id="df864-117">Crear una aplicación de proveedor OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="df864-117">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
