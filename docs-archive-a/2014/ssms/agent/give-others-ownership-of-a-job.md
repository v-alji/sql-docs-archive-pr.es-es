---
title: Asignar a otros usuarios la propiedad de un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], owners
- owners [SQL Server], jobs
- SQL Server Agent jobs, owners
ms.assetid: 2ded5e9c-4251-4fb1-a047-99f13d150b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2cf03fdc9031ce9761125d95619438837f2959bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662474"
---
# <a name="give-others-ownership-of-a-job"></a><span data-ttu-id="3667e-102">Give Others Ownership of a Job</span><span class="sxs-lookup"><span data-stu-id="3667e-102">Give Others Ownership of a Job</span></span>
  <span data-ttu-id="3667e-103">En este tema se describe cómo reasignar la propiedad de los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajos del agente a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="3667e-103">This topic describes how to reassign ownership of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>  
  
-   <span data-ttu-id="3667e-104">**Antes de empezar:**  [Limitaciones y restricciones](#Restrictions), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="3667e-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="3667e-105">**Para asignar a otros usuarios la propiedad de un trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="3667e-105">**To give others ownership of a job, using:**</span></span>  
  
     [<span data-ttu-id="3667e-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3667e-106">SQL Server Management Studio</span></span>](#SSMSProc2)  
  
     [<span data-ttu-id="3667e-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3667e-107">Transact-SQL</span></span>](#TsqlProc2)  
  
     [<span data-ttu-id="3667e-108">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3667e-108">SQL Server Management Objects</span></span>](#SMOProc2)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3667e-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="3667e-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3667e-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="3667e-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3667e-111">Para crear un trabajo, el usuario debe ser miembro de uno de los roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3667e-111">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="3667e-112">Solo pueden editar el trabajo el propietario de éste o los miembros del rol **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3667e-112">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="3667e-113">Para más información sobre los roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [Roles fijos de base de datos del Agente SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3667e-113">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="3667e-114">Para cambiar el propietario de un trabajo debe ser administrador de sistema.</span><span class="sxs-lookup"><span data-stu-id="3667e-114">You must be a system administrator to change the owner of a job.</span></span>  
  
 <span data-ttu-id="3667e-115">La asignación de un trabajo a otro inicio de sesión no garantiza que el nuevo propietario disponga de los permisos suficientes para ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="3667e-115">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3667e-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3667e-116">Security</span></span>  
 <span data-ttu-id="3667e-117">Por razones de seguridad, solo el propietario del trabajo o un miembro del rol **sysadmin** puede cambiar la definición del trabajo.</span><span class="sxs-lookup"><span data-stu-id="3667e-117">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="3667e-118">Solo los miembros del rol fijo de servidor **sysadmin** pueden asignar la propiedad de un trabajo a otros usuarios y pueden ejecutar cualquier trabajo, independientemente de quién sea el propietario del mismo.</span><span class="sxs-lookup"><span data-stu-id="3667e-118">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3667e-119">Si cambia la propiedad de un trabajo a un usuario que no es miembro del rol fijo de servidor **sysadmin** y el trabajo está ejecutando unos pasos que necesitan las cuentas de un servidor proxy (por ejemplo, la ejecución de paquetes [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), asegúrese de que el usuario tenga acceso a ese servidor proxy o, de lo contrario, se producirán errores en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="3667e-119">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3667e-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="3667e-120">Permissions</span></span>  
 <span data-ttu-id="3667e-121">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3667e-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProc2"></a> <span data-ttu-id="3667e-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3667e-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3667e-123">**Para asignar a otros usuarios la propiedad de un trabajo**</span><span class="sxs-lookup"><span data-stu-id="3667e-123">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="3667e-124">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="3667e-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3667e-125">Expanda el **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3667e-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3667e-126">En la lista **Propietario** , seleccione un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="3667e-126">In the **Owner** list, select a login.</span></span> <span data-ttu-id="3667e-127">Para cambiar el propietario de un trabajo debe ser administrador de sistema.</span><span class="sxs-lookup"><span data-stu-id="3667e-127">You must be a system administrator to change the owner of a job.</span></span>  
  
     <span data-ttu-id="3667e-128">La asignación de un trabajo a otro inicio de sesión no garantiza que el nuevo propietario disponga de los permisos suficientes para ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="3667e-128">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProc2"></a> <span data-ttu-id="3667e-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3667e-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="3667e-130">**Para asignar a otros usuarios la propiedad de un trabajo**</span><span class="sxs-lookup"><span data-stu-id="3667e-130">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="3667e-131">En el Explorador de objetos, conéctese a una instancia del Motor de base de datos y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="3667e-131">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3667e-132">En la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="3667e-132">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3667e-133">En la ventana de consulta, escriba las siguientes instrucciones que utilizan el sp_manage_jobs_by_login &#40;procedimiento almacenado del sistema [&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3667e-133">In the query window, enter the following statements that use the [sp_manage_jobs_by_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) system stored procedure.</span></span> <span data-ttu-id="3667e-134">En el siguiente ejemplo se reasignan todos los trabajos de `danw` a `fran??oisa`.</span><span class="sxs-lookup"><span data-stu-id="3667e-134">The following example reassigns all jobs from `danw` to `fran??oisa`.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_manage_jobs_by_login  
        @action = N'REASSIGN',  
        @current_owner_login_name = N'danw',  
        @new_owner_login_name = N'fran??oisa' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProc2"></a><span data-ttu-id="3667e-135">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3667e-135">Using SQL Server Management Objects</span></span>  

### <a name="to-give-others-ownership-of-a-job"></a><span data-ttu-id="3667e-136">Para asignar a otros usuarios la propiedad de un trabajo</span><span class="sxs-lookup"><span data-stu-id="3667e-136">To give others ownership of a job</span></span>
  
1.  <span data-ttu-id="3667e-137">Llame a la clase `Job` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3667e-137">Call the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="3667e-138">Para el código de ejemplo, consulte [Programar tareas administrativas automáticas en el Agente SQL Server](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="3667e-138">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3667e-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3667e-139">See Also</span></span>  
 <span data-ttu-id="3667e-140">[Implementar trabajos](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="3667e-140">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="3667e-141">Crear trabajos</span><span class="sxs-lookup"><span data-stu-id="3667e-141">Create Jobs</span></span>](create-jobs.md)  
