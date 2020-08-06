---
title: 'Tutorial: Uso del tipo de datos hierarchyid| Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- tutorials [hierarchyid]
- hierarchyid [Database Engine], tutorial
ms.assetid: 5a7f7cfd-7faf-439f-8085-8fd6bf7db355
author: stevestein
ms.author: sstein
ms.openlocfilehash: a735b4c2b51e1c680c8129647733ce1efd9f9984
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670906"
---
# <a name="tutorial-using-the-hierarchyid-data-type"></a><span data-ttu-id="df3f5-102">Tutorial: Uso del tipo de datos hierarchyid</span><span class="sxs-lookup"><span data-stu-id="df3f5-102">Tutorial: Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="df3f5-103">Este tutorial está destinado a usuarios con experiencia en [!INCLUDE[tsql](../../includes/tsql-md.md)], pero que desconocen los tipos de datos de `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="df3f5-103">This tutorial is intended for users who are experienced with [!INCLUDE[tsql](../../includes/tsql-md.md)], but are new to the `hierarchyid` data type.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="df3f5-104">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="df3f5-104">What You Will Learn</span></span>  
 <span data-ttu-id="df3f5-105">El tutorial está compuesto por dos lecciones:</span><span class="sxs-lookup"><span data-stu-id="df3f5-105">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="df3f5-106">Lección 1: Convertir una tabla en una estructura jerárquica</span><span class="sxs-lookup"><span data-stu-id="df3f5-106">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-converting-a-table-to-a-hierarchical-structure.md)  
 <span data-ttu-id="df3f5-107">En esta lección, se toma una tabla de empleado existente, estructurada como una jerarquía de elementos primarios y secundarios, y se mueven los datos a una nueva tabla que representa la jerarquía usando el tipo de datos de `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="df3f5-107">In this lesson, you take an existing employee table that is structured as a parent/child hierarchy and move the data into a new table that represents the hierarchy by using the `hierarchyid` data type.</span></span> <span data-ttu-id="df3f5-108">Esta lección requiere la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df3f5-108">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [<span data-ttu-id="df3f5-109">Lección 2: Creación y administración de los datos de una tabla jerárquica</span><span class="sxs-lookup"><span data-stu-id="df3f5-109">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
 <span data-ttu-id="df3f5-110">En esta lección, se crea una tabla usando el tipo de datos de `hierarchyid` para representar la estructura de jerarquía.</span><span class="sxs-lookup"><span data-stu-id="df3f5-110">In this lesson, you create a table by using the `hierarchyid` data type to represent the hierarchy structure.</span></span> <span data-ttu-id="df3f5-111">A continuación, se manipulan los datos de la tabla usando los métodos jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="df3f5-111">Then, you manipulate the data in the table by using the hierarchical methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df3f5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df3f5-112">Requirements</span></span>  
 <span data-ttu-id="df3f5-113">El sistema debe tener instalado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="df3f5-113">Your system must have the following installed:</span></span>  
  
-   <span data-ttu-id="df3f5-114">Cualquier edición de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o posterior.</span><span class="sxs-lookup"><span data-stu-id="df3f5-114">Any edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span>  
  
-   <span data-ttu-id="df3f5-115">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="df3f5-115">Either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span></span>  
  
-   <span data-ttu-id="df3f5-116">Internet Explorer versión 6 o posterior.</span><span class="sxs-lookup"><span data-stu-id="df3f5-116">Internet Explorer 6 or a later version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3f5-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df3f5-117">See Also</span></span>  
 <span data-ttu-id="df3f5-118">[Tutorial: Introducción con el Motor de base de datos](../tutorial-getting-started-with-the-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="df3f5-118">[Tutorial: Getting Started with the Database Engine](../tutorial-getting-started-with-the-database-engine.md) </span></span>  
 <span data-ttu-id="df3f5-119">[Tutorial: escribir instrucciones Transact-SQL](../../t-sql/tutorial-writing-transact-sql-statements.md) </span><span class="sxs-lookup"><span data-stu-id="df3f5-119">[Tutorial: Writing Transact-SQL Statements](../../t-sql/tutorial-writing-transact-sql-statements.md) </span></span>  
 <span data-ttu-id="df3f5-120">[Referencia del método de tipo de datos hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="df3f5-120">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="df3f5-121">[SQL Server de &#40;de datos jerárquicos&#41;](../hierarchical-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="df3f5-121">[Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md) </span></span>  
 [<span data-ttu-id="df3f5-122">hierarchyid &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="df3f5-122">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
