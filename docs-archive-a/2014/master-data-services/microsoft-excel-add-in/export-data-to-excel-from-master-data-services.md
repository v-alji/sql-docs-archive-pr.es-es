---
title: Carga de datos de MDS en Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: dd29389b-928c-4e50-995c-c6af27f97805
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 35672807d5bb108e9386f892aea1847d45ebeb33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745859"
---
# <a name="load-data-from-mds-into-excel"></a><span data-ttu-id="241e1-102">Cargar datos de MDS en Excel</span><span class="sxs-lookup"><span data-stu-id="241e1-102">Load Data from MDS into Excel</span></span>
  <span data-ttu-id="241e1-103">En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] , debe cargar los datos del repositorio MDS para poder trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="241e1-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must load data from the MDS repository in order to work with it.</span></span>  
  
 <span data-ttu-id="241e1-104">Si desea filtrar el conjunto de datos antes de cargar, consulte [filtrar los datos antes de cargar &#40;Complemento MDS para Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="241e1-104">If you want to filter the dataset before loading, see [Filter Data before Loading &#40;MDS Add-in for Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) instead.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="241e1-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="241e1-105">Prerequisites</span></span>  
 <span data-ttu-id="241e1-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="241e1-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="241e1-107">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="241e1-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-load-data-from-mds-into-excel"></a><span data-ttu-id="241e1-108">Para cargar datos de MDS en Excel</span><span class="sxs-lookup"><span data-stu-id="241e1-108">To load data from MDS into Excel</span></span>  
  
1.  <span data-ttu-id="241e1-109">Abra Excel y, en la pestaña **Datos maestros** , conéctese a un repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="241e1-109">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="241e1-110">Para obtener más información, consulte [Conectarse a un repositorio MDS &#40;complemento MDS para Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="241e1-110">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="241e1-111">En el panel **Explorador de datos maestros** , seleccione un modelo y una versión.</span><span class="sxs-lookup"><span data-stu-id="241e1-111">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="241e1-112">La lista de entidades se rellena.</span><span class="sxs-lookup"><span data-stu-id="241e1-112">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="241e1-113">Si el panel **Explorador de datos maestros** no está visible, en el grupo **Conectar y cargar** , haga clic en **Mostrar explorador**.</span><span class="sxs-lookup"><span data-stu-id="241e1-113">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="241e1-114">Si el panel **Explorador de datos maestros** está deshabilitado, se debe a que la hoja existente ya contiene datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="241e1-114">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="241e1-115">Para habilitar el panel, abra una nueva hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="241e1-115">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="241e1-116">En el panel **Explorador de datos maestros** , en la lista de entidades, haga doble clic en la entidad que quiera cargar.</span><span class="sxs-lookup"><span data-stu-id="241e1-116">In the **Master Data Explorer** pane, in the list of entities, double-click the entity you want to load.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="241e1-117">Solo se carga en Excel el primer millón de miembros.</span><span class="sxs-lookup"><span data-stu-id="241e1-117">Only the first one million members are loaded into Excel.</span></span> <span data-ttu-id="241e1-118">Para filtrar la lista antes de la carga, en la cinta de opciones, en el grupo **Conectar y cargar** , haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="241e1-118">To filter the list before loading, on the ribbon in the **Connect and Load** group, click **Filter**.</span></span>  
    > -   <span data-ttu-id="241e1-119">En las columnas que son listas restringidas (atributos basados en dominio), solo se cargan los 25.000 primeros valores.</span><span class="sxs-lookup"><span data-stu-id="241e1-119">In columns that are constrained lists (domain-based attributes), only the first 25,000 values are loaded.</span></span> <span data-ttu-id="241e1-120">Puede cambiar este número en la propiedad MaximumDbaEntitySize en el archivo de excelusersettings.config ubicado en el equipo en el que está instalado Excel.</span><span class="sxs-lookup"><span data-stu-id="241e1-120">You can change this number in the MaximumDbaEntitySize property in the excelusersettings.config file located on the computer that Excel is installed on.</span></span> <span data-ttu-id="241e1-121">Este archivo se encuentra en C:\Users \\<usuario \> \AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices \\ .</span><span class="sxs-lookup"><span data-stu-id="241e1-121">This file is located in C:\Users\\<user\>\AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices\\.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="241e1-122">Al cargar datos delimitados con texto mediante el complemento para Microsoft Excel con Excel de 32 bits y los valores de las propiedades **Cell Count to Load** (Recuento de celdas que se cargarán) y **Cell Count to Publish** (Recuento de celdas que se publicarán) se establecen en un máximo de 1000, se producirá un error de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="241e1-122">When you load text-delimited data using the Add-in for Microsoft Excel with 32-bit Excel, and the settings for the **Cell Count to Load** and **Cell Count to Publish** properties are both set to the maximum of 1000, an out-of-memory error will occur.</span></span> <span data-ttu-id="241e1-123">Tiene que usar Excel de 64 bits para poder usar los valores máximos en **Cell Count to Load** (Recuento de celdas que se cargarán) y **Cell Count to Publish**(Recuento de celdas que se publicarán).</span><span class="sxs-lookup"><span data-stu-id="241e1-123">You have to use 64-bit Excel to use the maximum settings for **Cell Count to Load** and **Cell Count to Publish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="241e1-124">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="241e1-124">Next Steps</span></span>  
 [<span data-ttu-id="241e1-125">Publicar datos de Excel en MDS &#40;Complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="241e1-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="241e1-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="241e1-126">See Also</span></span>  
 <span data-ttu-id="241e1-127">[Cargando datos &#40;Complemento MDS para Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="241e1-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="241e1-128">[Cuadro de diálogo filtrar &#40;Complemento MDS para Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="241e1-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="241e1-129">Complemento MDS para Excel de &#40;de datos de publicación&#41;</span><span class="sxs-lookup"><span data-stu-id="241e1-129">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
