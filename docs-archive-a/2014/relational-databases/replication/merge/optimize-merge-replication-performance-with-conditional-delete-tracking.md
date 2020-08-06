---
title: Optimizar el rendimiento de la replicación de mezcla con seguimiento condicional de eliminaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- conditional delete tracking [SQL Server replication]
- merge replication [SQL Server replication], conditional delete tracking
- articles [SQL Server replication], conditional delete tracking
ms.assetid: 58f120a3-ea3a-4e97-93f0-0eb4e580ecf2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46fc189d2a2e0ebf5ea44775585a69d52783a7e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661952"
---
# <a name="optimize-merge-replication-performance-with-conditional-delete-tracking"></a><span data-ttu-id="dcf5b-102">Optimizar el rendimiento de la replicación de mezcla con seguimiento condicional de eliminaciones</span><span class="sxs-lookup"><span data-stu-id="dcf5b-102">Optimize Merge Replication Performance with Conditional Delete Tracking</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="dcf5b-103">En la replicación de mezcla, puede especificar que los desencadenadores de replicación y las tablas del sistema no realicen el seguimiento de las eliminaciones de uno o varios artículos.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-103">With merge replication you can specify that deletes for one or more articles should not be tracked by replication triggers and system tables.</span></span> <span data-ttu-id="dcf5b-104">Si se especifica esta opción para un artículo, no se realiza el seguimiento ni la replicación de las eliminaciones del publicador ni de ningún suscriptor.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-104">If you specify this option for an article, deletes are not tracked or replicated from the Publisher or any Subscribers.</span></span> <span data-ttu-id="dcf5b-105">Esta opción está disponible para admitir una serie de casos de aplicación y para proporcionar una optimización del rendimiento para los casos en los que la replicación de eliminaciones no es necesaria o deseable.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-105">This option is available to support a number of application scenarios and to provide a performance optimization for cases in which the replication of deletes is not necessary or desirable.</span></span> <span data-ttu-id="dcf5b-106">El rendimiento se mejora de tres maneras: los metadatos de las eliminaciones no se almacenan, las eliminaciones no se enumeran durante la sincronización, y las eliminaciones no se replican ni se aplican en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-106">Performance is enhanced in three ways: metadata for deletes is not stored; deletes are not enumerated during synchronization; deletes are not replicated to and applied at the Subscriber.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcf5b-107">Para utilizar artículos de solo descarga, el nivel de compatibilidad de la publicación debe ser como mínimo de 90RTM.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-107">To use download-only articles, the compatibility level of the publication must be at least 90RTM.</span></span>  
  
 <span data-ttu-id="dcf5b-108">La opción se puede especificar al crear una publicación, o bien se puede activar o desactivar si la aplicación requiere que algunas eliminaciones se repliquen y otras no, como las eliminaciones por lotes.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-108">The option can be specified when a publication is created or it can be toggled on and off if an application requires that some deletes be replicated and that others not be replicated, such as batch deletes.</span></span> <span data-ttu-id="dcf5b-109">En los siguientes ejemplos se ilustra de qué maneras se puede utilizar esta opción en una aplicación:</span><span class="sxs-lookup"><span data-stu-id="dcf5b-109">The following examples illustrate ways in which this option might be used in an application:</span></span>  
  
-   <span data-ttu-id="dcf5b-110">Normalmente, una aplicación para personal de ventas móvil tiene tablas como **SalesOrderHeader**, **SalesOrderDetail** y **Product**.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-110">An application for a mobile sales force typically has tables such as **SalesOrderHeader**, **SalesOrderDetail** and **Product**.</span></span> <span data-ttu-id="dcf5b-111">Los pedidos se pasan al suscriptor y después se replican en el publicador, que suele proporcionar los datos a un sistema de cumplimentación de pedidos.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-111">Orders are entered at the Subscriber and then replicated to the Publisher, which often supplies data to an order fulfillment system.</span></span> <span data-ttu-id="dcf5b-112">Muchos trabajadores móviles utilizan dispositivos de mano que tienen un almacenamiento limitado: una vez recibido el pedido en el publicador, dicho pedido puede eliminarse del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-112">Many mobile workers use handheld devices which have limited storage: after the order is received at the Publisher, it can be deleted at the Subscriber.</span></span> <span data-ttu-id="dcf5b-113">La eliminación no se propaga al publicador porque el pedido sigue activo en el sistema.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-113">The delete is not propagated to the Publisher, because the order is still active in the system.</span></span>  
  
     <span data-ttu-id="dcf5b-114">En esta situación, no se realiza el seguimiento de las eliminaciones para las tablas **SalesOrderHeader** y **SalesOrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="dcf5b-114">In this scenario, deletes would not be tracked for the **SalesOrderHeader** and **SalesOrderDetail** tables.</span></span> <span data-ttu-id="dcf5b-115">Se realiza el seguimiento de las eliminaciones para la tabla **Product** , ya que si se elimina un producto en el publicador, la eliminación debe enviarse al suscriptor para que la lista de productos se mantenga actualizada.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-115">Deletes would be tracked for the **Product** table, because if a product is deleted at the Publisher, the delete should be sent to the Subscriber to keep the product list up to date.</span></span>  
  
