---
title: Abrir proyectos desde el control de código fuente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], opening
- opening projects
ms.assetid: 942f93a3-e264-4ec4-ba72-a28e0509a527
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 944b121516e3782e35e213e165405b0ecceb7456
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676646"
---
# <a name="open-projects-from-source-control"></a><span data-ttu-id="b9754-102">Abrir proyectos desde el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="b9754-102">Open Projects from Source Control</span></span>
  <span data-ttu-id="b9754-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] se puede utilizar para abrir proyectos directamente desde el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="b9754-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open projects directly from source control.</span></span> <span data-ttu-id="b9754-104">Al hacer esto, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] recupera la última versión del proyecto y la copia en el disco local.</span><span class="sxs-lookup"><span data-stu-id="b9754-104">When you do this, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] retrieves the latest version of the project and copies it to your local disk.</span></span> <span data-ttu-id="b9754-105">El entorno de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] también crea una solución para el proyecto de forma automática.</span><span class="sxs-lookup"><span data-stu-id="b9754-105">The [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment also creates a solution for the project automatically.</span></span>  
  
 <span data-ttu-id="b9754-106">Después de haber abierto un proyecto desde el control de código fuente, es posible desproteger y modificar los archivos de ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="b9754-106">After you have opened a project from source control, you can check out and modify the project files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9754-107">El siguiente procedimiento solamente debería utilizarse una vez.</span><span class="sxs-lookup"><span data-stu-id="b9754-107">The following procedure should only be used once.</span></span> <span data-ttu-id="b9754-108">A partir de ese momento, debe abrir el proyecto como cualquier otro proyecto (haciendo clic en **archivo**, **abrir**y, a continuación, en **proyecto**).</span><span class="sxs-lookup"><span data-stu-id="b9754-108">Thereafter, you should open the project like any other project (by clicking **File**, **Open**, and then **Project**).</span></span>  
  
### <a name="to-open-a-project-from-source-control"></a><span data-ttu-id="b9754-109">Para abrir un proyecto desde el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="b9754-109">To open a project from source control</span></span>  
  
1.  <span data-ttu-id="b9754-110">En el menú **archivo** , seleccione **control de código fuente**y haga clic en **abrir desde el control de código fuente**.</span><span class="sxs-lookup"><span data-stu-id="b9754-110">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="b9754-111">Si se le pide, inicie sesión en [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="b9754-111">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="b9754-112">En el cuadro de diálogo **crear un proyecto local de SourceSafe** , abra la carpeta que contiene el proyecto que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="b9754-112">In the **Create local project from SourceSafe** dialog box, open the folder that contains the project to open.</span></span>  
  
4.  <span data-ttu-id="b9754-113">El cuadro **crear un nuevo proyecto en la carpeta** cambia para identificar el directorio local en el que se creará el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b9754-113">The **Create a new project in the folder** box changes to identify the local directory in which the project will be created.</span></span> <span data-ttu-id="b9754-114">Si desea colocar el proyecto en un directorio diferente, escriba la ruta de acceso al directorio o use el botón **examinar** para buscar el directorio en el disco local.</span><span class="sxs-lookup"><span data-stu-id="b9754-114">If you want to place the project in a different directory, type the path to the directory or use the **Browse** button to locate the directory on your local disk.</span></span>  
  
5.  <span data-ttu-id="b9754-115">En el **cuadro crear un nuevo proyecto en la carpeta**, compruebe que se muestra la carpeta correcta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b9754-115">In the **Create a new project in the folder box**, verify that the correct folder is displayed, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b9754-116">En el cuadro de diálogo **Abrir solución** , seleccione el proyecto que desea abrir y haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="b9754-116">In the **Open Solution** dialog box, select the project you want to open, and click **Open**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9754-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9754-117">See Also</span></span>  
 <span data-ttu-id="b9754-118">[Abrir soluciones y proyectos desde el control de código fuente](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="b9754-118">[Open Solutions and Projects from Source Control](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span></span>  
 [<span data-ttu-id="b9754-119">Abrir soluciones desde el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="b9754-119">Open Solutions from Source Control</span></span>](../../2014/database-engine/open-solutions-from-source-control.md)  
  
  
