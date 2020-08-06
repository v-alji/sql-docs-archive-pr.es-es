---
title: Registrar en el componente de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], logging
ms.assetid: 17c19787-379e-43fe-9107-e36e17ecda53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c29dfffee6cacb39272aef07caa5539555cdd4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674202"
---
# <a name="logging-in-the-script-component"></a><span data-ttu-id="3e09d-102">Registrar en el componente de script</span><span class="sxs-lookup"><span data-stu-id="3e09d-102">Logging in the Script Component</span></span>
  <span data-ttu-id="3e09d-103">El registro en los paquetes de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] permite guardar información detallada sobre el progreso, los resultados y los problemas de ejecución al registrar eventos predefinidos o mensajes definidos por el usuario para su análisis posterior.</span><span class="sxs-lookup"><span data-stu-id="3e09d-103">Logging in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages lets you save detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="3e09d-104">El componente de script puede utilizar el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> de la clase `ScriptMain` para registrar datos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3e09d-104">The Script component can use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class to log user-defined data.</span></span> <span data-ttu-id="3e09d-105">Si está habilitado el registro y se ha seleccionado el evento **ScriptComponentLogEntry** para su registro en la pestaña **Detalles** del cuadro de diálogo **Configurar registros de SSIS**, una sola llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> almacena la información del evento en todos los proveedores de registro configurados para la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="3e09d-105">If logging is enabled, and the **ScriptComponentLogEntry** event is selected for logging on the **Details** tab of the **Configure SSIS Logs** dialog box, a single call to the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method stores the event information in all the log providers that have been configured for the data flow task.</span></span>  
  
 <span data-ttu-id="3e09d-106">A continuación se muestra un ejemplo sencillo de registro:</span><span class="sxs-lookup"><span data-stu-id="3e09d-106">Here is a simple example of logging:</span></span>  
  
 `Dim bt(0) As Byte`  
  
 `Me.Log("Test Log Event", _`  
  
 `0, _`  
  
 `bt)`  
  
> [!NOTE]  
>  <span data-ttu-id="3e09d-107">Si bien puede realizar registros directamente desde el componente de script, puede que le interese implementar eventos en lugar de registrarlos.</span><span class="sxs-lookup"><span data-stu-id="3e09d-107">Although you can perform logging directly from your Script component, you may want to consider implementing events rather than logging.</span></span> <span data-ttu-id="3e09d-108">Al utilizar eventos, no solamente puede habilitar el registro de mensajes de evento, sino que también puede responder al evento con controladores de eventos predeterminados o definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3e09d-108">When using events, not only can you enable the logging of event messages, but you can respond to the event with default or user-defined event handlers.</span></span>  
  
 <span data-ttu-id="3e09d-109">Para obtener más información sobre el registro, vea [Registro de Integration Services &#40;SSIS&#41;](../../performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="3e09d-109">For more information about logging, see [Integration Services &#40;SSIS&#41; Logging](../../performance/integration-services-ssis-logging.md).</span></span>  
  
<span data-ttu-id="3e09d-110">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="3e09d-110">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="3e09d-111">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="3e09d-111">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="3e09d-112">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="3e09d-112">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="3e09d-113">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="3e09d-113">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e09d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e09d-114">See Also</span></span>  
 [<span data-ttu-id="3e09d-115">Registro de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3e09d-115">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
