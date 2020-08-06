---
title: Abrir soluciones desde el control de código fuente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- opening solutions
- solutions [SQL Server Management Studio], opening
ms.assetid: a96a1f0d-0183-4587-a3b0-4598309cbdd2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 808a4851bcc1f51690b2ba924a859bcccf9a6adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676644"
---
# <a name="open-solutions-from-source-control"></a><span data-ttu-id="1e400-102">Abrir soluciones desde el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="1e400-102">Open Solutions from Source Control</span></span>
  <span data-ttu-id="1e400-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] se puede utilizar para abrir soluciones directamente desde el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="1e400-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open solutions directly from source control.</span></span> <span data-ttu-id="1e400-104">Al hacer esto, el entorno de Studio crea una copia de la última versión de los archivos de la solución en la ubicación que se especifique.</span><span class="sxs-lookup"><span data-stu-id="1e400-104">When you do this, the Studio environment creates a copy of the latest version of the solution files at the location you specify.</span></span>  
  
 <span data-ttu-id="1e400-105">Si no hay una copia local de la solución en el disco local, es necesario abrir el proyecto desde el control de código fuente antes de poder utilizar [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para desproteger la solución o recuperar los archivos de la misma.</span><span class="sxs-lookup"><span data-stu-id="1e400-105">If a local copy of the solution does not exist on your local disk, you must open the project from source control before you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out the solution or retrieve solution files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e400-106">Si ya hay una copia local de la solución que se está abriendo desde el control de código fuente, se le pedirá que sobrescriba esta copia local.</span><span class="sxs-lookup"><span data-stu-id="1e400-106">If you already have a local copy of the solution you are opening from source control, you are prompted to overwrite the local copy.</span></span>  
  
### <a name="to-open-a-solution-from-source-control"></a><span data-ttu-id="1e400-107">Para abrir una solución desde el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="1e400-107">To open a solution from source control</span></span>  
  
1.  <span data-ttu-id="1e400-108">En el menú **archivo** , seleccione **control de código fuente**y haga clic en **abrir desde el control de código fuente**.</span><span class="sxs-lookup"><span data-stu-id="1e400-108">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="1e400-109">Si se le pide, inicie sesión en [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="1e400-109">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="1e400-110">En el cuadro de diálogo **crear un proyecto local de SourceSafe** , seleccione la carpeta que contiene la solución que desea abrir y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1e400-110">In the **Create local project from SourceSafe** dialog box, select the folder that contains the solution you want to open, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="1e400-111">Si ya existe una carpeta de trabajo para la solución en la unidad de disco local, el cuadro **crear un nuevo proyecto en la carpeta** cambia para identificar el directorio local.</span><span class="sxs-lookup"><span data-stu-id="1e400-111">If a working folder for the solution already exists on your local disk drive, the **Create a new project in the folder** box changes to identify the local directory.</span></span> <span data-ttu-id="1e400-112">Si no hay una carpeta de trabajo para la solución, puede escribir la ruta o ir al directorio local en el que debe abrirse la solución.</span><span class="sxs-lookup"><span data-stu-id="1e400-112">If no working folder for the solution exists, you can type or browse to the local directory in which the solution should be opened.</span></span>  
  
5.  <span data-ttu-id="1e400-113">En el cuadro de diálogo **Abrir solución** , seleccione el archivo de solución y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1e400-113">In the **Open Solution** dialog box, select the solution file, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e400-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e400-114">See Also</span></span>  
 [<span data-ttu-id="1e400-115">Abrir proyectos desde el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="1e400-115">Open Projects from Source Control</span></span>](../../2014/database-engine/open-projects-from-source-control.md)  
  
  
