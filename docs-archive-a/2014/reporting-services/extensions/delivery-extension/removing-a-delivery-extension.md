---
title: Quitar una extensión de entrega | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- removing delivery extensions
- deleting delivery extensions
- delivery extensions [Reporting Services], removing
ms.assetid: dcb7caf2-d19a-4bc5-afb3-2b61ad11cac5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7c4320f46b5013b0fa2accbc81792748c2d9f384
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678076"
---
# <a name="removing-a-delivery-extension"></a><span data-ttu-id="e04e1-102">Quitar una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="e04e1-102">Removing a Delivery Extension</span></span>
  <span data-ttu-id="e04e1-103">Para quitar una extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], basta con quitar el elemento **Extension** para la extensión de entrega del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e04e1-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, simply remove the **Extension** element for your delivery extension from the configuration file.</span></span> <span data-ttu-id="e04e1-104">Después de quitar la información de configuración, la extensión de entrega deja de estar disponible en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e04e1-104">After the configuration information is removed, the delivery extension is no longer available to the report server.</span></span>  
  
 <span data-ttu-id="e04e1-105">Cuando el elemento **Extension** correspondiente de la extensión de entrega se quita del archivo de configuración, ya no está registrado en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e04e1-105">Once a delivery extension's corresponding **Extension** element is removed from the configuration file, it is no longer registered with the report server.</span></span> <span data-ttu-id="e04e1-106">El servidor de informes quita la entrada de la lista de extensiones de entrega y desactiva cualquier suscripción que use esa extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="e04e1-106">The report server removes the entry from the list of delivery extensions and deactivates any subscriptions which use that delivery extension.</span></span> <span data-ttu-id="e04e1-107">Cuando una extensión de entrega se quita, los usuarios ya no pueden seleccionarla como un método de notificación.</span><span class="sxs-lookup"><span data-stu-id="e04e1-107">When a delivery extension is removed, users are no longer able to select it as a method of notification.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e04e1-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e04e1-108">See Also</span></span>  
 <span data-ttu-id="e04e1-109">[Implementar una extensión de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="e04e1-109">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="e04e1-110">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e04e1-110">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
