---
title: Migración a una base de datos parcialmente independiente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, migrating to
ms.assetid: 90faac38-f79e-496d-b589-e8b2fe01c562
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6142d46dc0540e5998fa66d463538d1453a17d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751058"
---
# <a name="migrate-to-a-partially-contained-database"></a><span data-ttu-id="60e6e-102">Migrate to a Partially Contained Database</span><span class="sxs-lookup"><span data-stu-id="60e6e-102">Migrate to a Partially Contained Database</span></span>
  <span data-ttu-id="60e6e-103">En este tema se describe cómo preparar el cambio al modelo de base de datos parcialmente independiente y, a continuación, se proporcionan los pasos de migración.</span><span class="sxs-lookup"><span data-stu-id="60e6e-103">This topic discusses how to prepare to change to the partially contained database model and then provides the migration steps.</span></span>  
  
 <span data-ttu-id="60e6e-104">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="60e6e-104">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="60e6e-105">Preparar la migración de una base de datos</span><span class="sxs-lookup"><span data-stu-id="60e6e-105">Preparing to Migrate a Database</span></span>](#prepare)  
  
-   [<span data-ttu-id="60e6e-106">Habilitar bases de datos independientes</span><span class="sxs-lookup"><span data-stu-id="60e6e-106">Enable Contained Databases</span></span>](#enable)  
  
-   [<span data-ttu-id="60e6e-107">Convertir una base de datos en parcialmente independiente</span><span class="sxs-lookup"><span data-stu-id="60e6e-107">Converting a Database to Partially Contained</span></span>](#convert)  
  
-   [<span data-ttu-id="60e6e-108">Migrar usuarios a usuarios de base de datos independiente</span><span class="sxs-lookup"><span data-stu-id="60e6e-108">Migrating Users to Contained Database Users</span></span>](#users)  
  
##  <a name="preparing-to-migrate-a-database"></a><a name="prepare"></a> <span data-ttu-id="60e6e-109">Preparar la migración de una base de datos</span><span class="sxs-lookup"><span data-stu-id="60e6e-109">Preparing to Migrate a Database</span></span>  
 <span data-ttu-id="60e6e-110">Revise los siguientes aspectos cuando vaya a migrar una base de datos al modelo de base de datos parcialmente independiente.</span><span class="sxs-lookup"><span data-stu-id="60e6e-110">Review the following items when considering migrating a database to the partially contained database model.</span></span>  
  
-   <span data-ttu-id="60e6e-111">Debe entender el modelo de base de datos parcialmente independiente.</span><span class="sxs-lookup"><span data-stu-id="60e6e-111">You should understand the partially contained database model.</span></span> <span data-ttu-id="60e6e-112">Para más información, consulte [Contained Databases](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="60e6e-112">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
-   <span data-ttu-id="60e6e-113">Debe conocer los riesgos que son exclusivos de las bases de datos parcialmente independientes.</span><span class="sxs-lookup"><span data-stu-id="60e6e-113">You should understand risks that are unique to partially contained databases.</span></span> <span data-ttu-id="60e6e-114">Para más información, vea [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="60e6e-114">For more information, see [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span></span>  
  
-   <span data-ttu-id="60e6e-115">Las bases de datos independientes no admiten la replicación, la captura de datos modificados ni el seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="60e6e-115">Contained databases do not support replication, change data capture, or change tracking.</span></span> <span data-ttu-id="60e6e-116">Asegúrese de que la base de datos no utiliza estas características.</span><span class="sxs-lookup"><span data-stu-id="60e6e-116">Confirm the database does not use these features.</span></span>  
  
-   <span data-ttu-id="60e6e-117">Revise la lista de características de base de datos que se modifican en las bases de datos parcialmente independientes.</span><span class="sxs-lookup"><span data-stu-id="60e6e-117">Review the list of database features that are modified for partially contained databases.</span></span> <span data-ttu-id="60e6e-118">Para obtener más información, vea [Características modificadas &#40;base de datos independiente&#41;](modified-features-contained-database.md).</span><span class="sxs-lookup"><span data-stu-id="60e6e-118">For more information, see [Modified Features &#40;Contained Database&#41;](modified-features-contained-database.md).</span></span>  
  
-   <span data-ttu-id="60e6e-119">Consulte [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) para encontrar objetos o características sin contención en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="60e6e-119">Query [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) to find uncontained objects or features in the database.</span></span> <span data-ttu-id="60e6e-120">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="60e6e-120">For more information, see.</span></span>  
  
-   <span data-ttu-id="60e6e-121">Supervise el XEvent **database_uncontained_usage** para ver cuándo se usan características sin contención.</span><span class="sxs-lookup"><span data-stu-id="60e6e-121">Monitor the **database_uncontained_usage** XEvent to see when uncontained features are used.</span></span>  
  
##  <a name="enable-contained-databases"></a><a name="enable"></a> <span data-ttu-id="60e6e-122">Habilitar bases de datos independientes</span><span class="sxs-lookup"><span data-stu-id="60e6e-122">Enable Contained Databases</span></span>  
 <span data-ttu-id="60e6e-123">Las bases de datos independientes deben estar habilitadas en la instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]para poder crear bases de datos independientes.</span><span class="sxs-lookup"><span data-stu-id="60e6e-123">Contained databases must be enabled on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], before contained databases can be created.</span></span>  
  
### <a name="enabling-contained-databases-using-transact-sql"></a><span data-ttu-id="60e6e-124">Habilitar las bases de datos independientes mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60e6e-124">Enabling Contained Databases Using Transact-SQL</span></span>  
 <span data-ttu-id="60e6e-125">En el siguiente ejemplo se habilitan las bases de datos independientes en la instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60e6e-125">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE ;  
GO  
```  
  
#### <a name="enabling-contained-databases-using-management-studio"></a><span data-ttu-id="60e6e-126">Habilitar las bases de datos independientes mediante Management Studio</span><span class="sxs-lookup"><span data-stu-id="60e6e-126">Enabling Contained Databases Using Management Studio</span></span>  
 <span data-ttu-id="60e6e-127">En el siguiente ejemplo se habilitan las bases de datos independientes en la instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60e6e-127">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="60e6e-128">En el Explorador de objetos, haga clic con el botón derecho en el nombre del servidor y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="60e6e-128">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="60e6e-129">En la página **Avanzadas** , en la sección **Contención** , establezca la opción **Habilitar bases de datos independientes** en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="60e6e-129">On the **Advanced** page, in the **Containment** section, set the **Enable Contained Databases** option to **True**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="converting-a-database-to-partially-contained"></a><a name="convert"></a> <span data-ttu-id="60e6e-130">Convertir una base de datos en parcialmente independiente</span><span class="sxs-lookup"><span data-stu-id="60e6e-130">Converting a Database to Partially Contained</span></span>  
 <span data-ttu-id="60e6e-131">Una base de datos se convierte en base de datos independiente cambiando la **CONTAINMENT** opción.</span><span class="sxs-lookup"><span data-stu-id="60e6e-131">A database is converted to a contained database by changing the **CONTAINMENT** option.</span></span>  
  
### <a name="converting-a-database-to-partially-contained-using-transact-sql"></a><span data-ttu-id="60e6e-132">Convertir una base de datos en parcialmente independiente mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60e6e-132">Converting a Database to Partially Contained Using Transact-SQL</span></span>  
 <span data-ttu-id="60e6e-133">En el siguiente ejemplo se convierte en parcialmente independiente una base de datos denominada `Accounting` .</span><span class="sxs-lookup"><span data-stu-id="60e6e-133">The following example converts a database named `Accounting` to a partially contained database.</span></span>  
  
```sql  
USE [master]  
GO  
ALTER DATABASE [Accounting] SET CONTAINMENT = PARTIAL  
GO  
```  
  
### <a name="converting-a-database-to-partially-contained-using-management-studio"></a><span data-ttu-id="60e6e-134">Convertir una base de datos en parcialmente independiente mediante Management Studio</span><span class="sxs-lookup"><span data-stu-id="60e6e-134">Converting a Database to Partially contained Using Management Studio</span></span>  
 <span data-ttu-id="60e6e-135">En el siguiente ejemplo se convierte una base de datos en una base de datos parcialmente independiente.</span><span class="sxs-lookup"><span data-stu-id="60e6e-135">The following example converts a database to a partially contained database.</span></span>  
  
1.  <span data-ttu-id="60e6e-136">En el Explorador de objetos, expanda **Bases de datos**, haga clic con el botón derecho en la base de datos que quiera convertir y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="60e6e-136">In Object Explorer, expand **Databases**, right-click the database to be converted, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="60e6e-137">En la página **Opciones** , cambie la opción **Tipo de contención** a **Parcial**.</span><span class="sxs-lookup"><span data-stu-id="60e6e-137">On the **Options** page, change the **Containment type** option to **Partial**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="migrating-users-to-contained-database-users"></a><a name="users"></a> <span data-ttu-id="60e6e-138">Migrar usuarios a usuarios de base de datos independiente</span><span class="sxs-lookup"><span data-stu-id="60e6e-138">Migrating Users to Contained Database Users</span></span>  
 <span data-ttu-id="60e6e-139">En el siguiente ejemplo, se realiza la migración de todos los usuarios basados en inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a usuarios de base de datos independiente con contraseñas.</span><span class="sxs-lookup"><span data-stu-id="60e6e-139">The following example migrates all users that are based on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins to contained database users with passwords.</span></span> <span data-ttu-id="60e6e-140">En el ejemplo se excluyen los inicios de sesión que no están habilitados.</span><span class="sxs-lookup"><span data-stu-id="60e6e-140">The example excludes logins that are not enabled.</span></span> <span data-ttu-id="60e6e-141">El ejemplo se debe ejecutar en la base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="60e6e-141">The example must be executed in the contained database.</span></span>  
  
```sql  
DECLARE @username sysname ;  
DECLARE user_cursor CURSOR  
    FOR   
        SELECT dp.name   
        FROM sys.database_principals AS dp  
        JOIN sys.server_principals AS sp   
        ON dp.sid = sp.sid  
        WHERE dp.authentication_type = 1 AND sp.is_disabled = 0;  
OPEN user_cursor  
FETCH NEXT FROM user_cursor INTO @username  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        EXECUTE sp_migrate_user_to_contained   
        @username = @username,  
        @rename = N'keep_name',  
        @disablelogin = N'disable_login';  
    FETCH NEXT FROM user_cursor INTO @username  
    END  
CLOSE user_cursor ;  
DEALLOCATE user_cursor ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="60e6e-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60e6e-142">See Also</span></span>  
 <span data-ttu-id="60e6e-143">[Bases de datos independientes](contained-databases.md) </span><span class="sxs-lookup"><span data-stu-id="60e6e-143">[Contained Databases](contained-databases.md) </span></span>  
 <span data-ttu-id="60e6e-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="60e6e-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span></span>  
 [<span data-ttu-id="60e6e-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60e6e-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql)  
  
  
