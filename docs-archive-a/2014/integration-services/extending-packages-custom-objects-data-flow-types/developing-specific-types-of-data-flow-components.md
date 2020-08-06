---
title: Desarrollar tipos específicos de componentes de flujo de datos | Microsoft Docs
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
- data flow task [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 348e219a-b8ff-425e-b9c6-811880101c54
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e168c866e03bfa5fd1f32127e4bfd6e58a2e8d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748197"
---
# <a name="developing-specific-types-of-data-flow-components"></a><span data-ttu-id="0be78-102">Desarrollar tipos específicos de componentes de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="0be78-102">Developing Specific Types of Data Flow Components</span></span>
  <span data-ttu-id="0be78-103">En esta sección se tratan las características específicas del desarrollo de componentes de origen, componentes de transformación con salidas sincrónicas, componentes de transformación con salidas asincrónicas y componentes de destino.</span><span class="sxs-lookup"><span data-stu-id="0be78-103">This section covers the specifics of developing source components, transformation components with synchronous outputs, transformation components with asynchronous outputs, and destination components.</span></span>  
  
 <span data-ttu-id="0be78-104">Para obtener información sobre el desarrollo de componentes en general, vea [Desarrollar un componente de flujo de datos personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="0be78-104">For information about component development in general, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0be78-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0be78-105">In This Section</span></span>  
 [<span data-ttu-id="0be78-106">Desarrollar un componente de origen personalizado</span><span class="sxs-lookup"><span data-stu-id="0be78-106">Developing a Custom Source Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)  
 <span data-ttu-id="0be78-107">Contiene información sobre el desarrollo de un componente que tiene acceso a datos de un origen de datos externo y los proporciona a componentes de nivel inferior en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="0be78-107">Contains information on developing a component that accesses data from an external data source and supplies it to downstream components in the data flow.</span></span>  
  
 [<span data-ttu-id="0be78-108">Desarrollar un componente de transformación personalizado con salidas sincrónicas</span><span class="sxs-lookup"><span data-stu-id="0be78-108">Developing a Custom Transformation Component with Synchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md)  
 <span data-ttu-id="0be78-109">Contiene información sobre el desarrollo de un componente de transformación cuyas salidas son sincrónicas a sus entradas.</span><span class="sxs-lookup"><span data-stu-id="0be78-109">Contains information on developing a transformation component whose outputs are synchronous to its inputs.</span></span> <span data-ttu-id="0be78-110">Estos componentes no agregan datos al flujo de datos, sino que los procesan a medida que se pasa por ellos.</span><span class="sxs-lookup"><span data-stu-id="0be78-110">These components do not add data to the data flow, but process data as it passes through.</span></span>  
  
 [<span data-ttu-id="0be78-111">Desarrollar un componente de transformación personalizado con salidas asincrónicas</span><span class="sxs-lookup"><span data-stu-id="0be78-111">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md)  
 <span data-ttu-id="0be78-112">Contiene información sobre el desarrollo de un componente de transformación cuyas salidas no son sincrónicas a sus entradas.</span><span class="sxs-lookup"><span data-stu-id="0be78-112">Contains information on developing a transformation component whose outputs are not synchronous to its inputs.</span></span> <span data-ttu-id="0be78-113">Estos componentes reciben datos de componentes de nivel superior, pero también agregan datos al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="0be78-113">These components receive data from upstream components, but also add data to the dataflow.</span></span>  
  
 [<span data-ttu-id="0be78-114">Desarrollar un componente de destino personalizado</span><span class="sxs-lookup"><span data-stu-id="0be78-114">Developing a Custom Destination Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)  
 <span data-ttu-id="0be78-115">Contiene información sobre el desarrollo de un componente que recibe filas de componentes de nivel superior en el flujo de datos y los escribe en un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="0be78-115">Contains information on developing a component that receives rows from upstream components in the data flow and writes them to an external data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0be78-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="0be78-116">Reference</span></span>  
 <xref:Microsoft.SqlServer.Dts.Pipeline>  
 <span data-ttu-id="0be78-117">Contiene las clases e interfaces que se utilizan para crear componentes de flujo de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="0be78-117">Contains the classes and interfaces used to create custom data flow components.</span></span>  
  
 <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>  
 <span data-ttu-id="0be78-118">Contiene las clases e interfaces no administradas de la tarea de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="0be78-118">Contains the unmanaged classes and interfaces of the data flow task.</span></span> <span data-ttu-id="0be78-119">El desarrollador de software utiliza éstas y el espacio de nombres <xref:Microsoft.SqlServer.Dts.Pipeline> administrado al generar un flujo de datos mediante programación o crear componentes de flujo de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="0be78-119">The developer uses these, and the managed <xref:Microsoft.SqlServer.Dts.Pipeline> namespace, when building a data flow programmatically or creating custom data flow components.</span></span>  
  
<span data-ttu-id="0be78-120">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="0be78-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="0be78-121">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="0be78-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="0be78-122">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="0be78-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="0be78-123">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="0be78-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be78-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0be78-124">See Also</span></span>  
 <span data-ttu-id="0be78-125">[Comparar soluciones de scripting y objetos personalizados](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="0be78-125">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="0be78-126">Desarrollar tipos específicos de los componentes de script</span><span class="sxs-lookup"><span data-stu-id="0be78-126">Developing Specific Types of Script Components</span></span>](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md)  
  
  
