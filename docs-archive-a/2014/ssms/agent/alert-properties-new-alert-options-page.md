---
title: 'Propiedades de alerta: nueva alerta (página Opciones) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.options.f1
ms.assetid: 6e4f41aa-832d-46ba-b6b5-cf1d3b15d33f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a1507372aa1516c2a88b8682faa77a7d57e58f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748495"
---
# <a name="alert-properties-new-alert-options-page"></a><span data-ttu-id="45eeb-102">Propiedades de la alerta: Nueva alerta (página Opciones)</span><span class="sxs-lookup"><span data-stu-id="45eeb-102">Alert Properties: New Alert (Options Page)</span></span>
  <span data-ttu-id="45eeb-103">Utilice esta página para ver y modificar las opciones de las [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas del agente.</span><span class="sxs-lookup"><span data-stu-id="45eeb-103">Use this page to view and modify options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="45eeb-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="45eeb-104">Options</span></span>  
 <span data-ttu-id="45eeb-105">**Por**</span><span class="sxs-lookup"><span data-stu-id="45eeb-105">**E-mail**</span></span>  
 <span data-ttu-id="45eeb-106">Incluye el texto de error del evento, si existe alguno, en las notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="45eeb-106">Include error text from the event, if any, in e-mail notifications.</span></span>  
  
 <span data-ttu-id="45eeb-107">**Buscapersonas**</span><span class="sxs-lookup"><span data-stu-id="45eeb-107">**Pager**</span></span>  
 <span data-ttu-id="45eeb-108">Incluye el texto de error del evento, si existe alguno, en las notificaciones de buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="45eeb-108">Include error text from the event, if any, in pager notifications.</span></span>  
  
 <span data-ttu-id="45eeb-109">**Net send**</span><span class="sxs-lookup"><span data-stu-id="45eeb-109">**Net send**</span></span>  
 <span data-ttu-id="45eeb-110">Incluye el texto de error del evento, si existe alguno, en las notificaciones de NET SEND.</span><span class="sxs-lookup"><span data-stu-id="45eeb-110">Include error text from the event, if any, in net send notifications.</span></span>  
  
 <span data-ttu-id="45eeb-111">**Mensaje adicional de notificación para enviar**</span><span class="sxs-lookup"><span data-stu-id="45eeb-111">**Additional notification message to send**</span></span>  
 <span data-ttu-id="45eeb-112">Escriba el texto adicional que se va a incluir en los mensajes de notificación.</span><span class="sxs-lookup"><span data-stu-id="45eeb-112">Type any additional text to include in notification messages.</span></span>  
  
 <span data-ttu-id="45eeb-113">**Retardo entre respuestas**</span><span class="sxs-lookup"><span data-stu-id="45eeb-113">**Delay between responses**</span></span>  
 <span data-ttu-id="45eeb-114">Especifique un retardo para las repeticiones del evento.</span><span class="sxs-lookup"><span data-stu-id="45eeb-114">Specify a delay for repeated occurrences of the event.</span></span> <span data-ttu-id="45eeb-115">Algunos eventos pueden producirse con frecuencia durante un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="45eeb-115">Some events may occur frequently during a short period of time.</span></span> <span data-ttu-id="45eeb-116">En este caso, es posible que desee saber que se ha producido el evento, pero sin necesidad de generar una respuesta para cada evento.</span><span class="sxs-lookup"><span data-stu-id="45eeb-116">In this case, you may want to know that the event has occurred, but you may not want a response for every event.</span></span> <span data-ttu-id="45eeb-117">Utilice esta opción para especificar un tiempo de espera. Con un retraso, después de que la alerta responda a un evento, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente espera el retraso especificado antes de responder de nuevo, independientemente de si el evento se produce durante el retraso.</span><span class="sxs-lookup"><span data-stu-id="45eeb-117">Use this option to specify a time-out. With a delay, after the alert responds to an event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for the delay specified before responding again, regardless of whether the event occurs during the delay.</span></span>  
  
 <span data-ttu-id="45eeb-118">**Minutos**</span><span class="sxs-lookup"><span data-stu-id="45eeb-118">**Minutes**</span></span>  
 <span data-ttu-id="45eeb-119">Especifique un retardo en minutos.</span><span class="sxs-lookup"><span data-stu-id="45eeb-119">Specify a delay in minutes.</span></span> <span data-ttu-id="45eeb-120">Para responder cada vez que se produce el evento, especifique 0 minutos y 0 segundos.</span><span class="sxs-lookup"><span data-stu-id="45eeb-120">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
 <span data-ttu-id="45eeb-121">**Segundos**</span><span class="sxs-lookup"><span data-stu-id="45eeb-121">**Seconds**</span></span>  
 <span data-ttu-id="45eeb-122">Especifique un retardo en segundos.</span><span class="sxs-lookup"><span data-stu-id="45eeb-122">Specify a delay in seconds.</span></span> <span data-ttu-id="45eeb-123">Para responder cada vez que se produce el evento, especifique 0 minutos y 0 segundos.</span><span class="sxs-lookup"><span data-stu-id="45eeb-123">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45eeb-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45eeb-124">See Also</span></span>  
 [<span data-ttu-id="45eeb-125">Alertas</span><span class="sxs-lookup"><span data-stu-id="45eeb-125">Alerts</span></span>](alerts.md)  
  
  
