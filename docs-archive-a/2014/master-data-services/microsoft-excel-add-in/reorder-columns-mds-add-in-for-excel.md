---
title: Reordenar columnas (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ac00462e-c0f7-4b8d-86f2-d9eda2598a15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f0c47a631ffe699936a8d45bcc4e47e0b6f0a985
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745353"
---
# <a name="reorder-columns-mds-add-in-for-excel"></a><span data-ttu-id="6412a-102">Reordenar columnas (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="6412a-102">Reorder Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="6412a-103">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], puede reordenar las columnas si filtra la lista antes de cargar.</span><span class="sxs-lookup"><span data-stu-id="6412a-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you can reorder columns by filtering the list before loading.</span></span>  
  
 <span data-ttu-id="6412a-104">Cuando vuelva a ordenar atributos en el cuadro de diálogo **Filtro** , los datos se cargan en Excel con el orden nuevo.</span><span class="sxs-lookup"><span data-stu-id="6412a-104">When you reorder attributes in the **Filter** dialog box, the data is loaded into Excel with the new order.</span></span> <span data-ttu-id="6412a-105">Sin embargo, la próxima vez filtre los datos de atributo, el orden revertirá al orden del diseño original.</span><span class="sxs-lookup"><span data-stu-id="6412a-105">However, the next time that you filter the attribute data, the order will revert to the order in the original design.</span></span> <span data-ttu-id="6412a-106">Para cambiar el orden de forma permanente, un administrador debe cambiar el orden en el área de **Administración del sistema** de Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="6412a-106">To change the order permanently, an administrator should change the order in the **System Administration** area of Master Data Manager.</span></span> <span data-ttu-id="6412a-107">Para más información, consulte [Change the Order of Attributes](../change-the-order-of-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="6412a-107">For more information, see [Change the Order of Attributes](../change-the-order-of-attributes.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6412a-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6412a-108">Prerequisites</span></span>  
 <span data-ttu-id="6412a-109">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="6412a-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="6412a-110">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="6412a-110">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-reorder-mds-managed-columns"></a><span data-ttu-id="6412a-111">Para reordenar columnas administradas por MDS</span><span class="sxs-lookup"><span data-stu-id="6412a-111">To reorder MDS-managed columns</span></span>  
  
1.  <span data-ttu-id="6412a-112">Abra Excel y, en la pestaña **Datos maestros** , conéctese a un repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="6412a-112">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="6412a-113">Para obtener más información, consulte [Conectarse a un repositorio MDS &#40;complemento MDS para Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="6412a-113">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="6412a-114">En el panel **Explorador de datos maestros** , seleccione un modelo y una versión.</span><span class="sxs-lookup"><span data-stu-id="6412a-114">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="6412a-115">La lista de entidades se rellena.</span><span class="sxs-lookup"><span data-stu-id="6412a-115">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="6412a-116">Si el panel **Explorador de datos maestros** no está visible, en el grupo **Conectar y cargar** , haga clic en **Mostrar explorador**.</span><span class="sxs-lookup"><span data-stu-id="6412a-116">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="6412a-117">Si el panel **Explorador de datos maestros** está deshabilitado, se debe a que la hoja existente ya contiene datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="6412a-117">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="6412a-118">Para habilitar el panel, abra una nueva hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="6412a-118">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="6412a-119">En el panel **Explorador de datos maestros** , haga clic en una entidad.</span><span class="sxs-lookup"><span data-stu-id="6412a-119">In the **Master Data Explorer** pane, click an entity.</span></span>  
  
4.  <span data-ttu-id="6412a-120">En el grupo **Conectar y cargar** , haga clic en **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="6412a-120">In the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="6412a-121">En el cuadro de diálogo **Filtro** , en la sección **Columnas** , en la lista de atributos, haga clic en el atributo que desea mover.</span><span class="sxs-lookup"><span data-stu-id="6412a-121">In the **Filter** dialog box, in the **Columns** section, in the list of attributes, click the attribute you want to move.</span></span>  
  
6.  <span data-ttu-id="6412a-122">A la derecha de la lista, haga clic en la flecha **Arriba** o **Abajo** para mover el atributo a la derecha o a la izquierda en la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="6412a-122">To the right of the list, click the **Up** or **Down** arrow to move the attribute left and right in the worksheet.</span></span>  
  
7.  <span data-ttu-id="6412a-123">Repita el paso 7 para cada atributo hasta que el orden de arriba abajo represente el orden de izquierda a derecha que desee en la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="6412a-123">Repeat step 7 for each attribute until the top-to-bottom order represents the left-to-right order you want in the worksheet.</span></span>  
  
8.  <span data-ttu-id="6412a-124">Haga clic en **Cargar datos**.</span><span class="sxs-lookup"><span data-stu-id="6412a-124">Click **Load Data**.</span></span> <span data-ttu-id="6412a-125">La hoja se rellena con datos administrados por MDS y las columnas se muestran en el orden especificado.</span><span class="sxs-lookup"><span data-stu-id="6412a-125">The sheet is populated with MDS-managed data and the columns are displayed in the order you specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6412a-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6412a-126">See Also</span></span>  
 [<span data-ttu-id="6412a-127">Cargando datos &#40;Complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6412a-127">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
  
