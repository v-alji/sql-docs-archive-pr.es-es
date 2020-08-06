---
title: Guía para desarrolladores&#39;(Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Integration Services, programming
- SSIS, programming
- SQL Server Integration Services, programming
- packages [Integration Services], programming
ms.assetid: 60fe148b-a7c4-4289-ae3e-2e949fc1886c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c16ec1a21cf7ebb711f6d3996eb6239ea052c83c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676051"
---
# <a name="developer39s-guide-integration-services"></a><span data-ttu-id="0c955-102">Guía para desarrolladores&#39;(Integration Services)</span><span class="sxs-lookup"><span data-stu-id="0c955-102">Developer&#39;s Guide (Integration Services)</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="0c955-103">incluye un modelo de objetos completamente reescrito, que se ha mejorado con muchas características que consiguen que la extensión y la programación de paquetes resulten más sencillas, flexibles y eficaces.</span><span class="sxs-lookup"><span data-stu-id="0c955-103">includes a completely rewritten object model, which has been enhanced with many features that make extending and programming packages easier, more flexible, and more powerful.</span></span> <span data-ttu-id="0c955-104">Los desarrolladores pueden extender y programar prácticamente cualquier aspecto de los paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c955-104">Developers can extend and program almost every aspect of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="0c955-105">Como desarrollador de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], existen dos enfoques fundamentales que puede aplicar en la programación de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0c955-105">As an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] developer, there are two fundamental approaches that you can take to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming:</span></span>  
  
-   <span data-ttu-id="0c955-106">Puede extender los paquetes escribiendo componentes que pasan a estar disponibles en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] para proporcionar funcionalidad personalizada en un paquete.</span><span class="sxs-lookup"><span data-stu-id="0c955-106">You can extend packages by writing components that become available within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to provide custom functionality in a package.</span></span>  
  
-   <span data-ttu-id="0c955-107">Puede crear, configurar y ejecutar paquetes mediante programación desde sus propias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0c955-107">You can create, configure, and run packages programmatically from your own applications.</span></span>  
  
 <span data-ttu-id="0c955-108">Si los componentes integrados en [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no cumplen sus requisitos, puede ampliar la potencia de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] codificando sus propias extensiones.</span><span class="sxs-lookup"><span data-stu-id="0c955-108">If you find that the built-in components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="0c955-109">En este enfoque, tiene dos opciones diferentes:</span><span class="sxs-lookup"><span data-stu-id="0c955-109">In this approach, you have two discrete options:</span></span>  
  
-   <span data-ttu-id="0c955-110">Para el uso ad hoc en un paquete único, puede crear una tarea personalizada escribiendo código en la tarea Script o bien crear un componente de flujo de datos personalizado escribiendo código en el componente de script, que puede configurar como origen, transformación o destino.</span><span class="sxs-lookup"><span data-stu-id="0c955-110">For ad hoc use in a single package, you can create a custom task by writing code in the Script task, or a custom data flow component by writing code in the Script component, which you can configure as a source, transformation, or destination.</span></span> <span data-ttu-id="0c955-111">Estos eficaces contenedores escriben automáticamente el código de la infraestructura y permiten centrarse exclusivamente en desarrollar la funcionalidad personalizada; sin embargo, no se reutilizan con facilidad en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="0c955-111">These powerful wrappers write the infrastructure code for you and let you focus exclusively on developing your custom functionality; however, they are not easily reusable elsewhere.</span></span>  
  
-   <span data-ttu-id="0c955-112">Para el uso en varios paquetes, puede crear extensiones de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] personalizadas como administradores de conexión, tareas, enumeradores, proveedores de registro y componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="0c955-112">For use in multiple packages, you can create custom [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] extensions such as connection managers, tasks, enumerators, log providers, and data flow components.</span></span> <span data-ttu-id="0c955-113">El modelo de objetos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] administrado contiene clases base que proporcionan un punto de inicio y consiguen que el desarrollo de extensiones resulte más fácil que nunca.</span><span class="sxs-lookup"><span data-stu-id="0c955-113">The managed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model contains base classes that provide a starting point and make developing custom extensions easier than ever.</span></span>  
  
 <span data-ttu-id="0c955-114">Si desea crear paquetes de forma dinámica o administrar y ejecutar paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fuera del entorno de desarrollo, puede manipular los paquetes mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0c955-114">If you want to create packages dynamically, or to manage and run [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages outside the development environment, you can manipulate packages programmatically.</span></span> <span data-ttu-id="0c955-115">Puede cargar, modificar y ejecutar los paquetes existentes o bien puede crear y ejecutar paquetes completamente nuevos mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0c955-115">You can load, modify, and run existing packages, or you can create and run entirely new packages programmatically.</span></span> <span data-ttu-id="0c955-116">En este enfoque, tiene un intervalo de opciones continuo:</span><span class="sxs-lookup"><span data-stu-id="0c955-116">In this approach, you have a continuous range of options:</span></span>  
  
-   <span data-ttu-id="0c955-117">Cargar y ejecutar un paquete existente sin modificarlo.</span><span class="sxs-lookup"><span data-stu-id="0c955-117">Load and run an existing package without modification.</span></span>  
  
-   <span data-ttu-id="0c955-118">Cargar un paquete existente, volver a configurarlo (por ejemplo, especificar un origen de datos diferente) y ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="0c955-118">Load an existing package, reconfigure it (for example, specify a different data source), and run it.</span></span>  
  
