---
title: Crear y administrar medidas (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: edc1a4b2-96d3-4f34-bb70-6cacec79e819
author: minewiskan
ms.author: owend
ms.openlocfilehash: da507bf48b285a1414ffb85ba79da50508a2ae2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671204"
---
# <a name="create-and-manage-measures-ssas-tabular"></a><span data-ttu-id="1d997-102">Crear y administrar medidas (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="1d997-102">Create and Manage Measures (SSAS Tabular)</span></span>
  <span data-ttu-id="1d997-103">Una medida es una fórmula que se crea específicamente para su uso en un informe o una tabla dinámica de Excel (o gráfico dinámico).</span><span class="sxs-lookup"><span data-stu-id="1d997-103">A measure is a formula that is created for use in a report or Excel PivotTable (or PivotChart).</span></span> <span data-ttu-id="1d997-104">Las medidas pueden estar basadas en funciones de agregación estándar, como COUNT o SUM, o puede definir su propia fórmula utilizando DAX.</span><span class="sxs-lookup"><span data-stu-id="1d997-104">Measures can be based on standard aggregation functions, such as COUNT or SUM, or you can define your own formula by using DAX.</span></span> <span data-ttu-id="1d997-105">En las tareas de este tema se describe cómo crear y administrar medidas mediante la cuadrícula de medidas de una tabla.</span><span class="sxs-lookup"><span data-stu-id="1d997-105">The tasks in this topic describe how to create and manage measures by using a table's measure grid.</span></span>  
  
 <span data-ttu-id="1d997-106">En este tema se incluyen las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d997-106">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="1d997-107">Para crear una medida usando una fórmula de agregación estándar</span><span class="sxs-lookup"><span data-stu-id="1d997-107">To create a measure using a standard aggregation formula</span></span>](#bkmk_create_stand)  
  
-   [<span data-ttu-id="1d997-108">Para crear una medida mediante una fórmula personalizada</span><span class="sxs-lookup"><span data-stu-id="1d997-108">To create a measure using a custom formula</span></span>](#bkmk_create_custom)  
  
-   [<span data-ttu-id="1d997-109">Para editar las propiedades de las medidas</span><span class="sxs-lookup"><span data-stu-id="1d997-109">To edit measure properties</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="1d997-110">Para cambiar el nombre de una medida</span><span class="sxs-lookup"><span data-stu-id="1d997-110">To rename a measure</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="1d997-111">Para eliminar una medida</span><span class="sxs-lookup"><span data-stu-id="1d997-111">To delete a measure</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="1d997-112">Tareas</span><span class="sxs-lookup"><span data-stu-id="1d997-112">Tasks</span></span>  
 <span data-ttu-id="1d997-113">Para crear y administrar medidas, usará la cuadrícula de medidas de una tabla.</span><span class="sxs-lookup"><span data-stu-id="1d997-113">To create and manage measures, you will use a table's measure grid.</span></span> <span data-ttu-id="1d997-114">Solo puede ver la cuadrícula de medidas de una tabla en el diseñador de modelos en la Vista de datos.</span><span class="sxs-lookup"><span data-stu-id="1d997-114">You can view the measure grid for a table in the model designer in Data View only.</span></span> <span data-ttu-id="1d997-115">No puede crear medidas ni ver la cuadrícula de medidas en la Vista Diagrama; sin embargo, podrá ver las medidas existentes en dicha vista.</span><span class="sxs-lookup"><span data-stu-id="1d997-115">You cannot create measures or view the measure grid when in Diagram View; however, you can view existing measures in Diagram View.</span></span> <span data-ttu-id="1d997-116">Para mostrar la cuadrícula de medidas de una tabla, haga clic en el menú **Tabla** y en **Mostrar cuadrícula de medidas**.</span><span class="sxs-lookup"><span data-stu-id="1d997-116">To show the measure grid for a table, click the **Table** menu, and then click **Show Measure Grid**.</span></span>  
  
###  <a name="to-create-a-measure-using-a-standard-aggregation-formula"></a><a name="bkmk_create_stand"></a><span data-ttu-id="1d997-117">Para crear una medida mediante una fórmula de agregación estándar</span><span class="sxs-lookup"><span data-stu-id="1d997-117">To create a measure using a standard aggregation formula</span></span>  
  
-   <span data-ttu-id="1d997-118">Haga clic en la columna para la que desea crear la medida, haga clic en el menú **Columna** , seleccione **Autosuma**y, a continuación, haga clic en un tipo de agregación.</span><span class="sxs-lookup"><span data-stu-id="1d997-118">Click on the column for which you want to create the measure, then click the **Column** menu, then point to **AutoSum**, and then click an aggregation type.</span></span>  
  
     <span data-ttu-id="1d997-119">La medida se creará automáticamente con un nombre predeterminado, seguido de la fórmula en la primera celda de la cuadrícula de medidas directamente debajo de la columna.</span><span class="sxs-lookup"><span data-stu-id="1d997-119">The measure will be created automatically with a default name, followed by the formula in the first cell in the measure grid directly beneath the column.</span></span>  
  
###  <a name="to-create-a-measure-using-a-custom-formula"></a><a name="bkmk_create_custom"></a> <span data-ttu-id="1d997-120">Para crear una medida usando una fórmula personalizada</span><span class="sxs-lookup"><span data-stu-id="1d997-120">To create a measure using a custom formula</span></span>  
  
-   <span data-ttu-id="1d997-121">En la cuadrícula de medidas, debajo de la columna para la que quiere crear la medida, haga clic en una celda y, después, en la barra de fórmulas, escriba un nombre, seguido de un signo de dos puntos (:), un signo igual (=) y de la fórmula.</span><span class="sxs-lookup"><span data-stu-id="1d997-121">In the measure grid, beneath the column for which you want to create the measure, click a cell, then in the formula bar, type a name, followed by a colon (:), followed by an equals sign (=), followed by the formula.</span></span> <span data-ttu-id="1d997-122">Presione ENTRAR para aceptar la fórmula.</span><span class="sxs-lookup"><span data-stu-id="1d997-122">Press ENTER to accept the formula.</span></span>  
  
###  <a name="to-edit-measure-properties"></a><a name="bkmk_edit"></a><span data-ttu-id="1d997-123">Para editar las propiedades de la medida</span><span class="sxs-lookup"><span data-stu-id="1d997-123">To edit measure properties</span></span>  
  
-   <span data-ttu-id="1d997-124">En la cuadrícula de medidas, haga clic en una medida y, a continuación, en la ventana **Propiedades** , escriba o seleccione un valor de propiedad distinto.</span><span class="sxs-lookup"><span data-stu-id="1d997-124">In the measure grid, click a measure, and then In the **Properties** window, type or select a different property value.</span></span>  
  
###  <a name="to-rename-a-measure"></a><a name="bkmk_rename"></a><span data-ttu-id="1d997-125">Para cambiar el nombre de una medida</span><span class="sxs-lookup"><span data-stu-id="1d997-125">To rename a measure</span></span>  
  
-   <span data-ttu-id="1d997-126">En la cuadrícula de medidas, haga clic en una medida y, a continuación, en la ventana **Propiedades** , en **Nombre de medida**, escriba un nombre nuevo y haga clic en ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="1d997-126">In the measure grid, click on a measure, and then In the **Properties** window, in **Measure Name**, type a new name, and then click ENTER.</span></span>  
  
     <span data-ttu-id="1d997-127">También puede cambiar el nombre de una medida en la barra de fórmulas.</span><span class="sxs-lookup"><span data-stu-id="1d997-127">You can also rename a measure in the formula bar.</span></span> <span data-ttu-id="1d997-128">El nombre de la medida precede a la fórmula, y va seguido de un signo de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="1d997-128">The measure name precedes the formula, followed by a colon.</span></span>  
  
###  <a name="to-delete-a-measure"></a><a name="bkmk_delete"></a><span data-ttu-id="1d997-129">Para eliminar una medida</span><span class="sxs-lookup"><span data-stu-id="1d997-129">To delete a measure</span></span>  
  
-   <span data-ttu-id="1d997-130">En la cuadrícula de medidas, haga clic con el botón derecho en una medida y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="1d997-130">In the measure grid, right-click a measure, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d997-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d997-131">See Also</span></span>  
 <span data-ttu-id="1d997-132">[Medidas &#40;&#41;tabular de SSAS](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="1d997-132">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 <span data-ttu-id="1d997-133">[KPI &#40;&#41;tabular de SSAS](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="1d997-133">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="1d997-134">Columnas calculadas &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="1d997-134">Calculated Columns &#40;SSAS Tabular&#41;</span></span>](ssas-calculated-columns.md)  
  
  
