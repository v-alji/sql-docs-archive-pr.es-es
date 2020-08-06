---
title: Recuperar archivos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], file retrieval
- file retrieval [SQL Server]
- retrieving files
ms.assetid: 37b74426-e262-43b2-a81f-79b1fd1a36ec
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebced9ea69f304344893289140687cd6d511e923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676152"
---
# <a name="retrieve-files"></a><span data-ttu-id="01281-102">Recuperar archivos</span><span class="sxs-lookup"><span data-stu-id="01281-102">Retrieve Files</span></span>
  <span data-ttu-id="01281-103">Después de haber abierto un proyecto controlado por código fuente, puede utilizar [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para recuperar copias locales de los archivos del proyecto desde el almacén de control de código fuente en el directorio local en el que reside el proyecto.</span><span class="sxs-lookup"><span data-stu-id="01281-103">After you have opened a source-controlled project, you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to retrieve local copies of project files from the source control store to the local directory in which the project resides.</span></span>  
  
 <span data-ttu-id="01281-104">Puede usar el control de código fuente integrado para recuperar archivos de varias formas:</span><span class="sxs-lookup"><span data-stu-id="01281-104">You can use integrated source control to retrieve files in the following ways:</span></span>  
  
-   <span data-ttu-id="01281-105">Comando **obtener la última versión (recursivo)**</span><span class="sxs-lookup"><span data-stu-id="01281-105">**Get Latest Version (Recursive)** command</span></span>  
  
     <span data-ttu-id="01281-106">Recupera la última versión protegida de los archivos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="01281-106">Retrieves the latest checked in version of the selected files.</span></span> <span data-ttu-id="01281-107">Si se selecciona una solución o un proyecto, este comando recupera la última versión de todos los archivos de la solución y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="01281-107">If a solution or project is selected, this command retrieves the latest version of all solution and project files.</span></span>  
  
-   <span data-ttu-id="01281-108">**Get** (comando)</span><span class="sxs-lookup"><span data-stu-id="01281-108">**Get** command</span></span>  
  
     <span data-ttu-id="01281-109">Muestra el cuadro de diálogo **obtener** , que puede usar para recuperar la versión más reciente de un archivo seleccionado o para recuperar un subconjunto de los archivos de la solución o proyecto seleccionados.</span><span class="sxs-lookup"><span data-stu-id="01281-109">Displays the **Get** dialog box, which you can use to retrieve the latest version of a selected file, or to retrieve a subset of the files in the selected solution or project.</span></span>  
  
### <a name="to-retrieve-the-latest-version-of-all-the-files-in-a-project"></a><span data-ttu-id="01281-110">Para recuperar la última versión de todos los archivos de un proyecto</span><span class="sxs-lookup"><span data-stu-id="01281-110">To retrieve the latest version of all the files in a project</span></span>  
  
1.  <span data-ttu-id="01281-111">En el Explorador de soluciones, seleccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="01281-111">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="01281-112">En el menú **archivo** , seleccione **control de código fuente**y, a continuación, haga clic en **obtener la última versión (recursivo)**.</span><span class="sxs-lookup"><span data-stu-id="01281-112">On the **File** menu, point to **Source Control**, and then click **Get Latest Version (Recursive)**.</span></span>  
  
 <span data-ttu-id="01281-113">Se recuperan las versiones más recientes de los archivos del proyecto en la ubicación del proyecto en el disco local.</span><span class="sxs-lookup"><span data-stu-id="01281-113">The most recent versions of the files in the project are retrieved to the project location on your local disk.</span></span>  
  
#### <a name="to-retrieve-only-certain-files-in-a-project"></a><span data-ttu-id="01281-114">Para recuperar únicamente algunos archivos de un proyecto</span><span class="sxs-lookup"><span data-stu-id="01281-114">To retrieve only certain files in a project</span></span>  
  
1.  <span data-ttu-id="01281-115">En el Explorador de soluciones, seleccione el elemento que desea recuperar.</span><span class="sxs-lookup"><span data-stu-id="01281-115">In Solution Explorer, select the item you want to retrieve.</span></span>  
  
2.  <span data-ttu-id="01281-116">En el menú **archivo** , seleccione **control de código fuente**y, a continuación, haga clic en **obtener**.</span><span class="sxs-lookup"><span data-stu-id="01281-116">On the **File** menu, point to **Source Control**, and then click **Get**.</span></span>  
  
3.  <span data-ttu-id="01281-117">En el cuadro de diálogo **obtener** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="01281-117">In the **Get** dialog box, click **OK**.</span></span> <span data-ttu-id="01281-118">Si ha seleccionado una solución o un proyecto en el Explorador de soluciones, también puede desactivar las casillas que aparecen junto a los elementos que no desea recuperar.</span><span class="sxs-lookup"><span data-stu-id="01281-118">Alternatively, if you selected a solution or project in Solution Explorer, clear the check boxes that appear next to the items you do not want to retrieve.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01281-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01281-119">See Also</span></span>  
 <span data-ttu-id="01281-120">[Cuadro de diálogo obtener &#40;control de código fuente&#41;](../../2014/database-engine/get-dialog-box-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="01281-120">[Get Dialog Box &#40;Source Control&#41;](../../2014/database-engine/get-dialog-box-source-control.md) </span></span>  
 <span data-ttu-id="01281-121">[Establecer y recuperar información de versión](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="01281-121">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="01281-122">[Ver el historial del proyecto](../../2014/database-engine/view-project-history.md) </span><span class="sxs-lookup"><span data-stu-id="01281-122">[View Project History](../../2014/database-engine/view-project-history.md) </span></span>  
 [<span data-ttu-id="01281-123">Ver el estado de archivo</span><span class="sxs-lookup"><span data-stu-id="01281-123">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
  
