---
title: Validar una suscripción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.validateandresynch.f1
helpviewer_keywords:
- Validate Subscription dialog box
ms.assetid: 74bdf5e1-b886-4284-b5fb-332bf79ae083
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 010b5b2e9778ccf37133b0a84796373c012290f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670913"
---
# <a name="validate-subscription"></a><span data-ttu-id="6ba20-102">Validar suscripción</span><span class="sxs-lookup"><span data-stu-id="6ba20-102">Validate Subscription</span></span>
  <span data-ttu-id="6ba20-103">Use el cuadro de diálogo **Validar suscripción** para especificar que es necesario validar una suscripción a una publicación de combinación la próxima vez que se ejecute el Agente de mezcla para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="6ba20-103">Use the **Validate Subscription** dialog box to specify that a subscription to a merge publication should be validated the next time the Merge Agent for the subscription runs.</span></span> <span data-ttu-id="6ba20-104">El resultado de la validación se muestra en el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="6ba20-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="6ba20-105">Para más información, consulte [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="6ba20-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="6ba20-106">Para validar todas las suscripciones a una publicación de combinación, también puede hacer clic con el botón derecho en una publicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y hacer clic en **Validar todas las suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="6ba20-106">It is also possible to validate all subscriptions to a merge publication by right-clicking a publication in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate All Subscriptions**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6ba20-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="6ba20-107">Options</span></span>  
 <span data-ttu-id="6ba20-108">**Fecha del último intento de validación**</span><span class="sxs-lookup"><span data-stu-id="6ba20-108">**Date of the last attempted validation**</span></span>  
 <span data-ttu-id="6ba20-109">Muestra la fecha de la última sesión del Agente de mezcla en la que se validó la suscripción, independientemente de si la validación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ba20-109">The date of the last Merge Agent session that included subscription validation, whether or not that validation was successful.</span></span>  
  
 <span data-ttu-id="6ba20-110">**Fecha de la última validación correcta**</span><span class="sxs-lookup"><span data-stu-id="6ba20-110">**Date of the last successful validation**</span></span>  
 <span data-ttu-id="6ba20-111">Muestra la fecha de la sesión del Agente de mezcla en la que se realizó correctamente la validación de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="6ba20-111">The date of the last Merge Agent session that included a successful subscription validation.</span></span>  
  
 <span data-ttu-id="6ba20-112">**Validar esta suscripción**</span><span class="sxs-lookup"><span data-stu-id="6ba20-112">**Validate this subscription**</span></span>  
 <span data-ttu-id="6ba20-113">Seleccione esta opción para validar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="6ba20-113">Select to validate the subscription.</span></span>  
  
 <span data-ttu-id="6ba20-114">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="6ba20-114">**Options**</span></span>  
 <span data-ttu-id="6ba20-115">Haga clic para tener acceso al cuadro de diálogo **Opciones de validación de subscripciones** , que permite especificar si desea usar la validación del recuento de filas o la validación de las sumas de comprobación binarias.</span><span class="sxs-lookup"><span data-stu-id="6ba20-115">Click to access the **Subscription Validation Options** dialog box, which allows you to specify whether to use row count validation or binary checksum validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ba20-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ba20-116">See Also</span></span>  
 [<span data-ttu-id="6ba20-117">Validar datos replicados</span><span class="sxs-lookup"><span data-stu-id="6ba20-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
