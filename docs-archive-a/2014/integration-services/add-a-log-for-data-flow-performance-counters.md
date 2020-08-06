---
title: Agregar un registro para los contadores de rendimiento del flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- performance counters [Integration Services]
- counters [Integration Services]
- logs [Integration Services], data flow counters
ms.assetid: b500d166-33ba-4b82-a92d-b0a333924e8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 489bde1b0e5769f05d1063eb0af2376b659574de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748222"
---
# <a name="add-a-log-for-data-flow-performance-counters"></a><span data-ttu-id="2b902-102">Agregar un registro para los contadores de rendimiento del flujo de datos</span><span class="sxs-lookup"><span data-stu-id="2b902-102">Add a Log for Data Flow Performance Counters</span></span>
  <span data-ttu-id="2b902-103">Este procedimiento describe cómo agregar un registro para los contadores de rendimiento que proporciona el motor de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="2b902-103">This procedure describes how to add a log for the performance counters that the data flow engine provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b902-104">Si instala [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en un equipo que está ejecutando [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)]y, a continuación, actualiza el equipo a [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], el proceso de actualización quita del equipo los contadores de rendimiento de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b902-104">If you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] on a computer that is running [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)], and then upgrade that computer to [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], the upgrade process removes the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters from the computer.</span></span> <span data-ttu-id="2b902-105">Para restaurar en el equipo los contadores de rendimiento de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , ejecute el programa de instalación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en modo de reparación.</span><span class="sxs-lookup"><span data-stu-id="2b902-105">To restore the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters on the computer, run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup in repair mode.</span></span>  
  
### <a name="to-add-logging-of-performance-counters"></a><span data-ttu-id="2b902-106">Para agregar un registro de contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="2b902-106">To add logging of performance counters</span></span>  
  
1.  <span data-ttu-id="2b902-107">En el **Panel de control**, si utiliza la Vista clásica, haga clic en **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="2b902-107">In **Control Panel**, if you are using Classic view, click **Administrative Tools**.</span></span> <span data-ttu-id="2b902-108">Si utiliza la Vista por categorías, haga clic en **Rendimiento y mantenimiento** y, a continuación, en **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="2b902-108">If you are using Category view, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="2b902-109">Haga clic en **Rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="2b902-109">Click **Performance**.</span></span>  
  
3.  <span data-ttu-id="2b902-110">En el cuadro de diálogo **Rendimiento** , expanda **Registros y alertas de rendimiento**, haga clic con el botón derecho en **Registros de contador**y, después, haga clic en **Nueva configuración de registro**.</span><span class="sxs-lookup"><span data-stu-id="2b902-110">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span> <span data-ttu-id="2b902-111">Escriba el nombre del registro.</span><span class="sxs-lookup"><span data-stu-id="2b902-111">Type the name of the log.</span></span> <span data-ttu-id="2b902-112">Por ejemplo, escriba **miRegistro**.</span><span class="sxs-lookup"><span data-stu-id="2b902-112">For example, type **MyLog**.</span></span>  
  
4.  <span data-ttu-id="2b902-113">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b902-113">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="2b902-114">En el cuadro de diálogo **miRegistro** , haga clic en **Agregar contadores**.</span><span class="sxs-lookup"><span data-stu-id="2b902-114">In the **MyLog** dialog box, click **Add Counters**.</span></span>  
  
6.  <span data-ttu-id="2b902-115">Haga clic en **Usar contadores del equipo local** para registrar los contadores de rendimiento en el equipo local o bien, haga clic en **Seleccionar contadores del equipo** y seleccione un equipo de la lista para registrar los contadores de rendimiento en el equipo especificado.</span><span class="sxs-lookup"><span data-stu-id="2b902-115">Click **Use local computer counters** to log performance counters on the local computer, or click **Select counters from computer** and then select a computer from the list to log performance counters on the specified computer.</span></span>  
  
7.  <span data-ttu-id="2b902-116">En el cuadro de diálogo **Agregar contadores** , seleccione **SQL Server:SSIS Pipeline** en la lista **Objeto de rendimiento** .</span><span class="sxs-lookup"><span data-stu-id="2b902-116">In the **Add Counters** dialog box, select **SQL Server:SSIS Pipeline** in the **Performance object** list.</span></span>  
  
8.  <span data-ttu-id="2b902-117">Para seleccionar los contadores de rendimiento, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="2b902-117">To select performance counters, do one of the following:</span></span>  
  
    -   <span data-ttu-id="2b902-118">Seleccione **Todos los contadores** para registrar todos los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2b902-118">Select **All Counters** to log all performance counters.</span></span>  
  
    -   <span data-ttu-id="2b902-119">Elija **Seleccionar contadores de la lista** y seleccione los contadores de rendimiento que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="2b902-119">Select **Select counters in list** and select the performance counters to use.</span></span>  
  
9. <span data-ttu-id="2b902-120">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2b902-120">Click **Add**.</span></span>  
  
10. <span data-ttu-id="2b902-121">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2b902-121">Click **Close**.</span></span>  
  
11. <span data-ttu-id="2b902-122">En el cuadro de diálogo **miRegistro** , revise la lista de contadores de rendimiento del registro en la lista **Contadores** .</span><span class="sxs-lookup"><span data-stu-id="2b902-122">In the **MyLog** dialog box, review the list of logging performance counters in the **Counters** list.</span></span>  
  
12. <span data-ttu-id="2b902-123">Para agregar más contadores, repita los pasos 5 a 10.</span><span class="sxs-lookup"><span data-stu-id="2b902-123">To add additional counters, repeat steps 5 through 10.</span></span>  
  
13. <span data-ttu-id="2b902-124">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b902-124">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2b902-125">Debe iniciar el servicio Registros y alertas de rendimiento con una cuenta local o de dominio que sea miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="2b902-125">You must start the Performance Logs and Alerts service using a local account or a domain account that is a member of the Administrators group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b902-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b902-126">See Also</span></span>  
 <span data-ttu-id="2b902-127">[Contadores de rendimiento](performance/performance-counters.md) </span><span class="sxs-lookup"><span data-stu-id="2b902-127">[Performance Counters](performance/performance-counters.md) </span></span>  
 [<span data-ttu-id="2b902-128">Ver entradas del registro en la ventana Registrar eventos</span><span class="sxs-lookup"><span data-stu-id="2b902-128">View Log Entries in the Log Events Window</span></span>](../../2014/integration-services/view-log-entries-in-the-log-events-window.md)  
  
  
