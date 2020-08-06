---
title: Desarrollar un proveedor de registro personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- SSIS packages, log providers
- custom log providers [Integration Services]
- SQL Server Integration Services packages, log providers
- log providers [Integration Services]
- packages [Integration Services], logs
- Integration Services packages, log providers
ms.assetid: 3f715b95-7074-4f5c-8ae2-246998052e78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 88d4f70fa9d50628b831b56f9fa22100648fce51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663633"
---
# <a name="developing-a-custom-log-provider"></a><span data-ttu-id="ed6ee-102">Desarrollar un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="ed6ee-102">Developing a Custom Log Provider</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="ed6ee-103">incluye completas capacidades de registro que permiten capturar eventos que se producen durante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-103">has extensive logging capabilities that make it possible to capture events that occur during package execution.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="ed6ee-104">incluye varios proveedores de registro que permiten crear registros y almacenarlos en formatos como XML, texto, base de datos o en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-104">includes a variety of log providers that enable logs to be created and stored in formats such as XML, text, database, or in the Windows event log.</span></span> <span data-ttu-id="ed6ee-105">Si los proveedores de registro y los formatos de salida que se proporcionan no cumplen completamente sus requisitos, puede crear un proveedor de registro personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-105">If the log providers and the output formats that are provided do not entirely meet your requirements, you can create a custom log provider.</span></span>

 <span data-ttu-id="ed6ee-106">Para crear un proveedor de registro personalizado, debe crear una clase que herede de la clase base <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>, aplicar el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> a la nueva clase e invalidar los métodos y propiedades importantes de la clase base, incluidos la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> y el método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-106">To create a custom log provider, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ed6ee-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ed6ee-107">In This Section</span></span>
 <span data-ttu-id="ed6ee-108">En esta sección se describe cómo crear, configurar y codificar un proveedor de registro personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-108">This section describes how to create, configure, and code a custom log provider.</span></span>

 <span data-ttu-id="ed6ee-109">[Crear un proveedor de registro personalizado](creating-a-custom-log-provider.md) Describe cómo crear las clases para un proyecto de proveedor de registro personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-109">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) Describes how to create the classes for a custom log provider project.</span></span>

 <span data-ttu-id="ed6ee-110">[Codificar un proveedor de registro personalizado](coding-a-custom-log-provider.md) Describe cómo implementar un proveedor de registro personalizado invalidando los métodos y las propiedades de la clase base.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-110">[Coding a Custom Log Provider](coding-a-custom-log-provider.md) Describes how to implement a custom log provider by overriding the methods and properties of the base class.</span></span>

 <span data-ttu-id="ed6ee-111">[Desarrollar una interfaz de usuario para un proveedor de registro personalizado](developing-a-user-interface-for-a-custom-log-provider.md) Las interfaces de usuario personalizadas para los proveedores de registro personalizados no se admiten en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed6ee-111">[Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md) Custom user interfaces for custom log providers are not supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed6ee-112">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ed6ee-112">Related Topics</span></span>

### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="ed6ee-113">Información común a todos los objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="ed6ee-113">Information Common to all Custom Objects</span></span>
 <span data-ttu-id="ed6ee-114">Para obtener información común a todos los tipos de objetos personalizados que puede crear en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed6ee-114">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="ed6ee-115">[Desarrollar objetos personalizados para Integration Services](../developing-custom-objects-for-integration-services.md) Describe los pasos básicos para implementar todos los tipos de objetos personalizados para [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed6ee-115">[Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="ed6ee-116">[Conservar objetos personalizados](../persisting-custom-objects.md) Describe la persistencia personalizada y explica cuándo es necesario.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-116">[Persisting Custom Objects](../persisting-custom-objects.md) Describes custom persistence and explains when it is necessary.</span></span>

 <span data-ttu-id="ed6ee-117">[Compilar, implementar y depurar objetos personalizados](../building-deploying-and-debugging-custom-objects.md) Describe las técnicas para compilar, firmar, implementar y depurar objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-117">[Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md) Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>

### <a name="information-about-other-custom-objects"></a><span data-ttu-id="ed6ee-118">Información sobre otros objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="ed6ee-118">Information about Other Custom Objects</span></span>
 <span data-ttu-id="ed6ee-119">Para obtener información sobre los demás tipos de objetos personalizados que puede crear en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed6ee-119">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="ed6ee-120">[Desarrollar una tarea personalizada](../task/developing-a-custom-task.md) Describe cómo programar tareas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-120">[Developing a Custom Task](../task/developing-a-custom-task.md) Discusses how to program custom tasks.</span></span>

 <span data-ttu-id="ed6ee-121">[Desarrollar un administrador de conexiones personalizado](../connection-manager/developing-a-custom-connection-manager.md) Describe cómo programar administradores de conexiones personalizados.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-121">[Developing a Custom Connection Manager](../connection-manager/developing-a-custom-connection-manager.md) Discusses how to program custom connection managers.</span></span>

 <span data-ttu-id="ed6ee-122">[Desarrollar un enumerador Foreach personalizado](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Describe cómo programar los enumeradores personalizados.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-122">[Developing a Custom ForEach Enumerator](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Discusses how to program custom enumerators.</span></span>

 <span data-ttu-id="ed6ee-123">[Desarrollar un componente de flujo de datos personalizado](../data-flow/developing-a-custom-data-flow-component.md) Describe cómo programar orígenes, transformaciones y destinos de flujo de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-123">[Developing a Custom Data Flow Component](../data-flow/developing-a-custom-data-flow-component.md) Discusses how to program custom data flow sources, transformations, and destinations.</span></span>

<span data-ttu-id="ed6ee-124">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ed6ee-124">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ed6ee-125">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="ed6ee-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ed6ee-126">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="ed6ee-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ed6ee-127">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="ed6ee-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>


