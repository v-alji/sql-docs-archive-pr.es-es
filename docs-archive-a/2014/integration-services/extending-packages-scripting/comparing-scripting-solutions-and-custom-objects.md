---
title: Comparar soluciones de scripting y objetos personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- managed tasks [Integration Services]
- Script task [Integration Services], vs. custom managed tasks
- SSIS Script task, vs. custom managed tasks
- custom tasks [Integration Services], scripts
ms.assetid: c0aea822-a21e-44e1-a3d3-8777bd0a1c34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: acf6faf9cdd78e951b8298c4e3b144d3444fb1ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663625"
---
# <a name="comparing-scripting-solutions-and-custom-objects"></a><span data-ttu-id="c9bbd-102">Comparar soluciones de scripting y objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="c9bbd-102">Comparing Scripting Solutions and Custom Objects</span></span>
  <span data-ttu-id="c9bbd-103">Una tarea Script o el componente de script de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] puede implementar casi la misma funcionalidad que implementa una tarea administrada personalizada o componente de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="c9bbd-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task or Script component can implement much of the same functionality that is possible in a custom managed task or data flow component.</span></span> <span data-ttu-id="c9bbd-104">A continuación, se proporcionan algunas consideraciones que le servirán de ayuda para elegir el tipo de tarea adecuado a sus necesidades:</span><span class="sxs-lookup"><span data-stu-id="c9bbd-104">Here are some considerations to help you choose the appropriate type of task for your needs:</span></span>  
  
-   <span data-ttu-id="c9bbd-105">Si la configuración o la funcionalidad es específica de un paquete individual, debe usar la tarea Script o el componente de script en lugar de desarrollar un objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="c9bbd-105">If the configuration or functionality is specific to an individual package, you should use the Script task or the Script component instead of a developing a custom object.</span></span>  
  
-   <span data-ttu-id="c9bbd-106">Si la funcionalidad es genérica, y se podría usar en el futuro para otros paquetes y a través de otros programadores, debería crear un objeto personalizado en lugar de utilizar una solución de scripting.</span><span class="sxs-lookup"><span data-stu-id="c9bbd-106">If the functionality is generic, and might be used in the future for other packages and by other developers, you should create a custom object instead of using a scripting solution.</span></span> <span data-ttu-id="c9bbd-107">Puede usar un objeto personalizado en cualquier paquete, mientras que un script únicamente se puede utilizar en el paquete para el que se creó.</span><span class="sxs-lookup"><span data-stu-id="c9bbd-107">You can use a custom object in any package, whereas a script can be used only in the package for which it was created.</span></span>  
  
-   <span data-ttu-id="c9bbd-108">Si el código se reutiliza dentro del mismo paquete, debería considerar la creación un objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="c9bbd-108">If the code will be reused within the same package, you should consider creating a custom object.</span></span> <span data-ttu-id="c9bbd-109">Copiar código de una tarea Script o componente de script a otro lleva a la reducción de mantenimiento que dificulta el mantenimiento y la actualización de varias copias del código.</span><span class="sxs-lookup"><span data-stu-id="c9bbd-109">Copying code from one Script task or component to another leads to reduced maintainability by making it more difficult to maintain and update multiple copies of the code.</span></span>  
  
-   <span data-ttu-id="c9bbd-110">Si la implementación cambia con el tiempo, considere el uso de un objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="c9bbd-110">If the implementation will change over time, consider using a custom object.</span></span> <span data-ttu-id="c9bbd-111">Los objetos personalizados se pueden desarrollar e implementar independientemente del paquete primario, mientras que una actualización de una solución de scripting requiere volver a implementar todo el paquete.</span><span class="sxs-lookup"><span data-stu-id="c9bbd-111">Custom objects can be developed and deployed separately from the parent package, whereas an update made to a scripting solution requires the redeployment of the whole package.</span></span>  
  
<span data-ttu-id="c9bbd-112">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c9bbd-112">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c9bbd-113">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="c9bbd-113">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c9bbd-114">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="c9bbd-114">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c9bbd-115">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="c9bbd-115">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bbd-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9bbd-116">See Also</span></span>  
 [<span data-ttu-id="c9bbd-117">Ampliar paquetes con objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="c9bbd-117">Extending Packages with Custom Objects</span></span>](../extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
  
  
