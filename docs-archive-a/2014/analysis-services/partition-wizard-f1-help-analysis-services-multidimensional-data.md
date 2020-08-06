---
title: Asistente para particiones (ayuda F1) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Partition Wizard
ms.assetid: 3b6d7053-aeef-4d9e-af70-f5b40256e859
author: minewiskan
ms.author: owend
ms.openlocfilehash: fa8c0e94c2b18ffbd1228752bd7cb4ad4f684acb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670639"
---
# <a name="partition-wizard-f1-help-analysis-services---multidimensional-data"></a><span data-ttu-id="1f477-102">Asistente para particiones (Ayuda F1) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="1f477-102">Partition Wizard F1 Help (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="1f477-103">El Asistente para particiones sirve para definir particiones para un grupo de medida de un cubo.</span><span class="sxs-lookup"><span data-stu-id="1f477-103">You can use the Partition Wizard to define partitions for a measure group in a cube.</span></span> <span data-ttu-id="1f477-104">De forma predeterminada, se define una sola partición para cada grupo de medida de un cubo.</span><span class="sxs-lookup"><span data-stu-id="1f477-104">By default, a single partition is defined for each measure group in a cube.</span></span> <span data-ttu-id="1f477-105">No obstante, el rendimiento de acceso y de procesamiento pueden degradarse en particiones grandes.</span><span class="sxs-lookup"><span data-stu-id="1f477-105">Access and processing performance, however, can degrade for large partitions.</span></span> <span data-ttu-id="1f477-106">Creando varias particiones, cada una con una parte de los datos de un grupo de medida, el rendimiento de acceso y de procesamiento pueden mejorarse para dicho grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="1f477-106">By creating multiple partitions, each containing a portion of the data for a measure group, you can improve the access and processing performance for that measure group.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1f477-107">Se pueden crear particiones que pueden contener datos erróneos si se incluyen filas duplicadas en las páginas **Especificar información de origen** o **Restringir filas** .</span><span class="sxs-lookup"><span data-stu-id="1f477-107">It is possible to create partitions that may contain incorrect data by including duplicate rows in the **Specify Source Information** or **Restrict Rows** pages.</span></span>  
  
 <span data-ttu-id="1f477-108">El Asistente para particiones le guía por los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="1f477-108">The Partition Wizard guides you through the following steps:</span></span>  
  
-   <span data-ttu-id="1f477-109">Seleccionar la vista del origen de datos de la partición.</span><span class="sxs-lookup"><span data-stu-id="1f477-109">Selecting the data source view for the partition.</span></span>  
  
-   <span data-ttu-id="1f477-110">Crear un filtro para los registros incluidos en la partición.</span><span class="sxs-lookup"><span data-stu-id="1f477-110">Creating a filter for the records included in the partition.</span></span>  
  
-   <span data-ttu-id="1f477-111">Establecer las ubicaciones de procesamiento y almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="1f477-111">Setting the processing and storage locations.</span></span>  
  
-   <span data-ttu-id="1f477-112">Asignar un nombre a la partición y guardarla.</span><span class="sxs-lookup"><span data-stu-id="1f477-112">Naming and saving the partition.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f477-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1f477-113">In This Section</span></span>  
  
-   [<span data-ttu-id="1f477-114">Especificar información de origen &#40;Asistente para particiones&#41;</span><span class="sxs-lookup"><span data-stu-id="1f477-114">Specify Source Information &#40;Partition Wizard&#41;</span></span>](specify-source-information-partition-wizard.md)  
  
-   [<span data-ttu-id="1f477-115">Restringir filas &#40;Asistente para particiones&#41;</span><span class="sxs-lookup"><span data-stu-id="1f477-115">Restrict Rows &#40;Partition Wizard&#41;</span></span>](restrict-rows-partition-wizard.md)  
  
-   [<span data-ttu-id="1f477-116">Ubicaciones de procesamiento y almacenamiento &#40;Asistente para particiones&#41;</span><span class="sxs-lookup"><span data-stu-id="1f477-116">Processing and Storage Locations &#40;Partition Wizard&#41;</span></span>](processing-and-storage-locations-partition-wizard.md)  
  
-   [<span data-ttu-id="1f477-117">Finalización del asistente &#40;Asistente para particiones&#41;</span><span class="sxs-lookup"><span data-stu-id="1f477-117">Completing the Wizard &#40;Partition Wizard&#41;</span></span>](completing-the-wizard-partition-wizard.md)  
  
-   [<span data-ttu-id="1f477-118">Cuadro de diálogo Buscar carpeta remota &#40;Analysis Services-datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="1f477-118">Browse for Remote Folder Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md)  
  
## <a name="see-also"></a><span data-ttu-id="1f477-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f477-119">See Also</span></span>  
 [<span data-ttu-id="1f477-120">Particiones &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="1f477-120">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
