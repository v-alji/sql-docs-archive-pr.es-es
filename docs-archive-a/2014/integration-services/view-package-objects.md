---
title: Ver objetos de paquete | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, properties
- properties [Integration Services]
- Package Explorer window [Integration Services]
- packages [Integration Services], properties
- explorer view [Integration Services]
- SSIS packages, properties
- viewing package objects
- SQL Server Integration Services packages, properties
ms.assetid: a85c0245-0a68-4eb0-83b1-9b11df80bd10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffe46be35db26186f715b18ba6114732d130e02e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674893"
---
# <a name="view-package-objects"></a><span data-ttu-id="f4c78-102">Ver objetos de paquete</span><span class="sxs-lookup"><span data-stu-id="f4c78-102">View Package Objects</span></span>
  <span data-ttu-id="f4c78-103">En el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] , la pestaña **Explorador de paquetes** proporciona una vista de explorador del paquete.</span><span class="sxs-lookup"><span data-stu-id="f4c78-103">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the **Package Explorer** tab provides an explorer view of the package.</span></span> <span data-ttu-id="f4c78-104">La vista refleja la jerarquía de contenedores de la arquitectura de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4c78-104">The view reflects the container hierarchy of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] architecture.</span></span> <span data-ttu-id="f4c78-105">El contenedor de paquetes se encuentra en la parte superior de la jerarquía y puede expandir el paquete para ver las conexiones, ejecutables, controladores de eventos, proveedores de registro, restricciones de precedencia y variables del paquete.</span><span class="sxs-lookup"><span data-stu-id="f4c78-105">The package container is at the top of the hierarchy, and you expand the package to view the connections, executables, event handlers, log providers, precedence constraints, and variables in the package.</span></span>

 <span data-ttu-id="f4c78-106">Los ejecutables, que son los contenedores y las tareas del paquete, pueden incluir controladores de eventos, restricciones de precedencia y variables.</span><span class="sxs-lookup"><span data-stu-id="f4c78-106">The executables, which are the containers and tasks in the package, can include event handlers, precedence constraints, and variables.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f4c78-107">admite una jerarquía anidada de contenedores, y los contenedores de bucles For, bucles Foreach y secuencias pueden incluir otros ejecutables.</span><span class="sxs-lookup"><span data-stu-id="f4c78-107">supports a nested hierarchy of containers, and the For Loop, Foreach Loop, and Sequence containers can include other executables.</span></span>

 <span data-ttu-id="f4c78-108">Si un paquete incluye un flujo de datos, el **Explorador de paquetes** incluye la tarea Flujo de datos y una carpeta **Componentes** que enumera los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="f4c78-108">If a package includes a data flow, the **Package Explorer** lists the Data Flow task and includes a **Components** folder that lists the data flow components.</span></span>

 <span data-ttu-id="f4c78-109">Desde la pestaña **Explorador de paquetes** , puede eliminar objetos en un paquete y obtener acceso a la ventana **Propiedades** para ver las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="f4c78-109">From the **Package Explorer** tab, you can delete objects in a package and access the **Properties** window to view object properties.</span></span>

 <span data-ttu-id="f4c78-110">El siguiente diagrama muestra una vista de árbol de un paquete simple.</span><span class="sxs-lookup"><span data-stu-id="f4c78-110">The following diagram shows a tree view of a simple package.</span></span>

 <span data-ttu-id="f4c78-111">![Captura de pantalla de la pestaña Explorador de paquetes](media/packageexplorer.gif "Captura de pantalla de la pestaña Explorador de paquetes")</span><span class="sxs-lookup"><span data-stu-id="f4c78-111">![Screenshot of the Package Explorer tab](media/packageexplorer.gif "Screenshot of the Package Explorer tab")</span></span>

### <a name="to-view-package-content"></a><span data-ttu-id="f4c78-112">Para ver el contenido de los paquetes</span><span class="sxs-lookup"><span data-stu-id="f4c78-112">To view package content</span></span>

-   [<span data-ttu-id="f4c78-113">Ver objetos de paquete en el Explorador de paquetes</span><span class="sxs-lookup"><span data-stu-id="f4c78-113">View Package Objects in Package Explorer</span></span>](../../2014/integration-services/view-package-objects-in-package-explorer.md)

## <a name="see-also"></a><span data-ttu-id="f4c78-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4c78-114">See Also</span></span>
 <span data-ttu-id="f4c78-115">[Integration Services las tareas](control-flow/integration-services-tasks.md) [Integration Services](control-flow/integration-services-containers.md) las [restricciones de precedencia](control-flow/precedence-constraints.md) de los contenedores [Integration Services &#40;las variables de&#41; de SSIS](integration-services-ssis-variables.md) [Integration Services &#40;los controladores de eventos&#41; SSIS](integration-services-ssis-event-handlers.md) Integration Services &#40;el registro de&#41; de [SSIS](performance/integration-services-ssis-logging.md)</span><span class="sxs-lookup"><span data-stu-id="f4c78-115">[Integration Services Tasks](control-flow/integration-services-tasks.md) [Integration Services Containers](control-flow/integration-services-containers.md) [Precedence Constraints](control-flow/precedence-constraints.md) [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) [Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md)</span></span>


