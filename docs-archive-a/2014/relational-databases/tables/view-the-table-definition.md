---
title: Ver la definición de tabla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- showing table properties
- displaying table properties
- tables [SQL Server], properties
- viewing table properties
ms.assetid: 1865fb7c-f480-4100-9007-df5364cd002a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53170a78a104bfce4b4e4177015461f2eb9093e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678117"
---
# <a name="view-the-table-definition"></a><span data-ttu-id="a5473-102">Vea la definición de tabla</span><span class="sxs-lookup"><span data-stu-id="a5473-102">View the Table Definition</span></span>
  <span data-ttu-id="a5473-103">Puede mostrar las propiedades de una tabla en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5473-103">You can display properties for a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a5473-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a5473-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a5473-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a5473-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a5473-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a5473-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a5473-107">**Para mostrar las propiedades de la tabla con:**</span><span class="sxs-lookup"><span data-stu-id="a5473-107">**To display table properties, using:**</span></span>  
  
     [<span data-ttu-id="a5473-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a5473-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a5473-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a5473-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a5473-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a5473-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a5473-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a5473-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a5473-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="a5473-112">Permissions</span></span>  
 <span data-ttu-id="a5473-113">Solamente puede ver las propiedades de una tabla si es propietario de la tabla o tiene concedidos permisos para esa tabla.</span><span class="sxs-lookup"><span data-stu-id="a5473-113">You can only see properties in a table if you either own the table or have been granted permissions to that table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a5473-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a5473-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-table-properties-in-the-properties-window"></a><span data-ttu-id="a5473-115">Para mostrar las propiedades de la tabla en la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="a5473-115">To show table properties in the Properties window</span></span>  
  
1.  <span data-ttu-id="a5473-116">En el Explorador de objetos, seleccione la tabla cuyas propiedades desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="a5473-116">In Object Explorer, select the table for which you want to show properties.</span></span>  
  
2.  <span data-ttu-id="a5473-117">Haga clic con el botón derecho en la tabla y elija **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="a5473-117">Right-click the table and choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="a5473-118">Para obtener más información, consulte [Table Properties](table-properties-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="a5473-118">For more information, see [Table Properties](table-properties-ssms.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a5473-119">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a5473-119">Using Transact-SQL</span></span>  
  
#### <a name="to-show-table-properties"></a><span data-ttu-id="a5473-120">Para mostrar las propiedades de una tabla</span><span class="sxs-lookup"><span data-stu-id="a5473-120">To show table properties</span></span>  
  
1.  <span data-ttu-id="a5473-121">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5473-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a5473-122">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="a5473-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a5473-123">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a5473-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a5473-124">El ejemplo devuelve todas las columnas de la vista de catálogo `sys.tables` para el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="a5473-124">The example returns all columns from the `sys.tables` catalog view for the specified object.</span></span>  
  
    ```  
    SELECT * FROM sys.tables  
    WHERE object_id = 1973582069;  
  
    ```  
  
 <span data-ttu-id="a5473-125">Para obtener más información, vea [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a5473-125">For more information, see [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
