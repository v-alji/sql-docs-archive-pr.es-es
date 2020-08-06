---
title: Cambiar los detalles de la programación de un trabajo maestro del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: f5414451-4d8e-464b-bd9e-f2b70c6899b3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 85546bc93e6626bfcc85a28f06a4c2fe24fe9fd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677378"
---
# <a name="change-the-scheduling-details-for-a-sql-server-agent-master-job"></a><span data-ttu-id="a94f3-102">Change the Scheduling Details for a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="a94f3-102">Change the Scheduling Details for a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="a94f3-103">En este tema se describe cómo cambiar los detalles de la programación de una definición de trabajo en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a94f3-103">This topic describes how to change the scheduling details for a job definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a94f3-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a94f3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a94f3-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a94f3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a94f3-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a94f3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a94f3-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a94f3-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a94f3-108">**Para cambiar los detalles de la programación de una definición de trabajo mediante:**</span><span class="sxs-lookup"><span data-stu-id="a94f3-108">**To change the scheduling details for a job definition, using:**</span></span>  
  
     [<span data-ttu-id="a94f3-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a94f3-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a94f3-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a94f3-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a94f3-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a94f3-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a94f3-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a94f3-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a94f3-113">No se puede destinar un trabajo principal del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a servidores locales y remotos.</span><span class="sxs-lookup"><span data-stu-id="a94f3-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a94f3-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a94f3-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a94f3-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="a94f3-115">Permissions</span></span>  
 <span data-ttu-id="a94f3-116">A menos que sea miembro del rol fijo de servidor **sysadmin** , solo podrá modificar los trabajos de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="a94f3-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="a94f3-117">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="a94f3-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a94f3-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a94f3-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="a94f3-119">Para cambiar los detalles de la programación de una definición de trabajo</span><span class="sxs-lookup"><span data-stu-id="a94f3-119">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="a94f3-120">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor que contiene el trabajo cuya programación desea modificar.</span><span class="sxs-lookup"><span data-stu-id="a94f3-120">In **Object Explorer,** click the plus sign to expand the server that contains the job whose schedule you want to edit.</span></span>  
  
2.  <span data-ttu-id="a94f3-121">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a94f3-122">Haga clic en el signo más para expandir la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="a94f3-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="a94f3-123">Haga clic con el botón derecho en la programación que desea modificar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-123">Right-click the job whose schedule you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="a94f3-124">En el cuadro de diálogo **propiedades del trabajo-**_Job_name_ , en **seleccionar una página**, seleccione **programaciones**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Schedules**.</span></span> <span data-ttu-id="a94f3-125">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nueva página programaciones de &#40;de trabajos&#41;](job-properties-new-job-schedules-page.md).</span><span class="sxs-lookup"><span data-stu-id="a94f3-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md).</span></span>  
  
6.  <span data-ttu-id="a94f3-126">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a94f3-127">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a94f3-127">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="a94f3-128">Para cambiar los detalles de la programación de una definición de trabajo</span><span class="sxs-lookup"><span data-stu-id="a94f3-128">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="a94f3-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a94f3-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a94f3-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a94f3-131">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled status of the NightlyJobs schedule to 0   
    -- and sets the owner to terrid.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_schedule  
        @name = 'NightlyJobs',  
        @enabled = 0,  
        @owner_login_name = 'terrid' ;  
    GO  
    ```  
  
 <span data-ttu-id="a94f3-132">Para obtener más información, vea [sp_update_schedule &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a94f3-132">For more information, see [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span></span>  
  
  
