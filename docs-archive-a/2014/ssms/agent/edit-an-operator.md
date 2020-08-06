---
title: Editar un operador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- modifying operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], modifying with Management Studio
ms.assetid: b2ba2168-ca0b-4b59-9007-4e1e4c30679e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 45ffb520e240dfd97002060370ff6dcf7c60d083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662485"
---
# <a name="edit-an-operator"></a><span data-ttu-id="6251f-102">Editar un operador</span><span class="sxs-lookup"><span data-stu-id="6251f-102">Edit an Operator</span></span>
  <span data-ttu-id="6251f-103">En este tema se describe cómo editar la disponibilidad de un operador para que reciba notificaciones y cómo modificar las direcciones de correo electrónico, buscapersonas y NET SEND en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6251f-103">This topic describes how to edit an operators' availability for receiving notifications and their e-mail, pager, and net send addresses in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6251f-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6251f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6251f-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6251f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6251f-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6251f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6251f-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6251f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6251f-108">**Para editar un operador, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="6251f-108">**To edit an operator, using:**</span></span>  
  
     [<span data-ttu-id="6251f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6251f-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6251f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6251f-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6251f-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6251f-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6251f-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6251f-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6251f-113">Las opciones Buscapersonas y **net send** se quitarán del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una versión futura de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6251f-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6251f-114">Evite utilizar estas características en los nuevos trabajos de programación y planee modificar las aplicaciones que actualmente las utilizan.</span><span class="sxs-lookup"><span data-stu-id="6251f-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="6251f-115">Tenga en cuenta que deberá configurar el Agente SQL Server para que utilice el Correo electrónico de base de datos para enviar a los operadores notificaciones por correo electrónico o buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="6251f-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="6251f-116">Para obtener más información, vea el tema sobre [asignación de alertas a un operador](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6251f-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="6251f-117">ofrece un método gráfico sencillo para administrar trabajos y es el método recomendado para crear y administrar la infraestructura de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6251f-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6251f-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6251f-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6251f-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="6251f-119">Permissions</span></span>  
 <span data-ttu-id="6251f-120">Solo los miembros del rol fijo de servidor **sysadmin** pueden editar operadores.</span><span class="sxs-lookup"><span data-stu-id="6251f-120">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6251f-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6251f-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="6251f-122">Para modificar un operador</span><span class="sxs-lookup"><span data-stu-id="6251f-122">To edit an operator</span></span>  
  
1.  <span data-ttu-id="6251f-123">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene el operador que desea editar.</span><span class="sxs-lookup"><span data-stu-id="6251f-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to edit.</span></span>  
  
2.  <span data-ttu-id="6251f-124">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="6251f-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="6251f-125">Haga clic en el signo más para expandir la carpeta **Operadores** .</span><span class="sxs-lookup"><span data-stu-id="6251f-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="6251f-126">Haga clic con el botón derecho en el operador que desea editar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6251f-126">Right-click the operator that you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="6251f-127">Para más información sobre las opciones disponibles que se incluyen en el cuadro de diálogo _nombre_operador_**Propiedades** , consulte:</span><span class="sxs-lookup"><span data-stu-id="6251f-127">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="6251f-128">Propiedades del operador y nuevo operador &#40;página general&#41;</span><span class="sxs-lookup"><span data-stu-id="6251f-128">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="6251f-129">Propiedades de operador: nuevo operador &#40;página notificaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="6251f-129">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="6251f-130">Propiedades del operador &#40;Página Historial&#41;</span><span class="sxs-lookup"><span data-stu-id="6251f-130">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="6251f-131">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6251f-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6251f-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6251f-132">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="6251f-133">Para modificar un operador</span><span class="sxs-lookup"><span data-stu-id="6251f-133">To edit an operator</span></span>  
  
1.  <span data-ttu-id="6251f-134">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6251f-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6251f-135">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6251f-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6251f-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6251f-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- updates the operator status to enabled, and sets the days   
    -- (from Monday through Friday, from 8 A.M. through 5 P.M.) when the operator can be paged.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 1,  
        @email_address = N'fran??oisa',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 64 ;  
    GO  
    ```  
  
 <span data-ttu-id="6251f-137">Para obtener más información, vea [sp_update_operator &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6251f-137">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
