---
title: Soluciones (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- solutions [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d06a8a05-7201-4055-8cf3-21bcb4e82c25
author: stevestein
ms.author: sstein
ms.openlocfilehash: 836d3b3002d72541ad88ae55eac6d951530e0ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671301"
---
# <a name="solutions-sql-server-management-studio"></a><span data-ttu-id="089c1-102">Soluciones (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="089c1-102">Solutions (SQL Server Management Studio)</span></span>
  <span data-ttu-id="089c1-103">Una solución de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] es una colección de uno o más proyectos relacionados.</span><span class="sxs-lookup"><span data-stu-id="089c1-103">A [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution is a collection of one or more related projects.</span></span> <span data-ttu-id="089c1-104">Los proyectos son contenedores que los desarrolladores de software usan para organizar los archivos relacionados, como conjuntos de scripts de uso común.</span><span class="sxs-lookup"><span data-stu-id="089c1-104">Projects are containers that developers use to organize related files, such as sets of commonly used administration scripts.</span></span>  
  
## <a name="solution-overview"></a><span data-ttu-id="089c1-105">Información general de la solución</span><span class="sxs-lookup"><span data-stu-id="089c1-105">Solution Overview</span></span>  
 <span data-ttu-id="089c1-106">Puede usar [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] como plataforma de desarrollo de script de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="089c1-106">You can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] as a script development platform for [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="089c1-107">Use los editores de código de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para desarrollar scripts y consultas para bases de datos relacionales y multidimensionales, y recopile los scripts y las consultas relacionados agrupados en proyectos.</span><span class="sxs-lookup"><span data-stu-id="089c1-107">Use the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] code editors to develop scripts and queries for relational and multidimensional databases, and collect related scripts and queries together in projects.</span></span>  
  
 <span data-ttu-id="089c1-108">Los proyectos pueden contener:</span><span class="sxs-lookup"><span data-stu-id="089c1-108">Projects can contain:</span></span>  
  
-   <span data-ttu-id="089c1-109">Consultas y scripts que implementan procesos de producción.</span><span class="sxs-lookup"><span data-stu-id="089c1-109">Queries and scripts that implement production processes.</span></span>  
  
-   <span data-ttu-id="089c1-110">Información y archivos de conexión usados por consultas y scripts.</span><span class="sxs-lookup"><span data-stu-id="089c1-110">Connection information and files used by the queries and scripts.</span></span>  
  
 <span data-ttu-id="089c1-111">Uno o varios proyectos relacionados se pueden combinar en una solución.</span><span class="sxs-lookup"><span data-stu-id="089c1-111">One or more related projects can be combined in a solution.</span></span> <span data-ttu-id="089c1-112">Las soluciones y los proyectos se pueden administrar mediante el panel Explorador de soluciones de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="089c1-112">Solutions and projects can be managed by using the Solution Explorer pane in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="089c1-113">Las soluciones y proyectos pueden integrarse en una base de datos [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe (VSS) u otros proveedores de control de código fuente para realizar un seguimiento de los cambios de desarrollo y administrar el ciclo vital.</span><span class="sxs-lookup"><span data-stu-id="089c1-113">Solutions and projects can be integrated into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe (VSS) database or other third-party source control providers, for development change tracking and life-cycle management.</span></span>  
  
## <a name="solution-tasks"></a><span data-ttu-id="089c1-114">Tareas de la solución</span><span class="sxs-lookup"><span data-stu-id="089c1-114">Solution Tasks</span></span>  
  
|<span data-ttu-id="089c1-115">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="089c1-115">Task Description</span></span>|<span data-ttu-id="089c1-116">Tema</span><span class="sxs-lookup"><span data-stu-id="089c1-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="089c1-117">Describe cómo crear una solución que se puede usar para contener uno o más proyectos.</span><span class="sxs-lookup"><span data-stu-id="089c1-117">Describes how to create a new solution that can then be used to contain one or more projects.</span></span>|[<span data-ttu-id="089c1-118">Crear una nueva solución</span><span class="sxs-lookup"><span data-stu-id="089c1-118">Create a New Solution</span></span>](create-a-new-solution.md)|  
|<span data-ttu-id="089c1-119">Describe cómo abrir una solución existente en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="089c1-119">Describes how to open an existing solution in Solution Explorer.</span></span>|[<span data-ttu-id="089c1-120">Abrir una solución existente</span><span class="sxs-lookup"><span data-stu-id="089c1-120">Open an Existing Solution</span></span>](open-an-existing-solution.md)|  
|<span data-ttu-id="089c1-121">Describe cómo cerrar una solución.</span><span class="sxs-lookup"><span data-stu-id="089c1-121">Describes how to close a solution.</span></span>|[<span data-ttu-id="089c1-122">Cerrar una solución</span><span class="sxs-lookup"><span data-stu-id="089c1-122">Close a Solution</span></span>](close-a-solution.md)|  
|<span data-ttu-id="089c1-123">Describe cómo eliminar una solución.</span><span class="sxs-lookup"><span data-stu-id="089c1-123">Describes how to delete a solution.</span></span>|[<span data-ttu-id="089c1-124">Eliminar una solución</span><span class="sxs-lookup"><span data-stu-id="089c1-124">Delete a Solution</span></span>](delete-a-solution.md)|  
|<span data-ttu-id="089c1-125">Describe cómo copiar elementos entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="089c1-125">Describes how to copy items between projects.</span></span>|[<span data-ttu-id="089c1-126">Copiar elementos de una solución</span><span class="sxs-lookup"><span data-stu-id="089c1-126">Copy Items in a Solution</span></span>](copy-items-in-a-solution.md)|  
|<span data-ttu-id="089c1-127">Describe cómo eliminar elementos de un proyecto o todo un proyecto.</span><span class="sxs-lookup"><span data-stu-id="089c1-127">Describes how to delete items in a project, or an entire project.</span></span>|[<span data-ttu-id="089c1-128">Quitar o eliminar un elemento o un proyecto</span><span class="sxs-lookup"><span data-stu-id="089c1-128">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)|  
|<span data-ttu-id="089c1-129">Describe cómo mover elementos entre los proyectos de una solución.</span><span class="sxs-lookup"><span data-stu-id="089c1-129">Describes how to move items between projects in a solution.</span></span>|[<span data-ttu-id="089c1-130">Mover elementos en una solución</span><span class="sxs-lookup"><span data-stu-id="089c1-130">Move Items in a Solution</span></span>](move-items-in-a-solution.md)|  
|<span data-ttu-id="089c1-131">Describe cómo cambiar el nombre de una solución o elementos de la solución.</span><span class="sxs-lookup"><span data-stu-id="089c1-131">Describes how to rename a solution or the items in the solution.</span></span>|[<span data-ttu-id="089c1-132">Cambiar el nombre de las soluciones y los elementos de un proyecto</span><span class="sxs-lookup"><span data-stu-id="089c1-132">Rename Solutions and Project Items</span></span>](rename-solutions-and-project-items.md)|  
  
## <a name="see-also"></a><span data-ttu-id="089c1-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="089c1-133">See Also</span></span>  
 <span data-ttu-id="089c1-134">[Explorador de soluciones](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="089c1-134">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="089c1-135">[Proyectos &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="089c1-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="089c1-136">Control de código fuente del Explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="089c1-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
