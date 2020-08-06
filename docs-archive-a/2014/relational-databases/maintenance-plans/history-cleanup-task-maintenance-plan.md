---
title: Tarea Limpieza de historial (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.historycleanup.f1
helpviewer_keywords:
- History Cleanup Task dialog box
ms.assetid: 66bb6c39-958c-4053-a27f-b1118d2567f5
ms.reviewer: ''
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 03ff35b14fc13d2b4446b15501114489b52c421e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675348"
---
# <a name="history-cleanup-task-maintenance-plan"></a><span data-ttu-id="4d17e-102">Tarea Limpieza de historial (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="4d17e-102">History Cleanup Task (Maintenance Plan)</span></span>

  <span data-ttu-id="4d17e-103">Utilice el cuadro de diálogo **Tarea Limpieza de historial** para descartar la antigua información histórica de las tablas de la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="4d17e-103">Use the **History Cleanup Task** dialog to discard old historical information from tables in the msdb database.</span></span> <span data-ttu-id="4d17e-104">Esta tarea admite la eliminación del historial de copias de seguridad y restauración, del historial de trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y del historial del plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="4d17e-104">This task supports deleting backup and restore history, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job history, and maintenance plan history.</span></span>  
  
 <span data-ttu-id="4d17e-105">Esta instrucción usa las instrucciones **sp_purge_jobhistory** y **sp_delete_backuphistory** .</span><span class="sxs-lookup"><span data-stu-id="4d17e-105">This statement uses the **sp_purge_jobhistory** and **sp_delete_backuphistory** statements.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="4d17e-106">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4d17e-106">UI element list</span></span>  
 <span data-ttu-id="4d17e-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="4d17e-107">**Connection**</span></span>  
 <span data-ttu-id="4d17e-108">Seleccione la conexión al servidor que va a utilizar para la realización de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="4d17e-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="4d17e-109">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="4d17e-109">**New**</span></span>  
 <span data-ttu-id="4d17e-110">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="4d17e-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="4d17e-111">El cuadro de diálogo **Nueva conexión** se describe posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4d17e-111">The **New Connection** dialog box is described later in this topic.</span></span>  
  
 <span data-ttu-id="4d17e-112">**Historial de copias de seguridad y restauración**</span><span class="sxs-lookup"><span data-stu-id="4d17e-112">**Backup and restore history**</span></span>  
 <span data-ttu-id="4d17e-113">Conservar los registros de creación de las copias de seguridad recientes puede ser útil para que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cree un plan de recuperación cuando desee restaurar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="4d17e-113">Retaining records of when recent backups were created can help [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] create a recovery plan when you want to restore a database.</span></span> <span data-ttu-id="4d17e-114">El periodo de conservación debe tener, al menos, la frecuencia de las copias de seguridad completas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4d17e-114">The retention period should be at least the frequency of full database back ups.</span></span>  
  
 <span data-ttu-id="4d17e-115">**Historial de trabajos del Agente SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4d17e-115">**SQL Server Agent Job history**</span></span>  
 <span data-ttu-id="4d17e-116">Este historial puede ser útil para solucionar errores de los trabajos o para determinar las causas de las acciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4d17e-116">This history can help you troubleshoot failed jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="4d17e-117">**Historial del plan de mantenimiento**</span><span class="sxs-lookup"><span data-stu-id="4d17e-117">**Maintenance plan history**</span></span>  
 <span data-ttu-id="4d17e-118">Este historial puede ser útil para solucionar errores de los trabajos del plan de mantenimiento o para determinar las causas de las acciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4d17e-118">This history can help you troubleshoot failed maintenance plan jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="4d17e-119">**Quitar datos históricos anteriores a**</span><span class="sxs-lookup"><span data-stu-id="4d17e-119">**Remove historical data older than**</span></span>  
 <span data-ttu-id="4d17e-120">Especifique la antigüedad de los elementos que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="4d17e-120">Specify age of items that you want to delete.</span></span>  
  
 <span data-ttu-id="4d17e-121">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="4d17e-121">**View T-SQL**</span></span>  
 <span data-ttu-id="4d17e-122">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="4d17e-122">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d17e-123">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="4d17e-123">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="4d17e-124">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="4d17e-124">New Connection Dialog Box</span></span>  
 <span data-ttu-id="4d17e-125">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="4d17e-125">**Connection name**</span></span>  
 <span data-ttu-id="4d17e-126">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="4d17e-126">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="4d17e-127">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="4d17e-127">**Select or enter a server name**</span></span>  
 <span data-ttu-id="4d17e-128">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="4d17e-128">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="4d17e-129">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="4d17e-129">**Refresh**</span></span>  
 <span data-ttu-id="4d17e-130">Actualiza la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="4d17e-130">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="4d17e-131">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="4d17e-131">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="4d17e-132">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4d17e-132">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="4d17e-133">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="4d17e-133">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="4d17e-134">Se conecta a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] de SQL Server con la autenticación de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="4d17e-134">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="4d17e-135">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="4d17e-135">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="4d17e-136">Se conecta a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] de SQL Server utilizando la autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4d17e-136">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="4d17e-137">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="4d17e-137">This option is not available.</span></span>  
  
 <span data-ttu-id="4d17e-138">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="4d17e-138">**User name**</span></span>  
 <span data-ttu-id="4d17e-139">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="4d17e-139">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="4d17e-140">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="4d17e-140">This option is not available.</span></span>  
  
 <span data-ttu-id="4d17e-141">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="4d17e-141">**Password**</span></span>  
 <span data-ttu-id="4d17e-142">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="4d17e-142">Provide a password to use when authenticating.</span></span> <span data-ttu-id="4d17e-143">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="4d17e-143">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d17e-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d17e-144">See Also</span></span>  
 <span data-ttu-id="4d17e-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4d17e-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span></span>  
 [<span data-ttu-id="4d17e-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d17e-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql)  
  
  
