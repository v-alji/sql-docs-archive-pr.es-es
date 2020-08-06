---
title: Requisitos de Distributed Replay | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 6fffee7d-891f-4d9d-b2c3-dd19855a1c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 66be93534756360e722fcccaf405815e14ffa7ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672319"
---
# <a name="distributed-replay-requirements"></a><span data-ttu-id="131de-102">Distributed Replay Requirements</span><span class="sxs-lookup"><span data-stu-id="131de-102">Distributed Replay Requirements</span></span>
  <span data-ttu-id="131de-103">Antes de utilizar la característica Distributed Replay de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , tenga en cuenta los requisitos de productos que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="131de-103">Before using the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay feature, consider the product requirements that are outlined in this topic.</span></span>  
  
## <a name="input-trace-requirements"></a><span data-ttu-id="131de-104">Requisitos del seguimiento de entrada</span><span class="sxs-lookup"><span data-stu-id="131de-104">Input Trace Requirements</span></span>  
 <span data-ttu-id="131de-105">Para reproducir correctamente los datos de seguimiento, deben cumplir los requisitos de versión y el formato, y contener las columnas y eventos necesarios.</span><span class="sxs-lookup"><span data-stu-id="131de-105">To successfully replay trace data, it must meet the requirements for version and format, and contain the required events and columns.</span></span>  
  
### <a name="input-trace-versions"></a><span data-ttu-id="131de-106">Versiones de seguimiento de entrada</span><span class="sxs-lookup"><span data-stu-id="131de-106">Input Trace Versions</span></span>  
 <span data-ttu-id="131de-107">Distributed Replay admite los datos de seguimiento de entrada que se recopilan en las siguientes versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="131de-107">Distributed Replay supports input trace data that is collected on the following versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
### <a name="input-trace-formats"></a><span data-ttu-id="131de-108">Formatos de seguimiento de entrada</span><span class="sxs-lookup"><span data-stu-id="131de-108">Input Trace Formats</span></span>  
 <span data-ttu-id="131de-109">Los datos de seguimiento de entrada pueden estar en cualquiera de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="131de-109">The input trace data can be in any of the following formats:</span></span>  
  
-   <span data-ttu-id="131de-110">Un archivo de seguimiento con la extensión `.trc` .</span><span class="sxs-lookup"><span data-stu-id="131de-110">A single trace file that has the `.trc` extension.</span></span>  
  
-   <span data-ttu-id="131de-111">Un conjunto de archivos de seguimiento de sustitución que cumplen la convención de nomenclatura de sustitución incremental de archivos, por ejemplo: `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`… `<TraceFile>_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="131de-111">A set of rollover trace files that follow the file rollover naming convention, for example: `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, ... `<TraceFile>_n.trc`.</span></span>  
  
