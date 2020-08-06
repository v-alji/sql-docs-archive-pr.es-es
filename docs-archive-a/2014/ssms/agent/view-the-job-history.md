---
title: Ver el historial de trabajos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- viewing job history
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
- displaying job history
ms.assetid: 3bbd1556-abdb-48a3-b249-546eace76343
author: stevestein
ms.author: sstein
ms.openlocfilehash: e84fafdaeddb5748a8129cd5d71d667db7e5fa37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747404"
---
# <a name="view-the-job-history"></a><span data-ttu-id="f74cb-102">View the Job History</span><span class="sxs-lookup"><span data-stu-id="f74cb-102">View the Job History</span></span>
  <span data-ttu-id="f74cb-103">En este tema se describe cómo ver el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registro del historial de trabajos del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f74cb-103">This topic describes how to view the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="f74cb-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f74cb-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f74cb-105">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f74cb-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f74cb-106">**Para ver el registro de historial de trabajos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="f74cb-106">**To view the job history log, using:**</span></span>  
  
     [<span data-ttu-id="f74cb-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f74cb-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="f74cb-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f74cb-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="f74cb-109">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f74cb-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f74cb-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f74cb-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f74cb-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f74cb-111">Security</span></span>  
 <span data-ttu-id="f74cb-112">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="f74cb-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="f74cb-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f74cb-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="f74cb-114">Para ver el registro de historial de trabajos</span><span class="sxs-lookup"><span data-stu-id="f74cb-114">To view the job history log</span></span>  
  
1.  <span data-ttu-id="f74cb-115">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="f74cb-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f74cb-116">Expanda el **Agente SQL Server**y, a continuación, haga clic en **Trabajos**.</span><span class="sxs-lookup"><span data-stu-id="f74cb-116">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="f74cb-117">Haga clic con el botón derecho en un trabajo y, luego, haga clic en **Ver historial**.</span><span class="sxs-lookup"><span data-stu-id="f74cb-117">Right-click a job, and then click **View History**.</span></span>  
  
4.  <span data-ttu-id="f74cb-118">En el Visor del archivo de registros, vea el historial de trabajos.</span><span class="sxs-lookup"><span data-stu-id="f74cb-118">In the Log File Viewer, view the job history.</span></span>  
  
5.  <span data-ttu-id="f74cb-119">Para actualizar el historial de trabajos, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="f74cb-119">To update the job history, click **Refresh**.</span></span> <span data-ttu-id="f74cb-120">Para ver menos filas, haga clic en el botón **Filtro** y escriba los parámetros de filtro.</span><span class="sxs-lookup"><span data-stu-id="f74cb-120">To view fewer rows, click the **Filter** button and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="f74cb-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f74cb-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="f74cb-122">Para ver el registro de historial de trabajos</span><span class="sxs-lookup"><span data-stu-id="f74cb-122">To view the job history log</span></span>  
  
1.  <span data-ttu-id="f74cb-123">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f74cb-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f74cb-124">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f74cb-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f74cb-125">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f74cb-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all job information for the NightlyBackups job.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobhistory   
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="f74cb-126">Para obtener más información, vea [sp_help_jobhistory &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f74cb-126">For more information, see [sp_help_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="f74cb-127">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f74cb-127">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="f74cb-128">**Para ver el registro de historial de trabajos**</span><span class="sxs-lookup"><span data-stu-id="f74cb-128">**To view the job history log**</span></span>  
  
 <span data-ttu-id="f74cb-129">Llame al método `EnumHistory` de la clase `Job` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f74cb-129">Call the `EnumHistory` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="f74cb-130">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="f74cb-130">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
