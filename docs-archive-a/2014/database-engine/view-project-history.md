---
title: Ver historial del proyecto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- viewing project history
- version control services [SQL Server], project history
- projects [SQL Server Management Studio], historical information
- historical information [SQL Server], projects
ms.assetid: be0ea2ac-4a35-429c-9c9e-4001ea9035a4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85028141050e19e6ed6394a5bb17709ac8f906ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677228"
---
# <a name="view-project-history"></a><span data-ttu-id="d974a-102">Ver el historial del proyecto</span><span class="sxs-lookup"><span data-stu-id="d974a-102">View Project History</span></span>
  <span data-ttu-id="d974a-103">El historial de un proyecto de [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS) incluye una lista de todas las acciones realizadas en cada uno de los archivos de ese proyecto, incluida la creación, la adición, la eliminación y la recuperación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="d974a-103">The history of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS) project includes a list of all the actions taken on each of the project files, including file creation, addition, deletion, and recovery.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d974a-104">Normalmente, se suele hacer referencia a un proyecto de Visual SourceSafe como la carpeta del servidor de control de código fuente, la ubicación en la que la versión del servidor de un archivo controlado por código fuente está almacenada en el servidor.</span><span class="sxs-lookup"><span data-stu-id="d974a-104">A Visual SourceSafe project is more commonly referred to as the source control server folder, the location where the server version of a source-controlled file is stored on the server.</span></span>  
  
 <span data-ttu-id="d974a-105">Puede utilizar [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para examinar el historial del proyecto de Visual SourceSafe al que pertenece la solución cargada.</span><span class="sxs-lookup"><span data-stu-id="d974a-105">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to examine the history of the Visual SourceSafe project to which the currently loaded solution belongs.</span></span> <span data-ttu-id="d974a-106">Según la información mostrada como parte del historial de un proyecto, puede recuperar copias locales de las versiones del archivo, restaurar versiones eliminadas o compartir una versión entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="d974a-106">Based on the information displayed as part of the history of a project, you can retrieve local copies of file versions, restore deleted versions, or share a file version between projects.</span></span>  
  
### <a name="to-view-the-history-of-a-vss-project"></a><span data-ttu-id="d974a-107">Para ver el historial de un proyecto de VSS</span><span class="sxs-lookup"><span data-stu-id="d974a-107">To view the history of a VSS project</span></span>  
  
1.  <span data-ttu-id="d974a-108">En el Explorador de soluciones, seleccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d974a-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="d974a-109">En el menú **archivo** , seleccione **control de código fuente** y haga clic en **Ver historial**.</span><span class="sxs-lookup"><span data-stu-id="d974a-109">On the **File** menu, point to **Source Control** and click **View History**.</span></span>  
  
3.  <span data-ttu-id="d974a-110">En el **historial del cuadro de** \<Project> diálogo, realice cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d974a-110">In the **History of** \<Project> dialog box, perform any of the following actions:</span></span>  
  
    -   <span data-ttu-id="d974a-111">Ver la copia del sistema de control de código fuente de un archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d974a-111">View the source control system's copy of a selected file.</span></span>  
  
    -   <span data-ttu-id="d974a-112">Ver información detallada acerca de un archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d974a-112">View detailed information about a selected file.</span></span>  
  
    -   <span data-ttu-id="d974a-113">Recuperar un archivo seleccionado en el disco local.</span><span class="sxs-lookup"><span data-stu-id="d974a-113">Retrieve a selected file to your local disk.</span></span>  
  
    -   <span data-ttu-id="d974a-114">Desproteger un archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d974a-114">Check out a selected file.</span></span>  
  
    -   <span data-ttu-id="d974a-115">Compartir un archivo seleccionado entre dos proyectos de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="d974a-115">Share a selected file between two source control projects.</span></span>  
  
    -   <span data-ttu-id="d974a-116">Exportar el informe de historial a una impresora, a un archivo o al Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="d974a-116">Export the history report to a printer, a file, or the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d974a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d974a-117">See Also</span></span>  
 <span data-ttu-id="d974a-118">[Establecer y recuperar información de versión](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="d974a-118">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="d974a-119">[Ver el estado del archivo](../../2014/database-engine/view-file-status.md) </span><span class="sxs-lookup"><span data-stu-id="d974a-119">[View File Status](../../2014/database-engine/view-file-status.md) </span></span>  
 <span data-ttu-id="d974a-120">[Recuperación de archivos](../../2014/database-engine/retrieve-files.md) </span><span class="sxs-lookup"><span data-stu-id="d974a-120">[Retrieve Files](../../2014/database-engine/retrieve-files.md) </span></span>  
 [<span data-ttu-id="d974a-121">Comparar archivos</span><span class="sxs-lookup"><span data-stu-id="d974a-121">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
  
