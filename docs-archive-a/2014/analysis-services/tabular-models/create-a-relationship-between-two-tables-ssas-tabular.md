---
title: Crear una relación entre dos tablas (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.managereldb.f1
- sql12.asvs.bidtoolset.createrelatdb.f1
ms.assetid: 052d77b7-7922-408a-a200-786016ee4d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33481b8d50be9ca632bcade932d51df86c1910a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671212"
---
# <a name="create-a-relationship-between-two-tables-ssas-tabular"></a><span data-ttu-id="36158-102">Crear una relación entre dos tablas (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="36158-102">Create a Relationship Between Two Tables (SSAS Tabular)</span></span>
  <span data-ttu-id="36158-103">Si entre las tablas del origen de datos no hay relaciones existentes, o si agrega nuevas tablas, puede usar las herramientas del diseñador de modelos para crear relaciones.</span><span class="sxs-lookup"><span data-stu-id="36158-103">If the tables in your data source do not have existing relationships, or if you add new tables, you can use the tools in the model designer to create new relationships.</span></span> <span data-ttu-id="36158-104">Para más información sobre cómo se usan las relaciones en los modelos tabulares, vea [Relaciones &#40;SSAS tabular&#41;](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="36158-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="create-a-relationship-between-two-tables"></a><span data-ttu-id="36158-105">Crear una relación entre dos tablas</span><span class="sxs-lookup"><span data-stu-id="36158-105">Create a relationship between two tables</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-click-and-drag"></a><span data-ttu-id="36158-106">Para crear una relación entre dos tablas en la Vista de diagrama (hacer clic y arrastrar)</span><span class="sxs-lookup"><span data-stu-id="36158-106">To create a relationship between two tables in Diagram View (Click and drag)</span></span>  
  
1.  <span data-ttu-id="36158-107">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** , a continuación, en **Vista de modelo**y, por último, en **Vista de diagrama**.</span><span class="sxs-lookup"><span data-stu-id="36158-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="36158-108">Haga clic (y mantenga presionado el botón) en una columna de una tabla, a continuación arrastre el cursor a una columna de búsqueda relacionada en una tabla de búsqueda relacionada y suelte el botón.</span><span class="sxs-lookup"><span data-stu-id="36158-108">Click (and hold) on a column within a table, then drag the cursor to a related lookup column in a related lookup table, and then release.</span></span> <span data-ttu-id="36158-109">La relación se creará automáticamente en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="36158-109">The relationship will be created in the correct order automatically.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-right-click"></a><span data-ttu-id="36158-110">Para crear una relación entre dos tablas en la Vista de diagrama (hacer clic con el botón secundario)</span><span class="sxs-lookup"><span data-stu-id="36158-110">To create a relationship between two tables in Diagram View (Right-click)</span></span>  
  
1.  <span data-ttu-id="36158-111">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** , a continuación, en **Vista de modelo**y, por último, en **Vista de diagrama**.</span><span class="sxs-lookup"><span data-stu-id="36158-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="36158-112">Haga clic con el botón derecho en el encabezado de una tabla o en una columna y, luego, haga clic en **Crear relación**.</span><span class="sxs-lookup"><span data-stu-id="36158-112">Right-click a table heading or column, and then click **Create Relationship**.</span></span>  
  
3.  <span data-ttu-id="36158-113">En el cuadro de diálogo **Crear relación** , haga clic en la flecha abajo de **Tabla**y seleccione una tabla en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="36158-113">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="36158-114">En una relación de uno a varios, esta tabla debe estar en el extremo de "varios".</span><span class="sxs-lookup"><span data-stu-id="36158-114">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
4.  <span data-ttu-id="36158-115">En **Columna**, seleccione la columna que contiene los datos que se relacionan con **Columna de búsqueda relacionada**.</span><span class="sxs-lookup"><span data-stu-id="36158-115">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span> <span data-ttu-id="36158-116">La columna se selecciona automáticamente si hizo clic con el botón secundario en una columna para crear la relación.</span><span class="sxs-lookup"><span data-stu-id="36158-116">The column is automatically selected if you right-clicked on a column to create the relationship.</span></span>  
  
5.  <span data-ttu-id="36158-117">En **Columna de búsqueda relacionada**, seleccione una tabla que tenga al menos una columna de datos relacionada con la tabla que acaba de seleccionar en **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="36158-117">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="36158-118">En una relación "uno a varios", esta tabla debería estar en el extremo "uno", lo que quiere decir que los valores de la columna seleccionada no contienen duplicados.</span><span class="sxs-lookup"><span data-stu-id="36158-118">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="36158-119">Si intenta crear la relación en el orden equivocado (uno a varios en lugar de varios a uno), se mostrará un icono al lado del campo **Columna de búsqueda relacionada** .</span><span class="sxs-lookup"><span data-stu-id="36158-119">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="36158-120">Invierta el orden para crear una relación válida.</span><span class="sxs-lookup"><span data-stu-id="36158-120">Reverse the order to create a valid relationship.</span></span>  
  
6.  <span data-ttu-id="36158-121">En **Columna de búsqueda relacionada**, seleccione una columna que tenga valores únicos que coincidan con los valores seleccionados para **Columna**.</span><span class="sxs-lookup"><span data-stu-id="36158-121">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
7.  <span data-ttu-id="36158-122">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="36158-122">Click **Create**.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-data-view"></a><span data-ttu-id="36158-123">Para crear una relación entre dos tablas en la vista de datos</span><span class="sxs-lookup"><span data-stu-id="36158-123">To create a relationship between two tables in Data View</span></span>  
  
1.  <span data-ttu-id="36158-124">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], haga clic en el menú **Tabla** y, a continuación, en **Crear relaciones**.</span><span class="sxs-lookup"><span data-stu-id="36158-124">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Create Relationships**.</span></span>  
  
2.  <span data-ttu-id="36158-125">En el cuadro de diálogo **Crear relación** , haga clic en la flecha abajo de **Tabla**y seleccione una tabla en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="36158-125">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="36158-126">En una relación de uno a varios, esta tabla debe estar en el extremo de "varios".</span><span class="sxs-lookup"><span data-stu-id="36158-126">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
3.  <span data-ttu-id="36158-127">En **Columna**, seleccione la columna que contiene los datos que se relacionan con **Columna de búsqueda relacionada**.</span><span class="sxs-lookup"><span data-stu-id="36158-127">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span>  
  
4.  <span data-ttu-id="36158-128">En **Columna de búsqueda relacionada**, seleccione una tabla que tenga al menos una columna de datos relacionada con la tabla que acaba de seleccionar en **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="36158-128">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="36158-129">En una relación "uno a varios", esta tabla debería estar en el extremo "uno", lo que quiere decir que los valores de la columna seleccionada no contienen duplicados.</span><span class="sxs-lookup"><span data-stu-id="36158-129">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="36158-130">Si intenta crear la relación en el orden equivocado (uno a varios en lugar de varios a uno), se mostrará un icono al lado del campo **Columna de búsqueda relacionada** .</span><span class="sxs-lookup"><span data-stu-id="36158-130">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="36158-131">Invierta el orden para crear una relación válida.</span><span class="sxs-lookup"><span data-stu-id="36158-131">Reverse the order to create a valid relationship.</span></span>  
  
5.  <span data-ttu-id="36158-132">En **Columna de búsqueda relacionada**, seleccione una columna que tenga valores únicos que coincidan con los valores seleccionados para **Columna**.</span><span class="sxs-lookup"><span data-stu-id="36158-132">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
6.  <span data-ttu-id="36158-133">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="36158-133">Click **Create**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36158-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36158-134">See Also</span></span>  
 <span data-ttu-id="36158-135">[Eliminar relaciones &#40;SSAS tabular&#41;](delete-relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="36158-135">[Delete Relationships &#40;SSAS Tabular&#41;](delete-relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="36158-136">Relaciones &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="36158-136">Relationships &#40;SSAS Tabular&#41;</span></span>](relationships-ssas-tabular.md)  
  
  
