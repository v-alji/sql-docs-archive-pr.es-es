---
title: Implementar una extensión de entrega | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery [Reporting Services]
- custom delivery extensions [Reporting Services]
- extensions [Reporting Services], delivery
- delivery extensions [Reporting Services]
ms.assetid: 600cd229-efcd-480e-8c95-3c3c39ff4e7a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af1e804e029dae77fb7836577aa8d4a45ad20109
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678084"
---
# <a name="implementing-a-delivery-extension"></a><span data-ttu-id="a8508-102">Implementar una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-102">Implementing a Delivery Extension</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="a8508-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] permite a los usuarios crear y publicar informes que, una vez creados y publicados, se pueden entregar en varias ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="a8508-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enables users to create and publish reports that, once created and published, can be delivered to various locations.</span></span> <span data-ttu-id="a8508-104">Además, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] incluye varias extensiones de entrega y una API de entrega que permite a los programadores crear extensiones de entrega adicionales para extender aún más la funcionalidad de entrega en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8508-104">In addition, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes several delivery extensions and a delivery API that enable developers to create additional delivery extensions to further extend the functionality of delivery in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a8508-105">Para obtener una implementación de ejemplo de una extensión de entrega, vea [Ejemplos del producto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="a8508-105">For a sample implementation of a delivery extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8508-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a8508-106">In This Section</span></span>  
 <span data-ttu-id="a8508-107">[Introducción a las extensiones de entrega] Delivery-Extensions-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a8508-107">[Delivery Extensions Overview]delivery-extensions-overview.md)</span></span>  
 <span data-ttu-id="a8508-108">Introduce cómo escribir una extensión de entrega personalizada para [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8508-108">Introduces how to write a custom delivery extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="a8508-109">Preparación de la ejecución de una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-109">Preparing to Implement a Delivery Extension</span></span>](preparing-to-implement-a-delivery-extension.md)  
 <span data-ttu-id="a8508-110">Describe las interfaces y clases disponibles al implementar una extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], así como cuestiones que hay que considerar antes de la implementación.</span><span class="sxs-lookup"><span data-stu-id="a8508-110">Describes the interfaces and classes available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, as well as issues to consider before implementation.</span></span>  
  
 [<span data-ttu-id="a8508-111">Creación de una biblioteca de extensiones de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-111">Creating a Delivery Extension Library</span></span>](creating-a-delivery-extension-library.md)  
 <span data-ttu-id="a8508-112">Describe cómo asignar un espacio de nombres para su extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] y cómo compilarla en una biblioteca DLL.</span><span class="sxs-lookup"><span data-stu-id="a8508-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension and compiling your delivery extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="a8508-113">Ejecución de la interfaz IDeliveryExtension para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-113">Implementing the IDeliveryExtension Interface for a Delivery Extension</span></span>](implementing-the-ideliveryextension-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="a8508-114">Describe los atributos de una extensión de entrega y cómo implementar su propia clase de extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="a8508-114">Describes the attributes of a delivery extension, and how to implement your own delivery extension class.</span></span>  
  
 [<span data-ttu-id="a8508-115">Uso de una clase Notification para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-115">Using a Notification Class for a Delivery Extension</span></span>](using-a-notification-class-for-a-delivery-extension.md)  
 <span data-ttu-id="a8508-116">Describe los atributos de una clase **Notification** y cómo usarla en la implementación de la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="a8508-116">Describes the attributes of a **Notification** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="a8508-117">Uso de la clase Setting para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-117">Using the Setting Class for a Delivery Extension</span></span>](using-the-setting-class-for-a-delivery-extension.md)  
 <span data-ttu-id="a8508-118">Describe los atributos de una clase **Setting** y cómo usarla en la implementación de la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="a8508-118">Describes the attributes of a **Setting** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="a8508-119">Utilizar la interfaz IDeliveryReportServerInformation para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-119">Using the IDeliveryReportServerInformation Interface for a Delivery Extension</span></span>](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="a8508-120">Describe los atributos de una interfaz **IDeliveryReportServerInformation** y cómo usarla en la implementación de la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="a8508-120">Describes the attributes of a **IDeliveryReportServerInformation** interface and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="a8508-121">Usar la clase Report para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-121">Using the Report Class for a Delivery Extension</span></span>](using-the-report-class-for-a-delivery-extension.md)  
 <span data-ttu-id="a8508-122">Describe los atributos de una clase **Report** y cómo usarla en la implementación de la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="a8508-122">Describes the attributes of a **Report** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="a8508-123">Usar la clase RenderedOutputFile para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-123">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
 <span data-ttu-id="a8508-124">Describe los atributos de una clase **RenderedOutputFile** y cómo usarla en la implementación de la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="a8508-124">Describes the attributes of a **RenderedOutputFile** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="a8508-125">Implementar la interfaz ISubscriptionBaseUIUserControl para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-125">Implementing the ISubscriptionBaseUIUserControl Interface for a Delivery Extension</span></span>](implementing-the-isubscriptionbaseuiusercontrol-interface.md)  
 <span data-ttu-id="a8508-126">Describe los atributos de un control de usuario de extensión de entrega y cómo implementar su propia interfaz de usuario para una suscripción.</span><span class="sxs-lookup"><span data-stu-id="a8508-126">Describes the attributes of a delivery extension user control and how to implement your own user interface for a subscription.</span></span>  
  
 [<span data-ttu-id="a8508-127">Implementación de una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-127">Deploying a Delivery Extension</span></span>](deploying-a-delivery-extension.md)  
 <span data-ttu-id="a8508-128">Describe cómo implementar una extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="a8508-128">Describes how to deploy your delivery extension.</span></span>  
  
 [<span data-ttu-id="a8508-129">Depurar el código de extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-129">Debugging Delivery Extension Code</span></span>](debugging-delivery-extension-code.md)  
 <span data-ttu-id="a8508-130">Describe cómo depurar el código en una extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="a8508-130">Describes how to debug code in your delivery extension.</span></span>  
  
 [<span data-ttu-id="a8508-131">Quitar una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="a8508-131">Removing a Delivery Extension</span></span>](removing-a-delivery-extension.md)  
 <span data-ttu-id="a8508-132">Describe cómo quitar una extensión de entrega de un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a8508-132">Describes how to remove a delivery extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8508-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8508-133">See Also</span></span>  
 <span data-ttu-id="a8508-134">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="a8508-134">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="a8508-135">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a8508-135">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
