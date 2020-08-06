---
title: Desarrollar un enumerador Para cada uno personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services]
- custom foreach enumerators [Integration Services], about custom foreach enumerators
- foreach enumerators [Integration Services]
ms.assetid: bffe26e0-1b9a-47ad-bae6-6b708cb4cf4f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3d61f98266320f63d7ee56262b7c85dfb64d39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673204"
---
# <a name="developing-a-custom-foreach-enumerator"></a><span data-ttu-id="3a52b-102">Desarrollar un enumerador foreach personalizado</span><span class="sxs-lookup"><span data-stu-id="3a52b-102">Developing a Custom ForEach Enumerator</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="3a52b-103">usa enumeradores de foreach para iterar por los elementos de una colección y realizar las mismas tareas para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="3a52b-103">uses foreach enumerators to iterate over the items in a collection and perform the same tasks for each element.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="3a52b-104">incluye varios enumeradores de foreach que admiten las colecciones de uso más frecuente, como todos los archivos de una carpeta, todas las tablas de una base de datos o todos los elementos de una lista almacenados en una variable de paquete.</span><span class="sxs-lookup"><span data-stu-id="3a52b-104">includes a variety of foreach enumerators that support the most commonly used collections, such as all the files in a folder, all the tables in a database, or all the elements of a list stored in a package variable.</span></span> <span data-ttu-id="3a52b-105">Si las colecciones y enumeradores foreach que se proporcionan no cumplen completamente sus requisitos, puede crear un enumerador foreach personalizado.</span><span class="sxs-lookup"><span data-stu-id="3a52b-105">If the foreach enumerators and collections that are provided do not entirely meet your requirements, you can create a custom foreach enumerator.</span></span>  
  
 <span data-ttu-id="3a52b-106">Para crear un enumerador foreach personalizado, debe crear una clase que herede de la clase base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, aplicar el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> a la nueva clase e invalidar los métodos y propiedades importantes de la clase base, incluido el método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="3a52b-106">To create a custom foreach enumerator, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a52b-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3a52b-107">In This Section</span></span>  
 <span data-ttu-id="3a52b-108">En esta sección se describe cómo crear, configurar y codificar un enumerador foreach personalizado y su interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="3a52b-108">This section describes how to create, configure, and code a custom foreach enumerator and its custom user interface.</span></span>  
  
 [<span data-ttu-id="3a52b-109">Crear un enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="3a52b-109">Creating a Custom Foreach Enumerator</span></span>](creating-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="3a52b-110">Describe cómo crear las clases para un proyecto de enumerador foreach personalizado.</span><span class="sxs-lookup"><span data-stu-id="3a52b-110">Describes how to create the classes for a custom foreach enumerator project.</span></span>  
  
 [<span data-ttu-id="3a52b-111">Codificar un enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="3a52b-111">Coding a Custom Foreach Enumerator</span></span>](coding-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="3a52b-112">Describe cómo implementar un enumerador foreach personalizado invalidando los métodos y propiedades de la clase base.</span><span class="sxs-lookup"><span data-stu-id="3a52b-112">Describes how to implement a custom foreach enumerator by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="3a52b-113">Desarrollar una interfaz de usuario para un enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="3a52b-113">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="3a52b-114">Describe cómo implementar la clase de interfaz de usuario y el formulario que se utilizan para configurar el enumerador foreach personalizado.</span><span class="sxs-lookup"><span data-stu-id="3a52b-114">Describes how to implement the user interface class and the form that is used to configure the custom foreach enumerator.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="3a52b-115">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3a52b-115">Related Topics</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="3a52b-116">Información común a todos los objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="3a52b-116">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="3a52b-117">Para obtener información común a todos los tipos de objetos personalizados que puede crear en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a52b-117">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="3a52b-118">Desarrollar objetos personalizados para Integration Services</span><span class="sxs-lookup"><span data-stu-id="3a52b-118">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="3a52b-119">Describe los pasos básicos para implementar todos los tipos de objetos personalizados para [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a52b-119">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="3a52b-120">Conservar objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="3a52b-120">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="3a52b-121">Describe la persistencia personalizada y explica cuándo es necesaria.</span><span class="sxs-lookup"><span data-stu-id="3a52b-121">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="3a52b-122">Generar, implementar y depurar objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="3a52b-122">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="3a52b-123">Describe las técnicas para generar, firmar, implementar y depurar objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="3a52b-123">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="3a52b-124">Información sobre otros objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="3a52b-124">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="3a52b-125">Para obtener información sobre los demás tipos de objetos personalizados que puede crear en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a52b-125">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="3a52b-126">Desarrollar una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="3a52b-126">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="3a52b-127">Describe cómo programar las tareas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="3a52b-127">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="3a52b-128">Desarrollar un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="3a52b-128">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="3a52b-129">Describe cómo programar los administradores de conexiones personalizados.</span><span class="sxs-lookup"><span data-stu-id="3a52b-129">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="3a52b-130">Desarrollar un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="3a52b-130">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="3a52b-131">Describe cómo programar los proveedores de registro personalizados.</span><span class="sxs-lookup"><span data-stu-id="3a52b-131">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="3a52b-132">Desarrollar un componente de flujo de datos personalizado</span><span class="sxs-lookup"><span data-stu-id="3a52b-132">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="3a52b-133">Describe cómo programar orígenes, transformaciones y destinos personalizados del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="3a52b-133">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="3a52b-134">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="3a52b-134">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="3a52b-135">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="3a52b-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="3a52b-136">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="3a52b-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="3a52b-137">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="3a52b-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
