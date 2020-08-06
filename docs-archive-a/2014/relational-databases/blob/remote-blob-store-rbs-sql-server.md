---
title: Almacén remoto de blobs (RBS) (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- Remote Blob Store (RBS) [SQL Server]
- RBS (Remote Blob Store) [SQL Server]
ms.assetid: 31c947cf-53e9-4ff4-939b-4c1d034ea5b1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8f3425474ec3b9013355536424ffcf55d9426b9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744142"
---
# <a name="remote-blob-store-rbs-sql-server"></a><span data-ttu-id="b7741-102">Remote Blob Store (RBS) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b7741-102">Remote Blob Store (RBS) (SQL Server)</span></span>
  <span data-ttu-id="b7741-103">El almacén remoto de blobs RBS de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es un componente complementario opcional que permite a los administradores de bases de datos almacenar directamente objetos binarios grandes en soluciones de almacenamiento de artículos en lugar de en el servidor de base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="b7741-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Remote BLOB Store (RBS) is an optional add-on component that lets database administrators store binary large objects in commodity storage solutions instead of directly on the main database server.</span></span>  
  
 <span data-ttu-id="b7741-104">RBS se incluye en el disco de instalación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pero no lo instala el programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7741-104">RBS is included on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation media, but is not installed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program.</span></span>  
  
 <span data-ttu-id="b7741-105">Para obtener más información acerca de RBS, vea [RBS Resources](#rbsresources) en este tema.</span><span class="sxs-lookup"><span data-stu-id="b7741-105">For more information about RBS, see [RBS Resources](#rbsresources) in this topic.</span></span>  
  
## <a name="benefits-of-rbs"></a><span data-ttu-id="b7741-106">Ventajas de RBS</span><span class="sxs-lookup"><span data-stu-id="b7741-106">Benefits of RBS</span></span>  
 <span data-ttu-id="b7741-107">RBS proporciona las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="b7741-107">RBS provides the following benefits:</span></span>  
  
### <a name="optimized-database-storage-and-performance"></a><span data-ttu-id="b7741-108">Rendimiento y almacenamiento de base de datos optimizados</span><span class="sxs-lookup"><span data-stu-id="b7741-108">Optimized database storage and performance</span></span>  
 <span data-ttu-id="b7741-109">Si se almacenan los blobs en la base de datos, puede usarse una gran cantidad de espacio en los archivos y caros recursos del servidor.</span><span class="sxs-lookup"><span data-stu-id="b7741-109">Storing BLOBs in the database can consume large amounts of file space and expensive server resources.</span></span> <span data-ttu-id="b7741-110">RBS transfiere eficazmente los blobs a la solución de almacenamiento especializada que prefiera y almacena las referencias a los mismos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b7741-110">RBS efficiently transfers the BLOBs to a dedicated storage solution of your choosing, and stores references to them in the database.</span></span> <span data-ttu-id="b7741-111">Esto libera almacenamiento en el servidor para los datos estructurados y también recursos del servidor para las operaciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b7741-111">This frees server storage for structured data, and frees server resources for database operations.</span></span>  
  
### <a name="efficient-management-of-blobs"></a><span data-ttu-id="b7741-112">Una administración eficaz de los blobs</span><span class="sxs-lookup"><span data-stu-id="b7741-112">Efficient management of BLOBs</span></span>  
 <span data-ttu-id="b7741-113">Varias características de RBS permiten una cómoda administración de los blobs almacenados:</span><span class="sxs-lookup"><span data-stu-id="b7741-113">Several RBS features support the convenient management of stored BLOBs:</span></span>  
  
-   <span data-ttu-id="b7741-114">Los blobs se administran con transacciones duraderas de aislamiento atómico de coherencia (ACID).</span><span class="sxs-lookup"><span data-stu-id="b7741-114">BLOBS are managed with ACID (atomic consistency isolation durable) transactions.</span></span>  
  
-   <span data-ttu-id="b7741-115">Los blobs se organizan en colecciones.</span><span class="sxs-lookup"><span data-stu-id="b7741-115">BLOBs are organized into collections.</span></span>  
  
-   <span data-ttu-id="b7741-116">Se incluyen la recolección de elementos no utilizados, la comprobación de la coherencia y otras funciones de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b7741-116">Garbage collection, consistency checking, and other maintenance functions are included.</span></span>  
  
### <a name="standardized-api"></a><span data-ttu-id="b7741-117">API normalizada</span><span class="sxs-lookup"><span data-stu-id="b7741-117">Standardized API</span></span>  
 <span data-ttu-id="b7741-118">RBS define un conjunto de API que proporcionan un modelo de programación normalizado para que las aplicaciones obtengan acceso y modifiquen almacenes de blobs.</span><span class="sxs-lookup"><span data-stu-id="b7741-118">RBS defines a set of APIs that provide a standardized programming model for applications to access and modify any BLOB store.</span></span> <span data-ttu-id="b7741-119">Cada almacén de blobs puede especificar su propia biblioteca de proveedores, que se conecta a la biblioteca cliente de RBS y especifica cómo se almacenan los blobs y cómo se accede a ellos.</span><span class="sxs-lookup"><span data-stu-id="b7741-119">Each BLOB store can specify its own provider library, which plugs into the RBS client library and specifies how BLOBs are stored and accessed.</span></span>  
  
 <span data-ttu-id="b7741-120">Varios proveedores de soluciones de almacenamiento han desarrollado proveedores RBS que se ajustan a estas API estándar y son compatibles con el almacenamiento de blobs en varias plataformas de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b7741-120">A number of third-party storage solution vendors have developed RBS providers that conform to these standard APIs and support BLOB storage on various storage platforms.</span></span>  
  
## <a name="rbs-requirements"></a><span data-ttu-id="b7741-121">Requisitos de RBS</span><span class="sxs-lookup"><span data-stu-id="b7741-121">RBS Requirements</span></span>  
 <span data-ttu-id="b7741-122">RBS requiere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise para el servidor de base de datos principal en el que se almacenan los metadatos de los blobs.</span><span class="sxs-lookup"><span data-stu-id="b7741-122">RBS requires [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise for the main database server in which the BLOB metadata is stored.</span></span> <span data-ttu-id="b7741-123">Sin embargo, si usa el proveedor FILESTREAM suministrado, puede almacenar los propios blobs en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard.</span><span class="sxs-lookup"><span data-stu-id="b7741-123">However, if you use the supplied FILESTREAM provider, you can store the BLOBs themselves on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard.</span></span>  
  
 <span data-ttu-id="b7741-124">RBS incluye un proveedor FILESTREAM que permite usar RBS para almacenar los blobs en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7741-124">RBS includes a FILESTREAM provider that lets you use RBS to store BLOBs on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b7741-125">Si desea usar RBS para almacenar los blobs en una solución de almacenamiento diferente, tiene que usar un proveedor RBS de terceros desarrollado para dicha solución de almacenamiento o desarrollar un proveedor RBS personalizado con la API RBS.</span><span class="sxs-lookup"><span data-stu-id="b7741-125">If you want use RBS to store BLOBs in a different storage solution, you have to use a third party RBS provider developed for that storage solution, or develop a custom RBS provider using the RBS API.</span></span> <span data-ttu-id="b7741-126">En [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190)hay disponible como recurso de aprendizaje un ejemplo de proveedor que almacena los blobs en el sistema de archivos NTFS.</span><span class="sxs-lookup"><span data-stu-id="b7741-126">A sample provider that stores BLOBs in the NTFS file system is available as a learning resource on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190).</span></span>  
  
## <a name="rbs-security"></a><span data-ttu-id="b7741-127">Seguridad de RBS</span><span class="sxs-lookup"><span data-stu-id="b7741-127">RBS Security</span></span>  
 <span data-ttu-id="b7741-128">Cuando usa un proveedor personalizado para almacenar los blobs fuera de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], pueden estar disponibles para otros procesos que omiten el sistema de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7741-128">When you use a custom provider to store BLOBs outside of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], they may be available to other processes that bypass the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security system.</span></span> <span data-ttu-id="b7741-129">Asegúrese de que protege los blobs almacenados con opciones de cifrado y permisos apropiados para el medio de almacenamiento que use el proveedor personalizado.</span><span class="sxs-lookup"><span data-stu-id="b7741-129">Make sure that you protect the stored BLOBs with permissions and encryption options that are appropriate to the storage medium used by the custom provider.</span></span>  
  
##  <a name="rbs-resources"></a><a name="rbsresources"></a><span data-ttu-id="b7741-130">Recursos de RBS</span><span class="sxs-lookup"><span data-stu-id="b7741-130">RBS Resources</span></span>  
 <span data-ttu-id="b7741-131">**Documentación de RBS**</span><span class="sxs-lookup"><span data-stu-id="b7741-131">**RBS documentation**</span></span>  
 <span data-ttu-id="b7741-132">La documentación de RBS se incluye en el paquete del programa de instalación de Windows.</span><span class="sxs-lookup"><span data-stu-id="b7741-132">The RBS documentation is included in the Windows installer package.</span></span> <span data-ttu-id="b7741-133">Si desea examinar la documentación de RBS sin instalarlo, puede ver la versión de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] de la documentación [en línea en MSDN Library](https://go.microsoft.com/fwlink/?LinkId=210192).</span><span class="sxs-lookup"><span data-stu-id="b7741-133">If you want to review the RBS documentation without installing RBS, you can view the [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] version of the documentation [online in the MSDN Library](https://go.microsoft.com/fwlink/?LinkId=210192).</span></span>  
  
 <span data-ttu-id="b7741-134">**Notas del producto de RBS**</span><span class="sxs-lookup"><span data-stu-id="b7741-134">**RBS white paper**</span></span>  
 <span data-ttu-id="b7741-135">En las notas del producto "[Almacenamiento remoto de blobs](https://go.microsoft.com/fwlink/?LinkId=210422)", que pueden descargarse como documento de Microsoft Word, se proporciona información detallada acerca de la instalación y configuración de RBS.</span><span class="sxs-lookup"><span data-stu-id="b7741-135">The white paper "[Remote BLOB Storage](https://go.microsoft.com/fwlink/?LinkId=210422)", which is available for download as a Microsoft Word document, provides detailed information about installing and configuring RBS.</span></span>  
  
 <span data-ttu-id="b7741-136">**Ejemplos de RBS**</span><span class="sxs-lookup"><span data-stu-id="b7741-136">**RBS samples**</span></span>  
 <span data-ttu-id="b7741-137">Los ejemplos de RBS disponibles en [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190) demuestran cómo desarrollar una aplicación de RBS y cómo desarrollar e instalar un proveedor de RBS personalizado.</span><span class="sxs-lookup"><span data-stu-id="b7741-137">The RBS samples available on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190) demonstrate how to develop an RBS application, and how to develop and install a custom RBS provider.</span></span>  
  
 <span data-ttu-id="b7741-138">**Blog de RBS**</span><span class="sxs-lookup"><span data-stu-id="b7741-138">**RBS blog**</span></span>  
 <span data-ttu-id="b7741-139">En el [blog de RBS](https://go.microsoft.com/fwlink/?LinkId=210315) se proporciona información adicional para ayudarle a entender, implementar y mantener RBS.</span><span class="sxs-lookup"><span data-stu-id="b7741-139">The [RBS blog](https://go.microsoft.com/fwlink/?LinkId=210315) provides additional information to help you understand, deploy, and maintain RBS.</span></span>  
  
  
