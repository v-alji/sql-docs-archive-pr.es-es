---
title: Crear y administrar jerarquías (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8dd30cd0-a831-4d25-b577-648d7f3c7fa6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0bab3e09aadb4e0c857b9c1da3111e03e90f777e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671207"
---
# <a name="create-and-manage-hierarchies-ssas-tabular"></a><span data-ttu-id="37791-102">Crear y administrar jerarquías (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="37791-102">Create and Manage Hierarchies (SSAS Tabular)</span></span>
  <span data-ttu-id="37791-103">Las jerarquías se pueden crear y administrar en la Vista de diagrama del diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="37791-103">Hierarchies can be created and managed in the model designer, in Diagram View.</span></span> <span data-ttu-id="37791-104">Para ver el diseñador de modelos en la Vista de diagrama, en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic en el menú **Modelo** , seleccione **Vista de modelo**y haga clic en **Vista de diagrama**.</span><span class="sxs-lookup"><span data-stu-id="37791-104">To view the model designer in Diagram View, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
 <span data-ttu-id="37791-105">En este tema se incluyen las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="37791-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="37791-106">Crear una jerarquía</span><span class="sxs-lookup"><span data-stu-id="37791-106">Create a Hierarchy</span></span>](#bkmk_create)  
  
-   [<span data-ttu-id="37791-107">Editar una jerarquía</span><span class="sxs-lookup"><span data-stu-id="37791-107">Edit a Hierarchy</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="37791-108">Eliminar una jerarquía</span><span class="sxs-lookup"><span data-stu-id="37791-108">Delete a Hierarchy</span></span>](#bkmk_delete)  
  
##  <a name="create-a-hierarchy"></a><a name="bkmk_create"></a> <span data-ttu-id="37791-109">Crear una jerarquía</span><span class="sxs-lookup"><span data-stu-id="37791-109">Create a Hierarchy</span></span>  
 <span data-ttu-id="37791-110">Puede crear una jerarquía usando las columnas y el menú contextual de la tabla.</span><span class="sxs-lookup"><span data-stu-id="37791-110">You can create a hierarchy by using the columns and table context menu.</span></span> <span data-ttu-id="37791-111">Al crear una jerarquía, se muestra un nuevo nivel primario con las columnas seleccionadas como niveles secundarios.</span><span class="sxs-lookup"><span data-stu-id="37791-111">When you create a hierarchy, a new parent level displays with selected columns as child levels.</span></span>  
  
#### <a name="to-create-a-hierarchy-from-the-context-menu"></a><span data-ttu-id="37791-112">Para crear una jerarquía desde el menú contextual</span><span class="sxs-lookup"><span data-stu-id="37791-112">To create a hierarchy from the context menu</span></span>  
  
1.  <span data-ttu-id="37791-113">En el diseñador de modelos (Vista de diagrama), en una ventana de tabla, haga clic con el botón derecho en una columna y, después, haga clic en **Crear jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="37791-113">In the model designer (Diagram View), in a table window, right-click on a column, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="37791-114">Para seleccionar varias columnas, haga clic en cada columna, haga clic con el botón derecho para abrir el menú contextual y, después, haga clic en **Crear jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="37791-114">To select multiple columns, click each column, then right-click to open the context menu, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="37791-115">Se creará un nivel primario de la jerarquía en la parte inferior de la ventana de tabla y las columnas seleccionadas se copiarán debajo de la jerarquía como niveles secundarios.</span><span class="sxs-lookup"><span data-stu-id="37791-115">A parent hierarchy level is created at the bottom of the table window and the selected columns are copied under the hierarchy as child levels.</span></span>  
  
2.  <span data-ttu-id="37791-116">Escriba el nombre de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="37791-116">Type a name for the hierarchy.</span></span>  
  
 <span data-ttu-id="37791-117">Puede arrastrar columnas adicionales al nivel primario de la jerarquía, lo que copia las columnas.</span><span class="sxs-lookup"><span data-stu-id="37791-117">You can drag additional columns into your hierarchy's parent level, which copies the columns.</span></span> <span data-ttu-id="37791-118">Arrastre y coloque el nivel secundario para situarlo donde desea que aparezca en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="37791-118">Drop the child level to place it where you want it to appear in the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37791-119">El comando Crear jerarquía está deshabilitado en el menú contextual si realiza una selección múltiple de una medida junto con una o varias columnas, o si selecciona columnas de varias tablas.</span><span class="sxs-lookup"><span data-stu-id="37791-119">The Create Hierarchy command is disabled in the context menu if you multi-select a measure along with one or more columns or you select columns from multiple tables.</span></span>  
  
##  <a name="edit-a-hierarchy"></a><a name="bkmk_edit"></a><span data-ttu-id="37791-120">Editar una jerarquía</span><span class="sxs-lookup"><span data-stu-id="37791-120">Edit a Hierarchy</span></span>  
 <span data-ttu-id="37791-121">Puede cambiar el nombre de una jerarquía, cambiar el nombre de un nivel secundario, cambiar el orden de los niveles secundarios, agregar columnas adicionales como niveles secundarios, quitar un nivel secundario de una jerarquía, mostrar el nombre del origen de un nivel secundario (el nombre de columna) y ocultar un nivel secundario si tiene el mismo nombre que el nivel primario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="37791-121">You can rename a hierarchy, rename a child level, change the order of the child levels, add additional columns as child levels, remove a child level from a hierarchy, show the source name of a child level (the column name), and hide a child level if it has the same name as the hierarchy parent level.</span></span>  
  
#### <a name="to-change-the-name-of-a-hierarchy-or-child-level"></a><span data-ttu-id="37791-122">Para cambiar el nombre de una jerarquía o de un nivel secundario</span><span class="sxs-lookup"><span data-stu-id="37791-122">To change the name of a hierarchy or child level</span></span>  
  
1.  <span data-ttu-id="37791-123">Haga clic con el botón derecho en el nivel primario de la jerarquía o en un nivel secundario y, después, haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="37791-123">Right-click the hierarchy parent level or a child level, and the click **Rename**.</span></span>  
  
2.  <span data-ttu-id="37791-124">Escriba un nuevo nombre o edite el nombre existente.</span><span class="sxs-lookup"><span data-stu-id="37791-124">Type a new name or edit the existing name.</span></span>  
  
#### <a name="to-change-the-order-of-a-child-level-in-a-hierarchy"></a><span data-ttu-id="37791-125">Para cambiar el orden de un nivel secundario de una jerarquía</span><span class="sxs-lookup"><span data-stu-id="37791-125">To change the order of a child level in a hierarchy</span></span>  
  
-   <span data-ttu-id="37791-126">Haga clic en un nivel secundario y arrástrelo hasta una nueva posición en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="37791-126">Click and drag a child level into a new position in the hierarchy.</span></span>  
  
-   <span data-ttu-id="37791-127">O bien, haga clic con el botón secundario en un nivel secundario de la jerarquía y, a continuación, haga clic en Subir para mover el nivel hacia arriba en la lista o haga clic en Bajar para mover el nivel hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="37791-127">Or, right-click a child level of the hierarchy, and then click Move Up to move the level up in the list, or click Move Down to move the level down in the list.</span></span>  
  
-   <span data-ttu-id="37791-128">O bien, haga clic en un nivel secundario para seleccionarlo y, a continuación, presione Alt + Flecha arriba para mover el nivel hacia arriba o Alt + Flecha abajo para mover el nivel hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="37791-128">Or, click a child level to select it, and then press Alt + Up Arrow to move the level up, or press Alt+Down Arrow to move the level down in the list.</span></span>  
  
#### <a name="to-add-another-child-level-to-a-hierarchy"></a><span data-ttu-id="37791-129">Para agregar otro nivel secundario a una jerarquía</span><span class="sxs-lookup"><span data-stu-id="37791-129">To add another child level to a hierarchy</span></span>  
  
-   <span data-ttu-id="37791-130">Haga clic en una columna y arrástrela al nivel primario o a una ubicación específica de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="37791-130">Click and drag a column onto the parent level or into a specific location of the hierarchy.</span></span> <span data-ttu-id="37791-131">La columna se copiará como un nivel secundario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="37791-131">The column is copied as a child level of the hierarchy.</span></span>  
  
-   <span data-ttu-id="37791-132">O bien, haga clic con el botón derecho en una columna, seleccione **Agregar a jerarquía**y, después, haga clic en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="37791-132">Or, right-click a column, point to **Add to Hierarchy**, and then click the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37791-133">Puede agregar una columna oculta (una columna que no se muestra en los informes) como un nivel secundario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="37791-133">You can add a hidden column (a column that is hidden from reports) as a child level to the hierarchy.</span></span> <span data-ttu-id="37791-134">El nivel secundario no está oculto.</span><span class="sxs-lookup"><span data-stu-id="37791-134">The child level is not hidden.</span></span>  
  
#### <a name="to-remove-a-child-level-from-a-hierarchy"></a><span data-ttu-id="37791-135">Para quitar un nivel secundario de una jerarquía</span><span class="sxs-lookup"><span data-stu-id="37791-135">To remove a child level from a hierarchy</span></span>  
  
-   <span data-ttu-id="37791-136">Haga clic con el botón derecho en un nivel secundario y, después, haga clic en **Quitar de la jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="37791-136">Right-click a child level, and then click **Remove from Hierarchy**.</span></span>  
  
-   <span data-ttu-id="37791-137">O bien, haga clic en un nivel secundario y, a continuación, presione **Supr**.</span><span class="sxs-lookup"><span data-stu-id="37791-137">Or, click a child level, and then press **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37791-138">Si cambia el nombre de un nivel secundario de la jerarquía, dejará de tener el mismo nombre que la columna de la que se copió.</span><span class="sxs-lookup"><span data-stu-id="37791-138">If you rename a hierarchy child level, it no longer shares the same name as the column that it is copied from.</span></span> <span data-ttu-id="37791-139">Use el comando **Mostrar nombre del origen** para ver de qué columna se copió.</span><span class="sxs-lookup"><span data-stu-id="37791-139">Use the **Show Source Name** command to see which column it was copied from.</span></span>  
  
#### <a name="to-show-a-source-name"></a><span data-ttu-id="37791-140">Para mostrar un nombre de origen</span><span class="sxs-lookup"><span data-stu-id="37791-140">To show a source name</span></span>  
  
-   <span data-ttu-id="37791-141">Haga clic con el botón derecho en un nivel secundario de la jerarquía y, después, haga clic en **Show Source Name**(Mostrar nombre del origen).</span><span class="sxs-lookup"><span data-stu-id="37791-141">Right-click a hierarchy child level, and then click **Show Source Name**.</span></span> <span data-ttu-id="37791-142">Aparece el nombre de la columna de la que se copió la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="37791-142">The name of the column that it was copied from appears.</span></span>  
  
##  <a name="delete-a-hierarchy"></a><a name="bkmk_delete"></a><span data-ttu-id="37791-143">Eliminar una jerarquía</span><span class="sxs-lookup"><span data-stu-id="37791-143">Delete a Hierarchy</span></span>  
  
#### <a name="to-delete-a-hierarchy-and-remove-its-child-levels"></a><span data-ttu-id="37791-144">Para eliminar una jerarquía y quitar sus niveles secundarios</span><span class="sxs-lookup"><span data-stu-id="37791-144">To delete a hierarchy and remove its child levels</span></span>  
  
-   <span data-ttu-id="37791-145">Haga clic con el botón secundario en el nivel primario de la jerarquía y, a continuación, haga clic en Eliminar jerarquía.</span><span class="sxs-lookup"><span data-stu-id="37791-145">Right-click the parent hierarchy level, and then click Delete Hierarchy.</span></span>  
  
-   <span data-ttu-id="37791-146">O bien, haga clic en el nivel primario de la jerarquía y, a continuación, presione Supr.</span><span class="sxs-lookup"><span data-stu-id="37791-146">Or, click the parent hierarchy level, and then press Delete.</span></span> <span data-ttu-id="37791-147">Esto también quitará todos los niveles secundarios.</span><span class="sxs-lookup"><span data-stu-id="37791-147">This also removes all the child levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37791-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37791-148">See Also</span></span>  
 <span data-ttu-id="37791-149">[Diseñador de modelos tabulares &#40;&#41;tabular de SSAS](../tabular-model-designer-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="37791-149">[Tabular Model Designer &#40;SSAS Tabular&#41;](../tabular-model-designer-ssas-tabular.md) </span></span>  
 <span data-ttu-id="37791-150">[Jerarquías &#40;&#41;tabular de SSAS](hierarchies-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="37791-150">[Hierarchies &#40;SSAS Tabular&#41;](hierarchies-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="37791-151">Medidas &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="37791-151">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
