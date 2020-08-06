---
title: Opción Cancel (herramienta de administración de Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: fea376de-307a-4b45-b7e2-37df88f3681a
author: stevestein
ms.author: sstein
ms.openlocfilehash: d132fbf5ce541a2bdab82e44dc55e6fc92df536d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673952"
---
# <a name="cancel-option-distributed-replay-administration-tool"></a><span data-ttu-id="46d0a-102">Opción cancel (herramienta de administración de Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="46d0a-102">Cancel Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="46d0a-103">La [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herramienta de administración de Distributed Replay, `DReplay.exe` , es una herramienta de línea de comandos que puede usar para comunicarse con el controlador de reproducción distribuida.</span><span class="sxs-lookup"><span data-stu-id="46d0a-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="46d0a-104">En este tema se describe la opción de la línea de comandos **cancel** y la sintaxis correspondiente.</span><span class="sxs-lookup"><span data-stu-id="46d0a-104">This topic describes the **cancel** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="46d0a-105">La opción **cancel** cancela la operación actual que se ejecuta en la controladora.</span><span class="sxs-lookup"><span data-stu-id="46d0a-105">The **cancel** option cancels the current operation that is running on the controller.</span></span>

 <span data-ttu-id="46d0a-106">![Icono de vínculo de tema](../../database-engine/media/topic-link.gif "Icono de vínculo de tema") Para más información sobre las convenciones de sintaxis que se usan con la sintaxis de la herramienta de administración, consulte [Convenciones de sintaxis de Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="46d0a-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="46d0a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46d0a-107">Syntax</span></span>

```

dreplay cancel [-mcontroller] [-q] 
```

#### <a name="parameters"></a><span data-ttu-id="46d0a-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46d0a-108">Parameters</span></span>
 <span data-ttu-id="46d0a-109">**-m** *Controller* el nombre del equipo del controlador.</span><span class="sxs-lookup"><span data-stu-id="46d0a-109">**-m** *controller* The computer name of the controller.</span></span> <span data-ttu-id="46d0a-110">Puede utilizar "`localhost`" o "`.`" para hacer referencia al equipo local.</span><span class="sxs-lookup"><span data-stu-id="46d0a-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="46d0a-111">Si no se especifica el parámetro **-m** , se usará el equipo local.</span><span class="sxs-lookup"><span data-stu-id="46d0a-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="46d0a-112">**-q** Modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="46d0a-112">**-q** Quiet mode.</span></span> <span data-ttu-id="46d0a-113">No solicita confirmación.</span><span class="sxs-lookup"><span data-stu-id="46d0a-113">Does not prompt for confirmation.</span></span>

 <span data-ttu-id="46d0a-114">El parámetro **-q** es opcional.</span><span class="sxs-lookup"><span data-stu-id="46d0a-114">The **-q** parameter is optional.</span></span>

## <a name="examples"></a><span data-ttu-id="46d0a-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="46d0a-115">Examples</span></span>
 <span data-ttu-id="46d0a-116">En el ejemplo siguiente se envía una solicitud de cancelación en modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="46d0a-116">In the following example, a cancel request is submitted in quiet mode.</span></span> <span data-ttu-id="46d0a-117">El valor `localhost` indica que el servicio del controlador se está ejecutando en el mismo equipo que la herramienta de administración.</span><span class="sxs-lookup"><span data-stu-id="46d0a-117">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay cancel -m localhost -q
```

## <a name="permissions"></a><span data-ttu-id="46d0a-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="46d0a-118">Permissions</span></span>
 <span data-ttu-id="46d0a-119">Debe ejecutar la herramienta de administración como un usuario interactivo, como un usuario local o una cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="46d0a-119">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="46d0a-120">Para utilizar una cuenta de usuario local, la herramienta de administración y el controlador se deben estar ejecutando en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="46d0a-120">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="46d0a-121">Para más información, consulte [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="46d0a-121">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="46d0a-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46d0a-122">See Also</span></span>
 [<span data-ttu-id="46d0a-123">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="46d0a-123">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)


