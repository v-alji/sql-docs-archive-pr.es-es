---
title: Opción Preprocess (herramienta de administración de Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: 9b5012fd-233e-4a25-a2e1-585c63b70502
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7f168d45b03473d958e202bd75116f4519d2fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670725"
---
# <a name="preprocess-option-distributed-replay-administration-tool"></a><span data-ttu-id="047f0-102">Opción de preprocesamiento (herramienta de administración Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="047f0-102">Preprocess Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="047f0-103">La [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herramienta de administración de Distributed Replay, `DReplay.exe` , es una herramienta de línea de comandos que puede usar para comunicarse con el controlador de reproducción distribuida.</span><span class="sxs-lookup"><span data-stu-id="047f0-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="047f0-104">En este tema se describen la opción del símbolo del sistema **preprocess** y la sintaxis correspondiente.</span><span class="sxs-lookup"><span data-stu-id="047f0-104">This topic describes the **preprocess** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="047f0-105">La opción **preprocess** inicia la fase de preprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="047f0-105">The **preprocess** option initiates the preprocess stage.</span></span> <span data-ttu-id="047f0-106">Durante esta fase, el controlador prepara los datos de seguimiento de entrada para la reproducción en el servidor destino.</span><span class="sxs-lookup"><span data-stu-id="047f0-106">During this stage, the controller prepares the input trace data for replay against the target server.</span></span>

 <span data-ttu-id="047f0-107">![Icono de vínculo de tema](../../database-engine/media/topic-link.gif "Icono de vínculo de tema") Para más información sobre las convenciones de sintaxis que se usan con la sintaxis de la herramienta de administración, consulte [Convenciones de sintaxis de Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="047f0-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="047f0-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="047f0-108">Syntax</span></span>

```

      dreplay preprocess [-mcontroller] -iinput_trace_file
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="047f0-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="047f0-109">Parameters</span></span>
 <span data-ttu-id="047f0-110">*controlador* **-m** especifica el nombre del equipo del controlador.</span><span class="sxs-lookup"><span data-stu-id="047f0-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="047f0-111">Puede utilizar "`localhost`" o "`.`" para hacer referencia al equipo local.</span><span class="sxs-lookup"><span data-stu-id="047f0-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="047f0-112">Si no se especifica el parámetro **-m** , se usará el equipo local.</span><span class="sxs-lookup"><span data-stu-id="047f0-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="047f0-113">**-i** *input_trace_file* especifica la ruta de acceso completa del archivo de seguimiento de entrada en el controlador, como `D:\Mytrace.trc` .</span><span class="sxs-lookup"><span data-stu-id="047f0-113">**-i** *input_trace_file* Specifies the full path of the input trace file on the controller, such as `D:\Mytrace.trc`.</span></span> <span data-ttu-id="047f0-114">El parámetro **-i** es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="047f0-114">The **-i** parameter is required.</span></span>

 <span data-ttu-id="047f0-115">Si hay archivos de sustitución incremental en el mismo directorio, se cargarán y usarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="047f0-115">If there are rollover files in the same directory, they will be loaded and used automatically.</span></span> <span data-ttu-id="047f0-116">Los archivos deben seguir la convención de nomenclatura de sustitución incremental de archivos, por ejemplo: `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`... `Mytrace_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="047f0-116">The files must follow the file rollover naming convention, for example: `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, ... `Mytrace_n.trc`.</span></span>

> [!NOTE]
>  <span data-ttu-id="047f0-117">Si está usando la herramienta de administración en un equipo que no es el controlador, tendrá que copiar los archivos de seguimiento de entrada en el controlador de forma que se pueda usar una ruta de acceso local para este parámetro.</span><span class="sxs-lookup"><span data-stu-id="047f0-117">If you are using the administration tool on a different computer than the controller, you will need to copy the input trace files to the controller so that a local path can be used for this parameter.</span></span>

 <span data-ttu-id="047f0-118">**-d** *controller_working_dir* especifica el directorio del controlador donde se almacenará el archivo intermedio.</span><span class="sxs-lookup"><span data-stu-id="047f0-118">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="047f0-119">El parámetro **-d** es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="047f0-119">The **-d** parameter is required.</span></span>

 <span data-ttu-id="047f0-120">Se aplican los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="047f0-120">The following requirements apply:</span></span>

-   <span data-ttu-id="047f0-121">El directorio debe residir en el controlador.</span><span class="sxs-lookup"><span data-stu-id="047f0-121">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="047f0-122">Debe especificar la ruta de acceso completa, comenzando por una letra de unidad (por ejemplo, `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="047f0-122">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="047f0-123">La ruta de acceso no debe finalizar con una barra diagonal inversa "`\`".</span><span class="sxs-lookup"><span data-stu-id="047f0-123">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="047f0-124">No se admiten las rutas de acceso UNC.</span><span class="sxs-lookup"><span data-stu-id="047f0-124">UNC paths are not supported.</span></span>

 <span data-ttu-id="047f0-125">**-c** *config_file* es la ruta de acceso completa del archivo de configuración de preprocesamiento; se usa para especificar la ubicación del archivo de configuración de preprocesamiento cuando se almacena en una ubicación diferente.</span><span class="sxs-lookup"><span data-stu-id="047f0-125">**-c** *config_file* Is the full path of the preprocess configuration file; used to specify the location of the preprocess configuration file when stored in a different location.</span></span> <span data-ttu-id="047f0-126">Este parámetro puede ser una ruta UNC o puede residir localmente en el equipo donde se ejecuta la herramienta de administración.</span><span class="sxs-lookup"><span data-stu-id="047f0-126">This parameter can be a UNC path, or can reside locally on the computer where you run the administration tool.</span></span>

 <span data-ttu-id="047f0-127">El parámetro **-c** no es obligatorio si no se necesita ningún filtrado o si no se quiere modificar el tiempo de inactividad máximo.</span><span class="sxs-lookup"><span data-stu-id="047f0-127">The **-c** parameter is not required if no filtering is needed, or if you do not want to modify the maximum idle time.</span></span>

 <span data-ttu-id="047f0-128">Sin el parámetro **-c** , se usa el archivo de configuración de preprocesamiento predeterminado, `DReplay.exe.preprocess.config`.</span><span class="sxs-lookup"><span data-stu-id="047f0-128">Without the **-c** parameter, the default preprocess configuration file, `DReplay.exe.preprocess.config`, is used.</span></span>

 <span data-ttu-id="047f0-129">**-f** *status_interval* especifica la frecuencia (en segundos) con la que se muestran los mensajes de estado.</span><span class="sxs-lookup"><span data-stu-id="047f0-129">**-f** *status_interval* Specifies the frequency (in seconds) at which to display status messages.</span></span>

 <span data-ttu-id="047f0-130">Si no se especifica **-f** , el intervalo predeterminado es de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="047f0-130">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="047f0-131">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="047f0-131">Examples</span></span>
 <span data-ttu-id="047f0-132">En este ejemplo, la copia intermedia del preprocesamiento se inicia con toda la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="047f0-132">In this example, the preprocess stage is initiated with all of the default settings.</span></span> <span data-ttu-id="047f0-133">El valor `localhost` indica que el servicio del controlador se está ejecutando en el mismo equipo que la herramienta de administración.</span><span class="sxs-lookup"><span data-stu-id="047f0-133">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span> <span data-ttu-id="047f0-134">El parámetro *input_trace_file* especifica la ubicación de los datos de seguimiento de entrada, `c:\mytrace.trc`.</span><span class="sxs-lookup"><span data-stu-id="047f0-134">The *input_trace_file* parameter specifies the location of the input trace data, `c:\mytrace.trc`.</span></span> <span data-ttu-id="047f0-135">Dado que no se usa ningún filtrado de archivos de seguimiento, no es necesario especificar el parámetro **-c** .</span><span class="sxs-lookup"><span data-stu-id="047f0-135">Because there is no trace file filtering involved, the **-c** parameter does have to be specified.</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir
```

 <span data-ttu-id="047f0-136">En este ejemplo, se inicia la fase de preprocesamiento y se especifica un archivo de configuración del preprocesamiento modificado.</span><span class="sxs-lookup"><span data-stu-id="047f0-136">In this example, the preprocess stage is initiated and a modified preprocess configuration file is specified.</span></span> <span data-ttu-id="047f0-137">A diferencia del ejemplo anterior, el parámetro **-c** se usa para indicar el archivo de configuración modificado, si se ha almacenado en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="047f0-137">Unlike the previous example, the **-c** parameter is used to point to the modified configuration file, if you have stored it in a different location.</span></span> <span data-ttu-id="047f0-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="047f0-138">For example:</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir -c c:\DReplay.exe.preprocess.config
```

 <span data-ttu-id="047f0-139">En el archivo de configuración del preprocesamiento modificado, se agrega una condición de filtro que deja fuera las sesiones del sistema durante la reproducción distribuida.</span><span class="sxs-lookup"><span data-stu-id="047f0-139">In the modified preprocess configuration file, a filter condition is added that filters out system sessions during distributed replay.</span></span> <span data-ttu-id="047f0-140">El filtro se agrega modificando el elemento `<PreprocessModifiers>` del archivo de configuración del preprocesamiento, `DReplay.exe.preprocess.config`.</span><span class="sxs-lookup"><span data-stu-id="047f0-140">The filter is added by modifying the `<PreprocessModifiers>` element in the preprocess configuration file, `DReplay.exe.preprocess.config`.</span></span>

 <span data-ttu-id="047f0-141">En el ejemplo siguiente se muestra un ejemplo del archivo de configuración modificado:</span><span class="sxs-lookup"><span data-stu-id="047f0-141">The following shows an example of the modified configuration file:</span></span>

```
<?xml version='1.0'?>
<Options>
    <PreprocessModifiers>
        <IncSystemSession>No</IncSystemSession>
        <MaxIdleTime>-1</MaxIdleTime>
    </PreprocessModifiers>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="047f0-142">Permisos</span><span class="sxs-lookup"><span data-stu-id="047f0-142">Permissions</span></span>
 <span data-ttu-id="047f0-143">Debe ejecutar la herramienta de administración como un usuario interactivo, como un usuario local o una cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="047f0-143">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="047f0-144">Para utilizar una cuenta de usuario local, la herramienta de administración y el controlador se deben estar ejecutando en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="047f0-144">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="047f0-145">Para más información, consulte [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="047f0-145">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="047f0-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="047f0-146">See Also</span></span>
 <span data-ttu-id="047f0-147">[Preparar los datos de seguimiento de entrada](prepare-the-input-trace-data.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [configurar Distributed Replay](configure-distributed-replay.md)</span><span class="sxs-lookup"><span data-stu-id="047f0-147">[Prepare the Input Trace Data](prepare-the-input-trace-data.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md)</span></span>


