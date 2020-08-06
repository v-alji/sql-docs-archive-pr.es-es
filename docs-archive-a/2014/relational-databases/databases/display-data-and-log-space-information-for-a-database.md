---
title: Mostrar la información del espacio ocupado por los datos y el registro de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], space
- status information [SQL Server], space
- displaying space information
- disk space [SQL Server], displaying
- databases [SQL Server], space used
- viewing space information
- space allocation [SQL Server], displaying
- data space [SQL Server]
ms.assetid: c7b99463-4bab-4e9b-9217-fcb0898dc757
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1beb8cdedbc2b72eadeeb350ee1c3b6d16218205
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751093"
---
# <a name="display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="2aba8-102">Mostrar la información del espacio ocupado por los datos y el registro de una base de datos</span><span class="sxs-lookup"><span data-stu-id="2aba8-102">Display Data and Log Space Information for a Database</span></span>
  <span data-ttu-id="2aba8-103">En este tema se describe cómo mostrar la información del espacio ocupado por los datos y el registro de una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2aba8-103">This topic describes how to display the data and log space information for a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2aba8-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="2aba8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2aba8-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="2aba8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2aba8-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2aba8-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2aba8-107">**Para mostrar la información del espacio ocupado por los datos y el registro, use:**</span><span class="sxs-lookup"><span data-stu-id="2aba8-107">**To display data and log space information for a database, using:**</span></span>  
  
     [<span data-ttu-id="2aba8-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2aba8-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2aba8-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2aba8-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2aba8-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2aba8-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2aba8-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2aba8-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2aba8-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="2aba8-112">Permissions</span></span>  
 <span data-ttu-id="2aba8-113">El permiso para ejecutar **sp_spaceused** se otorga al rol **public** .</span><span class="sxs-lookup"><span data-stu-id="2aba8-113">Permission to execute **sp_spaceused** is granted to the **public** role.</span></span> <span data-ttu-id="2aba8-114">Solo los miembros del rol fijo de base de datos **db_owner** pueden especificar el parámetro **@updateusage** .</span><span class="sxs-lookup"><span data-stu-id="2aba8-114">Only members of the **db_owner** fixed database role can specify the **@updateusage** parameter.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2aba8-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2aba8-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="2aba8-116">Para mostrar la información del espacio ocupado por los datos y el registro de una base de datos</span><span class="sxs-lookup"><span data-stu-id="2aba8-116">To display data and log space information for a database</span></span>  
  
1.  <span data-ttu-id="2aba8-117">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="2aba8-117">In Object Explorer, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2aba8-118">Expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="2aba8-118">Expand **Databases**.</span></span>  
  
3.  <span data-ttu-id="2aba8-119">Haga clic con el botón derecho en una base de datos, seleccione **Informes**e **Informes estándar**y, luego, haga clic en **Uso de disco**.</span><span class="sxs-lookup"><span data-stu-id="2aba8-119">Right-click a database, point to **Reports**, point to **Standard Reports,**, and then click **Disk Usage**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2aba8-120">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2aba8-120">Using Transact-SQL</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-using-sp_spaceused"></a><span data-ttu-id="2aba8-121">Para mostrar la información del espacio ocupado por los datos y el registro de una base de datos mediante sp_spaceused</span><span class="sxs-lookup"><span data-stu-id="2aba8-121">To display data and log space information for a database by using sp_spaceused</span></span>  
  
1.  <span data-ttu-id="2aba8-122">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2aba8-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2aba8-123">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2aba8-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2aba8-124">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2aba8-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2aba8-125">En este ejemplo se usa el procedimiento almacenado del sistema [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) para notificar información de espacio en disco para la tabla `Vendor` y sus índices.</span><span class="sxs-lookup"><span data-stu-id="2aba8-125">This example uses the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure to report disk space information for the `Vendor` table and its indexes.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_spaceused N'Purchasing.Vendor';  
GO  
```  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-querying-sysdatabase_files"></a><span data-ttu-id="2aba8-126">Para mostrar la información del espacio ocupado por los datos y el registro de una base de datos mediante una consulta a sys.database_files</span><span class="sxs-lookup"><span data-stu-id="2aba8-126">To display data and log space information for a database by querying sys.database_files</span></span>  
  
1.  <span data-ttu-id="2aba8-127">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2aba8-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2aba8-128">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2aba8-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2aba8-129">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2aba8-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2aba8-130">En este ejemplo se consulta la vista de catálogo [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) para devolver información específica sobre los archivos de datos y de registro de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2aba8-130">This example queries the [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) catalog view to return specific information about the data and log files in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT file_id, name, type_desc, physical_name, size, max_size  
FROM sys.database_files ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="2aba8-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2aba8-131">See Also</span></span>  
 <span data-ttu-id="2aba8-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2aba8-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="2aba8-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2aba8-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="2aba8-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2aba8-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span></span>  
 <span data-ttu-id="2aba8-135">[Agregar archivos de datos o de registro a una base de datos](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="2aba8-135">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="2aba8-136">Eliminar archivos de datos o de registro de una base de datos</span><span class="sxs-lookup"><span data-stu-id="2aba8-136">Delete Data or Log Files from a Database</span></span>](delete-data-or-log-files-from-a-database.md)  
  
  
