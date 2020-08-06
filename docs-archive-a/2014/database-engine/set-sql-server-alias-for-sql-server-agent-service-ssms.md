---
title: Establecer un alias de SQL Server para el servicio Agente SQL Server (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], creating
- SQL Server Agent, aliases
ms.assetid: 02d6295d-ab52-44f0-8f1b-f3910a507d8f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b178d91a47d907b182ef7962b98c7f22d4454094
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663084"
---
# <a name="set-a-sql-server-alias-for-the-sql-server-agent-service-sql-server-management-studio"></a><span data-ttu-id="11ed3-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="11ed3-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span></span>
  <span data-ttu-id="11ed3-103">En este tema se describe cómo establecer un [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que el agente lo use para conectarse a [!INCLUDE[ssDE](../includes/ssde-md.md)] mediante [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11ed3-103">This topic describes how to set a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to use to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="11ed3-104">De manera predeterminada, el servicio del Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se conecta a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a través de canalizaciones con nombre, mediante nombres de servidores dinámicos que no requieren ninguna configuración adicional del cliente.</span><span class="sxs-lookup"><span data-stu-id="11ed3-104">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] over named pipes by using dynamic server names that require no additional client configuration.</span></span> <span data-ttu-id="11ed3-105">Solo es necesario configurar un alias de conexión de servidor si no se utiliza el transporte de red predeterminado o si se va a conectar a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a la escucha en una canalización con nombre alternativa.</span><span class="sxs-lookup"><span data-stu-id="11ed3-105">You need to configure a server connection alias only if you are not using the default network transport or if you are connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="11ed3-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="11ed3-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="11ed3-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="11ed3-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="11ed3-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="11ed3-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="11ed3-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="11ed3-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="11ed3-110">Para establecer un alias de SQL Server para el servicio del Agente SQL Server utilizando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="11ed3-110">To set a SQL Server Alias for the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="11ed3-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="11ed3-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="11ed3-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="11ed3-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="11ed3-113">no funcionará correctamente si no se selecciona un alias que haga referencia a la instancia local de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11ed3-113">Agent will not work correctly unless you select an alias that refers to the local instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="11ed3-114">El Explorador de objetos solo muestra el nodo del Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] si se tiene permiso para usarlo.</span><span class="sxs-lookup"><span data-stu-id="11ed3-114">Object Explorer only displays the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="11ed3-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="11ed3-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="11ed3-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="11ed3-116">Permissions</span></span>  
 <span data-ttu-id="11ed3-117">Para realizar sus funciones, el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] debe configurarse de modo que use las credenciales de una cuenta que sea miembro del rol fijo de servidor **sysadmin** en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11ed3-117">To perform its functions, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="11ed3-118">La cuenta debe tener los siguientes permisos de Windows:</span><span class="sxs-lookup"><span data-stu-id="11ed3-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="11ed3-119">Iniciar sesión como servicio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="11ed3-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="11ed3-120">Reemplazar un token de nivel de proceso (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="11ed3-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="11ed3-121">Omitir la comprobación transversal (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="11ed3-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="11ed3-122">Ajustar las cuotas de memoria de un proceso (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="11ed3-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="11ed3-123">Para obtener más información acerca de los permisos de Windows necesarios para la [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cuenta de servicio del agente, consulte [seleccionar una cuenta para el servicio de Agente SQL Server](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) y [configurar los permisos y las cuentas de servicio de Windows](configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="11ed3-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="11ed3-124">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="11ed3-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-sql-server-alias-for-the-sql-server-agent-service"></a><span data-ttu-id="11ed3-125">Para establecer un alias de SQL Server para servicio del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="11ed3-125">To set a SQL Server Alias for the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="11ed3-126">En el **Explorador de objetos**, conéctese a una instancia de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="11ed3-126">In the **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="11ed3-127">Haga clic con el botón derecho en **Agente SQL Server**y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="11ed3-127">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="11ed3-128">En el cuadro de diálogo **propiedades de Agente SQL Server**_Server_name_ , en **seleccionar una página**, seleccione **conexión**y</span><span class="sxs-lookup"><span data-stu-id="11ed3-128">In the **SQL Server Agent Properties**_server_name_ dialog box, under **Select a page**, select **Connection**, and</span></span>  
  
4.  <span data-ttu-id="11ed3-129">En el cuadro de **Servidor de host local del alias** , escriba el alias de servidor al que debe conectarse el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11ed3-129">In the **Alias local host server** box, type the alias of the server to which [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should connect.</span></span>  
  
5.  <span data-ttu-id="11ed3-130">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="11ed3-130">Click **OK**.</span></span>  
  
  