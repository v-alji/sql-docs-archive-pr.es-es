---
title: Usar el regulador de recursos para limitar el uso de CPU mediante compresión de copia de seguridad (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup compression [SQL Server], Resource Governor
- backup compression [SQL Server], CPU usage
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- Resource Governor, backup compression
ms.assetid: 01796551-578d-4425-9b9e-d87210f7ba72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19a95cfa5c6780fbdf71ae58bd141aa9aa351efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751210"
---
# <a name="use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql"></a><span data-ttu-id="dce56-102">Usar el regulador de recursos para limitar el uso de CPU mediante compresión de copia de seguridad (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dce56-102">Use Resource Governor to Limit CPU Usage by Backup Compression (Transact-SQL)</span></span>
  <span data-ttu-id="dce56-103">De forma predeterminada, la copia de seguridad con compresión aumenta significativamente el uso de CPU, y la CPU adicional consumida por el proceso de compresión puede afectar adversamente a las operaciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="dce56-103">By default, backing up using compression significantly increases CPU usage, and the additional CPU consumed by the compression process can adversely impact concurrent operations.</span></span> <span data-ttu-id="dce56-104">Por consiguiente, podría querer crear una copia de seguridad comprimida de prioridad baja en una sesión en la que el uso de CPU esté limitado por el[regulador de recursos](../resource-governor/resource-governor.md) cuando se produce la contención por la CPU.</span><span class="sxs-lookup"><span data-stu-id="dce56-104">Therefore, you might want to create a low-priority compressed backup in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md) when CPU contention occurs.</span></span> <span data-ttu-id="dce56-105">En este tema se presenta un escenario en el que se clasifican las sesiones de un usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] determinado asignándolas a un grupo de cargas de trabajo del regulador de recursos que limita el uso de CPU en tales casos.</span><span class="sxs-lookup"><span data-stu-id="dce56-105">This topic presents a scenario that classifies the sessions of a particular [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user by mapping them to a Resource Governor workload group that limits CPU usage in such cases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dce56-106">En un escenario determinado en el que se use el regulador de recursos, la clasificación de la sesión podría basarse en un nombre de usuario, un nombre de aplicación u otra característica que pueda diferenciar una conexión.</span><span class="sxs-lookup"><span data-stu-id="dce56-106">In a given Resource Governor scenario, session classification might be based on a user name, an application name, or anything else that can differentiate a connection.</span></span> <span data-ttu-id="dce56-107">Para obtener más información, consulte [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) y [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="dce56-107">For more information, see [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) and [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span></span>  
  
##  <a name="this-topic-contains-the-following-set-of-scenarios-which-are-presented-in-sequence"></a><a name="Top"></a> <span data-ttu-id="dce56-108">Este tema contiene el conjunto siguiente de escenarios, que se presentan en secuencia:</span><span class="sxs-lookup"><span data-stu-id="dce56-108">This topic contains the following set of scenarios, which are presented in sequence:</span></span>  
  
1.  [<span data-ttu-id="dce56-109">Configurar un inicio de sesión y un usuario para operaciones de prioridad baja</span><span class="sxs-lookup"><span data-stu-id="dce56-109">Setting Up a Login and User for Low-Priority Operations</span></span>](#setup_login_and_user)  
  
2.  [<span data-ttu-id="dce56-110">Configurar el regulador de recursos para limitar el uso de CPU</span><span class="sxs-lookup"><span data-stu-id="dce56-110">Configuring Resource Governor to Limit CPU Usage</span></span>](#configure_RG)  
  
3.  [<span data-ttu-id="dce56-111">Comprobar la clasificación de la sesión actual (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dce56-111">Verifying the Classification of the Current Session (Transact-SQL)</span></span>](#verifying)  
  
4.  [<span data-ttu-id="dce56-112">Comprimir las copias de seguridad utilizando una sesión con CPU limitada</span><span class="sxs-lookup"><span data-stu-id="dce56-112">Compressing Backups Using a Session with Limited CPU</span></span>](#creating_compressed_backup)  
  
##  <a name="setting-up-a-login-and-user-for-low-priority-operations"></a><a name="setup_login_and_user"></a> <span data-ttu-id="dce56-113">Configurar un inicio de sesión y un usuario para operaciones de prioridad baja</span><span class="sxs-lookup"><span data-stu-id="dce56-113">Setting Up a Login and User for Low-Priority Operations</span></span>  
 <span data-ttu-id="dce56-114">El escenario de este tema requiere un usuario y un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de prioridad baja.</span><span class="sxs-lookup"><span data-stu-id="dce56-114">The scenario in this topic requires a low-priority [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user.</span></span> <span data-ttu-id="dce56-115">El nombre de usuario se utilizará para clasificar las sesiones que se ejecutan en el inicio de sesión y enrutarlas a un grupo de cargas de trabajo del regulador de recursos que limita el uso de CPU.</span><span class="sxs-lookup"><span data-stu-id="dce56-115">The user name will be used to classify sessions running in the login and route them to a Resource Governor workload group that limits CPU usage.</span></span>  
  
 <span data-ttu-id="dce56-116">En el procedimiento siguiente se describen los pasos para configurar un inicio de sesión y un usuario con este propósito, además de un ejemplo de [!INCLUDE[tsql](../../includes/tsql-md.md)], "Ejemplo A: Configurar un inicio de sesión y un usuario (Transact-SQL)".</span><span class="sxs-lookup"><span data-stu-id="dce56-116">The following procedure describes the steps for setting up a login and user for this purpose, followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example, "Example A: Setting Up a Login and User (Transact-SQL)."</span></span>  
  
### <a name="to-set-up-a-login-and-database-user-for-classifying-sessions"></a><span data-ttu-id="dce56-117">Para configurar un inicio de sesión y un usuario de la base de datos para clasificar las sesiones</span><span class="sxs-lookup"><span data-stu-id="dce56-117">To set up a login and database user for classifying sessions</span></span>  
  
1.  <span data-ttu-id="dce56-118">Cree un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para crear copias de seguridad comprimidas de prioridad baja.</span><span class="sxs-lookup"><span data-stu-id="dce56-118">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login for creating low-priority compressed backups.</span></span>  
  
     <span data-ttu-id="dce56-119">**Para crear un inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="dce56-119">**To create a login**</span></span>  
  
    -   [<span data-ttu-id="dce56-120">Crear un inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="dce56-120">Create a Login</span></span>](../security/authentication-access/create-a-login.md)  
  
    -   [<span data-ttu-id="dce56-121">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dce56-121">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
2.  <span data-ttu-id="dce56-122">Si lo desea, puede conceder el permiso VIEW SERVER STATE a este inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="dce56-122">Optionally, grant VIEW SERVER STATE to this login.</span></span>  
  
    -   [<span data-ttu-id="dce56-123">Permisos de objeto de sistema GRANT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dce56-123">GRANT System Object Permissions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-system-object-permissions-transact-sql)  
  
     <span data-ttu-id="dce56-124">Para obtener más información, vea [Permisos de entidad de seguridad de base de datos GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dce56-124">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
3.  <span data-ttu-id="dce56-125">Cree un usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para este inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="dce56-125">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user for this login.</span></span>  
  
     <span data-ttu-id="dce56-126">**Para crear un usuario**</span><span class="sxs-lookup"><span data-stu-id="dce56-126">**To create a user**</span></span>  
  
    -   [<span data-ttu-id="dce56-127">Crear un usuario de base de datos</span><span class="sxs-lookup"><span data-stu-id="dce56-127">Create a Database User</span></span>](../security/authentication-access/create-a-database-user.md)  
  
    -   [<span data-ttu-id="dce56-128">CREATE USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dce56-128">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
4.  <span data-ttu-id="dce56-129">Para que las sesiones de este inicio de sesión y este usuario puedan realizar una copia de seguridad de una base de datos determinada, agregue el usuario al rol de base de datos db_backupoperator de esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="dce56-129">To enable sessions of this login and user to back up a given database, add the user to the db_backupoperator database role of that database.</span></span> <span data-ttu-id="dce56-130">Haga esto con cada base de datos de la que este usuario vaya a hacer una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dce56-130">Do this for each database that this user will back up.</span></span> <span data-ttu-id="dce56-131">Si lo desea, puede agregar el usuario a los demás roles fijos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="dce56-131">Optionally, add the user to other fixed database roles.</span></span>  
  
     <span data-ttu-id="dce56-132">**Para agregar un usuario a un rol fijo de base de datos**</span><span class="sxs-lookup"><span data-stu-id="dce56-132">**To add a user to a fixed database role**</span></span>  
  
    -   [<span data-ttu-id="dce56-133">sp_addrolemember &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dce56-133">sp_addrolemember &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql)  
  
     <span data-ttu-id="dce56-134">Para obtener más información, vea [Permisos de entidad de seguridad de base de datos GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dce56-134">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
### <a name="example-a-setting-up-a-login-and-user-transact-sql"></a><span data-ttu-id="dce56-135">Ejemplo A: Configurar un inicio de sesión y un usuario (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dce56-135">Example A: Setting Up a Login and User (Transact-SQL)</span></span>  
 <span data-ttu-id="dce56-136">El ejemplo siguiente solo es pertinente si decide crear un usuario y un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nuevos para las copias de seguridad de prioridad baja.</span><span class="sxs-lookup"><span data-stu-id="dce56-136">The following example is relevant only if you choose to create a new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user for low-priority backups.</span></span> <span data-ttu-id="dce56-137">Por otro lado, puede usar un inicio de sesión y un usuario existentes, si hay alguno adecuado.</span><span class="sxs-lookup"><span data-stu-id="dce56-137">Alternatively, you can use an existing login and user, if an appropriate one exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dce56-138">En el ejemplo siguiente se usa un inicio de sesión y un nombre de usuario de ejemplo, *nombre_de_dominio*`\MAX_CPU`.</span><span class="sxs-lookup"><span data-stu-id="dce56-138">The following example uses a sample login and user name, *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="dce56-139">Reemplácelos por los nombres del usuario y el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que piensa usar al crear las copias de seguridad comprimidas de prioridad baja.</span><span class="sxs-lookup"><span data-stu-id="dce56-139">Replace these with the names of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user that you plan to use when creating your low-priority compressed backups.</span></span>  
  
 <span data-ttu-id="dce56-140">En este ejemplo se crea un inicio de sesión para la cuenta de Windows *nombre_de_dominio*`\MAX_CPU` y, después, se concede el permiso VIEW SERVER STATE al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="dce56-140">This example creates a login for the *domain_name*`\MAX_CPU` Windows account and then grants VIEW SERVER STATE permission to the login.</span></span> <span data-ttu-id="dce56-141">Este permiso permite comprobar la clasificación que hace el regulador de recursos de las sesiones del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="dce56-141">This permission enables you to verify the Resource Governor classification of sessions of the login.</span></span> <span data-ttu-id="dce56-142">Después, en el ejemplo se crea un usuario para *nombre_de_dominio*`\MAX_CPU` y se agrega al rol fijo de base de datos db_backupoperator para la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dce56-142">The example then creates a user for *domain_name*`\MAX_CPU` and adds it to the db_backupoperator fixed database role for the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="dce56-143">La función clasificadora del regulador de recursos usará este nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="dce56-143">This user name will be used by the Resource Governor classifier function.</span></span>  
  
```sql  
-- Create a SQL Server login for low-priority operations  
USE master;  
CREATE LOGIN [domain_name\MAX_CPU] FROM WINDOWS;  
GRANT VIEW SERVER STATE TO [domain_name\MAX_CPU];  
GO  
-- Create a SQL Server user in AdventureWorks2012 for this login  
USE AdventureWorks2012;  
CREATE USER [domain_name\MAX_CPU] FOR LOGIN [domain_name\MAX_CPU];  
EXEC sp_addrolemember 'db_backupoperator', 'domain_name\MAX_CPU';  
GO  
  
```  
  
 [<span data-ttu-id="dce56-144">&#91;Principio&#93;</span><span class="sxs-lookup"><span data-stu-id="dce56-144">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="configuring-resource-governor-to-limit-cpu-usage"></a><a name="configure_RG"></a> <span data-ttu-id="dce56-145">Configurar el regulador de recursos para limitar el uso de CPU</span><span class="sxs-lookup"><span data-stu-id="dce56-145">Configuring Resource Governor to Limit CPU Usage</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dce56-146">Asegúrese de que el regulador de recursos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="dce56-146">Ensure that Resource Governor is enabled.</span></span> <span data-ttu-id="dce56-147">Para obtener más información, vea [Habilitar el regulador de recursos](../resource-governor/enable-resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="dce56-147">For more information, see [Enable Resource Governor](../resource-governor/enable-resource-governor.md).</span></span>  
  
 <span data-ttu-id="dce56-148">En este escenario en el que se usa el regulador de recursos, la configuración comprende los pasos básicos siguientes:</span><span class="sxs-lookup"><span data-stu-id="dce56-148">In this Resource Governor scenario, configuration comprises the following basic steps:</span></span>  
  
1.  <span data-ttu-id="dce56-149">Cree y configure un grupo de recursos de servidor del regulador de recursos que limite el ancho de banda máximo medio de CPU que se concederá a las solicitudes en el grupo de recursos de servidor cuando se produzca la contención por la CPU.</span><span class="sxs-lookup"><span data-stu-id="dce56-149">Create and configure a Resource Governor resource pool that limits the maximum average CPU bandwidth that will be given to requests in the resource pool when CPU contention occurs.</span></span>  
  
2.  <span data-ttu-id="dce56-150">Cree y configure un grupo de cargas de trabajo del regulador de recursos que utiliza este grupo.</span><span class="sxs-lookup"><span data-stu-id="dce56-150">Create and configure a Resource Governor workload group that uses this pool.</span></span>  
  
3.  <span data-ttu-id="dce56-151">Cree una *función clasificadora*; se trata de una función definida por el usuario (UDF) que devuelve unos valores que el regulador de recursos usa para clasificar las sesiones de modo que se enruten al grupo de cargas de trabajo adecuado.</span><span class="sxs-lookup"><span data-stu-id="dce56-151">Create a *classifier function*, which is a user-defined function (UDF) whose return values are used by Resource Governor for classifying sessions so that they are routed to the appropriate workload group.</span></span>  
  
4.  <span data-ttu-id="dce56-152">Registre la función clasificadora con el regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="dce56-152">Register the classifier function with Resource Governor.</span></span>  
  
5.  <span data-ttu-id="dce56-153">Aplique los cambios a la configuración en memoria del regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="dce56-153">Apply the changes to the Resource Governor in-memory configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dce56-154">Para obtener información sobre los grupos de recursos de servidor del regulador de recursos, los grupos de cargas de trabajo y la clasificación, vea [Regulador de recursos](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="dce56-154">For information about Resource Governor resource pools, workload groups, and classification, see [Resource Governor](../resource-governor/resource-governor.md).</span></span>  
  
 <span data-ttu-id="dce56-155">Las instrucciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] para estos pasos se describen en el procedimiento "Para configurar el regulador de recursos de modo que se limite el uso de CPU”. Después, se muestra un ejemplo de [!INCLUDE[tsql](../../includes/tsql-md.md)] del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="dce56-155">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for these steps are described in the procedure, "To configure Resource Governor for limiting CPU usage," which is followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of the procedure.</span></span>  
  
 <span data-ttu-id="dce56-156">**Para configurar el regulador de recursos (SQL Server Management Studio)**</span><span class="sxs-lookup"><span data-stu-id="dce56-156">**To configure Resource Governor (SQL Server Management Studio)**</span></span>  
  
-   [<span data-ttu-id="dce56-157">Configurar el regulador de recursos mediante una plantilla</span><span class="sxs-lookup"><span data-stu-id="dce56-157">Configure Resource Governor Using a Template</span></span>](../resource-governor/configure-resource-governor-using-a-template.md)  
  
-   [<span data-ttu-id="dce56-158">Crear un grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="dce56-158">Create a Resource Pool</span></span>](../resource-governor/create-a-resource-pool.md)  
  
-   [<span data-ttu-id="dce56-159">Crear un grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="dce56-159">Create a Workload Group</span></span>](../resource-governor/create-a-workload-group.md)  
  
### <a name="to-configure-resource-governor-for-limiting-cpu-usage-transact-sql"></a><span data-ttu-id="dce56-160">Para configurar el regulador de recursos de modo que se limite el uso de CPU (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dce56-160">To configure Resource Governor for limiting CPU usage (Transact-SQL)</span></span>  
  
1.  <span data-ttu-id="dce56-161">Emita una instrucción [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) para crear un grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="dce56-161">Issue a [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) statement to create a resource pool.</span></span> <span data-ttu-id="dce56-162">En el ejemplo de este procedimiento se utiliza la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="dce56-162">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="dce56-163">*CREATE RESOURCE POOL pool_name* WITH ( MAX_CPU_PERCENT = *value* );</span><span class="sxs-lookup"><span data-stu-id="dce56-163">*CREATE RESOURCE POOL pool_name* WITH ( MAX_CPU_PERCENT = *value* );</span></span>  
  
     <span data-ttu-id="dce56-164">*Value* es un número entero comprendido entre 1 y 100 que indica el porcentaje máximo medio de ancho banda de CPU.</span><span class="sxs-lookup"><span data-stu-id="dce56-164">*Value* is an integer from 1 to 100 that indicates the percentage of maximum average CPU bandwidth.</span></span> <span data-ttu-id="dce56-165">El valor adecuado depende del entorno.</span><span class="sxs-lookup"><span data-stu-id="dce56-165">The appropriate value depends on your environment.</span></span> <span data-ttu-id="dce56-166">A efectos de ilustración, en el ejemplo de este tema se utiliza un porcentaje del 20% (MAX_CPU_PERCENT = 20.)</span><span class="sxs-lookup"><span data-stu-id="dce56-166">For the purpose of illustration, the example in this topic uses 20%  percent (MAX_CPU_PERCENT = 20.)</span></span>  
  
2.  <span data-ttu-id="dce56-167">Emita una instrucción [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) para crear un grupo de cargas de trabajo para las operaciones de prioridad baja cuyo uso de CPU quiera regular.</span><span class="sxs-lookup"><span data-stu-id="dce56-167">Issue a [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) statement to create a workload group for low-priority operations whose CPU usage you want to govern.</span></span> <span data-ttu-id="dce56-168">En el ejemplo de este procedimiento se utiliza la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="dce56-168">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="dce56-169">CREATE WORKLOAD GROUP *group_name* USING *pool_name*;</span><span class="sxs-lookup"><span data-stu-id="dce56-169">CREATE WORKLOAD GROUP *group_name* USING *pool_name*;</span></span>  
  
3.  <span data-ttu-id="dce56-170">Emita una instrucción [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) para crear una función clasificadora que asigne el grupo de cargas de trabajo creado en el paso anterior al usuario del inicio de sesión de prioridad baja.</span><span class="sxs-lookup"><span data-stu-id="dce56-170">Issue a [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) statement to create a classifier function that maps the workload group created in the preceding step to the user of the low-priority login.</span></span> <span data-ttu-id="dce56-171">En el ejemplo de este procedimiento se utiliza la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="dce56-171">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="dce56-172">CREATE FUNCTION [*schema_name*.]*function_name*() RETURNS sysname</span><span class="sxs-lookup"><span data-stu-id="dce56-172">CREATE FUNCTION [*schema_name*.]*function_name*() RETURNS sysname</span></span>  
  
     <span data-ttu-id="dce56-173">WITH SCHEMABINDING</span><span class="sxs-lookup"><span data-stu-id="dce56-173">WITH SCHEMABINDING</span></span>  
  
     <span data-ttu-id="dce56-174">AS</span><span class="sxs-lookup"><span data-stu-id="dce56-174">AS</span></span>  
  
     <span data-ttu-id="dce56-175">BEGIN</span><span class="sxs-lookup"><span data-stu-id="dce56-175">BEGIN</span></span>  
  
     <span data-ttu-id="dce56-176">DECLARE @workload_group_name AS *sysname*</span><span class="sxs-lookup"><span data-stu-id="dce56-176">DECLARE @workload_group_name AS *sysname*</span></span>  
  
     <span data-ttu-id="dce56-177">IF (SUSER_NAME() = '*user_of_low_priority_login*')</span><span class="sxs-lookup"><span data-stu-id="dce56-177">IF (SUSER_NAME() = '*user_of_low_priority_login*')</span></span>  
  
     <span data-ttu-id="dce56-178">SET @workload_group_name = '*workload_group_name*'</span><span class="sxs-lookup"><span data-stu-id="dce56-178">SET @workload_group_name = '*workload_group_name*'</span></span>  
  
     <span data-ttu-id="dce56-179">RETURN @workload_group_name</span><span class="sxs-lookup"><span data-stu-id="dce56-179">RETURN @workload_group_name</span></span>  
  
     <span data-ttu-id="dce56-180">FIN</span><span class="sxs-lookup"><span data-stu-id="dce56-180">END</span></span>  
  
     <span data-ttu-id="dce56-181">Para obtener información sobre los componentes de esta instrucción CREATE FUNCTION, vea:</span><span class="sxs-lookup"><span data-stu-id="dce56-181">For information about the components of this CREATE FUNCTION statement, see:</span></span>  
  
    -   [<span data-ttu-id="dce56-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dce56-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
    -   [<span data-ttu-id="dce56-183">SUSER_SNAME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dce56-183">SUSER_SNAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/suser-sname-transact-sql)  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="dce56-184">SUSER_NAME es solo una de las diversas funciones del sistema que se pueden utilizar en una función clasificadora.</span><span class="sxs-lookup"><span data-stu-id="dce56-184">SUSER_NAME is just one of several system functions that can be used in a classifier function.</span></span> <span data-ttu-id="dce56-185">Para obtener más información, vea [Crear y probar una función clasificadora definida por el usuario](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span><span class="sxs-lookup"><span data-stu-id="dce56-185">For more information, see [Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span></span>  
  
    -   <span data-ttu-id="dce56-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dce56-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span></span>  
  
4.  <span data-ttu-id="dce56-187">Emita una instrucción [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) para registrar la función clasificadora con el regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="dce56-187">Issue an [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) statement to register the classifier function with Resource Governor.</span></span> <span data-ttu-id="dce56-188">En el ejemplo de este procedimiento se utiliza la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="dce56-188">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="dce56-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *schema_name*.*function_name*);</span><span class="sxs-lookup"><span data-stu-id="dce56-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *schema_name*.*function_name*);</span></span>  
  
5.  <span data-ttu-id="dce56-190">Emita una segunda instrucción ALTER RESOURCE GOVERNOR para aplicar los cambios a la configuración en memoria del regulador de recursos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="dce56-190">Issue a second ALTER RESOURCE GOVERNOR statement to apply the changes to the Resource Governor in-memory configuration, as follows:</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE;  
    ```  
  
### <a name="example-b-configuring-resource-governor-transact-sql"></a><span data-ttu-id="dce56-191">Ejemplo B: Configurar Resource Governor (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dce56-191">Example B: Configuring Resource Governor (Transact-SQL)</span></span>  
 <span data-ttu-id="dce56-192">En el ejemplo siguiente se realizan los pasos dentro de una única transacción:</span><span class="sxs-lookup"><span data-stu-id="dce56-192">The following example performs the following steps within a single transaction:</span></span>  
  
1.  <span data-ttu-id="dce56-193">Crea el grupo de recursos de servidor `pMAX_CPU_PERCENT_20` .</span><span class="sxs-lookup"><span data-stu-id="dce56-193">Creates the `pMAX_CPU_PERCENT_20` resource pool.</span></span>  
  
2.  <span data-ttu-id="dce56-194">Crea el grupo de cargas de trabajo `gMAX_CPU_PERCENT_20` .</span><span class="sxs-lookup"><span data-stu-id="dce56-194">Creates the `gMAX_CPU_PERCENT_20` workload group.</span></span>  
  
3.  <span data-ttu-id="dce56-195">Crea la función clasificadora `rgclassifier_MAX_CPU()` , que utiliza el nombre de usuario creado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="dce56-195">Creates the `rgclassifier_MAX_CPU()` classifier function, which uses the user name created in the preceding example.</span></span>  
  
4.  <span data-ttu-id="dce56-196">Registra la función clasificadora con el regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="dce56-196">Registers the classifier function with Resource Governor.</span></span>  
  
 <span data-ttu-id="dce56-197">Después de confirmar la transacción, el ejemplo aplica los cambios de configuración solicitados en las instrucciones ALTER WORKLOAD GROUP o ALTER RESOURCE POOL.</span><span class="sxs-lookup"><span data-stu-id="dce56-197">After committing the transaction, the example applies the configuration changes requested in the ALTER WORKLOAD GROUP or ALTER RESOURCE POOL statements.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dce56-198">En el ejemplo siguiente se usa el nombre de usuario del usuario de ejemplo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creado en "Ejemplo A: Configurar un inicio de sesión y un usuario (Transact-SQL)", *nombre_de_dominio*`\MAX_CPU`.</span><span class="sxs-lookup"><span data-stu-id="dce56-198">The following example uses the user name of the sample [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user created in "Example A: Setting Up a Login and User (Transact-SQL)," *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="dce56-199">Reemplace esto por el nombre del usuario del inicio de sesión que piensa usar para crear copias de seguridad comprimidas de prioridad baja.</span><span class="sxs-lookup"><span data-stu-id="dce56-199">Replace this with the name of the user of the login that you plan to use for creating low-priority compressed backups.</span></span>  
  
```sql  
-- Configure Resource Governor.  
BEGIN TRAN  
USE master;  
-- Create a resource pool that sets the MAX_CPU_PERCENT to 20%.   
CREATE RESOURCE POOL pMAX_CPU_PERCENT_20  
   WITH  
      (MAX_CPU_PERCENT = 20);  
GO  
-- Create a workload group to use this pool.   
CREATE WORKLOAD GROUP gMAX_CPU_PERCENT_20  
USING pMAX_CPU_PERCENT_20;  
GO  
-- Create a classification function.  
-- Note that any request that does not get classified goes into   
-- the 'Default' group.  
CREATE FUNCTION dbo.rgclassifier_MAX_CPU() RETURNS sysname   
WITH SCHEMABINDING  
AS  
BEGIN  
    DECLARE @workload_group_name AS sysname  
      IF (SUSER_NAME() = 'domain_name\MAX_CPU')  
          SET @workload_group_name = 'gMAX_CPU_PERCENT_20'  
    RETURN @workload_group_name  
END;  
GO  
  
-- Register the classifier function with Resource Governor.  
ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION= dbo.rgclassifier_MAX_CPU);  
COMMIT TRAN;  
GO  
-- Start Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
  
```  
  
 [<span data-ttu-id="dce56-200">&#91;Principio&#93;</span><span class="sxs-lookup"><span data-stu-id="dce56-200">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="verifying-the-classification-of-the-current-session-transact-sql"></a><a name="verifying"></a> <span data-ttu-id="dce56-201">Comprobar la clasificación de la sesión actual (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dce56-201">Verifying the Classification of the Current Session (Transact-SQL)</span></span>  
 <span data-ttu-id="dce56-202">Si lo desea, inicie sesión como el usuario que especificó en la función clasificadora y compruebe la clasificación de la sesión emitiendo la instrucción [SELECT](/sql/t-sql/queries/select-transact-sql) siguiente en el Explorador de objetos:</span><span class="sxs-lookup"><span data-stu-id="dce56-202">Optionally, log in as the user that you specified in your classifier function, and verify the session classification by issuing the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement in Object Explorer:</span></span>  
  
```sql  
USE master;  
SELECT sess.session_id, sess.login_name, sess.group_id, grps.name   
FROM sys.dm_exec_sessions AS sess   
JOIN sys.dm_resource_governor_workload_groups AS grps   
    ON sess.group_id = grps.group_id  
WHERE session_id > 50;  
GO  
```  
  
 <span data-ttu-id="dce56-203">En el panel de resultados, la columna **name** debe enumerar una o varias sesiones para el nombre del grupo de cargas de trabajo que especificó en la función clasificadora.</span><span class="sxs-lookup"><span data-stu-id="dce56-203">In the results pane, the **name** column should list one or more sessions for the workload-group name that you specified in your classifier function.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dce56-204">Para obtener información sobre las vistas de administración dinámica invocadas por esta instrucción SELECT, vea [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) y [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dce56-204">For information about the dynamic management views called by this SELECT statement, see [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span></span>  
  
 [<span data-ttu-id="dce56-205">&#91;Principio&#93;</span><span class="sxs-lookup"><span data-stu-id="dce56-205">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="compressing-backups-using-a-session-with-limited-cpu"></a><a name="creating_compressed_backup"></a> <span data-ttu-id="dce56-206">Comprimir las copias de seguridad utilizando una sesión con CPU limitada</span><span class="sxs-lookup"><span data-stu-id="dce56-206">Compressing Backups Using a Session with Limited CPU</span></span>  
 <span data-ttu-id="dce56-207">Para crear una copia de seguridad comprimida en una sesión con el uso máximo de CPU limitado, inicie sesión como el usuario especificado en la función clasificadora.</span><span class="sxs-lookup"><span data-stu-id="dce56-207">To create a compressed backup in a session with a limited maximum CPU, log in as the user specified in your classifier function.</span></span> <span data-ttu-id="dce56-208">En el comando de copia de seguridad, especifique WITH COMPRESSION ( [!INCLUDE[tsql](../../includes/tsql-md.md)] ) o seleccione **comprimir copia de seguridad** ( [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="dce56-208">In your backup command, either specify WITH COMPRESSION ([!INCLUDE[tsql](../../includes/tsql-md.md)]) or select **Compress backup** ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]).</span></span> <span data-ttu-id="dce56-209">Para crear una copia de seguridad comprimida de la base de datos, vea [Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dce56-209">To create a compressed database backup, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
### <a name="example-c-creating-a-compressed-backup-transact-sql"></a><span data-ttu-id="dce56-210">Ejemplo C: Crear una copia de seguridad comprimida (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dce56-210">Example C: Creating a Compressed Backup (Transact-SQL)</span></span>  
 <span data-ttu-id="dce56-211">En el ejemplo [BACKUP](/sql/t-sql/statements/backup-transact-sql) siguiente se crea una copia de seguridad completa comprimida de la base de datos [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] en un archivo de copia de seguridad al que se ha dado formato recientemente, `Z:\SQLServerBackups\AdvWorksData.bak`.</span><span class="sxs-lookup"><span data-stu-id="dce56-211">The following [BACKUP](/sql/t-sql/statements/backup-transact-sql) example creates a compressed full backup of the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database in a newly formatted backup file, `Z:\SQLServerBackups\AdvWorksData.bak`.</span></span>  
  
```sql  
--Run backup statement in the gBackup session.  
BACKUP DATABASE AdventureWorks2012 TO DISK='Z:\SQLServerBackups\AdvWorksData.bak'   
WITH   
   FORMAT,   
   MEDIADESCRIPTION='AdventureWorks2012 Compressed Data Backups'  
   DESCRIPTION='First database backup on AdventureWorks2012 Compressed Data Backups media set'  
   COMPRESSION;  
GO  
```  
  
 [<span data-ttu-id="dce56-212">&#91;Principio&#93;</span><span class="sxs-lookup"><span data-stu-id="dce56-212">&#91;Top&#93;</span></span>](#Top)  
  
## <a name="see-also"></a><span data-ttu-id="dce56-213">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dce56-213">See Also</span></span>  
 <span data-ttu-id="dce56-214">[Crear y probar una función clasificadora definida por el usuario](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="dce56-214">[Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span></span>  
 [<span data-ttu-id="dce56-215">Regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="dce56-215">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
