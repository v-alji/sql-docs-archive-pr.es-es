---
title: Opción Status (herramienta de administración de Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: ea89386e-1598-4412-8b37-680d14b2a5b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ce3d07bc357c5f3788fb6f995a43399021b3553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743798"
---
# <a name="status-option-distributed-replay-administration-tool"></a><span data-ttu-id="a93cf-102">Opción Status (herramienta de administración de Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="a93cf-102">Status Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="a93cf-103">La [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herramienta de administración de Distributed Replay, `DReplay.exe` , es una herramienta de línea de comandos que puede usar para comunicarse con el controlador de reproducción distribuida.</span><span class="sxs-lookup"><span data-stu-id="a93cf-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="a93cf-104">En este tema se describe la opción del símbolo del sistema **status** y la sintaxis correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a93cf-104">This topic describes the **status** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="a93cf-105">La opción **status** consulta el controlador y muestra el estado actual.</span><span class="sxs-lookup"><span data-stu-id="a93cf-105">The **status** option queries the controller and displays the current status.</span></span>

 <span data-ttu-id="a93cf-106">![Icono de vínculo de tema](../../database-engine/media/topic-link.gif "Icono de vínculo de tema") Para obtener más información sobre las convenciones de sintaxis que se usan con la sintaxis de la herramienta de administración, vea [Convenciones de sintaxis de Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a93cf-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="a93cf-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a93cf-107">Syntax</span></span>

```

dreplay status [-mcontroller] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="a93cf-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a93cf-108">Parameters</span></span>
 <span data-ttu-id="a93cf-109">*controlador* **-m** especifica el nombre del equipo del controlador.</span><span class="sxs-lookup"><span data-stu-id="a93cf-109">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="a93cf-110">Puede utilizar "`localhost`" o "`.`" para hacer referencia al equipo local.</span><span class="sxs-lookup"><span data-stu-id="a93cf-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="a93cf-111">Si no se especifica el parámetro **-m** , se usará el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a93cf-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="a93cf-112">**-f** *status_interval* especifica la frecuencia (en segundos) con la que se va a mostrar el estado.</span><span class="sxs-lookup"><span data-stu-id="a93cf-112">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="a93cf-113">Si no se especifica el parámetro **-f** , el intervalo predeterminado es de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="a93cf-113">If the **-f** parameter is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="a93cf-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a93cf-114">Examples</span></span>
 <span data-ttu-id="a93cf-115">En el ejemplo siguiente, se muestra el estado actual cada 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="a93cf-115">In the following example, the current status is displayed every 60 seconds.</span></span> <span data-ttu-id="a93cf-116">El valor `localhost` indica que el servicio del controlador se está ejecutando en el mismo equipo que la herramienta de administración.</span><span class="sxs-lookup"><span data-stu-id="a93cf-116">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay status -m localhost -f 60
```

## <a name="permissions"></a><span data-ttu-id="a93cf-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="a93cf-117">Permissions</span></span>
 <span data-ttu-id="a93cf-118">Debe ejecutar la herramienta de administración como un usuario interactivo, como un usuario local o una cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="a93cf-118">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="a93cf-119">Para utilizar una cuenta de usuario local, la herramienta de administración y el controlador se deben estar ejecutando en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="a93cf-119">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="a93cf-120">Para más información, consulte [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="a93cf-120">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a93cf-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a93cf-121">See Also</span></span>
 <span data-ttu-id="a93cf-122">[SQL Server Distributed Replay](sql-server-distributed-replay.md) [depurador de Transact-SQL](../../relational-databases/scripting/transact-sql-debugger.md)</span><span class="sxs-lookup"><span data-stu-id="a93cf-122">[SQL Server Distributed Replay](sql-server-distributed-replay.md) [Transact-SQL Debugger](../../relational-databases/scripting/transact-sql-debugger.md)</span></span>


