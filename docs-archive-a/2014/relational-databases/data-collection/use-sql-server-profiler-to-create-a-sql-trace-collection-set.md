---
title: Usar SQL Server Profiler para crear un conjunto de recopilación de seguimiento de SQL (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace collector set
ms.assetid: b6941dc0-50f5-475d-82eb-ce7c68117489
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e9c9514fef8069cef615d1480aad1e0acd1582cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676007"
---
# <a name="use-sql-server-profiler-to-create-a-sql-trace-collection-set-sql-server-management-studio"></a><span data-ttu-id="1706d-102">Usar SQL Server Profiler para crear un conjunto de recopilación de Seguimiento SQL (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1706d-102">Use SQL Server Profiler to Create a SQL Trace Collection Set (SQL Server Management Studio)</span></span>
  <span data-ttu-id="1706d-103">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] puede aprovechar la funcionalidad de seguimiento del lado servidor de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para exportar una definición de seguimiento y emplearla después para crear un conjunto de recopilación que use el tipo de recopilador genérico de Seguimiento de SQL.</span><span class="sxs-lookup"><span data-stu-id="1706d-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] you can exploit the server-side trace capabilities of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to export a trace definition that you can use to create a collection set that uses the Generic SQL Trace collector type.</span></span> <span data-ttu-id="1706d-104">En este proceso hay dos partes:</span><span class="sxs-lookup"><span data-stu-id="1706d-104">There are two parts to this process:</span></span>  
  
1.  <span data-ttu-id="1706d-105">Crear y exportar un seguimiento de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1706d-105">Create and export a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace.</span></span>  
  
2.  <span data-ttu-id="1706d-106">Crear un script de un nuevo conjunto de recopilación basado en un seguimiento exportado.</span><span class="sxs-lookup"><span data-stu-id="1706d-106">Script a new collection set based on an exported trace.</span></span>  
  
 <span data-ttu-id="1706d-107">El escenario para los procedimientos siguientes implica recopilar datos sobre cualquier procedimiento almacenado que requiera 80 milisegundos o más en completarse.</span><span class="sxs-lookup"><span data-stu-id="1706d-107">The scenario for the following procedures involves collecting data about any stored procedure that requires 80 milliseconds or longer to complete.</span></span> <span data-ttu-id="1706d-108">Para completar estos procedimientos debería ser capaz de:</span><span class="sxs-lookup"><span data-stu-id="1706d-108">In order to complete these procedures you should be able to:</span></span>  
  
