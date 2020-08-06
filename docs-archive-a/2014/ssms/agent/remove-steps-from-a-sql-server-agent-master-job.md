---
title: Quitar los pasos de un trabajo maestro del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 871e6162-1221-464d-8f7f-7e454dcd9edb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5996971225ee0b300b307c5af24dec464dbfd43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677348"
---
# <a name="remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="e9765-102">Remove Steps from a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="e9765-102">Remove Steps from a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="e9765-103">En este tema se describe cómo quitar los pasos de un trabajo maestro del Agente SQL Server en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9765-103">This topic describes how to remove steps from a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e9765-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="e9765-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e9765-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="e9765-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e9765-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="e9765-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e9765-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e9765-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e9765-108">**Para quitar los pasos de un trabajo maestro del Agente SQL Server mediante:**</span><span class="sxs-lookup"><span data-stu-id="e9765-108">**To remove steps from a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="e9765-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9765-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e9765-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e9765-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e9765-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e9765-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e9765-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="e9765-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e9765-113">No se puede destinar un trabajo principal del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a servidores locales y remotos.</span><span class="sxs-lookup"><span data-stu-id="e9765-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e9765-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e9765-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e9765-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="e9765-115">Permissions</span></span>  
 <span data-ttu-id="e9765-116">A menos que sea miembro del rol fijo de servidor **sysadmin** , solo podrá modificar los trabajos de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="e9765-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="e9765-117">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e9765-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e9765-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9765-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="e9765-119">Para quitar los pasos de un trabajo maestro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9765-119">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="e9765-120">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor que contiene el trabajo del que desea eliminar los pasos.</span><span class="sxs-lookup"><span data-stu-id="e9765-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to delete steps.</span></span>  
  
2.  <span data-ttu-id="e9765-121">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e9765-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="e9765-122">Haga clic en el signo más para expandir la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="e9765-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="e9765-123">Haga clic con el botón derecho en el trabajo del que desea eliminar los pasos y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e9765-123">Right-click the job where you want to delete steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="e9765-124">En el cuadro de diálogo **propiedades del trabajo-**_Job_name_ , en **seleccionar una página**, seleccione **pasos**.</span><span class="sxs-lookup"><span data-stu-id="e9765-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="e9765-125">Bajo **Lista de pasos de trabajo**, seleccione el paso de trabajo que desea eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e9765-125">Under **Job step list**, select the job step you want to delete and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="e9765-126">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e9765-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e9765-127">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e9765-127">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="e9765-128">Para quitar los pasos de un trabajo maestro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9765-128">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="e9765-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9765-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e9765-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e9765-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e9765-131">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e9765-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes job step 1 from the job Weekly Sales Data Backup   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="e9765-132">Para obtener más información, vea [sp_delete_jobstep &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9765-132">For more information, see [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span></span>  
  
  
