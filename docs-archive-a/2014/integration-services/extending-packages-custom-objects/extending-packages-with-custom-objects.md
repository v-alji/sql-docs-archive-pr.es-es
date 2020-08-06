---
title: Ampliar paquetes con objetos personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
ms.assetid: 26616eb8-9e80-434d-b22a-ece1b00f449d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0159983f518e51aa082ea23745663e7f09eee1fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743602"
---
# <a name="extending-packages-with-custom-objects"></a><span data-ttu-id="c0316-102">Ampliar paquetes con objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="c0316-102">Extending Packages with Custom Objects</span></span>
  <span data-ttu-id="c0316-103">Si los componentes que proporciona [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no satisfacen sus requisitos, puede ampliar la eficacia de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] codificando sus propias extensiones.</span><span class="sxs-lookup"><span data-stu-id="c0316-103">If you find that the components provided in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="c0316-104">Cuenta con dos opciones diferenciadas para ampliar los paquetes: puede escribir código dentro de los potentes contenedores que proporcionan la tarea Script y el componente de script o puede crear extensiones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personalizadas desde cero derivando de las clases base que proporciona el modelo de objetos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0316-104">You have two discrete options for extending your packages: you can write code within the powerful wrappers provided by the Script task and the Script component, or you can create custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] extensions from scratch by deriving from the base classes provided by the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model.</span></span>  
  
 <span data-ttu-id="c0316-105">En esta sección, se explora la opción más avanzada de las dos, la ampliación de paquetes con objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="c0316-105">This section explores the more advanced of the two options - extending packages with custom objects.</span></span>  
  
 <span data-ttu-id="c0316-106">Cuando la solución de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personalizada requiere mayor flexibilidad de la que proporcionan la tarea Script y el componente de script (o cuando necesita un componente que se pueda volver a utilizar en varios paquetes) el modelo de objetos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] permite crear tareas personalizadas, componentes de flujo de datos y otros objetos de paquete en código administrado a partir de cero.</span><span class="sxs-lookup"><span data-stu-id="c0316-106">When your custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solution requires more flexibility than the Script task and the Script component provide, or when you need a component that you can reuse in multiple packages, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model lets you build custom tasks, data flow components, and other package objects in managed code from the ground up.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0316-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c0316-107">In This Section</span></span>  
 [<span data-ttu-id="c0316-108">Desarrollar objetos personalizados para Integration Services</span><span class="sxs-lookup"><span data-stu-id="c0316-108">Developing Custom Objects for Integration Services</span></span>](developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="c0316-109">Describe los objetos personalizados que se pueden crear para [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] y resume los pasos y valores esenciales.</span><span class="sxs-lookup"><span data-stu-id="c0316-109">Discusses the custom objects that can be created for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and summarizes the essential steps and settings.</span></span>  
  
 [<span data-ttu-id="c0316-110">Conservar objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="c0316-110">Persisting Custom Objects</span></span>](persisting-custom-objects.md)  
 <span data-ttu-id="c0316-111">Describe la persistencia predeterminada de los objetos personalizados y el proceso de implementación de la persistencia personalizada.</span><span class="sxs-lookup"><span data-stu-id="c0316-111">Discusses the default persistence of custom objects, and the process of implementing custom persistence.</span></span>  
  
 [<span data-ttu-id="c0316-112">Generar, implementar y depurar objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="c0316-112">Building, Deploying, and Debugging Custom Objects</span></span>](building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="c0316-113">Describe los enfoques comunes para generar, implementar y probar los diferentes tipos de objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="c0316-113">Discusses the common approaches to building, deploying and testing the various types of custom objects.</span></span>  
  
 [<span data-ttu-id="c0316-114">Desarrollar una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="c0316-114">Developing a Custom Task</span></span>](task/developing-a-custom-task.md)  
 <span data-ttu-id="c0316-115">Describe el proceso de codificación de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="c0316-115">Describes the process of coding a custom task.</span></span>  
  
 [<span data-ttu-id="c0316-116">Desarrollar un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="c0316-116">Developing a Custom Connection Manager</span></span>](connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="c0316-117">Describe el proceso de codificación de un administrador de conexiones personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0316-117">Describes the process of coding a custom connection manager.</span></span>  
  
 [<span data-ttu-id="c0316-118">Desarrollar un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="c0316-118">Developing a Custom Log Provider</span></span>](log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="c0316-119">Describe el proceso de codificación de un proveedor de registro personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0316-119">Describes the process of coding a custom log provider.</span></span>  
  
 [<span data-ttu-id="c0316-120">Desarrollar un enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="c0316-120">Developing a Custom ForEach Enumerator</span></span>](foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="c0316-121">Describe el proceso de codificación de un enumerador personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0316-121">Describes the process of coding a custom enumerator.</span></span>  
  
 [<span data-ttu-id="c0316-122">Desarrollar un componente de flujo de datos personalizado</span><span class="sxs-lookup"><span data-stu-id="c0316-122">Developing a Custom Data Flow Component</span></span>](data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="c0316-123">Describe cómo programar orígenes, transformaciones y destinos personalizados del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="c0316-123">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c0316-124">Referencia</span><span class="sxs-lookup"><span data-stu-id="c0316-124">Reference</span></span>  
 [<span data-ttu-id="c0316-125">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="c0316-125">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
 <span data-ttu-id="c0316-126">Muestra los códigos de error predefinidos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] con sus nombres simbólicos y sus descripciones.</span><span class="sxs-lookup"><span data-stu-id="c0316-126">Lists the predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error codes with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c0316-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c0316-127">Related Sections</span></span>  
 [<span data-ttu-id="c0316-128">Ampliar paquetes con scripting</span><span class="sxs-lookup"><span data-stu-id="c0316-128">Extending Packages with Scripting</span></span>](../extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="c0316-129">Describe cómo extender el flujo de control mediante la tarea Script o el flujo de datos mediante el componente de script.</span><span class="sxs-lookup"><span data-stu-id="c0316-129">Discusses how to extend the control flow by using the Script task, or extend the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="c0316-130">Compilar paquetes mediante programación</span><span class="sxs-lookup"><span data-stu-id="c0316-130">Building Packages Programmatically</span></span>](../building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="c0316-131">Describe cómo crear, configurar, ejecutar, cargar, guardar y administrar paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] mediante programación.</span><span class="sxs-lookup"><span data-stu-id="c0316-131">Describes how to create, configure, run, load, save, and manage [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
<span data-ttu-id="c0316-132">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c0316-132">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c0316-133">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="c0316-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c0316-134">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="c0316-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c0316-135">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="c0316-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0316-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0316-136">See Also</span></span>  
 <span data-ttu-id="c0316-137">[Comparar soluciones de scripting y objetos personalizados](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="c0316-137">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="c0316-138">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="c0316-138">SQL Server Integration Services</span></span>](../sql-server-integration-services.md)  
  
  
