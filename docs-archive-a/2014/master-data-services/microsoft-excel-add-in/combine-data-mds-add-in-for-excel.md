---
title: Combinar datos (Complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: a867dc15-5a0d-457c-8304-ac323bcf9377
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bc2d5bffb6d7a12164a8643e9a790b32538f8979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745357"
---
# <a name="combine-data-mds-add-in-for-excel"></a><span data-ttu-id="4f29e-102">Combinar datos (Complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="4f29e-102">Combine Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="4f29e-103">En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], combine los datos de dos hojas de cálculo si desea comparar los datos antes de publicarlos.</span><span class="sxs-lookup"><span data-stu-id="4f29e-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], combine data from two worksheets when you want to compare data before publishing.</span></span> <span data-ttu-id="4f29e-104">En este procedimiento, se combinan los datos de dos hojas de cálculo en una.</span><span class="sxs-lookup"><span data-stu-id="4f29e-104">In this procedure, you combine data from a two worksheets into one.</span></span> <span data-ttu-id="4f29e-105">Puede realizar otras comparaciones y determinar qué datos publicar en el repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="4f29e-105">Then you can perform further comparisons and determine which data, if any, to publish to the MDS repository.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4f29e-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4f29e-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="4f29e-107">Debe tener una hoja de cálculo activa que contenga los datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="4f29e-107">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="4f29e-108">Para obtener más información, consulte [carga de datos de MDS en Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4f29e-108">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4f29e-109">Debe tener una hoja de cálculo que contenga los datos que desea combinar con los datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="4f29e-109">You must have a worksheet that contains data you want to combine with MDS-managed data.</span></span> <span data-ttu-id="4f29e-110">Esta hoja debe tener una fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="4f29e-110">This sheet must have a header row.</span></span>  
  
### <a name="to-combine-non-managed-data-into-an-mds-managed-sheet"></a><span data-ttu-id="4f29e-111">Para combinar los datos no administrados en una hoja administrada por MDS</span><span class="sxs-lookup"><span data-stu-id="4f29e-111">To combine non-managed data into an MDS-managed sheet</span></span>  
  
1.  <span data-ttu-id="4f29e-112">En la hoja que contiene los datos administrados por MDS, en el grupo **Publicar y validar** , haga clic en **Combinar datos**.</span><span class="sxs-lookup"><span data-stu-id="4f29e-112">On the sheet that contains MDS-managed data, in the **Publish and Validate** group, click **Combine Data**.</span></span>  
  
2.  <span data-ttu-id="4f29e-113">En el cuadro de diálogo **Combinar datos** , junto al cuadro de texto **Intervalo para combinar con los datos MDS** , haga clic en el icono.</span><span class="sxs-lookup"><span data-stu-id="4f29e-113">In the **Combine Data** dialog box, next to the **Range to combine with MDS data** text box, click the icon.</span></span> <span data-ttu-id="4f29e-114">El cuadro de diálogo se contrae.</span><span class="sxs-lookup"><span data-stu-id="4f29e-114">The dialog box contracts.</span></span>  
  
3.  <span data-ttu-id="4f29e-115">Haga clic en la hoja que contiene los datos que desea combinar.</span><span class="sxs-lookup"><span data-stu-id="4f29e-115">Click the sheet that contains the data you want to combine.</span></span>  
  
4.  <span data-ttu-id="4f29e-116">Resalte todas las celdas de la hoja que desea combinar, incluida la fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="4f29e-116">Highlight all cells on the sheet that you want to combine, including the header row.</span></span>  
  
5.  <span data-ttu-id="4f29e-117">En el cuadro de diálogo **Combinar datos** , haga clic en el icono.</span><span class="sxs-lookup"><span data-stu-id="4f29e-117">In the **Combine Data** dialog box, click the icon.</span></span> <span data-ttu-id="4f29e-118">El cuadro de diálogo se expande.</span><span class="sxs-lookup"><span data-stu-id="4f29e-118">The dialog box expands.</span></span>  
  
6.  <span data-ttu-id="4f29e-119">Para una columna enumerada para la entidad MDS, seleccione una columna debajo de **Columna correspondiente**.</span><span class="sxs-lookup"><span data-stu-id="4f29e-119">For a column listed for the MDS entity, select a column under **Corresponding Column**.</span></span> <span data-ttu-id="4f29e-120">Ninguna columna MDS necesita las columnas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4f29e-120">All MDS columns do not need corresponding columns.</span></span>  
  
7.  <span data-ttu-id="4f29e-121">Haga clic en **Combinar**.</span><span class="sxs-lookup"><span data-stu-id="4f29e-121">Click **Combine**.</span></span> <span data-ttu-id="4f29e-122">Se muestra una columna **SOURCE** , que indica si los datos son de MDS o un origen externo.</span><span class="sxs-lookup"><span data-stu-id="4f29e-122">A **SOURCE** column is displayed, indicating whether the data is from MDS or an external source.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4f29e-123">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4f29e-123">Next Steps</span></span>  
  
-   <span data-ttu-id="4f29e-124">Para buscar similitudes entre los datos administrados por MDS y los datos externos, vea [Coincidir datos similares &#40;Complemento MDS para Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="4f29e-124">To find similarities between the MDS-managed and external data, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f29e-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f29e-125">See Also</span></span>  
 <span data-ttu-id="4f29e-126">[Cargando datos &#40;Complemento MDS para Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="4f29e-126">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="4f29e-127">Coincidencia de calidad de datos en el Complemento MDS para Excel</span><span class="sxs-lookup"><span data-stu-id="4f29e-127">Data Quality Matching in the MDS Add-in for Excel</span></span>](data-quality-matching-in-the-mds-add-in-for-excel.md)  
  
  
