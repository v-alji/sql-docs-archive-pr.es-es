---
title: Explorador de soluciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- solutions [SQL Server Management Studio], about solutions
- SQL Server Management Studio [SQL Server], items
- items [SQL Server]
ms.assetid: 0df09843-0d4f-4925-bc6c-99265035a0c1
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa312f5e097fa1c59b9ba545709dc964a184c3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671303"
---
# <a name="solution-explorer"></a><span data-ttu-id="c66e5-102">Explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="c66e5-102">Solution Explorer</span></span>
  <span data-ttu-id="c66e5-103">El panel Explorador de soluciones de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] proporciona contenedores denominados proyectos para administrar elementos, tales como scripts de base de datos, consultas, conexiones de datos y archivos.</span><span class="sxs-lookup"><span data-stu-id="c66e5-103">The Solution Explorer pane in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides containers called projects for managing items such as database scripts, queries, data connections, and files.</span></span> <span data-ttu-id="c66e5-104">Uno o varios proyectos que están relacionados entre sí se pueden combinar en un contenedor denominado solución.</span><span class="sxs-lookup"><span data-stu-id="c66e5-104">One or more projects that are related to each other can be combined in a container called a solution.</span></span>  
  
 <span data-ttu-id="c66e5-105">Una solución contiene uno o varios proyectos, además de archivos y metadatos que ayudan a definir la solución como un conjunto.</span><span class="sxs-lookup"><span data-stu-id="c66e5-105">A solution includes one or more projects, plus files and metadata that help define the solution as a whole.</span></span> <span data-ttu-id="c66e5-106">Un proyecto es un conjunto de archivos y metadatos relacionados, por ejemplo, información de conexión.</span><span class="sxs-lookup"><span data-stu-id="c66e5-106">A project is a set of files, plus related metadata such as connection information.</span></span> <span data-ttu-id="c66e5-107">Las soluciones y los proyectos contienen elementos que representan los scripts, las consultas, la información de conexión y los archivos necesarios para crear la solución de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c66e5-107">Solutions and projects contain items that represent the scripts, queries, connection information and files that you need to create your database solution.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="benefits-of-using-solutions"></a><span data-ttu-id="c66e5-108">Ventajas de usar Soluciones</span><span class="sxs-lookup"><span data-stu-id="c66e5-108">Benefits of Using Solutions</span></span>  
 <span data-ttu-id="c66e5-109">Use estos contenedores para:</span><span class="sxs-lookup"><span data-stu-id="c66e5-109">Use these containers to:</span></span>  
  
-   <span data-ttu-id="c66e5-110">Implementar el control de código fuente en consultas y scripts.</span><span class="sxs-lookup"><span data-stu-id="c66e5-110">Implement source control on queries and scripts.</span></span>  
  
-   <span data-ttu-id="c66e5-111">Administrar la configuración de una solución como un conjunto o de proyectos individuales.</span><span class="sxs-lookup"><span data-stu-id="c66e5-111">Manage settings for your solution as a whole or for individual projects.</span></span>  
  
-   <span data-ttu-id="c66e5-112">Controlar los detalles de la administración de archivos mientras se centra en los elementos que conforman la solución de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c66e5-112">Handle the details of file management while you focus on items that make up your database solution.</span></span>  
  
-   <span data-ttu-id="c66e5-113">Agregar elementos de utilidad para varios proyectos de la solución o para la solución en sí sin hacer referencia al elemento de cada proyecto.</span><span class="sxs-lookup"><span data-stu-id="c66e5-113">Add items that are useful to multiple projects in the solution or to the solution without referencing the item in each project.</span></span>  
  
-   <span data-ttu-id="c66e5-114">Trabajar en varios archivos independientes de las soluciones o los proyectos.</span><span class="sxs-lookup"><span data-stu-id="c66e5-114">Work on miscellaneous files that are independent from solutions or projects.</span></span>  
  
 <span data-ttu-id="c66e5-115">Los elementos incluidos en los proyectos dependen del tipo de proyecto y de si se está usando o no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c66e5-115">The items contained in projects depend on the project type and whether you are using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c66e5-116">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c66e5-116">Related Tasks</span></span>  
 <span data-ttu-id="c66e5-117">Use los siguientes temas para empezar a trabajar con Soluciones de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="c66e5-117">Use the following topics to get started with SQL Server Solutions:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c66e5-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c66e5-118">**Description**</span></span>|<span data-ttu-id="c66e5-119">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="c66e5-119">**Topic**</span></span>|  
|<span data-ttu-id="c66e5-120">Describe cómo recopilar uno o varios proyectos en una solución.</span><span class="sxs-lookup"><span data-stu-id="c66e5-120">Describes how to collect one or more projects in a solution.</span></span>|[<span data-ttu-id="c66e5-121">Soluciones &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="c66e5-121">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solutions-sql-server-management-studio.md)|  
|<span data-ttu-id="c66e5-122">Describe cómo crear un proyecto y agregar elementos como scripts y conexiones.</span><span class="sxs-lookup"><span data-stu-id="c66e5-122">Describes how to create a project and add items like scripts and connections.</span></span>|[<span data-ttu-id="c66e5-123">Proyectos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="c66e5-123">Projects &#40;SQL Server Management Studio&#41;</span></span>](projects-sql-server-management-studio.md)|  
|<span data-ttu-id="c66e5-124">Describe cómo integrar soluciones o proyectos individuales en un sistema de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="c66e5-124">Describes how to integrate solutions or individual projects into a source code control system.</span></span>|[<span data-ttu-id="c66e5-125">Control de código fuente del Explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="c66e5-125">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)|  
|<span data-ttu-id="c66e5-126">Proporciona información acerca de los archivos usados por [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para administrar soluciones y archivos.</span><span class="sxs-lookup"><span data-stu-id="c66e5-126">Provides information about the files used by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage solutions and files.</span></span>|[<span data-ttu-id="c66e5-127">Archivos que administran soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="c66e5-127">Files That Manage Solutions and Projects</span></span>](files-that-manage-solutions-and-projects.md)|  
  
  
