---
title: Desarrollar tipos específicos de los componentes de script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: dfbbe959-6b4e-4b47-b9dd-bcc31929482d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 114c9ddca90ea02a8e1847444b28b9d5876650a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673770"
---
# <a name="developing-specific-types-of-script-components"></a><span data-ttu-id="78a2c-102">Desarrollar tipos específicos de los componentes de script</span><span class="sxs-lookup"><span data-stu-id="78a2c-102">Developing Specific Types of Script Components</span></span>
  <span data-ttu-id="78a2c-103">El componente de script es una herramienta configurable que puede utilizar en el flujo de los datos de un paquete para llenar casi cualquier requisito no cumplido por los orígenes, transformaciones y destinos que se incluyen con [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78a2c-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="78a2c-104">Esta sección contiene ejemplos de código de componente de script que muestran las cuatro opciones para configurar el componente de script:</span><span class="sxs-lookup"><span data-stu-id="78a2c-104">This section contains Script component code samples that demonstrate the four options for configuring the Script component:</span></span>  
  
-   <span data-ttu-id="78a2c-105">Como un origen.</span><span class="sxs-lookup"><span data-stu-id="78a2c-105">As a source.</span></span>  
  
-   <span data-ttu-id="78a2c-106">Como una transformación con salidas sincrónicas.</span><span class="sxs-lookup"><span data-stu-id="78a2c-106">As a transformation with synchronous outputs.</span></span>  
  
-   <span data-ttu-id="78a2c-107">Como una transformación con salidas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="78a2c-107">As a transformation with asynchronous outputs.</span></span>  
  
-   <span data-ttu-id="78a2c-108">Como un destino.</span><span class="sxs-lookup"><span data-stu-id="78a2c-108">As a destination.</span></span>  
  
 <span data-ttu-id="78a2c-109">Para obtener ejemplos adicionales del componente de Script, consulte [Ejemplos de componente de script adicionales](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="78a2c-109">For additional examples of the Script component, see [Additional Script Component Examples](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78a2c-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="78a2c-110">In This Section</span></span>  
 [<span data-ttu-id="78a2c-111">Crear un origen con el componente de script</span><span class="sxs-lookup"><span data-stu-id="78a2c-111">Creating a Source with the Script Component</span></span>](creating-a-source-with-the-script-component.md)  
 <span data-ttu-id="78a2c-112">Explica y muestra cómo crear un origen de flujo de datos mediante el componente de script.</span><span class="sxs-lookup"><span data-stu-id="78a2c-112">Explains and demonstrates how to create a data flow source by using the Script component.</span></span>  
  
 [<span data-ttu-id="78a2c-113">Crear una transformación sincrónica con el componente de script</span><span class="sxs-lookup"><span data-stu-id="78a2c-113">Creating a Synchronous Transformation with the Script Component</span></span>](creating-a-synchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="78a2c-114">Explica y muestra cómo crear una transformación de flujo de datos con salidas sincrónicas mediante el componente de script.</span><span class="sxs-lookup"><span data-stu-id="78a2c-114">Explains and demonstrates how to create a data flow transformation with synchronous outputs by using the Script component.</span></span> <span data-ttu-id="78a2c-115">Este tipo de transformación modifica filas de datos en su lugar cuando pasan a través del componente.</span><span class="sxs-lookup"><span data-stu-id="78a2c-115">This kind of transformation modifies rows of data in place as they pass through the component.</span></span>  
  
 [<span data-ttu-id="78a2c-116">Crear una transformación asincrónica con el componente de script</span><span class="sxs-lookup"><span data-stu-id="78a2c-116">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="78a2c-117">Explica y muestra cómo crear una transformación de flujo de datos con salidas asincrónicas mediante el componente de script.</span><span class="sxs-lookup"><span data-stu-id="78a2c-117">Explains and demonstrates how to create a data flow transformation with asynchronous outputs by using the Script component.</span></span> <span data-ttu-id="78a2c-118">Este tipo de transformación tiene que leer todas las filas de datos antes de poder agregar más información, como agregados calculados, a los datos que pasan a través del componente.</span><span class="sxs-lookup"><span data-stu-id="78a2c-118">This kind of transformation has to read all rows of data before it can add more information, such as calculated aggregates, to the data that passes through the component.</span></span>  
  
 [<span data-ttu-id="78a2c-119">Crear un destino con el componente de script</span><span class="sxs-lookup"><span data-stu-id="78a2c-119">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
 <span data-ttu-id="78a2c-120">Explica y muestra cómo crear un destino de flujo de datos mediante el componente de script.</span><span class="sxs-lookup"><span data-stu-id="78a2c-120">Explains and demonstrates how to create a data flow destination by using the Script component.</span></span>  
  
<span data-ttu-id="78a2c-121">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="78a2c-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="78a2c-122">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="78a2c-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="78a2c-123">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="78a2c-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="78a2c-124">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="78a2c-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a2c-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78a2c-125">See Also</span></span>  
 <span data-ttu-id="78a2c-126">[Comparar soluciones de scripting y objetos personalizados](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="78a2c-126">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="78a2c-127">Desarrollar tipos específicos de componentes de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="78a2c-127">Developing Specific Types of Data Flow Components</span></span>](../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md)  
  
  
