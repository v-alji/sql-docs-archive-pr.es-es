---
title: Objetos de origen de datos (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], data source objects
- SQL Server Native Client, data source objects
- SQLNCLI, data source objects
- SQL Server Native Client OLE DB provider, data source objects
- OLE DB data source objects [SQL Server Native Client]
- data source objects [OLE DB]
- CLSID
ms.assetid: c1d4ed20-ad3b-4e33-a26b-38d7517237b7
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cf3f0b0308d655b50149c174547c19966f550ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744072"
---
# <a name="data-source-objects-ole-db"></a><span data-ttu-id="da118-102">Objetos de origen de datos (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="da118-102">Data Source Objects (OLE DB)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="da118-103">Native Client usa el término origen de datos para el conjunto de interfaces OLE DB utilizadas para establecer un vínculo a un almacén de datos, como [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da118-103">Native Client uses the term data source for the set of OLE DB interfaces used to establish a link to a data store, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="da118-104">Crear una instancia del objeto de origen de datos del proveedor es la primera tarea de un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor de Native Client.</span><span class="sxs-lookup"><span data-stu-id="da118-104">Creating an instance of the data source object of the provider is the first task of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client consumer.</span></span>  
  
 <span data-ttu-id="da118-105">Todos los proveedores OLE DB declaran un identificador de clase (CLSID) para sí mismo.</span><span class="sxs-lookup"><span data-stu-id="da118-105">Every OLE DB provider declares a class identifier (CLSID) for itself.</span></span> <span data-ttu-id="da118-106">El CLSID del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client es el GUID de C/C++ CLSID_SQLNCLI10 (el símbolo SQLNCLI_CLSID se resolverá en el ProgID correcto del archivo SQLNCLI. h al que haga referencia).</span><span class="sxs-lookup"><span data-stu-id="da118-106">The CLSID for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is the C/C++ GUID CLSID_SQLNCLI10 (the symbol SQLNCLI_CLSID will resolve to the correct progid in the sqlncli.h file that you reference).</span></span> <span data-ttu-id="da118-107">Con el CLSID, el consumidor usa la función de OLE **CoCreateInstance** para fabricar una instancia del objeto de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="da118-107">With the CLSID, the consumer uses the OLE **CoCreateInstance** function to manufacture an instance of the data source object.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="da118-108">Native Client es un servidor en proceso.</span><span class="sxs-lookup"><span data-stu-id="da118-108">Native Client is an in-process server.</span></span> <span data-ttu-id="da118-109">Las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objetos de proveedor de OLE DB de Native Client se crean mediante la macro CLSCTX_INPROC_SERVER para indicar el contexto ejecutable.</span><span class="sxs-lookup"><span data-stu-id="da118-109">Instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider objects are created using the CLSCTX_INPROC_SERVER macro to indicate the executable context.</span></span>  
  
 <span data-ttu-id="da118-110">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objeto de origen de datos del proveedor de OLE DB de Native Client expone las interfaces de inicialización OLE DB que permiten al consumidor conectarse a las bases de datos existentes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da118-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object exposes the OLE DB initialization interfaces that allow the consumer to connect to existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="da118-111">Cada conexión realizada a través del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client establece estas opciones automáticamente:</span><span class="sxs-lookup"><span data-stu-id="da118-111">Every connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets these options automatically:</span></span>  
  
-   <span data-ttu-id="da118-112">SET ANSI_WARNINGS ON</span><span class="sxs-lookup"><span data-stu-id="da118-112">SET ANSI_WARNINGS ON</span></span>  
  
-   <span data-ttu-id="da118-113">SET ANSI_NULLS ON</span><span class="sxs-lookup"><span data-stu-id="da118-113">SET ANSI_NULLS ON</span></span>  
  
-   <span data-ttu-id="da118-114">SET ANSI_PADDING ON</span><span class="sxs-lookup"><span data-stu-id="da118-114">SET ANSI_PADDING ON</span></span>  
  
-   <span data-ttu-id="da118-115">SET ANSI_NULL_DFLT_ON ON</span><span class="sxs-lookup"><span data-stu-id="da118-115">SET ANSI_NULL_DFLT_ON ON</span></span>  
  
