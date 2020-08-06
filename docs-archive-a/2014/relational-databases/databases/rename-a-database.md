---
title: Cambio de nombre de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], renaming
- renaming databases
ms.assetid: 44c69d35-abcb-4da3-9370-5e0bc9a28496
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd25a78e3d3b9be2e7191ce6ed3d6bdcbb0f9606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672090"
---
# <a name="rename-a-database"></a><span data-ttu-id="4b165-102">Cambiar el nombre de una base de datos</span><span class="sxs-lookup"><span data-stu-id="4b165-102">Rename a Database</span></span>
  <span data-ttu-id="4b165-103">En este tema se describe cómo cambiar el nombre de una base de datos definida por el usuario en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b165-103">This topic describes how to rename a user-defined database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4b165-104">El nombre de la base de datos puede incluir cualquier carácter que se ajuste a las reglas para identificadores.</span><span class="sxs-lookup"><span data-stu-id="4b165-104">The name of the database can include any characters that follow the rules for identifiers.</span></span>  
  
 <span data-ttu-id="4b165-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4b165-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4b165-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4b165-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4b165-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4b165-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4b165-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4b165-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4b165-109">**Para cambiar el nombre de una base de datos, use:**</span><span class="sxs-lookup"><span data-stu-id="4b165-109">**To rename a database, using:**</span></span>  
  
     [<span data-ttu-id="4b165-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b165-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4b165-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b165-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="4b165-112">**Seguimiento:**  [Después de cambiar el nombre de una base de datos](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="4b165-112">**Follow Up:**  [After renaming a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4b165-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4b165-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4b165-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4b165-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4b165-115">No se puede cambiar el nombre de las bases de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="4b165-115">System databases cannot be renamed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4b165-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4b165-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4b165-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="4b165-117">Permissions</span></span>  
 <span data-ttu-id="4b165-118">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4b165-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4b165-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b165-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="4b165-120">Para cambiar el nombre de una base de datos</span><span class="sxs-lookup"><span data-stu-id="4b165-120">To rename a database</span></span>  
  
1.  <span data-ttu-id="4b165-121">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="4b165-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4b165-122">Asegúrese de que nadie usa la base de datos y luego [establezca la base de datos en modo de usuario único](set-a-database-to-single-user-mode.md).</span><span class="sxs-lookup"><span data-stu-id="4b165-122">Make sure that no one is using the database, and then [set the database to single-user mode](set-a-database-to-single-user-mode.md).</span></span>  
  
3.  <span data-ttu-id="4b165-123">Expanda **Bases de datos**, haga clic con el botón derecho en la base de datos cuyo nombre quiere cambiar y luego haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="4b165-123">Expand **Databases**, right-click the database to rename, and then click **Rename**.</span></span>  
  
4.  <span data-ttu-id="4b165-124">Escriba el nuevo nombre de la base de datos y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b165-124">Enter the new database name, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4b165-125">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b165-125">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="4b165-126">Para cambiar el nombre de una base de datos</span><span class="sxs-lookup"><span data-stu-id="4b165-126">To rename a database</span></span>  
  
1.  <span data-ttu-id="4b165-127">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b165-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4b165-128">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4b165-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4b165-129">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4b165-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4b165-130">Este ejemplo cambia el nombre de la base de datos `AdventureWorks2012` a `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="4b165-130">This example changes the name of the `AdventureWorks2012` database to `Northwind`.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
Modify Name = Northwind ;  
GO  
```  
  
###  <a name="TsqlExample"></a>   
##  <a name="follow-up-after-renaming-a-database"></a><a name="FollowUp"></a><span data-ttu-id="4b165-131">Seguimiento: después de cambiar el nombre de una base de datos</span><span class="sxs-lookup"><span data-stu-id="4b165-131">Follow Up: After renaming a database</span></span>  
 <span data-ttu-id="4b165-132">Después de cambiar el nombre de cualquier base de datos, realice una copia de seguridad de la base de datos **maestra** .</span><span class="sxs-lookup"><span data-stu-id="4b165-132">Back up the **master** database after you rename any database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b165-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b165-133">See Also</span></span>  
 <span data-ttu-id="4b165-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4b165-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="4b165-135">Identificadores de base de datos</span><span class="sxs-lookup"><span data-stu-id="4b165-135">Database Identifiers</span></span>](database-identifiers.md)  
  
  
