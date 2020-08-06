---
title: Ayuda F1 del Visor de archivos de registro | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.errorlog.f1
helpviewer_keywords:
- Log File Viewer
ms.assetid: 2243845c-4880-4aa0-9ee8-0a97a128996b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6eadb4baa4a47202b40a9cde1eca896022f31d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671535"
---
# <a name="log-file-viewer-f1-help"></a><span data-ttu-id="62057-102">Ayuda F1 del Visor de archivos de registro</span><span class="sxs-lookup"><span data-stu-id="62057-102">Log File Viewer F1 Help</span></span>
  <span data-ttu-id="62057-103">El Visor de archivos de registro muestra información de registro de muchos componentes diferentes.</span><span class="sxs-lookup"><span data-stu-id="62057-103">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="62057-104">Cuando el Visor del archivo de registros esté abierto, utilice el panel **Seleccionar registros** para seleccionar los registros que desea que se muestren.</span><span class="sxs-lookup"><span data-stu-id="62057-104">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="62057-105">Cada registro muestra las columnas apropiadas a ese tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="62057-105">Each log displays columns appropriate to that kind of log.</span></span>  
  
 <span data-ttu-id="62057-106">La disponibilidad de los registros dependerá del modo en que se abra el Visor del archivo de registros.</span><span class="sxs-lookup"><span data-stu-id="62057-106">The logs that are available depend on how Log File Viewer is opened.</span></span> <span data-ttu-id="62057-107">Para obtener más información, vea [Abrir el Visor de archivos de registro](open-log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="62057-107">For more information, see [Open Log File Viewer](open-log-file-viewer.md).</span></span>  
  
 <span data-ttu-id="62057-108">El número de filas que se muestran para los registros de auditoría se puede configurar en la página **Explorador de objetos de SQL Server/Comandos** del cuadro de diálogo **Herramientas/Opciones** .</span><span class="sxs-lookup"><span data-stu-id="62057-108">The number of rows that are displayed for audit logs can be configured on the **SQL Server Object Explorer/Commands** page of the **Tools/Options** dialog box.</span></span> <span data-ttu-id="62057-109">Para obtener la descripción de las columnas que se muestran para los registros de auditoría, vea [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62057-109">For descriptions of the columns that are displayed for audit logs, see [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="62057-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="62057-110">Options</span></span>  
 <span data-ttu-id="62057-111">**Cargar registro**</span><span class="sxs-lookup"><span data-stu-id="62057-111">**Load Log**</span></span>  
 <span data-ttu-id="62057-112">Abre un cuadro de diálogo donde puede especificar un archivo de registro para cargar.</span><span class="sxs-lookup"><span data-stu-id="62057-112">Open a dialog box where you can specify a log file to load.</span></span>  
  
 <span data-ttu-id="62057-113">**Exportarar**</span><span class="sxs-lookup"><span data-stu-id="62057-113">**Export**</span></span>  
 <span data-ttu-id="62057-114">Abre un cuadro de diálogo que permite exportar la información que se muestra en la cuadrícula **Resumen de archivos de registro** a un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="62057-114">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
 <span data-ttu-id="62057-115">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="62057-115">**Refresh**</span></span>  
 <span data-ttu-id="62057-116">Actualice la vista de los registros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="62057-116">Refresh the view of the selected logs.</span></span> <span data-ttu-id="62057-117">El botón **Actualizar** hace que se vuelvan a leer los registros seleccionados del servidor de destino al tiempo que se aplica una configuración de filtro.</span><span class="sxs-lookup"><span data-stu-id="62057-117">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
 <span data-ttu-id="62057-118">**Filter**</span><span class="sxs-lookup"><span data-stu-id="62057-118">**Filter**</span></span>  
 <span data-ttu-id="62057-119">Abre un cuadro de diálogo que permite especificar la configuración que se usa para filtrar el archivo de registro, como **Conexión**, **Fecha**u otros criterios de filtro de **General** .</span><span class="sxs-lookup"><span data-stu-id="62057-119">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
 <span data-ttu-id="62057-120">**Búsqueda**</span><span class="sxs-lookup"><span data-stu-id="62057-120">**Search**</span></span>  
 <span data-ttu-id="62057-121">Permite buscar texto específico en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="62057-121">Search the log file for specific text.</span></span> <span data-ttu-id="62057-122">No se admite la búsqueda con caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="62057-122">Searching with wildcard characters is not supported.</span></span>  
  
 <span data-ttu-id="62057-123">**Detención**</span><span class="sxs-lookup"><span data-stu-id="62057-123">**Stop**</span></span>  
 <span data-ttu-id="62057-124">Detiene la carga de las entradas del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="62057-124">Stops loading the log file entries.</span></span> <span data-ttu-id="62057-125">Por ejemplo, puede utilizar esta opción si la carga de un archivo de registro remoto o sin conexión tarda mucho tiempo y solo desea ver las entradas más recientes.</span><span class="sxs-lookup"><span data-stu-id="62057-125">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
 <span data-ttu-id="62057-126">**Resumen de archivos de registro**</span><span class="sxs-lookup"><span data-stu-id="62057-126">**Log file summary**</span></span>  
 <span data-ttu-id="62057-127">Este panel de información muestra un resumen del filtro del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="62057-127">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="62057-128">Si no se ha filtrado el archivo, se mostrará el siguiente texto: **No se aplicó ningún filtro**.</span><span class="sxs-lookup"><span data-stu-id="62057-128">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="62057-129">Si se aplicó un filtro al registro, se mostrará el texto **Filtrar entradas del registro en:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="62057-129">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
 <span data-ttu-id="62057-130">**Detalles de las filas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="62057-130">**Selected row details**</span></span>  
 <span data-ttu-id="62057-131">Seleccione una fila para mostrar detalles adicionales sobre la fila de evento seleccionada en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="62057-131">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="62057-132">Puede ordenar de nuevo las columnas arrastrándolas a nuevas ubicaciones de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="62057-132">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="62057-133">Puede modificar el tamaño de las columnas arrastrando las barras de separación de las columnas del encabezado de la cuadrícula hacia la izquierda o hacia la derecha.</span><span class="sxs-lookup"><span data-stu-id="62057-133">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="62057-134">Haga doble clic en las barras de separación de las columnas del encabezado de la cuadrícula para ajustar automáticamente el tamaño de la columna al ancho del contenido.</span><span class="sxs-lookup"><span data-stu-id="62057-134">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
 <span data-ttu-id="62057-135">**Instancia**</span><span class="sxs-lookup"><span data-stu-id="62057-135">**Instance**</span></span>  
 <span data-ttu-id="62057-136">Nombre de la instancia en que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="62057-136">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="62057-137">Esto se muestra como *nombre de equipo*\\*nombre de instancia*.</span><span class="sxs-lookup"><span data-stu-id="62057-137">This is displayed as *computer name*\\*instance name*.</span></span>  
  
## <a name="frequently-displayed-columns"></a><span data-ttu-id="62057-138">Columnas que se muestran con frecuencia</span><span class="sxs-lookup"><span data-stu-id="62057-138">Frequently Displayed Columns</span></span>  
 <span data-ttu-id="62057-139">**Date**</span><span class="sxs-lookup"><span data-stu-id="62057-139">**Date**</span></span>  
 <span data-ttu-id="62057-140">Muestra la fecha del evento.</span><span class="sxs-lookup"><span data-stu-id="62057-140">Displays the date of the event.</span></span>  
  
 <span data-ttu-id="62057-141">**Origen**</span><span class="sxs-lookup"><span data-stu-id="62057-141">**Source**</span></span>  
 <span data-ttu-id="62057-142">Muestra la característica de origen desde la que se crea el evento, como el nombre del servicio (MSSQLSERVER, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="62057-142">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="62057-143">No aparece para todos los tipos de registro.</span><span class="sxs-lookup"><span data-stu-id="62057-143">This does not appear for all log types.</span></span>  
  
 <span data-ttu-id="62057-144">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="62057-144">**Message**</span></span>  
 <span data-ttu-id="62057-145">Muestra todos los mensajes asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="62057-145">Displays any messages associated with the event.</span></span>  
  
 <span data-ttu-id="62057-146">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="62057-146">**Log Type**</span></span>  
 <span data-ttu-id="62057-147">Muestra el tipo de registro al que pertenece el evento.</span><span class="sxs-lookup"><span data-stu-id="62057-147">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="62057-148">Todos los registros seleccionados aparecen en la ventana de resumen del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="62057-148">All selected logs appear in the log file summary window.</span></span>  
  
 <span data-ttu-id="62057-149">**Origen del registro**</span><span class="sxs-lookup"><span data-stu-id="62057-149">**Log Source**</span></span>  
 <span data-ttu-id="62057-150">Muestra una descripción del registro de origen en el que se captura el evento.</span><span class="sxs-lookup"><span data-stu-id="62057-150">Displays a description of the source log in which the event is captured.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="62057-151">Permisos</span><span class="sxs-lookup"><span data-stu-id="62057-151">Permissions</span></span>  
 <span data-ttu-id="62057-152">Para tener acceso a los archivos de registro en instancias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en línea, se requiere pertenecer al rol fijo de servidor securityadmin.</span><span class="sxs-lookup"><span data-stu-id="62057-152">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="62057-153">Para tener acceso a los archivos de registro en instancias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sin conexión, se debe tener acceso de lectura tanto al espacio de nombres WMI **Root\Microsoft\SqlServer\ComputerManagement10** como a la carpeta donde están almacenados los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="62057-153">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="62057-154">Para obtener más información, vea la sección Seguridad del tema [Ver archivos del registro sin conexión](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="62057-154">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62057-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62057-155">See Also</span></span>  
 <span data-ttu-id="62057-156">[Visor de archivos de registro](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="62057-156">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="62057-157">[Abrir el Visor de archivos de registro](open-log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="62057-157">[Open Log File Viewer](open-log-file-viewer.md) </span></span>  
 [<span data-ttu-id="62057-158">Ver archivos del registro sin conexión</span><span class="sxs-lookup"><span data-stu-id="62057-158">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
