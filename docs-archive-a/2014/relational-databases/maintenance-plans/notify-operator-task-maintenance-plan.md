---
title: Tarea Notificar al operador (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.notifyoperator.f1
helpviewer_keywords:
- Notify Operator Task dialog box
ms.assetid: 39c0797c-ad2b-4591-85c9-a23a7f902895
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb59622c2a42de67193c75d545a6b8a2a08863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674110"
---
# <a name="notify-operator-task-maintenance-plan"></a><span data-ttu-id="2e2db-102">Tarea Notificar al operador (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="2e2db-102">Notify Operator Task (Maintenance Plan)</span></span>
  <span data-ttu-id="2e2db-103">Utilice el cuadro de diálogo **Tarea Notificar al operador** para agregar una notificación automática a este plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="2e2db-103">Use the **Notify Operators Task** dialog to add an automatic notification to this maintenance plan.</span></span> <span data-ttu-id="2e2db-104">Para usar esta tarea, Correo electrónico de base de datos debe estar habilitado y configurado adecuadamente con MSDB como base de datos host de correo y debe tener un operador del Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una dirección de correo electrónico válida.</span><span class="sxs-lookup"><span data-stu-id="2e2db-104">To use this task you must have Database Mail enabled and properly configured with MSDB as a Mail Host Database, and have a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator with a valid e-mail address.</span></span>  
  
 <span data-ttu-id="2e2db-105">Esta tarea usa el procedimiento almacenado sp_notify_operator.</span><span class="sxs-lookup"><span data-stu-id="2e2db-105">This task uses the sp_notify_operator stored procedure.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2e2db-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="2e2db-106">Options</span></span>  
 <span data-ttu-id="2e2db-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="2e2db-107">**Connection**</span></span>  
 <span data-ttu-id="2e2db-108">Seleccione la conexión al servidor que va a utilizar para la realización de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="2e2db-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="2e2db-109">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="2e2db-109">**New**</span></span>  
 <span data-ttu-id="2e2db-110">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="2e2db-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="2e2db-111">El cuadro de diálogo **Nueva conexión** se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="2e2db-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="2e2db-112">**Operadores a los que notificar**</span><span class="sxs-lookup"><span data-stu-id="2e2db-112">**Operators to notify**</span></span>  
 <span data-ttu-id="2e2db-113">Especifica el destinatario del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2e2db-113">Specify the recipient of the e-mail.</span></span>  
  
 <span data-ttu-id="2e2db-114">**Asunto del mensaje de notificación**</span><span class="sxs-lookup"><span data-stu-id="2e2db-114">**Notification message subject**</span></span>  
 <span data-ttu-id="2e2db-115">Especifica el texto que se va a incluir en la línea de asunto del mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="2e2db-115">Specify the text to include in the notification message subject line.</span></span>  
  
 <span data-ttu-id="2e2db-116">**Cuerpo del mensaje de notificación**</span><span class="sxs-lookup"><span data-stu-id="2e2db-116">**Notification message body**</span></span>  
 <span data-ttu-id="2e2db-117">Especifica el texto que se va a incluir en el cuerpo del mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="2e2db-117">Specify the text to include in the notification message body.</span></span>  
  
 <span data-ttu-id="2e2db-118">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="2e2db-118">**View T-SQL**</span></span>  
 <span data-ttu-id="2e2db-119">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="2e2db-119">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e2db-120">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="2e2db-120">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="2e2db-121">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="2e2db-121">New Connection Dialog Box</span></span>  
 <span data-ttu-id="2e2db-122">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="2e2db-122">**Connection name**</span></span>  
 <span data-ttu-id="2e2db-123">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="2e2db-123">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="2e2db-124">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="2e2db-124">**Select or enter a server name**</span></span>  
 <span data-ttu-id="2e2db-125">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="2e2db-125">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="2e2db-126">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="2e2db-126">**Refresh**</span></span>  
 <span data-ttu-id="2e2db-127">Actualiza la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="2e2db-127">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="2e2db-128">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="2e2db-128">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="2e2db-129">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="2e2db-129">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="2e2db-130">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="2e2db-130">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="2e2db-131">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] con autenticación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="2e2db-131">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="2e2db-132">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="2e2db-132">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="2e2db-133">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] mediante autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e2db-133">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="2e2db-134">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2e2db-134">This option is not available.</span></span>  
  
 <span data-ttu-id="2e2db-135">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="2e2db-135">**User name**</span></span>  
 <span data-ttu-id="2e2db-136">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="2e2db-136">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="2e2db-137">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2e2db-137">This option is not available.</span></span>  
  
 <span data-ttu-id="2e2db-138">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="2e2db-138">**Password**</span></span>  
 <span data-ttu-id="2e2db-139">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="2e2db-139">Provide a password to use when authenticating.</span></span> <span data-ttu-id="2e2db-140">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2e2db-140">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e2db-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e2db-141">See Also</span></span>  
 <span data-ttu-id="2e2db-142">[Correo electrónico de base de datos](../database-mail/database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="2e2db-142">[Database Mail](../database-mail/database-mail.md) </span></span>  
 [<span data-ttu-id="2e2db-143">sp_notify_operator &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2e2db-143">sp_notify_operator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-notify-operator-transact-sql)  
  
  
