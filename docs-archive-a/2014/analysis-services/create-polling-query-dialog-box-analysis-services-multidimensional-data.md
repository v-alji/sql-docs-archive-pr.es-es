---
title: Cuadro de diálogo Crear consulta de sondeo (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.createpollingquerydialog.f1
ms.assetid: 0f2902b5-796a-4eb0-be03-01514dc01b9a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 186f5d8c1838ed8edaba446e954e39f513bc6fca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671859"
---
# <a name="create-polling-query-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="c9882-102">Cuadro de diálogo Crear consulta de sondeo (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="c9882-102">Create Polling Query Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="c9882-103">Utilice el cuadro de diálogo **Crear consulta de sondeo** en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para crear una consulta de sondeo en la pestaña **Notificaciones** del cuadro de diálogo **Opciones de almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="c9882-103">Use the **Create Polling Query** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a polling query in the **Notifications** tab of the **Storage Options** dialog box.</span></span> <span data-ttu-id="c9882-104">Una consulta de sondeo es, por lo general, una consulta singleton que devuelve un valor que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] puede utilizar para determinar si los cambios se realizaron en una tabla o en otro objeto relacional.</span><span class="sxs-lookup"><span data-stu-id="c9882-104">A polling query is typically a singleton query that returns a value [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] can use to determine if changes have been made to a table or other relational object.</span></span> <span data-ttu-id="c9882-105">Para mostrar el cuadro de diálogo **Crear consulta de sondeo**, haga clic en el botón de puntos suspensivos (**...**) que se encuentra en la columna **Consulta de sondeo** de la cuadrícula correspondiente a la opción **Sondeo programado** de la pestaña **Notificaciones** del cuadro de diálogo **Opciones de almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="c9882-105">You can display the **Create Polling Query** dialog box by clicking the ellipsis button (**...**) on the **Polling Query** column of the grid for the **Scheduled polling** option on the **Notifications** tab of the **Storage Options** dialog box.</span></span> <span data-ttu-id="c9882-106">Para obtener más información sobre la pestaña **Notificaciones** del cuadro de diálogo **Opciones de almacenamiento**, vea [Notificaciones &#40;cuadro de diálogo Opciones de almacenamiento&#41; &#40;Analysis Services - Datos multidimensionales&#41;](notifications-storage-options-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="c9882-106">For more information about the **Notifications** tab of the **Storage Options** dialog box, see [Notifications &#40;Storage Options Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](notifications-storage-options-dialog-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="c9882-107">El tipo de valor que debe devolver la consulta de sondeo depende del tipo de actualización planeado para la caché de OLAP multidimensional (MOLAP) del objeto, en función de la tabla que se está consultando:</span><span class="sxs-lookup"><span data-stu-id="c9882-107">The type of value that should be returned by the polling query depends on the type of updates planned for the multidimensional OLAP (MOLAP) cache of the object based on the table being queried:</span></span>  
  
-   <span data-ttu-id="c9882-108">Si no se ha seleccionado **Habilitar actualizaciones incrementales** en la pestaña **Notificaciones** del cuadro de diálogo **Opciones de almacenamiento**, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] actualiza completamente la caché de MOLAP correspondiente al objeto si se detecta un cambio durante el sondeo programado.</span><span class="sxs-lookup"><span data-stu-id="c9882-108">If **Enable incremental update** is not selected on the **Notifications** tab of the **Storage Options** dialog box, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] fully updates the MOLAP cache for the object if a change is detected during scheduled polling.</span></span> <span data-ttu-id="c9882-109">La consulta de sondeo utilizada debe determinar si se han agregado registros a la tabla desde el último período de sondeo.</span><span class="sxs-lookup"><span data-stu-id="c9882-109">The polling query used should determine if records have been added to the table since the last polling period.</span></span>  
  
