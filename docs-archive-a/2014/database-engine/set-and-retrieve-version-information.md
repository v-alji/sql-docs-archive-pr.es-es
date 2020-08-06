---
title: Establecer y recuperar información de versión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- historical information [SQL Server]
- source controls [SQL Server Management Studio], version information
- retrieving version information
- current file version information
- version control services [SQL Server], retrieving version information
- version control services [SQL Server], setting version information
- status information [SQL Server], source control files
- historical information [SQL Server], source control files
ms.assetid: c3f253c4-4e3d-48e8-8d90-bd6ee899faf7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: eff3d40ba9b663ba8611508c5b9f0c9961005b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744291"
---
# <a name="set-and-retrieve-version-information"></a><span data-ttu-id="2d3d6-102">Establecer y recuperar información de versión</span><span class="sxs-lookup"><span data-stu-id="2d3d6-102">Set and Retrieve Version Information</span></span>
  <span data-ttu-id="2d3d6-103">La información de versión incluye el historial y el estado actual de un archivo controlado por código fuente.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-103">Version information includes the history and current status of a source-controlled file.</span></span> <span data-ttu-id="2d3d6-104">[!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe conserva un historial completo de cada archivo controlado por código fuente, lo que permite realizar un seguimiento de la evolución de uno o más archivos a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-104">For every source-controlled file, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe maintains a comprehensive history, so you can track the evolution of one or more files over time.</span></span> <span data-ttu-id="2d3d6-105">Además, esta información se puede utilizar para recuperar una copia local de cualquier versión del archivo o para comparar dos versiones cualesquiera.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-105">You can also use this information to retrieve a local copy of any version of the file or to compare any two file versions.</span></span>  
  
 <span data-ttu-id="2d3d6-106">El historial de un archivo incluye:</span><span class="sxs-lookup"><span data-stu-id="2d3d6-106">The history of a file includes:</span></span>  
  
-   <span data-ttu-id="2d3d6-107">El número de versión, que identifica su secuencia entre otras versiones del mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-107">The version number, which identifies its sequence among other versions of the same file.</span></span>  
  
-   <span data-ttu-id="2d3d6-108">acción realizada.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-108">The action performed.</span></span> <span data-ttu-id="2d3d6-109">Las operaciones realizadas incluyen la creación del archivo, la protección y la eliminación.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-109">Tracked operations include file creation, check in, and deletion.</span></span>  
  
-   <span data-ttu-id="2d3d6-110">El nombre de usuario de la persona que realizó una acción con el archivo.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-110">The user name of the person who performed an action involving the file.</span></span>  
  
-   <span data-ttu-id="2d3d6-111">La fecha y la hora en que se realizó la operación.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-111">The date and time when the operation was performed.</span></span>  
  
 <span data-ttu-id="2d3d6-112">Visual SourceSafe también conserva información de estado actual sobre la solución cargada.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-112">Visual SourceSafe also maintains current status information on the currently loaded solution.</span></span> <span data-ttu-id="2d3d6-113">Esta información proporciona una instantánea del estado actual del archivo, lo que incluye:</span><span class="sxs-lookup"><span data-stu-id="2d3d6-113">This information provides a snapshot of the current state of the file, including:</span></span>  
  
-   <span data-ttu-id="2d3d6-114">La identidad del usuario que tiene desprotegido el archivo.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-114">The identity of the user who has the file checked out.</span></span>  
  
-   <span data-ttu-id="2d3d6-115">El número de la última versión del archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-115">The latest version number of the selected file.</span></span>  
  
-   <span data-ttu-id="2d3d6-116">La fecha en la que se creó la versión.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-116">The date when the version was created.</span></span>  
  
-   <span data-ttu-id="2d3d6-117">Los comentarios de usuario asociados a la versión.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-117">The user comment associated with the version.</span></span>  
  
-   <span data-ttu-id="2d3d6-118">Las rutas de acceso a los proyectos que comparten el archivo.</span><span class="sxs-lookup"><span data-stu-id="2d3d6-118">The paths to the projects with which the file is shared.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d3d6-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2d3d6-119">In This Section</span></span>  
  
-   [<span data-ttu-id="2d3d6-120">Ver el historial de un archivo</span><span class="sxs-lookup"><span data-stu-id="2d3d6-120">View File History</span></span>](../../2014/database-engine/view-file-history.md)  
  
-   [<span data-ttu-id="2d3d6-121">Ver el historial del proyecto</span><span class="sxs-lookup"><span data-stu-id="2d3d6-121">View Project History</span></span>](../../2014/database-engine/view-project-history.md)  
  
-   [<span data-ttu-id="2d3d6-122">Ver el estado de archivo</span><span class="sxs-lookup"><span data-stu-id="2d3d6-122">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
-   [<span data-ttu-id="2d3d6-123">Recuperar archivos</span><span class="sxs-lookup"><span data-stu-id="2d3d6-123">Retrieve Files</span></span>](../../2014/database-engine/retrieve-files.md)  
  
-   [<span data-ttu-id="2d3d6-124">Especificar una versión como última versión</span><span class="sxs-lookup"><span data-stu-id="2d3d6-124">Specify a Version as the Latest Version</span></span>](../../2014/database-engine/specify-a-version-as-the-latest-version.md)  
  
-   [<span data-ttu-id="2d3d6-125">Comparar archivos</span><span class="sxs-lookup"><span data-stu-id="2d3d6-125">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
-   [<span data-ttu-id="2d3d6-126">Compartir archivos</span><span class="sxs-lookup"><span data-stu-id="2d3d6-126">Share Files</span></span>](../../2014/database-engine/share-files.md)  
  
-   [<span data-ttu-id="2d3d6-127">Crear informes de historial y estado</span><span class="sxs-lookup"><span data-stu-id="2d3d6-127">Create History and Status Reports</span></span>](../../2014/database-engine/create-history-and-status-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="2d3d6-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d3d6-128">See Also</span></span>  
 [<span data-ttu-id="2d3d6-129">Fundamentos del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="2d3d6-129">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
