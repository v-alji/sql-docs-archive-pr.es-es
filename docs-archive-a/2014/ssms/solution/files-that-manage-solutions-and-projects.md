---
title: Archivos que administran soluciones y proyectos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], files
- .ssmssln files
- .ssmsmobileproj files
- .ssmsasproj files
- .ssmssqlproj files
- .sqlsuo files
- files [SQL Server Management Studio], projects
ms.assetid: e19d2859-0b97-4727-ac27-c4c226d86b2f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c94f1f853263c3969961de91ec95b921f5d78ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746082"
---
# <a name="files-that-manage-solutions-and-projects"></a><span data-ttu-id="30a54-102">Archivos que administran soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="30a54-102">Files That Manage Solutions and Projects</span></span>
  <span data-ttu-id="30a54-103">En este tema se describen los tipos de archivos específicos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30a54-103">This topic describes the file types that are specific to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="30a54-104">De forma predeterminada, todas las soluciones y sus proyectos se crean en \Mis documentos\SQL Server Management Studio Projects.</span><span class="sxs-lookup"><span data-stu-id="30a54-104">By default, all solutions and their projects are created in \My Documents\SQL Server Management Studio Projects.</span></span>  
  
## <a name="management-studio-solution-files"></a><span data-ttu-id="30a54-105">Archivos de solución de Management Studio</span><span class="sxs-lookup"><span data-stu-id="30a54-105">Management Studio Solution Files</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="30a54-106">usa tipos de archivos distintos a los de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="30a54-106">uses different file types than [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span></span> <span data-ttu-id="30a54-107">Esto significa que no es posible abrir una solución de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="30a54-107">This means you cannot open a [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or in Visual Studio.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="30a54-108">los archivos de solución permiten que el Explorador de soluciones muestre una interfaz gráfica para administrar los archivos.</span><span class="sxs-lookup"><span data-stu-id="30a54-108">solution files allow Solution Explorer to display a graphical interface for managing your files.</span></span>  
  
|<span data-ttu-id="30a54-109">Extensión</span><span class="sxs-lookup"><span data-stu-id="30a54-109">Extension</span></span>|<span data-ttu-id="30a54-110">Tipo de archivo</span><span class="sxs-lookup"><span data-stu-id="30a54-110">File type</span></span>|<span data-ttu-id="30a54-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="30a54-111">Description</span></span>|<span data-ttu-id="30a54-112">Creado por</span><span class="sxs-lookup"><span data-stu-id="30a54-112">Created by</span></span>|  
|---------------|---------------|-----------------|----------------|  
|<span data-ttu-id="30a54-113">.ssmssln</span><span class="sxs-lookup"><span data-stu-id="30a54-113">.ssmssln</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="30a54-114">Objeto de solución</span><span class="sxs-lookup"><span data-stu-id="30a54-114">Solution Object</span></span>|<span data-ttu-id="30a54-115">Proporciona al entorno referencias sobre la ubicación en el disco de los proyectos, los elementos de proyecto y las soluciones de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30a54-115">Provides the environment with references to the location on disk of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] projects, project items, and solution</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]|  
  
## <a name="management-studio-project-files"></a><span data-ttu-id="30a54-116">Archivos de proyecto de Management Studio</span><span class="sxs-lookup"><span data-stu-id="30a54-116">Management Studio Project Files</span></span>  
 <span data-ttu-id="30a54-117">Del mismo modo que las soluciones contienen archivos de solución que administran objetos de una solución, los proyectos contienen archivos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="30a54-117">In the same way that solutions contain solution files that manage objects in a solution, projects contain project files.</span></span> <span data-ttu-id="30a54-118">El tipo de archivo de proyecto que crea [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para un proyecto depende de la plantilla utiliza para crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="30a54-118">The type of project file that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates for a project depends on the template used to create the project.</span></span> <span data-ttu-id="30a54-119">En la tabla siguiente se describe el tipo de archivo creado para cada proyecto.</span><span class="sxs-lookup"><span data-stu-id="30a54-119">The following table describes the type of file created for each project.</span></span>  
  
|<span data-ttu-id="30a54-120">Extensión</span><span class="sxs-lookup"><span data-stu-id="30a54-120">Extension</span></span>|<span data-ttu-id="30a54-121">Plantilla de proyecto</span><span class="sxs-lookup"><span data-stu-id="30a54-121">Project template</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="30a54-122">.ssmssqlproj</span><span class="sxs-lookup"><span data-stu-id="30a54-122">.ssmssqlproj</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="30a54-123">Proyecto de scripts</span><span class="sxs-lookup"><span data-stu-id="30a54-123">Scripts Project</span></span>|  
|<span data-ttu-id="30a54-124">.ssmsasproj</span><span class="sxs-lookup"><span data-stu-id="30a54-124">.ssmsasproj</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="30a54-125">Proyecto de scripts</span><span class="sxs-lookup"><span data-stu-id="30a54-125">Scripts Project</span></span>|  
  
## <a name="location-of-solution-level-files"></a><span data-ttu-id="30a54-126">Ubicación de los archivos de la solución</span><span class="sxs-lookup"><span data-stu-id="30a54-126">Location of Solution-Level Files</span></span>  
 <span data-ttu-id="30a54-127">De forma predeterminada, los archivos de la solución se crean en el directorio físico del primer proyecto creado con la solución.</span><span class="sxs-lookup"><span data-stu-id="30a54-127">By default, solution-level files are created in the physical directory of the first project that is created with the solution.</span></span> <span data-ttu-id="30a54-128">Puede especificar un directorio para la solución al crear una solución. También puede especificar el directorio al crear un proyecto nuevo.</span><span class="sxs-lookup"><span data-stu-id="30a54-128">You can specify a directory for the solution by creating a solution, or you can specify the directory when you create a new project.</span></span>  
  
 <span data-ttu-id="30a54-129">Si tiene una estructura de directorios similar a la estructura lógica que aparece en el Explorador de soluciones, será más fácil encontrar los proyectos y los archivos de la solución y compartirlos con otros programadores de un equipo.</span><span class="sxs-lookup"><span data-stu-id="30a54-129">If you have a directory structure similar to the logical structure shown in Solution Explorer, project and solution files are easier to locate and share with other developers on a team.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a54-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30a54-130">See Also</span></span>  
 <span data-ttu-id="30a54-131">[Administrar archivos con codificación](manage-files-with-encoding.md) </span><span class="sxs-lookup"><span data-stu-id="30a54-131">[Manage Files with Encoding](manage-files-with-encoding.md) </span></span>  
 <span data-ttu-id="30a54-132">[Archivos varios](miscellaneous-files.md) </span><span class="sxs-lookup"><span data-stu-id="30a54-132">[Miscellaneous Files](miscellaneous-files.md) </span></span>  
 <span data-ttu-id="30a54-133">[Explorador de soluciones](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="30a54-133">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="30a54-134">[Soluciones &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="30a54-134">[Solutions &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="30a54-135">[Proyectos &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="30a54-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="30a54-136">Control de código fuente del Explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="30a54-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