-   <span data-ttu-id="1706d-109">Usar [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para crear y configurar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1706d-109">Use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create and configure a trace.</span></span>  
  
-   <span data-ttu-id="1706d-110">Usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para abrir, modificar y ejecutar una consulta.</span><span class="sxs-lookup"><span data-stu-id="1706d-110">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to open, edit, and execute a query.</span></span>  
  
### <a name="create-and-export-a-sql-server-profiler-trace"></a><span data-ttu-id="1706d-111">Crear y exportar un seguimiento de SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1706d-111">Create and export a SQL Server Profiler trace</span></span>  
  
1.  <span data-ttu-id="1706d-112">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1706d-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="1706d-113">En el menú **Herramientas** , haga clic en **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="1706d-113">(On the **Tools** menu, click **SQL Server Profiler**.)</span></span>  
  
2.  <span data-ttu-id="1706d-114">En el cuadro de diálogo **Conectar con el servidor** , haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="1706d-114">In the **Connect to Server** dialog box, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="1706d-115">Para este escenario, asegúrese de que los valores de duración estén configurados para mostrarse en milisegundos (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="1706d-115">For this scenario, ensure that duration values are configured to display in milliseconds (the default).</span></span> <span data-ttu-id="1706d-116">Para ello, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1706d-116">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="1706d-117">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="1706d-117">On the **Tools** menu, click **Options**.</span></span>  
  
    2.  <span data-ttu-id="1706d-118">En el área **Opciones de visualización** , asegúrese de que esté desactivada la casilla Mostrar valores en la columna Duración en microsegundos.</span><span class="sxs-lookup"><span data-stu-id="1706d-118">In the **Display Options** area, ensure that the Show values in Duration column in microseconds check box is cleared.</span></span>  
  
    3.  <span data-ttu-id="1706d-119">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Opciones generales** .</span><span class="sxs-lookup"><span data-stu-id="1706d-119">Click **OK** to close the **General Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="1706d-120">En el menú **Archivo** , haga clic en **Nuevo seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="1706d-120">On the **File** menu, click **New Trace**.</span></span>  
  
5.  <span data-ttu-id="1706d-121">En el cuadro de diálogo **Conectar con el servidor** , seleccione el servidor con el que desea conectarse y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="1706d-121">In the **Connect to Server** dialog box, select the server that you want to connect to, and then click **Connect**.</span></span>  
  
     <span data-ttu-id="1706d-122">Aparecerá el cuadro de diálogo **Propiedades de seguimiento** .</span><span class="sxs-lookup"><span data-stu-id="1706d-122">The **Trace Properties** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="1706d-123">En la pestaña **General** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1706d-123">On the **General** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="1706d-124">En el cuadro **Nombre de seguimiento** , escriba el nombre que desee usar para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1706d-124">In the **Trace name** box, type the name that you want to use for the trace.</span></span> <span data-ttu-id="1706d-125">En este ejemplo, el nombre del seguimiento es `SPgt80`.</span><span class="sxs-lookup"><span data-stu-id="1706d-125">For this example, the trace name is `SPgt80`.</span></span>  
  
    2.  <span data-ttu-id="1706d-126">En la lista **Usar la plantilla**, seleccione la plantilla que desea usar para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1706d-126">In the **Use the template list**, select the template to use for the trace.</span></span> <span data-ttu-id="1706d-127">Para este ejemplo, haga clic en **TSQL_SPs**.</span><span class="sxs-lookup"><span data-stu-id="1706d-127">For this example, click **TSQL_SPs**.</span></span>  
  
7.  <span data-ttu-id="1706d-128">En la pestaña **Selección de eventos** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1706d-128">On the **Events Selection** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="1706d-129">Identifique los eventos que se van a usar para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1706d-129">Identify the events to use for the trace.</span></span> <span data-ttu-id="1706d-130">En este ejemplo, desactive todas las casillas de la columna **Eventos** excepto **ExistingConnection** y **SP:Completed**.</span><span class="sxs-lookup"><span data-stu-id="1706d-130">For this example, clear all check boxes in the **Events** column, except for **ExistingConnection** and **SP:Completed**.</span></span>  
  
    2.  <span data-ttu-id="1706d-131">En la esquina inferior derecha, active la casilla **Mostrar todas las columnas** .</span><span class="sxs-lookup"><span data-stu-id="1706d-131">In the lower-right corner, select the **Show all columns** check box.</span></span>  
  
    3.  <span data-ttu-id="1706d-132">Haga clic en la fila **SP:Completed** .</span><span class="sxs-lookup"><span data-stu-id="1706d-132">Click the **SP:Completed** row.</span></span>  
  
    4.  <span data-ttu-id="1706d-133">Desplácese por la fila hasta la columna **Duración** y, a continuación, active la casilla **Duración** .</span><span class="sxs-lookup"><span data-stu-id="1706d-133">Scroll across the row to the **Duration** column, and then select the **Duration** check box.</span></span>  
  
8.  <span data-ttu-id="1706d-134">En la esquina inferior derecha, haga clic en **Filtros de columna** para abrir el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="1706d-134">In the lower-right corner, click **Column Filters** to open the **Edit Filter** dialog box.</span></span> <span data-ttu-id="1706d-135">En el cuadro de diálogo **Editar filtro** , realice las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="1706d-135">In the **Edit Filter** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="1706d-136">En la lista de filtros, haga clic en **Duración**.</span><span class="sxs-lookup"><span data-stu-id="1706d-136">In the filter list, click **Duration**.</span></span>  
  
    2.  <span data-ttu-id="1706d-137">En la ventana de operadores booleanos, expanda el nodo **mayor o igual que** , escriba `80` como valor y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1706d-137">In the Boolean operator window, expand the **Greater than or equal** node, type `80` as the value, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="1706d-138">Haga clic en **Ejecutar** para iniciar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1706d-138">Click **Run** to start the trace.</span></span>  
  
10. <span data-ttu-id="1706d-139">En la barra de herramientas, haga clic en **Detener seguimiento seleccionado** o **Pausar seguimiento seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="1706d-139">On the toolbar, click **Stop Selected Trace** or **Pause Selected Trace**.</span></span>  
  
11. <span data-ttu-id="1706d-140">En el menú **Archivo** , seleccione **Exportar**, **Definición de seguimiento de scripts**y, a continuación, haga clic en **Para el conjunto de recopilación de Seguimiento de SQL**.</span><span class="sxs-lookup"><span data-stu-id="1706d-140">On the **File** menu, point to **Export**, point to **Script Trace Definition**, and then click **For SQL Trace Collection Set**.</span></span>  
  
12. <span data-ttu-id="1706d-141">En el cuadro **Nombre de archivo** del cuadro de diálogo **Guardar como** , escriba el nombre que desea usar para la definición de seguimiento y, a continuación, guárdela en la ubicación que desee.</span><span class="sxs-lookup"><span data-stu-id="1706d-141">In the **Save As** dialog box, type the name that you want to use for the trace definition in the **File name** box, and then save it in the location that you want.</span></span> <span data-ttu-id="1706d-142">En este ejemplo, el nombre de archivo es igual que el nombre de seguimiento (SPgt80).</span><span class="sxs-lookup"><span data-stu-id="1706d-142">For this example, the file name is the same as the trace name (SPgt80).</span></span>  
  
13. <span data-ttu-id="1706d-143">Haga clic en **Aceptar** cuando aparezca el mensaje que indica que el archivo se guardó correctamente y, a continuación, cierre [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1706d-143">Click **OK** when you receive a message that the file was successfully saved, and then close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="script-a-new-collection-set-from-a-sql-server-profiler-trace"></a><span data-ttu-id="1706d-144">Crear un script de un nuevo conjunto de recopilación a partir de un seguimiento de SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1706d-144">Script a new collection set from a SQL Server Profiler trace</span></span>  
  
1.  <span data-ttu-id="1706d-145">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Archivo** , seleccione **Abrir** y haga clic en **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="1706d-145">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, point to **Open,** and then click **File**.</span></span>  
  
2.  <span data-ttu-id="1706d-146">En el cuadro de diálogo **Abrir archivo** , localice el archivo que creó en el procedimiento anterior (SPgt80) y ábralo.</span><span class="sxs-lookup"><span data-stu-id="1706d-146">In the **Open File** dialog box, locate and then open the file that you created in the previous procedure (SPgt80).</span></span>  
  
     <span data-ttu-id="1706d-147">La información de seguimiento que guardó se abre en una ventana Consulta y se combina en un script que puede ejecutar para crear el nuevo conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="1706d-147">The trace information that you saved is opened in a Query window and merged into a script that you can run to create the new collection set.</span></span>  
  
3.  <span data-ttu-id="1706d-148">Desplácese a través del script y realice las sustituciones siguientes, que están anotadas en el texto de los comentarios del script:</span><span class="sxs-lookup"><span data-stu-id="1706d-148">Scroll through the script and make the following replacements, which are noted in the script comment text:</span></span>  
  
    -   <span data-ttu-id="1706d-149">Reemplace **SQLTrace Collection Set Name Here** por el nombre que desea usar para el conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="1706d-149">Replace **SQLTrace Collection Set Name Here** with the name that you want to use for the collection set.</span></span> <span data-ttu-id="1706d-150">En este ejemplo, asigne el nombre `SPROC_CollectionSet` al conjunto de colección.</span><span class="sxs-lookup"><span data-stu-id="1706d-150">For this example, name the collection set `SPROC_CollectionSet`.</span></span>  
  
    -   <span data-ttu-id="1706d-151">Reemplace **SQLTrace Collection Item Name Here** por el nombre que desea usar para el elemento de recopilación.</span><span class="sxs-lookup"><span data-stu-id="1706d-151">Replace **SQLTrace Collection Item Name Here** with the name that you want to use for the collection item.</span></span> <span data-ttu-id="1706d-152">En este ejemplo, asigne el nombre `SPROC_Collection_Item` al elemento de colección.</span><span class="sxs-lookup"><span data-stu-id="1706d-152">For this example, name the collection item `SPROC_Collection_Item`.</span></span>  
  
4.  <span data-ttu-id="1706d-153">Haga clic en **Ejecutar** para ejecutar la consulta y crear el conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="1706d-153">Click **Execute** to run the query and to create the collection set.</span></span>  
  
5.  <span data-ttu-id="1706d-154">En el Explorador de objetos, compruebe que se ha creado el conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="1706d-154">In Object Explorer, verify that the collection set was created.</span></span> <span data-ttu-id="1706d-155">Para ello, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1706d-155">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="1706d-156">Haga clic con el botón derecho en **Administración**y, después, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="1706d-156">Right-click **Management**, and then click **Refresh**.</span></span>  
  
    2.  <span data-ttu-id="1706d-157">Expanda **Administración**y, a continuación, expanda **Recopilación de datos**.</span><span class="sxs-lookup"><span data-stu-id="1706d-157">Expand **Management**, and then expand **Data Collection**.</span></span>  
  
     <span data-ttu-id="1706d-158">El `SPROC_CollectionSet` conjunto de recopilación aparece en el mismo nivel que el nodo **conjuntos de recopilación de datos del sistema** .</span><span class="sxs-lookup"><span data-stu-id="1706d-158">The `SPROC_CollectionSet` collection set appears at the same level as the **System Data Collection Sets** node.</span></span> <span data-ttu-id="1706d-159">De manera predeterminada, el conjunto de recopilación está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1706d-159">By default, the collection set is disabled.</span></span>  
  
6.  <span data-ttu-id="1706d-160">Use el Explorador de objetos para editar las propiedades de SPROC_CollectionSet, como el modo de recopilación y la programación de carga.</span><span class="sxs-lookup"><span data-stu-id="1706d-160">Use Object Explorer to edit the properties of SPROC_CollectionSet, such as the collection mode and upload schedule.</span></span> <span data-ttu-id="1706d-161">Realice los mismos procedimientos que usaría para los conjuntos de recopilación de datos del sistema que se proporcionan con el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="1706d-161">Follow the same procedures that you would for the System Data collection sets that are provided with the data collector.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1706d-162">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1706d-162">Example</span></span>  
 <span data-ttu-id="1706d-163">El ejemplo de código siguiente es el script final que resulta de los pasos que se documentan en los procedimientos anteriores.</span><span class="sxs-lookup"><span data-stu-id="1706d-163">The following code sample is the final script resulting from the steps documented in the preceding procedures.</span></span>  
  
```  
/*************************************************************/  
-- SQL Trace collection set generated from SQL Server Profiler  
-- Date: 11/19/2007  12:55:31 AM  
/*************************************************************/  
  
USE msdb  
GO  
  
BEGIN TRANSACTION  
BEGIN TRY  
  
-- Define collection set  
-- ***  
-- *** Replace 'SqlTrace Collection Set Name Here' in the   
-- *** following script with the name you want  
-- *** to use for the collection set.  
-- ***  
DECLARE @collection_set_id int;  
EXEC [dbo].[sp_syscollector_create_collection_set]  
    @name = N'SPROC_CollectionSet',  
    @schedule_name = N'CollectorSchedule_Every_15min',  
    @collection_mode = 0, -- cached mode needed for Trace collections  
    @logging_level = 0, -- minimum logging  
    @days_until_expiration = 5,  
    @description = N'Collection set generated by SQL Server Profiler',  
    @collection_set_id = @collection_set_id output;  
SELECT @collection_set_id;  
  
-- Define input and output variables for the collection item.  
DECLARE @trace_definition xml;  
DECLARE @collection_item_id int;  
  
-- Define the trace parameters as an XML variable  
SELECT @trace_definition = convert(xml,   
N'<ns:SqlTraceCollector xmlns:ns"DataCollectorType" use_default="0">  
<Events>  
  <EventType name="Sessions">  
    <Event id="17" name="ExistingConnection" columnslist="1,2,14,26,3,35,12" />  
  </EventType>  
  <EventType name="Stored Procedures">  
    <Event id="43" name="SP:Completed" columnslist="1,2,26,34,3,35,12,13,14,22" />  
  </EventType>  
</Events>  
<Filters>  
  <Filter columnid="13" columnname="Duration" logical_operator="AND" comparison_operator="GE" value="80000L" />  
</Filters>  
</ns:SqlTraceCollector>  
');  
  
-- Retrieve the collector type GUID for the trace collector type.  
DECLARE @collector_type_GUID uniqueidentifier;  
SELECT @collector_type_GUID = collector_type_uid FROM [dbo].[syscollector_collector_types] WHERE name = N'Generic SQL Trace Collector Type';  
  
-- Create the trace collection item.  
-- ***  
-- *** Replace 'SqlTrace Collection Item Name Here' in   
-- *** the following script with the name you want to  
-- *** use for the collection item.  
-- ***  
EXEC [dbo].[sp_syscollector_create_collection_item]  
   @collection_set_id = @collection_set_id,  
   @collector_type_uid = @collector_type_GUID,  
   @name = N'SPROC_Collection_Item',  
   @frequency = 900, -- specified the frequency for checking to see if trace is still running  
   @parameters = @trace_definition,  
   @collection_item_id = @collection_item_id output;  
SELECT @collection_item_id;  
  
COMMIT TRANSACTION;  
END TRY  
  
BEGIN CATCH  
ROLLBACK TRANSACTION;  
DECLARE @ErrorMessage nvarchar(4000);  
DECLARE @ErrorSeverity int;  
DECLARE @ErrorState int;  
DECLARE @ErrorNumber int;  
DECLARE @ErrorLine int;  
DECLARE @ErrorProcedure nvarchar(200);  
SELECT @ErrorLine = ERROR_LINE(),  
       @ErrorSeverity = ERROR_SEVERITY(),  
       @ErrorState = ERROR_STATE(),  
       @ErrorNumber = ERROR_NUMBER(),  
       @ErrorMessage = ERROR_MESSAGE(),  
       @ErrorProcedure = ISNULL(ERROR_PROCEDURE(), '-');  
RAISERROR (14684, @ErrorSeverity, 1 , @ErrorNumber, @ErrorSeverity, @ErrorState, @ErrorProcedure, @ErrorLine, @ErrorMessage);  
END CATCH;  
GO  
```  
  
  
