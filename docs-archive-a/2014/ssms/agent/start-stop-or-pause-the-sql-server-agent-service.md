---
title: Iniciar, detener o pausar el servicio del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- SQL Server Agent, pausing
- SQL Server Agent, stopping
ms.assetid: c95a9759-dd30-4ab6-9ab0-087bb3bfb97c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2feb6a18c602271b1bec871fbfc9793979b100e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743902"
---
# <a name="start-stop-or-pause-the-sql-server-agent-service"></a><span data-ttu-id="ba9ed-102">Start, Stop, or Pause the SQL Server Agent Service</span><span class="sxs-lookup"><span data-stu-id="ba9ed-102">Start, Stop, or Pause the SQL Server Agent Service</span></span>
  <span data-ttu-id="ba9ed-103">En este tema se describe cómo iniciar, detener o reiniciar el servicio del Agente SQL Server en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba9ed-103">This topic describes how to start, stop, or restart the SQL Server Agent Service in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ba9ed-104">Puede configurar el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que se inicie automáticamente cuando se inicie el sistema operativo o puede iniciarlo manualmente cuando necesite completar trabajos.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-104">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically when the operating system starts, or you can start it manually when you need to complete jobs.</span></span> <span data-ttu-id="ba9ed-105">El servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se puede detener o pausar con el fin de suspender trabajos, notificaciones para los operadores y alertas.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-105">You can stop or pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to suspend jobs, operator notifications, and alerts.</span></span>  
  
 <span data-ttu-id="ba9ed-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="ba9ed-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ba9ed-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="ba9ed-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ba9ed-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ba9ed-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ba9ed-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ba9ed-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="ba9ed-110">Para iniciar, detener o reiniciar el servicio del Agente SQL Server mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ba9ed-110">To start, stop, or restart the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ba9ed-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ba9ed-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ba9ed-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ba9ed-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="ba9ed-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]El agente debe ejecutarse como un servicio con el fin de automatizar las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running as a service in order to automate administrative tasks.</span></span> <span data-ttu-id="ba9ed-114">Para obtener más información, consulte [Configure SQL Server Agent](configure-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="ba9ed-114">For more information, see [Configure SQL Server Agent](configure-sql-server-agent.md).</span></span>  
  
-   <span data-ttu-id="ba9ed-115">El Explorador de objetos solo muestra el nodo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se tiene permiso para usarlo.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ba9ed-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ba9ed-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ba9ed-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="ba9ed-117">Permissions</span></span>  
 <span data-ttu-id="ba9ed-118">Para realizar sus funciones, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe configurarse de modo que use las credenciales de una cuenta que sea miembro del rol fijo de servidor **sysadmin** en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba9ed-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ba9ed-119">La cuenta debe tener los siguientes permisos de Windows:</span><span class="sxs-lookup"><span data-stu-id="ba9ed-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="ba9ed-120">Iniciar sesión como servicio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="ba9ed-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="ba9ed-121">Reemplazar un token de nivel de proceso (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="ba9ed-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="ba9ed-122">Omitir la comprobación transversal (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="ba9ed-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="ba9ed-123">Ajustar las cuotas de memoria de un proceso (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="ba9ed-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="ba9ed-124">Para obtener más información acerca de los permisos de Windows necesarios para la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuenta de servicio del agente, consulte [seleccionar una cuenta para el servicio de Agente SQL Server](select-an-account-for-the-sql-server-agent-service.md) y [configurar los permisos y las cuentas de servicio de Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ba9ed-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ba9ed-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ba9ed-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-stop-or-restart-the-sql-server-agent-service"></a><span data-ttu-id="ba9ed-126">Para iniciar, detener o reiniciar el servicio del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba9ed-126">To start, stop, or restart the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="ba9ed-127">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que desea administrar el servicio del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-127">In **Object Explorer**, click the plus sign to expand the server where you want to manage SQL Server Agent Service.</span></span>  
  
2.  <span data-ttu-id="ba9ed-128">Haga clic con el botón derecho en **Agente SQL Server**y, luego, seleccione **Iniciar**, **Detener**o **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-128">Right-click **SQL Server Agent**, and then select either **Start**, **Stop**, or **Restart**.</span></span>  
  
3.  <span data-ttu-id="ba9ed-129">En el cuadro de diálogo **Control de cuentas de usuario**, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-129">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
4.  <span data-ttu-id="ba9ed-130">Cuando se le pregunte si desea realizar la acción, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-130">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
 <span data-ttu-id="ba9ed-131">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ba9ed-131">For more information, see:</span></span>  
  
-   [<span data-ttu-id="ba9ed-132">Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="ba9ed-132">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
-   [<span data-ttu-id="ba9ed-133">Iniciar automáticamente el Agente SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ba9ed-133">Autostart SQL Server Agent &#40;SQL Server Management Studio&#41;</span></span>](autostart-sql-server-agent-sql-server-management-studio.md)  
  
  
