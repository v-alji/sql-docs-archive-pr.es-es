---
title: Provocar eventos en el componente de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], raising events
ms.assetid: bb389073-e1d0-4794-8d29-c8b293b6a5e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 78eb44239f4e58e43bdd65c41d5fdeb58d053a6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674200"
---
# <a name="raising-events-in-the-script-component"></a><span data-ttu-id="abcc1-102">Provocar eventos en el componente de script</span><span class="sxs-lookup"><span data-stu-id="abcc1-102">Raising Events in the Script Component</span></span>
  <span data-ttu-id="abcc1-103">Los eventos proporcionan una manera de notificar errores, advertencias y otra información, como el progreso o el estado de una tarea, al paquete contenedor.</span><span class="sxs-lookup"><span data-stu-id="abcc1-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="abcc1-104">El paquete proporciona controladores de eventos para administrar las notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="abcc1-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="abcc1-105">El componente de script puede provocar eventos mediante una llamada a los métodos en la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> de la clase `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="abcc1-105">The Script component can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class.</span></span> <span data-ttu-id="abcc1-106">Para obtener más información sobre la manera en que los paquetes [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] controlan los eventos, vea [Controladores de eventos de Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="abcc1-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="abcc1-107">Los eventos se pueden registrar en cualquier proveedor de registro habilitado en el paquete.</span><span class="sxs-lookup"><span data-stu-id="abcc1-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="abcc1-108">Los proveedores de registro almacenan información sobre los eventos en un almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="abcc1-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="abcc1-109">El componente de script también puede usar el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> para registrar información en un proveedor de registro sin provocar un evento.</span><span class="sxs-lookup"><span data-stu-id="abcc1-109">The Script component can also use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="abcc1-110">Para obtener más información acerca de cómo usar el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A>, vea la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="abcc1-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method, see the following section.</span></span>  
  
 <span data-ttu-id="abcc1-111">Para provocar un evento, la tarea Script llama a uno de los siguientes métodos de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> expuestos por la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A>:</span><span class="sxs-lookup"><span data-stu-id="abcc1-111">To raise an event, the Script task calls one of the following methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface exposed by the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property:</span></span>  
  
|<span data-ttu-id="abcc1-112">Evento</span><span class="sxs-lookup"><span data-stu-id="abcc1-112">Event</span></span>|<span data-ttu-id="abcc1-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="abcc1-113">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>|<span data-ttu-id="abcc1-114">Provoca un evento personalizado definido por el usuario en el paquete.</span><span class="sxs-lookup"><span data-stu-id="abcc1-114">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A>|<span data-ttu-id="abcc1-115">Informa al paquete de una condición de error.</span><span class="sxs-lookup"><span data-stu-id="abcc1-115">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A>|<span data-ttu-id="abcc1-116">Proporciona información al usuario.</span><span class="sxs-lookup"><span data-stu-id="abcc1-116">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireProgress%2A>|<span data-ttu-id="abcc1-117">Informa al paquete del progreso del componente.</span><span class="sxs-lookup"><span data-stu-id="abcc1-117">Informs the package of the progress of the component.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A>|<span data-ttu-id="abcc1-118">Informa al paquete de que el componente está en un estado que garantiza la notificación del usuario, pero no es una condición de error.</span><span class="sxs-lookup"><span data-stu-id="abcc1-118">Informs the package that the component is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
 <span data-ttu-id="abcc1-119">Aquí se proporciona un ejemplo simple de cómo provocar un evento Error:</span><span class="sxs-lookup"><span data-stu-id="abcc1-119">Here is a simple example of raising an Error event:</span></span>  
  
 `Dim myMetadata as IDTSComponentMetaData100`  
  
 `myMetaData = Me.ComponentMetaData`  
  
 `myMetaData.FireError(...)`  
  
<span data-ttu-id="abcc1-120">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="abcc1-120">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="abcc1-121">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="abcc1-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="abcc1-122">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="abcc1-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="abcc1-123">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="abcc1-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abcc1-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="abcc1-124">See Also</span></span>  
 <span data-ttu-id="abcc1-125">[Controladores de eventos de Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="abcc1-125">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="abcc1-126">Agregar un controlador de eventos a un paquete</span><span class="sxs-lookup"><span data-stu-id="abcc1-126">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
