---
title: Desarrollar un administrador de conexiones personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], connections
- custom connection managers [Integration Services], about custom connection managers
- connection managers [Integration Services], custom
- Integration Services packages, connection managers
- SSIS packages, connection managers
- SQL Server Integration Services packages, connection managers
- custom connection managers [Integration Services]
ms.assetid: bda0b29e-57f5-4879-b04d-1396dc56daa8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19c5a9066db6542742537a41a7f567d1b4b1d23d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751302"
---
# <a name="developing-a-custom-connection-manager"></a><span data-ttu-id="2ef14-102">Desarrollar un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="2ef14-102">Developing a Custom Connection Manager</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="2ef14-103">usa administradores de conexión para encapsular la información necesaria para conectarse a un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="2ef14-103">uses connection managers to encapsulate the information needed to connect to an external data source.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="2ef14-104">incluye diversos administradores de conexión que admiten conexiones a los orígenes de datos usados con más frecuencia, desde bases de datos empresariales hasta archivos de texto y hojas de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="2ef14-104">includes a variety of connection managers that support connections to the most commonly used data sources, from enterprise databases to text files and Excel worksheets.</span></span> <span data-ttu-id="2ef14-105">Si [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] admite administradores de conexiones y orígenes de datos externos que no cumplen completamente sus requisitos, puede crear un administrador de conexiones personalizado.</span><span class="sxs-lookup"><span data-stu-id="2ef14-105">If the connection managers and external data sources supported by [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] do not entirely meet your requirements, you can create a custom connection manager.</span></span>  
  
 <span data-ttu-id="2ef14-106">Para crear un administrador de conexiones personalizado, debe crear una clase que herede de la clase base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, aplicar el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> a la nueva clase e invalidar los métodos y propiedades importantes de la clase base, incluidos la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> y el método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ef14-106">To create a custom connection manager, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2ef14-107">Muchas de las tareas, orígenes y destinos que se han incluido en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] se usan únicamente con tipos específicos de administradores de conexiones integrados.</span><span class="sxs-lookup"><span data-stu-id="2ef14-107">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="2ef14-108">Antes de desarrollar un administrador de conexiones personalizado para utilizar con tareas y componentes integrados, compruebe si esos componentes restringen la lista de administradores de conexiones disponibles a aquéllos de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="2ef14-108">Before developing a custom connection manager for use with built-in tasks and components, check whether those components restrict the list of available connection managers to those of a specific type.</span></span> <span data-ttu-id="2ef14-109">Si su solución requiere un administrador de conexiones personalizado, también podría tener que desarrollar una tarea personalizada, o un origen o destino personalizados, para su uso con el administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="2ef14-109">If your solution requires a custom connection manager, you might also have to develop a custom task, or a custom source or destination, for use with the connection manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ef14-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2ef14-110">In This Section</span></span>  
 <span data-ttu-id="2ef14-111">En esta sección se describe cómo crear, configurar y codificar un administrador de conexiones y su interfaz de usuario personalizada opcional.</span><span class="sxs-lookup"><span data-stu-id="2ef14-111">This section describes how to create, configure, and code a custom connection manager and its optional custom user interface.</span></span> <span data-ttu-id="2ef14-112">Los fragmentos de código mostrados en esta sección se deducen del ejemplo de administrador de conexiones personalizado de Sql Server.</span><span class="sxs-lookup"><span data-stu-id="2ef14-112">The code snippets shown in this section are drawn from the Sql Server Custom Connection Manager Sample.</span></span>  
  
 [<span data-ttu-id="2ef14-113">Crear un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="2ef14-113">Creating a Custom Connection Manager</span></span>](creating-a-custom-connection-manager.md)  
 <span data-ttu-id="2ef14-114">Describe cómo crear las clases para un proyecto de administrador de conexiones personalizado.</span><span class="sxs-lookup"><span data-stu-id="2ef14-114">Describes how to create the classes for a custom connection manager project.</span></span>  
  
 [<span data-ttu-id="2ef14-115">Codificar un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="2ef14-115">Coding a Custom Connection Manager</span></span>](coding-a-custom-connection-manager.md)  
 <span data-ttu-id="2ef14-116">Describe cómo implementar un administrador de conexiones personalizado invalidando los métodos y propiedades de la clase base.</span><span class="sxs-lookup"><span data-stu-id="2ef14-116">Describes how to implement a custom connection manager by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="2ef14-117">Desarrollar una interfaz de usuario para un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="2ef14-117">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
 <span data-ttu-id="2ef14-118">Describe cómo implementar la clase de interfaz de usuario y el formulario que se utilizan para configurar el administrador de conexiones personalizado.</span><span class="sxs-lookup"><span data-stu-id="2ef14-118">Describes how to implement the user interface class and the form that is used to configure the custom connection manager.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2ef14-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2ef14-119">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="2ef14-120">Información común a todos los objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="2ef14-120">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="2ef14-121">Para obtener información común a todos los tipos de objetos personalizados que puede crear en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2ef14-121">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="2ef14-122">Desarrollar objetos personalizados para Integration Services</span><span class="sxs-lookup"><span data-stu-id="2ef14-122">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="2ef14-123">Describe los pasos básicos para implementar todos los tipos de objetos personalizados para [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ef14-123">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="2ef14-124">Conservar objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="2ef14-124">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="2ef14-125">Describe la persistencia personalizada y explica cuándo es necesaria.</span><span class="sxs-lookup"><span data-stu-id="2ef14-125">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="2ef14-126">Generar, implementar y depurar objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="2ef14-126">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="2ef14-127">Describe las técnicas para generar, firmar, implementar y depurar objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="2ef14-127">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="2ef14-128">Información sobre otros objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="2ef14-128">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="2ef14-129">Para obtener información sobre los demás tipos de objetos personalizados que puede crear en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2ef14-129">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="2ef14-130">Desarrollar una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="2ef14-130">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="2ef14-131">Describe cómo programar las tareas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2ef14-131">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="2ef14-132">Desarrollar un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="2ef14-132">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="2ef14-133">Describe cómo programar los proveedores de registro personalizados.</span><span class="sxs-lookup"><span data-stu-id="2ef14-133">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="2ef14-134">Desarrollar un enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="2ef14-134">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="2ef14-135">Describe cómo programar los enumeradores personalizados.</span><span class="sxs-lookup"><span data-stu-id="2ef14-135">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="2ef14-136">Desarrollar un componente de flujo de datos personalizado</span><span class="sxs-lookup"><span data-stu-id="2ef14-136">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="2ef14-137">Describe cómo programar orígenes, transformaciones y destinos personalizados del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="2ef14-137">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="2ef14-138">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2ef14-138">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2ef14-139">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="2ef14-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2ef14-140">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="2ef14-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2ef14-141">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="2ef14-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
