---
title: Agregar o quitar un proyecto de Integration Services en una solución | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- Integration Services projects, adding
- SQL Server Integration Services projects, adding
- SSIS projects, adding
- projects [Integration Services], adding
ms.assetid: f01f6475-b63c-41dc-82ac-b62162b3adf7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49984c61047a6b716015bd72e518b73cb08b3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662223"
---
# <a name="add-or-remove-an-integration-services-project-in-a-solution"></a><span data-ttu-id="d5fe1-102">Agregar o quitar un proyecto de Integration Services en una solución</span><span class="sxs-lookup"><span data-stu-id="d5fe1-102">Add or Remove an Integration Services Project in a Solution</span></span>
  <span data-ttu-id="d5fe1-103">Los procedimientos siguientes describen cómo agregar o quitar un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en una solución.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-103">The following procedures descibe how to add or remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in a solution.</span></span>  
  
 <span data-ttu-id="d5fe1-104">Solo se puede agregar un proyecto a una solución existente, o quitar un proyecto de una solución, mientras esta está visible en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5fe1-104">You can only add a project to an existing solution, or remove a project from a solution, when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d5fe1-105">Si ha seleccionado la opción **Mostrar solución siempre** en [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , mostrará [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] una solución aunque esa solución contenga solo un proyecto.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-105">If you have selected the **Always show solution** option in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution even when that solution contains only one project.</span></span> <span data-ttu-id="d5fe1-106">En caso contrario, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] solo mostrará una solución cuando esta contenga varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-106">Otherwise, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution only when that solution contains more than one project.</span></span> <span data-ttu-id="d5fe1-107">Los proyectos adicionales pueden ser proyectos de [!INCLUDE[ssIS](../includes/ssis-md.md)] o de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-107">The additional projects can be either [!INCLUDE[ssIS](../includes/ssis-md.md)] projects or projects of other types.</span></span>  
  
## <a name="adding-an-integration-services-project"></a><span data-ttu-id="d5fe1-108">Agregar un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="d5fe1-108">Adding an Integration Services Project</span></span>  
 <span data-ttu-id="d5fe1-109">Cuando agregue un proyecto, puede crear uno en blanco con [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o agregar uno creado anteriormente para otra solución.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-109">When you add a project, you can have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] create a new, blank project, or you can add a project that you have already created for a different solution.</span></span> <span data-ttu-id="d5fe1-110">Solo puede agregar un proyecto a una solución existente mientras la solución está visible en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5fe1-110">You can only add a project to an existing solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
#### <a name="to-add-a-new-integration-services-project-to-a-solution"></a><span data-ttu-id="d5fe1-111">Para agregar un proyecto nuevo de Integration Services a una solución</span><span class="sxs-lookup"><span data-stu-id="d5fe1-111">To add a new Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="d5fe1-112">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra la solución para la cual desea agregar un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nuevo y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d5fe1-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="d5fe1-113">Haga clic con el botón derecho en la solución, seleccione **Agregar** y, después, haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-113">Right-click the solution, click **Add**, and then click **New Project**.</span></span>  
  
    -   <span data-ttu-id="d5fe1-114">En el menú **Archivo** , seleccione **Agregar**y haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-114">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="d5fe1-115">En el cuadro de diálogo **Nuevo proyecto** , seleccione **Proyecto de Integration Services** del panel **Plantillas** .</span><span class="sxs-lookup"><span data-stu-id="d5fe1-115">In the **Add New Project** dialog box, click **Integration Services Project** in the **Templates** pane.</span></span>  
  
3.  <span data-ttu-id="d5fe1-116">Opcionalmente, modifique el nombre y ubicación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-116">Optionally, edit the project name and location.</span></span>  
  
4.  <span data-ttu-id="d5fe1-117">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-117">Click **OK**.</span></span>  
  
#### <a name="to-add-an-existing-integration-services-project-to-a-solution"></a><span data-ttu-id="d5fe1-118">Para agregar un proyecto de Integration Services existente a una solución</span><span class="sxs-lookup"><span data-stu-id="d5fe1-118">To add an existing Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="d5fe1-119">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra la solución para la cual desee agregar un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] existente y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d5fe1-119">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="d5fe1-120">Haga clic con el botón derecho en la solución, seleccione **Agregar** y, después, haga clic en **Proyecto existente**.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-120">Right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  
  
    -   <span data-ttu-id="d5fe1-121">En el menú **Archivo** , seleccione **Agregar**y haga clic en **Proyecto existente**.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-121">On the **File** menu, click **Add**, and then click **Existing Project**.</span></span>  
  
2.  <span data-ttu-id="d5fe1-122">En el cuadro de diálogo **Agregar proyecto existente** , busque el proyecto que desee agregar y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-122">In the **Add Existing Project** dialog box, browse to locate the project you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="d5fe1-123">El proyecto se agrega a la carpeta de soluciones en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-123">The project is added to the solution folder in **Solution Explorer**.</span></span>  
  
## <a name="removing-an-integration-services-project"></a><span data-ttu-id="d5fe1-124">Quitar un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="d5fe1-124">Removing an Integration Services Project</span></span>  
 <span data-ttu-id="d5fe1-125">Solo puede quitar un proyecto de una solución mientras la solución está visible en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5fe1-125">You can only remove a project from a solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d5fe1-126">Una vez que la solución está visible, puede quitar todos los proyectos excepto uno.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-126">After the solution is visible, you can remove all except one project.</span></span> <span data-ttu-id="d5fe1-127">Tan pronto como queda un solo proyecto, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ya no muestra la carpeta de la solución y no se puede quitar el último proyecto.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-127">As soon as only one project remains, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] no longer displays the solution folder and you cannot remove the last project.</span></span>  
  
#### <a name="to-remove-an-integration-services-project-from-a-solution"></a><span data-ttu-id="d5fe1-128">Para quitar un proyecto de Integration Services de una solución</span><span class="sxs-lookup"><span data-stu-id="d5fe1-128">To remove an Integration Services project from a solution</span></span>  
  
1.  <span data-ttu-id="d5fe1-129">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra la solución de la que desea quitar un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5fe1-129">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution from which you want to remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="d5fe1-130">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y, después, haga clic en **Descargar el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-130">In Solution Explorer, right-click the project, and then click **Unload Project**.</span></span>  
  
3.  <span data-ttu-id="d5fe1-131">Haga clic en **Aceptar** para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-131">Click **OK** to confirm the removal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5fe1-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5fe1-132">See Also</span></span>  
 <span data-ttu-id="d5fe1-133">[Integration Services &#40;proyectos&#41; de SSIS](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="d5fe1-133">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="d5fe1-134">Crear un nuevo proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="d5fe1-134">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
  
