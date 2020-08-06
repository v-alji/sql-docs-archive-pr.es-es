---
title: Ver un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], viewing
- viewing jobs
- SQL Server Agent jobs, viewing
- displaying jobs
ms.assetid: d2241a3f-dbcf-433c-b7bc-f96bdf0eac8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 26406aaf2ba0ac4809eb7ac2c84799469d0468d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678014"
---
# <a name="view-a-job"></a><span data-ttu-id="92387-102">View a Job</span><span class="sxs-lookup"><span data-stu-id="92387-102">View a Job</span></span>
  <span data-ttu-id="92387-103">En este tema se describe cómo ver los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajos del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92387-103">This topic describes how to view [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="92387-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="92387-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="92387-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="92387-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="92387-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="92387-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="92387-107">**Para ver un trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="92387-107">**To view a job, using:**</span></span>  
  
     [<span data-ttu-id="92387-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92387-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="92387-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92387-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="92387-110">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="92387-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="92387-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="92387-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="92387-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="92387-112">Security</span></span>  
 <span data-ttu-id="92387-113">Puede ver únicamente los trabajos de su propiedad, a menos que sea miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="92387-113">You can only view jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="92387-114">Los miembros de este rol pueden ver todos los trabajos.</span><span class="sxs-lookup"><span data-stu-id="92387-114">Members of this role can view all jobs.</span></span> <span data-ttu-id="92387-115">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="92387-115">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="92387-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92387-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="92387-117">Para ver un trabajo</span><span class="sxs-lookup"><span data-stu-id="92387-117">To view a job</span></span>  
  
1.  <span data-ttu-id="92387-118">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="92387-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="92387-119">Expanda el **Agente SQL Server**y, a continuación, haga clic en **Trabajos**.</span><span class="sxs-lookup"><span data-stu-id="92387-119">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="92387-120">Haga clic con el botón derecho en un trabajo y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="92387-120">Right-click a job, and then click **Properties**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="92387-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92387-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="92387-122">Para ver un trabajo</span><span class="sxs-lookup"><span data-stu-id="92387-122">To view a job</span></span>  
  
1.  <span data-ttu-id="92387-123">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92387-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="92387-124">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="92387-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="92387-125">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="92387-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all aspects of the information for the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_job  
        @job_name = N'NightlyBackups',  
        @job_aspect = N'ALL' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="92387-126">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="92387-126">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="92387-127">**Para ver un trabajo**</span><span class="sxs-lookup"><span data-stu-id="92387-127">**To view a job**</span></span>  
  
 <span data-ttu-id="92387-128">Utilice la clase `Job` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92387-128">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="92387-129">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="92387-129">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
