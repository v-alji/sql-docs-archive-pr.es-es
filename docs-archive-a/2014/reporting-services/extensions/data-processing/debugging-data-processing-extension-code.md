---
title: Depurar el código de extensión de procesamiento de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- debugging data processing extensions [Reporting Services]
- troubleshooting [Reporting Services], data processing extensions
- data processing extensions [Reporting Services], debugging
ms.assetid: e963e205-9ae0-446d-97df-028a1d2727d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bf7490145f91ee8b3cfc2357c34010bed593ed9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671933"
---
# <a name="debugging-data-processing-extension-code"></a><span data-ttu-id="df455-102">Depurar el código de extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="df455-102">Debugging Data Processing Extension Code</span></span>
  <span data-ttu-id="df455-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proporciona varias herramientas de depuración que pueden ayudarle a analizar el código de extensión del procesamiento de datos y localizar errores en él.</span><span class="sxs-lookup"><span data-stu-id="df455-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your data processing extension code and locate errors in it.</span></span> <span data-ttu-id="df455-104">La herramienta más conveniente dependerá de lo que intente llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="df455-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="df455-105">En este ejemplo se usa [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df455-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-data-processing-extension-code"></a><span data-ttu-id="df455-106">Para depurar el código de extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="df455-106">To debug your data processing extension code</span></span>  
  
1.  <span data-ttu-id="df455-107">Inicie [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] y abra el proyecto de extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="df455-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)], and open your data processing extension project.</span></span>  
  
2.  <span data-ttu-id="df455-108">Genere el proyecto e implemente el ensamblado de extensión de procesamiento de datos y el archivo .pdb acompañante en el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="df455-108">Build the project, and deploy your data processing extension assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="df455-109">Para más información sobre la implementación, vea [How to: Deploy a Data Processing Extension to Report Designer](deploying-a-data-processing-extension-to-report-designer.md) (Cómo implementar una extensión de procesamiento de datos en el Diseñador de informes).</span><span class="sxs-lookup"><span data-stu-id="df455-109">For more information about deployment, see [How to: Deploy a Data Processing Extension to Report Designer](deploying-a-data-processing-extension-to-report-designer.md).</span></span>  
  
3.  <span data-ttu-id="df455-110">Abra un nuevo proyecto de informe en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] al tiempo que deja el código de la extensión de procesamiento de datos abierto en una ventana independiente de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df455-110">Open a new Report Project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] while leaving your data processing extension code open in a separate window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="df455-111">Navegue a la ventana de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] que contenga el proyecto de extensión de procesamiento de datos y establezca algunos puntos de interrupción en el código.</span><span class="sxs-lookup"><span data-stu-id="df455-111">Navigate to the window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] that contains your data processing extension project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="df455-112">Con el proyecto de extensión de procesamiento de datos en la ventana del proyecto activa, haga clic en **Asociar al proceso** desde el menú **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="df455-112">With the data processing extension project window still active, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="df455-113">Se abre el cuadro de diálogo **Asociar al proceso**.</span><span class="sxs-lookup"><span data-stu-id="df455-113">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="df455-114">En la lista de procesos, seleccione el proceso devenv.exe que corresponda al proyecto de informe y haga clic en **Asociar**.</span><span class="sxs-lookup"><span data-stu-id="df455-114">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="df455-115">Defina el origen de datos del informe utilizando la pestaña **Datos de informe** del Proyecto de informe.</span><span class="sxs-lookup"><span data-stu-id="df455-115">Define your report data source using the **Report Data** tab of the Report Project.</span></span> <span data-ttu-id="df455-116">Probablemente utilizará el Diseñador de consultas genérico para ejecutar una consulta con el origen de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="df455-116">You will most likely use the generic Query Designer to execute a query against your custom data source.</span></span> <span data-ttu-id="df455-117">De esta forma se debería invocar el depurador y ejecutar el código correspondiente a sus puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="df455-117">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="df455-118">Recorra el código con la tecla F11.</span><span class="sxs-lookup"><span data-stu-id="df455-118">Step through your code using the F11 key.</span></span> <span data-ttu-id="df455-119">Para obtener más información sobre cómo utilizar [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para la depuración, vea la documentación de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df455-119">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df455-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df455-120">See Also</span></span>  
 <span data-ttu-id="df455-121">[Implementación de una extensión de procesamiento de datos](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="df455-121">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="df455-122">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="df455-122">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="df455-123">[Implementar una extensión de procesamiento de datos](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="df455-123">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="df455-124">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="df455-124">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
