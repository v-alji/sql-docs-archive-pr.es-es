---
title: Aumentar el tamaño de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], size
- increasing database size
- database size [SQL Server], increasing
- size [SQL Server], databases
ms.assetid: 14f4206d-3afa-4ba9-9849-23e81d63306d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 71dcb00b3f5525f7059fc54911baed929f763008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751086"
---
# <a name="increase-the-size-of-a-database"></a><span data-ttu-id="7f4e2-102">Aumentar el tamaño de una base de datos</span><span class="sxs-lookup"><span data-stu-id="7f4e2-102">Increase the Size of a Database</span></span>
  <span data-ttu-id="7f4e2-103">En este tema se describe cómo aumentar el tamaño de una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f4e2-103">This topic describes how to increase the size of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7f4e2-104">La base de datos se expande aumentando el tamaño de los datos o el archivo de registro existentes, o bien agregando un archivo nuevo a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-104">The database is expanded by either increasing the size of an existing data or log file or by adding a new file to the database.</span></span>  
  
 <span data-ttu-id="7f4e2-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="7f4e2-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7f4e2-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="7f4e2-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7f4e2-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7f4e2-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7f4e2-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7f4e2-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7f4e2-109">**Para aumentar el tamaño de una base de datos, use:**</span><span class="sxs-lookup"><span data-stu-id="7f4e2-109">**To increase the size of a database, using:**</span></span>  
  
     [<span data-ttu-id="7f4e2-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7f4e2-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7f4e2-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7f4e2-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7f4e2-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7f4e2-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7f4e2-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7f4e2-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7f4e2-114">No se puede agregar o quitar un archivo mientras se está ejecutando una instrucción BACKUP.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-114">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7f4e2-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7f4e2-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7f4e2-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="7f4e2-116">Permissions</span></span>  
 <span data-ttu-id="7f4e2-117">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7f4e2-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7f4e2-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="7f4e2-119">Para aumentar el tamaño de una base de datos</span><span class="sxs-lookup"><span data-stu-id="7f4e2-119">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="7f4e2-120">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7f4e2-121">Expanda **Bases de datos**, haga clic con el botón derecho en la base de datos cuyo tamaño quiera aumentar y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-121">Expand **Databases**, right-click the database to increase, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7f4e2-122">En **Propiedades de la base de datos**, seleccione la página **Archivos** .</span><span class="sxs-lookup"><span data-stu-id="7f4e2-122">In **Database Properties**, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="7f4e2-123">Para aumentar el tamaño de un archivo existente, aumente el valor de la columna **Tamaño inicial (MB)** correspondiente al archivo.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-123">To increase the size of an existing file, increase the value in the **Initial Size (MB)** column for the file.</span></span> <span data-ttu-id="7f4e2-124">Debe aumentar el tamaño de la base datos en 1 megabyte como mínimo.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-124">You must increase the size of the database by at least 1 megabyte.</span></span>  
  
5.  <span data-ttu-id="7f4e2-125">Para aumentar el tamaño de una base de datos agregando un nuevo archivo, haga clic en **Agregar** y especifique los valores de dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-125">To increase the size of the database by adding a new file, click **Add** and then enter the values for the new file.</span></span> <span data-ttu-id="7f4e2-126">Para obtener más información, consulte [Agregar archivos de datos o de registro a una base de datos](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="7f4e2-126">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
6.  <span data-ttu-id="7f4e2-127">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-127">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7f4e2-128">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7f4e2-128">Using Transact-SQL</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="7f4e2-129">Para aumentar el tamaño de una base de datos</span><span class="sxs-lookup"><span data-stu-id="7f4e2-129">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="7f4e2-130">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f4e2-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7f4e2-131">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7f4e2-132">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7f4e2-133">Este ejemplo aumenta el tamaño del archivo `test1dat3`.</span><span class="sxs-lookup"><span data-stu-id="7f4e2-133">This example increases the size of the file `test1dat3`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase5](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase5)]  
  
 <span data-ttu-id="7f4e2-134">Para obtener más ejemplos, vea [Opciones File y Filegroup de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="7f4e2-134">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f4e2-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f4e2-135">See Also</span></span>  
 <span data-ttu-id="7f4e2-136">[Agregar archivos de datos o de registro a una base de datos](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="7f4e2-136">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="7f4e2-137">Reducir una base de datos</span><span class="sxs-lookup"><span data-stu-id="7f4e2-137">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
