---
title: Creación de una alerta de base de datos de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database performance [SQL Server], alerts
- alerts [SQL Server], creating
- thresholds [SQL Server]
- database alerts [SQL Server]
- tuning databases [SQL Server], alerts
- monitoring performance [SQL Server], alerts
- monitoring server performance [SQL Server], alerts
- database monitoring [SQL Server], alerts
- server performance [SQL Server], alerts
ms.assetid: 0511136a-1b6b-4095-aa45-39e77b67aba2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fd0cc926412d64f7686744ee60840a32473d2386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749248"
---
# <a name="create-a-sql-server-database-alert"></a><span data-ttu-id="ae8d2-102">Crear una alerta de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae8d2-102">Create a SQL Server Database Alert</span></span>
  <span data-ttu-id="ae8d2-103">El Monitor del sistema permite crear una alerta que se activará al alcanzar un valor de umbral de un contador del Monitor del sistema.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-103">You can use System Monitor to create an alert that is raised when a threshold value for a System Monitor counter has been reached.</span></span> <span data-ttu-id="ae8d2-104">Como respuesta a la alerta, el Monitor del sistema puede iniciar una aplicación, como por ejemplo una aplicación personalizada creada para tratar la condición de alerta.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-104">In response to the alert, System Monitor launches an application, such as a custom application written to handle the alert condition.</span></span> <span data-ttu-id="ae8d2-105">Por ejemplo, puede crear una alerta que se active cuando el número de interbloqueos sea superior a un valor específico.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-105">For example, you could create an alert that is raised when the number of deadlocks exceeds a specific value.</span></span>  
  
 <span data-ttu-id="ae8d2-106">También se pueden definir alertas mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae8d2-106">Alerts also can be defined by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="ae8d2-107">Para más información, consulte [Alertas](../../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="ae8d2-107">For more information, see [Alerts](../../ssms/agent/alerts.md).</span></span>  
  
 <span data-ttu-id="ae8d2-108">Para obtener más información sobre cómo usar el Monitor del sistema para configurar una alerta de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Configurar una alerta de base de datos de SQL Server &#40;Windows&#41;](../performance/set-up-a-sql-server-database-alert-windows.md).</span><span class="sxs-lookup"><span data-stu-id="ae8d2-108">For more information about using System Monitor to set up a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database alert, see [Set Up a SQL Server Database Alert &#40;Windows&#41;](../performance/set-up-a-sql-server-database-alert-windows.md) .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8d2-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae8d2-109">See Also</span></span>  
 <span data-ttu-id="ae8d2-110">[sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ae8d2-110">[sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql) </span></span>  
 [<span data-ttu-id="ae8d2-111">sys.sysperfinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae8d2-111">sys.sysperfinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysperfinfo-transact-sql)  
  
  
