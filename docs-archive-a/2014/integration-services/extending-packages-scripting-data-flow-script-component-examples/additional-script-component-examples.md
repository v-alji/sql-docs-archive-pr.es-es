---
title: Ejemplos de componente de script adicionales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: 849dd38a-abb5-4702-a413-882aae3980a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 897ca075674f5c3dbaf355390fe8346580bf638a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674217"
---
# <a name="additional-script-component-examples"></a><span data-ttu-id="1f5b0-102">Ejemplos de componente de script adicionales</span><span class="sxs-lookup"><span data-stu-id="1f5b0-102">Additional Script Component Examples</span></span>
  <span data-ttu-id="1f5b0-103">El componente de script es una herramienta configurable que puede utilizar en el flujo de los datos de un paquete para llenar casi cualquier requisito no cumplido por los orígenes, transformaciones y destinos que se incluyen con [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f5b0-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="1f5b0-104">Esta sección contiene ejemplos de código del componente de script que muestran los distintos tipos de funcionalidades disponibles.</span><span class="sxs-lookup"><span data-stu-id="1f5b0-104">This section contains Script component code samples that demonstrate the various types of functionality that are available.</span></span>  
  
 <span data-ttu-id="1f5b0-105">Para obtener ejemplos que demuestran cómo configurar el componente de script como origen, transformación o destino básico, vea [Desarrollar tipos específicos de los componentes de script](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span><span class="sxs-lookup"><span data-stu-id="1f5b0-105">For samples that demonstrate how to configure the Script component as a basic source, transformation, or destination, see [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f5b0-106">Si desea crear componentes que pueda reutilizar más fácilmente en varias tareas de flujo de datos y varios paquetes, considere utilizar el código de estos ejemplos de componente de script como punto de inicio para los componentes de flujo de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="1f5b0-106">If you want to create components that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in these Script component samples as the starting point for custom data flow components.</span></span> <span data-ttu-id="1f5b0-107">Para obtener más información, vea [Desarrollar un componente de flujo de datos personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="1f5b0-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f5b0-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1f5b0-108">In This Section</span></span>  
 [<span data-ttu-id="1f5b0-109">Simular una salida de error para el componente de script</span><span class="sxs-lookup"><span data-stu-id="1f5b0-109">Simulating an Error Output for the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md)  
 <span data-ttu-id="1f5b0-110">El componente de script no admite una salida de error estándar, pero puede simular esta última con muy poca configuración y codificación adicionales.</span><span class="sxs-lookup"><span data-stu-id="1f5b0-110">The Script component does not support a standard error output, but you can simulate a standard error output with very little additional configuration and coding.</span></span>  
  
 [<span data-ttu-id="1f5b0-111">Mejorar una salida de errores con el componente de script</span><span class="sxs-lookup"><span data-stu-id="1f5b0-111">Enhancing an Error Output with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/enhancing-an-error-output-with-the-script-component.md)  
 <span data-ttu-id="1f5b0-112">Explica y muestra cómo agregar información adicional a una salida de error estándar mediante el componente de script.</span><span class="sxs-lookup"><span data-stu-id="1f5b0-112">Explains and demonstrates how to add additional information to a standard error output by using the Script component.</span></span>  
  
 [<span data-ttu-id="1f5b0-113">Crear un destino ODBC con el componente de script</span><span class="sxs-lookup"><span data-stu-id="1f5b0-113">Creating an ODBC Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/creating-an-odbc-destination-with-the-script-component.md)  
 <span data-ttu-id="1f5b0-114">Explica y muestra cómo crear un destino de flujo de datos de ODBC mediante el componente de script.</span><span class="sxs-lookup"><span data-stu-id="1f5b0-114">Explains and demonstrates how to create an ODBC data flow destination by using the Script component.</span></span>  
  
 [<span data-ttu-id="1f5b0-115">Analizar formatos de archivo de texto no estándar con el componente de script</span><span class="sxs-lookup"><span data-stu-id="1f5b0-115">Parsing Non-Standard Text File Formats with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/parsing-non-standard-text-file-formats-with-the-script-component.md)  
 <span data-ttu-id="1f5b0-116">Explica y muestra cómo analizar dos formatos de archivo de texto no estándar distintos en las tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="1f5b0-116">Explains and demonstrates how to parse two different non-standard text file formats into destination tables.</span></span>  
  
<span data-ttu-id="1f5b0-117">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="1f5b0-117">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1f5b0-118">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="1f5b0-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1f5b0-119">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="1f5b0-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1f5b0-120">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="1f5b0-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
