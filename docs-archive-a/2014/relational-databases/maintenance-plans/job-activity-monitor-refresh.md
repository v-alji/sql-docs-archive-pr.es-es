---
title: Actualización del Monitor de actividad de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.jobactivitymon.refresh.f1
ms.assetid: 413a368e-fd2b-4e1f-b370-002cdbc85bab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f290825f8a776c954ef802b184f7600aea5dc9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672971"
---
# <a name="job-activity-monitor-refresh"></a><span data-ttu-id="977c2-102">Actualizar el Monitor de actividad de trabajo</span><span class="sxs-lookup"><span data-stu-id="977c2-102">Job Activity Monitor Refresh</span></span>
  <span data-ttu-id="977c2-103">Utilice el cuadro de diálogo **Actualizar configuración** para configurar la frecuencia con la que el Monitor de actividad de trabajo obtiene información nueva sobre la actividad del servidor.</span><span class="sxs-lookup"><span data-stu-id="977c2-103">Use the **Refresh Settings** dialog box to configure how often Job Activity Monitor obtains new information about server activity.</span></span> <span data-ttu-id="977c2-104">El Monitor de actividad debe ejecutar consultas en el servidor supervisado para obtener información sobre la cuadrícula Monitor de actividad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="977c2-104">Job Activity Monitor must run queries on the monitored server to obtain information for the Job Activity Monitor grid.</span></span> <span data-ttu-id="977c2-105">Cuando el intervalo de actualización automática se establece en un valor inferior a 30 segundos, el tiempo usado para ejecutar estas consultas puede afectar al rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="977c2-105">When the auto-refresh interval is set to less than 30 seconds, the time used to run these queries can affect server performance.</span></span>  
  
 <span data-ttu-id="977c2-106">Para abrir este cuadro de diálogo, haga clic en **Ver configuración de actualización**, en la sección **Estado** del Monitor de actividad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="977c2-106">To open this dialog, click **View refresh settings**, in the **Status** section of Job Activity Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="977c2-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="977c2-107">Options</span></span>  
 <span data-ttu-id="977c2-108">**Actualizar automáticamente cada**</span><span class="sxs-lookup"><span data-stu-id="977c2-108">**Auto-refresh every**</span></span>  
 <span data-ttu-id="977c2-109">Realiza comprobaciones para iniciar la actualización automática de la información del Monitor de actividad.</span><span class="sxs-lookup"><span data-stu-id="977c2-109">Check to initiate automatic refreshing of Activity Monitor information.</span></span> <span data-ttu-id="977c2-110">Esta opción está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="977c2-110">This is off by default.</span></span>  
  
 <span data-ttu-id="977c2-111">**segundos**</span><span class="sxs-lookup"><span data-stu-id="977c2-111">**seconds**</span></span>  
 <span data-ttu-id="977c2-112">Número de segundos entre los distintos intentos de actualización automática.</span><span class="sxs-lookup"><span data-stu-id="977c2-112">The number of seconds between auto-refresh attempts.</span></span> <span data-ttu-id="977c2-113">El valor predeterminado es 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="977c2-113">Defaults to 60 seconds.</span></span> <span data-ttu-id="977c2-114">Realiza actualizaciones cada 5 segundos cuando se establece en 5 o en un valor inferior.</span><span class="sxs-lookup"><span data-stu-id="977c2-114">Refreshes every 5 seconds when set to 5 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="977c2-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="977c2-115">See Also</span></span>  
 [<span data-ttu-id="977c2-116">Actividad de trabajos de monitor</span><span class="sxs-lookup"><span data-stu-id="977c2-116">Monitor Job Activity</span></span>](../../ssms/agent/monitor-job-activity.md)  
  
  