-   <span data-ttu-id="dcf5b-116">Una aplicación puede almacenar datos históricos en una tabla como **TransactionHistory**, de la que periódicamente se purgan los registros cuya antigüedad es superior a un año.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-116">An application could store historical data in a table such as **TransactionHistory**, which is periodically purged of records older than a year.</span></span> <span data-ttu-id="dcf5b-117">La tabla se puede filtrar para que los suscriptores reciban solo los datos de las transacciones del mes en curso.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-117">The table could be filtered such that Subscribers only receive data on transactions within the current month.</span></span> <span data-ttu-id="dcf5b-118">Las eliminaciones mensuales de lotes en el publicador que purgan datos antiguos no son relevantes para los suscriptores, pero aun así se realiza un seguimiento de las mismas y se enumeran de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-118">Monthly batch deletes at the Publisher that purge older data are not relevant to Subscribers, but they would still be tracked and enumerated by default.</span></span>  
  
     <span data-ttu-id="dcf5b-119">En esta situación, antes de que tenga lugar el procesamiento por lotes, la actividad podría detenerse en el sistema y la aplicación podría deshabilitar el seguimiento de las eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-119">In this scenario, before the batch processing occurred, activity could be stopped on the system, and the application could disable the tracking of deletes.</span></span> <span data-ttu-id="dcf5b-120">Una vez completado el procesamiento, el seguimiento podría volver a habilitarse.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-120">After the processing has finished, tracking could again be enabled.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dcf5b-121">Si siguen llevándose a cabo otras actividades en el publicador, deberá asegurarse de que no se producen eliminaciones que se deban propagar a los suscriptores mientras el seguimiento de eliminaciones está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-121">If other activity continues at the Publisher, you must ensure that deletes that should be propagated to Subscribers do not occur while delete tracking is disabled.</span></span>  
  
 <span data-ttu-id="dcf5b-122">**Para especificar que no se realice el seguimiento de las eliminaciones**</span><span class="sxs-lookup"><span data-stu-id="dcf5b-122">**To specify that deletes should not be tracked**</span></span>  
  
-   <span data-ttu-id="dcf5b-123">Programación [!INCLUDE[tsql](../../../includes/tsql-md.md)] de la replicación: [especificar que no se debe realizar un seguimiento de las eliminaciones para los artículos de mezcla &#40;programación de la replicación con Transact-SQL&#41;](..//publish/specify-merge-replication-properties.md#tracking-deletes)</span><span class="sxs-lookup"><span data-stu-id="dcf5b-123">Replication [!INCLUDE[tsql](../../../includes/tsql-md.md)] programming: [Specify That Deletes Should Not Be Tracked For Merge Articles &#40;Replication Transact-SQL Programming&#41;](..//publish/specify-merge-replication-properties.md#tracking-deletes)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf5b-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dcf5b-124">See Also</span></span>  
 <span data-ttu-id="dcf5b-125">[Opciones de artículo para la replicación de mezcla](article-options-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="dcf5b-125">[Article Options for Merge Replication](article-options-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="dcf5b-126">Optimizar el rendimiento de la replicación de mezcla con artículos de solo descarga</span><span class="sxs-lookup"><span data-stu-id="dcf5b-126">Optimize Merge Replication Performance with Download-Only Articles</span></span>](optimize-merge-replication-performance-with-download-only-articles.md)  
  
  
