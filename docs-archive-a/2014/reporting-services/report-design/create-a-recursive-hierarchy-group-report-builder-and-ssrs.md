---
title: Crear un grupo de jerarquía recursiva (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8b830ba5-4d64-4348-a2b1-76b9338a1462
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf86c3989170ed8cd452168a558ead348258331e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671426"
---
# <a name="create-a-recursive-hierarchy-group-report-builder-and-ssrs"></a><span data-ttu-id="e5d66-102">Crear un grupo de jerarquía recursiva (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="e5d66-102">Create a Recursive Hierarchy Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e5d66-103">Un grupo de jerarquía recursiva organiza los datos existentes en un único conjunto de datos de informe donde existen varios niveles jerárquicos, como puede ser la estructura de mando para las relaciones entre jefes y empleados en una jerarquía de organización.</span><span class="sxs-lookup"><span data-stu-id="e5d66-103">A recursive hierarchy group organizes data from a single report dataset that includes multiple hierarchical levels, such as the report-to structure for manager-employee relationships in an organizational hierarchy.</span></span>  
  
 <span data-ttu-id="e5d66-104">Para poder organizar los datos de una tabla como un grupo de jerarquía recursiva, todos los datos jerárquicos deben hallarse en un único conjunto de datos, con campos independientes para el elemento que se va a agrupar y para el elemento por el que se va a agrupar.</span><span class="sxs-lookup"><span data-stu-id="e5d66-104">Before you can organize data in a table as a recursive hierarchy group, you must have a single dataset that contains all the hierarchical data, You must have separate fields for the item to group and for the item to group by.</span></span> <span data-ttu-id="e5d66-105">Por ejemplo, un conjunto de datos donde quiere agrupar a los empleados recursivamente bajo su jefe podría contener contenga un nombre, un nombre de empleado, un identificador de empleado y un identificador de jefe.</span><span class="sxs-lookup"><span data-stu-id="e5d66-105">For example, a dataset where you want to group employees recursively under their manager might contain a name, an employee name, an employee ID, and a manager ID.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-recursive-hierarchy-group"></a><span data-ttu-id="e5d66-106">Para crear un grupo de jerarquía recursiva</span><span class="sxs-lookup"><span data-stu-id="e5d66-106">To create a recursive hierarchy group</span></span>  
  
1.  <span data-ttu-id="e5d66-107">En la vista Diseño, agregue una tabla y arrastre los campos del conjunto de datos que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="e5d66-107">In Design view, add a table, and drag the dataset fields to display.</span></span> <span data-ttu-id="e5d66-108">Normalmente, el campo que se desea mostrar como una jerarquía se encuentra en la primera columna.</span><span class="sxs-lookup"><span data-stu-id="e5d66-108">Typically, the field that you want to show as a hierarchy is in the first column.</span></span>  
  
2.  <span data-ttu-id="e5d66-109">Haga clic con el botón secundario en cualquier lugar de la tabla para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="e5d66-109">Right-click anywhere in the table to select it.</span></span> <span data-ttu-id="e5d66-110">El Panel de agrupación muestra el grupo de detalles para la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e5d66-110">The Grouping pane displays the details group for the selected table.</span></span> <span data-ttu-id="e5d66-111">En el panel Grupos de filas, haga clic con el botón derecho en **Detalles**y, después, haga clic en **Editar grupo**.</span><span class="sxs-lookup"><span data-stu-id="e5d66-111">In the Row Groups pane, right-click **Details**, and then click **Edit Group**.</span></span> <span data-ttu-id="e5d66-112">Se abrirá el cuadro de diálogo **Propiedades de grupo** .</span><span class="sxs-lookup"><span data-stu-id="e5d66-112">The **Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e5d66-113">En **Expresiones de grupo**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e5d66-113">In **Group expressions**, click **Add**.</span></span> <span data-ttu-id="e5d66-114">Aparecerá una nueva fila en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e5d66-114">A new row appears in the grid.</span></span>  
  
4.  <span data-ttu-id="e5d66-115">En la lista **Agrupar por** , escriba o seleccione el campo para agrupar.</span><span class="sxs-lookup"><span data-stu-id="e5d66-115">In the **Group on** list, type or select the field to group.</span></span>  
  
5.  <span data-ttu-id="e5d66-116">Haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e5d66-116">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="e5d66-117">En la lista **Primaria recursiva** , escriba o seleccione el campo por el que va a agrupar.</span><span class="sxs-lookup"><span data-stu-id="e5d66-117">In the **Recursive Parent** list, enter or select the field to group on.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="e5d66-118">Ejecute el informe.</span><span class="sxs-lookup"><span data-stu-id="e5d66-118">Run the report.</span></span> <span data-ttu-id="e5d66-119">El informe muestra el grupo de jerarquía recursiva, aunque no hay sangría que muestre la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="e5d66-119">The report displays the recursive hierarchy group, although there is no indent to show the hierarchy</span></span>  
  
### <a name="to-format-a-recursive-hierarchy-group-with-indent-levels"></a><span data-ttu-id="e5d66-120">Para dar formato a un grupo de jerarquía recursiva con niveles de sangría</span><span class="sxs-lookup"><span data-stu-id="e5d66-120">To format a recursive hierarchy group with indent levels</span></span>  
  
1.  <span data-ttu-id="e5d66-121">Haga clic en el cuadro de texto que contiene el campo al que desea agregar niveles de sangría para mostrar la jerarquía con formato.</span><span class="sxs-lookup"><span data-stu-id="e5d66-121">Click the text box that contains the field to which you want to add indent levels to display a hierarchy format.</span></span> <span data-ttu-id="e5d66-122">Las propiedades del cuadro de texto aparecen en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="e5d66-122">The properties for the text box appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e5d66-123">Si el panel Propiedades no está visible, en la pestaña **Ver** , haga clic en **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="e5d66-123">If you do not see the Properties pane, click **Properties** on the **View** tab.</span></span>  
  
2.  <span data-ttu-id="e5d66-124">En el panel Propiedades, expanda el `Padding` nodo, haga clic en **izquierda**y, en la lista desplegable, seleccione **\<Expression...>** .</span><span class="sxs-lookup"><span data-stu-id="e5d66-124">In the Properties pane, expand the `Padding` node, click **Left**, and from the drop-down list, select **\<Expression...>**.</span></span>  
  
3.  <span data-ttu-id="e5d66-125">En el panel Expresión, escriba la expresión siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5d66-125">In the Expression pane, type the following expression:</span></span>  
  
     `=CStr(2 + (Level()*10)) + "pt"`  
  
     <span data-ttu-id="e5d66-126">Las propiedades de relleno requieren una cadena con el formato *nnyy*, donde *nn* es un número e *yy* es la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="e5d66-126">The Padding properties all require a string in the format *nnyy*, where *nn* is a number and *yy* is the unit of measure.</span></span> <span data-ttu-id="e5d66-127">La expresión de ejemplo genera una cadena que usa la función `Level` para aumentar el tamaño del relleno según el nivel de recursividad.</span><span class="sxs-lookup"><span data-stu-id="e5d66-127">The example expression builds a string that uses the `Level` function to increase the size of the padding based on recursion level.</span></span> <span data-ttu-id="e5d66-128">Por ejemplo, una fila que tenga un nivel de 1 daría lugar a un relleno de (2 + (1\*10))=12pt, y una fila que tenga un nivel de 3 se traduciría en un relleno de (2 + (3\*10))=32pt.</span><span class="sxs-lookup"><span data-stu-id="e5d66-128">For example, a row that has a level of 1 would result in a padding of (2 + (1\*10))=12pt, and a row that has a level of 3 would result in a padding of (2 + (3\*10))=32pt.</span></span> <span data-ttu-id="e5d66-129">Para obtener información sobre la `Level` función, vea [LEVEL](report-builder-functions-level-function.md).</span><span class="sxs-lookup"><span data-stu-id="e5d66-129">For information about the `Level` function, see [Level](report-builder-functions-level-function.md).</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="e5d66-130">Ejecute el informe.</span><span class="sxs-lookup"><span data-stu-id="e5d66-130">Run the report.</span></span> <span data-ttu-id="e5d66-131">El informe muestra una vista jerárquica de los datos agrupados.</span><span class="sxs-lookup"><span data-stu-id="e5d66-131">The report displays a hierarchical view of the grouped data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d66-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5d66-132">See Also</span></span>  
 <span data-ttu-id="e5d66-133">[Crear grupos de jerarquía recursiva &#40;Generador de informes y SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e5d66-133">[Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e5d66-134">[Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e5d66-134">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e5d66-135">[Referencia a las funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e5d66-135">[Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span></span>  
 <span data-ttu-id="e5d66-136">[Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e5d66-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e5d66-137">[Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e5d66-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e5d66-138">[Listas &#40;Generador de informes y SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e5d66-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e5d66-139">Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e5d66-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
