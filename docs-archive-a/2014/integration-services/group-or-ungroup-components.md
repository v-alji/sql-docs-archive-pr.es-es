---
title: Agrupar o desagrupar componentes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- grouping containers
- tasks [Integration Services], grouping
- containers [Integration Services], grouping
- grouping tasks
ms.assetid: 34320838-c271-4f8c-90b3-1254690890bb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6811dffca41a12fe0afeeeb334e0107ac127c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663592"
---
# <a name="group-or-ungroup-components"></a><span data-ttu-id="83e71-102">Agrupar o desagrupar componentes</span><span class="sxs-lookup"><span data-stu-id="83e71-102">Group or Ungroup Components</span></span>
  <span data-ttu-id="83e71-103">Las pestañas **Flujo de control**, **Flujo de datos**y **Controladores de eventos** del Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] admiten la agrupación contraíble.</span><span class="sxs-lookup"><span data-stu-id="83e71-103">The **Control Flow**, **Data Flow**, and **Event Handlers** tabs in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer supports collapsible grouping.</span></span> <span data-ttu-id="83e71-104">Si un paquete tiene muchos componentes, las pestañas pueden estar abarrotadas, lo que dificulta la visión de todos los componentes a la vez y la búsqueda del elemento con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="83e71-104">If a package has many components, the tabs can become crowded, making it difficult to view all the components at one time and to locate the item with which you want to work.</span></span> <span data-ttu-id="83e71-105">La característica de agrupación contraíble puede ahorrar espacio en la superficie de trabajo y facilitar el trabajo con paquetes grandes.</span><span class="sxs-lookup"><span data-stu-id="83e71-105">The collapsible grouping feature can conserve space on the work surface and make it easier to work with large packages.</span></span>  
  
 <span data-ttu-id="83e71-106">Se seleccionan los componentes que desea agrupar, los agrupa y luego expande o contrae los grupos para facilitar su trabajo.</span><span class="sxs-lookup"><span data-stu-id="83e71-106">You select the components that you want to group, group them, and then expand or collapse the groups to suit your work.</span></span> <span data-ttu-id="83e71-107">Al expandir un grupo se proporciona acceso a las propiedades de los componentes del grupo.</span><span class="sxs-lookup"><span data-stu-id="83e71-107">Expanding a group provides access to the properties of the components in the group.</span></span> <span data-ttu-id="83e71-108">Las restricciones de precedencia que conectan las tareas y contenedores se incluyen automáticamente en el grupo.</span><span class="sxs-lookup"><span data-stu-id="83e71-108">The precedence constraints that connect tasks and containers are automatically included in the group.</span></span>  
  
 <span data-ttu-id="83e71-109">A continuación se presentan las consideraciones para la agrupación de componentes.</span><span class="sxs-lookup"><span data-stu-id="83e71-109">The following are considerations for grouping components.</span></span>  
  
-   <span data-ttu-id="83e71-110">Para agrupar componentes, el flujo de control, el flujo de datos o el controlador de eventos deben contener más de un componente.</span><span class="sxs-lookup"><span data-stu-id="83e71-110">To group components, the control flow, data flow, or event handler must contain more than one component.</span></span>  
  
-   <span data-ttu-id="83e71-111">Los grupos también pueden anidarse, permitiendo la creación de grupos dentro de grupos.</span><span class="sxs-lookup"><span data-stu-id="83e71-111">Groups can also be nested, making it possible to create groups within groups.</span></span> <span data-ttu-id="83e71-112">La superficie de diseño puede implementar varios grupos no anidados, pero un componente solamente puede pertenecer a un grupo, a menos que los grupos estén anidados.</span><span class="sxs-lookup"><span data-stu-id="83e71-112">The design surface can implement multiple un-nested groups, but a component can belong to only one group, unless the groups are nested.</span></span>  
  
-   <span data-ttu-id="83e71-113">Cuando se guarda un paquete, el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] guarda la agrupación, pero la agrupación no tiene ningún efecto sobre la ejecución de paquetes.</span><span class="sxs-lookup"><span data-stu-id="83e71-113">When a package is saved, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the grouping, but the grouping has no effect on package execution.</span></span> <span data-ttu-id="83e71-114">La capacidad para agrupar componentes es una característica de tiempo de diseño que no afecta al comportamiento de tiempo de ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="83e71-114">The ability to group components is a design-time feature; it does not affect the run-time behavior of the package.</span></span>  
  
### <a name="to-group-components"></a><span data-ttu-id="83e71-115">Para agrupar componentes</span><span class="sxs-lookup"><span data-stu-id="83e71-115">To group components</span></span>  
  
1.  <span data-ttu-id="83e71-116">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="83e71-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="83e71-117">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="83e71-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="83e71-118">Haga clic en la pestaña **Flujo de control**, **Flujo de datos**o **Controladores de eventos** .</span><span class="sxs-lookup"><span data-stu-id="83e71-118">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="83e71-119">En la superficie de diseño de la pestaña, seleccione los componentes que quiera agrupar, haga clic con el botón derecho en un componente que haya seleccionado y, después, haga clic en **Agrupar**.</span><span class="sxs-lookup"><span data-stu-id="83e71-119">On the design surface of the tab, select the components you want to group, right-click a selected component, and then click **Group**.</span></span>  
  
5.  <span data-ttu-id="83e71-120">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="83e71-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-ungroup-components"></a><span data-ttu-id="83e71-121">Para desagrupar componentes</span><span class="sxs-lookup"><span data-stu-id="83e71-121">To ungroup components</span></span>  
  
1.  <span data-ttu-id="83e71-122">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="83e71-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="83e71-123">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="83e71-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="83e71-124">Haga clic en la pestaña **Flujo de control**, **Flujo de datos**o **Controladores de eventos** .</span><span class="sxs-lookup"><span data-stu-id="83e71-124">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="83e71-125">En la superficie de diseño de la pestaña, seleccione el grupo que contenga el componente que quiera desagrupar, haga clic con el botón derecho y, después, haga clic en **Desagrupar**.</span><span class="sxs-lookup"><span data-stu-id="83e71-125">On the design surface of the tab, select the group that contains the component you want to ungroup, right-click, and then click **Ungroup**.</span></span>  
  
5.  <span data-ttu-id="83e71-126">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="83e71-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e71-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83e71-127">See Also</span></span>  
 [<span data-ttu-id="83e71-128">Agregar o eliminar tareas o contenedores en un flujo de control</span><span class="sxs-lookup"><span data-stu-id="83e71-128">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
     
 [<span data-ttu-id="83e71-129">Conectar tareas y contenedores mediante una restricción de precedencia predeterminada</span><span class="sxs-lookup"><span data-stu-id="83e71-129">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md)  
  
  
