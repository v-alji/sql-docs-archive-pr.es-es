---
title: Opciones de línea de comandos de la herramienta de administración (utilidad Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: c01b0ed3-67e4-4561-92d2-a8fbb086aca8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 506be071f44937d82902585e5a0621212083dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673953"
---
# <a name="administration-tool-command-line-options-distributed-replay-utility"></a><span data-ttu-id="15e45-102">Opciones de línea de comandos de la herramienta de administración (utilidad Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="15e45-102">Administration Tool Command-line Options (Distributed Replay Utility)</span></span>
  <span data-ttu-id="15e45-103">La [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herramienta de administración de Distributed Replay, `DReplay.exe` , es una herramienta de línea de comandos que puede usar para comunicarse con el controlador de reproducción distribuida.</span><span class="sxs-lookup"><span data-stu-id="15e45-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="15e45-104">Utilice la herramienta de administración para iniciar, supervisar y cancelar operaciones en el controlador.</span><span class="sxs-lookup"><span data-stu-id="15e45-104">Use the administration tool to initiate, monitor, and cancel operations on the controller.</span></span>  
  
 <span data-ttu-id="15e45-105">![Icono de vínculo de tema](../../database-engine/media/topic-link.gif "Icono de vínculo de tema") Para más información sobre las convenciones de sintaxis que se usan con la sintaxis de la herramienta de administración, consulte [Convenciones de sintaxis de Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15e45-105">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15e45-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15e45-106">Syntax</span></span>  
  
```  
  
      dreplay {preprocess|replay|status|cancel} [options] [-?]}  
  
Usage:  
  
  dreplay preprocess [-mcontroller] -iinput_trace_file  
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]  
  
  dreplay replay [-mcontroller] -dcontroller_working_dir [-o]  
    [-starget_server] -wclients [-cconfig_file]  
    [-fstatus_interval]  
  
  dreplay status [-mcontroller] [-fstatus_interval]  
  
  dreplay cancel [-mcontroller] [-q]   
```  
  
## <a name="remarks"></a><span data-ttu-id="15e45-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15e45-107">Remarks</span></span>  
 <span data-ttu-id="15e45-108">Puede emitir las siguientes opciones de línea de comandos con `DReplay.exe`:</span><span class="sxs-lookup"><span data-stu-id="15e45-108">You can issue the following command-line options with `DReplay.exe`:</span></span>  
  
 <span data-ttu-id="15e45-109">**preprocess**</span><span class="sxs-lookup"><span data-stu-id="15e45-109">**preprocess**</span></span>  
 <span data-ttu-id="15e45-110">Inicia la fase de preprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="15e45-110">Initiates the preprocess stage.</span></span> <span data-ttu-id="15e45-111">El controlador prepara la información de seguimiento de entrada, que se capturó en el entorno de producción, para la reproducción en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="15e45-111">The controller prepares the input trace data, which you captured from the production environment, for replay against the target server.</span></span>  
  
 <span data-ttu-id="15e45-112">**reproducir**</span><span class="sxs-lookup"><span data-stu-id="15e45-112">**replay**</span></span>  
 <span data-ttu-id="15e45-113">Inicia la fase de reproducción de eventos.</span><span class="sxs-lookup"><span data-stu-id="15e45-113">Initiates the event replay stage.</span></span> <span data-ttu-id="15e45-114">El controlador envía los datos de la reproducción a los clientes especificados, inicia la reproducción distribuida y sincroniza los clientes.</span><span class="sxs-lookup"><span data-stu-id="15e45-114">The controller dispatches replay data to the specified clients, launches the distributed replay, and synchronizes the clients.</span></span> <span data-ttu-id="15e45-115">Opcionalmente, cada cliente que se ha seleccionado registra la actividad de reproducción y guarda los archivos de seguimiento del resultado localmente.</span><span class="sxs-lookup"><span data-stu-id="15e45-115">Optionally, each client that was selected records the replay activity and saves result trace files locally.</span></span>  
  
 <span data-ttu-id="15e45-116">**status**</span><span class="sxs-lookup"><span data-stu-id="15e45-116">**status**</span></span>  
 <span data-ttu-id="15e45-117">Consulta el controlador y muestra el estado actual.</span><span class="sxs-lookup"><span data-stu-id="15e45-117">Queries the controller and displays the current status.</span></span>  
  
 <span data-ttu-id="15e45-118">**cancel**</span><span class="sxs-lookup"><span data-stu-id="15e45-118">**cancel**</span></span>  
 <span data-ttu-id="15e45-119">Cancela la operación que se está ejecutando actualmente en el controlador.</span><span class="sxs-lookup"><span data-stu-id="15e45-119">Cancels the current operation that is running on the controller.</span></span>  
  
 <span data-ttu-id="15e45-120">Para obtener información de la sintaxis detallada que incluye los argumentos de comando y ejemplos, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="15e45-120">For detailed syntax information that includes the command arguments and examples, see the following topics:</span></span>  
  
-   [<span data-ttu-id="15e45-121">Opción de preprocesamiento &#40;herramienta de administración Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="15e45-121">Preprocess Option &#40;Distributed Replay Administration Tool&#41;</span></span>](preprocess-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="15e45-122">Opción Replay &#40;herramienta de administración Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="15e45-122">Replay Option &#40;Distributed Replay Administration Tool&#41;</span></span>](replay-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="15e45-123">Opción Status &#40;herramienta de administración de Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="15e45-123">Status Option &#40;Distributed Replay Administration Tool&#41;</span></span>](status-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="15e45-124">Opción cancel &#40;herramienta de administración de Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="15e45-124">Cancel Option &#40;Distributed Replay Administration Tool&#41;</span></span>](cancel-option-distributed-replay-administration-tool.md)  
  
 <span data-ttu-id="15e45-125">Las RPC se reproducen como RPC y no como eventos de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="15e45-125">RPCs are replayed as RPCs and not as language events.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="15e45-126">Permisos</span><span class="sxs-lookup"><span data-stu-id="15e45-126">Permissions</span></span>  
 <span data-ttu-id="15e45-127">Debe ejecutar la herramienta de administración como un usuario interactivo, como un usuario local o una cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="15e45-127">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="15e45-128">Para utilizar una cuenta de usuario local, la herramienta de administración y el controlador se deben estar ejecutando en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="15e45-128">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>  
  
 <span data-ttu-id="15e45-129">Para más información, consulte [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="15e45-129">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e45-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15e45-130">See Also</span></span>  
 [<span data-ttu-id="15e45-131">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="15e45-131">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)  
  
  
