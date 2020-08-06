---
title: Cuadro de diálogo Editar propiedades de tabla (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.edittablepropdb.f1
ms.assetid: 8d913e83-7246-44cc-8fc7-31729023c0d8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6664d244f5f653610b37bd628abdb2263e015c0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676234"
---
# <a name="edit-table-properties-dialog-box-ssas"></a><span data-ttu-id="fa9c6-102">Editar propiedades de tabla, cuadro de diálogo (SSAS)</span><span class="sxs-lookup"><span data-stu-id="fa9c6-102">Edit Table Properties Dialog Box (SSAS)</span></span>
  <span data-ttu-id="fa9c6-103">El cuadro de diálogo **Editar propiedades de tabla** le permite ver y modificar las propiedades de las tablas importadas en el diseñador de modelos mediante el Asistente para la importación de tablas.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-103">The **Edit Table Properties** dialog box enables you to view and modify the properties of tables that are imported into the model designer by using the Table Import Wizard.</span></span> <span data-ttu-id="fa9c6-104">Para obtener acceso a este cuadro de diálogo, en el diseñador de modelos, seleccione una tabla, haga clic en el menú **Tabla** y, a continuación, haga clic en **Propiedades de tabla**.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-104">To access this dialog box, in the model designer, select a table, then click the **Table** menu, and then click **Table Properties**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="fa9c6-105">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="fa9c6-105">UI element list</span></span>  
 <span data-ttu-id="fa9c6-106">Las opciones de este cuadro de diálogo varían dependiendo de si importó los datos originalmente seleccionando las tablas en una lista o usando una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-106">The options for this dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span>  
  
## <a name="table-preview-mode"></a><span data-ttu-id="fa9c6-107">Modo de vista previa de tabla</span><span class="sxs-lookup"><span data-stu-id="fa9c6-107">Table Preview Mode</span></span>  
 <span data-ttu-id="fa9c6-108">**Nombre de la tabla**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-108">**Table name**</span></span>  
 <span data-ttu-id="fa9c6-109">Muestra el nombre de la tabla de datos en el modelo.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-109">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa9c6-110">No puede modificar el nombre aquí.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-110">You cannot edit the name here.</span></span> <span data-ttu-id="fa9c6-111">Sin embargo, puede cambiar el nombre de la tabla haciendo clic con el botón secundario en la pestaña de la tabla en la parte inferior del diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-111">However, you can change the name of the table by right-clicking the table tab at the bottom of the model designer.</span></span>  
  
 <span data-ttu-id="fa9c6-112">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-112">**Connection name**</span></span>  
 <span data-ttu-id="fa9c6-113">Muestra el nombre de la conexión que se usa actualmente.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-113">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="fa9c6-114">**Nombre de origen**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-114">**Source name**</span></span>  
 <span data-ttu-id="fa9c6-115">Se usa para mostrar o cambiar la tabla de la que se obtienen los datos.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-115">Display or change the table from which the data is obtained.</span></span>  
  
 <span data-ttu-id="fa9c6-116">Si se cambia el origen a una tabla que tiene columnas distintas que la tabla actual, aparece un mensaje que advierte que las columnas son distintas.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-116">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="fa9c6-117">En ese caso, debe seleccionar las columnas que desea poner en la tabla actual y hacer clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-117">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="fa9c6-118">Puede reemplazar toda la tabla activando la casilla de la izquierda de la tabla.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-118">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa9c6-119">Al cambiar el origen de datos de una tabla, lo que se hace es reemplazar el contenido de la tabla actual con el contenido de la nueva tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-119">When you change the data source of a table, you essentially replace the contents of the current table with the contents of the new source table.</span></span>  
  
 <span data-ttu-id="fa9c6-120">**Nombres de columna de**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-120">**Column names from**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="fa9c6-121">**Origen**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-121">**Source**</span></span>|<span data-ttu-id="fa9c6-122">Seleccione esta opción para reemplazar los nombres de columna actuales por los nombres de columna de la tabla de origen seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-122">Select this option to replace the current column names with the column names from the selected source table.</span></span>|  
|<span data-ttu-id="fa9c6-123">**Modelo**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-123">**Model**</span></span>|<span data-ttu-id="fa9c6-124">Seleccione esta opción para usar los nombres de columna actual tal como aparecen en el modelo.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-124">Select this option to use the current column names as they exist in the model.</span></span>|  
  
 <span data-ttu-id="fa9c6-125">**Actualizar vista previa**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-125">**Refresh preview**</span></span>  
 <span data-ttu-id="fa9c6-126">Haga clic en esta opción para ver las columnas de datos de la tabla de origen actualmente seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-126">Click to view the columns of data in the currently selected source table.</span></span>  
  
 <span data-ttu-id="fa9c6-127">**Cambiar a**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-127">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="fa9c6-128">**Vista previa de tabla**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-128">**Table preview**</span></span>|<span data-ttu-id="fa9c6-129">Seleccione esta opción de la lista para obtener una vista previa de la tabla seleccionada y un número limitado de filas de datos.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-129">Select this option to preview the selected table and a limited number of rows of data.</span></span>|  
|<span data-ttu-id="fa9c6-130">**Editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-130">**Query editor**</span></span>|<span data-ttu-id="fa9c6-131">Seleccione esta opción para ver la consulta en el origen de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-131">Select this option to view the query against the selected data source.</span></span> <span data-ttu-id="fa9c6-132">Esta opción no está disponible para todos los orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-132">This option is not available for all data sources.</span></span>|  
  
 <span data-ttu-id="fa9c6-133">**Casilla en el encabezado de columna**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-133">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="fa9c6-134">Active la casilla para incluir la columna en la importación de datos.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-134">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="fa9c6-135">Desactive la casilla para quitar la columna de la importación de datos.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-135">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="fa9c6-136">**Botón de flecha abajo en el encabezado de columna**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-136">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="fa9c6-137">Filtre los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-137">Filter data in the column.</span></span>  
  
 <span data-ttu-id="fa9c6-138">**Borrar filtros de fila**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-138">**Clear row filters**</span></span>  
 <span data-ttu-id="fa9c6-139">Haga clic en esta opción para quitar los filtros que se hayan aplicado.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-139">Click to remove any filters that have been applied.</span></span>  
  
 <span data-ttu-id="fa9c6-140">**OK (CORRECTO)**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-140">**OK**</span></span>  
 <span data-ttu-id="fa9c6-141">Haga clic en esta opción para aplicar todos los cambios, incluso el reemplazo de columnas.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-141">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="query-design-mode"></a><span data-ttu-id="fa9c6-142">Modo de diseño de consulta</span><span class="sxs-lookup"><span data-stu-id="fa9c6-142">Query Design Mode</span></span>  
 <span data-ttu-id="fa9c6-143">**Nombre de la tabla**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-143">**Table name**</span></span>  
 <span data-ttu-id="fa9c6-144">Muestra el nombre de la tabla de datos en el modelo.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-144">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa9c6-145">Aquí no se puede modificar el nombre. El nombre de la tabla se puede cambiar haciendo clic con el botón secundario en la pestaña de la tabla de la parte inferior del diseñador.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-145">You cannot edit the name here; however, you can change the name of the table by right-clicking the table tab at the bottom of the designer.</span></span>  
  
 <span data-ttu-id="fa9c6-146">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-146">**Connection name**</span></span>  
 <span data-ttu-id="fa9c6-147">Muestra el nombre de la conexión que se usa actualmente.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-147">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="fa9c6-148">**Cambiar a**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-148">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="fa9c6-149">**Vista previa de tabla**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-149">**Table preview**</span></span>|<span data-ttu-id="fa9c6-150">Seleccione esta opción para obtener una vista previa de la tabla seleccionada y algunas filas de datos.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-150">Select this option to preview the selected table and a few rows of data.</span></span>|  
|<span data-ttu-id="fa9c6-151">**Editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-151">**Query editor**</span></span>|<span data-ttu-id="fa9c6-152">Seleccione esta opción para ver la consulta que se emitirá para el origen de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-152">Select this option to view the query that will be issued against the selected data source.</span></span>|  
  
 <span data-ttu-id="fa9c6-153">**Instrucción SQL**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-153">**Sql statement**</span></span>  
 <span data-ttu-id="fa9c6-154">Muestra la instrucción SQL que se emite al origen de datos actual para recuperar filas.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-154">Displays the SQL statement that is issued against the current data source to retrieve rows.</span></span> <span data-ttu-id="fa9c6-155">De forma predeterminada, se recuperan todas las filas, pero se puede recuperar un subconjunto de filas diseñando un filtro o editando la instrucción SQL manualmente.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-155">By default, all rows are retrieved, but you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="fa9c6-156">**Validación**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-156">**Validate**</span></span>  
 <span data-ttu-id="fa9c6-157">Haga clic en esta opción para comprobar si la instrucción es sintácticamente correcta para el origen de datos y el proveedor seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-157">Click to verify that the statement is syntactically correct for the selected data source and provider.</span></span>  
  
 <span data-ttu-id="fa9c6-158">**Diseño**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-158">**Design**</span></span>  
 <span data-ttu-id="fa9c6-159">Haga clic en esta opción para abrir un diseñador de consultas visual y generar una instrucción de consulta.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-159">Click to open a visual query designer and build a query statement.</span></span> <span data-ttu-id="fa9c6-160">Para obtener información acerca de cómo utilizar el diseñador, presione F1 desde el diseñador.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-160">For information about how to use the designer, press F1 from the designer.</span></span>  
  
 <span data-ttu-id="fa9c6-161">**OK (CORRECTO)**</span><span class="sxs-lookup"><span data-stu-id="fa9c6-161">**OK**</span></span>  
 <span data-ttu-id="fa9c6-162">Haga clic en esta opción para aplicar todos los cambios, incluso el reemplazo de columnas.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-162">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa9c6-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa9c6-163">See Also</span></span>  
 [<span data-ttu-id="fa9c6-164">Definir tablas y columnas &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="fa9c6-164">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tabular-models/tables-and-columns-ssas-tabular.md)  
  
  
