---
title: Modificar los servidores de destino asociados a un trabajo maestro de Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 176e73b6-08aa-48ec-b349-e84b431e65cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6b7b5ab114366cdafe40b7a70f523fef43eb11d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677364"
---
# <a name="modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="7ae0d-102">Modificar los servidores de destino asociados a un trabajo maestro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ae0d-102">Modify the Target Server(s) Associated with a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="7ae0d-103">En este tema se describe cómo modificar los servidores de destino asociados a un trabajo maestro del Agente SQL Server en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ae0d-103">This topic describes how to modify the target server(s) associated with a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7ae0d-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="7ae0d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7ae0d-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="7ae0d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7ae0d-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7ae0d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7ae0d-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7ae0d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7ae0d-108">**Para modificar los servidores de destino asociados a un trabajo maestro del Agente SQL Server mediante:**</span><span class="sxs-lookup"><span data-stu-id="7ae0d-108">**To modify the target server(s) associated with a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="7ae0d-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ae0d-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7ae0d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ae0d-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7ae0d-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7ae0d-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7ae0d-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7ae0d-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="7ae0d-113">No se puede destinar un trabajo principal del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a servidores locales y remotos.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7ae0d-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7ae0d-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7ae0d-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="7ae0d-115">Permissions</span></span>  
 <span data-ttu-id="7ae0d-116">A menos que sea miembro del rol fijo de servidor **sysadmin** , solo podrá modificar los trabajos de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="7ae0d-117">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="7ae0d-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7ae0d-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ae0d-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="7ae0d-119">Para modificar los servidores de destino asociados a un trabajo maestro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ae0d-119">To modify the target server(s) associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="7ae0d-120">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor que contiene el trabajo cuyo servidor de destino desea modificar.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify the target server.</span></span>  
  
2.  <span data-ttu-id="7ae0d-121">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="7ae0d-122">Haga clic en el signo más para expandir la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="7ae0d-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="7ae0d-123">Haga clic con el botón derecho en el trabajo en el que desea modificar el servidor de destino y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-123">Right-click the job where you want to modify the target server and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="7ae0d-124">En el cuadro de diálogo **propiedades del trabajo-**_Job_name_ , en **seleccionar una página**, seleccione **destinos**.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Targets**.</span></span> <span data-ttu-id="7ae0d-125">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nuevo trabajo &#40;página destinos&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="7ae0d-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
6.  <span data-ttu-id="7ae0d-126">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7ae0d-127">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ae0d-127">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-target-server-currently-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="7ae0d-128">Para eliminar un servidor de destino asociado actualmente a un trabajo maestro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ae0d-128">To delete a target server currently associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="7ae0d-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ae0d-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7ae0d-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7ae0d-131">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes the server SEATTLE2 from processing the Weekly Sales Backupsjob   
    -- assumes that the Weekly Sales Backups job exists  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="7ae0d-132">Para obtener más información, vea [sp_delete_jobserver &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ae0d-132">For more information, see [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span></span>  
  
#### <a name="to-associate-a-target-server-with-the-current-sql-server-agent-master-job"></a><span data-ttu-id="7ae0d-133">Para asociar un servidor de destino al trabajo maestro del Agente SQL Server actual</span><span class="sxs-lookup"><span data-stu-id="7ae0d-133">To associate a target server with the current SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="7ae0d-134">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ae0d-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7ae0d-135">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7ae0d-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7ae0d-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2   
    -- assumes that the Weekly Sales Backups job already exists and that   
    -- SEATTLE2 is registered as a target server for the current instance  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="7ae0d-137">Para obtener más información, vea [sp_add_jobserver &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ae0d-137">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
  
