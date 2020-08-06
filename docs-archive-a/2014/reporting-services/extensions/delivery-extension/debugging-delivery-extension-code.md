---
title: Depurar el código de extensión de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], debugging
- debugging delivery extensions [Reporting Services]
- troubleshooting [Reporting Services], delivery extensions
ms.assetid: a7d959da-5005-4a50-aca7-2cef36aa9947
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb80ac97f5c0e346b208784f1fa5b857ff93ef57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750461"
---
# <a name="debugging-delivery-extension-code"></a><span data-ttu-id="ead9d-102">Depurar el código de extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="ead9d-102">Debugging Delivery Extension Code</span></span>
  <span data-ttu-id="ead9d-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proporciona varias herramientas de depuración que pueden ayudarle a analizar el código de extensión de entrega y localizar errores en él.</span><span class="sxs-lookup"><span data-stu-id="ead9d-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your delivery extension code and locate errors in it.</span></span> <span data-ttu-id="ead9d-104">La herramienta más conveniente dependerá de lo que intente llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="ead9d-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="ead9d-105">En este ejemplo se usa [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ead9d-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-delivery-extension-code"></a><span data-ttu-id="ead9d-106">Para depurar el código de extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="ead9d-106">To debug your delivery extension code</span></span>  
  
1.  <span data-ttu-id="ead9d-107">Inicie [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] y abra el proyecto de extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="ead9d-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] and open your delivery extension project.</span></span>  
  
2.  <span data-ttu-id="ead9d-108">Genere el proyecto e implemente el ensamblado de extensión de entrega y el archivo .pdb acompañante en el servidor de informes y el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="ead9d-108">Build the project and deploy your delivery extension assembly and the accompanying .pdb file to the report server and Report Manager.</span></span> <span data-ttu-id="ead9d-109">Para más información sobre cómo implementar extensiones, vea [Implementar una extensión de entrega](deploying-a-delivery-extension.md).</span><span class="sxs-lookup"><span data-stu-id="ead9d-109">For more information about deployment, see [Deploying a Delivery Extension](deploying-a-delivery-extension.md).</span></span>  
  
3.  <span data-ttu-id="ead9d-110">Si ha escrito una interfaz de usuario de suscripción para extender el Administrador de informes, ha abierto Internet Explorer y ha navegado al Administrador de informes mientras dejaba abierto el código de extensión de entrega en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ead9d-110">If you have written a subscription user interface to extend Report Manager, open Internet Explorer and navigate to Report Manager while leaving your delivery extension code open in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="ead9d-111">Si no tiene implementada una interfaz de usuario de suscripción para el Administrador de informes, simplemente abra la aplicación cliente desde la que llama a la extensión de entrega utilizando la API SOAP.</span><span class="sxs-lookup"><span data-stu-id="ead9d-111">If you do not have a subscription user interface deployed for Report Manager, simply open the client application from which you call your delivery extension using the SOAP API.</span></span>  
  
4.  <span data-ttu-id="ead9d-112">Navegue a [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] y al proyecto de extensión de entrega, y establezca algunos puntos de interrupción en el código.</span><span class="sxs-lookup"><span data-stu-id="ead9d-112">Navigate to [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] and your delivery extension project, and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="ead9d-113">Con el proyecto de extensión de entrega aún en la ventana activa, haga clic en **Asociar al proceso** en el menú **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="ead9d-113">With the delivery extension project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="ead9d-114">Se abre el cuadro de diálogo **Asociar al proceso**.</span><span class="sxs-lookup"><span data-stu-id="ead9d-114">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="ead9d-115">En la lista de procesos, seleccione el proceso aspnet_wp.exe (o w3wp.exe, si la aplicación se implementa en IIS 6.0) y haga clic en **Asociar**.</span><span class="sxs-lookup"><span data-stu-id="ead9d-115">From the list of processes, select the aspnet_wp.exe process (or w3wp.exe if your application is deployed on IIS 6.0), and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="ead9d-116">Defina una nueva suscripción mediante su extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="ead9d-116">Define a new subscription using your delivery extension.</span></span> <span data-ttu-id="ead9d-117">Probablemente utilizará el Administrador de informes o la API SOAP.</span><span class="sxs-lookup"><span data-stu-id="ead9d-117">You will most likely use Report Manager or the SOAP API.</span></span> <span data-ttu-id="ead9d-118">De esta forma se debería invocar el depurador y ejecutar el código correspondiente a sus puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="ead9d-118">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="ead9d-119">Recorra el código con la tecla **F11**.</span><span class="sxs-lookup"><span data-stu-id="ead9d-119">Step through your code using the **F11** key.</span></span> <span data-ttu-id="ead9d-120">Para obtener más información sobre cómo utilizar [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para la depuración, vea la documentación de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ead9d-120">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ead9d-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ead9d-121">See Also</span></span>  
 <span data-ttu-id="ead9d-122">[Implementar una extensión de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="ead9d-122">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="ead9d-123">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ead9d-123">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