-   <span data-ttu-id="da118-116">SET QUOTED_IDENTIFIER ON</span><span class="sxs-lookup"><span data-stu-id="da118-116">SET QUOTED_IDENTIFIER ON</span></span>  
  
-   <span data-ttu-id="da118-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span><span class="sxs-lookup"><span data-stu-id="da118-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span></span>  
  
 <span data-ttu-id="da118-118">En este ejemplo se usa la macro de identificador de clase para crear un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objeto de origen de datos del proveedor de OLE DB de cliente nativo y obtener una referencia a su interfaz **IDBInitialize** .</span><span class="sxs-lookup"><span data-stu-id="da118-118">This example uses the class identifier macro to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object and get a reference to its **IDBInitialize** interface.</span></span>  
  
```  
IDBInitialize*   pIDBInitialize;  
HRESULT          hr;  
  
hr = CoCreateInstance(CLSID_SQLNCLI10, NULL, CLSCTX_INPROC_SERVER,  
    IID_IDBInitialize, (void**) &pIDBInitialize);  
  
if (SUCCEEDED(hr))  
{  
    //  Perform necessary processing with the interface.  
    pIDBInitialize->Uninitialize();  
    pIDBInitialize->Release();  
}  
else  
{  
    // Display error from CoCreateInstance.  
}  
```  
  
 <span data-ttu-id="da118-119">Al crear correctamente una instancia de un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objeto de origen de datos del proveedor de OLE DB de Native Client, la aplicación de consumidor puede continuar inicializando el origen de datos y creando sesiones.</span><span class="sxs-lookup"><span data-stu-id="da118-119">With successful creation of an instance of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object, the consumer application can continue by initializing the data source and creating sessions.</span></span> <span data-ttu-id="da118-120">Las sesiones OLE DB presentan las interfaces que permiten manipulación y acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="da118-120">OLE DB sessions present the interfaces that allow data access and manipulation.</span></span>  
  
 <span data-ttu-id="da118-121">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client realiza su primera conexión a una instancia especificada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como parte de una inicialización de origen de datos correcta.</span><span class="sxs-lookup"><span data-stu-id="da118-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider makes its first connection to a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as part of a successful data source initialization.</span></span> <span data-ttu-id="da118-122">Se mantiene la conexión siempre que se mantenga una referencia en cualquier interfaz de inicialización de origen de datos, o hasta que se llame al método **IDBInitialize::Uninitialize**.</span><span class="sxs-lookup"><span data-stu-id="da118-122">The connection is maintained as long as a reference is maintained on any data source initialization interface, or until the **IDBInitialize::Uninitialize** method is called.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da118-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="da118-123">In This Section</span></span>  
  
-   [<span data-ttu-id="da118-124">Propiedades del origen de datos &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="da118-124">Data Source Properties &#40;OLE DB&#41;</span></span>](data-source-properties-ole-db.md)  
  
-   [<span data-ttu-id="da118-125">Propiedades de información de orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="da118-125">Data Source Information Properties</span></span>](data-source-information-properties.md)  
  
-   [<span data-ttu-id="da118-126">Propiedades de inicialización y autorización</span><span class="sxs-lookup"><span data-stu-id="da118-126">Initialization and Authorization Properties</span></span>](initialization-and-authorization-properties.md)  
  
-   [<span data-ttu-id="da118-127">Sesiones</span><span class="sxs-lookup"><span data-stu-id="da118-127">Sessions</span></span>](sessions.md)  
  
-   [<span data-ttu-id="da118-128">Propiedades de sesión</span><span class="sxs-lookup"><span data-stu-id="da118-128">Session Properties</span></span>](session-properties-sql-server-native-client-ole-db-provider.md)  
  
-   [<span data-ttu-id="da118-129">Objetos de origen de datos persistentes</span><span class="sxs-lookup"><span data-stu-id="da118-129">Persisted Data Source Objects</span></span>](persisted-data-source-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="da118-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da118-130">See Also</span></span>  
 [<span data-ttu-id="da118-131">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="da118-131">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
