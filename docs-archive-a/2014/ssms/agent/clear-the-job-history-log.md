---
title: Borrar el registro del historial de trabajos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- clearing job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 34b9398a-c409-4040-8ea1-0deceb18f961
author: stevestein
ms.author: sstein
ms.openlocfilehash: 813c2c7c86a769eea09a093f2de999460d78ef54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677375"
---
# <a name="clear-the-job-history-log"></a><span data-ttu-id="f854f-102">Clear the Job History Log</span><span class="sxs-lookup"><span data-stu-id="f854f-102">Clear the Job History Log</span></span>
  <span data-ttu-id="f854f-103">En este tema se describe cómo eliminar el contenido del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registro de historial de trabajos del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f854f-103">This topic describes how to delete the contents of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="f854f-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f854f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f854f-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f854f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f854f-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f854f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f854f-107">**Para borrar el registro del historial de trabajos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="f854f-107">**To clear the job history log, using:**</span></span>  
  
     [<span data-ttu-id="f854f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f854f-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="f854f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f854f-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="f854f-110">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f854f-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f854f-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f854f-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f854f-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f854f-112">Security</span></span>  
 <span data-ttu-id="f854f-113">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="f854f-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="f854f-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f854f-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="f854f-115">Para borrar el registro del historial de trabajos</span><span class="sxs-lookup"><span data-stu-id="f854f-115">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="f854f-116">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="f854f-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f854f-117">Expanda el **Agente SQL Server**y, a continuación, haga clic en **Trabajos**.</span><span class="sxs-lookup"><span data-stu-id="f854f-117">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="f854f-118">Haga clic con el botón derecho en un trabajo y, luego, haga clic en **Ver historial**.</span><span class="sxs-lookup"><span data-stu-id="f854f-118">Right-click a job and click **View history**.</span></span>  
  
4.  <span data-ttu-id="f854f-119">En el **Visor del archivo de registros**, seleccione el trabajo cuyo historial desee borrar y, a continuación, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f854f-119">In the **Log File Viewer**, select the job for which you want to clear history, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="f854f-120">Haga clic en **Eliminar**y, a continuación, haga clic en **Eliminar todo el historial** en el cuadro de diálogo **Eliminar historial** .</span><span class="sxs-lookup"><span data-stu-id="f854f-120">Click **Delete**, and then click **Delete all history** in the **Delete History** dialog.</span></span> <span data-ttu-id="f854f-121">Puede eliminar todo el historial de trabajos o solamente el historial anterior a una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="f854f-121">You can delete all job history or only history that is older than a specified date.</span></span> <span data-ttu-id="f854f-122">Si desea eliminar todo el historial de trabajos, haga clic en **Eliminar todo el historial**.</span><span class="sxs-lookup"><span data-stu-id="f854f-122">If you want to remove all job history, click **Delete all history**.</span></span> <span data-ttu-id="f854f-123">Si solo desea eliminar los registros más antiguos del historial de trabajos, haga clic en **Eliminar el historial antes de**y, a continuación, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="f854f-123">If you only want to remove older job history logs, click **Delete history before**, and then specify a date.</span></span>  
  
    -   <span data-ttu-id="f854f-124">Haga clic en **Estado del trabajo** si desea borrar el registro del historial de un trabajo multiservidor.</span><span class="sxs-lookup"><span data-stu-id="f854f-124">Click **Job status** if you want to clear the history log of a multiserver job.</span></span> <span data-ttu-id="f854f-125">Haga clic en **Trabajo**, haga clic en el nombre de un trabajo y, a continuación, haga clic en **Ver historial de trabajos remotos**.</span><span class="sxs-lookup"><span data-stu-id="f854f-125">Click **Job**, click a job name, and then click **View Remote Job History**.</span></span>  
  
5.  <span data-ttu-id="f854f-126">Haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f854f-126">Click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="f854f-127">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f854f-127">Using Transact-SQL</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="f854f-128">Para borrar el registro del historial de trabajos</span><span class="sxs-lookup"><span data-stu-id="f854f-128">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="f854f-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f854f-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f854f-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f854f-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f854f-131">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f854f-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- example removes the history for a job named NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_purge_jobhistory  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="f854f-132">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f854f-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="f854f-133">**Para borrar el registro del historial de trabajos**</span><span class="sxs-lookup"><span data-stu-id="f854f-133">**To clear the job history log**</span></span>  
  
 <span data-ttu-id="f854f-134">Use el método `PurgeJobHistory` de la clase `JobServer` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f854f-134">Use the `PurgeJobHistory` method of the `JobServer` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="f854f-135">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="f854f-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
