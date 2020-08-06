---
title: Plan de mantenimiento (Servidores) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.server.f1
- sql12.swb.maint.servers.f1
ms.assetid: ac24d1a8-dd2f-4162-b804-c0df1fc1e61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c971edc9b641846068313f47ca410715ec552014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671520"
---
# <a name="maintenance-plan-servers"></a><span data-ttu-id="7c6db-102">Plan de mantenimiento (Servidores)</span><span class="sxs-lookup"><span data-stu-id="7c6db-102">Maintenance Plan (Servers)</span></span>
  <span data-ttu-id="7c6db-103">Use el cuadro de diálogo **Servidores** para seleccionar los servidores donde desea ejecutar el plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="7c6db-103">Use the **Servers** dialog box to select the servers where you want to run the maintenance plan.</span></span>  
  
 <span data-ttu-id="7c6db-104">Para crear un plan de mantenimiento multiservidor debe configurarse un entorno multiservidor que contenga un servidor maestro y uno o varios servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="7c6db-104">A multiserver environment containing one master server and one or more target servers must be configured to create a multiserver maintenance plan.</span></span> <span data-ttu-id="7c6db-105">En los planes de mantenimiento multiservidor, el servidor local debe configurarse como servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="7c6db-105">For multiserver maintenance plans, the local server should be configured as a master server.</span></span> <span data-ttu-id="7c6db-106">En entornos multiservidor, este cuadro de diálogo muestra el servidor maestro **(local)** y todos los servidores de destino correspondientes.</span><span class="sxs-lookup"><span data-stu-id="7c6db-106">In multiserver environments, this dialog box displays the **(local)** master server and all corresponding target servers.</span></span> <span data-ttu-id="7c6db-107">Para el servidor local, se crea un trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c6db-107">One [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created for the local server.</span></span> <span data-ttu-id="7c6db-108">Se habilita o deshabilita dependiendo de si se selecciona el servidor **(local)** .</span><span class="sxs-lookup"><span data-stu-id="7c6db-108">It is enabled or disabled depending on whether you select the **(local)** server.</span></span> <span data-ttu-id="7c6db-109">Si se seleccionan servidores de destino, se crea un trabajo multiservidor y se descarga en cada uno de los servidores de destino seleccionados.</span><span class="sxs-lookup"><span data-stu-id="7c6db-109">If target servers are selected, a multiserver job is created and downloaded to each of the selected target servers.</span></span> <span data-ttu-id="7c6db-110">Si no se seleccionan servidores de destino, el trabajo multiservidor se elimina.</span><span class="sxs-lookup"><span data-stu-id="7c6db-110">If no target servers are selected, the multiserver job is deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c6db-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c6db-111">See Also</span></span>  
 <span data-ttu-id="7c6db-112">[Planes de mantenimiento](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="7c6db-112">[Maintenance Plans](maintenance-plans.md) </span></span>  
 <span data-ttu-id="7c6db-113">[Crear un entorno multiservidor](../../ssms/agent/create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="7c6db-113">[Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="7c6db-114">[Establecer un servidor maestro](../../ssms/agent/make-a-master-server.md) </span><span class="sxs-lookup"><span data-stu-id="7c6db-114">[Make a Master Server](../../ssms/agent/make-a-master-server.md) </span></span>  
 [<span data-ttu-id="7c6db-115">Establecer un servidor de destino</span><span class="sxs-lookup"><span data-stu-id="7c6db-115">Make a Target Server</span></span>](../../ssms/agent/make-a-target-server.md)  
  
  
