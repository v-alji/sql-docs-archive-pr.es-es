---
title: Iniciar SQL Server Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: 22e57ffa-63b0-4de3-b92e-df297dda1226
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05743927420865a9b6341fc050ca999f494d64d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747330"
---
# <a name="start-sql-server-profiler"></a><span data-ttu-id="65220-102">Iniciar SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="65220-102">Start SQL Server Profiler</span></span>
  <span data-ttu-id="65220-103">Puede iniciar [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] de varias formas distintas para admitir la recopilación de resultados de seguimiento en diversos escenarios.</span><span class="sxs-lookup"><span data-stu-id="65220-103">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] in several different ways to support gathering trace output in a variety of scenarios.</span></span> <span data-ttu-id="65220-104">Entre las diferentes formas de iniciar [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] se incluyen: desde el menú **Inicio** , desde el menú **Herramientas** en el Asistente para la optimización de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y desde varias ubicaciones en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65220-104">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] include from the **Start** menu, from the **Tools** menu in [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor, and from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="65220-105">Al iniciar [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] por primera vez y seleccionar **Nuevo seguimiento** en el menú **Archivo** , la aplicación muestra un cuadro de diálogo **Conectar al servidor** en el que se puede especificar la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a la que se desea conectar.</span><span class="sxs-lookup"><span data-stu-id="65220-105">When you first start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and select **New Trace** from the **File** menu, the application displays a **Connect to Server** dialog box where you can specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to which you want to connect.</span></span>  
  
### <a name="to-start-sql-server-profiler-from-the-start-menu"></a><span data-ttu-id="65220-106">Para iniciar SQL Server Profiler desde el menú Inicio</span><span class="sxs-lookup"><span data-stu-id="65220-106">To start SQL Server Profiler from the Start menu</span></span>  
  
1.  <span data-ttu-id="65220-107">En el menú **Inicio** , elija **Todos los programas**, seleccione [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Herramientas de rendimiento**y, a continuación, haga clic en **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="65220-107">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and then click **SQL Server Profiler**.</span></span>  
  
### <a name="to-start-sql-server-profiler-in-database-engine-tuning-advisor"></a><span data-ttu-id="65220-108">Para iniciar SQL Server Profiler en el Asistente para la optimización de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="65220-108">To start SQL Server Profiler in Database Engine Tuning Advisor</span></span>  
  
1.  <span data-ttu-id="65220-109">En el menú [!INCLUDE[ssDE](../../includes/ssde-md.md)] Herramientas **del Asistente para la optimización de** , haga clic en **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="65220-109">On the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
## <a name="starting-sql-server-profiler-in-management-studio"></a><span data-ttu-id="65220-110">Iniciar SQL Server Profiler en Management Studio</span><span class="sxs-lookup"><span data-stu-id="65220-110">Starting SQL Server Profiler in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="65220-111">inicia cada sesión del generador de perfiles en su propia instancia y continúa ejecutándose después de cerrar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65220-111">starts each profiler session in its own instance and continues to run if you shutdown [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="65220-112">Puede iniciar [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] desde varias ubicaciones en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], tal y como se muestra en los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="65220-112">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as illustrated in the following procedures.</span></span> <span data-ttu-id="65220-113">Cuando se inicia [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , éste carga el contexto de conexión, la plantilla de seguimiento y el contexto del filtro de su punto de inicio.</span><span class="sxs-lookup"><span data-stu-id="65220-113">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] starts it loads the connection context, trace template, and filter context of its launch point.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-tools-menu"></a><span data-ttu-id="65220-114">Para iniciar SQL Server Profiler desde el menú Herramientas</span><span class="sxs-lookup"><span data-stu-id="65220-114">To start SQL Server Profiler from the Tools menu</span></span>  
  
1.  <span data-ttu-id="65220-115">En el menú **Herramientas** de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], haga clic en **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="65220-115">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-query-editor"></a><span data-ttu-id="65220-116">Para iniciar SQL Server Profiler desde el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="65220-116">To start SQL Server Profiler from the Query Editor</span></span>  
  
1.  <span data-ttu-id="65220-117">En la barra de menús de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="65220-117">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] menu bar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="65220-118">En el Editor de consultas, haga clic con el botón derecho y seleccione **Realizar seguimiento de la consulta en SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="65220-118">In Query Editor, right-click and then select **Trace Query in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="65220-119">El contexto de conexión es la conexión del editor, la plantilla de seguimiento es TSQL_SPs y el filtro aplicado es SPID = ventana de consulta SPID.</span><span class="sxs-lookup"><span data-stu-id="65220-119">The connection context is the editor connection, the trace template is TSQL_SPs, and the applied filter is SPID = query window SPID.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-activity-monitor"></a><span data-ttu-id="65220-120">Para iniciar SQL Server Profiler desde el Monitor de actividad</span><span class="sxs-lookup"><span data-stu-id="65220-120">To start SQL Server Profiler from Activity Monitor</span></span>  
  
1.  <span data-ttu-id="65220-121">En el Explorador de objetos, haga clic con el botón derecho en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]y haga clic en **Monitor de actividad**.</span><span class="sxs-lookup"><span data-stu-id="65220-121">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="65220-122">Haga clic en el panel **Procesos** , haga clic con el botón derecho en el proceso cuyo perfil quiera generar y haga clic en **Realizar seguimiento de proceso en SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="65220-122">Click the **Processes** pane, right-click the process that you want to profile, and then click **Trace Process in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="65220-123">Cuando se selecciona un proceso, el contexto de conexión es la conexión del Explorador de objetos cuando se abrió el Monitor de actividad.</span><span class="sxs-lookup"><span data-stu-id="65220-123">When a process is selected, the connection context is the Object Explorer connection when Activity Monitor was opened.</span></span> <span data-ttu-id="65220-124">La plantilla de seguimiento es el valor predeterminado según el tipo de servidor y el SPID es igual al SPID del proceso seleccionado.</span><span class="sxs-lookup"><span data-stu-id="65220-124">The trace template is the default based on the server type, and the SPID equals the SPID for the selected process.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="65220-125">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="65220-125">.NET Framework Security</span></span>  
 <span data-ttu-id="65220-126">En el modo de autenticación de Windows, la cuenta de usuario que ejecuta [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] debe tener permiso para conectarse a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65220-126">In Windows Authentication mode, the user account that runs [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] must have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="65220-127">Para realizar seguimientos con el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], los usuarios también deben disponer del permiso ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="65220-127">To perform tracing with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], users must also have the ALTER TRACE permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65220-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65220-128">See Also</span></span>  
 <span data-ttu-id="65220-129">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="65220-129">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="65220-130">Usar SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65220-130">Use SQL Server Management Studio</span></span>](../../database-engine/use-sql-server-management-studio.md)  
  
  
