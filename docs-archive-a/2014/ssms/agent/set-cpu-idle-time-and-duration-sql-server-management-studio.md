---
title: Establecer la duración y el tiempo de inactividad de la CPU (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CPU [SQL Server], idle conditions
- time [SQL Server], CPU idle and duration
- duration of CPU idle [SQL Server]
- SQL Server Agent, CPU idle conditions
- idle time [SQL Server]
ms.assetid: 8647b465-d899-4cc7-9640-134a506d0a2e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1660f6d70977b8f590a18adf952a6a19f32a26cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751634"
---
# <a name="set-cpu-idle-time-and-duration-sql-server-management-studio"></a><span data-ttu-id="a2531-102">Establecer la duración y el tiempo de inactividad de la CPU (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a2531-102">Set CPU Idle Time and Duration (SQL Server Management Studio)</span></span>
  <span data-ttu-id="a2531-103">En este tema se explica cómo definir la condición de inactividad de la CPU para el servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2531-103">This topic explains how to define the CPU idle condition for your server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a2531-104">La definición de inactividad de CPU influye en cómo el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente responde a los eventos.</span><span class="sxs-lookup"><span data-stu-id="a2531-104">The CPU idle definition influences how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent responds to events.</span></span> <span data-ttu-id="a2531-105">Por ejemplo, supongamos que define la condición de inactividad de la CPU como el momento en que el uso de la CPU se sitúa por debajo del 10% y permanece en este nivel durante 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="a2531-105">For example, suppose that you define the CPU idle condition as when the average CPU usage falls below 10 percent and remains at this level for 10 minutes.</span></span> <span data-ttu-id="a2531-106">En este caso, si ha definido trabajos que deben ejecutarse cuando la CPU del servidor alcance una condición de inactividad, estos trabajos se iniciarán cuando el uso de la CPU se sitúe por debajo del 10% y permanezca en este nivel durante 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="a2531-106">Then if you have defined jobs to execute whenever the server CPU reaches an idle condition, the job will start when the CPU usage falls below 10 percent and remains at that level for 10 minutes.</span></span> <span data-ttu-id="a2531-107">Si se trata de un trabajo que tiene consecuencias importantes sobre el rendimiento del servidor, es importante la forma en que define la condición de inactividad de la CPU.</span><span class="sxs-lookup"><span data-stu-id="a2531-107">If this is a job that significantly impacts the performance of your server, how you define the CPU idle condition is important.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a2531-108">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a2531-108">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-cpu-idle-time-and-duration"></a><span data-ttu-id="a2531-109">Para establecer la duración y el tiempo de inactividad de la CPU</span><span class="sxs-lookup"><span data-stu-id="a2531-109">To set CPU idle time and duration</span></span>  
  
1.  <span data-ttu-id="a2531-110">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="a2531-110">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a2531-111">Haga clic con el botón derecho en el **Agente SQL Server**, haga clic en **Propiedades**y seleccione la página **Avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="a2531-111">Right-click **SQL Server Agent**, click **Properties**, and select the **Advanced** page.</span></span>  
  
3.  <span data-ttu-id="a2531-112">En **Condición de CPU inactiva**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2531-112">Under **Idle CPU condition**, do the following:</span></span>  
  
    -   <span data-ttu-id="a2531-113">Active la opción **Definir condición de CPU inactiva**.</span><span class="sxs-lookup"><span data-stu-id="a2531-113">Check **Define idle CPU condition.**</span></span>  
  
    -   <span data-ttu-id="a2531-114">Especifique un porcentaje para el cuadro **El promedio de uso de la CPU baja de** (para todas las CPU).</span><span class="sxs-lookup"><span data-stu-id="a2531-114">Specify a percentage for the **Average CPU usage falls below** (across all CPUs) box.</span></span> <span data-ttu-id="a2531-115">Esto establece el nivel de uso por debajo del cual debe situarse la CPU para que se considere inactiva.</span><span class="sxs-lookup"><span data-stu-id="a2531-115">This sets the usage level that the CPU must fall below before it is considered idle.</span></span>  
  
    -   <span data-ttu-id="a2531-116">Especifique un número de segundos para el cuadro **Y permanece por debajo durante** .</span><span class="sxs-lookup"><span data-stu-id="a2531-116">Specify a number of seconds for the **And remains below this level for** box.</span></span> <span data-ttu-id="a2531-117">Esto establece la duración del uso mínimo de la CPU para que ésta se considere inactiva.</span><span class="sxs-lookup"><span data-stu-id="a2531-117">This sets the duration that the minimum CPU usage must remain at before it is considered idle.</span></span>  
  
  
