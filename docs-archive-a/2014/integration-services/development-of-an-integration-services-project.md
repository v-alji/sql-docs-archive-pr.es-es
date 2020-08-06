---
title: Desarrollo de un proyecto de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Integration Services], creating
- Integration Services projects, creating
- SQL Server Integration Services projects, creating
- SSIS projects, creating
ms.assetid: 6e90b016-36a5-415e-9440-a20199fffff0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da648b3b09b25fa2a7b1cf886ad1bf770296f5ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676600"
---
# <a name="development-of-an-integration-services-project"></a><span data-ttu-id="7ca74-102">Desarrollo de un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="7ca74-102">Development of an Integration Services Project</span></span>
  <span data-ttu-id="7ca74-103">Puede agregar paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] a proyectos.</span><span class="sxs-lookup"><span data-stu-id="7ca74-103">You add [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to projects.</span></span> <span data-ttu-id="7ca74-104">Para crear y trabajar con proyectos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , debe instalar el entorno de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ca74-104">To create and work with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects, you must install the [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] environment.</span></span> <span data-ttu-id="7ca74-105">Para más información, vea [Instalar Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="7ca74-105">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
 <span data-ttu-id="7ca74-106">Al crear un proyecto nuevo de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], el cuadro de diálogo **Nuevo proyecto** incluye una plantilla **Proyecto de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="7ca74-106">When you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the **New Project** dialog box includes an **Integration Services Project** template.</span></span> <span data-ttu-id="7ca74-107">Esta plantilla de proyecto crea un proyecto nuevo que contiene un único paquete.</span><span class="sxs-lookup"><span data-stu-id="7ca74-107">This project template creates a new project that contains a single package.</span></span>  
  
## <a name="projects-and-solutions"></a><span data-ttu-id="7ca74-108">Proyectos y soluciones</span><span class="sxs-lookup"><span data-stu-id="7ca74-108">Projects and Solutions</span></span>  
 <span data-ttu-id="7ca74-109">Los proyectos se almacenan en soluciones.</span><span class="sxs-lookup"><span data-stu-id="7ca74-109">Projects are stored in solutions.</span></span> <span data-ttu-id="7ca74-110">Primero se crea una solución y luego se agrega un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] a la solución.</span><span class="sxs-lookup"><span data-stu-id="7ca74-110">You can create a solution first and then add an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the solution.</span></span> <span data-ttu-id="7ca74-111">Si no existe solución, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] crea automáticamente una cuando se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ca74-111">If no solution exists, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] automatically creates one for you when you first create the project.</span></span> <span data-ttu-id="7ca74-112">Una solución puede contener varios proyectos de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="7ca74-112">A solution can contain multiple projects of different types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ca74-113">De forma predeterminada, al crear un proyecto nuevo de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], la solución no se muestra en el panel **Explorador de soluciones** .</span><span class="sxs-lookup"><span data-stu-id="7ca74-113">By default, when you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the solution is not shown in the **Solution Explorer** pane.</span></span> <span data-ttu-id="7ca74-114">Para cambiar este comportamiento predeterminado, en el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="7ca74-114">To change this default behavior, on the **Tools** menus, click **Options**.</span></span> <span data-ttu-id="7ca74-115">En el cuadro de diálogo **Opciones** , expanda **Proyectos y soluciones**y, a continuación, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="7ca74-115">In the **Options** dialog box, expand **Projects and Solutions**, and then click **General**.</span></span> <span data-ttu-id="7ca74-116">En la página **General** , seleccione **Mostrar solución siempre**.</span><span class="sxs-lookup"><span data-stu-id="7ca74-116">On the **General** page, select **Always show solution**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7ca74-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="7ca74-117">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7ca74-118">Crear un nuevo proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="7ca74-118">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="7ca74-119">Agregar un elemento a un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="7ca74-119">Add an Item to an Integration Services Project</span></span>](../../2014/integration-services/add-an-item-to-an-integration-services-project.md)  
  
-   [<span data-ttu-id="7ca74-120">Agregar o quitar un proyecto de Integration Services en una solución</span><span class="sxs-lookup"><span data-stu-id="7ca74-120">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
