---
title: Ver una lista de bases de datos en una instancia de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- current databases
- databases currently on server [SQL Server]
- database list [SQL Server]
- viewing database list
- displaying database list
- databases [SQL Server], viewing
- servers [SQL Server], databases listed on
- listing databases
ms.assetid: 7ee7a789-db36-4be9-8a0e-0362a1e152dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 47283fa9065a0b9d6238dab804094d9a65d17897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749970"
---
# <a name="view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="8705d-102">Ver una lista de bases de datos en una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8705d-102">View a List of Databases on an Instance of SQL Server</span></span>
  <span data-ttu-id="8705d-103">En este tema se describe cómo ver una lista de bases de datos en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8705d-103">This topic describes how to view a list of databases on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8705d-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="8705d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8705d-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="8705d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8705d-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8705d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8705d-107">**Para ver una lista de bases de datos en una instancia de SQL Server, use:**</span><span class="sxs-lookup"><span data-stu-id="8705d-107">**To view a list of databases on an instance of SQL Server, using:**</span></span>  
  
     [<span data-ttu-id="8705d-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8705d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8705d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8705d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8705d-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8705d-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8705d-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8705d-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8705d-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="8705d-112">Permissions</span></span>  
 <span data-ttu-id="8705d-113">Si el autor de la llamada de **sys.databases** no es el propietario de la base de datos y la base de datos no es **maestra** o **tempdb**, los permisos mínimos necesarios para ver la fila correspondiente son el permiso ALTER ANY DATABASE o VIEW ANY DATABASE de nivel de servidor, o el permiso CREATE DATABASE en la base de datos **maestra** .</span><span class="sxs-lookup"><span data-stu-id="8705d-113">If the caller of **sys.databases** is not the owner of the database and the database is not **master** or **tempdb**, the minimum permissions required to see the corresponding row are ALTER ANY DATABASE or VIEW ANY DATABASE server-level permission, or CREATE DATABASE permission in the **master** database.</span></span> <span data-ttu-id="8705d-114">La base de datos a la que está conectado el autor de la llamada siempre se puede ver en **sys.databases**.</span><span class="sxs-lookup"><span data-stu-id="8705d-114">The database to which the caller is connected can always be viewed in **sys.databases**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8705d-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8705d-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="8705d-116">Para ver una lista de bases de datos en una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8705d-116">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="8705d-117">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="8705d-117">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8705d-118">Para ver una lista de todas las bases de datos de la instancia, expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="8705d-118">To see a list of all databases on the instance, expand **Databases**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8705d-119">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8705d-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="8705d-120">Para ver una lista de bases de datos en una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8705d-120">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="8705d-121">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8705d-121">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8705d-122">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="8705d-122">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8705d-123">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8705d-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8705d-124">En este ejemplo se devuelve una lista de las bases de datos de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8705d-124">This example returns a list of databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8705d-125">La lista incluye los nombres de las bases de datos, los id. de base de datos y las fechas en que se crearon las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="8705d-125">The list includes the names of the databases, their database IDs, and the dates when the databases were created.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT name, database_id, create_date  
FROM sys.databases ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="8705d-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8705d-126">See Also</span></span>  
 <span data-ttu-id="8705d-127">[Vistas de catálogo de archivos y bases de datos &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8705d-127">[Databases and Files Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="8705d-128">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8705d-128">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
