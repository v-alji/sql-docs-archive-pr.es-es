---
title: Asignar un trabajo a una categoría de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], assigning
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- SQL Server Agent jobs, assigning
- assigning job to category
ms.assetid: a9ea65a2-1d73-4582-a335-63adeb450cb6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 208ff6722a9c18fd4dd0d061575f0d496af27810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677382"
---
# <a name="assign-a-job-to-a-job-category"></a><span data-ttu-id="3e380-102">Asignar un trabajo a una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="3e380-102">Assign a Job to a Job Category</span></span>
  <span data-ttu-id="3e380-103">En este tema se describe cómo asignar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajos del agente a categorías de trabajo en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3e380-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to job categories in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="3e380-104">Las categorías de trabajo le ayudan a organizar los trabajos para poder filtrarlos y agruparlos fácilmente.</span><span class="sxs-lookup"><span data-stu-id="3e380-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="3e380-105">Por ejemplo, puede organizar todos los trabajos de copia de seguridad de las bases de datos en la categoría Mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="3e380-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="3e380-106">Puede asignar trabajos a las categorías de trabajo integradas o puede crear una categoría de trabajo definida por el usuario y, después, asignarle trabajos.</span><span class="sxs-lookup"><span data-stu-id="3e380-106">You can assign jobs to built-in job categories, or you can create a user-defined job category and then assign jobs to that.</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3e380-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="3e380-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3e380-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3e380-108">Security</span></span>  
 <span data-ttu-id="3e380-109">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3e380-109">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="3e380-110">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e380-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="3e380-111">Para asignar un trabajo a una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="3e380-111">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="3e380-112">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que desea asignar un trabajo a una categoría de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3e380-112">In **Object Explorer**, click the plus sign to expand the server where you want to assign a job to a job category.</span></span>  
  
2.  <span data-ttu-id="3e380-113">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3e380-113">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="3e380-114">Haga clic en el signo más para expandir la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="3e380-114">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="3e380-115">Haga clic con el botón derecho en el trabajo que desee editar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3e380-115">Right-click the job you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="3e380-116">En el cuadro de diálogo **Propiedades del trabajo -**_nombre_trabajo_ , en la lista **Categoría** , seleccione la categoría de trabajo que quiere asignar al trabajo.</span><span class="sxs-lookup"><span data-stu-id="3e380-116">In the **Job Properties -**_job_name_ dialog box, in the **Category** list, select the job category you want to assign to the job.</span></span>  
  
6.  <span data-ttu-id="3e380-117">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e380-117">Click **OK**.</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="3e380-118">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e380-118">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="3e380-119">Para asignar un trabajo a una categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="3e380-119">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="3e380-120">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e380-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3e380-121">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="3e380-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3e380-122">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3e380-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="3e380-123">Para obtener más información, vea [sp_update_job &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e380-123">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="3e380-124">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3e380-124">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="3e380-125">**Para asignar un trabajo a una categoría de trabajo**</span><span class="sxs-lookup"><span data-stu-id="3e380-125">**To assign a job to a job category**</span></span>  
  
 <span data-ttu-id="3e380-126">Utilice la clase `JobCategory` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e380-126">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
  
  
