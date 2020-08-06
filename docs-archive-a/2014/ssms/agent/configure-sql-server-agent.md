---
title: Configurar el Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, configuring
- accounts [SQL Server], SQL Server Agent
- SQL Server Agent, permissions
- security [SQL Server], SQL Server Agent
ms.assetid: 2e361a62-9e92-4fcd-80d7-d6960f127900
author: stevestein
ms.author: sstein
ms.openlocfilehash: 81c78faf733fac5ffb9a6e74dbf03f8caaff03d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672358"
---
# <a name="configure-sql-server-agent"></a><span data-ttu-id="669ab-102">Configure SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="669ab-102">Configure SQL Server Agent</span></span>
  <span data-ttu-id="669ab-103">En este tema se describe cómo especificar algunas opciones de configuración para el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durante la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="669ab-103">This topic describes how to specify some configuration options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent during installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="669ab-104">El conjunto completo de opciones de configuración del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] solo está disponible dentro de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], Objetos de administración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SMO) o los procedimientos almacenados del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="669ab-104">The full set of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent configuration options is only available within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO), or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures.</span></span>  
  
 <span data-ttu-id="669ab-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="669ab-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="669ab-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="669ab-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="669ab-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="669ab-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="669ab-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="669ab-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="669ab-109">Para configurar el Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="669ab-109">To configure SQL Server Agent</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="669ab-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="669ab-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="669ab-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="669ab-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="669ab-112">Haga clic en el **Agente SQL Server** en el Explorador de objetos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para administrar trabajos, operadores, alertas y el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="669ab-112">Click **SQL Server Agent** in Object Explorer of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to administer jobs, operators, alerts, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="669ab-113">No obstante, el Explorador de objetos solo muestra el nodo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si tiene permiso para utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="669ab-113">However, Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="669ab-114">El reinicio automático no debe habilitarse para el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o el servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en las instancias de clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="669ab-114">Auto-restart should not be enabled for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on failover cluster instances.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="669ab-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="669ab-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="669ab-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="669ab-116">Permissions</span></span>  
 <span data-ttu-id="669ab-117">Para realizar sus funciones, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe configurarse de modo que use las credenciales de una cuenta que sea miembro del rol fijo de servidor **sysadmin** en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="669ab-117">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="669ab-118">La cuenta debe tener los siguientes permisos de Windows:</span><span class="sxs-lookup"><span data-stu-id="669ab-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="669ab-119">Iniciar sesión como servicio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="669ab-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="669ab-120">Reemplazar un token de nivel de proceso (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="669ab-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="669ab-121">Omitir la comprobación transversal (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="669ab-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="669ab-122">Ajustar las cuotas de memoria de un proceso (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="669ab-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="669ab-123">Para obtener más información acerca de los permisos de Windows necesarios para la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuenta de servicio del agente, consulte [seleccionar una cuenta para el servicio de Agente SQL Server](select-an-account-for-the-sql-server-agent-service.md) y [configurar los permisos y las cuentas de servicio de Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="669ab-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="669ab-124">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="669ab-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent"></a><span data-ttu-id="669ab-125">Para configurar el Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="669ab-125">To configure SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="669ab-126">Haga clic en el botón **Inicio** y después, en el menú **Inicio**  , haga clic en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="669ab-126">Click the **Start** button, and then, on the **Start**  menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="669ab-127">En el Panel de control, haga clic en **Sistema y seguridad**, haga clic en **Herramientas administrativas**y seleccione **Directiva de seguridad local**.</span><span class="sxs-lookup"><span data-stu-id="669ab-127">In Control Panel, click **System and Security**, click **Administrative Tools**, and then select **Local Security Policy**.</span></span>  
  
3.  <span data-ttu-id="669ab-128">En Directiva de seguridad local, haga clic en las comillas angulares para expandir la carpeta **Directivas locales** y, a continuación, haga clic en la carpeta **Asignación de derechos de usuario** .</span><span class="sxs-lookup"><span data-stu-id="669ab-128">In Local Security Policy, click the chevron to expand the **Local Policies** folder, and then click the **User Rights Assignment** folder.</span></span>  
  
4.  <span data-ttu-id="669ab-129">Haga clic con el botón derecho en un permiso que desee configurar para su uso con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="669ab-129">Right-click a permission that you want to configure for use with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="669ab-130">En el cuadro de diálogo de propiedades del permiso, compruebe que se muestra la cuenta con la que se ejecuta el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="669ab-130">In the permission's properties dialog box, verify that the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs is listed.</span></span> <span data-ttu-id="669ab-131">Si no aparece, haga clic en **Agregar usuario o grupo**, escriba la cuenta bajo la que se ejecuta el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el cuadro de diálogo **Seleccionar usuarios, equipos, cuentas de servicio o grupos** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="669ab-131">If not, click **Add User or Group**, enter the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs in the **Select Users, Computers, Service Accounts, or Groups** dialog box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="669ab-132">Repita el proceso para cada permiso que desee agregar para el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="669ab-132">Repeat for each permission that you want to add to run with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="669ab-133">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="669ab-133">When finished, click **OK**.</span></span>  
  
  
