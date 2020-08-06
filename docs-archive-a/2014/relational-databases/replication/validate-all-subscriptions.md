---
title: Validar todas las suscripciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.allsubscriptions.f1
helpviewer_keywords:
- Validate All Subscriptions dialog box
ms.assetid: 32e31469-36e4-42d9-a57a-12388bfd229d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27a7a4f5e5c3c303d5a1cbe257c0a0e9b531e824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675259"
---
# <a name="validate-all-subscriptions"></a><span data-ttu-id="28f9d-102">Validar todas las suscripciones</span><span class="sxs-lookup"><span data-stu-id="28f9d-102">Validate All Subscriptions</span></span>
  <span data-ttu-id="28f9d-103">Use el cuadro de diálogo **Validar todas las suscripciones** para especificar que todas las suscripciones a una publicación de combinación deben validarse la próxima vez que se ejecute el Agente de mezcla para cada suscripción.</span><span class="sxs-lookup"><span data-stu-id="28f9d-103">Use the **Validate All Subscriptions** dialog box to specify that all subscriptions to a merge publication should be validated the next time the Merge Agent for each subscription runs.</span></span> <span data-ttu-id="28f9d-104">El resultado de la validación se muestra en el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="28f9d-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="28f9d-105">Para más información, consulte [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="28f9d-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="28f9d-106">También puede validar una sola suscripción si hace clic con el botón secundario en una suscripción en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y hace clic en **Validar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="28f9d-106">It is also possible to validate a single subscription by right-clicking a subscription in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate Subscription**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="28f9d-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="28f9d-107">Options</span></span>  
 <span data-ttu-id="28f9d-108">**Solo comprobar recuentos de filas**</span><span class="sxs-lookup"><span data-stu-id="28f9d-108">**Verify the row counts only**</span></span>  
 <span data-ttu-id="28f9d-109">Seleccione esta opción para validar si la tabla del suscriptor tiene el mismo número de filas que la tabla del publicador.</span><span class="sxs-lookup"><span data-stu-id="28f9d-109">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="28f9d-110">Este método no valida si el contenido de las filas coincide.</span><span class="sxs-lookup"><span data-stu-id="28f9d-110">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="28f9d-111">La validación del recuento de filas proporciona una idea sobre validación que puede ponerle al corriente de problemas con los datos.</span><span class="sxs-lookup"><span data-stu-id="28f9d-111">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="28f9d-112">**Comprobar los recuentos de filas y comparar las sumas de comprobación para comprobar los datos de las filas**</span><span class="sxs-lookup"><span data-stu-id="28f9d-112">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="28f9d-113">Además de llevar a cabo un recuento de filas en el publicador y en el suscriptor, se calcula una suma de comprobación de todos los datos utilizando el algoritmo binario de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="28f9d-113">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="28f9d-114">Si el número de filas da un error, no se lleva a cabo la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="28f9d-114">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="28f9d-115">Esta opción no es válida para [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28f9d-115">This option is not valid for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f9d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28f9d-116">See Also</span></span>  
 [<span data-ttu-id="28f9d-117">Validar datos replicados</span><span class="sxs-lookup"><span data-stu-id="28f9d-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
