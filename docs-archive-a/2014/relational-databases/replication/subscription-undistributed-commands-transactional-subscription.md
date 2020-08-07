---
title: Suscripción, comandos sin distribuir (suscripción transaccional, SQL Server 2005 y versiones posteriores) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.performance.f1
ms.assetid: 5451561e-0ce3-4bb5-844a-88cd15b0b371
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6bbd82b4f4855c99076404d8b621edca11a7e1e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745710"
---
# <a name="subscription-undistributed-commands-transactional-subscription-sql-server-2005-and-later"></a><span data-ttu-id="f7bff-102">Suscripción, Comandos sin distribuir (Suscripción transaccional, SQL Server 2005 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="f7bff-102">Subscription, Undistributed Commands (Transactional Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="f7bff-103">En la pestaña **Comandos sin distribuir** se muestra información sobre le número de comandos de la base de datos de distribución que no se han entregado al suscriptor seleccionado y el tiempo estimado para entregar esos comandos.</span><span class="sxs-lookup"><span data-stu-id="f7bff-103">The **Undistributed Commands** tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="f7bff-104">Para información sobre cómo ver los comandos en la base de datos de distribución, vea [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f7bff-104">For information about viewing the commands in the distribution database, see [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f7bff-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="f7bff-105">Options</span></span>  
 <span data-ttu-id="f7bff-106">**Número de comandos en la base de datos de distribución en espera de ser aplicados al suscriptor**</span><span class="sxs-lookup"><span data-stu-id="f7bff-106">**Number of commands in the distribution database waiting to be applied to this Subscriber**</span></span>  
 <span data-ttu-id="f7bff-107">Número de comandos de la base de datos de distribución que no se han entregado al suscriptor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f7bff-107">The number of commands in the distribution database that have not been delivered to the selected Subscriber.</span></span> <span data-ttu-id="f7bff-108">Un comando se compone de una instrucción de lenguaje de manipulación de datos (DML) de Transact-SQL o una instrucción de lenguaje de definición de datos (DDL).</span><span class="sxs-lookup"><span data-stu-id="f7bff-108">A command consists of one Transact-SQL data manipulation language (DML) statement or one data definition language (DDL) statement.</span></span>  
  
 <span data-ttu-id="f7bff-109">**Tiempo estimado para aplicar estos comandos según las últimas operaciones**</span><span class="sxs-lookup"><span data-stu-id="f7bff-109">**Estimated time to apply these commands, based on past performance**</span></span>  
 <span data-ttu-id="f7bff-110">Cantidad estimada de tiempo para entregar comandos al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="f7bff-110">The estimated amount of time to deliver commands to the Subscriber.</span></span> <span data-ttu-id="f7bff-111">Si este valor es superior al tiempo necesario para generar y aplicar una instantánea en el suscriptor, considere la posibilidad de volver a reinicializar el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="f7bff-111">If this value is greater than the amount of time required to generate and apply a snapshot to the Subscriber, consider reinitializing the Subscriber.</span></span> <span data-ttu-id="f7bff-112">Para obtener más información, vea [Reinicializar suscripciones](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="f7bff-112">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7bff-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7bff-113">See Also</span></span>  
 <span data-ttu-id="f7bff-114">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f7bff-114">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="f7bff-115">[Supervisar el rendimiento con el monitor de replicación](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f7bff-115">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 [<span data-ttu-id="f7bff-116">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="f7bff-116">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
