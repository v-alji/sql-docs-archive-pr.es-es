---
title: 'Lección 1: Conversión de una tabla en una estructura jerárquica | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 5ee6f19a-6dd7-4730-a91c-bbed1bd77e0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 196a546093786f9be4b88536763b3150ae750f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749693"
---
# <a name="lesson-1-converting-a-table-to-a-hierarchical-structure"></a><span data-ttu-id="325d6-102">Lección 1: Convertir una tabla en una estructura jerárquica</span><span class="sxs-lookup"><span data-stu-id="325d6-102">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>
  <span data-ttu-id="325d6-103">Los clientes que tienen tablas que utilizan autocombinaciones para expresar las relaciones jerárquicas pueden convertir sus tablas en una estructura jerárquica usando esta lección como guía.</span><span class="sxs-lookup"><span data-stu-id="325d6-103">Customers who have tables using self joins to express hierarchical relationships can convert their tables to a hierarchical structure using this lesson as a guide.</span></span> <span data-ttu-id="325d6-104">Es relativamente fácil migrar de esta representación a una que use `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="325d6-104">It is relatively easy to migrate from this representation to one using `hierarchyid`.</span></span> <span data-ttu-id="325d6-105">Después de la migración, los usuarios tendrán una representación jerárquica compacta y fácil de entender, que se puede indizar de varias maneras para conseguir consultas eficaces.</span><span class="sxs-lookup"><span data-stu-id="325d6-105">After migration, users will have a compact and easy to understand hierarchical representation, which can be indexed in several ways for efficient queries.</span></span>  
  
 <span data-ttu-id="325d6-106">En esta lección se examina una tabla existente, se crea una nueva tabla que contiene una columna `hierarchyid`, se rellena la tabla con los datos de la tabla de origen y, a continuación, se muestran tres estrategias de indización.</span><span class="sxs-lookup"><span data-stu-id="325d6-106">This lesson, examines an existing table, creates a new table containing a `hierarchyid` column, populates the table with the data from the source table, and then demonstrates three indexing strategies.</span></span> <span data-ttu-id="325d6-107">En esta lección se incluyen los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="325d6-107">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="325d6-108">Examen de la estructura actual de la tabla Empleado</span><span class="sxs-lookup"><span data-stu-id="325d6-108">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
-   [<span data-ttu-id="325d6-109">Rellenar una tabla con los datos jerárquicos existentes</span><span class="sxs-lookup"><span data-stu-id="325d6-109">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
-   [<span data-ttu-id="325d6-110">Optimizar la tabla NewOrg</span><span class="sxs-lookup"><span data-stu-id="325d6-110">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
-   [<span data-ttu-id="325d6-111">Resumen: Conversión de una tabla en una estructura jerárquica</span><span class="sxs-lookup"><span data-stu-id="325d6-111">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
## <a name="prerequisites"></a><span data-ttu-id="325d6-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="325d6-112">Prerequisites</span></span>  
 <span data-ttu-id="325d6-113">Esta lección requiere la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="325d6-113">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="325d6-114">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="325d6-114">Next Task in Lesson</span></span>  
 [<span data-ttu-id="325d6-115">Examen de la estructura actual de la tabla Empleado</span><span class="sxs-lookup"><span data-stu-id="325d6-115">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="325d6-116">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="325d6-116">Next Lesson</span></span>  
 [<span data-ttu-id="325d6-117">Lección 2: Creación y administración de los datos de una tabla jerárquica</span><span class="sxs-lookup"><span data-stu-id="325d6-117">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
  
  
