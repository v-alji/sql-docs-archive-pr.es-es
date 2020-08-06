---
title: Ejecutar instrucciones en varios servidores simultáneamente
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- executing queries against multiple servers
- queries [SQL Server], multiserver
ms.assetid: 197760f3-0a06-43de-8162-69c27d3fbe56
author: markingmyname
ms.author: maghan
ms.openlocfilehash: b94775029a1501d3e894d84ef4a027fc1595dc10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746676"
---
# <a name="execute-statements-against-multiple-servers-simultaneously-sql-server-management-studio"></a><span data-ttu-id="aef43-102">Ejecutar instrucciones con varios servidores simultáneamente (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="aef43-102">Execute Statements Against Multiple Servers Simultaneously (SQL Server Management Studio)</span></span>
  <span data-ttu-id="aef43-103">En este tema se describe cómo consultar al mismo tiempo varios servidores en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]creando un grupo de servidores locales o un Servidor de administración central y uno o varios grupos de servidores, y uno o varios servidores registrados dentro de los grupos, y consultando a continuación el grupo completo.</span><span class="sxs-lookup"><span data-stu-id="aef43-103">This topic describes how to query multiple servers at the same time in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], by creating a local server group, or a Central Management Server and one or more server groups, and one or more registered servers within the groups, and then querying the complete group.</span></span> <span data-ttu-id="aef43-104">Los resultados que devuelve la consulta se pueden combinar en un único panel de resultados o en paneles de resultados independientes.</span><span class="sxs-lookup"><span data-stu-id="aef43-104">The results that are returned by the query can be combined into a single results pane, or can be returned in separate results panes.</span></span> <span data-ttu-id="aef43-105">El conjunto de resultados puede incluir columnas adicionales para el nombre de servidor y el inicio de sesión que usa la consulta en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="aef43-105">The results set can include additional columns for the server name and the login that is used by the query on each server.</span></span> <span data-ttu-id="aef43-106">Los Servidores de administración central y los servidores secundarios se pueden registrar únicamente utilizando la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="aef43-106">Central Management Servers and subordinate servers can be registered by using only Windows Authentication.</span></span> <span data-ttu-id="aef43-107">Los servidores de los grupos de servidores locales se pueden registrar con la autenticación de Windows o con la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aef43-107">Servers in local server groups can be registered by using Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aef43-108">Antes de ejecutar los procedimientos siguientes, cree un Servidor de administración central y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="aef43-108">Before you execute the following procedures, create a Central Management Server and server groups.</span></span> <span data-ttu-id="aef43-109">Para obtener más información, vea [Crear un servidor de administración central y un grupo de servidores &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="aef43-109">For more information, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span></span>  
  
 <span data-ttu-id="aef43-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="aef43-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aef43-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="aef43-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aef43-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="aef43-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="aef43-113">**Para ejecutar instrucciones en varios servidores, usando:**</span><span class="sxs-lookup"><span data-stu-id="aef43-113">**To execute statements against multiple servers, using:**</span></span>  
  
     [<span data-ttu-id="aef43-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aef43-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aef43-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="aef43-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aef43-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="aef43-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aef43-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="aef43-117">Permissions</span></span>  
 <span data-ttu-id="aef43-118">Dado que las conexiones que mantiene un Servidor de administración central se ejecutan en el contexto del usuario, si se usara la autenticación de Windows, los permisos vigentes en los servidores registrados podrían variar.</span><span class="sxs-lookup"><span data-stu-id="aef43-118">Because the connections maintained by a Central Management Server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="aef43-119">Por ejemplo, el usuario podría ser miembro del rol fijo de servidor sysadmin en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, pero tener permisos limitados en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span><span class="sxs-lookup"><span data-stu-id="aef43-119">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="aef43-120">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aef43-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-statements-against-multiple-configuration-targets-simultaneously"></a><span data-ttu-id="aef43-121">Para ejecutar instrucciones con varios destinos de configuración simultáneamente</span><span class="sxs-lookup"><span data-stu-id="aef43-121">To execute statements against multiple configuration targets simultaneously</span></span>  
  
1.  <span data-ttu-id="aef43-122">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Ver** , haga clic en **Servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="aef43-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="aef43-123">Expanda un Servidor de administración central, haga clic con el botón derecho en un grupo de servidores, seleccione **Conectar**y haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="aef43-123">Expand a Central Management Server, right-click a server group, point to **Connect**, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="aef43-124">En el Editor de consultas, escriba y ejecute una instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] , como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="aef43-124">In Query Editor, type and execute a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as the following:</span></span>  
  
    ```  
    USE master  
    GO  
    SELECT * FROM sysdatabases;  
    GO  
    ```  
  
     <span data-ttu-id="aef43-125">De forma predeterminada, el panel de resultados combinará los resultados de la consulta de todos los servidores del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="aef43-125">By default, the results pane will combine the query results from all the servers in the server group.</span></span>  
  
#### <a name="to-change-the-multiserver-results-options"></a><span data-ttu-id="aef43-126">Para cambiar las opciones de los resultados multiservidor</span><span class="sxs-lookup"><span data-stu-id="aef43-126">To change the multiserver results options</span></span>  
  
1.  <span data-ttu-id="aef43-127">En [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], en el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="aef43-127">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="aef43-128">Expanda **Resultados de la consulta**, expanda **SQL Server**y, a continuación, haga clic en **Resultados multiservidor**.</span><span class="sxs-lookup"><span data-stu-id="aef43-128">Expand **Query Results**, expand **SQL Server**, and then click **Multiserver Results**.</span></span>  
  
3.  <span data-ttu-id="aef43-129">En la página **Resultados multiservidor** , especifique la configuración de las opciones que desee y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aef43-129">On the **Multiserver Results** page, specify the option settings that you want, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef43-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aef43-130">See Also</span></span>  
 [<span data-ttu-id="aef43-131">Administrar varios servidores mediante servidores de administración central</span><span class="sxs-lookup"><span data-stu-id="aef43-131">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
