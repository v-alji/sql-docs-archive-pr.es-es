---
title: Eliminación de archivos de datos o de registro de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- deleting files
- removing files
- removing data
- data deletions [SQL Server]
- file deletion [SQL Server]
- deleting data
ms.assetid: 0db4018c-ce2c-4ba1-bb29-1e4f3791c925
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6f7bd170e085e9bc94b00446545850e905efaa34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751094"
---
# <a name="delete-data-or-log-files-from-a-database"></a><span data-ttu-id="3ef72-102">Eliminar archivos de datos o de registro de una base de datos</span><span class="sxs-lookup"><span data-stu-id="3ef72-102">Delete Data or Log Files from a Database</span></span>
  <span data-ttu-id="3ef72-103">En este tema se describe cómo eliminar archivos de datos o de registro en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ef72-103">This topic describes how to delete data or log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3ef72-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="3ef72-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="3ef72-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3ef72-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="3ef72-106">Para poder eliminar un archivo debe estar vacío.</span><span class="sxs-lookup"><span data-stu-id="3ef72-106">A file must be empty before it can be deleted.</span></span> <span data-ttu-id="3ef72-107">Para obtener más información, vea [Reducir un archivo](shrink-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="3ef72-107">For more information, see [Shrink a File](shrink-a-file.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3ef72-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3ef72-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3ef72-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="3ef72-109">Permissions</span></span>  
 <span data-ttu-id="3ef72-110">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3ef72-110">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3ef72-111">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ef72-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="3ef72-112">Para eliminar archivos de datos o de registro de una base de datos</span><span class="sxs-lookup"><span data-stu-id="3ef72-112">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="3ef72-113">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="3ef72-113">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3ef72-114">Expanda **Bases de datos**, haga clic con el botón derecho en la base de datos de la que quiera eliminar el archivo y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3ef72-114">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3ef72-115">Seleccione la página **Archivos** .</span><span class="sxs-lookup"><span data-stu-id="3ef72-115">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="3ef72-116">En la cuadrícula **Archivos de base de datos** , seleccione el archivo que desee eliminar y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="3ef72-116">In the **Database files** grid, select the file to delete and then click **Remove**.</span></span>  
  
5.  <span data-ttu-id="3ef72-117">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ef72-117">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3ef72-118">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3ef72-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="3ef72-119">Para eliminar archivos de datos o de registro de una base de datos</span><span class="sxs-lookup"><span data-stu-id="3ef72-119">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="3ef72-120">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ef72-120">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3ef72-121">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="3ef72-121">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3ef72-122">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3ef72-122">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3ef72-123">Este ejemplo quita el archivo `test1dat4`.</span><span class="sxs-lookup"><span data-stu-id="3ef72-123">This example removes the file `test1dat4`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase4](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase4)]  
  
 <span data-ttu-id="3ef72-124">Para obtener más ejemplos, vea [Opciones File y Filegroup de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="3ef72-124">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef72-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ef72-125">See Also</span></span>  
 <span data-ttu-id="3ef72-126">[Reducir una base de datos](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="3ef72-126">[Shrink a Database](shrink-a-database.md) </span></span>  
 [<span data-ttu-id="3ef72-127">Agregar archivos de datos o de registro a una base de datos</span><span class="sxs-lookup"><span data-stu-id="3ef72-127">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
