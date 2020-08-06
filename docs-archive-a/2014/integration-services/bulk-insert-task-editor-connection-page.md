---
title: Editor de la tarea inserción masiva (página conexión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.connection.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: 51252c20-8865-4ede-a3fd-bd73a968f47d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2cd722fd8520ff011c0d57040a55d624178e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748882"
---
# <a name="bulk-insert-task-editor-connection-page"></a><span data-ttu-id="08106-102">Editor de la tarea Inserción masiva (página Conexión)</span><span class="sxs-lookup"><span data-stu-id="08106-102">Bulk Insert Task Editor (Connection Page)</span></span>
  <span data-ttu-id="08106-103">Use la página **Conexión** del cuadro de diálogo **Editor de la tarea Inserción masiva** para especificar el origen y el destino de la operación de inserción masiva y el formato que se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="08106-103">Use the **Connection** page of the **Bulk Insert Task Editor** dialog box to specify the source and destination of the bulk insert operation and the format to use.</span></span>  
  
 <span data-ttu-id="08106-104">Para más información sobre las inserciones masivas, vea [Tarea Inserción masiva](control-flow/bulk-insert-task.md) y [Archivos de formato para importar o exportar datos &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="08106-104">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="08106-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="08106-105">Options</span></span>  
 <span data-ttu-id="08106-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="08106-106">**Connection**</span></span>  
 <span data-ttu-id="08106-107">Seleccione un administrador de conexiones OLE DB de la lista o haga clic en \<**New connection...**> para crear una conexión nueva.</span><span class="sxs-lookup"><span data-stu-id="08106-107">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="08106-108">**Temas relacionados:** [Administrador de conexiones OLE DB](connection-manager/ole-db-connection-manager.md), [Configurar el administrador de conexiones OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="08106-108">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="08106-109">**Tabla de destino**</span><span class="sxs-lookup"><span data-stu-id="08106-109">**DestinationTable**</span></span>  
 <span data-ttu-id="08106-110">Escriba el nombre de la tabla o la vista de destino, o seleccione una tabla o una vista de la lista.</span><span class="sxs-lookup"><span data-stu-id="08106-110">Type the name of the destination table or view or select a table or view in the list.</span></span>  
  
 <span data-ttu-id="08106-111">**Formato**</span><span class="sxs-lookup"><span data-stu-id="08106-111">**Format**</span></span>  
 <span data-ttu-id="08106-112">Seleccione el origen del formato de la inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="08106-112">Select the source of the format for the bulk insert.</span></span> <span data-ttu-id="08106-113">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="08106-113">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="08106-114">Value</span><span class="sxs-lookup"><span data-stu-id="08106-114">Value</span></span>|<span data-ttu-id="08106-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="08106-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08106-116">**Utilizar archivo**</span><span class="sxs-lookup"><span data-stu-id="08106-116">**Use File**</span></span>|<span data-ttu-id="08106-117">Seleccione un archivo que contenga la especificación de formato.</span><span class="sxs-lookup"><span data-stu-id="08106-117">Select a file containing the format specification.</span></span> <span data-ttu-id="08106-118">Si se selecciona esta opción, se muestra la opción dinámica **FormatFile**.</span><span class="sxs-lookup"><span data-stu-id="08106-118">Selecting this option displays the dynamic option, **FormatFile**.</span></span>|  
|<span data-ttu-id="08106-119">**Especificar**</span><span class="sxs-lookup"><span data-stu-id="08106-119">**Specify**</span></span>|<span data-ttu-id="08106-120">Especifique el formato.</span><span class="sxs-lookup"><span data-stu-id="08106-120">Specify the format.</span></span> <span data-ttu-id="08106-121">Al seleccionar esta opción se muestran las opciones dinámicas, `RowDelimiter` y `ColumnDelimiter` .</span><span class="sxs-lookup"><span data-stu-id="08106-121">Selecting this option displays the dynamic options, `RowDelimiter` and `ColumnDelimiter`.</span></span>|  
  
 <span data-ttu-id="08106-122">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="08106-122">**File**</span></span>  
 <span data-ttu-id="08106-123">Seleccione un administrador de conexiones de archivo o de archivo plano de la lista o haga clic en \<**New connection...**> para crear una conexión nueva.</span><span class="sxs-lookup"><span data-stu-id="08106-123">Select a File or Flat File connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="08106-124">La ubicación del archivo es relativa al motor de base de datos de SQL Server especificado en el administrador de conexiones para esta tarea.</span><span class="sxs-lookup"><span data-stu-id="08106-124">The file location is relative to the SQL Server Database Engine specified in the connection manager for this task.</span></span> <span data-ttu-id="08106-125">Es preciso que el motor de base de datos de SQL Server tenga acceso al archivo de texto en un disco duro local en el servidor o mediante una unidad compartida o asignada a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="08106-125">The text file must be accessible by the SQL Server Database Engine either on a local hard drive on the server, or via a share or mapped drive to the SQL Server.</span></span> <span data-ttu-id="08106-126">El tiempo de ejecución de SSIS no tiene acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="08106-126">The file is not accessed by the SSIS Runtime.</span></span>  
  
 <span data-ttu-id="08106-127">Si obtiene acceso al archivo de origen utilizando el administrador de conexiones de archivos planos, la tarea Inserción masiva no utiliza el formato especificado en el administrador de conexiones de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="08106-127">If you access the source file by using a Flat File connection manager, the Bulk Insert task does not use the format specified in the Flat File connection manager.</span></span> <span data-ttu-id="08106-128">En su lugar, la tarea Inserción masiva usa el formato especificado en un archivo de formato o los valores de las propiedades RowDelimiter y ColumnDelimiter de la tarea.</span><span class="sxs-lookup"><span data-stu-id="08106-128">Instead, the Bulk Insert task uses either the format specified in a format file or the values of the RowDelimiter and ColumnDelimiter properties of the task.</span></span>  
  
 <span data-ttu-id="08106-129">**Temas relacionados:** [Administrador de conexiones de archivos](connection-manager/file-connection-manager.md), [Editor del administrador de conexiones de archivos](../../2014/integration-services/file-connection-manager-editor.md), [Administrador de conexiones de archivos planos](connection-manager/flat-file-connection-manager.md), [Editor del administrador de conexiones de archivos planos &#40;página General&#41;](general-page-of-integration-services-designers-options.md), [Editor del administrador de conexiones de archivos planos &#40;página Columnas&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Editor del administrador de conexiones de archivos planos &#40;página Avanzadas&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span><span class="sxs-lookup"><span data-stu-id="08106-129">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md), [Flat File Connection Manager](connection-manager/flat-file-connection-manager.md), [Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md), [Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span></span>  
  
 <span data-ttu-id="08106-130">**Actualizar tablas**</span><span class="sxs-lookup"><span data-stu-id="08106-130">**Refresh Tables**</span></span>  
 <span data-ttu-id="08106-131">Actualice la lista de tablas y vistas.</span><span class="sxs-lookup"><span data-stu-id="08106-131">Refresh the list of tables and views.</span></span>  
  
## <a name="format-dynamic-options"></a><span data-ttu-id="08106-132">Opciones dinámicas de formato</span><span class="sxs-lookup"><span data-stu-id="08106-132">Format Dynamic Options</span></span>  
  
### <a name="format--use-file"></a><span data-ttu-id="08106-133">Formato = Utilizar archivo</span><span class="sxs-lookup"><span data-stu-id="08106-133">Format = Use File</span></span>  
 <span data-ttu-id="08106-134">**FormatFile**</span><span class="sxs-lookup"><span data-stu-id="08106-134">**FormatFile**</span></span>  
 <span data-ttu-id="08106-135">Escriba la ruta de acceso del archivo de formato, o bien haga clic en el botón de puntos suspensivos ( **…** ) para buscar el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="08106-135">Type the path of the format file or click the ellipsis button **(...)** to locate the format file.</span></span>  
  
### <a name="format--specify"></a><span data-ttu-id="08106-136">Formato = Especificar</span><span class="sxs-lookup"><span data-stu-id="08106-136">Format = Specify</span></span>  
 `RowDelimiter`  
 <span data-ttu-id="08106-137">Especifique el delimitador de filas en el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="08106-137">Specify the row delimiter in the source file.</span></span> <span data-ttu-id="08106-138">El valor predeterminado es **{CR}{LF}** .</span><span class="sxs-lookup"><span data-stu-id="08106-138">The default value is **{CR}{LF}**.</span></span>  
  
 `ColumnDelimiter`  
 <span data-ttu-id="08106-139">Especifique el delimitador de columna en el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="08106-139">Specify the column delimiter in the source file.</span></span> <span data-ttu-id="08106-140">El valor predeterminado es **Tab**.</span><span class="sxs-lookup"><span data-stu-id="08106-140">The default is **Tab**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08106-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08106-141">See Also</span></span>  
 <span data-ttu-id="08106-142">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="08106-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="08106-143">[Editor de la tarea inserción masiva &#40;página general&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="08106-143">[Bulk Insert Task Editor &#40;General Page&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="08106-144">[Editor de la tarea inserción masiva &#40;página Opciones&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="08106-144">[Bulk Insert Task Editor &#40;Options Page&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span></span>  
 <span data-ttu-id="08106-145">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="08106-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="08106-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="08106-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="08106-147">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="08106-147">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
