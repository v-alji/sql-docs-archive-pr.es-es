---
title: Monitor de actividad | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server]
ms.assetid: 1e6c430d-3a2a-468e-a3d5-ef5459c36c15
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 71fd0d1172b4fcd5739a3af1a60246cc7dce3b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749249"
---
# <a name="activity-monitor"></a><span data-ttu-id="6800b-102">Monitor de actividad</span><span class="sxs-lookup"><span data-stu-id="6800b-102">Activity Monitor</span></span>
  <span data-ttu-id="6800b-103">El Monitor de actividad muestra información acerca de los procesos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el modo en que estos afectan a la instancia actual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6800b-103">Activity Monitor displays information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="benefits-of-activity-monitor"></a><span data-ttu-id="6800b-104">Ventajas del Monitor de actividad</span><span class="sxs-lookup"><span data-stu-id="6800b-104">Benefits of Activity Monitor</span></span>  
 <span data-ttu-id="6800b-105">El monitor de actividad es una ventana de documento con pestañas que tiene los siguientes paneles que se pueden expandir y contraer: **información general**, **tareas de usuario activas**, **esperas de recursos**, **e/s de archivos de datos**y **consultas costosas recientes**.</span><span class="sxs-lookup"><span data-stu-id="6800b-105">Activity Monitor is a tabbed document window that has the following expandable and collapsible panes: **Overview**, **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries**.</span></span> <span data-ttu-id="6800b-106">Cuando un panel está expandido, el Monitor de actividad consulta la instancia en busca de información.</span><span class="sxs-lookup"><span data-stu-id="6800b-106">When any pane is expanded, Activity Monitor queries the instance for information.</span></span> <span data-ttu-id="6800b-107">Si el panel está contraído, cualquier actividad de consulta se detiene en ese panel.</span><span class="sxs-lookup"><span data-stu-id="6800b-107">When a pane is collapsed, all querying activity stops for that pane.</span></span> <span data-ttu-id="6800b-108">Se pueden expandir uno o varios paneles al mismo tiempo para ver diferentes tipos de actividad de la instancia.</span><span class="sxs-lookup"><span data-stu-id="6800b-108">You can also expand one or more panes at the same time to view different kinds of activity on the instance.</span></span>  
  
 <span data-ttu-id="6800b-109">En el caso de las columnas incluidas en los paneles **tareas de usuario activas**, **esperas de recursos**, **e/s de archivos de datos**y **consultas costosas recientes** , puede personalizar la presentación de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="6800b-109">For the columns that are included in the **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries** panes, you can customize the display in the following ways:</span></span>  
  
1.  <span data-ttu-id="6800b-110">Para reorganizar el orden de las columnas, haga clic en el encabezado de una columna y arrástrelo hasta otra ubicación de la cinta de opciones del encabezado.</span><span class="sxs-lookup"><span data-stu-id="6800b-110">To rearrange the order of the columns, click the column heading and drag it to another location in the heading ribbon.</span></span>  
  
2.  <span data-ttu-id="6800b-111">Para ordenar una columna, haga clic en el nombre de la columna.</span><span class="sxs-lookup"><span data-stu-id="6800b-111">To sort a column, click the column name.</span></span>  
  
3.  <span data-ttu-id="6800b-112">Para filtrar por una o varias columnas, haga clic en la flecha de lista desplegable del encabezado de columna y, a continuación, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6800b-112">To filter on one or more columns, click the drop-down arrow in the column heading, and then select a value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6800b-113">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6800b-113">Related Tasks</span></span>  
 <span data-ttu-id="6800b-114">Use las siguientes tareas para empezar a trabajar con el Monitor de actividad:</span><span class="sxs-lookup"><span data-stu-id="6800b-114">Use the following tasks to get started with Activity Monitor:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6800b-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6800b-115">**Description**</span></span>|<span data-ttu-id="6800b-116">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="6800b-116">**Topic**</span></span>|  
|<span data-ttu-id="6800b-117">Describe cómo abrir el Monitor de actividad y la forma en que se establece el intervalo de actualización del Monitor de actividad.</span><span class="sxs-lookup"><span data-stu-id="6800b-117">Describes how to open Activity Monitor and how to set the Activity Monitor refresh interval.</span></span>|[<span data-ttu-id="6800b-118">Abrir el Monitor de actividad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6800b-118">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)|  
|<span data-ttu-id="6800b-119">Vínculos a temas de supervisión de la actividad y el rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="6800b-119">Links to topics for server performance and activity monitoring.</span></span>|[<span data-ttu-id="6800b-120">Supervisión de la actividad y rendimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="6800b-120">Server Performance and Activity Monitoring</span></span>](../performance/server-performance-and-activity-monitoring.md)|  
  
  
