---
title: Propiedades de almacén de propiedades | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Income property
- InitialBonus property
- PercentScanPerPrice property
- FileStore properties
- BackgroundTrimCost property
- Tax property
- PerformanceTrace property
- MinimumBalance property
- UnbufferedThreshold property
- BackgroundTrimAmount property
- MaximumBalance property
- MemoryLimitMin property
- MemoryLimit property
ms.assetid: 580cf0aa-7425-4d48-aa8d-128f5b488fcd
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc81273b55dea5820ef80f34c22d293492eb8055
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752398"
---
# <a name="filestore-properties"></a><span data-ttu-id="4f9f9-102">Filestore, propiedades</span><span class="sxs-lookup"><span data-stu-id="4f9f9-102">Filestore Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="4f9f9-103">admite las propiedades del servidor de almacén de archivos que aparecen en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="4f9f9-103">supports the filestore server properties listed in the following tables.</span></span> <span data-ttu-id="4f9f9-104">Todas son propiedades avanzadas que no se deben cambiar, salvo bajo la orientación de soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-104">These are all advanced properties that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span> <span data-ttu-id="4f9f9-105">Para obtener más información sobre las propiedades de servidor adicionales y cómo establecerlas, vea [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="4f9f9-105">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="4f9f9-106">**Se aplica a:** modo de servidor multidimensional y tabular</span><span class="sxs-lookup"><span data-stu-id="4f9f9-106">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4f9f9-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4f9f9-107">Properties</span></span>  
 `MemoryLimit`  
 <span data-ttu-id="4f9f9-108">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-108">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryLimitMin`  
 <span data-ttu-id="4f9f9-109">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PercentScanPerPrice`  
 <span data-ttu-id="4f9f9-110">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PerformanceTrace`  
 <span data-ttu-id="4f9f9-111">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-111">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RandomFileAccessMode`  
 <span data-ttu-id="4f9f9-112">Una propiedad booleana que indica si se tiene acceso a los archivos de base de datos y a los archivos almacenados en memoria caché en modo de acceso a archivos aleatorio.</span><span class="sxs-lookup"><span data-stu-id="4f9f9-112">A Boolean property that indicates whether database files and cached files are accessed in random file access mode.</span></span> <span data-ttu-id="4f9f9-113">Esta propiedad está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4f9f9-113">This property is off by default.</span></span> <span data-ttu-id="4f9f9-114">De forma predeterminada, Analysis Services no establece la marca de acceso a archivos aleatorio al abrir los archivos de datos de partición para el acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="4f9f9-114">By default, Analysis Services does not set the random file access flag when opening partition data files for read access.</span></span>  
  
 <span data-ttu-id="4f9f9-115">En sistemas de tecnología avanzada, especialmente en aquellos con grandes recursos de memoria y varios nodos NUMA, puede ser ventajoso utilizar el acceso a archivos aleatorio.</span><span class="sxs-lookup"><span data-stu-id="4f9f9-115">On high-end systems, particularly those with large memory resources and multiple NUMA nodes, it can be advantageous to use random file access.</span></span> <span data-ttu-id="4f9f9-116">En modo de acceso aleatorio, Windows omite las operaciones de asignación de páginas que leen datos del disco en la memoria caché de archivos del sistema, con lo que reduce la contención en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4f9f9-116">In random access mode, Windows bypasses page mapping operations that read data from disk into the system file cache, thereby lowering contention on the cache.</span></span>  
  
 <span data-ttu-id="4f9f9-117">Tendrá que ejecutar pruebas comparativas para determinar si el rendimiento de las consultas mejora al cambiar esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="4f9f9-117">You will need to run comparison tests to determine whether query performance is improved as the result of changing this property.</span></span> <span data-ttu-id="4f9f9-118">Para obtener las prácticas recomendadas para realizar pruebas comparativas, como es borrar la memoria caché y evitar errores comunes, vea la [Guía de operaciones de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="4f9f9-118">For best practices on running comparison tests, including clearing the cache and avoiding common mistakes, see the [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span> <span data-ttu-id="4f9f9-119">Para obtener más información sobre los inconvenientes del uso de esta propiedad, vea [https://support.microsoft.com/kb/2549369](https://support.microsoft.com/kb/2549369) .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-119">For additional information on the tradeoffs of using this property, see [https://support.microsoft.com/kb/2549369](https://support.microsoft.com/kb/2549369).</span></span>  
  
 <span data-ttu-id="4f9f9-120">Para ver o modificar esta propiedad en Management Studio, habilite la lista de propiedades avanzadas en la página de propiedades del servidor.</span><span class="sxs-lookup"><span data-stu-id="4f9f9-120">To view or modify this property in Management Studio, enable the advanced properties list in the server properties page.</span></span> <span data-ttu-id="4f9f9-121">También puede cambiar la propiedad en el archivo msmdsrv.ini.</span><span class="sxs-lookup"><span data-stu-id="4f9f9-121">You can also change the property in the msmdsrv.ini file.</span></span> <span data-ttu-id="4f9f9-122">Se recomienda reiniciar el servidor después de establecer esta propiedad; en caso contrario, se seguirá accediendo a los archivos que ya estén abiertos en el modo anterior.</span><span class="sxs-lookup"><span data-stu-id="4f9f9-122">Restarting the server is recommended after setting this property; otherwise files that are already open will continue to be accessed in the previous mode.</span></span>  
  
 `UnbufferedThreshold`  
 <span data-ttu-id="4f9f9-123">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-123">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="memory-model-category"></a><span data-ttu-id="4f9f9-124">Categoría de modelo de memoria</span><span class="sxs-lookup"><span data-stu-id="4f9f9-124">Memory Model Category</span></span>  
 `MemoryModel\Tax`  
 <span data-ttu-id="4f9f9-125">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-125">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\Income`  
 <span data-ttu-id="4f9f9-126">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-126">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\MaximumBalance`  
 <span data-ttu-id="4f9f9-127">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-127">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\MinimumBalance`  
 <span data-ttu-id="4f9f9-128">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-128">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\InitialBonus`  
 <span data-ttu-id="4f9f9-129">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f9-129">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9f9-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f9f9-130">See Also</span></span>  
 <span data-ttu-id="4f9f9-131">[Configurar las propiedades del servidor en Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="4f9f9-131">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="4f9f9-132">Determinar el modo de servidor de una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4f9f9-132">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
