---
title: Volver a utilizar objetos de paquete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- GUID regenerating [Integration Services]
- reusing packages
- templates [Integration Services]
- copying packages
- regenerating package GUID
ms.assetid: 08f723bf-15b5-44bd-9a46-04e8781bfbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b7612cb2684bb842108068b062e54fbe9dee4327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744751"
---
# <a name="reuse-of-package-objects"></a><span data-ttu-id="6c775-102">Volver a utilizar objetos de paquete</span><span class="sxs-lookup"><span data-stu-id="6c775-102">Reuse of Package Objects</span></span>
  <span data-ttu-id="6c775-103">Funcionalidad frecuente de paquetes que desea volver a usar.</span><span class="sxs-lookup"><span data-stu-id="6c775-103">Frequently packages functionality that you want to reuse.</span></span> <span data-ttu-id="6c775-104">Por ejemplo, si creó un conjunto de tareas, es posible que desee volver a utilizar todos los elementos como grupo, o que desee volver a utilizar un único elemento, como por ejemplo, un administrador de conexiones que creó en un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] diferente.</span><span class="sxs-lookup"><span data-stu-id="6c775-104">For example, if you created a set of tasks, you might want to reuse the items together as a group, or you might want to reuse a single item such as a connection manager that you created in a different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
## <a name="copy-and-paste"></a><span data-ttu-id="6c775-105">Copiar y pegar</span><span class="sxs-lookup"><span data-stu-id="6c775-105">Copy and Paste</span></span>  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="6c775-106">y el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] admiten la funcionalidad de copiar y pegar objetos de paquete, que puede incluir elementos de flujo de control, elementos de flujo de datos y administradores de conexión.</span><span class="sxs-lookup"><span data-stu-id="6c775-106">and [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer support copying and pasting package objects, which can include control flow items, data flow items, and connection managers.</span></span> <span data-ttu-id="6c775-107">Puede copiar y pegar entre proyectos y entre paquetes.</span><span class="sxs-lookup"><span data-stu-id="6c775-107">You can copy and paste between projects and between packages.</span></span> <span data-ttu-id="6c775-108">Si la solución contiene varios proyectos, puede copiar entre proyectos, y los proyectos pueden ser de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="6c775-108">If the solution contains multiple projects you can copy between projects, and the projects can be of different types.</span></span>  
  
 <span data-ttu-id="6c775-109">Si una solución contiene varios paquetes, puede copiar y pegar entre éstos.</span><span class="sxs-lookup"><span data-stu-id="6c775-109">If a solution contains multiple packages, you can copy and paste between them.</span></span> <span data-ttu-id="6c775-110">Los paquetes pueden pertenecer a los mismos proyectos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o a proyectos diferentes.</span><span class="sxs-lookup"><span data-stu-id="6c775-110">The packages can be in the same or different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="6c775-111">Sin embargo, los objetos de paquete pueden tener dependencias de otros objetos, sin las cuales no son válidos.</span><span class="sxs-lookup"><span data-stu-id="6c775-111">However, package objects may have dependencies on other objects, without which they are not valid.</span></span> <span data-ttu-id="6c775-112">Por ejemplo, una tarea Ejecutar SQL utiliza un administrador de conexiones que también debe copiar para que la tarea funcione.</span><span class="sxs-lookup"><span data-stu-id="6c775-112">For example, an Execute SQL task uses a connection manager, which you must copy as well to make the task work.</span></span> <span data-ttu-id="6c775-113">Asimismo, algunos objetos de paquete requieren que el paquete ya contenga un determinado objeto, ya que sin este objeto no podrá copiar ni pegar objetos correctamente en un paquete.</span><span class="sxs-lookup"><span data-stu-id="6c775-113">Also, some package objects require that the package already contain a certain object, and without this object you cannot successfully paste the copied objects into a package.</span></span> <span data-ttu-id="6c775-114">Por ejemplo, no puede pegar un flujo de datos en un paquete que no tiene al menos una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6c775-114">For example, you cannot paste a data flow into a package that does not have at least one Data Flow task.</span></span>  
  
 <span data-ttu-id="6c775-115">Puede encontrarse con que copia siempre los mismos paquetes.</span><span class="sxs-lookup"><span data-stu-id="6c775-115">You may find that you copy the same packages repeatedly.</span></span> <span data-ttu-id="6c775-116">Para evitar el proceso de copia, puede designar estos paquetes como plantillas y utilizarlos en la creación de nuevos paquetes.</span><span class="sxs-lookup"><span data-stu-id="6c775-116">To avoid the copy process, you can designate these packages as templates and use them when you create new packages.</span></span>  
  
 <span data-ttu-id="6c775-117">Cuando copia un objeto de paquete, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] automáticamente asigna un nuevo GUID a la propiedad `ID` del nuevo objeto y actualiza la propiedad `Name`.</span><span class="sxs-lookup"><span data-stu-id="6c775-117">When you copy a package object, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] automatically assigns a new GUID to the `ID` property of the new object and updates the `Name` property.</span></span>  
  
 <span data-ttu-id="6c775-118">Las variables no se pueden copiar.</span><span class="sxs-lookup"><span data-stu-id="6c775-118">You cannot copy variables.</span></span> <span data-ttu-id="6c775-119">Si un objeto, como una tarea, utiliza variables, debe volver a crear las variables en el paquete de destino.</span><span class="sxs-lookup"><span data-stu-id="6c775-119">If an object such as a task uses variables, then you must re-create the variables in the destination package.</span></span> <span data-ttu-id="6c775-120">Por el contrario, si copia todo el paquete, también se copian las variables del paquete.</span><span class="sxs-lookup"><span data-stu-id="6c775-120">In contrast, if you copy the entire package, then the variables in the package are also copied.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6c775-121">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6c775-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6c775-122">Copiar objetos de paquete</span><span class="sxs-lookup"><span data-stu-id="6c775-122">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
-   [<span data-ttu-id="6c775-123">Copiar los elementos de proyectos</span><span class="sxs-lookup"><span data-stu-id="6c775-123">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
-   [<span data-ttu-id="6c775-124">Guardar un paquete como una plantilla de paquete</span><span class="sxs-lookup"><span data-stu-id="6c775-124">Save a Package as a Package Template</span></span>](../../2014/integration-services/save-a-package-as-a-package-template.md)  
  
  
