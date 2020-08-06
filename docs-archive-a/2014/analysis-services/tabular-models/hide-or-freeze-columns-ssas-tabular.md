---
title: Ocultar o inmovilizar columnas (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.hideunhidecolumnsdb.f1
ms.assetid: 5407aee5-6a07-4559-a2ba-2ca00a242f02
author: minewiskan
ms.author: owend
ms.openlocfilehash: 71398eecbc342b4e3f9c2445fef3023132266dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744375"
---
# <a name="hide-or-freeze-columns-ssas-tabular"></a><span data-ttu-id="d2254-102">Ocultar o inmovilizar columnas (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="d2254-102">Hide or Freeze Columns (SSAS Tabular)</span></span>
  <span data-ttu-id="d2254-103">Si en el diseñador de modelos hay columnas que no desea mostrar en una tabla, puede ocultarlas temporalmente.</span><span class="sxs-lookup"><span data-stu-id="d2254-103">In the model designer, if there are columns that you don't want to display in a table, you can temporarily hide them.</span></span> <span data-ttu-id="d2254-104">Si oculta una columna, dispone de más espacio en la pantalla para agregar columnas nuevas o para trabajar solo con las columnas de datos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="d2254-104">Hiding a column gives you more room on the screen to add new columns or to work with only relevant columns of data.</span></span> <span data-ttu-id="d2254-105">Puede ocultar y mostrar columnas desde el menú **Columna** del diseñador de modelos y desde el menú contextual disponible en cada encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="d2254-105">You can hide and unhide columns from the **Column** menu in the model designer, and from the right-click menu available from each column header.</span></span> <span data-ttu-id="d2254-106">Para mantener visible un área de un modelo mientras se desplaza a otra área del modelo, puede inmovilizar columnas específicas para bloquearlas.</span><span class="sxs-lookup"><span data-stu-id="d2254-106">To keep an area of a model visible while you scroll to another area of the model, you can lock specific columns in one area by freezing them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d2254-107">La capacidad de ocultar columnas no tiene como finalidad la seguridad de los datos; solo pretende simplificar y acortar la lista de columnas visibles en el diseñador de modelos o en los informes.</span><span class="sxs-lookup"><span data-stu-id="d2254-107">The ability to hide columns is not intended to be used for data security, only to simplify and shorten the list of columns visible in the model designer or reports.</span></span> <span data-ttu-id="d2254-108">Para proteger los datos, puede definir roles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d2254-108">To secure data, you can define security roles.</span></span> <span data-ttu-id="d2254-109">Los roles solo pueden restringir los metadatos y los datos visibles a los objetos definidos en el rol.</span><span class="sxs-lookup"><span data-stu-id="d2254-109">Roles can limit viewable metadata and data to only those objects defined in the role.</span></span> <span data-ttu-id="d2254-110">Para obtener más información, vea [Roles &#40;SSAS tabular&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d2254-110">For more information, see [Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="d2254-111">A la hora de ocultar una columna, tiene la opción de ocultarla mientras trabaja en el diseñador de modelos o en los informes.</span><span class="sxs-lookup"><span data-stu-id="d2254-111">When you hide a column, you have the option to hide the column while you are working in the model designer or in reports.</span></span> <span data-ttu-id="d2254-112">Si oculta todas las columnas, la tabla aparece vacía en su totalidad en el Diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="d2254-112">If you hide all columns, the entire table appears blank in the model designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2254-113">Si necesita ocultar muchas columnas, puede crear una perspectiva en lugar de ocultarlas y mostrarlas.</span><span class="sxs-lookup"><span data-stu-id="d2254-113">If you have many columns to hide, you can create a perspective instead of hiding and unhiding columns.</span></span> <span data-ttu-id="d2254-114">Una perspectiva es una vista personalizada de los datos que facilita el trabajo con subconjuntos de datos relacionados.</span><span class="sxs-lookup"><span data-stu-id="d2254-114">A perspective is a custom view of the data that makes it easier to work with subset of related data.</span></span> <span data-ttu-id="d2254-115">Para obtener más información, vea [Crear y administrar perspectivas &#40;SSAS tabular&#41;](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d2254-115">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md)</span></span>  
  
### <a name="to-hide-an-individual-column"></a><span data-ttu-id="d2254-116">Para ocultar una sola columna</span><span class="sxs-lookup"><span data-stu-id="d2254-116">To hide an individual column</span></span>  
  
1.  <span data-ttu-id="d2254-117">En el diseñador de modelos, seleccione la tabla que contenga la columna que desee ocultar.</span><span class="sxs-lookup"><span data-stu-id="d2254-117">In the model designer, select the table that contains the column that you want to hide.</span></span>  
  
2.  <span data-ttu-id="d2254-118">Haga clic con el botón derecho en la columna, haga clic en **Ocultar columnas**y, después, haga clic en **Desde el Diseñador e Informes**, **Desde informes**o **Desde diseñador**.</span><span class="sxs-lookup"><span data-stu-id="d2254-118">Right-click the column, then click **Hide Columns**, and then click **From Designer and Reports**, **From Reports**, or **From Designer**.</span></span>  
  
### <a name="to-hide-multiple-columns"></a><span data-ttu-id="d2254-119">Para ocultar varias columnas</span><span class="sxs-lookup"><span data-stu-id="d2254-119">To hide multiple columns</span></span>  
  
1.  <span data-ttu-id="d2254-120">En el diseñador de modelos, seleccione la tabla que contenga las columnas que desee ocultar.</span><span class="sxs-lookup"><span data-stu-id="d2254-120">In the model designer, select the table that contains the columns that you want to hide.</span></span>  
  
2.  <span data-ttu-id="d2254-121">Haga clic en el menú **Columnas** y, a continuación, en **Ocultar y mostrar**.</span><span class="sxs-lookup"><span data-stu-id="d2254-121">Click on the **Columns** menu, and then click **Hide and Unhide**.</span></span>  
  
3.  <span data-ttu-id="d2254-122">En el cuadro de diálogo **Ocultar y mostrar columnas** , busque cada columna que desee ocultar y, a continuación, anule la selección de una de las opciones **En diseñador** y **En informes**, o ambas.</span><span class="sxs-lookup"><span data-stu-id="d2254-122">In the **Hide and Unhide Columns** dialog box, locate each column that you want to hide, and then deselect one or both of **In Designer** and **In Reports**.</span></span>  
  
4.  <span data-ttu-id="d2254-123">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2254-123">Click **OK**.</span></span>  
  
### <a name="to-freeze-columns"></a><span data-ttu-id="d2254-124">Para inmovilizar columnas</span><span class="sxs-lookup"><span data-stu-id="d2254-124">To freeze columns</span></span>  
  
1.  <span data-ttu-id="d2254-125">En el diseñador de modelos, seleccione la tabla que contenga las columnas que desee inmovilizar.</span><span class="sxs-lookup"><span data-stu-id="d2254-125">In the model designer, select the table that contains the columns that you want to freeze.</span></span>  
  
2.  <span data-ttu-id="d2254-126">Seleccione las columnas que desee inmovilizar.</span><span class="sxs-lookup"><span data-stu-id="d2254-126">Select one or more columns to freeze.</span></span>  
  
3.  <span data-ttu-id="d2254-127">Haga clic en el menú **Columnas** y, a continuación, en **Inmovilizar**.</span><span class="sxs-lookup"><span data-stu-id="d2254-127">Click on the **Columns** menu, and then click **Freeze**..</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d2254-128">Cuando se inmovilizan columnas, estas se mueven a la izquierda (o delante) de la tabla en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="d2254-128">When a column(s) is frozen, it is moved to left (or front) of the table in the designer.</span></span> <span data-ttu-id="d2254-129">Cuando se libera una columna, esta no recupera su ubicación original.</span><span class="sxs-lookup"><span data-stu-id="d2254-129">Unfreezing the column does not move it back to its original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2254-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2254-130">See Also</span></span>  
 <span data-ttu-id="d2254-131">[Tablas y columnas &#40;SSAS tabular&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="d2254-131">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="d2254-132">[Perspectivas &#40;SSAS tabular&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="d2254-132">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="d2254-133">Roles &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="d2254-133">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
