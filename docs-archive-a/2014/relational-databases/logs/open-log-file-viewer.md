---
title: Apertura del visor de archivos de registro | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, opening
ms.assetid: a86b89cb-0432-4648-895a-05ecc5450e45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269ff10275f7463a8a85249a2a0f06fe9bde364a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671528"
---
# <a name="open-log-file-viewer"></a><span data-ttu-id="118a3-102">Abrir el Visor de archivos de registro</span><span class="sxs-lookup"><span data-stu-id="118a3-102">Open Log File Viewer</span></span>
  <span data-ttu-id="118a3-103">Puede usar el Visor del archivo de registros de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para obtener acceso a la información sobre los errores y eventos capturados en los registros siguientes:</span><span class="sxs-lookup"><span data-stu-id="118a3-103">You can use Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to access information about errors and events that are captured in the following logs:</span></span>  
  
-   <span data-ttu-id="118a3-104">Recopilación de auditoría</span><span class="sxs-lookup"><span data-stu-id="118a3-104">Audit Collection</span></span>  
  
-   <span data-ttu-id="118a3-105">Recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="118a3-105">Data Collection</span></span>  
  
-   <span data-ttu-id="118a3-106">Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="118a3-106">Database Mail</span></span>  
  
-   <span data-ttu-id="118a3-107">Historial de trabajos</span><span class="sxs-lookup"><span data-stu-id="118a3-107">Job History</span></span>  
  
-   <span data-ttu-id="118a3-108">SQL Server</span><span class="sxs-lookup"><span data-stu-id="118a3-108">SQL Server</span></span>  
  
