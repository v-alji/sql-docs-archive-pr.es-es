---
title: Filtrar datos antes de cargarlos (Complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9e30eae0-776b-4a09-aac3-0c0249d92ca5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6d0ccf667f37763326e27dcd8d0cfc005627ebc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745858"
---
# <a name="filter-data-before-loading-mds-add-in-for-excel"></a><span data-ttu-id="caa38-102">Filtrar datos antes de cargarlos (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="caa38-102">Filter Data before Loading (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="caa38-103">En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] , filtre los datos si desea limitar el tamaño o el ámbito de los datos que va a cargar en Excel.</span><span class="sxs-lookup"><span data-stu-id="caa38-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], filter data when you want to limit the size or scope of data that you are loading into Excel.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="caa38-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="caa38-104">Prerequisites</span></span>  
 <span data-ttu-id="caa38-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="caa38-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="caa38-106">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="caa38-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-filter-data-before-loading"></a><span data-ttu-id="caa38-107">Para filtrar datos antes de cargarlos</span><span class="sxs-lookup"><span data-stu-id="caa38-107">To filter data before loading</span></span>  
  
1.  <span data-ttu-id="caa38-108">Abra Excel y, en la pestaña **Datos maestros** , conéctese a un repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="caa38-108">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="caa38-109">Para obtener más información, consulte [Conectarse a un repositorio MDS &#40;complemento MDS para Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="caa38-109">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="caa38-110">En el panel **Explorador de datos maestros** , seleccione un modelo y una versión.</span><span class="sxs-lookup"><span data-stu-id="caa38-110">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="caa38-111">La lista de entidades se rellena.</span><span class="sxs-lookup"><span data-stu-id="caa38-111">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="caa38-112">Si el panel **Explorador de datos maestros** no está visible, en el grupo **Conectar y cargar** , haga clic en **Mostrar explorador**.</span><span class="sxs-lookup"><span data-stu-id="caa38-112">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="caa38-113">Si el panel **Explorador de datos maestros** está deshabilitado, se debe a que la hoja existente ya contiene datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="caa38-113">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="caa38-114">Para habilitar el panel, abra una nueva hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="caa38-114">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="caa38-115">En el panel **Explorador de datos maestros** , en la lista de entidades, haga clic en la entidad que desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="caa38-115">In the **Master Data Explorer** pane, in the list of entities, click the entity you want to filter.</span></span>  
  
4.  <span data-ttu-id="caa38-116">En la cinta de opciones, en el grupo **Conectar y cargar** , haga clic en **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="caa38-116">On the ribbon, in the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="caa38-117">Para completar el cuadro de diálogo **Filtro** , seleccione los atributos (columnas) para mostrar, establecer el orden de las columnas y, si es necesario, filtrar los datos de modo que se devuelvan menos filas.</span><span class="sxs-lookup"><span data-stu-id="caa38-117">Complete the **Filter** dialog box by selecting the attributes (columns) to display, setting the order of the columns, and if needed, filtering the data so fewer rows are returned.</span></span> <span data-ttu-id="caa38-118">Vea en el panel **Resumen** cuántos datos se devolverán.</span><span class="sxs-lookup"><span data-stu-id="caa38-118">View the **Summary** pane for how much data will be returned.</span></span> <span data-ttu-id="caa38-119">Para más información, vea [Cuadro de diálogo Filtrar &#40;Complemento MDS para Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="caa38-119">For more information, see [Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md).</span></span>  
  
6.  <span data-ttu-id="caa38-120">Haga clic en **Cargar datos**.</span><span class="sxs-lookup"><span data-stu-id="caa38-120">Click **Load Data**.</span></span> <span data-ttu-id="caa38-121">La hoja se rellena con datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="caa38-121">The sheet is populated with MDS-managed data.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="caa38-122">Solo se carga en Excel el primer millón de miembros.</span><span class="sxs-lookup"><span data-stu-id="caa38-122">Only the first one million members are loaded into Excel.</span></span>  
    > -   <span data-ttu-id="caa38-123">En las columnas que son listas restringidas (atributos basados en dominio), solo se cargan los primeros 1000.</span><span class="sxs-lookup"><span data-stu-id="caa38-123">In columns that are constrained lists (domain-based attributes), only the first 1000 values are loaded.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="caa38-124">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="caa38-124">Next Steps</span></span>  
 [<span data-ttu-id="caa38-125">Publicar datos de Excel en MDS &#40;Complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="caa38-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="caa38-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="caa38-126">See Also</span></span>  
 <span data-ttu-id="caa38-127">[Cargando datos &#40;Complemento MDS para Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="caa38-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="caa38-128">[Cuadro de diálogo filtrar &#40;Complemento MDS para Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="caa38-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="caa38-129">Reordenar columnas &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="caa38-129">Reorder Columns &#40;MDS Add-in for Excel&#41;</span></span>](reorder-columns-mds-add-in-for-excel.md)  
  
  
