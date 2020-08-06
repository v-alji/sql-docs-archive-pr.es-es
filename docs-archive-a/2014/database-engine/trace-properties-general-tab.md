---
title: Propiedades de seguimiento (pestaña general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.general.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: 25227268-143b-477e-aac9-8268bcaf2078
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 30de30c88db35a41f8f118b6545d56a78b2dec79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750114"
---
# <a name="trace-properties-general-tab"></a><span data-ttu-id="96172-102">Propiedades de seguimiento (pestaña General)</span><span class="sxs-lookup"><span data-stu-id="96172-102">Trace Properties (General Tab)</span></span>
  <span data-ttu-id="96172-103">Utilice la pestaña **General** del cuadro de diálogo **Propiedades de seguimiento** para ver o especificar las propiedades de un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96172-103">Use the **General** tab of the **Trace Properties** dialog box to view or specify properties of a trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="96172-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="96172-104">Options</span></span>  
 <span data-ttu-id="96172-105">**Nombre de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="96172-105">**Trace name**</span></span>  
 <span data-ttu-id="96172-106">Especifica el nombre del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96172-106">Specify the name of the trace.</span></span>  
  
 <span data-ttu-id="96172-107">**Nombre del proveedor de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="96172-107">**Trace provider name**</span></span>  
 <span data-ttu-id="96172-108">Muestra el nombre de la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] de la que va a realizarse un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96172-108">Shows the name of the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that will be traced.</span></span> <span data-ttu-id="96172-109">Este campo se rellena automáticamente con el nombre del servidor que haya especificado al conectarse.</span><span class="sxs-lookup"><span data-stu-id="96172-109">This field is populated automatically with the name of the server that you specified when you connected.</span></span> <span data-ttu-id="96172-110">Para cambiar el nombre del proveedor de seguimiento, haga clic en **Cancelar** para cerrar el cuadro de diálogo e iniciar un nuevo seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96172-110">To change the name of the trace provider, click **Cancel** to close the dialog box, and start a new trace.</span></span>  
  
 <span data-ttu-id="96172-111">**Tipo de proveedor de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="96172-111">**Trace provider type**</span></span>  
 <span data-ttu-id="96172-112">Muestra el tipo de proveedor que proporciona el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96172-112">Shows the server type that is providing the trace.</span></span> <span data-ttu-id="96172-113">El archivo de definición de seguimiento rellena el campo **Tipo de proveedor de seguimiento** automáticamente.</span><span class="sxs-lookup"><span data-stu-id="96172-113">The trace definition file populates the **Trace provider type** field automatically.</span></span> <span data-ttu-id="96172-114">No se puede modificar este campo.</span><span class="sxs-lookup"><span data-stu-id="96172-114">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="96172-115">**version**</span><span class="sxs-lookup"><span data-stu-id="96172-115">**version**</span></span>  
 <span data-ttu-id="96172-116">Muestra la versión del servidor que proporciona el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96172-116">Shows the version of the server that is providing the trace.</span></span> <span data-ttu-id="96172-117">El archivo de definición de seguimiento rellena el campo **Versión** automáticamente.</span><span class="sxs-lookup"><span data-stu-id="96172-117">The trace definition file populates the **Version** field automatically.</span></span> <span data-ttu-id="96172-118">No se puede modificar este campo.</span><span class="sxs-lookup"><span data-stu-id="96172-118">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="96172-119">**Uso de la plantilla**</span><span class="sxs-lookup"><span data-stu-id="96172-119">**Use the template**</span></span>  
 <span data-ttu-id="96172-120">Selecciona una plantilla del directorio de plantillas.</span><span class="sxs-lookup"><span data-stu-id="96172-120">Select a template from the template directory.</span></span> <span data-ttu-id="96172-121">El directorio se rellena con las plantillas predeterminadas y con cualquier tipo de plantilla definida por el usuario que se haya creado para el tipo de proveedor de seguimiento actual.</span><span class="sxs-lookup"><span data-stu-id="96172-121">The directory is populated with the default templates and any user-defined templates created for the current trace provider type.</span></span>  
  
 <span data-ttu-id="96172-122">**Guardar en el archivo**</span><span class="sxs-lookup"><span data-stu-id="96172-122">**Save to file**</span></span>  
 <span data-ttu-id="96172-123">Captura los datos del seguimiento en un archivo .trc.</span><span class="sxs-lookup"><span data-stu-id="96172-123">Capture the trace data to a .trc file.</span></span> <span data-ttu-id="96172-124">Guardar los datos del seguimiento es útil para su posterior revisión y análisis.</span><span class="sxs-lookup"><span data-stu-id="96172-124">Saving trace data is useful for later review and analysis.</span></span>  
  
 <span data-ttu-id="96172-125">**Establecer el tamaño máximo de archivo (MB)**</span><span class="sxs-lookup"><span data-stu-id="96172-125">**Set maximum file size (MB)**</span></span>  
 <span data-ttu-id="96172-126">Si elige la opción de guardar los datos de seguimiento en un archivo, deberá especificar el tamaño máximo del mismo.</span><span class="sxs-lookup"><span data-stu-id="96172-126">If you choose to save the trace data to a file, you must specify the maximum size of the trace file.</span></span> <span data-ttu-id="96172-127">El valor predeterminado es 5 megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="96172-127">The default is 5 megabytes (MB).</span></span> <span data-ttu-id="96172-128">El tamaño máximo está limitado únicamente por el sistema de archivos (NTFS, FAT) donde se guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="96172-128">The maximum size is limited only by the file system (NTFS, FAT) where the file is saved.</span></span>  
  
 <span data-ttu-id="96172-129">\<Graphic>**Guardar como**</span><span class="sxs-lookup"><span data-stu-id="96172-129">\<Graphic> **Save As**</span></span>  
 <span data-ttu-id="96172-130">Después de seleccionar guardar, puede seleccionar este icono para cambiar el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="96172-130">After you have selected to save, you can select this icon to change the file name.</span></span>  
  
 <span data-ttu-id="96172-131">**Habilitar sustitución incremental de archivos**</span><span class="sxs-lookup"><span data-stu-id="96172-131">**Enable file rollover**</span></span>  
 <span data-ttu-id="96172-132">Seleccione esta opción para habilitar la creación de archivos adicionales, para que se acepten los datos del seguimiento cuando se alcance el tamaño máximo de archivo.</span><span class="sxs-lookup"><span data-stu-id="96172-132">Select to enable the creation of additional files to accept the trace data when the maximum file size is reached.</span></span> <span data-ttu-id="96172-133">Los nuevos nombres de archivo consisten en el nombre de archivo .trc original, numerado de forma secuencial.</span><span class="sxs-lookup"><span data-stu-id="96172-133">Each new file name consists of the original .trc file name, numbered sequentially.</span></span> <span data-ttu-id="96172-134">Por ejemplo, una vez que **NewTrace.trc** alcanza el tamaño máximo de archivo, se cierra, y se abre un nuevo archivo, **NewTrace_1.trc**, seguido de **NewTrace_2.trc**y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="96172-134">For example, once it reaches maximum file size, **NewTrace.trc** closes, and a new file, **NewTrace_1.trc**, opens, followed by **NewTrace_2.trc**, and so on.</span></span> <span data-ttu-id="96172-135">La sustitución incremental de archivos está habilitada de forma predeterminada cuando se guarda un seguimiento en un archivo.</span><span class="sxs-lookup"><span data-stu-id="96172-135">File rollover is enabled by default when you save a trace to a file.</span></span>  
  
 <span data-ttu-id="96172-136">**El servidor procesa los datos de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="96172-136">**Server processes trace data**</span></span>  
 <span data-ttu-id="96172-137">Especifica que el servidor que ejecuta el seguimiento debe procesar los datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96172-137">Specify that the server running the trace should process the trace data.</span></span> <span data-ttu-id="96172-138">El uso de esta opción reduce la sobrecarga de rendimiento en la que se incurre con el trazado.</span><span class="sxs-lookup"><span data-stu-id="96172-138">Using this option reduces the performance overhead incurred by tracing.</span></span> <span data-ttu-id="96172-139">Si se selecciona esta opción, no se omite ningún evento, incluso en condiciones de gran demanda.</span><span class="sxs-lookup"><span data-stu-id="96172-139">If selected, no events are skipped even under stress conditions.</span></span> <span data-ttu-id="96172-140">Si esta casilla está desactivada, el Analizar de SQL Server se encarga del procesamiento y existe la posibilidad de que no se realice un seguimiento de algunos eventos de gran demanda.</span><span class="sxs-lookup"><span data-stu-id="96172-140">If this check box is cleared, processing is performed by SQL Server Profiler, and there is a possibility that some events are not traced under stress conditions.</span></span>  
  
 <span data-ttu-id="96172-141">**Guardar en la tabla**</span><span class="sxs-lookup"><span data-stu-id="96172-141">**Save to table**</span></span>  
 <span data-ttu-id="96172-142">Captura los datos del seguimiento en una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="96172-142">Capture the trace data to a database table.</span></span> <span data-ttu-id="96172-143">Guardar los datos del seguimiento es útil para su posterior revisión y análisis.</span><span class="sxs-lookup"><span data-stu-id="96172-143">Saving trace data is useful for later review and analysis.</span></span> <span data-ttu-id="96172-144">Sin embargo, guardar los datos de un seguimiento en una tabla también puede aumentar de forma significativa la sobrecarga en el servidor en el que se guarda el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96172-144">However, saving trace data to a table can incur significant overhead on the server where the trace is being saved.</span></span> <span data-ttu-id="96172-145">Si es posible, no guarde la tabla de seguimiento en el mismo servidor del que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96172-145">If possible, do not save the trace table on the same server that is being traced.</span></span>  
  
 <span data-ttu-id="96172-146">\<Graphic>**Tabla de destino**</span><span class="sxs-lookup"><span data-stu-id="96172-146">\<Graphic> **Destination Table**</span></span>  
 <span data-ttu-id="96172-147">Después de seleccionar que los datos de seguimiento se guarden en una tabla de base de datos, puede seleccionar este icono para cambiar el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="96172-147">After you have selected to save the trace data to a database table, you can select this icon to change the table name.</span></span>  
  
 <span data-ttu-id="96172-148">**Establecer número máximo de filas (en miles)**</span><span class="sxs-lookup"><span data-stu-id="96172-148">**Set maximum rows (in thousands)**</span></span>  
 <span data-ttu-id="96172-149">Especifica el número máximo de filas en las que guardar los datos.</span><span class="sxs-lookup"><span data-stu-id="96172-149">Specify the largest number of rows in which to save data.</span></span> <span data-ttu-id="96172-150">El valor predeterminado es 1000 filas.</span><span class="sxs-lookup"><span data-stu-id="96172-150">The default is 1000 rows.</span></span>  
  
 <span data-ttu-id="96172-151">**Habilitar hora de detención de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="96172-151">**Enable trace stop time**</span></span>  
 <span data-ttu-id="96172-152">Establece la fecha y la hora de finalización y de cierre del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96172-152">Set the date and time for the trace to end and close itself.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96172-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96172-153">See Also</span></span>  
 [<span data-ttu-id="96172-154">Crear un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="96172-154">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
