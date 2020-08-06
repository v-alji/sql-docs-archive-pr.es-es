---
title: Difundir un mensaje de cierre del sistema (símbolo del sistema) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, stopping
- named instances [SQL Server], broadcasting shutdown messages
- shutdown message broadcast
- broadcasting shutdown message
- command prompt [SQL Server], broadcasting shutdown messages
- default instances [SQL Server], broadcasting shutdown messages
- stopping SQL Server
ms.assetid: 9f20ccd5-d952-431d-ba12-339911af9430
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 540baada4a78d7b5caf54cbabb9196ce5a79780e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746522"
---
# <a name="broadcast-a-shutdown-message-command-prompt"></a><span data-ttu-id="0716d-102">Difundir un mensaje de cierre del sistema (símbolo del sistema)</span><span class="sxs-lookup"><span data-stu-id="0716d-102">Broadcast a Shutdown Message (Command Prompt)</span></span>
  <span data-ttu-id="0716d-103">En este tema se describe cómo difundir un mensaje de cierre en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante el comando **net send** .</span><span class="sxs-lookup"><span data-stu-id="0716d-103">This topic describes how to broadcast a shutdown message in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using the **net send** command.</span></span> <span data-ttu-id="0716d-104">En el mensaje, incluya la hora a la que se va a detener la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que los usuarios puedan finalizar sus tareas.</span><span class="sxs-lookup"><span data-stu-id="0716d-104">In the message, include the time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be stopped so that users can finish their tasks.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-broadcast-a-shutdown-message"></a><span data-ttu-id="0716d-105">Para difundir un mensaje de cierre</span><span class="sxs-lookup"><span data-stu-id="0716d-105">To broadcast a shutdown message</span></span>  
  
1.  <span data-ttu-id="0716d-106">Desde el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="0716d-106">From a command prompt, enter:</span></span>  
  
     <span data-ttu-id="0716d-107">**net send /users "message"**</span><span class="sxs-lookup"><span data-stu-id="0716d-107">**net send /users "message"**</span></span>  
  
     <span data-ttu-id="0716d-108">La opción **/users** especifica que el mensaje se enviará a todos los usuarios conectados al servidor</span><span class="sxs-lookup"><span data-stu-id="0716d-108">The **/users** option specifies that the message be sent to all users connected to the server</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0716d-109">El comando **net send** requiere que se esté ejecutando el servicio de mensajería tanto en el equipo emisor como en el receptor.</span><span class="sxs-lookup"><span data-stu-id="0716d-109">The **net send** command requires the messenger service to be running on both the sending and the receiving computers.</span></span> <span data-ttu-id="0716d-110">El servicio de mensajería se deshabilita de forma predeterminada en Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="0716d-110">The messenger service is disabled by default on Windows Server 2003.</span></span> <span data-ttu-id="0716d-111">Para obtener información sobre **net send**, vea la documentación de Windows.</span><span class="sxs-lookup"><span data-stu-id="0716d-111">For information about **net send**, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="0716d-112">Es posible que en su red sea más conveniente ponerse en contacto con los usuarios por correo electrónico o teléfono.</span><span class="sxs-lookup"><span data-stu-id="0716d-112">On your network, it may be more appropriate to contact users by e-mail or the telephone.</span></span> <span data-ttu-id="0716d-113">Para determinar qué usuarios están conectados actualmente a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], utilice el Monitor de actividad.</span><span class="sxs-lookup"><span data-stu-id="0716d-113">To determine which users are currently connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the Activity Monitor.</span></span> <span data-ttu-id="0716d-114">Para obtener información sobre el Monitor de actividad, vea [Monitor de actividad](../../relational-databases/performance-monitor/activity-monitor.md) y [Abrir el Monitor de actividad &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="0716d-114">For information on the Activity Monitor, see [Activity Monitor](../../relational-databases/performance-monitor/activity-monitor.md) and [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0716d-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0716d-115">See Also</span></span>  
 [<span data-ttu-id="0716d-116">Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="0716d-116">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
