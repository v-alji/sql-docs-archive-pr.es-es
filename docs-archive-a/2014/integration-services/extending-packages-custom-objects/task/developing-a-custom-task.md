---
title: Desarrollar una tarea personalizada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom tasks [Integration Services], about custom tasks
- Task class
- custom tasks [Integration Services]
- SSIS custom tasks
- SSIS custom tasks, about custom tasks
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- tasks [Integration Services], custom
- TaskHost object
ms.assetid: dcbd8615-fa6d-4ddb-b8a5-0b19dddd6239
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d9d3446acff7ced73ab47014bec51708dba225b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674952"
---
# <a name="developing-a-custom-task"></a><span data-ttu-id="2f9db-102">Desarrollar una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="2f9db-102">Developing a Custom Task</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="2f9db-103">usa tareas para realizar unidades de trabajo con el fin de admitir la extracción, transformación y carga de datos.</span><span class="sxs-lookup"><span data-stu-id="2f9db-103">uses tasks to perform units of work in support of the extraction, transformation, and loading of data.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="2f9db-104">incluye varias tareas que realizan las acciones usadas con más frecuencia, desde ejecutar una instrucción SQL hasta descargar un archivo de un sitio FTP.</span><span class="sxs-lookup"><span data-stu-id="2f9db-104">includes a variety of tasks that perform the most frequently used actions, from executing an SQL statement to downloading a file from an FTP site.</span></span> <span data-ttu-id="2f9db-105">Si las tareas incluidas y las acciones compatibles no cumplen completamente sus requisitos, puede crear una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="2f9db-105">If the included tasks and supported actions do not completely meet your requirements, you can create a custom task.</span></span>  
  
 <span data-ttu-id="2f9db-106">Para crear una tarea personalizada, debe crear una clase que herede de la clase base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), aplicar el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> a la nueva clase e invalidar los métodos y propiedades importantes de la clase base, incluido el método <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f9db-106">To create a custom task, you have to create a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f9db-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2f9db-107">In This Section</span></span>  
 <span data-ttu-id="2f9db-108">En esta sección se describe cómo crear, configurar y codificar una tarea personalizada y su interfaz de usuario personalizada opcional.</span><span class="sxs-lookup"><span data-stu-id="2f9db-108">This section describes how to create, configure, and code a custom task and its optional custom user interface.</span></span>  
  
 [<span data-ttu-id="2f9db-109">Crear una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="2f9db-109">Creating a Custom Task</span></span>](creating-a-custom-task.md)  
 <span data-ttu-id="2f9db-110">Describe el primer paso, que crea la tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="2f9db-110">Describes the first step, which is creating the custom task.</span></span>  
  
 [<span data-ttu-id="2f9db-111">Codificar una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="2f9db-111">Coding a Custom Task</span></span>](coding-a-custom-task.md)  
 <span data-ttu-id="2f9db-112">Describe cómo codificar los métodos principales de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="2f9db-112">Describes how to code the principal methods of a custom task.</span></span>  
  
 [<span data-ttu-id="2f9db-113">Conectarse a orígenes de datos de una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="2f9db-113">Connecting to Data Sources in a Custom Task</span></span>](connecting-to-data-sources-in-a-custom-task.md)  
 <span data-ttu-id="2f9db-114">Describe cómo conectar una tarea personalizada a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2f9db-114">Describes how to connect a custom task to a data source.</span></span>  
  
 [<span data-ttu-id="2f9db-115">Provocar y definir eventos en una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="2f9db-115">Raising and Defining Events in a Custom Task</span></span>](raising-and-defining-events-in-a-custom-task.md)  
 <span data-ttu-id="2f9db-116">Describe cómo provocar eventos y definir eventos personalizados de la tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="2f9db-116">Describes how to raise events and define custom events from the custom task.</span></span>  
  
 [<span data-ttu-id="2f9db-117">Agregar compatibilidad con la depuración de una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="2f9db-117">Adding Support for Debugging in a Custom Task</span></span>](adding-support-for-debugging-in-a-custom-task.md)  
 <span data-ttu-id="2f9db-118">Describe cómo crear los destinos de punto de interrupción en la tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="2f9db-118">Describes how to create breakpoint targets in the custom task.</span></span>  
  
 [<span data-ttu-id="2f9db-119">Desarrollar una interfaz de usuario para una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="2f9db-119">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
 <span data-ttu-id="2f9db-120">Describe cómo crear una interfaz de usuario que se muestra en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] para configurar propiedades en la tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="2f9db-120">Describes how to create a user interface that shows in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to configure properties on the custom task.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2f9db-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2f9db-121">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="2f9db-122">Información común a todos los objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="2f9db-122">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="2f9db-123">Para obtener información común a todos los tipos de objetos personalizados que puede crear en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f9db-123">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="2f9db-124">Desarrollar objetos personalizados para Integration Services</span><span class="sxs-lookup"><span data-stu-id="2f9db-124">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="2f9db-125">Describe los pasos básicos para implementar todos los tipos de objetos personalizados para [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f9db-125">Describes the basic steps in implementing all kinds of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="2f9db-126">Conservar objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="2f9db-126">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="2f9db-127">Describe la persistencia personalizada y explica cuándo es necesaria.</span><span class="sxs-lookup"><span data-stu-id="2f9db-127">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="2f9db-128">Generar, implementar y depurar objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="2f9db-128">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="2f9db-129">Describe las técnicas para generar, firmar, implementar y depurar objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="2f9db-129">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="2f9db-130">Información sobre otros objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="2f9db-130">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="2f9db-131">Para obtener información acerca de los demás tipos de objetos personalizados que puede crear en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f9db-131">For information about the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="2f9db-132">Desarrollar un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="2f9db-132">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="2f9db-133">Describe cómo programar los administradores de conexiones personalizados.</span><span class="sxs-lookup"><span data-stu-id="2f9db-133">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="2f9db-134">Desarrollar un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="2f9db-134">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="2f9db-135">Describe cómo programar los proveedores de registro personalizados.</span><span class="sxs-lookup"><span data-stu-id="2f9db-135">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="2f9db-136">Desarrollar un enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="2f9db-136">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="2f9db-137">Describe cómo programar los enumeradores personalizados.</span><span class="sxs-lookup"><span data-stu-id="2f9db-137">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="2f9db-138">Desarrollar un componente de flujo de datos personalizado</span><span class="sxs-lookup"><span data-stu-id="2f9db-138">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="2f9db-139">Describe cómo programar orígenes, transformaciones y destinos personalizados del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="2f9db-139">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="2f9db-140">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2f9db-140">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2f9db-141">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="2f9db-141">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2f9db-142">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="2f9db-142">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2f9db-143">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="2f9db-143">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f9db-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f9db-144">See Also</span></span>  
 <span data-ttu-id="2f9db-145">[Extender el paquete con la tarea Script](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span><span class="sxs-lookup"><span data-stu-id="2f9db-145">[Extending the Package with the Script Task](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span></span>  
 [<span data-ttu-id="2f9db-146">Comparar soluciones de scripting y objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="2f9db-146">Comparing Scripting Solutions and Custom Objects</span></span>](../../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md)  
  
  
