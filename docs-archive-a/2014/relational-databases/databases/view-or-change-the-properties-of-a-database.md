---
title: Ver o cambiar las propiedades de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- displaying databases
- database viewing [SQL Server]
- databases [SQL Server], viewing
- viewing databases
ms.assetid: 9e8ac097-84b7-46c7-85e3-c1e79f94d747
author: stevestein
ms.author: sstein
ms.openlocfilehash: d6aee7503ca02d47575be4e8103641f61d9696d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749961"
---
# <a name="view-or-change-the-properties-of-a-database"></a><span data-ttu-id="cc254-102">Ver o cambiar las propiedades de una base de datos</span><span class="sxs-lookup"><span data-stu-id="cc254-102">View or Change the Properties of a Database</span></span>
  <span data-ttu-id="cc254-103">En este tema se describe cómo ver o cambiar las propiedades de una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc254-103">This topic describes how to view or change the properties of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cc254-104">Después de cambiar una propiedad de la base de datos, la modificación surte efecto de inmediato.</span><span class="sxs-lookup"><span data-stu-id="cc254-104">After you change a database property, the modification takes effect immediately.</span></span>  
  
 <span data-ttu-id="cc254-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="cc254-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cc254-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="cc254-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cc254-107">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="cc254-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="cc254-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="cc254-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cc254-109">**Para ver o cambiar las propiedades de una base de datos, use:**</span><span class="sxs-lookup"><span data-stu-id="cc254-109">**To view or change the properties of a database, using:**</span></span>  
  
     [<span data-ttu-id="cc254-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc254-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cc254-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cc254-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cc254-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="cc254-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="cc254-113">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="cc254-113">Recommendations</span></span>  
  
-   <span data-ttu-id="cc254-114">Si AUTO_CLOSE es ON, algunas columnas de la vista de catálogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) y de la función DATABASEPROPERTYEX devuelven NULL porque la base de datos no está disponible para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="cc254-114">When AUTO_CLOSE is ON, some columns in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view and DATABASEPROPERTYEX function will return NULL because the database is unavailable to retrieve the data.</span></span> <span data-ttu-id="cc254-115">Para resolver este problema, ejecute la instrucción USE para abrir la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cc254-115">To resolve this, execute a USE statement to open the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cc254-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="cc254-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cc254-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="cc254-117">Permissions</span></span>  
 <span data-ttu-id="cc254-118">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cc254-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cc254-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc254-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-properties-of-a-database"></a><span data-ttu-id="cc254-120">Para ver o cambiar las propiedades de una base de datos</span><span class="sxs-lookup"><span data-stu-id="cc254-120">To view or change the properties of a database</span></span>  
  
1.  <span data-ttu-id="cc254-121">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="cc254-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cc254-122">Expanda **Bases de datos**, haga clic con el botón derecho en la base de datos que quiera ver y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cc254-122">Expand **Databases**, right-click the database to view, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="cc254-123">En el cuadro de diálogo **Propiedades de la base de datos** , seleccione una página para ver la información correspondiente.</span><span class="sxs-lookup"><span data-stu-id="cc254-123">In the **Database Properties** dialog box, select a page to view the corresponding information.</span></span> <span data-ttu-id="cc254-124">Por ejemplo, seleccione la página **Archivos** para ver información acerca de los archivos de datos y de registro.</span><span class="sxs-lookup"><span data-stu-id="cc254-124">For example, select the **Files** page to view data and log file information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cc254-125">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cc254-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-property-of-a-database-by-using-databasepropertyex"></a><span data-ttu-id="cc254-126">Para ver una propiedad de una base de datos con DATABASEPROPERTYEX</span><span class="sxs-lookup"><span data-stu-id="cc254-126">To view a property of a database by using DATABASEPROPERTYEX</span></span>  
  
