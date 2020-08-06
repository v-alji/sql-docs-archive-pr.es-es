---
title: Eliminar un registro de pasos de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [SQL Server Agent]
- deleting job step logs
- logs [SQL Server], jobs
- removing job step logs
ms.assetid: ee20c6cd-0258-4550-bdb0-71e86a0fb330
author: stevestein
ms.author: sstein
ms.openlocfilehash: de7c64c4d7cf461eef563ae6989e043d125c6f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673991"
---
# <a name="delete-a-job-step-log"></a><span data-ttu-id="34e4b-102">Delete a Job Step Log</span><span class="sxs-lookup"><span data-stu-id="34e4b-102">Delete a Job Step Log</span></span>
  <span data-ttu-id="34e4b-103">En este tema se describe cómo eliminar un registro de pasos de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34e4b-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step log.</span></span>  
  
-   <span data-ttu-id="34e4b-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="34e4b-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="34e4b-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="34e4b-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="34e4b-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="34e4b-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="34e4b-107">**Para eliminar un registro de pasos de trabajo del Agente SQL Server, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="34e4b-107">**To delete a SQL Server Agent job step log, using:**</span></span>  
  
     [<span data-ttu-id="34e4b-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34e4b-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="34e4b-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="34e4b-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="34e4b-110">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="34e4b-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="34e4b-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="34e4b-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="34e4b-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="34e4b-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="34e4b-113">Cuando se eliminan pasos de trabajo, sus registros de salida respectivos también se eliminan de forma automática.</span><span class="sxs-lookup"><span data-stu-id="34e4b-113">When job steps are deleted their output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="34e4b-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="34e4b-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="34e4b-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="34e4b-115">Permissions</span></span>  
 <span data-ttu-id="34e4b-116">A menos que sea miembro del rol fijo de servidor **sysadmin** , solo podrá modificar los trabajos de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="34e4b-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="34e4b-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34e4b-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="34e4b-118">Para eliminar un registro de paso de trabajo del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="34e4b-118">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="34e4b-119">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="34e4b-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="34e4b-120">Expanda **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que desee modificar y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="34e4b-120">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="34e4b-121">En el cuadro de diálogo **Propiedades del trabajo** , elimine el paso de trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="34e4b-121">In the **Job Properties** dialog box, delete the selected job step.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="34e4b-122">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="34e4b-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="34e4b-123">Para eliminar un registro de paso de trabajo del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="34e4b-123">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="34e4b-124">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34e4b-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="34e4b-125">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="34e4b-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="34e4b-126">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="34e4b-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- removes the job step log for step 2 in the job Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobsteplog  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 2;  
    GO  
    ```  
  
 <span data-ttu-id="34e4b-127">Para obtener más información, vea [sp_delete_jobsteplog &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="34e4b-127">For more information, see [sp_delete_jobsteplog &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="34e4b-128">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="34e4b-128">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="34e4b-129">Use los métodos `DeleteJobStepLogs` de la clase `Job` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34e4b-129">Use the `DeleteJobStepLogs` methods of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="34e4b-130">Para más información, consulte[Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="34e4b-130">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
```powershell
# Delete all job step log files that have ID values larger than 5.  
$srv = New-Object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = $srv.JobServer.Jobs["Test Job"]  
$jb.DeleteJobStepLogs(5)  
```
