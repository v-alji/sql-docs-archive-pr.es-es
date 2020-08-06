---
title: Usar la clase Setting para una extensión de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], settings
- Setting class
ms.assetid: 50746639-da7c-46a5-ac7b-e87dd6b91880
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 594cf28391ae4523e1a95ad79ee5b1280ff72218
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744521"
---
# <a name="using-the-setting-class-for-a-delivery-extension"></a><span data-ttu-id="6e063-102">Usar la clase Setting para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="6e063-102">Using the Setting Class for a Delivery Extension</span></span>
  <span data-ttu-id="6e063-103">La clase <xref:Microsoft.ReportingServices.Interfaces.Setting> se encuentra en el espacio de nombres <xref:Microsoft.ReportingServices.Interfaces> y representa información sobre la configuración de una extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="6e063-103">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is located in the <xref:Microsoft.ReportingServices.Interfaces> namespace and represents information about extension settings for a delivery extension.</span></span> <span data-ttu-id="6e063-104">La clase <xref:Microsoft.ReportingServices.Interfaces.Setting> proporciona la infraestructura para almacenar información sobre la configuración que se requiere para que una extensión de entrega funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="6e063-104">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class provides infrastructure for storing information about the settings that are required in order for a delivery extension to function properly.</span></span> <span data-ttu-id="6e063-105">Por ejemplo, en la distribución por correo electrónico del servidor de informes, un usuario debe proporcionar la configuración específica para la entrega por correo electrónico, por ejemplo la dirección del destinatario, la dirección del remitente, la línea de asunto del correo electrónico, entre otras.</span><span class="sxs-lookup"><span data-stu-id="6e063-105">For example, in Report Server E-Mail delivery, a user is required to supply settings specific to e-mail delivery, such as the recipient's address, the sender's address, the subject line of the e-mail, and more.</span></span> <span data-ttu-id="6e063-106">Indudablemente, los proveedores de entrega personalizados exigirán al usuario que proporcione valores concretos para que la extensión de entrega entregue las notificaciones e informes.</span><span class="sxs-lookup"><span data-stu-id="6e063-106">Undoubtedly, your custom delivery providers will require the user to supply specific settings in order for the delivery extension to deliver notifications and reports.</span></span>  
  
 <span data-ttu-id="6e063-107">La clase <xref:Microsoft.ReportingServices.Interfaces.Setting> se usa al implementar la propiedad <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ExtensionSettings%2A> de la interfaz <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>.</span><span class="sxs-lookup"><span data-stu-id="6e063-107">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is used when implementing the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ExtensionSettings%2A> property of the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface.</span></span> <span data-ttu-id="6e063-108">La clase <xref:Microsoft.ReportingServices.Interfaces.Setting> también se utiliza para procesar los datos de configuración de las extensiones que proporciona un usuario cuando se crea una suscripción o notificación.</span><span class="sxs-lookup"><span data-stu-id="6e063-108">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is also used for processing the extension setting data that is supplied by a user when a subscription or notification is created.</span></span>  
  
 <span data-ttu-id="6e063-109">Para obtener un ejemplo de cómo usar la clase <xref:Microsoft.ReportingServices.Interfaces.Setting>, vea [Ejemplos del producto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="6e063-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.Setting> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e063-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e063-110">See Also</span></span>  
 <span data-ttu-id="6e063-111">[Implementar una extensión de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="6e063-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="6e063-112">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6e063-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
