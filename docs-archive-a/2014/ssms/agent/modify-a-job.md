---
title: Modificar un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
ms.assetid: dd5e5f20-20c4-4ab9-a19a-db87577dcd43
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0d25830ad119a1f5f344a4dcf318c35bee5f86ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671341"
---
# <a name="modify-a-job"></a><span data-ttu-id="ef24b-102">Modify a Job</span><span class="sxs-lookup"><span data-stu-id="ef24b-102">Modify a Job</span></span>
  <span data-ttu-id="ef24b-103">En este tema se describe cómo cambiar las propiedades de los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajos del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ef24b-103">This topic describes how to change the properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="ef24b-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="ef24b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ef24b-105">**Antes de empezar:** ,</span><span class="sxs-lookup"><span data-stu-id="ef24b-105">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="ef24b-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ef24b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ef24b-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ef24b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ef24b-108">**Para modificar un trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="ef24b-108">**To modify a job, using:**</span></span>  
  
     [<span data-ttu-id="ef24b-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef24b-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="ef24b-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef24b-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="ef24b-111">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ef24b-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ef24b-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ef24b-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ef24b-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ef24b-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ef24b-114">No se puede destinar un trabajo principal del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a servidores locales y remotos.</span><span class="sxs-lookup"><span data-stu-id="ef24b-114">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ef24b-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ef24b-115">Security</span></span>  
 <span data-ttu-id="ef24b-116">A menos que sea miembro del rol fijo de servidor **sysadmin** , solo podrá modificar los trabajos de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="ef24b-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="ef24b-117">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="ef24b-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="ef24b-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef24b-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="ef24b-119">Para modificar un trabajo</span><span class="sxs-lookup"><span data-stu-id="ef24b-119">To modify a job</span></span>  
  
1.  <span data-ttu-id="ef24b-120">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="ef24b-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ef24b-121">Expanda **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que desee modificar y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ef24b-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ef24b-122">En el cuadro de diálogo **Propiedades del trabajo** , actualice las propiedades, los pasos, la programación, las alertas y las notificaciones del trabajo desde las páginas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="ef24b-122">In the **Job Properties** dialog box, update the job's properties, steps, schedule, alerts, and notifications using the corresponding pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="ef24b-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef24b-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="ef24b-124">Para modificar un trabajo</span><span class="sxs-lookup"><span data-stu-id="ef24b-124">To modify a job</span></span>  
  
1.  <span data-ttu-id="ef24b-125">En el Explorador de objetos, conéctese a una instancia del Motor de base de datos y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="ef24b-125">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ef24b-126">En la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="ef24b-126">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ef24b-127">En la ventana de consulta, use los siguientes procedimientos almacenados del sistema para modificar un trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef24b-127">In the query window, use the following system stored procedures to modify a job.</span></span>  
  
    -   <span data-ttu-id="ef24b-128">Ejecute [sp_update_job &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) para cambiar los atributos de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef24b-128">Execute [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) to change the attributes of a job.</span></span>  
  
    -   <span data-ttu-id="ef24b-129">Ejecute [sp_update_schedule &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) para cambiar los detalles de la programación de una definición de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef24b-129">Execute [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) to change the scheduling details for a job definition.</span></span>  
  
    -   <span data-ttu-id="ef24b-130">Ejecute [sp_add_jobstep &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) para agregar nuevos pasos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef24b-130">Execute [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) to add new job steps.</span></span>  
  
    -   <span data-ttu-id="ef24b-131">Ejecute [sp_update_jobstep &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) para cambiar los pasos de trabajo ya existentes.</span><span class="sxs-lookup"><span data-stu-id="ef24b-131">Execute [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) to change pre-existing job steps.</span></span>  
  
    -   <span data-ttu-id="ef24b-132">Ejecute [sp_delete_jobstep &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) para quitar un paso de trabajo de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef24b-132">Execute [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) to remove a job step from a job.</span></span>  
  
    -   <span data-ttu-id="ef24b-133">Procedimientos almacenados adicionales para modificar cualquier trabajo maestro del Agente SQL Server:</span><span class="sxs-lookup"><span data-stu-id="ef24b-133">Additional stored procedures to modify any SQL Server Agent master job:</span></span>  
  
        -   <span data-ttu-id="ef24b-134">Ejecute [sp_delete_jobserver &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) para eliminar un servidor asociado actualmente a un trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef24b-134">Execute [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) to delete a server currently associated with a job.</span></span>  
  
        -   <span data-ttu-id="ef24b-135">Ejecute [sp_add_jobserver &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) para asociar un servidor al trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="ef24b-135">Execute [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) to associate a server with the current job.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="ef24b-136">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ef24b-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="ef24b-137">**Para modificar un trabajo**</span><span class="sxs-lookup"><span data-stu-id="ef24b-137">**To modify a job**</span></span>  
  
 <span data-ttu-id="ef24b-138">Utilice la clase `Job` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef24b-138">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="ef24b-139">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="ef24b-139">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
