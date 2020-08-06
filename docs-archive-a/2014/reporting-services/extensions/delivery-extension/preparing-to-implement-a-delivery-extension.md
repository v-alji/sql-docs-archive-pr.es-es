---
title: Preparar la implementación de una extensión de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- interfaces [Reporting Services]
- delivery extensions [Reporting Services], implementing
ms.assetid: aee1608d-374f-4ad3-bc23-fe07fdaa52b7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bbf98286e6ed35542d8117b4b87b5ff3425def69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678078"
---
# <a name="preparing-to-implement-a-delivery-extension"></a><span data-ttu-id="1d9f6-102">Preparar la implementación de una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="1d9f6-102">Preparing to Implement a Delivery Extension</span></span>
  <span data-ttu-id="1d9f6-103">Antes de implementar la extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], debería definir las interfaces que se van a implementar.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-103">Before you implement your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, you should define the interfaces to implement.</span></span> <span data-ttu-id="1d9f6-104">Primero hay que decidir cómo se utilizará la extensión de entrega, qué valores requerirá y la funcionalidad concreta que tendrá que implementar para entregar las notificaciones de informes.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-104">You first need to decide how your delivery extension will be used, what settings your delivery extension will require, and the specific functionality you will need to implement in order to deliver report notifications.</span></span>  
  
 <span data-ttu-id="1d9f6-105">Cada extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] debe proporcionar la funcionalidad siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d9f6-105">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension must provide the following functionality:</span></span>  
  
-   <span data-ttu-id="1d9f6-106">Una implementación de la interfaz <xref:Microsoft.ReportingServices.Interfaces.IExtension> que representa la extensión y un nombre de extensión traducido.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-106">An <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface implementation that represents the extension and a localized extension name.</span></span>  
  
-   <span data-ttu-id="1d9f6-107">Una implementación <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> que crea una extensión de entrega que se puede utilizar para entregar notificaciones de informe a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-107">An <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> implementation that creates a delivery extension that can be used to deliver report notifications to end users.</span></span>  
  
-   <span data-ttu-id="1d9f6-108">La capacidad de procesar los datos de usuarios concretos para una suscripción.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-108">The ability to process specific user data for a subscription.</span></span>  
  
 <span data-ttu-id="1d9f6-109">Cada extensión de entrega puede mejorarse para incluir la funcionalidad siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d9f6-109">Each delivery extension can be enhanced to include the following functionality:</span></span>  
  
-   <span data-ttu-id="1d9f6-110">Una implementación del control de usuario de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] que permite a los usuarios finales utilizar el Administrador de informes para crear suscripciones de informe que utilizan la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-110">An [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] user control implementation that enables end users to use Report Manager to create report subscriptions that use the delivery extension.</span></span>  
  
 <span data-ttu-id="1d9f6-111">En la tabla siguiente se describen las interfaces y la clases disponibles para las extensiones de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-111">The following table describes the available interfaces and classes for delivery extensions.</span></span>  
  
|<span data-ttu-id="1d9f6-112">Interfaz o clase</span><span class="sxs-lookup"><span data-stu-id="1d9f6-112">Interface or class</span></span>|<span data-ttu-id="1d9f6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d9f6-113">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="1d9f6-114"><xref:Microsoft.ReportingServices.Interfaces.IExtension> Interfaz</span><span class="sxs-lookup"><span data-stu-id="1d9f6-114"><xref:Microsoft.ReportingServices.Interfaces.IExtension> Interface</span></span>|<span data-ttu-id="1d9f6-115">Representa una extensión en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d9f6-115">Represents an extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|<span data-ttu-id="1d9f6-116"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> Interfaz</span><span class="sxs-lookup"><span data-stu-id="1d9f6-116"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> Interface</span></span>|<span data-ttu-id="1d9f6-117">Representa una extensión de entrega en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d9f6-117">Represents a delivery extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|<span data-ttu-id="1d9f6-118"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> Interfaz</span><span class="sxs-lookup"><span data-stu-id="1d9f6-118"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> Interface</span></span>|<span data-ttu-id="1d9f6-119">Contiene información sobre el servidor de informes que requieren las extensiones de entrega (por ejemplo, una lista de las extensiones de representación disponibles).</span><span class="sxs-lookup"><span data-stu-id="1d9f6-119">Contains information about the report server that is required by delivery extensions (for example, a list of the available rendering extensions).</span></span>|  
|<span data-ttu-id="1d9f6-120">Clase <xref:Microsoft.ReportingServices.Interfaces.Setting></span><span class="sxs-lookup"><span data-stu-id="1d9f6-120"><xref:Microsoft.ReportingServices.Interfaces.Setting> Class</span></span>|<span data-ttu-id="1d9f6-121">Representa un valor para una extensión.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-121">Represents a setting for an extension.</span></span>|  
|<span data-ttu-id="1d9f6-122">Clase <xref:Microsoft.ReportingServices.Interfaces.Notification></span><span class="sxs-lookup"><span data-stu-id="1d9f6-122"><xref:Microsoft.ReportingServices.Interfaces.Notification> Class</span></span>|<span data-ttu-id="1d9f6-123">Contiene información de suscripción que las extensiones de entrega utilizan para entregar los informes.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-123">Contains subscription information that delivery extensions use to deliver reports.</span></span>|  
|<span data-ttu-id="1d9f6-124">Clase <xref:Microsoft.ReportingServices.Interfaces.Report></span><span class="sxs-lookup"><span data-stu-id="1d9f6-124"><xref:Microsoft.ReportingServices.Interfaces.Report> Class</span></span>|<span data-ttu-id="1d9f6-125">Representa la información específica del informe y los métodos que permiten a las extensiones de entrega entregar los informes a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-125">Represents report-specific information and methods that enable delivery extensions to deliver reports to users.</span></span>|  
|<span data-ttu-id="1d9f6-126">Clase <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile></span><span class="sxs-lookup"><span data-stu-id="1d9f6-126"><xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> Class</span></span>|<span data-ttu-id="1d9f6-127">Representa la salida de una extensión de representación.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-127">Represents the output from a rendering extension.</span></span> <span data-ttu-id="1d9f6-128">Un objeto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> contiene el nombre de archivo asociado e información de tipo que requiere la extensión de entrega para procesar el flujo que devuelve la extensión de representación.</span><span class="sxs-lookup"><span data-stu-id="1d9f6-128">A <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object contains the associated file name and type information that is required by the delivery extension in order to process the stream returned by the rendering extension.</span></span>|  
|<span data-ttu-id="1d9f6-129"><xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> Interfaz</span><span class="sxs-lookup"><span data-stu-id="1d9f6-129"><xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> Interface</span></span>|<span data-ttu-id="1d9f6-130">Un control de usuario que representa los medios para recuperar la información de la suscripción específica de la extensión de entrega del usuario en el Administrador de informes (por ejemplo, una dirección de correo electrónico o la ruta de acceso a un recurso compartido de archivos).</span><span class="sxs-lookup"><span data-stu-id="1d9f6-130">A user control that represents the means to retrieve delivery extension-specific subscription information from the user in Report Manager (for example, an e-mail address or the path to a file share).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d9f6-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d9f6-131">See Also</span></span>  
 <span data-ttu-id="1d9f6-132">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="1d9f6-132">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="1d9f6-133">[Implementar una extensión de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="1d9f6-133">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="1d9f6-134">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1d9f6-134">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