-   <span data-ttu-id="0c955-119">Crear un nuevo paquete, agregar y configurar componentes, realizar cambios objeto a objeto y propiedad a propiedad, guardarlo y ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="0c955-119">Create a new package, add and configure components, making changes object by object and property by property, save it, and then run it.</span></span>  
  
 <span data-ttu-id="0c955-120">Estos enfoques de la programación de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] se describen en esta sección y se muestran con ejemplos.</span><span class="sxs-lookup"><span data-stu-id="0c955-120">These approaches to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming are described in this section and demonstrated with examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0c955-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0c955-121">In This Section</span></span>  
 [<span data-ttu-id="0c955-122">Información general sobre la programación de Integration Services</span><span class="sxs-lookup"><span data-stu-id="0c955-122">Integration Services Programming Overview</span></span>](integration-services-programming-overview.md)  
 <span data-ttu-id="0c955-123">Describe los roles de flujo de control y flujo de datos en el desarrollo de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c955-123">Describes the roles of control flow and data flow in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] development.</span></span>  
  
 [<span data-ttu-id="0c955-124">Descripción de las transformaciones sincrónicas y asincrónicas</span><span class="sxs-lookup"><span data-stu-id="0c955-124">Understanding Synchronous and Asynchronous Transformations</span></span>](understanding-synchronous-and-asynchronous-transformations.md)  
 <span data-ttu-id="0c955-125">Describe la distinción importante entre las salidas sincrónicas y asincrónicas, y los componentes que las utilizan en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="0c955-125">Describes the important distinction between synchronous and asynchronous outputs and the components that use them in the data flow.</span></span>  
  
 [<span data-ttu-id="0c955-126">Trabajar con administradores de conexiones mediante programación</span><span class="sxs-lookup"><span data-stu-id="0c955-126">Working with Connection Managers Programmatically</span></span>](working-with-connection-managers-programmatically.md)  
 <span data-ttu-id="0c955-127">Muestra los administradores de conexiones que puede usar en el código administrado y los valores que devuelven cuando en el código se llama al método `AcquireConnection`.</span><span class="sxs-lookup"><span data-stu-id="0c955-127">Lists the connection managers that you can use from managed code, and the values that the connection managers return when the code calls the `AcquireConnection` method.</span></span>  
  
 [<span data-ttu-id="0c955-128">Ampliar paquetes con scripting</span><span class="sxs-lookup"><span data-stu-id="0c955-128">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="0c955-129">Describe cómo extender el flujo de control mediante la tarea Script o el flujo de datos mediante el componente de script.</span><span class="sxs-lookup"><span data-stu-id="0c955-129">Describes how to extend the control flow by using the Script task, or the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="0c955-130">Ampliar paquetes con objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="0c955-130">Extending Packages with Custom Objects</span></span>](extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 <span data-ttu-id="0c955-131">Describe cómo crear y programar tareas personalizadas de programa, componentes de flujo de datos y otros objetos de paquete para su uso en varios paquetes.</span><span class="sxs-lookup"><span data-stu-id="0c955-131">Describes how to create and program custom tasks, data flow components, and other package objects for use in multiple packages.</span></span>  
  
 [<span data-ttu-id="0c955-132">Compilar paquetes mediante programación</span><span class="sxs-lookup"><span data-stu-id="0c955-132">Building Packages Programmatically</span></span>](building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="0c955-133">Describe cómo crear, configurar y guardar los paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0c955-133">Describes how to create, configure, and save [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
 [<span data-ttu-id="0c955-134">Ejecutar y administrar paquetes mediante programación</span><span class="sxs-lookup"><span data-stu-id="0c955-134">Running and Managing Packages Programmatically</span></span>](run-manage-packages-programmatically/running-and-managing-packages-programmatically.md)  
 <span data-ttu-id="0c955-135">Describe cómo enumerar, ejecutar y administrar paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0c955-135">Describes how to enumerate, run, and manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0c955-136">Referencia</span><span class="sxs-lookup"><span data-stu-id="0c955-136">Reference</span></span>  
 [<span data-ttu-id="0c955-137">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="0c955-137">Integration Services Error and Message Reference</span></span>](integration-services-error-and-message-reference.md)  
 <span data-ttu-id="0c955-138">Enumera los códigos de error predefinidos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], junto con sus nombres simbólicos y descripciones.</span><span class="sxs-lookup"><span data-stu-id="0c955-138">Lists the predefined [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error codes, together with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0c955-139">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="0c955-139">Related Sections</span></span>  
 [<span data-ttu-id="0c955-140">Herramientas para solucionar problemas con el desarrollo de paquetes</span><span class="sxs-lookup"><span data-stu-id="0c955-140">Troubleshooting Tools for Package Development</span></span>](troubleshooting/troubleshooting-tools-for-package-development.md)  
 <span data-ttu-id="0c955-141">Describe las características y herramientas que ofrece [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para solucionar problemas de los paquetes durante el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="0c955-141">Describes the features and tools that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides for troubleshooting packages during development.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="0c955-142">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="0c955-142">External Resources</span></span>  
  
-   <span data-ttu-id="0c955-143">Ejemplos de CodePlex, en la página [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=131204)de www.codeplex.com/MSFTISProdSamples.</span><span class="sxs-lookup"><span data-stu-id="0c955-143">CodePlex samples, [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=131204), on www.codeplex.com/MSFTISProdSamples</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c955-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c955-144">See Also</span></span>  
 [<span data-ttu-id="0c955-145">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="0c955-145">SQL Server Integration Services</span></span>](sql-server-integration-services.md)  
  
  
