---
title: Deshabilitar o habilitar un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- stopping jobs
- disabling jobs
- SQL Server Agent jobs, disabling
- jobs [SQL Server Agent], disabling
ms.assetid: 5041261f-0c32-4d4a-8bee-59a6c16200dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42fe7cbeed1e2ff3f93b1afef52b165a7d660ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662487"
---
# <a name="disable-or-enable-a-job"></a><span data-ttu-id="57d4b-102">Deshabilitar o habilitar un trabajo</span><span class="sxs-lookup"><span data-stu-id="57d4b-102">Disable or Enable a Job</span></span>
  <span data-ttu-id="57d4b-103">En este tema se describe cómo deshabilitar un trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57d4b-103">This topic describes how to disable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="57d4b-104">Al deshabilitar un trabajo, éste no se elimina y se puede habilitar de nuevo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="57d4b-104">When you disable a job, it is not deleted and can be enabled again when necessary.</span></span>  
  
 <span data-ttu-id="57d4b-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="57d4b-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="57d4b-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="57d4b-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="57d4b-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="57d4b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="57d4b-108">**Para deshabilitar o habilitar un trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="57d4b-108">**To disable or enable a job, using:**</span></span>  
  
     [<span data-ttu-id="57d4b-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57d4b-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="57d4b-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57d4b-110">Transact-SQL</span></span>](#TSQL)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="57d4b-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="57d4b-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="57d4b-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="57d4b-112">Security</span></span>  
 <span data-ttu-id="57d4b-113">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="57d4b-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="57d4b-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57d4b-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="57d4b-115">Para deshabilitar o habilitar un trabajo</span><span class="sxs-lookup"><span data-stu-id="57d4b-115">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="57d4b-116">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="57d4b-116">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="57d4b-117">Expanda **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="57d4b-117">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="57d4b-118">Expanda **Trabajos**y, luego, haga clic con el botón derecho en el trabajo que desee deshabilitar o habilitar.</span><span class="sxs-lookup"><span data-stu-id="57d4b-118">Expand **Jobs**, and then right-click the job that you want to disable or enable.</span></span>  
  
4.  <span data-ttu-id="57d4b-119">Para deshabilitar un trabajo, haga clic en **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="57d4b-119">To disable a job, click **Disable**.</span></span> <span data-ttu-id="57d4b-120">Para habilitar un trabajo, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="57d4b-120">To enable a job, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="57d4b-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57d4b-121">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="57d4b-122">Para deshabilitar o habilitar un trabajo</span><span class="sxs-lookup"><span data-stu-id="57d4b-122">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="57d4b-123">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57d4b-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="57d4b-124">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="57d4b-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="57d4b-125">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="57d4b-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the name, description, and enables status of the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @new_name = N'NightlyBackups -- Disabled',  
        @description = N'Nightly backups disabled during server migration.',  
        @enabled = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="57d4b-126">Para obtener más información, vea [sp_update_job &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="57d4b-126">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
