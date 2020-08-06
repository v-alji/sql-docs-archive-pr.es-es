---
title: Cambio de los valores de configuración de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database configuration [SQL Server]
- configuration options [SQL Server], databases
- modifying database configuration settings
ms.assetid: c29c3385-5043-400f-bb4e-044a4c9a9a4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f9edecefae5154bb66a65e38724d9e77a94fdbb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751129"
---
# <a name="change-the-configuration-settings-for-a-database"></a><span data-ttu-id="89b3f-102">Cambiar los valores de configuración de una base de datos</span><span class="sxs-lookup"><span data-stu-id="89b3f-102">Change the Configuration Settings for a Database</span></span>
  <span data-ttu-id="89b3f-103">En este tema se describe cómo cambiar las opciones de nivel de base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89b3f-103">This topic describes how to change database-level options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="89b3f-104">Las opciones son únicas para cada base de datos y no afectan a otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="89b3f-104">These options are unique to each database and do not affect other databases.</span></span>  
  
 <span data-ttu-id="89b3f-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="89b3f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="89b3f-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="89b3f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="89b3f-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="89b3f-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="89b3f-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="89b3f-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="89b3f-109">**Para cambiar la configuración de las opciones de una base de datos, use:**</span><span class="sxs-lookup"><span data-stu-id="89b3f-109">**To change the option settings for a database, using:**</span></span>  
  
     [<span data-ttu-id="89b3f-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="89b3f-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="89b3f-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="89b3f-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="89b3f-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="89b3f-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="89b3f-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="89b3f-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="89b3f-114">Solo el administrador del sistema o los propietarios de la base de datos, los miembros de los roles fijos de servidor **sysadmin** y **dbcreator** y de los roles fijos de base de datos **db_owner** pueden modificar estas opciones.</span><span class="sxs-lookup"><span data-stu-id="89b3f-114">Only the system administrator, database owner, members of the **sysadmin** and **dbcreator** fixed server roles and **db_owner** fixed database roles can modify these options.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="89b3f-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="89b3f-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="89b3f-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="89b3f-116">Permissions</span></span>  
 <span data-ttu-id="89b3f-117">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="89b3f-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="89b3f-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="89b3f-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="89b3f-119">Para cambiar la configuración de las opciones de una base de datos</span><span class="sxs-lookup"><span data-stu-id="89b3f-119">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="89b3f-120">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , expanda el servidor, expanda **Bases de datos**, haga clic con el botón derecho en una base de datos y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="89b3f-120">In Object Explorer, connect to a [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, expand the server, expand **Databases**, right-click a database, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="89b3f-121">En el cuadro de diálogo **Propiedades de la base de datos** , haga clic en **Opciones** para obtener acceso a la mayoría de los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="89b3f-121">In the **Database Properties** dialog box, click **Options** to access most of the configuration settings.</span></span> <span data-ttu-id="89b3f-122">Las configuraciones de archivo y grupo de archivos, la creación de reflejos y el trasvase de registros se encuentran en sus páginas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="89b3f-122">File and filegroup configurations, mirroring and log shipping are on their respective pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="89b3f-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="89b3f-123">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="89b3f-124">Para cambiar la configuración de las opciones de una base de datos</span><span class="sxs-lookup"><span data-stu-id="89b3f-124">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="89b3f-125">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89b3f-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="89b3f-126">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="89b3f-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="89b3f-127">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="89b3f-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="89b3f-128">En este ejemplo se establece el modelo de recuperación y las opciones de comprobación de páginas de datos para la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="89b3f-128">This example sets the recovery model and data page verification options for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase7](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase7)]  
  
 <span data-ttu-id="89b3f-129">Para ver más ejemplos, vea [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="89b3f-129">For more examples, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b3f-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89b3f-130">See Also</span></span>  
 <span data-ttu-id="89b3f-131">[Nivel de compatibilidad de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="89b3f-131">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 <span data-ttu-id="89b3f-132">[Reflejo de la base de datos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="89b3f-132">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="89b3f-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="89b3f-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="89b3f-134">[Cambiar el nombre de una base de datos](rename-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="89b3f-134">[Rename a Database](rename-a-database.md) </span></span>  
 [<span data-ttu-id="89b3f-135">Reducir una base de datos</span><span class="sxs-lookup"><span data-stu-id="89b3f-135">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
