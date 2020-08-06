---
title: Tarea Ejecutar trabajo del Agente SQL Server (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.executejob.f1
helpviewer_keywords:
- Execute SQL Server Agent Job Task dialog box
ms.assetid: 4ed75956-ebb8-4d8c-9c16-fc0eb00bd3a0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b997d5144b113102ba0ed2d9d1df59b6707acbee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675349"
---
# <a name="execute-sql-server-agent-job-task-maintenance-plan"></a><span data-ttu-id="f2de5-102">Tarea Ejecutar trabajo del Agente SQL Server (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="f2de5-102">Execute SQL Server Agent Job Task (Maintenance Plan)</span></span>
  <span data-ttu-id="f2de5-103">Utilice el cuadro de diálogo **Tarea Ejecutar trabajo del Agente SQL Server** para ejecutar trabajos del Agente Microsoft SQL Server dentro de un plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="f2de5-103">Use the **Execute SQL Server Agent Job Task** dialog to execute Microsoft SQL Server Agent jobs within a maintenance plan.</span></span> <span data-ttu-id="f2de5-104">Esta opción no estará disponible si no tiene trabajos del Agente SQL Server en la conexión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f2de5-104">This option will not be available if you have no SQL Server Agent jobs on the selected connection.</span></span>  
  
 <span data-ttu-id="f2de5-105">Esta tarea usa la instrucción **.sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="f2de5-105">This task uses the **.sp_start_job** statement.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f2de5-106">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f2de5-106">UI element list</span></span>  
 <span data-ttu-id="f2de5-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="f2de5-107">**Connection**</span></span>  
 <span data-ttu-id="f2de5-108">Seleccione la conexión al servidor que va a utilizar para la realización de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="f2de5-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="f2de5-109">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="f2de5-109">**New**</span></span>  
 <span data-ttu-id="f2de5-110">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="f2de5-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="f2de5-111">El cuadro de diálogo **Nueva conexión** se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="f2de5-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="f2de5-112">**Trabajos del Agente SQL Server disponibles**</span><span class="sxs-lookup"><span data-stu-id="f2de5-112">**Available SQL Agent jobs**</span></span>  
 <span data-ttu-id="f2de5-113">Seleccione el trabajo que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="f2de5-113">Select the job to execute.</span></span> <span data-ttu-id="f2de5-114">La cuadrícula proporciona el **Nombre del trabajo** y la **Descripción** para identificar los trabajos.</span><span class="sxs-lookup"><span data-stu-id="f2de5-114">The grid provides the **Job name** and **Description** to identify the jobs.</span></span>  
  
 <span data-ttu-id="f2de5-115">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="f2de5-115">**View T-SQL**</span></span>  
 <span data-ttu-id="f2de5-116">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="f2de5-116">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2de5-117">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="f2de5-117">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="f2de5-118">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="f2de5-118">New Connection Dialog Box</span></span>  
 <span data-ttu-id="f2de5-119">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="f2de5-119">**Connection name**</span></span>  
 <span data-ttu-id="f2de5-120">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="f2de5-120">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="f2de5-121">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="f2de5-121">**Select or enter a server name**</span></span>  
 <span data-ttu-id="f2de5-122">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="f2de5-122">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="f2de5-123">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="f2de5-123">**Refresh**</span></span>  
 <span data-ttu-id="f2de5-124">Actualiza la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="f2de5-124">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="f2de5-125">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="f2de5-125">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="f2de5-126">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f2de5-126">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="f2de5-127">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="f2de5-127">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="f2de5-128">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] con autenticación de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="f2de5-128">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="f2de5-129">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="f2de5-129">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="f2de5-130">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] mediante autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2de5-130">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="f2de5-131">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f2de5-131">This option is not available.</span></span>  
  
 <span data-ttu-id="f2de5-132">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="f2de5-132">**User name**</span></span>  
 <span data-ttu-id="f2de5-133">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f2de5-133">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="f2de5-134">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f2de5-134">This option is not available.</span></span>  
  
 <span data-ttu-id="f2de5-135">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="f2de5-135">**Password**</span></span>  
 <span data-ttu-id="f2de5-136">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f2de5-136">Provide a password to use when authenticating.</span></span> <span data-ttu-id="f2de5-137">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f2de5-137">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2de5-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2de5-138">See Also</span></span>  
 <span data-ttu-id="f2de5-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f2de5-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span></span>  
 <span data-ttu-id="f2de5-140">[Crear un trabajo](../../ssms/agent/create-a-job.md) </span><span class="sxs-lookup"><span data-stu-id="f2de5-140">[Create a Job](../../ssms/agent/create-a-job.md) </span></span>  
 [<span data-ttu-id="f2de5-141">sp_start_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f2de5-141">sp_start_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql)  
  
  