1.  <span data-ttu-id="cc254-127">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc254-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cc254-128">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="cc254-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cc254-129">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="cc254-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="cc254-130">Este ejemplo usa la función de sistema [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) para devolver el estado de la opción de base de datos AUTO_SHRINK en la base de datos de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc254-130">This example uses the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) system function to return the status of the AUTO_SHRINK database option in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="cc254-131">Un valor devuelto de 1 significa que la opción está establecida en ON y un valor devuelto de 0 significa que la opción está establecida en OFF.</span><span class="sxs-lookup"><span data-stu-id="cc254-131">A return value of 1 means that the option is set to ON, and a return value of 0 means that the option is set to OFF.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT DATABASEPROPERTYEX('AdventureWorks2012', 'IsAutoShrink');  
GO  
  
```  
  
#### <a name="to-view-the-properties-of-a-database-by-querying-sysdatabases"></a><span data-ttu-id="cc254-132">Para ver las propiedades de una base de datos consultando sys.databases</span><span class="sxs-lookup"><span data-stu-id="cc254-132">To view the properties of a database by querying sys.databases</span></span>  
  
1.  <span data-ttu-id="cc254-133">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc254-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cc254-134">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="cc254-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cc254-135">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="cc254-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="cc254-136">En este ejemplo se consulta la vista de catálogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) para ver varias propiedades de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc254-136">This example queries the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to view several properties of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="cc254-137">Este ejemplo devuelve el número de id. de base de datos (`database_id`), un valor que indica si la base de datos es de solo lectura o de lectura y escritura (`is_read_only`), la intercalación de la base de datos (`collation_name`) y el nivel de compatibilidad de la base de datos (`compatibility_level`).</span><span class="sxs-lookup"><span data-stu-id="cc254-137">This example returns the database ID number (`database_id`), whether the database is read-only or read-write (`is_read_only`), the collation for the database (`collation_name`), and the database compatibility level (`compatibility_level`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT database_id, is_read_only, collation_name, compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-properties-of-a-database"></a><span data-ttu-id="cc254-138">Para cambiar las propiedades de una base de datos</span><span class="sxs-lookup"><span data-stu-id="cc254-138">To change the properties of a database</span></span>  
  
1.  <span data-ttu-id="cc254-139">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc254-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cc254-140">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="cc254-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cc254-141">Copie y pegue el ejemplo siguiente en la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="cc254-141">Copy and paste the following example into the query window.</span></span> <span data-ttu-id="cc254-142">El ejemplo determina el estado de aislamiento de instantánea en la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , cambia el estado de la propiedad y comprueba el cambio.</span><span class="sxs-lookup"><span data-stu-id="cc254-142">The example determines the state of snapshot isolation on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, changes the state of the property, and then verifies the change.</span></span>  
  
     <span data-ttu-id="cc254-143">Para determinar el estado de aislamiento de instantánea, seleccione la primera instrucción `SELECT` y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="cc254-143">To determine the state of snapshot isolation, select the first `SELECT` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="cc254-144">Para cambiar el estado de aislamiento de instantánea, seleccione la instrucción `ALTER DATABASE` y haga clic en **Ejecutar**de.</span><span class="sxs-lookup"><span data-stu-id="cc254-144">To change the state of snapshot isolation, select the `ALTER DATABASE` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="cc254-145">Para comprobar el cambio, seleccione la segunda instrucción `SELECT` y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="cc254-145">To verify the change, select the second `SELECT` statement, and click **Execute**.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase9](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase9)]  
  
## <a name="see-also"></a><span data-ttu-id="cc254-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cc254-146">See Also</span></span>  
 <span data-ttu-id="cc254-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc254-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="cc254-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="cc254-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="cc254-149">[Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="cc254-149">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="cc254-150">[Reflejo de la base de datos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="cc254-150">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="cc254-151">[Nivel de compatibilidad de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="cc254-151">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 [<span data-ttu-id="cc254-152">Opciones File y Filegroup de ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc254-152">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
  