-   <span data-ttu-id="118a3-109">Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="118a3-109">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="118a3-110">Eventos de Windows (también se puede obtener acceso a los eventos de Windows desde el Visor de eventos).</span><span class="sxs-lookup"><span data-stu-id="118a3-110">Windows events (These Windows events can also be accessed from Event Viewer.)</span></span>  
  
 <span data-ttu-id="118a3-111">A partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], puede utilizar Servidores registrados para ver los archivos de registro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de instancias locales o remotas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="118a3-111">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can use Registered Servers to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from local or remote instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="118a3-112">Mediante Servidores registrados, puede ver los archivos de registro con o sin las instancias en línea.</span><span class="sxs-lookup"><span data-stu-id="118a3-112">By using Registered Servers, you can view the log files when the instances are either online or offline.</span></span> <span data-ttu-id="118a3-113">Para obtener más información acerca del acceso en línea, vea el procedimiento “Ver archivos de registro en línea desde servidores registrados” más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="118a3-113">For more information about online access, see the procedure "To view online log files from Registered Servers" later in this topic.</span></span> <span data-ttu-id="118a3-114">Para obtener más información sobre el acceso sin conexión a los archivos de registros de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea [Ver archivos del registro sin conexión](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="118a3-114">For more information about how to access offline [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files, see [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
 <span data-ttu-id="118a3-115">El Visor del archivo de registros se puede abrir de varias maneras, dependiendo de la información que se desee ver.</span><span class="sxs-lookup"><span data-stu-id="118a3-115">You can open Log File Viewer in several ways, depending on the information that you want to view.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="118a3-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="118a3-116">Permissions</span></span>  
 <span data-ttu-id="118a3-117">Para tener acceso a los archivos de registro en instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en línea, se requiere pertenecer al rol fijo de servidor securityadmin.</span><span class="sxs-lookup"><span data-stu-id="118a3-117">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="118a3-118">Para tener acceso a los archivos de registro en instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sin conexión, se debe tener acceso de lectura tanto al espacio de nombres WMI **Root\Microsoft\SqlServer\ComputerManagement10** como a la carpeta donde están almacenados los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="118a3-118">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="118a3-119">Para obtener más información, vea la sección Seguridad del tema [Ver archivos del registro sin conexión](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="118a3-119">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
### <a name="security"></a><span data-ttu-id="118a3-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="118a3-120">Security</span></span>  
 <span data-ttu-id="118a3-121">Debe pertenecer al rol fijo de servidor securityadmin.</span><span class="sxs-lookup"><span data-stu-id="118a3-121">Requires membership in the securityadmin fixed server role.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="118a3-122">Ver archivos de registro</span><span class="sxs-lookup"><span data-stu-id="118a3-122">View Log Files</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-general-sql-server-activity"></a><span data-ttu-id="118a3-123">Para ver los registros relacionados con la actividad general de SQL Server</span><span class="sxs-lookup"><span data-stu-id="118a3-123">To view logs that are related to general SQL Server activity</span></span>  
  
1.  <span data-ttu-id="118a3-124">En el Explorador de objetos, expanda **Administración**.</span><span class="sxs-lookup"><span data-stu-id="118a3-124">In Object Explorer, expand **Management**.</span></span>  
  
2.  <span data-ttu-id="118a3-125">Realice cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="118a3-125">Do either of the following:</span></span>  
  
    -   <span data-ttu-id="118a3-126">Haga clic con el botón derecho en **Registros de SQL Server**, seleccione **Ver**y, después, haga clic en **Registro de SQL Server** o **Registro de Windows y SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="118a3-126">Right-click **SQL Server Logs**, point to **View**, and then click either **SQL Server Log** or **SQL Server and Windows Log**.</span></span>  
  
    -   <span data-ttu-id="118a3-127">Expanda **Registros de SQL Server**, haga clic con el botón derecho en cualquier archivo de registro y, después, haga clic en **Ver registro de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="118a3-127">Expand **SQL Server Logs**, right-click any log file, and then click **View SQL Server Log**.</span></span> <span data-ttu-id="118a3-128">También puede hacer doble clic en cualquier archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="118a3-128">You can also double-click any log file.</span></span>  
  
     <span data-ttu-id="118a3-129">Los registros son **Correo electrónico de base de datos**, **SQL Server**, **Agente SQL Server**y **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="118a3-129">The logs include **Database Mail**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-jobs"></a><span data-ttu-id="118a3-130">Para ver los registros relacionados con los trabajos</span><span class="sxs-lookup"><span data-stu-id="118a3-130">To view logs that are related to jobs</span></span>  
  
-   <span data-ttu-id="118a3-131">En el Explorador de objetos, expanda **Agente SQL Server**, haga clic con el botón derecho en **Trabajos**y, después, haga clic en **Ver historial**.</span><span class="sxs-lookup"><span data-stu-id="118a3-131">In Object Explorer, expand **SQL Server Agent**, right-click **Jobs**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="118a3-132">Los registros son **Correo electrónico de base de datos**, **Historial de trabajos**y **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="118a3-132">The logs include **Database Mail**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-maintenance-plans"></a><span data-ttu-id="118a3-133">Para ver los registros relacionados con los planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="118a3-133">To view logs that are related to maintenance plans</span></span>  
  
-   <span data-ttu-id="118a3-134">En el Explorador de objetos, expanda **Administración**, haga clic con el botón derecho en **Planes de mantenimiento**y, después, haga clic en **Ver historial**.</span><span class="sxs-lookup"><span data-stu-id="118a3-134">In Object Explorer, expand **Management**, right-click **Maintenance Plans**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="118a3-135">Los registros son **Correo electrónico de base de datos**, **Historial de trabajos**, **Planes de mantenimiento**, **Planes de mantenimiento remotos**y **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="118a3-135">The logs include **Database Mail**, **Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-data-collection"></a><span data-ttu-id="118a3-136">Para ver los registros relacionados con la recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="118a3-136">To view logs that are related to Data Collection</span></span>  
  
-   <span data-ttu-id="118a3-137">En el Explorador de objetos, expanda **Administración**, haga clic con el botón derecho en **Recopilación de datos**y, después, haga clic en **Ver registros**.</span><span class="sxs-lookup"><span data-stu-id="118a3-137">In Object Explorer, expand **Management**, right-click **Data Collection**, and then click **View Logs**.</span></span>  
  
     <span data-ttu-id="118a3-138">Los registros son **Recopilación de datos**, **Historial de trabajos**y **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="118a3-138">The logs include **Data Collection**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-database-mail"></a><span data-ttu-id="118a3-139">Para ver los registros relacionados con Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="118a3-139">To view logs that are related to Database Mail</span></span>  
  
-   <span data-ttu-id="118a3-140">En el Explorador de objetos, expanda **Administración**, haga clic con el botón derecho en **Correo electrónico de base de datos**y, después, haga clic en **Ver registro de Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="118a3-140">In Object Explorer, expand **Management**, right-click **Database Mail**, and then click **View Database Mail Log**.</span></span>  
  
     <span data-ttu-id="118a3-141">Los registros son **Correo electrónico de base de datos, Historial de trabajos**, **Planes de mantenimiento**, **Planes de mantenimiento remotos**, **SQL Server**, **Agente SQL Server**y **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="118a3-141">The logs include **Database Mail, Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="118a3-142">Para ver los registros relacionados con las recopilaciones de auditorías</span><span class="sxs-lookup"><span data-stu-id="118a3-142">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="118a3-143">En el Explorador de objetos, expanda **Seguridad**, expanda **Auditorías**, haga clic con el botón derecho en una auditoría y, después, haga clic en **Ver registros de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="118a3-143">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="118a3-144">Los registros son **Recopilación de auditoría** y **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="118a3-144">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="118a3-145">Para ver los registros relacionados con las recopilaciones de auditorías</span><span class="sxs-lookup"><span data-stu-id="118a3-145">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="118a3-146">En el Explorador de objetos, expanda **Seguridad**, expanda **Auditorías**, haga clic con el botón derecho en una auditoría y, después, haga clic en **Ver registros de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="118a3-146">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="118a3-147">Los registros son **Recopilación de auditoría** y **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="118a3-147">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118a3-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="118a3-148">See Also</span></span>  
 <span data-ttu-id="118a3-149">[Visor de archivos de registro](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="118a3-149">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="118a3-150">[SQL Server Audit &#40;motor de base de datos&#41;](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="118a3-150">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="118a3-151">Ver archivos del registro sin conexión</span><span class="sxs-lookup"><span data-stu-id="118a3-151">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
