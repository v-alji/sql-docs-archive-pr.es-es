---
title: Agregar tabla (cuadro de diálogo, diseñadores de consultas y vistas) (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.query.addtable
- vdtsql.chm:65565
ms.assetid: fce7adcc-4cf5-4a52-9203-11c13d1ecf08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d7bf30cbdd37927735c36f184208a1ded957763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670749"
---
# <a name="add-table-dialog-box-query-and-view-designers-visual-database-tools"></a><span data-ttu-id="405cf-102">Agregar tabla (cuadro de diálogo, Diseñadores de consultas y vistas, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="405cf-102">Add Table Dialog Box (Query and View Designers) (Visual Database Tools)</span></span>
  <span data-ttu-id="405cf-103">Este cuadro de diálogo permite agregar tablas, vistas, funciones definidas por el usuario o sinónimos a una consulta o una vista.</span><span class="sxs-lookup"><span data-stu-id="405cf-103">This dialog box lets you add tables, views, user-defined functions, or synonyms to a query or view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="405cf-104">Si se publica la tabla para la replicación, debe modificar el esquema mediante la instrucción Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) u Objetos de administración de SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="405cf-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="405cf-105">Si se modifica el esquema mediante el Diseñador de tablas o el Diseñador de diagramas de base de datos, se intentará eliminar la tabla y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="405cf-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="405cf-106">No se pueden eliminar objetos publicados, por lo que la modificación del esquema generará un error.</span><span class="sxs-lookup"><span data-stu-id="405cf-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="405cf-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="405cf-107">Options</span></span>  
 <span data-ttu-id="405cf-108">**Tablas**</span><span class="sxs-lookup"><span data-stu-id="405cf-108">**Tables**</span></span>  
 <span data-ttu-id="405cf-109">Muestra las tablas que puede agregar al panel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="405cf-109">Lists the tables you can add to the **Diagram** pane.</span></span> <span data-ttu-id="405cf-110">Para agregar una tabla, selecciónela y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="405cf-110">To add a table, select it and click **Add**.</span></span> <span data-ttu-id="405cf-111">Para agregar varias tablas al mismo tiempo, selecciónelas y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="405cf-111">To add several tables at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="405cf-112">**Vistas**</span><span class="sxs-lookup"><span data-stu-id="405cf-112">**Views**</span></span>  
 <span data-ttu-id="405cf-113">Muestra las vistas que puede agregar al panel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="405cf-113">Lists the views you can add to the **Diagram** pane.</span></span> <span data-ttu-id="405cf-114">Para agregar una vista, selecciónela y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="405cf-114">To add a view, select it and click **Add**.</span></span> <span data-ttu-id="405cf-115">Para agregar varias vistas al mismo tiempo, selecciónelas y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="405cf-115">To add several views at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="405cf-116">**Funciones**</span><span class="sxs-lookup"><span data-stu-id="405cf-116">**Functions**</span></span>  
 <span data-ttu-id="405cf-117">Muestra las funciones definidas por el usuario que puede agregar al panel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="405cf-117">Lists the user-defined functions you can add to the **Diagram** pane.</span></span> <span data-ttu-id="405cf-118">Para agregar una función, selecciónela y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="405cf-118">To add a function, select it and click **Add**.</span></span> <span data-ttu-id="405cf-119">Para agregar varias funciones al mismo tiempo, selecciónelas y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="405cf-119">To add several functions at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="405cf-120">**Sinónimos**</span><span class="sxs-lookup"><span data-stu-id="405cf-120">**Synonyms**</span></span>  
 <span data-ttu-id="405cf-121">Muestra los sinónimos que se pueden agregar al panel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="405cf-121">Lists the synonyms you can add to the **Diagram** pane.</span></span> <span data-ttu-id="405cf-122">Para agregar un sinónimo, selecciónelo y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="405cf-122">To add a synonym, select it and click **Add**.</span></span> <span data-ttu-id="405cf-123">Para agregar varios sinónimos al mismo tiempo, selecciónelos y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="405cf-123">To add several synonyms at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="405cf-124">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="405cf-124">**Refresh**</span></span>  
 <span data-ttu-id="405cf-125">Actualiza la lista para que incluya los cambios realizados en la base de datos desde la última vez que se recuperó la lista.</span><span class="sxs-lookup"><span data-stu-id="405cf-125">Update the list to include any changes made to the database since the list was last retrieved.</span></span>  
  
 <span data-ttu-id="405cf-126">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="405cf-126">**Add**</span></span>  
 <span data-ttu-id="405cf-127">Agrega los elementos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="405cf-127">Add the selected item or items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="405cf-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="405cf-128">See Also</span></span>  
 [<span data-ttu-id="405cf-129">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="405cf-129">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
