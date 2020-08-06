---
title: blocked process threshold (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- thresholds [SQL Server]
- blocked process threshold option
ms.assetid: 3d46d143-bc6a-4220-8b55-6baa37547c25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9d5b61aaf23a8e74cb11afbf4e8bdb958fde6abe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748257"
---
# <a name="blocked-process-threshold-server-configuration-option"></a><span data-ttu-id="c5125-102">blocked process threshold (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="c5125-102">blocked process threshold Server Configuration Option</span></span>
  <span data-ttu-id="c5125-103">Utilice la opción **blocked process threshold** (umbral de proceso bloqueado) para especificar el umbral, en segundos, con el que se generan los informes de procesos bloqueados.</span><span class="sxs-lookup"><span data-stu-id="c5125-103">Use the **blocked process threshold** option to specify the threshold, in seconds, at which blocked process reports are generated.</span></span> <span data-ttu-id="c5125-104">El umbral puede establecerse en un valor comprendido entre 0 y 86.400.</span><span class="sxs-lookup"><span data-stu-id="c5125-104">The threshold can be set from 0 to 86,400.</span></span> <span data-ttu-id="c5125-105">De manera predeterminada, se producen informes de procesos no bloqueados.</span><span class="sxs-lookup"><span data-stu-id="c5125-105">By default, no blocked process reports are produced.</span></span> <span data-ttu-id="c5125-106">Este evento no se genera para las tareas del sistema o las tareas que están esperando en recursos que no generan interbloqueos detectables.</span><span class="sxs-lookup"><span data-stu-id="c5125-106">This event is not generated for system tasks or for tasks that are waiting on resources that do not generate detectable deadlocks.</span></span>  
  
 <span data-ttu-id="c5125-107">Puede definir una [alerta](../../ssms/agent/alerts.md) para que se ejecute cuando se genera este evento.</span><span class="sxs-lookup"><span data-stu-id="c5125-107">You can define an [alert](../../ssms/agent/alerts.md) to be executed when this event is generated.</span></span> <span data-ttu-id="c5125-108">Por ejemplo, puede elegir que se envíe un aviso al localizador del administrador para que tome la acción adecuada en una situación de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c5125-108">So for example, you can choose to page the administrator to take appropriate action to handle the blocking situation.</span></span>  
  
 <span data-ttu-id="c5125-109">El umbral de proceso bloqueado utiliza el subproceso en segundo plano de supervisión de interbloqueos para desplazarse por la lista de tareas a la espera de un tiempo superior al del umbral configurado o múltiplo de ese tiempo.</span><span class="sxs-lookup"><span data-stu-id="c5125-109">Blocked process threshold uses the deadlock monitor background thread to walk through the list of tasks waiting for a time greater than or multiples of the configured threshold.</span></span> <span data-ttu-id="c5125-110">El evento se genera una vez por intervalo de informe para cada tarea bloqueada.</span><span class="sxs-lookup"><span data-stu-id="c5125-110">The event is generated once per reporting interval for each of the blocked tasks.</span></span>  
  
 <span data-ttu-id="c5125-111">El informe de procesos bloqueados se realiza de la mejor forma posible.</span><span class="sxs-lookup"><span data-stu-id="c5125-111">The blocked process report is done on a best effort basis.</span></span> <span data-ttu-id="c5125-112">No existe ninguna garantía de que los informes generados muestren resultados en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="c5125-112">There is no guarantee of any real-time or even close to real-time reporting.</span></span>  
  
 <span data-ttu-id="c5125-113">La configuración surte efecto inmediatamente, sin necesidad de detener y reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="c5125-113">The setting takes effect immediately without a server stop and restart.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c5125-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c5125-114">Examples</span></span>  
 <span data-ttu-id="c5125-115">El siguiente ejemplo establece `blocked process threshold` en `20` segundos y genera un informe de proceso bloqueado para cada tarea bloqueada.</span><span class="sxs-lookup"><span data-stu-id="c5125-115">The following example sets the `blocked process threshold` to `20` seconds, generating a blocked process report for each task that is blocked.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 20 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5125-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5125-116">See Also</span></span>  
 <span data-ttu-id="c5125-117">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5125-117">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="c5125-118">Blocked Process Report (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="c5125-118">Blocked Process Report Event Class</span></span>](../../relational-databases/event-classes/blocked-process-report-event-class.md)  
  
  
