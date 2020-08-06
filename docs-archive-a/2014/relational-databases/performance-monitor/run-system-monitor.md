---
title: Ejecutar Monitor de sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], running
- Windows System Monitor [SQL Server], running
- remote procedure calls [SQL Server]
- starting Windows NT System Monitor
- RPC
ms.assetid: 05297984-bc8d-43df-829c-032387f7ea61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dd0baf32402d69e36dc5120d0259b2f8d689897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749237"
---
# <a name="run-system-monitor"></a><span data-ttu-id="143b4-102">Ejecutar Monitor de sistema</span><span class="sxs-lookup"><span data-stu-id="143b4-102">Run System Monitor</span></span>
  <span data-ttu-id="143b4-103">El Monitor del sistema utiliza llamadas a procedimiento remoto (RPC) para recopilar información de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="143b4-103">System Monitor uses remote procedure calls (RPCs) to collect information from Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="143b4-104">Cualquier usuario que disponga de permisos de Microsoft Windows para ejecutar el Monitor del sistema puede utilizarlo para supervisar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="143b4-104">Any user who has Microsoft Windows permissions to run System Monitor can use System Monitor to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="143b4-105">Cuando utilice el Monitor del sistema o el Monitor de rendimiento, no podrá conectarse a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecute en Windows 98.</span><span class="sxs-lookup"><span data-stu-id="143b4-105">When using System Monitor or Performance Monitor, you cannot connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on Windows 98.</span></span>  
  
 <span data-ttu-id="143b4-106">Al igual que con todas las herramientas para la supervisión del rendimiento, es normal que se produzca una disminución del rendimiento al supervisar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]con el Monitor del sistema.</span><span class="sxs-lookup"><span data-stu-id="143b4-106">As with all performance monitoring tools, expect some performance overhead when you use System Monitor to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="143b4-107">La sobrecarga real en una instancia específica dependerá de la plataforma de hardware, el número de contadores y el intervalo de actualización seleccionado.</span><span class="sxs-lookup"><span data-stu-id="143b4-107">The actual overhead in any specific instance depends on the hardware platform, the number of counters, and the selected update interval.</span></span> <span data-ttu-id="143b4-108">No obstante, la integración del Monitor del sistema con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está diseñada para que la disminución del rendimiento sea la mínima.</span><span class="sxs-lookup"><span data-stu-id="143b4-108">However, the integration of System Monitor with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is designed to minimize any reduction in performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="143b4-109">Si ha seleccionado los contadores de rendimiento de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la supervisión en el complemento Monitor del sistema, los contadores estarán presentes aunque no se ejecute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="143b4-109">If you have selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performance counters to monitor in the System Monitor snap-in, you will see the counters even if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running.</span></span>  
  
 <span data-ttu-id="143b4-110">Para obtener información sobre cómo iniciar el Monitor del sistema, vea [Iniciar el Monitor de sistema &#40;Windows&#41;](../performance/start-system-monitor-windows.md).</span><span class="sxs-lookup"><span data-stu-id="143b4-110">For information about starting System Monitor, see [Start System Monitor &#40;Windows&#41;](../performance/start-system-monitor-windows.md).</span></span>  
  
  
