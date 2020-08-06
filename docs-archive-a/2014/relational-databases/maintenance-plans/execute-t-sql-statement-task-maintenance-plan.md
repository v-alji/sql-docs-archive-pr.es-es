---
title: Tarea Ejecutar instrucción T-SQL (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.tsql.f1
helpviewer_keywords:
- Execute T-SQL Statement Task dialog box
ms.assetid: fef3e259-0c47-4f6e-ade0-aee95e3d6c1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63738758ce228a51ab6c75eb11a681eec3b27352
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675350"
---
# <a name="execute-t-sql-statement-task-maintenance-plan"></a><span data-ttu-id="55633-102">Tarea Ejecutar instrucción T-SQL (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="55633-102">Execute T-SQL Statement Task (Maintenance Plan)</span></span>
  <span data-ttu-id="55633-103">Use el cuadro de diálogo **Tarea Ejecutar instrucción T-SQL** para personalizar el plan de mantenimiento agregando las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que quiera a este plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="55633-103">Use the **Execute T-SQL Statement Task** dialog to customize your maintenance plan by adding [!INCLUDE[tsql](../../includes/tsql-md.md)] statements of your choice to this maintenance plan.</span></span>  
  
## <a name="options"></a><span data-ttu-id="55633-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="55633-104">Options</span></span>  
 <span data-ttu-id="55633-105">**Connection**</span><span class="sxs-lookup"><span data-stu-id="55633-105">**Connection**</span></span>  
 <span data-ttu-id="55633-106">Seleccione la conexión al servidor que va a utilizar para la realización de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="55633-106">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="55633-107">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="55633-107">**New**</span></span>  
 <span data-ttu-id="55633-108">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="55633-108">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="55633-109">El cuadro de diálogo **Nueva conexión** se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="55633-109">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="55633-110">**Tiempo de espera de ejecución**</span><span class="sxs-lookup"><span data-stu-id="55633-110">**Execution time out**</span></span>  
 <span data-ttu-id="55633-111">Tiempo (en segundos) de espera de finalización de la tarea.</span><span class="sxs-lookup"><span data-stu-id="55633-111">Time (seconds) to wait for task completion before timing out (terminating task).</span></span>  
  
 <span data-ttu-id="55633-112">**Instrucción T-SQL**</span><span class="sxs-lookup"><span data-stu-id="55633-112">**T-SQL statement**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="55633-113">Instrucciones Transact-SQL que se van a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="55633-113">statements to execute.</span></span>  
  
 <span data-ttu-id="55633-114">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="55633-114">**View T-SQL**</span></span>  
 <span data-ttu-id="55633-115">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="55633-115">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55633-116">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="55633-116">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="55633-117">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="55633-117">New Connection Dialog Box</span></span>  
 <span data-ttu-id="55633-118">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="55633-118">**Connection name**</span></span>  
 <span data-ttu-id="55633-119">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="55633-119">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="55633-120">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="55633-120">**Select or enter a server name**</span></span>  
 <span data-ttu-id="55633-121">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="55633-121">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="55633-122">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="55633-122">**Refresh**</span></span>  
 <span data-ttu-id="55633-123">Actualiza la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="55633-123">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="55633-124">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="55633-124">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="55633-125">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="55633-125">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="55633-126">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="55633-126">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="55633-127">Conéctese a una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con autenticación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="55633-127">Connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="55633-128">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="55633-128">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="55633-129">Se conecta a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55633-129">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="55633-130">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="55633-130">This option is not available.</span></span>  
  
 <span data-ttu-id="55633-131">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="55633-131">**User name**</span></span>  
 <span data-ttu-id="55633-132">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="55633-132">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="55633-133">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="55633-133">This option is not available.</span></span>  
  
 <span data-ttu-id="55633-134">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="55633-134">**Password**</span></span>  
 <span data-ttu-id="55633-135">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="55633-135">Provide a password to use when authenticating.</span></span> <span data-ttu-id="55633-136">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="55633-136">This option is not available.</span></span>  
  
  
