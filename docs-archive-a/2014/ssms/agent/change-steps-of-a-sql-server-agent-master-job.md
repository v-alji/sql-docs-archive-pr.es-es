---
title: Cambiar los pasos de un trabajo maestro del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 8f1a0ee6-49ff-4080-94ca-d661daeff2a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a9defc17b5b39ab8a322b6da29960eb9968c2e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677380"
---
# <a name="change-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="0fced-102">Change Steps of a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="0fced-102">Change Steps of a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="0fced-103">En este tema se describe cómo cambiar los pasos de un trabajo maestro del Agente SQL Server en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fced-103">This topic describes how to make changes to the steps of a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0fced-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="0fced-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0fced-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="0fced-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0fced-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="0fced-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0fced-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0fced-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0fced-108">**Para realizar cambios en los pasos de un trabajo maestro del Agente SQL Server mediante:**</span><span class="sxs-lookup"><span data-stu-id="0fced-108">**To make changes to the steps of a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="0fced-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0fced-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0fced-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0fced-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0fced-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="0fced-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0fced-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="0fced-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="0fced-113">No se puede destinar un trabajo principal del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a servidores locales y remotos.</span><span class="sxs-lookup"><span data-stu-id="0fced-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0fced-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0fced-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0fced-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="0fced-115">Permissions</span></span>  
 <span data-ttu-id="0fced-116">A menos que sea miembro del rol fijo de servidor **sysadmin** , solo podrá modificar los trabajos de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="0fced-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="0fced-117">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="0fced-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0fced-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0fced-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="0fced-119">Para realizar cambios en los pasos de un trabajo maestro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="0fced-119">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="0fced-120">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor que contiene el trabajo en el que desea modificar los pasos.</span><span class="sxs-lookup"><span data-stu-id="0fced-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify steps.</span></span>  
  
2.  <span data-ttu-id="0fced-121">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0fced-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="0fced-122">Haga clic en el signo más para expandir la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="0fced-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="0fced-123">Haga clic con el botón derecho en el trabajo del que quiera modificar los pasos y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0fced-123">Right-click the job where you want to modify steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="0fced-124">En el cuadro de diálogo **propiedades del trabajo-**_Job_name_ , en **seleccionar una página**, seleccione **pasos**.</span><span class="sxs-lookup"><span data-stu-id="0fced-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="0fced-125">Haga clic en **Editar** para abrir el cuadro **de diálogo Propiedades de paso de trabajo-**_job_step_name_ .</span><span class="sxs-lookup"><span data-stu-id="0fced-125">Click **Edit** to open the **Job Step Properties -**_job_step_name_ dialog box.</span></span> <span data-ttu-id="0fced-126">Para obtener más información sobre las opciones disponibles en este cuadro de diálogo, vea [propiedades de paso de trabajo: nuevo paso de trabajo &#40;página General&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) y [propiedades de paso de trabajo: nuevo paso de trabajo &#40;página avanzadas&#41;](job-step-properties-new-job-step-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="0fced-126">For more information on the available options in this dialog box, see [Job Step Properties: New Job Step &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) and [Job Step Properties: New Job Step &#40;Advanced Page&#41;](job-step-properties-new-job-step-advanced-page.md).</span></span>  
  
7.  <span data-ttu-id="0fced-127">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0fced-127">When finished, click **OK**.</span></span>  
  
8.  <span data-ttu-id="0fced-128">En el cuadro de diálogo **propiedades del trabajo-**_job_name_ , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0fced-128">In the **Job Properties -**_job_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0fced-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0fced-129">Using Transact-SQL</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="0fced-130">Para realizar cambios en los pasos de un trabajo maestro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="0fced-130">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="0fced-131">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fced-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0fced-132">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="0fced-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0fced-133">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="0fced-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the number of retry attempts for the first step of the Weekly Sales Data Backup job.   
    -- After running this example, the number of retry attempts is 10   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1,  
        @retry_attempts = 10 ;  
    GO  
    ```  
  
 <span data-ttu-id="0fced-134">Para obtener más información, vea [sp_update_jobstep &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0fced-134">For more information, see [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span></span>  
  
  
