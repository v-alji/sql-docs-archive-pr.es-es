---
title: Establecer la cuenta de inicio del servicio para Agente SQL Server (Administrador de configuración de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- startup accounts [SQL Server]
- service startup accounts [SQL Server Agent]
ms.assetid: 46ffe818-ebb5-43a0-840b-923f219a2472
author: stevestein
ms.author: sstein
ms.openlocfilehash: 63e5ba7c24f1aa1a3f79f80e5ca28c02a0cd5812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745619"
---
# <a name="set-the-service-startup-account-for-sql-server-agent-sql-server-configuration-manager"></a><span data-ttu-id="1306d-102">Establecer la cuenta de inicio del servicio para el Agente SQL Server (Administrador de configuración de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1306d-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="1306d-103">La cuenta de inicio del servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] define la cuenta de Windows en la que se ejecuta el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], así como sus permisos de red.</span><span class="sxs-lookup"><span data-stu-id="1306d-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account defines the Windows account that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs as, as well as its network permissions.</span></span> <span data-ttu-id="1306d-104">En este tema se describe cómo establecer la cuenta del servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1306d-104">This topic describes how to set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1306d-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="1306d-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1306d-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="1306d-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1306d-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="1306d-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1306d-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1306d-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="1306d-109">Para establecer la cuenta de inicio de servicio para el Agente SQL Server utilizando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1306d-109">To set the Service Startup Account for SQL Server Agent using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1306d-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1306d-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1306d-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="1306d-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1306d-112">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ya no necesita que la cuenta de inicio del servicio sea miembro del grupo Administradores de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1306d-112">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer requires that the service startup account be a member of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Administrators group.</span></span> <span data-ttu-id="1306d-113">Sin embargo, la cuenta de inicio de servicio para el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe ser miembro del rol fijo de servidor sysadmin de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1306d-113">However, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account must be a member of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sysadmin fixed server role.</span></span> <span data-ttu-id="1306d-114">La cuenta también debe ser miembro del rol TargetServersRole de la base de datos msdb en el servidor maestro si se usa el procesamiento de trabajos multiservidor.</span><span class="sxs-lookup"><span data-stu-id="1306d-114">The account must also be a member of the msdb database role TargetServersRole on the master server if multiserver job processing is used.</span></span>  
  
-   <span data-ttu-id="1306d-115">El Explorador de objetos solo muestra el nodo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se tiene permiso para usarlo.</span><span class="sxs-lookup"><span data-stu-id="1306d-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1306d-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1306d-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1306d-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="1306d-117">Permissions</span></span>  
 <span data-ttu-id="1306d-118">Para realizar sus funciones, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] el agente debe configurarse para utilizar las credenciales de una cuenta que sea miembro del `sysadmin` rol fijo de servidor en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1306d-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the `sysadmin` fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1306d-119">La cuenta debe tener los siguientes permisos de Windows:</span><span class="sxs-lookup"><span data-stu-id="1306d-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="1306d-120">Iniciar sesión como servicio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="1306d-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="1306d-121">Reemplazar un token de nivel de proceso (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="1306d-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="1306d-122">Omitir la comprobación transversal (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="1306d-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="1306d-123">Ajustar las cuotas de memoria de un proceso (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="1306d-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="1306d-124">Para obtener más información acerca de los permisos de Windows necesarios para la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuenta de servicio del agente, consulte [seleccionar una cuenta para el servicio de Agente SQL Server](select-an-account-for-the-sql-server-agent-service.md) y [configurar los permisos y las cuentas de servicio de Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1306d-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1306d-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1306d-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-service-startup-account-for-sql-server-agent"></a><span data-ttu-id="1306d-126">Para establecer la cuenta de inicio de servicio para el Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="1306d-126">To set the Service Startup Account for SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="1306d-127">En **Servidores registrados**, haga clic en el signo más para expandir **Motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1306d-127">In **Registered Servers**, click the plus sign to expand **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="1306d-128">Haga clic en el signo más para expandir la carpeta **Grupos de servidores locales** .</span><span class="sxs-lookup"><span data-stu-id="1306d-128">Click the plus sign to expand the **Local Server Groups** folder.</span></span>  
  
3.  <span data-ttu-id="1306d-129">Haga clic con el botón derecho en la instancia de servidor donde quiera instalar la cuenta de inicio de servicio y seleccione **Administrador de configuración de SQL Server...**.</span><span class="sxs-lookup"><span data-stu-id="1306d-129">Right-click the server instance where you want set up the Service Startup Account, and select **SQL Server Configuration Manager...**.</span></span>  
  
4.  <span data-ttu-id="1306d-130">En el cuadro de diálogo **Control de cuentas de usuario**, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="1306d-130">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="1306d-131">En el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , en el panel de la consola, seleccione **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="1306d-131">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, select **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="1306d-132">En el panel de detalles, haga clic con el botón secundario en **Agente SQL Server**_(SERVER_NAME)_, donde *SERVER_NAME* es el nombre de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instancia del agente cuya cuenta de inicio de servicio desea cambiar y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1306d-132">In the details pane, right-click **SQL Server Agent**_(server_name)_, where *server_name* is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance for which you want to change the service startup account, and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="1306d-133">En el cuadro de diálogo **propiedades** de **Agente SQL Server**_(SERVER_NAME)_ , en la pestaña **iniciar sesión** , seleccione una de las opciones siguientes en **iniciar sesión como**:</span><span class="sxs-lookup"><span data-stu-id="1306d-133">In the **SQL Server Agent**_(server_name)_ **Properties** dialog box, in the **Log On** tab, select one of the following options under **Log on as**:</span></span>  
  
    -   <span data-ttu-id="1306d-134">**Cuenta integrada**: seleccione esta opción si los trabajos solo necesitan recursos del servidor local.</span><span class="sxs-lookup"><span data-stu-id="1306d-134">**Built-in account**: select this option if your jobs require resources from the local server only.</span></span> <span data-ttu-id="1306d-135">Para información sobre cómo elegir un tipo de cuenta integrada de Windows, consulte [Seleccionar una cuenta para el servicio del Agente SQL Server](https://msdn.microsoft.com/library/ms191543.aspx).</span><span class="sxs-lookup"><span data-stu-id="1306d-135">For information about how to choose a Windows built-in account type, see [Selecting an Account for SQL Server Agent Service.](https://msdn.microsoft.com/library/ms191543.aspx)</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="1306d-136"> El servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no admite la cuenta del **Servicio local** en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1306d-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service does not support the **Local Service** account in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="1306d-137">**Esta cuenta**: seleccione esta opción si los trabajos necesitan recursos de la red, incluidos recursos de aplicaciones; por ejemplo, si desea reenviar eventos a otros registros de aplicación Windows o si desea notificar a operadores mediante mensajes de correo electrónico o buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="1306d-137">**This account**: select this option if your jobs require resources across the network, including application resources; if you want to forward events to other Windows application logs; or if you want to notify operators through e-mail or pagers.</span></span>  
  
         <span data-ttu-id="1306d-138">Si selecciona esta opción:</span><span class="sxs-lookup"><span data-stu-id="1306d-138">If you select this option:</span></span>  
  
        1.  <span data-ttu-id="1306d-139">En el cuadro **Nombre de cuenta** , escriba la cuenta que se utilizará para ejecutar el Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1306d-139">In the **Account Name** box, enter the account that will be used to run SQL Server Agent.</span></span> <span data-ttu-id="1306d-140">Como alternativa, haga clic en **Examinar** para abrir el cuadro de diálogo **Seleccionar usuarios o grupos** y seleccione la cuenta que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="1306d-140">Alternately, click **Browse** to open the **Select User or Group** dialog box and select the account to use.</span></span>  
  
        2.  <span data-ttu-id="1306d-141">En el cuadro **Contraseña** , escriba la contraseña para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="1306d-141">In the **Password** box, enter the password for the account.</span></span> <span data-ttu-id="1306d-142">Vuelva a escribir la contraseña en el cuadro **Confirmar contraseña** .</span><span class="sxs-lookup"><span data-stu-id="1306d-142">Re-enter the password in the **Confirm password** box.</span></span>  
  
8.  <span data-ttu-id="1306d-143">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="1306d-143">Click **OK**.</span></span>  
  
9. <span data-ttu-id="1306d-144">En Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , haga clic en el botón **Cerrar** .</span><span class="sxs-lookup"><span data-stu-id="1306d-144">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, click the **Close** button.</span></span>  
  
  
