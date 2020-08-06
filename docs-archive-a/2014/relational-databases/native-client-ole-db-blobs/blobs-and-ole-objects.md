---
title: BLOB y objetos OLE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BLOBs, OLE objects
- BLOBs
- storage object [OLE DB]
- SQL Server Native Client OLE DB provider, BLOBs
- large data, OLE objects
ms.assetid: 767fa2f6-9cd2-436f-add5-e760bed29a58
author: rothja
ms.author: jroth
ms.openlocfilehash: 15f8b4915ba9b05a5be19854a2e27a2e8ff3a346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750822"
---
# <a name="blobs-and-ole-objects"></a><span data-ttu-id="853de-102">BLOB y objetos OLE</span><span class="sxs-lookup"><span data-stu-id="853de-102">BLOBs and OLE Objects</span></span>
  <span data-ttu-id="853de-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client expone la interfaz **ISequentialStream** para admitir el acceso de consumidor a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de datos **ntext**, **Text**, **Image**, **VARCHAR (Max)**, **nvarchar (Max)**, **varbinary (Max)** y XML como objetos binarios grandes (BLOB).</span><span class="sxs-lookup"><span data-stu-id="853de-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ISequentialStream** interface to support consumer access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **ntext**, **text**, **image**, **varchar(max)**, **nvarchar(max)**, **varbinary(max)**, and xml data types as binary large objects (BLOBs).</span></span> <span data-ttu-id="853de-104">El método **Read** de **ISequentialStream** permite al consumidor recuperar muchos datos en fragmentos fáciles de administrar.</span><span class="sxs-lookup"><span data-stu-id="853de-104">The **Read** method on **ISequentialStream** lets the consumer retrieve much data in manageable chunks.</span></span>  
  
 <span data-ttu-id="853de-105">Para obtener un ejemplo que muestra esta característica, consulte [Establecimiento de datos grandes &#40;OLE DB&#41;](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="853de-105">For a sample demonstrating this feature, see [Set Large Data &#40;OLE DB&#41;](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span></span>  
  
 <span data-ttu-id="853de-106">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client puede utilizar una interfaz **IStorage** implementada por el consumidor cuando el consumidor proporciona el puntero de interfaz en un descriptor de acceso enlazado para la modificación de datos.</span><span class="sxs-lookup"><span data-stu-id="853de-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can use a consumer-implemented **IStorage** interface when the consumer provides the interface pointer in an accessor bound for data modification.</span></span>  
  
 <span data-ttu-id="853de-107">En el caso de los tipos de datos de valores grandes, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client comprueba las suposiciones de tamaño de tipo en las interfaces **IROWSET** e DDL.</span><span class="sxs-lookup"><span data-stu-id="853de-107">For large value data types, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider checks for type size assumptions in **IRowset** and DDL interfaces.</span></span> <span data-ttu-id="853de-108">Las columnas con tipos de datos **VARCHAR**, **nvarchar**y **varbinary** con un tamaño máximo establecido en Unlimited se representarán como ISLONG a través de los conjuntos de filas de esquema e interfaces que devuelven tipos de datos de columna.</span><span class="sxs-lookup"><span data-stu-id="853de-108">Columns with **varchar**, **nvarchar**, and **varbinary** data types with max size set to unlimited will be represented as ISLONG through the schema rowsets and interfaces returning column data types.</span></span>  
  
 <span data-ttu-id="853de-109">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client expone los tipos **VARCHAR (Max)**, **varbinary (Max)** y **nvarchar (Max)** como DBTYPE_STR, DBTYPE_BYTES y DBTYPE_WSTR respectivamente.</span><span class="sxs-lookup"><span data-stu-id="853de-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **varchar(max)**, **varbinary(max)** and **nvarchar(max)** types as DBTYPE_STR, DBTYPE_BYTES and DBTYPE_WSTR respectively.</span></span>  
  
 <span data-ttu-id="853de-110">Para trabajar con estos tipos, una aplicación tiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="853de-110">To work with these types an application has the following options:</span></span>  
  
-   <span data-ttu-id="853de-111">Enlazar como el tipo (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span><span class="sxs-lookup"><span data-stu-id="853de-111">Bind as the type (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span></span> <span data-ttu-id="853de-112">Si el búfer no es suficientemente grande, se producirá un truncamiento, exactamente igual que ocurría con estos tipos en las versiones anteriores (aunque ahora hay valores mayores).</span><span class="sxs-lookup"><span data-stu-id="853de-112">If the buffer is not big enough truncation will occur, exactly as for these types in previous releases (although larger values are now available).</span></span>  
  
-   <span data-ttu-id="853de-113">Enlazar como el tipo y también especificar DBTYPE_BYREF.</span><span class="sxs-lookup"><span data-stu-id="853de-113">Bind as the type and also specify DBTYPE_BYREF.</span></span>  
  
-   <span data-ttu-id="853de-114">Enlazar como DBTYPE_IUNKNOWN y usar la transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="853de-114">Bind as DBTYPE_IUNKNOWN and use streaming.</span></span>  
  
 <span data-ttu-id="853de-115">Si se enlaza a DBTYPE_IUNKNOWN, se utiliza la funcionalidad de flujo de ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="853de-115">If bound to DBTYPE_IUNKNOWN, ISequentialStream stream functionality is used.</span></span> <span data-ttu-id="853de-116">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client admite parámetros de salida de enlace como DBTYPE_IUNKNOWN para tipos de datos de valores grandes con el fin de facilitar escenarios en los que un procedimiento almacenado devuelve estos tipos de datos como valores devueltos que se expondrán como DBTYPE_IUNKNOWN al cliente.</span><span class="sxs-lookup"><span data-stu-id="853de-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports binding output parameters as DBTYPE_IUNKNOWN for large value data types to facilitate scenarios where a stored procedure returns these data types as return values which will be exposed as DBTYPE_IUNKNOWN to the client.</span></span>  
  
## <a name="storage-object-limitations"></a><span data-ttu-id="853de-117">Limitaciones de los objetos de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="853de-117">Storage Object Limitations</span></span>  
  
-   <span data-ttu-id="853de-118">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client solo puede admitir un único objeto de almacenamiento abierto.</span><span class="sxs-lookup"><span data-stu-id="853de-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can support only a single open storage object.</span></span> <span data-ttu-id="853de-119">Cuando se intenta abrir más de un objeto de almacenamiento (para obtener una referencia en más de un puntero de interfaz **ISequentialStream**), se recibe DBSTATUS_E_CANTCREATE.</span><span class="sxs-lookup"><span data-stu-id="853de-119">Attempts to open more than one storage object (to get a reference on more than one **ISequentialStream** interface pointer) return DBSTATUS_E_CANTCREATE.</span></span>  
  
-   <span data-ttu-id="853de-120">En el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client, se VARIANT_TRUE el valor predeterminado de la propiedad DBPROP_BLOCKINGSTORAGEOBJECTS de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="853de-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the default value of the DBPROP_BLOCKINGSTORAGEOBJECTS read-only property is VARIANT_TRUE.</span></span> <span data-ttu-id="853de-121">Esto indica que si un objeto de almacenamiento está activo, algunos métodos (salvo en los que están en los objetos de almacenamiento) sufrirán un error con E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="853de-121">This indicates that if a storage object is active, some methods (other than those on the storage objects) will fail with E_UNEXPECTED.</span></span>  
  
-   <span data-ttu-id="853de-122">La longitud de los datos presentados por un objeto de almacenamiento implementado por el consumidor debe ser conocida por el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client cuando se crea el descriptor de acceso de fila que hace referencia al objeto de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="853de-122">The length of data presented by a consumer-implemented storage object must be made known to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider when the row accessor that references the storage object is created.</span></span> <span data-ttu-id="853de-123">El consumidor debe enlazar un indicador de longitud de la estructura DBBINDING que se utiliza para la creación del descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="853de-123">The consumer must bind a length indicator in the DBBINDING structure used for accessor creation.</span></span>  
  
-   <span data-ttu-id="853de-124">Si una fila contiene más de un valor de datos de gran tamaño y DBPROP_ACCESSORDER no es DBPROPVAL_AO_RANDOM, el consumidor debe usar un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjunto de filas compatible con cursores de proveedor de OLE DB de cliente nativo para recuperar los datos de fila o procesar todos los valores de datos grandes antes de recuperar otros valores de fila.</span><span class="sxs-lookup"><span data-stu-id="853de-124">If a row contains more than a single large data value and DBPROP_ACCESSORDER is not DBPROPVAL_AO_RANDOM, the consumer must either use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider cursor-supported rowset to retrieve row data or process all large data values before retrieving other row values.</span></span> <span data-ttu-id="853de-125">Si DBPROP_ACCESSORDER es DBPROPVAL_AO_RANDOM, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client almacena en caché todos los tipos de datos XML como objetos binarios grandes (BLOB) para que se pueda tener acceso a ellos en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="853de-125">If DBPROP_ACCESSORDER is DBPROPVAL_AO_RANDOM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider caches all the xml data types as binary large objects (BLOBs) so that it can be accessed in any order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="853de-126">En esta sección</span><span class="sxs-lookup"><span data-stu-id="853de-126">In This Section</span></span>  
  
-   [<span data-ttu-id="853de-127">Obtener datos grandes</span><span class="sxs-lookup"><span data-stu-id="853de-127">Getting Large Data</span></span>](getting-large-data.md)  
  
-   [<span data-ttu-id="853de-128">Definir datos grandes</span><span class="sxs-lookup"><span data-stu-id="853de-128">Setting Large Data</span></span>](setting-large-data.md)  
  
-   [<span data-ttu-id="853de-129">Compatibilidad con la transmisión por secuencias de parámetros de salida BLOB</span><span class="sxs-lookup"><span data-stu-id="853de-129">Streaming Support for BLOB Output Parameters</span></span>](streaming-support-for-blob-output-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="853de-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="853de-130">See Also</span></span>  
 <span data-ttu-id="853de-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="853de-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="853de-132">Usar tipos de valor grande</span><span class="sxs-lookup"><span data-stu-id="853de-132">Using Large Value Types</span></span>](../native-client/features/using-large-value-types.md)  
  
  
