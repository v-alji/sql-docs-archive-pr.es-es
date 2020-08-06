---
title: Ver o cambiar el nivel de compatibilidad de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- compatibility levels [SQL Server], viewing
- compatibility [SQL Server], databases
- compatibility levels [SQL Server], changing
ms.assetid: 579867ec-57cb-4cb8-af35-9688c1e9e15d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35cf7af50eba333440c42a1bac428df1fff156b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749978"
---
# <a name="view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="c0356-102">Ver o cambiar el nivel de compatibilidad de una base de datos</span><span class="sxs-lookup"><span data-stu-id="c0356-102">View or Change the Compatibility Level of a Database</span></span>
  <span data-ttu-id="c0356-103">En este tema se describe cómo ver o cambiar el nivel de compatibilidad de una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0356-103">This topic describes how to view or change the compatibility level of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c0356-104">Antes de cambiar el nivel de compatibilidad de una base de datos, debería conocer el impacto que el cambio tendría en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c0356-104">Before you change the compatibility level of a database, you should understand the impact of the change on your applications.</span></span> <span data-ttu-id="c0356-105">Para obtener más información, vea [Nivel de compatibilidad de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="c0356-105">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
 <span data-ttu-id="c0356-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="c0356-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c0356-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="c0356-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c0356-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c0356-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c0356-109">**Para ver o cambiar el nivel de compatibilidad de una base de datos, use:**</span><span class="sxs-lookup"><span data-stu-id="c0356-109">**To view or change the compatibility level of a database, using:**</span></span>  
  
     [<span data-ttu-id="c0356-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0356-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c0356-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0356-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c0356-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="c0356-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c0356-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c0356-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c0356-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="c0356-114">Permissions</span></span>  
 <span data-ttu-id="c0356-115">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c0356-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c0356-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0356-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="c0356-117">Para ver o cambiar el nivel de compatibilidad de una base de datos</span><span class="sxs-lookup"><span data-stu-id="c0356-117">To view or change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="c0356-118">Después de conectarse a la instancia apropiada de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="c0356-118">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name.</span></span>  
  
2.  <span data-ttu-id="c0356-119">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="c0356-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="c0356-120">Haga clic con el botón derecho en la base de datos y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c0356-120">Right-click the database, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="c0356-121">Se abre el cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="c0356-121">The **Database Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="c0356-122">En el panel **Seleccionar una página** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="c0356-122">In the **Select a page** pane, click **Options**.</span></span>  
  
     <span data-ttu-id="c0356-123">El nivel de compatibilidad actual se muestra en el cuadro de lista **Nivel de compatibilidad** .</span><span class="sxs-lookup"><span data-stu-id="c0356-123">The current compatibility level is displayed in the **Compatibility level** list box.</span></span>  
  
5.  <span data-ttu-id="c0356-124">Para cambiar el nivel de compatibilidad, seleccione una opción diferente de la lista.</span><span class="sxs-lookup"><span data-stu-id="c0356-124">To change the compatibility level, select a different option from the list.</span></span> <span data-ttu-id="c0356-125">Las opciones son **SQL Server 2008 (100)**, **SQL Server 2012 (110)** o **SQL Server 2014 (120)**.</span><span class="sxs-lookup"><span data-stu-id="c0356-125">The choices are **SQL Server 2008 (100)**, **SQL Server 2012 (110)**, or **SQL Server 2014 (120)**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c0356-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0356-126">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-compatibility-level-of-a-database"></a><span data-ttu-id="c0356-127">Para ver el nivel de compatibilidad de una base de datos</span><span class="sxs-lookup"><span data-stu-id="c0356-127">To view the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="c0356-128">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0356-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0356-129">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c0356-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c0356-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c0356-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c0356-131">Este ejemplo devuelve el nivel de compatibilidad de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0356-131">This example returns the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="c0356-132">Para cambiar el nivel de compatibilidad de una base de datos</span><span class="sxs-lookup"><span data-stu-id="c0356-132">To change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="c0356-133">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0356-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0356-134">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c0356-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c0356-135">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c0356-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c0356-136">En este ejemplo se cambia el nivel de compatibilidad de [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0356-136">This example changes the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)].</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET COMPATIBILITY_LEVEL = 120;  
GO  
```  
  
  