-   <span data-ttu-id="c9882-110">Si se ha seleccionado **Habilitar actualizaciones incrementales** en la pestaña **Notificaciones** del cuadro de diálogo **Opciones de almacenamiento**, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] actualiza incrementalmente la caché de MOLAP correspondiente al objeto cuando se detecta un cambio durante el sondeo programado.</span><span class="sxs-lookup"><span data-stu-id="c9882-110">If **Enable incremental update** is selected on the **Notifications** tab of the **Storage Options** dialog box, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] incrementally updates the MOLAP cache for the object if a change is detected during scheduled polling.</span></span> <span data-ttu-id="c9882-111">La consulta de sondeo usada debe determinar el último registro de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c9882-111">The polling query used should determine the last record in the table.</span></span>  
  
 <span data-ttu-id="c9882-112">Por ejemplo, puede utilizar las siguientes consultas de sondeo para proporcionar actualizaciones completas o incrementales para la dimensión Cliente en la base de datos de ejemplo [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9882-112">For example, you can use the following polling queries to supply either full or incremental updates for the Customer dimension in the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database:</span></span>  
  
|<span data-ttu-id="c9882-113">Tipo de actualización</span><span class="sxs-lookup"><span data-stu-id="c9882-113">Update type</span></span>|<span data-ttu-id="c9882-114">Consulta de sondeo</span><span class="sxs-lookup"><span data-stu-id="c9882-114">Polling query</span></span>|  
|-----------------|-------------------|  
|<span data-ttu-id="c9882-115">Actualización completa</span><span class="sxs-lookup"><span data-stu-id="c9882-115">Full update</span></span>|`SELECT`<br /><br /> `COUNT(*) AS TotalCount`<br /><br /> `FROM`<br /><br /> `[dbo].[DimCustomer]`|  
|<span data-ttu-id="c9882-116">Actualización incremental</span><span class="sxs-lookup"><span data-stu-id="c9882-116">Incremental update</span></span>|`SELECT`<br /><br /> `MAX([CustomerKey]) AS LastCustomerKey`<br /><br /> `FROM`<br /><br /> `[dbo].[DimCustomer]`|  
  
 <span data-ttu-id="c9882-117">Para más información sobre las actualizaciones incrementales para notificaciones de sondeos programados, vea [Almacenamiento en caché automático &#40;Particiones&#41;](multidimensional-models-olap-logical-cube-objects/partitions-proactive-caching.md).</span><span class="sxs-lookup"><span data-stu-id="c9882-117">For more information about full and incremental updates for scheduled polling notifications, see [Proactive Caching &#40;Partitions&#41;](multidimensional-models-olap-logical-cube-objects/partitions-proactive-caching.md).</span></span>  
  
 <span data-ttu-id="c9882-118">La consulta proporcionada debe ser un comando de consulta válido para el proveedor subyacente.</span><span class="sxs-lookup"><span data-stu-id="c9882-118">The query entered must be a valid query command for the underlying provider.</span></span> <span data-ttu-id="c9882-119">La consulta se prepara para la validación con el proveedor correspondiente, así como para identificar las columnas devueltas.</span><span class="sxs-lookup"><span data-stu-id="c9882-119">The query is prepared with the underlying provider for validation, and to identify the columns returned.</span></span> <span data-ttu-id="c9882-120">El cuadro de diálogo puede presentar dos vistas:</span><span class="sxs-lookup"><span data-stu-id="c9882-120">The dialog box can present two views:</span></span>  
  
-   <span data-ttu-id="c9882-121">Generador de consultas de Visual Database Tools (VDT)</span><span class="sxs-lookup"><span data-stu-id="c9882-121">Visual Database Tools (VDT) Query Builder</span></span>  
  
     <span data-ttu-id="c9882-122">El Generador de consultas de VDT proporciona a todos los usuarios un conjunto de herramientas de interfaz de usuario para crear y probar de forma visual consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="c9882-122">For all users, the VDT Query Builder view provides a set of user interface tools for visually constructing and testing a SQL query.</span></span>  
  
-   <span data-ttu-id="c9882-123">Generador de consultas genérico</span><span class="sxs-lookup"><span data-stu-id="c9882-123">Generic Query Builder</span></span>  
  
     <span data-ttu-id="c9882-124">El Generador de consultas genérico proporciona a los usuarios avanzados una interfaz de usuario más sencilla y más directa para crear y probar consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="c9882-124">For advanced users, the Generic Query Builder view provides a simpler, more direct user interface for constructing and testing a SQL query.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9882-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="c9882-125">Options</span></span>  
 <span data-ttu-id="c9882-126">**Data Source** (Origen de datos)</span><span class="sxs-lookup"><span data-stu-id="c9882-126">**Data Source**</span></span>  
 <span data-ttu-id="c9882-127">Especifique el origen de datos para la consulta.</span><span class="sxs-lookup"><span data-stu-id="c9882-127">Specifies the data source for the query.</span></span>  
  
 <span data-ttu-id="c9882-128">**Definición de la consulta**</span><span class="sxs-lookup"><span data-stu-id="c9882-128">**Query definition**</span></span>  
 <span data-ttu-id="c9882-129">La definición de la consulta proporciona una barra de herramientas y paneles (que dependerán de la vista seleccionada) para definir y probar consultas.</span><span class="sxs-lookup"><span data-stu-id="c9882-129">The query definition provides a toolbar and panes in which to define and test the query, depending on the selected view.</span></span>  
  
 <span data-ttu-id="c9882-130">**Barra de herramientas**</span><span class="sxs-lookup"><span data-stu-id="c9882-130">**Toolbar**</span></span>  
 <span data-ttu-id="c9882-131">Use la barra de herramientas para administrar conjuntos de datos, seleccionar los paneles que desea mostrar y controlar diversas funciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="c9882-131">Use the toolbar to manage datasets, select panes to display, and control various query functions.</span></span>  
  
|<span data-ttu-id="c9882-132">Value</span><span class="sxs-lookup"><span data-stu-id="c9882-132">Value</span></span>|<span data-ttu-id="c9882-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9882-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c9882-134">**Cambiar a Generador de consultas genérico**</span><span class="sxs-lookup"><span data-stu-id="c9882-134">**Switch to Generic Query Builder**</span></span>|<span data-ttu-id="c9882-135">Seleccione esta opción si desea mostrar únicamente las opciones disponibles para la vista del Generador de consultas genérico.</span><span class="sxs-lookup"><span data-stu-id="c9882-135">Select to display only the options available to the Generic Query Builder view.</span></span> <span data-ttu-id="c9882-136">Se mostrará solo una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c9882-136">Only the following options are displayed:</span></span><br /><br /> <span data-ttu-id="c9882-137">**Panel SQL**</span><span class="sxs-lookup"><span data-stu-id="c9882-137">**SQL pane**</span></span><br /><br /> <span data-ttu-id="c9882-138">**Panel de resultados**</span><span class="sxs-lookup"><span data-stu-id="c9882-138">**Result pane**</span></span><br /><br /> <span data-ttu-id="c9882-139">**Barra de herramientas**, que contiene únicamente **Cambiar a Generador de consultas de VDT** y **Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="c9882-139">**Toolbar**, containing only **Switch to VDT Query Builder** and **Run**</span></span><br /><br /> <br /><br /> <span data-ttu-id="c9882-140">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-140">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-141">**Cambiar a Generador de consultas de VDT**</span><span class="sxs-lookup"><span data-stu-id="c9882-141">**Switch to VDT Query Builder**</span></span>|<span data-ttu-id="c9882-142">Seleccione esta opción si desea mostrar todas las opciones disponibles para la vista del Generador de consultas de Visual Database Tools (VDT).</span><span class="sxs-lookup"><span data-stu-id="c9882-142">Select to display all of the options available to the Visual Database Tools (VDT) Query Builder view.</span></span><br /><br /> <span data-ttu-id="c9882-143">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas genérico** .</span><span class="sxs-lookup"><span data-stu-id="c9882-143">Note: This option is displayed only if **Switch to Generic Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-144">**Mostrar u ocultar panel de diagrama**</span><span class="sxs-lookup"><span data-stu-id="c9882-144">**Show/Hide Diagram Pane**</span></span>|<span data-ttu-id="c9882-145">Muestra u oculta el **panel Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="c9882-145">Shows or hides the **Diagram pane**.</span></span><br /><br /> <span data-ttu-id="c9882-146">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-146">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-147">**Mostrar u ocultar panel de cuadrícula**</span><span class="sxs-lookup"><span data-stu-id="c9882-147">**Show/Hide Grid Pane**</span></span>|<span data-ttu-id="c9882-148">Muestra u oculta el **panel Cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="c9882-148">Shows or hides the **Grid pane**.</span></span><br /><br /> <span data-ttu-id="c9882-149">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-149">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-150">**Mostrar u ocultar panel de SQL**</span><span class="sxs-lookup"><span data-stu-id="c9882-150">**Show/Hide SQL Pane**</span></span>|<span data-ttu-id="c9882-151">Muestra u oculta el **panel de SQL**.</span><span class="sxs-lookup"><span data-stu-id="c9882-151">Shows or hides the **SQL pane**.</span></span><br /><br /> <span data-ttu-id="c9882-152">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-152">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-153">**Mostrar u ocultar el panel Resultado**</span><span class="sxs-lookup"><span data-stu-id="c9882-153">**Show/Hide Result Pane**</span></span>|<span data-ttu-id="c9882-154">Muestra u oculta el **panel Resultado**.</span><span class="sxs-lookup"><span data-stu-id="c9882-154">Shows or hides the **Result pane**.</span></span><br /><br /> <span data-ttu-id="c9882-155">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-155">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-156">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="c9882-156">**Run**</span></span>|<span data-ttu-id="c9882-157">Ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="c9882-157">Runs the query.</span></span> <span data-ttu-id="c9882-158">Los resultados se muestran en el **panel Resultado**.</span><span class="sxs-lookup"><span data-stu-id="c9882-158">Results are displayed in the **Result pane**.</span></span>|  
|<span data-ttu-id="c9882-159">**Comprobar SQL**</span><span class="sxs-lookup"><span data-stu-id="c9882-159">**Verify SQL**</span></span>|<span data-ttu-id="c9882-160">Comprueba la instrucción SQL de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c9882-160">Verifies the SQL statement in the query.</span></span><br /><br /> <span data-ttu-id="c9882-161">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-161">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-162">**Orden ascendente**</span><span class="sxs-lookup"><span data-stu-id="c9882-162">**Sort Ascending**</span></span>|<span data-ttu-id="c9882-163">Ordena de forma ascendente las filas de salida de la columna seleccionada en el **panel Cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="c9882-163">Sorts output rows on the selected column in the **Grid pane**, in ascending order.</span></span><br /><br /> <span data-ttu-id="c9882-164">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-164">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-165">**Orden descendente**</span><span class="sxs-lookup"><span data-stu-id="c9882-165">**Sort Descending**</span></span>|<span data-ttu-id="c9882-166">Ordena de forma descendente las filas de salida de la columna seleccionada en el **panel Cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="c9882-166">Sorts output rows on the selected column in the **Grid pane**, in descending order.</span></span><br /><br /> <span data-ttu-id="c9882-167">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-167">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-168">**Quitar filtro**</span><span class="sxs-lookup"><span data-stu-id="c9882-168">**Remove Filter**</span></span>|<span data-ttu-id="c9882-169">Quita los criterios de ordenación, si corresponde, para la fila seleccionada en el **panel Cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="c9882-169">Removes sort criteria, if applicable, for the selected row in the **Grid pane**.</span></span><br /><br /> <span data-ttu-id="c9882-170">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-170">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-171">**Usar GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="c9882-171">**Use Group By**</span></span>|<span data-ttu-id="c9882-172">Agrega la funcionalidad de agrupamiento a la consulta.</span><span class="sxs-lookup"><span data-stu-id="c9882-172">Adds grouping functionality to the query.</span></span><br /><br /> <span data-ttu-id="c9882-173">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-173">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
|<span data-ttu-id="c9882-174">**Agregar tabla**</span><span class="sxs-lookup"><span data-stu-id="c9882-174">**Add Table**</span></span>|<span data-ttu-id="c9882-175">Muestra el cuadro de diálogo **Agregar tabla** para agregar una nueva tabla o vista a la consulta.</span><span class="sxs-lookup"><span data-stu-id="c9882-175">Displays the **Add Table** dialog box to add a new table or view to the query.</span></span> <span data-ttu-id="c9882-176">Para obtener más información sobre el cuadro de diálogo **Agregar tabla**, vea [Cuadro de diálogo Agregar tabla &#40;Analysis Services - Datos multidimensionales&#41;](add-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="c9882-176">For more information about the **Add Table** dialog box, see [Add Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](add-table-dialog-box-analysis-services-multidimensional-data.md).</span></span><br /><br /> <span data-ttu-id="c9882-177">Nota: Esta opción solo se muestra si se selecciona **Cambiar a Generador de consultas de VDT** .</span><span class="sxs-lookup"><span data-stu-id="c9882-177">Note: This option is displayed only if **Switch to VDT Query Builder** is selected.</span></span>|  
  
 <span data-ttu-id="c9882-178">**Panel Diagrama**</span><span class="sxs-lookup"><span data-stu-id="c9882-178">**Diagram pane**</span></span>  
 <span data-ttu-id="c9882-179">Muestra en un diagrama los objetos a los que se hace referencia en la consulta.</span><span class="sxs-lookup"><span data-stu-id="c9882-179">Displays the objects referenced by the query as a diagram.</span></span> <span data-ttu-id="c9882-180">El diagrama muestra las tablas incluidas en la consulta y cómo se combinan.</span><span class="sxs-lookup"><span data-stu-id="c9882-180">The diagram shows the tables included in the query, and how they are joined.</span></span> <span data-ttu-id="c9882-181">Active o desactive la casilla situada junto a una columna de la tabla para agregarla a (o quitarla de) la salida de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c9882-181">Select or clear the check box next to a column in a table to add or remove it from the query output.</span></span>  
  
 <span data-ttu-id="c9882-182">Al agregar tablas a la consulta, el cuadro de diálogo crea combinaciones entre las tablas teniendo en cuenta las claves.</span><span class="sxs-lookup"><span data-stu-id="c9882-182">When you add tables to the query, the dialog box creates joins between tables based on the keys in the table.</span></span> <span data-ttu-id="c9882-183">Para agregar una combinación, arrastre un campo de una de las tablas a un campo de otra tabla.</span><span class="sxs-lookup"><span data-stu-id="c9882-183">To add a join, drag a field from one table onto a field in another table.</span></span> <span data-ttu-id="c9882-184">Para administrar una combinación, haga clic en ella con el botón secundario.</span><span class="sxs-lookup"><span data-stu-id="c9882-184">To manage a join, right-click the join.</span></span>  
  
 <span data-ttu-id="c9882-185">Haga clic con el botón derecho en el **panel Diagrama** para agregar o quitar tablas, seleccionar todas las tablas y mostrar u ocultar paneles.</span><span class="sxs-lookup"><span data-stu-id="c9882-185">Right-click the **Diagram pane** to add or remove tables, select all the tables, and show or hide panes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9882-186"> Los contenidos del **panel Diagrama**, el **panel Cuadrícula**y el **panel de SQL** están sincronizados de forma que los cambios realizados en un panel se reflejen en los otros dos paneles.</span><span class="sxs-lookup"><span data-stu-id="c9882-186">The contents of the **Diagram pane**, **Grid pane**, and **SQL pane** are synchronized, so that changes in one pane are reflected in the other two panes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c9882-187">No es posible cambiar los tipos de consulta en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c9882-187">Changing query types is not supported by the dialog box.</span></span>  
  
 <span data-ttu-id="c9882-188">**panel Cuadrícula**</span><span class="sxs-lookup"><span data-stu-id="c9882-188">**Grid pane**</span></span>  
 <span data-ttu-id="c9882-189">Muestra en una cuadrícula los objetos a los que se hace referencia en la consulta.</span><span class="sxs-lookup"><span data-stu-id="c9882-189">Displays the objects referenced by the query in a grid.</span></span> <span data-ttu-id="c9882-190">Puede usar este panel para agregar y quitar columnas en la consulta, y para cambiar la configuración de cada columna.</span><span class="sxs-lookup"><span data-stu-id="c9882-190">You can use this pane to add and remove columns to the query and change the settings for each column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9882-191"> Los contenidos del **panel Diagrama**, el **panel Cuadrícula**y el **panel de SQL** están sincronizados de forma que los cambios realizados en un panel se reflejen en los otros dos paneles.</span><span class="sxs-lookup"><span data-stu-id="c9882-191">The contents of the **Diagram pane**, **Grid pane**, and **SQL pane** are synchronized, so that changes in one pane are reflected in the other two panes.</span></span>  
  
 <span data-ttu-id="c9882-192">**Panel SQL**</span><span class="sxs-lookup"><span data-stu-id="c9882-192">**SQL pane**</span></span>  
 <span data-ttu-id="c9882-193">Muestra la consulta como una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="c9882-193">Displays the query as a SQL statement.</span></span> <span data-ttu-id="c9882-194">Le permite modificar la instrucción SQL de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c9882-194">Type to change the SQL statement for the query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9882-195"> Los contenidos del **panel Diagrama**, el **panel Cuadrícula**y el **panel de SQL** están sincronizados de forma que los cambios realizados en un panel se reflejen en los otros dos paneles.</span><span class="sxs-lookup"><span data-stu-id="c9882-195">The contents of the **Diagram pane**, **Grid pane**, and **SQL pane** are synchronized, so that changes in one pane are reflected in the other two panes.</span></span>  
  
 <span data-ttu-id="c9882-196">**Panel de resultados**</span><span class="sxs-lookup"><span data-stu-id="c9882-196">**Result pane**</span></span>  
 <span data-ttu-id="c9882-197">Muestra los resultados de la consulta al hacer clic en **Ejecutar** en el panel **Barra de herramientas** .</span><span class="sxs-lookup"><span data-stu-id="c9882-197">Displays the results of the query when you click **Run** on the **Toolbar** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9882-198">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9882-198">See Also</span></span>  
 [<span data-ttu-id="c9882-199">Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="c9882-199">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  