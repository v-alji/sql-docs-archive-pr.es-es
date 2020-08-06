---
title: Ver el registro de errores del Agente SQL Server (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- viewing SQL Server Agent error logs
- displaying SQL Server Agent error logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: de920425-fa44-469f-b83d-49e3f97e97f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: b88214a158a970a754c5f313bde3d53f2652ae73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747408"
---
# <a name="view-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="f804e-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f804e-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f804e-103">En este tema se describe el modo de ver el registro de errores del Agente  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f804e-103">This topic describes how to view the  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f804e-104">El Visor de archivos de registro muestra información de registro de muchos componentes diferentes.</span><span class="sxs-lookup"><span data-stu-id="f804e-104">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="f804e-105">Cuando el Visor del archivo de registros esté abierto, utilice el panel **Seleccionar registros** para seleccionar los registros que desea que se muestren.</span><span class="sxs-lookup"><span data-stu-id="f804e-105">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="f804e-106">Cada registro muestra las columnas apropiadas a ese tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="f804e-106">Each log displays columns appropriate to that kind of log.</span></span> <span data-ttu-id="f804e-107">La disponibilidad de los registros dependerá del modo en que se abra el Visor del archivo de registros.</span><span class="sxs-lookup"><span data-stu-id="f804e-107">The logs that are available depend on how Log File Viewer is opened.</span></span>  
  
 <span data-ttu-id="f804e-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f804e-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f804e-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f804e-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f804e-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f804e-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f804e-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f804e-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="f804e-112">Para ver el registro de errores del Agente SQL Server utilizando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f804e-112">To view the SQL Server Agent error log, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f804e-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f804e-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f804e-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f804e-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f804e-115">El Explorador de objetos solo muestra el nodo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se tiene permiso para usarlo.</span><span class="sxs-lookup"><span data-stu-id="f804e-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f804e-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f804e-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f804e-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="f804e-117">Permissions</span></span>  
 <span data-ttu-id="f804e-118">Para realizar sus funciones, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe configurarse de modo que use las credenciales de una cuenta que sea miembro del rol fijo de servidor **sysadmin** en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f804e-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f804e-119">La cuenta debe tener los siguientes permisos de Windows:</span><span class="sxs-lookup"><span data-stu-id="f804e-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="f804e-120">Iniciar sesión como servicio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="f804e-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="f804e-121">Reemplazar un token de nivel de proceso (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="f804e-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="f804e-122">Omitir la comprobación transversal (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="f804e-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="f804e-123">Ajustar las cuotas de memoria de un proceso (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="f804e-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="f804e-124">Para obtener más información acerca de los permisos de Windows necesarios para la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuenta de servicio del agente, consulte [seleccionar una cuenta para el servicio de Agente SQL Server](select-an-account-for-the-sql-server-agent-service.md) y [configurar los permisos y las cuentas de servicio de Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f804e-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f804e-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f804e-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-ssnoversion-agent-error-log"></a><span data-ttu-id="f804e-126">Para ver el registro de errores del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f804e-126">To view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log</span></span>  
  
1.  <span data-ttu-id="f804e-127">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene el registro de errores del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuyo nombre desea ver.</span><span class="sxs-lookup"><span data-stu-id="f804e-127">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to view.</span></span>  
  
2.  <span data-ttu-id="f804e-128">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f804e-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="f804e-129">Haga clic en el signo más para expandir la carpeta **Registros de errores** .</span><span class="sxs-lookup"><span data-stu-id="f804e-129">Click the plus sign to expand the **Error Logs** folder.</span></span>  
  
4.  <span data-ttu-id="f804e-130">Haga clic con el botón derecho en el registro de errores que desea ver y seleccione **Ver registro del agente**.</span><span class="sxs-lookup"><span data-stu-id="f804e-130">Right-click the error log you want to view and select **View Agent Log**.</span></span>  
  
     <span data-ttu-id="f804e-131">Las siguientes opciones están disponibles en el cuadro de diálogo **visor del archivo de registros-**_SERVER_NAME_ :</span><span class="sxs-lookup"><span data-stu-id="f804e-131">The following options are available in the **Log File Viewer -**_server_name_ dialog box:</span></span>  
  
     <span data-ttu-id="f804e-132">**Cargar registro**</span><span class="sxs-lookup"><span data-stu-id="f804e-132">**Load Log**</span></span>  
     <span data-ttu-id="f804e-133">Abre un cuadro de diálogo donde puede especificar un archivo de registro para cargar.</span><span class="sxs-lookup"><span data-stu-id="f804e-133">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="f804e-134">**Exportarar**</span><span class="sxs-lookup"><span data-stu-id="f804e-134">**Export**</span></span>  
     <span data-ttu-id="f804e-135">Abre un cuadro de diálogo que permite exportar la información que se muestra en la cuadrícula **Resumen de archivos de registro** a un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f804e-135">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="f804e-136">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="f804e-136">**Refresh**</span></span>  
     <span data-ttu-id="f804e-137">Actualice la vista de los registros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f804e-137">Refresh the view of the selected logs.</span></span> <span data-ttu-id="f804e-138">El botón **Actualizar** hace que se vuelvan a leer los registros seleccionados del servidor de destino al tiempo que se aplica una configuración de filtro.</span><span class="sxs-lookup"><span data-stu-id="f804e-138">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="f804e-139">**Filter**</span><span class="sxs-lookup"><span data-stu-id="f804e-139">**Filter**</span></span>  
     <span data-ttu-id="f804e-140">Abre un cuadro de diálogo que permite especificar la configuración que se usa para filtrar el archivo de registro, como **Conexión**, **Fecha**u otros criterios de filtro de **General** .</span><span class="sxs-lookup"><span data-stu-id="f804e-140">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="f804e-141">**Búsqueda**</span><span class="sxs-lookup"><span data-stu-id="f804e-141">**Search**</span></span>  
     <span data-ttu-id="f804e-142">Permite buscar texto específico en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="f804e-142">Search the log file for specific text.</span></span> <span data-ttu-id="f804e-143">No se admite la búsqueda con caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="f804e-143">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="f804e-144">**Detención**</span><span class="sxs-lookup"><span data-stu-id="f804e-144">**Stop**</span></span>  
     <span data-ttu-id="f804e-145">Detiene la carga de las entradas del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="f804e-145">Stops loading the log file entries.</span></span> <span data-ttu-id="f804e-146">Por ejemplo, puede utilizar esta opción si la carga de un archivo de registro remoto o sin conexión tarda mucho tiempo y solo desea ver las entradas más recientes.</span><span class="sxs-lookup"><span data-stu-id="f804e-146">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="f804e-147">**Resumen de archivos de registro**</span><span class="sxs-lookup"><span data-stu-id="f804e-147">**Log file summary**</span></span>  
     <span data-ttu-id="f804e-148">Este panel de información muestra un resumen del filtro del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="f804e-148">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="f804e-149">Si no se ha filtrado el archivo, se mostrará el siguiente texto: **No se aplicó ningún filtro**.</span><span class="sxs-lookup"><span data-stu-id="f804e-149">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="f804e-150">Si se aplicó un filtro al registro, se mostrará el texto **Filtrar entradas del registro en:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="f804e-150">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="f804e-151">**Detalles de las filas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="f804e-151">**Selected row details**</span></span>  
     <span data-ttu-id="f804e-152">Seleccione una fila para mostrar detalles adicionales sobre la fila de evento seleccionada en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="f804e-152">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="f804e-153">Puede ordenar de nuevo las columnas arrastrándolas a nuevas ubicaciones de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f804e-153">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="f804e-154">Puede modificar el tamaño de las columnas arrastrando las barras de separación de las columnas del encabezado de la cuadrícula hacia la izquierda o hacia la derecha.</span><span class="sxs-lookup"><span data-stu-id="f804e-154">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="f804e-155">Haga doble clic en las barras de separación de las columnas del encabezado de la cuadrícula para ajustar automáticamente el tamaño de la columna al ancho del contenido.</span><span class="sxs-lookup"><span data-stu-id="f804e-155">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="f804e-156">**Instancia**</span><span class="sxs-lookup"><span data-stu-id="f804e-156">**Instance**</span></span>  
     <span data-ttu-id="f804e-157">Nombre de la instancia en que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="f804e-157">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="f804e-158">Esto se muestra como *nombre de equipo*\\*nombre de instancia*.</span><span class="sxs-lookup"><span data-stu-id="f804e-158">This is displayed as *computer name*\\*instance name*.</span></span>  
  
     <span data-ttu-id="f804e-159">**Date**</span><span class="sxs-lookup"><span data-stu-id="f804e-159">**Date**</span></span>  
     <span data-ttu-id="f804e-160">Muestra la fecha del evento.</span><span class="sxs-lookup"><span data-stu-id="f804e-160">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="f804e-161">**Origen**</span><span class="sxs-lookup"><span data-stu-id="f804e-161">**Source**</span></span>  
     <span data-ttu-id="f804e-162">Muestra la característica de origen desde la que se crea el evento, como el nombre del servicio (MSSQLSERVER, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="f804e-162">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="f804e-163">No aparece para todos los tipos de registro.</span><span class="sxs-lookup"><span data-stu-id="f804e-163">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="f804e-164">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="f804e-164">**Message**</span></span>  
     <span data-ttu-id="f804e-165">Muestra todos los mensajes asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="f804e-165">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="f804e-166">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="f804e-166">**Log Type**</span></span>  
     <span data-ttu-id="f804e-167">Muestra el tipo de registro al que pertenece el evento.</span><span class="sxs-lookup"><span data-stu-id="f804e-167">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="f804e-168">Todos los registros seleccionados aparecen en la ventana de resumen del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="f804e-168">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="f804e-169">**Origen del registro**</span><span class="sxs-lookup"><span data-stu-id="f804e-169">**Log Source**</span></span>  
     <span data-ttu-id="f804e-170">Muestra una descripción del registro de origen en el que se captura el evento.</span><span class="sxs-lookup"><span data-stu-id="f804e-170">Displays a description of the source log in which the event is captured.</span></span>  
  
5.  <span data-ttu-id="f804e-171">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f804e-171">When finished, click **Close**.</span></span>  
  
  
