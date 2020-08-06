---
title: Ubicaciones de procesamiento y almacenamiento (Asistente para particiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifyprocessingandstorage.f1
ms.assetid: dda2dc57-923d-4db9-93a7-38e95770f3df
author: minewiskan
ms.author: owend
ms.openlocfilehash: 00ab88bac184f57bd2b4dcfdb8d00909a85ece4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750250"
---
# <a name="processing-and-storage-locations-partition-wizard"></a><span data-ttu-id="09739-102">Ubicaciones de procesamiento y almacenamiento (Asistente para particiones)</span><span class="sxs-lookup"><span data-stu-id="09739-102">Processing and Storage Locations (Partition Wizard)</span></span>
  <span data-ttu-id="09739-103">Use la página **Ubicaciones de procesamiento y almacenamiento** para especificar la instancia de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] del cubo propietario de la partición, así como la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que almacena los datos para la partición.</span><span class="sxs-lookup"><span data-stu-id="09739-103">Use the **Processing and Storage Locations** page to specify the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance of the cube that owns the partition, as well as the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that stores the data for the partition.</span></span> <span data-ttu-id="09739-104">Puede definir una partición como remota si especifica una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] remota o una ubicación de almacenamiento distinta de la ubicación de almacenamiento predeterminada.</span><span class="sxs-lookup"><span data-stu-id="09739-104">You can define a partition as a remote partition by specifying either a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a storage location other than the default storage location.</span></span> <span data-ttu-id="09739-105">Para más información sobre las particiones remotas, vea [Particiones remotas](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="09739-105">For more information about remote partitions, see [Remote Partitions](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span></span>  
  
## <a name="processing-location-options"></a><span data-ttu-id="09739-106">Opciones de ubicación de procesamiento</span><span class="sxs-lookup"><span data-stu-id="09739-106">Processing location Options</span></span>  
 <span data-ttu-id="09739-107">**Instancia de servidor actual**</span><span class="sxs-lookup"><span data-stu-id="09739-107">**Current server instance**</span></span>  
 <span data-ttu-id="09739-108">Hace a la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] actual responsable de procesar la partición.</span><span class="sxs-lookup"><span data-stu-id="09739-108">Makes the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
 <span data-ttu-id="09739-109">**Origen de datos remoto de Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="09739-109">**Remote Analysis Services data source**</span></span>  
 <span data-ttu-id="09739-110">Convierte a una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] remota responsable de procesar esta partición.</span><span class="sxs-lookup"><span data-stu-id="09739-110">Makes a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing this partition.</span></span>  
  
 <span data-ttu-id="09739-111">En la lista desplegable, seleccione el origen de datos que representa la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] remota responsable de procesar la partición.</span><span class="sxs-lookup"><span data-stu-id="09739-111">From the dropdown list, select the data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that will be responsible for processing the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09739-112">Se producirá un error si selecciona un origen de datos en el que la propiedad de la cadena de conexión del `Initial Catalog` no está definida para una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] válida, o si la base de datos especificada en la propiedad de la cadena de conexión del `Initial Catalog` no admite particiones remotas (en otras palabras, la propiedad `MasterDatasourceID` de la base de datos especificada no se ha configurado con un valor válido).</span><span class="sxs-lookup"><span data-stu-id="09739-112">An error occurs if you select a data source in which the `Initial Catalog` connection string property is not set to a valid [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, or if the database specified in the `Initial Catalog` connection string property does not support remote partitions (in other words, the `MasterDatasourceID` property of the specified database is not set to a valid value).</span></span>  
  
 <span data-ttu-id="09739-113">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="09739-113">**New**</span></span>  
 <span data-ttu-id="09739-114">Crea un nuevo origen de datos que representa la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] remota responsable de procesar la partición.</span><span class="sxs-lookup"><span data-stu-id="09739-114">Creates a new data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
## <a name="storage-location-options"></a><span data-ttu-id="09739-115">Opciones de ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="09739-115">Storage location Options</span></span>  
 <span data-ttu-id="09739-116">**Ubicación de servidor predeterminada**</span><span class="sxs-lookup"><span data-stu-id="09739-116">**Default server location**</span></span>  
 <span data-ttu-id="09739-117">Convierte la carpeta de datos de la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] actual en la ubicación de almacenamiento de los datos de indización y agregación de la partición.</span><span class="sxs-lookup"><span data-stu-id="09739-117">Makes the data folder of the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="09739-118">**Carpeta especificada**</span><span class="sxs-lookup"><span data-stu-id="09739-118">**Specified folder**</span></span>  
 <span data-ttu-id="09739-119">Especifica la ubicación de almacenamiento de los datos de agregación e indización de la partición.</span><span class="sxs-lookup"><span data-stu-id="09739-119">Specifies the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="09739-120">**...**</span><span class="sxs-lookup"><span data-stu-id="09739-120">**...**</span></span>  
 <span data-ttu-id="09739-121">Muestra el cuadro de diálogo **Buscar carpeta remota** en el que se puede seleccionar una carpeta para **Carpeta especificada**.</span><span class="sxs-lookup"><span data-stu-id="09739-121">Displays the **Browse for Remote Folder** dialog box in which you can select a folder for **Specified folder**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09739-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09739-122">See Also</span></span>  
 <span data-ttu-id="09739-123">[Asistente para particiones ayuda F1 &#40;Analysis Services-datos multidimensionales&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="09739-123">[Partition Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="09739-124">[Particiones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="09739-124">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="09739-125">Cuadro de diálogo Buscar carpeta remota &#40;Analysis Services-datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="09739-125">Browse for Remote Folder Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md)  
  
  
