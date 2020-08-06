---
title: Crear un servidor de administración central y un grupo
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- configuration server
ms.assetid: da265482-3953-440a-ac23-0ab7e42a55eb
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f53b75966a14dbc6fd6cdc9bea0929ccac7780c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743882"
---
# <a name="create-a-central-management-server-and-server-group-sql-server-management-studio"></a><span data-ttu-id="56de7-102">Crear un servidor de administración central y un grupo de servidores (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="56de7-102">Create a Central Management Server and Server Group (SQL Server Management Studio)</span></span>
  <span data-ttu-id="56de7-103">En este tema se describe cómo designar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como servidor de administración central de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56de7-103">This topic describes how to designate an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a central management server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="56de7-104">Los servidores de administración central almacenan una lista de instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se organizan en uno o varios grupos de este tipo de servidores.</span><span class="sxs-lookup"><span data-stu-id="56de7-104">Central management servers store a list of instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is organized into one or more central management server groups.</span></span> <span data-ttu-id="56de7-105">Las acciones que se llevan a cabo mediante un servidor de administración central actúan en todos los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="56de7-105">Actions that are taken by using a central management server group act on all servers in the server group.</span></span> <span data-ttu-id="56de7-106">Esto incluye la conexión a los servidores mediante el Explorador de objetos y la ejecución de instrucciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] y de directivas de administración basada en directivas en varios servidores al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="56de7-106">This includes connecting to servers by using Object Explorer and executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and Policy-Based Management policies on multiple servers at the same time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56de7-107">Las versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] no se pueden designar como servidores de administración central.</span><span class="sxs-lookup"><span data-stu-id="56de7-107">Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] cannot be designated as a central management server.</span></span>  
  
 <span data-ttu-id="56de7-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="56de7-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="56de7-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="56de7-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="56de7-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="56de7-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="56de7-111">**Para crear un servidor de administración central y un grupo de servidores, usando:**</span><span class="sxs-lookup"><span data-stu-id="56de7-111">**To create a Central Management Server and Server Group, using:**</span></span>  
  
     [<span data-ttu-id="56de7-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="56de7-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="56de7-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="56de7-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="56de7-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="56de7-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="56de7-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="56de7-115">Permissions</span></span>  
 <span data-ttu-id="56de7-116">Dos roles de base de datos en la base de datos msdb conceden acceso a los servidores de administración central.</span><span class="sxs-lookup"><span data-stu-id="56de7-116">Two database roles in the msdb database grant access to central management servers.</span></span> <span data-ttu-id="56de7-117">Solo los miembros del rol ServerGroupAdministratorRole pueden administrar el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="56de7-117">Only members of the ServerGroupAdministratorRole role can manage the central management server.</span></span> <span data-ttu-id="56de7-118">La pertenencia al rol ServerGroupReaderRole es necesaria para conectarse a un servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="56de7-118">Membership in the ServerGroupReaderRole role is required to connect to a central management server.</span></span>  
  
 <span data-ttu-id="56de7-119">Dado que las conexiones que mantiene un servidor de administración central se ejecutan en el contexto del usuario, si se usara la autenticación de Windows los permisos vigentes en los servidores registrados podrían variar.</span><span class="sxs-lookup"><span data-stu-id="56de7-119">Because the connections that are maintained by a central management server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="56de7-120">Por ejemplo, el usuario podría ser miembro del rol fijo de servidor sysadmin en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, pero tener permisos limitados en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span><span class="sxs-lookup"><span data-stu-id="56de7-120">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="56de7-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="56de7-121">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="56de7-122">Los procedimientos siguientes describen cómo realizar los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="56de7-122">The following procedures describe how to perform the following steps.</span></span>  
  
1.  <span data-ttu-id="56de7-123">Cree un servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="56de7-123">Create a central management server.</span></span>  
  
2.  <span data-ttu-id="56de7-124">Agregue uno o varios grupos de servidores al servidor de administración central y uno o más servidores registrados a los grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="56de7-124">Add one or more server groups to the central management server and add one or more registered servers to the server groups.</span></span>  
  
#### <a name="create-a-central-management-server"></a><span data-ttu-id="56de7-125">Crear un servidor de administración central</span><span class="sxs-lookup"><span data-stu-id="56de7-125">Create a central management server</span></span>  
  
1.  <span data-ttu-id="56de7-126">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Ver** , haga clic en **Servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="56de7-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="56de7-127">En Servidores registrados, expanda **Motor de base de datos**, haga clic con el botón derecho en **Servidores de administración central**y, después, haga clic en **Registrar servidor de administración central**.</span><span class="sxs-lookup"><span data-stu-id="56de7-127">In Registered Servers, expand **Database Engine**, right-click **Central Management Servers**, and then  click **Register Central Management Server**.</span></span>  
  
3.  <span data-ttu-id="56de7-128">En el cuadro de diálogo **Nuevo registro de servidor** , seleccione la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que quiera que se convierta en el servidor de administración central en la lista desplegable de servidores.</span><span class="sxs-lookup"><span data-stu-id="56de7-128">In the **New Server Registration** dialog box, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to become the central management server from the drop-down list of servers.</span></span> <span data-ttu-id="56de7-129">Utilice la autenticación de Windows para el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="56de7-129">You must use Windows Authentication for the central management server.</span></span>  
  
4.  <span data-ttu-id="56de7-130">En **Servidor registrado**, escriba un nombre de servidor y una descripción opcional.</span><span class="sxs-lookup"><span data-stu-id="56de7-130">In **Registered Server**, enter a server name and optional description.</span></span>  
  
5.  <span data-ttu-id="56de7-131">En la pestaña **Propiedades de conexión** , revise o modifique las propiedades de conexión y red.</span><span class="sxs-lookup"><span data-stu-id="56de7-131">From the **Connection Properties** tab, review or modifiy the network  and connection properties.</span></span> <span data-ttu-id="56de7-132">Para obtener más información, vea [Conectar al servidor &#40;página Propiedades de conexión del motor de base de datos&#41;](../f1-help/connect-to-server-connection-properties-page-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="56de7-132">For more information, see [Connect to Server &#40;Connection Properties Page&#41; Database Engine](../f1-help/connect-to-server-connection-properties-page-database-engine.md)</span></span>  
  
6.  <span data-ttu-id="56de7-133">Haga clic en **Probar**para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="56de7-133">Click **Test**, to test the connection.</span></span>  
  
7.  <span data-ttu-id="56de7-134">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="56de7-134">Click **Save**.</span></span> <span data-ttu-id="56de7-135">La instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aparecerá en la carpeta de **Servidores de administración central** .</span><span class="sxs-lookup"><span data-stu-id="56de7-135">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will appear under the **Central Management Servers** folder.</span></span>  
  
#### <a name="create-a-new-server-group-and-add-servers-to-the-group"></a><span data-ttu-id="56de7-136">Crear un nuevo grupo de servidores y agregar servidores el grupo</span><span class="sxs-lookup"><span data-stu-id="56de7-136">Create a new server group and add servers to the group</span></span>  
  
1.  <span data-ttu-id="56de7-137">En **Servidores registrados**, expanda **Servidores de administración central**.</span><span class="sxs-lookup"><span data-stu-id="56de7-137">From **Registered Servers**, expand **Central Management Servers**.</span></span> <span data-ttu-id="56de7-138">Haga clic con el botón derecho en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agregada en el procedimiento anterior y seleccione **Nuevo grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="56de7-138">Right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] added in the procedure above and select **New Server Group**.</span></span>  
  
2.  <span data-ttu-id="56de7-139">En **Propiedades de nuevo grupo de servidores**, escriba un nombre de grupo y una descripción opcional.</span><span class="sxs-lookup"><span data-stu-id="56de7-139">In **New Server Group Properties**, enter a group name and optional description.</span></span>  
  
3.  <span data-ttu-id="56de7-140">En **Servidores registrados**, haga clic con el botón derecho en el grupo de servidores y haga clic en **Nuevo registro de servidor**.</span><span class="sxs-lookup"><span data-stu-id="56de7-140">From **Registered Servers**, right-click the server group and click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="56de7-141">En Nuevo registro de servidor, seleccione una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56de7-141">From New Server Registration, select an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="56de7-142">Para obtener más información, vea [Crear un servidor registrado &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="56de7-142">For more information, see [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span></span> <span data-ttu-id="56de7-143">Agregue más servidores según corresponda.</span><span class="sxs-lookup"><span data-stu-id="56de7-143">Add more servers as appropriate.</span></span>  
  
#### <a name="to-execute-queries-against-several-configuration-targets-at-the-same-time"></a><span data-ttu-id="56de7-144">Para ejecutar al mismo tiempo consultas con varios destinos de configuración</span><span class="sxs-lookup"><span data-stu-id="56de7-144">To execute queries against several configuration targets at the same time</span></span>  
  
-   <span data-ttu-id="56de7-145">Después de crear un servidor de administración central, uno o varios grupos de servidores, y uno o varios servidores registrados, puede ejecutar al mismo tiempo las consultas con un grupo entero.</span><span class="sxs-lookup"><span data-stu-id="56de7-145">After you create a central management server, one or more server groups, and one or more registered servers, you can execute queries against a whole group at the same time.</span></span> <span data-ttu-id="56de7-146">Para obtener más información sobre cómo ejecutar instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] en los servidores de un grupo de servidores al mismo tiempo, vea [Ejecutar instrucciones con varios servidores simultáneamente &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span><span class="sxs-lookup"><span data-stu-id="56de7-146">For more information about how to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on the servers in a server group at the same time, see [Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56de7-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56de7-147">See Also</span></span>  
 [<span data-ttu-id="56de7-148">Administrar varios servidores mediante Servidores de administración central</span><span class="sxs-lookup"><span data-stu-id="56de7-148">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
