---
title: Configurar una alerta de base de datos de SQL Server (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
ms.assetid: 65d2c5c1-921f-4eff-9ef7-149170ab61e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 090eeda2c134857df18d083ce06d460214aa4dfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677599"
---
# <a name="set-up-a-sql-server-database-alert-windows"></a><span data-ttu-id="5bb90-102">Configurar una alerta de base de datos (Windows)</span><span class="sxs-lookup"><span data-stu-id="5bb90-102">Set Up a SQL Server Database Alert (Windows)</span></span>
  <span data-ttu-id="5bb90-103">Mediante el Monitor de sistema, puede crear una alerta que se active cuando se alcance un valor de umbral de un contador del Monitor de sistema.</span><span class="sxs-lookup"><span data-stu-id="5bb90-103">Using System Monitor, you can create an alert to be raised when a threshold value for a System Monitor counter has been reached.</span></span> <span data-ttu-id="5bb90-104">Como respuesta a la alerta, el Monitor del sistema puede iniciar una aplicación, como, por ejemplo, una aplicación personalizada creada para tratar la condición de alerta.</span><span class="sxs-lookup"><span data-stu-id="5bb90-104">In response to the alert, System Monitor can launch an application, such as a custom application written to handle the alert condition.</span></span> <span data-ttu-id="5bb90-105">Por ejemplo, puede crear una alerta que se active cuando el número de interbloqueos sea superior a un valor específico.</span><span class="sxs-lookup"><span data-stu-id="5bb90-105">For example, you can create an alert that is raised when the number of deadlocks exceeds a specific value.</span></span>  
  
 <span data-ttu-id="5bb90-106">También se pueden definir alertas mediante Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bb90-106">Alerts also can be defined using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="5bb90-107">Para más información, consulte [Alertas](../../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="5bb90-107">For more information, see [Alerts](../../ssms/agent/alerts.md).</span></span>  
  
### <a name="to-set-up-a-sql-server-database-alert"></a><span data-ttu-id="5bb90-108">Para configurar una alerta de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5bb90-108">To set up a SQL Server database alert</span></span>  
  
1.  <span data-ttu-id="5bb90-109">En el árbol de navegación de la ventana Rendimiento, expanda **Registros y alertas de rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="5bb90-109">On the navigation tree of the Performance window, expand **Performance Logs and Alerts**.</span></span>  
  
2.  <span data-ttu-id="5bb90-110">Haga clic con el botón derecho en **Alertas**y, después, haga clic en **Nueva configuración de alerta**.</span><span class="sxs-lookup"><span data-stu-id="5bb90-110">Right-click **Alerts**, and then click **New Alert Settings**.</span></span>  
  
3.  <span data-ttu-id="5bb90-111">En el cuadro de diálogo **Nueva configuración de alerta** , escriba el nombre de la nueva alerta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5bb90-111">In the **New Alert Settings** dialog box, type a name for the new alert, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="5bb90-112">En la pestaña **General** del cuadro de diálogo de la nueva alerta, agregue un **Comentario**y haga clic en **Agregar** para agregar un contador a la alerta.</span><span class="sxs-lookup"><span data-stu-id="5bb90-112">On the **General** tab of the dialog box for the new alert, add a **Comment**, and click **Add** to add a counter to the alert.</span></span>  
  
     <span data-ttu-id="5bb90-113">Todas las alertas deben tener, como mínimo, un contador.</span><span class="sxs-lookup"><span data-stu-id="5bb90-113">All alerts must have at least one counter.</span></span>  
  
5.  <span data-ttu-id="5bb90-114">En el cuadro de diálogo Agregar contadores, seleccione un objeto de SQL Server de la lista **Objeto de rendimiento** y, a continuación, seleccione un contador en **Seleccionar contadores de la lista**.</span><span class="sxs-lookup"><span data-stu-id="5bb90-114">In the Add Counters dialog box, select a SQL Server object from the **Performance Object** list, and then select a counter from the **Select counters from list**.</span></span>  
  
6.  <span data-ttu-id="5bb90-115">Para agregar el contador a la alerta, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5bb90-115">To add the counter to the alert, click **Add**.</span></span> <span data-ttu-id="5bb90-116">Puede continuar agregando contadores o hacer clic en **Cerrar** para volver al cuadro de diálogo de la nueva alerta.</span><span class="sxs-lookup"><span data-stu-id="5bb90-116">You can continue to add counters, or you can click **Close** to return to the dialog box for the new alert.</span></span>  
  
7.  <span data-ttu-id="5bb90-117">En el cuadro de diálogo de la nueva alerta, haga clic en **Superio a** o **Inferior a**in the **Alertar cuando el valor sea** y escriba un valor de umbral en **Límite**.</span><span class="sxs-lookup"><span data-stu-id="5bb90-117">In the new alert dialog box, click either **Over** or **Under**in the **Alert when the value is** list, and then enter a threshold value in **Limit**.</span></span>  
  
     <span data-ttu-id="5bb90-118">La alerta se genera cuando el valor del contador es superior o inferior al valor de umbral, dependiendo de si ha elegido **Superior a** o **Inferior a**.</span><span class="sxs-lookup"><span data-stu-id="5bb90-118">The alert is generated when the value for the counter is more than or less than the threshold value (depending on whether you clicked **Over** or **Under**).</span></span>  
  
8.  <span data-ttu-id="5bb90-119">En los cuadros **Tomar datos de muestra cada** , establezca la frecuencia de muestreo.</span><span class="sxs-lookup"><span data-stu-id="5bb90-119">In the **Sample data every** boxes, set the sampling frequency.</span></span>  
  
9. <span data-ttu-id="5bb90-120">En la pestaña **Acción** , establezca las acciones que tendrán lugar cada vez que se desencadene la alerta.</span><span class="sxs-lookup"><span data-stu-id="5bb90-120">On the **Action** tab, set actions to occur every time the alert is triggered.</span></span>  
  
10. <span data-ttu-id="5bb90-121">En la pestaña **Programación** , establezca el programa de inicio y fin de detección de alertas.</span><span class="sxs-lookup"><span data-stu-id="5bb90-121">On the **Schedule** tab, set the start and stop schedule for the alert scan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb90-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5bb90-122">See Also</span></span>  
 [<span data-ttu-id="5bb90-123">Crear una alerta de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5bb90-123">Create a SQL Server Database Alert</span></span>](../performance-monitor/create-a-sql-server-database-alert.md)  
  
  
