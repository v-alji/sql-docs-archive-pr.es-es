---
title: Propiedades de Agente SQL Server (página Avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.advanced.f1
ms.assetid: a4d798ee-4c18-40d4-b6af-63d17503738c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8ec0d9d7fbd51f9350bf692588f90c292e54f4e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676308"
---
# <a name="sql-server-agent-properties-advanced-page"></a><span data-ttu-id="d4dab-102">Propiedades de Agente SQL Server (página Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="d4dab-102">SQL Server Agent Properties (Advanced Page)</span></span>
  <span data-ttu-id="d4dab-103">Utilice esta página para ver y modificar las propiedades avanzadas del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servicio del agente.</span><span class="sxs-lookup"><span data-stu-id="d4dab-103">Use this page to view and modify advanced properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d4dab-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="d4dab-104">Options</span></span>  
 <span data-ttu-id="d4dab-105">**Reenvío de eventos de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d4dab-105">**SQL Server event forwarding**</span></span>  
 <span data-ttu-id="d4dab-106">Las opciones de esta categoría activan y configuran el reenvío de eventos.</span><span class="sxs-lookup"><span data-stu-id="d4dab-106">The options in this category activate and configure event forwarding.</span></span>  
  
 <span data-ttu-id="d4dab-107">**Reenviar eventos a otro servidor**</span><span class="sxs-lookup"><span data-stu-id="d4dab-107">**Forward events to a different server**</span></span>  
 <span data-ttu-id="d4dab-108">Reenvía los eventos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="d4dab-108">Forwards [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events to a different server.</span></span>  
  
 <span data-ttu-id="d4dab-109">**Server**</span><span class="sxs-lookup"><span data-stu-id="d4dab-109">**Server**</span></span>  
 <span data-ttu-id="d4dab-110">Seleccione el nombre del servidor al que se reenvían los eventos.</span><span class="sxs-lookup"><span data-stu-id="d4dab-110">Select the name of the server to forward events to.</span></span>  
  
 <span data-ttu-id="d4dab-111">**Eventos no controlados**</span><span class="sxs-lookup"><span data-stu-id="d4dab-111">**Unhandled events**</span></span>  
 <span data-ttu-id="d4dab-112">Solo reenvía eventos no controlados al servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="d4dab-112">Forwards only unhandled events to the specified server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d4dab-113">solo reenvía eventos a los que no responde ninguna alerta.</span><span class="sxs-lookup"><span data-stu-id="d4dab-113">Agent forwards only events that no alert responds to.</span></span>  
  
 <span data-ttu-id="d4dab-114">**Todos los eventos**</span><span class="sxs-lookup"><span data-stu-id="d4dab-114">**All events**</span></span>  
 <span data-ttu-id="d4dab-115">Reenvía todos los eventos.</span><span class="sxs-lookup"><span data-stu-id="d4dab-115">Forwards all events.</span></span> <span data-ttu-id="d4dab-116">Cuando una alerta de la instancia local responde al evento, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reenvía el evento y procesa la alerta.</span><span class="sxs-lookup"><span data-stu-id="d4dab-116">When an alert in the local instance responds to the event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent will both forward the event and process the alert.</span></span>  
  
 <span data-ttu-id="d4dab-117">**Si el evento tiene una gravedad de o por encima de**</span><span class="sxs-lookup"><span data-stu-id="d4dab-117">**If event has severity at or above**</span></span>  
 <span data-ttu-id="d4dab-118">Solo reenvía eventos con el nivel de gravedad igual o superior al especificado.</span><span class="sxs-lookup"><span data-stu-id="d4dab-118">Forwards only events with a severity level at or above the level specified.</span></span>  
  
 <span data-ttu-id="d4dab-119">**Condición de CPU inactiva**</span><span class="sxs-lookup"><span data-stu-id="d4dab-119">**Idle CPU Condition**</span></span>  
 <span data-ttu-id="d4dab-120">Las opciones de esta categoría definen las condiciones en las que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ejecuta trabajos programados para ejecutarse en la programación de CPU inactiva.</span><span class="sxs-lookup"><span data-stu-id="d4dab-120">The options in this category define the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs scheduled to run on the Idle CPU schedule.</span></span>  
  
 <span data-ttu-id="d4dab-121">**Definir condición de CPU inactiva**</span><span class="sxs-lookup"><span data-stu-id="d4dab-121">**Define idle CPU condition**</span></span>  
 <span data-ttu-id="d4dab-122">Define las condiciones en las que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] considera que la CPU está inactiva.</span><span class="sxs-lookup"><span data-stu-id="d4dab-122">Defines the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent considers the CPU to be idle.</span></span>  
  
 <span data-ttu-id="d4dab-123">**El promedio de uso de la CPU baja de**</span><span class="sxs-lookup"><span data-stu-id="d4dab-123">**Average CPU usage falls below**</span></span>  
 <span data-ttu-id="d4dab-124">Porcentaje de uso de CPU por debajo del cual se considera inactiva la CPU.</span><span class="sxs-lookup"><span data-stu-id="d4dab-124">Percentage of CPU usage below which the CPU is considered to be idle.</span></span>  
  
 <span data-ttu-id="d4dab-125">**Y permanece por debajo durante**</span><span class="sxs-lookup"><span data-stu-id="d4dab-125">**And remains below this level for**</span></span>  
 <span data-ttu-id="d4dab-126">Cantidad de tiempo que el promedio de uso de la CPU debe situarse por debajo del nivel especificado antes de que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ejecute trabajos en la programación de CPU inactiva.</span><span class="sxs-lookup"><span data-stu-id="d4dab-126">Amount of time that the average CPU must below the level specified before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs on the Idle CPU schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4dab-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4dab-127">See Also</span></span>  
 <span data-ttu-id="d4dab-128">[Crear y adjuntar programaciones a trabajos](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="d4dab-128">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 [<span data-ttu-id="d4dab-129">Administrar eventos</span><span class="sxs-lookup"><span data-stu-id="d4dab-129">Manage Events</span></span>](manage-events.md)  
  
  
