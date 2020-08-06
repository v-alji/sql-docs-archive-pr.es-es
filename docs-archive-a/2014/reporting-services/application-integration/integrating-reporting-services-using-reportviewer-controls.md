---
title: Integrar Reporting Services con los controles ReportViewer | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- ReportViewer controls
- integrating reports [Reporting Services]
ms.assetid: 3ba47fb4-73a9-4059-89fd-329adebe94a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 18e28dbf1557bf36106b454738d0c0bfc037f2a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662680"
---
# <a name="integrating-reporting-services-using-the-reportviewer-controls"></a><span data-ttu-id="90e21-102">Integrar Reporting Services con los controles ReportViewer</span><span class="sxs-lookup"><span data-stu-id="90e21-102">Integrating Reporting Services Using the ReportViewer Controls</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="90e21-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)]proporciona dos controles ReportViewer para integrar la funcionalidad de visualización de informes en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="90e21-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] provides two ReportViewer controls for integrating report viewing functionality into your applications.</span></span> <span data-ttu-id="90e21-104">Hay una versión para las aplicaciones basadas en formularios Windows Forms y otra para las aplicaciones de formularios Web Forms.</span><span class="sxs-lookup"><span data-stu-id="90e21-104">There is a version for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="90e21-105">Cada control proporciona una funcionalidad similar, pero cada uno está diseñado para sus entornos individuales.</span><span class="sxs-lookup"><span data-stu-id="90e21-105">Each control provides similar functionality but each is designed to target their individual environments.</span></span> <span data-ttu-id="90e21-106">Ambos controles pueden procesar los informes que se han implementado en un servidor de informes (modo de procesamiento remoto) o que se han copiado en un equipo en el que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no se ha instalado (modo de procesamiento local).</span><span class="sxs-lookup"><span data-stu-id="90e21-106">Both controls can process reports that have been deployed to a report server (remote processing mode) or have been copied to a computer where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] has not been installed (local processing mode).</span></span>  
  
 <span data-ttu-id="90e21-107">El control ReportViewer no incluye compatibilidad integrada para adaptarse dinámicamente a distintos dispositivos con diferentes resoluciones de pantalla.</span><span class="sxs-lookup"><span data-stu-id="90e21-107">The ReportViewer control does not include built-in support for dynamically adapting to different devices with different screen resolutions.</span></span>  
  
## <a name="remote-processing-mode"></a><span data-ttu-id="90e21-108">Modo de procesamiento remoto</span><span class="sxs-lookup"><span data-stu-id="90e21-108">Remote Processing Mode</span></span>  
 <span data-ttu-id="90e21-109">El modo del procesamiento remoto es el método preferido para ver los informes implementados en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="90e21-109">Remote processing mode is the preferred method for viewing reports that have been deployed to a report server.</span></span> <span data-ttu-id="90e21-110">El modo de procesamiento remoto proporciona las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="90e21-110">Remote processing mode provides the following advantages:</span></span>  
  
-   <span data-ttu-id="90e21-111">El procesamiento remoto proporciona una solución optimizada para ejecutar informes porque el servidor de informes los procesa.</span><span class="sxs-lookup"><span data-stu-id="90e21-111">Remote processing provides an optimized solution for running reports because the report is processed by the report server.</span></span>  
  
-   <span data-ttu-id="90e21-112">Dado que el servidor de informes controla todo el procesamiento, en una implementación escalada, varios servidores de informes pueden procesar una solicitud de informe o bien, en un escenario de ampliación de la capacidad, puede procesarla un servidor que tenga varios procesadores.</span><span class="sxs-lookup"><span data-stu-id="90e21-112">Because all processing is handled by the report server, a report request can be processed by multiple report servers in a scale-out deployment or a server that has multiple processors in a scale-up scenario.</span></span>  
  
 <span data-ttu-id="90e21-113">Además, los informes que se ejecutan en modo remoto pueden utilizar la funcionalidad completa del servidor de informes incluidas todas las extensiones de datos y de representación.</span><span class="sxs-lookup"><span data-stu-id="90e21-113">In addition, reports run in remote mode can utilize the full functionality of the report server including all rendering and data extensions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90e21-114">La lista de extensiones disponibles para el control ReportViewer cuando se ejecuta en modo de procesamiento remoto depende de la edición de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que esté instalada en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="90e21-114">The list of extensions available to the ReportViewer control when it is running in remote processing mode depends on the edition of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is installed on the report server.</span></span>  
  
## <a name="local-processing-mode"></a><span data-ttu-id="90e21-115">Modo de procesamiento local</span><span class="sxs-lookup"><span data-stu-id="90e21-115">Local Processing Mode</span></span>  
 <span data-ttu-id="90e21-116">El modo de procesamiento local proporciona un método alternativo para ver y representar los informes cuando [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no está instalado.</span><span class="sxs-lookup"><span data-stu-id="90e21-116">Local processing mode provides an alternative method for viewing and rendering reports when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is not installed.</span></span> <span data-ttu-id="90e21-117">A diferencia del procesamiento remoto, en el control solo está disponible un subconjunto de la funcionalidad que proporciona el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="90e21-117">Unlike remote processing only a subset of the functionality provided by the report server is available in the control.</span></span> <span data-ttu-id="90e21-118">En el modo de procesamiento local, el control no administra el procesamiento de los datos sino que se implementa mediante la aplicación de host.</span><span class="sxs-lookup"><span data-stu-id="90e21-118">In local processing mode, data processing is not handled by the control but rather implemented by the hosting application.</span></span> <span data-ttu-id="90e21-119">Pero el propio control controla el procesamiento de informes.</span><span class="sxs-lookup"><span data-stu-id="90e21-119">However report processing is handled by the control itself.</span></span> <span data-ttu-id="90e21-120">En el modo de procesamiento local, solo están disponibles las extensiones de representación PDF, Excel, Word e Image.</span><span class="sxs-lookup"><span data-stu-id="90e21-120">In local processing mode, only the PDF, Excel, Word, and Image rendering extensions are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e21-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90e21-121">See Also</span></span>  
 <span data-ttu-id="90e21-122">[Integración de Reporting Services en aplicaciones](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="90e21-122">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="90e21-123">Crear informes de SSRS mediante Visual Studio (blog)</span><span class="sxs-lookup"><span data-stu-id="90e21-123">Create SSRS Reports Using Visual Studio (Blog)</span></span>](https://jwcooney.com/2015/01/07/ssrs-basics-set-up-visual-studio-to-write-a-new-ssrs-report/)  
  
  
