---
title: Agregar pasos a un trabajo maestro del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9cc1e8ab-7ddc-427b-859e-203aa7e24642
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccff8d6f4faa7bef549b5a179a957ce798250dbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661789"
---
# <a name="add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="6df0b-102">Add Steps to a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="6df0b-102">Add Steps to a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="6df0b-103">En este tema se describe cómo agregar pasos a un trabajo maestro del Agente SQL Server en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6df0b-103">This topic describes how to add steps to a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6df0b-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6df0b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6df0b-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6df0b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6df0b-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6df0b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6df0b-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6df0b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6df0b-108">**Para agregar pasos a un trabajo maestro del Agente SQL Server mediante:**</span><span class="sxs-lookup"><span data-stu-id="6df0b-108">**To add steps to a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="6df0b-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6df0b-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6df0b-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6df0b-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6df0b-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6df0b-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6df0b-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6df0b-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="6df0b-113">No se puede destinar un trabajo principal del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a servidores locales y remotos.</span><span class="sxs-lookup"><span data-stu-id="6df0b-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6df0b-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6df0b-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6df0b-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="6df0b-115">Permissions</span></span>  
 <span data-ttu-id="6df0b-116">A menos que sea miembro del rol fijo de servidor **sysadmin** , solo podrá modificar los trabajos de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="6df0b-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="6df0b-117">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](../agent/implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="6df0b-117">For detailed information, see [Implement SQL Server Agent Security](../agent/implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6df0b-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6df0b-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="6df0b-119">Para agregar pasos a un trabajo maestro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="6df0b-119">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="6df0b-120">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor que contiene el trabajo al que desea agregar pasos.</span><span class="sxs-lookup"><span data-stu-id="6df0b-120">In **Object Explorer,** click the plus sign to expand the server that contains the job to which you want to add steps.</span></span>  
  
2.  <span data-ttu-id="6df0b-121">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="6df0b-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="6df0b-122">Haga clic en el signo más para expandir la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="6df0b-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="6df0b-123">Haga clic con el botón derecho en el trabajo al que desea agregar pasos y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6df0b-123">Right-click the job to which you want to add steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="6df0b-124">En el cuadro de diálogo **Propiedades del trabajo-** _nombre_de_trabajo_, en **Seleccionar una página**, seleccione **Pasos**.</span><span class="sxs-lookup"><span data-stu-id="6df0b-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span> <span data-ttu-id="6df0b-125">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nuevo trabajo &#40;página pasos&#41;](../agent/job-properties-new-job-steps-page.md).</span><span class="sxs-lookup"><span data-stu-id="6df0b-125">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](../agent/job-properties-new-job-steps-page.md).</span></span>  

6.  <span data-ttu-id="6df0b-126">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6df0b-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6df0b-127">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6df0b-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="6df0b-128">Para agregar pasos a un trabajo maestro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="6df0b-128">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="6df0b-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6df0b-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6df0b-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6df0b-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6df0b-131">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6df0b-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a job step that changes database access to read-only for the Sales database.   
    -- specifies 5 retry attempts, with each retry to occur after a 5 minute wait.   
    -- assumes that the Weekly Sales Data Backup job already exists  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="6df0b-132">Para obtener más información, vea [sp_add_jobstep &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6df0b-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
  
