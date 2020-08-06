---
title: Opción Replay (herramienta de administración de Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: d7bce6a5-d414-488d-a3cd-50c1c62019c4
author: stevestein
ms.author: sstein
ms.openlocfilehash: a3114d7c2a2a7908e4e010fbf5d80c7d332d264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749536"
---
# <a name="replay-option-distributed-replay-administration-tool"></a><span data-ttu-id="10d39-102">Opción Replay (herramienta de administración de Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="10d39-102">Replay Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="10d39-103">La [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] herramienta de administración de Distributed Replay, `DReplay.exe` , es una herramienta de línea de comandos que puede usar para comunicarse con el controlador de reproducción distribuida.</span><span class="sxs-lookup"><span data-stu-id="10d39-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="10d39-104">En este tema se describe la opción de la línea de comandos **replay** y la sintaxis correspondiente.</span><span class="sxs-lookup"><span data-stu-id="10d39-104">This topic describes the **replay** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="10d39-105">La opción **replay** inicia la fase de reproducción de eventos, en la que el controlador envía los datos de reproducción a los clientes especificados, inicia la reproducción distribuida y sincroniza los clientes.</span><span class="sxs-lookup"><span data-stu-id="10d39-105">The **replay** option initiates the event replay stage, in which the controller dispatches replay data to the specified clients, launches the distributed replay and synchronizes the clients.</span></span> <span data-ttu-id="10d39-106">Opcionalmente, cada cliente que participa en la reproducción puede grabar la actividad de reproducción y guardar un archivo de seguimiento del resultado localmente.</span><span class="sxs-lookup"><span data-stu-id="10d39-106">Optionally, each client participating in the replay can record the replay activity and save a result trace file locally.</span></span>

 <span data-ttu-id="10d39-107">![Icono de vínculo de tema](../../database-engine/media/topic-link.gif "Icono de vínculo de tema") Para más información sobre las convenciones de sintaxis que se usan con la sintaxis de la herramienta de administración, consulte [Convenciones de sintaxis de Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="10d39-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="10d39-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10d39-108">Syntax</span></span>

```

      dreplay replay [-mcontroller] -dcontroller_working_dir [-o]
    [-starget_server] -wclients [-cconfig_file]
    [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="10d39-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10d39-109">Parameters</span></span>
 <span data-ttu-id="10d39-110">*controlador* **-m** especifica el nombre del equipo del controlador.</span><span class="sxs-lookup"><span data-stu-id="10d39-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="10d39-111">Puede utilizar "`localhost`" o "`.`" para hacer referencia al equipo local.</span><span class="sxs-lookup"><span data-stu-id="10d39-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="10d39-112">Si no se especifica el parámetro **-m** , se usará el equipo local.</span><span class="sxs-lookup"><span data-stu-id="10d39-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="10d39-113">**-d** *controller_working_dir* especifica el directorio del controlador donde se almacenará el archivo intermedio.</span><span class="sxs-lookup"><span data-stu-id="10d39-113">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="10d39-114">El parámetro **-d** es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="10d39-114">The **-d** parameter is required.</span></span>

 <span data-ttu-id="10d39-115">Se aplican los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="10d39-115">The following requirements apply:</span></span>

-   <span data-ttu-id="10d39-116">El directorio debe residir en el controlador.</span><span class="sxs-lookup"><span data-stu-id="10d39-116">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="10d39-117">Debe especificar la ruta de acceso completa, comenzando por una letra de unidad (por ejemplo, `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="10d39-117">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="10d39-118">La ruta de acceso no debe finalizar con una barra diagonal inversa "`\`".</span><span class="sxs-lookup"><span data-stu-id="10d39-118">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="10d39-119">No se admiten las rutas de acceso UNC.</span><span class="sxs-lookup"><span data-stu-id="10d39-119">UNC paths are not supported.</span></span>

 <span data-ttu-id="10d39-120">**-o** Captura la actividad de reproducción de los clientes y la guarda en un archivo de seguimiento de resultados en la ruta de acceso especificada por el `<ResultDirectory>` elemento en el archivo de configuración del cliente, `DReplayClient.xml` .</span><span class="sxs-lookup"><span data-stu-id="10d39-120">**-o** Captures the clients' replay activity and saves it to a result trace file in the path specified by the `<ResultDirectory>` element in the client configuration file, `DReplayClient.xml`.</span></span>

 <span data-ttu-id="10d39-121">Cuando no se especifica el parámetro **-o**, no se genera el archivo de seguimiento de resultados.</span><span class="sxs-lookup"><span data-stu-id="10d39-121">When the **-o** parameter is not specified, the result trace file is not generated.</span></span> <span data-ttu-id="10d39-122">La salida de la consola devuelve información de resumen al final de la reproducción, pero no hay ninguna otra estadística de reproducción disponible.</span><span class="sxs-lookup"><span data-stu-id="10d39-122">The console output returns summary information at the end of replay, but no other replay statistics are available.</span></span>

 <span data-ttu-id="10d39-123">**-s** *target_server* especifica la instancia de destino de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la que se debe volver a reproducir la carga de trabajo distribuida.</span><span class="sxs-lookup"><span data-stu-id="10d39-123">**-s** *target_server* Specifies the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that the distributed workload should be replayed against.</span></span> <span data-ttu-id="10d39-124">Debe especificar este parámetro con el formato **nombre_servidor[\nombre de instancia]** .</span><span class="sxs-lookup"><span data-stu-id="10d39-124">You must specify this parameter in the format **server_name[\instance name]**.</span></span>

 <span data-ttu-id="10d39-125">No se puede utilizar "`localhost`" ni "`.`" como servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="10d39-125">You cannot use "`localhost`" or "`.`" as the target server.</span></span>

 <span data-ttu-id="10d39-126">El parámetro **-s** no es necesario si se especifica el elemento `<Server>` en la sección `<ReplayOptions>` del archivo de configuración de reproducción, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="10d39-126">The **-s** parameter is not required if the `<Server>` element is specified in the `<ReplayOptions>` section of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="10d39-127">Si se usa el parámetro **-s** , se omitirá el elemento `<Server>` de la sección `<ReplayOptions>` del archivo de configuración de reproducción.</span><span class="sxs-lookup"><span data-stu-id="10d39-127">If the **-s** parameter is used, the `<Server>` element in the `<ReplayOptions>` section of the replay configuration file will be ignored.</span></span>

 <span data-ttu-id="10d39-128">**-w** *clientes* este parámetro obligatorio es una lista separada por comas (sin espacios) que especifica los nombres de equipo de los clientes que deben participar en la reproducción distribuida.</span><span class="sxs-lookup"><span data-stu-id="10d39-128">**-w** *clients* This required parameter is a comma-separated list (without spaces) that specifies the computer names of clients that should participate in the distributed replay.</span></span> <span data-ttu-id="10d39-129">No se permiten direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="10d39-129">IP addresses are not allowed.</span></span> <span data-ttu-id="10d39-130">Tenga en cuenta que los clientes ya deben estar registrados con el controlador.</span><span class="sxs-lookup"><span data-stu-id="10d39-130">Be aware that the clients must already be registered with the controller.</span></span>

> [!NOTE]
>  <span data-ttu-id="10d39-131">Cada cliente se registra con el controlador especificado en el archivo de configuración del cliente cuando se inicia el servicio del cliente.</span><span class="sxs-lookup"><span data-stu-id="10d39-131">Each client registers with the controller that is specified in the client configuration file when the client service starts.</span></span>

 <span data-ttu-id="10d39-132">**-c** *config_file* es la ruta de acceso completa del archivo de configuración de reproducción; se usa para especificar la ubicación cuando se almacena en una ubicación diferente.</span><span class="sxs-lookup"><span data-stu-id="10d39-132">**-c** *config_file* Is the full path of the replay configuration file; used to specify the location when it is stored in a different location.</span></span>

 <span data-ttu-id="10d39-133">No se requiere el parámetro **-c** si pretende usar los valores predeterminados del archivo de configuración de reproducción, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="10d39-133">The **-c** parameter is not required if you want to use the default values of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="10d39-134">**-f** *status_interval* especifica la frecuencia (en segundos) con la que se va a mostrar el estado.</span><span class="sxs-lookup"><span data-stu-id="10d39-134">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="10d39-135">Si no se especifica **-f** , el intervalo predeterminado es de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="10d39-135">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="10d39-136">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="10d39-136">Examples</span></span>
 <span data-ttu-id="10d39-137">En este ejemplo, la reproducción distribuida deriva gran parte de su comportamiento de un archivo de configuración de reproducción modificado, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="10d39-137">In this example, the distributed replay derives much of its behavior from a modified replay configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="10d39-138">El parámetro **-m** especifica que un equipo denominado `controller1` actúa como controlador.</span><span class="sxs-lookup"><span data-stu-id="10d39-138">The **-m** parameter specifies that a computer named `controller1` acts as the controller.</span></span> <span data-ttu-id="10d39-139">Se debe especificar el nombre de equipo cuando el servicio del controlador se está ejecutando en un equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="10d39-139">The computer name must be specified when the controller service is running on a different computer.</span></span>

-   <span data-ttu-id="10d39-140">El parámetro **-d** especifica la ubicación del archivo intermedio en el controlador, `c:\WorkingDir`.</span><span class="sxs-lookup"><span data-stu-id="10d39-140">The **-d** parameter specifies the location of the intermediate file on the controller, `c:\WorkingDir`.</span></span>

-   <span data-ttu-id="10d39-141">El parámetro **-o** establece que cada cliente especificado captura la actividad de reproducción y la guarda en un archivo de seguimiento de resultados.</span><span class="sxs-lookup"><span data-stu-id="10d39-141">The **-o** parameter specifies that each specified client capture the replay activity and save it to a result trace file.</span></span> <span data-ttu-id="10d39-142">Nota: El elemento `<ResultTrace>` del archivo de configuración se puede usar para especificar si se registran el recuento de filas y el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="10d39-142">Note: The `<ResultTrace>` element in the configuration file can be used to specify if row count and result set be recorded.</span></span>

-   <span data-ttu-id="10d39-143">El parámetro **-w** especifica que los equipos de `client1` a `client4` participan como clientes en la reproducción distribuida.</span><span class="sxs-lookup"><span data-stu-id="10d39-143">The **-w** parameter specifies that computers `client1` through `client4` participate as clients in the distributed replay.</span></span>

-   <span data-ttu-id="10d39-144">El parámetro **-c** se usa para apuntar al archivo de configuración modificado, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="10d39-144">The **-c** parameter is used to point to the modified configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="10d39-145">El parámetro **-s** no es necesario porque el elemento `<Server>` se especifica en el elemento `<ReplayOptions>` del archivo de configuración de reproducción, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="10d39-145">The **-s** parameter is not required because the `<Server>` element is specified in the `<ReplayOptions>` element of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="10d39-146">La fase de reproducción de eventos se inicia con la siguiente sintaxis cuando la herramienta de administración se ejecuta en un equipo diferente al controlador:</span><span class="sxs-lookup"><span data-stu-id="10d39-146">The event replay stage is initiated with the following syntax, when the administration tool is run from a different computer than the controller:</span></span>

```
dreplay replay -m controller1 -d c:\WorkingDir -o -w client1,client2,client3,client4 -c c:\DReplay.exe.replay.config
```

 <span data-ttu-id="10d39-147">Para especificar un modo secuenciación sincrónico, el elemento `<SequencingMode>` del archivo `DReplay.exe.replay.config` se establece igual que el valor `synchronization`.</span><span class="sxs-lookup"><span data-stu-id="10d39-147">To specify a synchronous sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `synchronization`.</span></span> <span data-ttu-id="10d39-148">La sección `<ResultTrace>` del archivo de configuración de reproducción se modifica para especificar que se registre el recuento de filas.</span><span class="sxs-lookup"><span data-stu-id="10d39-148">The `<ResultTrace>` section of the replay configuration file is modified to specify that row count be recorded.</span></span> <span data-ttu-id="10d39-149">Estos cambios se muestran en el siguiente ejemplo de XML:</span><span class="sxs-lookup"><span data-stu-id="10d39-149">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance</Server>
        <SequencingMode>synchronization</SequencingMode>
        <ConnectTimeScale></ConnectTimeScale>
        <ThinkTimeScale></ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

 <span data-ttu-id="10d39-150">Para especificar un modo de secuenciación de esfuerzo, el elemento `<SequencingMode>` del archivo `DReplay.exe.replay.config` se establece igual que el valor `stress`.</span><span class="sxs-lookup"><span data-stu-id="10d39-150">To specify a stress sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `stress`.</span></span> <span data-ttu-id="10d39-151">Los elementos `<ConnectTimeScale>` y `<ThinkTimeScale>` se establecen en el valor `50` (para especificar el 50 por ciento).</span><span class="sxs-lookup"><span data-stu-id="10d39-151">The `<ConnectTimeScale>` and `<ThinkTimeScale>` elements are set to the value `50` (to specify 50 percent).</span></span> <span data-ttu-id="10d39-152">Para obtener más información sobre el tiempo de conexión y tiempo de reflexión, vea [Configure Distributed Replay](configure-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="10d39-152">For more information about connect time and think time, see [Configure Distributed Replay](configure-distributed-replay.md).</span></span> <span data-ttu-id="10d39-153">Estos cambios se muestran en el siguiente ejemplo de XML:</span><span class="sxs-lookup"><span data-stu-id="10d39-153">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance_name</Server>
        <SequencingMode>stress</SequencingMode>
        <ConnectTimeScale>50</ConnectTimeScale>
        <ThinkTimeScale>50</ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="10d39-154">Permisos</span><span class="sxs-lookup"><span data-stu-id="10d39-154">Permissions</span></span>
 <span data-ttu-id="10d39-155">Debe ejecutar la herramienta de administración como un usuario interactivo, como un usuario local o una cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="10d39-155">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="10d39-156">Para utilizar una cuenta de usuario local, la herramienta de administración y el controlador se deben estar ejecutando en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="10d39-156">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="10d39-157">Para más información, consulte [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="10d39-157">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="10d39-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10d39-158">See Also</span></span>
 <span data-ttu-id="10d39-159">[Reproducir datos de seguimiento](replay-trace-data.md) [Revise los resultados de la reproducción](review-the-replay-results.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [configurar Distributed Replay](configure-distributed-replay.md) [SQL Server Foro de Distributed Replay](https://social.technet.microsoft.com/Forums/sl/sqldru/) [con Distributed Replay para realizar una prueba de carga de la SQL Server, parte 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [usando Distributed Replay para la prueba de carga de la SQL Server, parte 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span><span class="sxs-lookup"><span data-stu-id="10d39-159">[Replay Trace Data](replay-trace-data.md) [Review the Replay Results](review-the-replay-results.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md) [SQL Server Distributed Replay Forum](https://social.technet.microsoft.com/Forums/sl/sqldru/) [Using Distributed Replay to Load Test Your SQL Server - Part 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [Using Distributed Replay to Load Test Your SQL Server - Part 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span></span>


