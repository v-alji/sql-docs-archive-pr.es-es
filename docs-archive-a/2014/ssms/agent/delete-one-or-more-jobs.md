---
title: Eliminar uno o más trabajos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, deleting
- dropping jobs
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 67dcdad0-57b2-431c-b77f-4ffc926af93d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 436625f9ad629a6b0e574aa046059f4e7e9c2bf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663278"
---
# <a name="delete-one-or-more-jobs"></a><span data-ttu-id="4b7b9-102">Eliminar uno o más trabajos</span><span class="sxs-lookup"><span data-stu-id="4b7b9-102">Delete One or More Jobs</span></span>
  <span data-ttu-id="4b7b9-103">En este tema se describe cómo eliminar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajos del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4b7b9-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4b7b9-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4b7b9-105">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4b7b9-105">Security</span></span>  
 <span data-ttu-id="4b7b9-106">Solo podrá eliminar los trabajos que posea, a menos que sea miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4b7b9-106">Unless you are a member of the **sysadmin** fixed server role, you can only delete jobs that you own.</span></span>  
  
 
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="4b7b9-107">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b7b9-107">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="4b7b9-108">Para eliminar un trabajo</span><span class="sxs-lookup"><span data-stu-id="4b7b9-108">To delete a job</span></span>  
  
1.  <span data-ttu-id="4b7b9-109">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-109">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4b7b9-110">Expanda **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que desee eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-110">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="4b7b9-111">En el cuadro de diálogo **Eliminar objeto** , confirme que el trabajo que desea eliminar está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-111">In the **Delete Object** dialog box, confirm that the job you intend to delete is selected.</span></span>  
  
4.  <span data-ttu-id="4b7b9-112">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-112">Click **OK**.</span></span>  
  
#### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="4b7b9-113">Para eliminar varios trabajos</span><span class="sxs-lookup"><span data-stu-id="4b7b9-113">To delete multiple jobs</span></span>  
  
1.  <span data-ttu-id="4b7b9-114">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-114">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4b7b9-115">Expanda **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-115">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="4b7b9-116">Haga clic con el botón secundario en **monitor de actividad de trabajo**y haga clic en **ver actividad de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-116">Right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="4b7b9-117">En Monitor de actividad de trabajo, seleccione los trabajos que desee eliminar, haga clic con el botón derecho en la selección y, luego, elija **Eliminar trabajos**.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-117">In the Job Activity Monitor, select the jobs you want to delete, right-click your selection, and choose **Delete jobs**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="4b7b9-118">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b7b9-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="4b7b9-119">Para eliminar un trabajo</span><span class="sxs-lookup"><span data-stu-id="4b7b9-119">To delete a job</span></span>  
  
1.  <span data-ttu-id="4b7b9-120">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b7b9-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4b7b9-121">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4b7b9-122">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC sp_delete_job  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="4b7b9-123">Para obtener más información, vea [sp_delete_job &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b7b9-123">For more information, see [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="4b7b9-124">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b7b9-124">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="4b7b9-125">Para eliminar varios trabajos</span><span class="sxs-lookup"><span data-stu-id="4b7b9-125">To delete multiple jobs</span></span>
  
 <span data-ttu-id="4b7b9-126">Utilice la clase `JobCollection` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b7b9-126">Use the `JobCollection` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="4b7b9-127">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="4b7b9-127">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