### <a name="input-trace-events-and-columns"></a><span data-ttu-id="131de-112">Columnas y eventos de seguimiento de entrada</span><span class="sxs-lookup"><span data-stu-id="131de-112">Input Trace Events and Columns</span></span>  
 <span data-ttu-id="131de-113">Los datos de seguimiento de entrada deben contener columnas y eventos específicos que se reproduzcan mediante Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="131de-113">The input trace data must contain specific events and columns to be replayed by Distributed Replay.</span></span> <span data-ttu-id="131de-114">La plantilla **TSQL_Replay** de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] contiene todas las columnas y eventos necesarios, además de información adicional.</span><span class="sxs-lookup"><span data-stu-id="131de-114">The **TSQL_Replay** template in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] contains all of the required events and columns, in addition to extra information.</span></span> <span data-ttu-id="131de-115">Para obtener más información acerca de esa plantilla, vea [Replay Requirements](../sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="131de-115">For more information about that template, see [Replay Requirements](../sql-server-profiler/replay-requirements.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="131de-116">Si no usa la plantilla **TSQL_Replay** para capturar los datos de seguimiento de entrada, o si los requisitos de seguimiento de entrada no se cumplen, puede obtener resultados de la reproducción inesperados.</span><span class="sxs-lookup"><span data-stu-id="131de-116">If you do not use the **TSQL_Replay** template to capture the input trace data, or if the input trace requirements are not satisfied, you may receive unexpected replay results.</span></span>  
  
 <span data-ttu-id="131de-117">También puede crear una plantilla de seguimiento personalizada y utilizarla para reproducir los eventos mediante Distributed Replay, siempre que contenga los eventos siguientes:</span><span class="sxs-lookup"><span data-stu-id="131de-117">You can also create a custom trace template and use it to replay events with Distributed Replay, as long as it contains the following events:</span></span>  
  
-   <span data-ttu-id="131de-118">Audit Login</span><span class="sxs-lookup"><span data-stu-id="131de-118">Audit Login</span></span>  
  
-   <span data-ttu-id="131de-119">Audit Logout</span><span class="sxs-lookup"><span data-stu-id="131de-119">Audit Logout</span></span>  
  
-   <span data-ttu-id="131de-120">ExistingConnection</span><span class="sxs-lookup"><span data-stu-id="131de-120">ExistingConnection</span></span>  
  
-   <span data-ttu-id="131de-121">RPC Output Parameter</span><span class="sxs-lookup"><span data-stu-id="131de-121">RPC Output Parameter</span></span>  
  
-   <span data-ttu-id="131de-122">RPC:Completed</span><span class="sxs-lookup"><span data-stu-id="131de-122">RPC:Completed</span></span>  
  
-   <span data-ttu-id="131de-123">RPC:Starting</span><span class="sxs-lookup"><span data-stu-id="131de-123">RPC:Starting</span></span>  
  
-   <span data-ttu-id="131de-124">SQL:BatchCompleted</span><span class="sxs-lookup"><span data-stu-id="131de-124">SQL:BatchCompleted</span></span>  
  
-   <span data-ttu-id="131de-125">SQL:BatchStarting</span><span class="sxs-lookup"><span data-stu-id="131de-125">SQL:BatchStarting</span></span>  
  
 <span data-ttu-id="131de-126">Si reproduce los cursores de servidor, los siguientes eventos también se requieren:</span><span class="sxs-lookup"><span data-stu-id="131de-126">If you are replaying server-side cursors, the following events are also required:</span></span>  
  
-   <span data-ttu-id="131de-127">CursorClose</span><span class="sxs-lookup"><span data-stu-id="131de-127">CursorClose</span></span>  
  
-   <span data-ttu-id="131de-128">CursorExecute</span><span class="sxs-lookup"><span data-stu-id="131de-128">CursorExecute</span></span>  
  
-   <span data-ttu-id="131de-129">CursorOpen</span><span class="sxs-lookup"><span data-stu-id="131de-129">CursorOpen</span></span>  
  
-   <span data-ttu-id="131de-130">CursorPrepare</span><span class="sxs-lookup"><span data-stu-id="131de-130">CursorPrepare</span></span>  
  
-   <span data-ttu-id="131de-131">CursorUnprepare</span><span class="sxs-lookup"><span data-stu-id="131de-131">CursorUnprepare</span></span>  
  
 <span data-ttu-id="131de-132">Si está reproduciendo instrucciones de SQL preparadas en el servidor, los siguientes eventos también se requieren:</span><span class="sxs-lookup"><span data-stu-id="131de-132">If you are replaying server-side prepared SQL statements, the following events are also required:</span></span>  
  
-   <span data-ttu-id="131de-133">Exec Prepared SQL</span><span class="sxs-lookup"><span data-stu-id="131de-133">Exec Prepared SQL</span></span>  
  
-   <span data-ttu-id="131de-134">Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="131de-134">Prepare SQL</span></span>  
  
 <span data-ttu-id="131de-135">Todos los datos de seguimiento de entrada deben contener las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="131de-135">All input trace data must contain the following columns:</span></span>  
  
-   <span data-ttu-id="131de-136">Clase de eventos</span><span class="sxs-lookup"><span data-stu-id="131de-136">Event Class</span></span>  
  
-   <span data-ttu-id="131de-137">EventSequence</span><span class="sxs-lookup"><span data-stu-id="131de-137">EventSequence</span></span>  
  
-   <span data-ttu-id="131de-138">TextData</span><span class="sxs-lookup"><span data-stu-id="131de-138">TextData</span></span>  
  
-   <span data-ttu-id="131de-139">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="131de-139">Application Name</span></span>  
  
-   <span data-ttu-id="131de-140">LoginName</span><span class="sxs-lookup"><span data-stu-id="131de-140">LoginName</span></span>  
  
-   <span data-ttu-id="131de-141">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="131de-141">DatabaseName</span></span>  
  
-   <span data-ttu-id="131de-142">Identificador de base de datos</span><span class="sxs-lookup"><span data-stu-id="131de-142">Database ID</span></span>  
  
-   <span data-ttu-id="131de-143">HostName</span><span class="sxs-lookup"><span data-stu-id="131de-143">HostName</span></span>  
  
-   <span data-ttu-id="131de-144">Binary Data</span><span class="sxs-lookup"><span data-stu-id="131de-144">Binary Data</span></span>  
  
-   <span data-ttu-id="131de-145">SPID</span><span class="sxs-lookup"><span data-stu-id="131de-145">SPID</span></span>  
  
-   <span data-ttu-id="131de-146">Hora de inicio</span><span class="sxs-lookup"><span data-stu-id="131de-146">Start Time</span></span>  
  
-   <span data-ttu-id="131de-147">EndTime</span><span class="sxs-lookup"><span data-stu-id="131de-147">EndTime</span></span>  
  
-   <span data-ttu-id="131de-148">IsSystem</span><span class="sxs-lookup"><span data-stu-id="131de-148">IsSystem</span></span>  
  
## <a name="supported-input-trace-and-target-server-combinations"></a><span data-ttu-id="131de-149">Combinaciones admitidas de servidor de destino y seguimiento de entrada</span><span class="sxs-lookup"><span data-stu-id="131de-149">Supported Input Trace and Target Server Combinations</span></span>  
 <span data-ttu-id="131de-150">En la tabla siguiente se enumeran las versiones admitidas de los datos de seguimiento y, para cada una, las versiones admitidas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en las que los datos se pueden reproducir.</span><span class="sxs-lookup"><span data-stu-id="131de-150">The following table lists the supported versions of trace data, and for each, the supported versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that data can be replayed against.</span></span>  
  
|<span data-ttu-id="131de-151">Versión de los datos de seguimiento de entrada</span><span class="sxs-lookup"><span data-stu-id="131de-151">Version of Input Trace Data</span></span>|<span data-ttu-id="131de-152">Versiones admitidas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la instancia del servidor de destino</span><span class="sxs-lookup"><span data-stu-id="131de-152">Supported Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the Target Server Instance</span></span>|  
|---------------------------------|------------------------------------------------------------------------------------|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="131de-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="131de-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="131de-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="131de-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="131de-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="131de-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]<span data-ttu-id="131de-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="131de-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|  
  
## <a name="operating-system-requirements"></a><span data-ttu-id="131de-157">Requisitos del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="131de-157">Operating System Requirements</span></span>  
 <span data-ttu-id="131de-158">Los sistemas operativos admitidos para ejecutar la herramienta de administración y los servicios del controlador y el cliente son los mismos que para la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="131de-158">Supported operating systems for running the administration tool and the controller and client services is the same as your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="131de-159">Para obtener más información acerca de los sistemas operativos que se admiten para la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instancia de, consulte [requisitos de hardware y software para la instalación de SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="131de-159">For more information about which operating systems are supported for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, see [Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
 <span data-ttu-id="131de-160">Las características de Distributed Replay se admiten en sistemas operativos basados en x86 y en x64.</span><span class="sxs-lookup"><span data-stu-id="131de-160">Distributed Replay features are supported on both x86-based and x64-based operating systems.</span></span> <span data-ttu-id="131de-161">Para los sistemas operativos basados en x64, solo se admite el modo Windows sobre Windows (WOW).</span><span class="sxs-lookup"><span data-stu-id="131de-161">For x64-based operating systems, only Windows on Windows (WOW) mode is supported.</span></span>  
  
## <a name="installation-limitations"></a><span data-ttu-id="131de-162">Limitaciones de la instalación</span><span class="sxs-lookup"><span data-stu-id="131de-162">Installation Limitations</span></span>  
 <span data-ttu-id="131de-163">Un equipo solo puede tener instalada una única instancia de cada característica Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="131de-163">Any one computer can only have a single instance of each Distributed Replay feature installed.</span></span> <span data-ttu-id="131de-164">La siguiente tabla muestra cuántas instalaciones de cada característica se permiten en un único entorno de Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="131de-164">The following table lists how many installations of each feature are allowed in a single Distributed Replay environment.</span></span>  
  
|<span data-ttu-id="131de-165">Característica Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="131de-165">Distributed Replay Feature</span></span>|<span data-ttu-id="131de-166">Instalaciones máximas por cada entorno de reproducción</span><span class="sxs-lookup"><span data-stu-id="131de-166">Maximum Installations Per Replay Environment</span></span>|  
|--------------------------------|--------------------------------------------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="131de-167">Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="131de-167">Distributed Replay controller service</span></span>|<span data-ttu-id="131de-168">1</span><span class="sxs-lookup"><span data-stu-id="131de-168">1</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="131de-169">Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="131de-169">Distributed Replay client service</span></span>|<span data-ttu-id="131de-170">16 (equipos físicos o virtuales)</span><span class="sxs-lookup"><span data-stu-id="131de-170">16 (physical or virtual computers)</span></span>|  
|<span data-ttu-id="131de-171">Herramienta de administración</span><span class="sxs-lookup"><span data-stu-id="131de-171">Administration tool</span></span>|<span data-ttu-id="131de-172">Sin límite</span><span class="sxs-lookup"><span data-stu-id="131de-172">Unlimited</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="131de-173">Aunque solo se puede instalar una instancia de la herramienta de administración en un solo equipo, puede iniciar varias instancias de la herramienta de administración.</span><span class="sxs-lookup"><span data-stu-id="131de-173">Although only one instance of the administration tool can be installed on a single computer, you can start multiple instances of the administration tool.</span></span> <span data-ttu-id="131de-174">Los comandos emitidos desde varias herramientas de administración se resuelven en el mismo orden en el que se reciben.</span><span class="sxs-lookup"><span data-stu-id="131de-174">Commands issued from multiple administration tools are resolved in the order in which they are received.</span></span>  
  
## <a name="data-access-provider"></a><span data-ttu-id="131de-175">Proveedor de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="131de-175">Data Access Provider</span></span>  
 <span data-ttu-id="131de-176">Distributed Replay solamente admite el proveedor de acceso a datos ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="131de-176">Distributed Replay only supports the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC data access provider.</span></span>  
  
## <a name="target-server-preparation-requirements"></a><span data-ttu-id="131de-177">Requisitos de preparación del servidor de destino</span><span class="sxs-lookup"><span data-stu-id="131de-177">Target Server Preparation Requirements</span></span>  
 <span data-ttu-id="131de-178">Se recomienda que el servidor de destino se encuentre en un entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="131de-178">We recommend that the target server be located in a test environment.</span></span> <span data-ttu-id="131de-179">Para reproducir los datos de seguimiento en otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diferente a donde se registró originalmente, asegúrese de que se ha realizado lo siguiente en el servidor de destino:</span><span class="sxs-lookup"><span data-stu-id="131de-179">To replay trace data against a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] than it was originally recorded, make sure that the following has been done to the target server:</span></span>  
  
-   <span data-ttu-id="131de-180">Todos los inicios de sesión y los usuarios que se encuentran en los datos de seguimiento deben estar presentes en la misma base de datos del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="131de-180">All logins and users that are contained in the trace data must be present in the same database on the target server.</span></span>  
  
-   <span data-ttu-id="131de-181">Todos los inicios de sesión y los usuarios en el servidor destino deben tener los mismos permisos que tenían en el servidor original.</span><span class="sxs-lookup"><span data-stu-id="131de-181">All logins and users on the target server must have the same permissions they had on the original server.</span></span>  
  
-   <span data-ttu-id="131de-182">Los Id. de base de datos del destino deben ser los mismos que los del origen.</span><span class="sxs-lookup"><span data-stu-id="131de-182">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="131de-183">Sin embargo, si no son los mismos, se puede realizar la coincidencia basándose en **DatabaseName** , si está presente en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="131de-183">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="131de-184">La base de datos predeterminada de cada inicio de sesión contenido en los datos de seguimiento debe establecerse (en el servidor de destino) en la base de datos de destino respectiva del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="131de-184">The default database for each login that is contained in the trace data must be set (on the target server) to the respective target database of the login.</span></span> <span data-ttu-id="131de-185">Por ejemplo, los datos de seguimiento que se van a reproducir contienen la actividad del inicio de sesión, **Fred**, en la base de datos **Fred_Db** de la instancia original de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="131de-185">For example, the trace data to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the original instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="131de-186">Por tanto, en el servidor de destino, la base de datos predeterminada del inicio de sesión, **Fred**, debe establecerse en la base de datos que coincida con **Fred_Db** (aunque el nombre de la base de datos sea diferente).</span><span class="sxs-lookup"><span data-stu-id="131de-186">Therefore, on the target server, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="131de-187">Para establecer la base de datos predeterminada del inicio de sesión, utilice el procedimiento almacenado del sistema `sp_defaultdb` .</span><span class="sxs-lookup"><span data-stu-id="131de-187">To set the default database of the login, use the `sp_defaultdb` system stored procedure.</span></span>  
  
 <span data-ttu-id="131de-188">La reproducción de eventos asociados a inicios de sesión que faltan o que son incorrectos tendrá como resultado errores de reproducción, pero la operación de reproducción continuará.</span><span class="sxs-lookup"><span data-stu-id="131de-188">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131de-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="131de-189">See Also</span></span>  
 <span data-ttu-id="131de-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span><span class="sxs-lookup"><span data-stu-id="131de-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span></span>  
 <span data-ttu-id="131de-191">[Seguridad de Distributed Replay](distributed-replay-security.md) </span><span class="sxs-lookup"><span data-stu-id="131de-191">[Distributed Replay Security](distributed-replay-security.md) </span></span>  
 [<span data-ttu-id="131de-192">Instalar Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="131de-192">Install Distributed Replay</span></span>](install-distributed-replay-overview.md)  
  
  
