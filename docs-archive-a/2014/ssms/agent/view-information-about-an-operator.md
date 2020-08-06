---
title: Ver información sobre un operador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- viewing operators
- operators (users) [Database Engine], viewing with Management Studio
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- displaying operators
ms.assetid: 92c82cdf-f704-444e-9539-82aea7fe6fb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 680b90401f800a9c435bdae33b8e55385541cc4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671312"
---
# <a name="view-information-about-an-operator"></a><span data-ttu-id="996b9-102">Ver información acerca de un operador</span><span class="sxs-lookup"><span data-stu-id="996b9-102">View Information About an Operator</span></span>
  <span data-ttu-id="996b9-103">En este tema se describe cómo ver información sobre un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] operador del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="996b9-103">This topic describes how to view information about a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="996b9-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="996b9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="996b9-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="996b9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="996b9-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="996b9-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="996b9-107">**Para ver información acerca de un operador, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="996b9-107">**To view information about an operator, using:**</span></span>  
  
     [<span data-ttu-id="996b9-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="996b9-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="996b9-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="996b9-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="996b9-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="996b9-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="996b9-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="996b9-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="996b9-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="996b9-112">Permissions</span></span>  
 <span data-ttu-id="996b9-113">De forma predeterminada, los miembros del rol fijo de servidor **sysadmin** pueden ejecutar este procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="996b9-113">By default, members of the **sysadmin** fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="996b9-114">Al resto de usuarios se les debe conceder uno de los siguientes roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la base de datos **msdb** :</span><span class="sxs-lookup"><span data-stu-id="996b9-114">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="996b9-115">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="996b9-115">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="996b9-116">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="996b9-116">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="996b9-117">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="996b9-117">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="996b9-118">Para detalles sobre los permisos de estos roles, consulte [Roles fijos de base de datos del Agente SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="996b9-118">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="996b9-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="996b9-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="996b9-120">Para ver información acerca de un operador</span><span class="sxs-lookup"><span data-stu-id="996b9-120">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="996b9-121">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene el operador que desea ver.</span><span class="sxs-lookup"><span data-stu-id="996b9-121">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to view.</span></span>  
  
2.  <span data-ttu-id="996b9-122">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="996b9-122">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="996b9-123">Haga clic en el signo más para expandir la carpeta **Operadores** .</span><span class="sxs-lookup"><span data-stu-id="996b9-123">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="996b9-124">Haga clic con el botón derecho en el operador que desea ver y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="996b9-124">Right-click the operator that you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="996b9-125">Para más información sobre las opciones disponibles que se incluyen en el cuadro de diálogo _nombre_operador_**Propiedades** , consulte:</span><span class="sxs-lookup"><span data-stu-id="996b9-125">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="996b9-126">Propiedades del operador y nuevo operador &#40;página general&#41;</span><span class="sxs-lookup"><span data-stu-id="996b9-126">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="996b9-127">Propiedades de operador: nuevo operador &#40;página notificaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="996b9-127">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="996b9-128">Propiedades del operador &#40;Página Historial&#41;</span><span class="sxs-lookup"><span data-stu-id="996b9-128">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="996b9-129">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="996b9-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="996b9-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="996b9-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="996b9-131">Para ver información acerca de un operador</span><span class="sxs-lookup"><span data-stu-id="996b9-131">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="996b9-132">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="996b9-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="996b9-133">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="996b9-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="996b9-134">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="996b9-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about operator Fran??ois Ajenstat   
    -- This example assumes that the operator exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_operator  
        @operator_name = N'Fran??ois Ajenstat' ;  
    GO  
    ```  
  
 <span data-ttu-id="996b9-135">Para obtener más información, vea [sp_help_operator &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="996b9-135">For more information, see [sp_help_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span></span>  
  
  
