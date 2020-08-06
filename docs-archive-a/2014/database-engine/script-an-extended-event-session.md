---
title: Generar un script para una sesión de eventos extendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f9fdde-1f13-4292-a4fc-55da826be3b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11adc60ae7c7e0f8b8012d06f56c83874d3708ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671665"
---
# <a name="script-an-extended-event-session"></a><span data-ttu-id="d7631-102">Crear un script para una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="d7631-102">Script an Extended Event Session</span></span>
  <span data-ttu-id="d7631-103">En este tema se describe cómo crear un script para una sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="d7631-103">This topic describes how to script an event session.</span></span> <span data-ttu-id="d7631-104">Puede exportar, modificar o quitar la sesión de eventos, o quitar y crear la sesión de eventos en:</span><span class="sxs-lookup"><span data-stu-id="d7631-104">You can export, alter, or drop the event session, or drop and create the event session to the following:</span></span>  
  
-   <span data-ttu-id="d7631-105">**Nueva ventana del editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="d7631-105">**New Query Editor Window**</span></span>  
  
-   <span data-ttu-id="d7631-106">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="d7631-106">**File**</span></span>  
  
-   <span data-ttu-id="d7631-107">**Portapapeles**</span><span class="sxs-lookup"><span data-stu-id="d7631-107">**Clipboard**</span></span>  
  
-   <span data-ttu-id="d7631-108">**Trabajo del Agente**</span><span class="sxs-lookup"><span data-stu-id="d7631-108">**Agent Job**</span></span>  
  
### <a name="to-script-an-existing-event-session"></a><span data-ttu-id="d7631-109">Para crear un script para una sesión de eventos existente</span><span class="sxs-lookup"><span data-stu-id="d7631-109">To script an existing event session</span></span>  
  
1.  <span data-ttu-id="d7631-110">En el Explorador de objetos, expanda el nodo **Administración** y, a continuación, expanda **Eventos extendidos**.</span><span class="sxs-lookup"><span data-stu-id="d7631-110">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="d7631-111">Haga clic con el botón secundario en la sesión para la que desea crear un script, señale **Incluir sesión como**, señale **CREATE To**y, a continuación, seleccione dónde desea crear un script para la sesión.</span><span class="sxs-lookup"><span data-stu-id="d7631-111">Right-click the session you want to script, point to **Script Session as**, point to **CREATE to**, and then select where you want to script the session.</span></span>  
  
### <a name="to-script-a-new-event-session"></a><span data-ttu-id="d7631-112">Para crear un script para una nueva sesión de eventos</span><span class="sxs-lookup"><span data-stu-id="d7631-112">To script a new event session</span></span>  
  
1.  <span data-ttu-id="d7631-113">En el Explorador de objetos, expanda el nodo **Administración** y, a continuación, expanda **Eventos extendidos**.</span><span class="sxs-lookup"><span data-stu-id="d7631-113">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="d7631-114">Haga clic con el botón secundario en **Sesiones**y, a continuación, haga clic en **Nueva sesión**.</span><span class="sxs-lookup"><span data-stu-id="d7631-114">Right-click **Sessions**, and then click **New Session**.</span></span>  
  
3.  <span data-ttu-id="d7631-115">En la interfaz de usuario **Nueva sesión** , cree la sesión de eventos y, a continuación, seleccione dónde desea crear un script para la sesión de eventos en la lista desplegable **Script** .</span><span class="sxs-lookup"><span data-stu-id="d7631-115">In the **New Session** UI, create the event session, and then select where you want to script the event session from the **Script** drop-down list.</span></span>  
  
### <a name="to-script-a-modified-event-session"></a><span data-ttu-id="d7631-116">Para crear un script para una sesión de eventos modificada</span><span class="sxs-lookup"><span data-stu-id="d7631-116">To script a modified event session</span></span>  
  
1.  <span data-ttu-id="d7631-117">En el Explorador de objetos, expanda el nodo **Administración** y, a continuación, expanda **Eventos extendidos**.</span><span class="sxs-lookup"><span data-stu-id="d7631-117">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="d7631-118">Haga clic con el botón secundario en la sesión que desea modificar y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d7631-118">Right-click the session you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d7631-119">En el cuadro de diálogo **Propiedades de la sesión** , modifique la sesión de eventos y, a continuación, seleccione dónde desea crear un script para la sesión modificada en la lista desplegable **Script** .</span><span class="sxs-lookup"><span data-stu-id="d7631-119">In the **Session Properties** dialog box, modify the event session, and then select where you want to script the modified session from the **Script** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7631-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7631-120">See Also</span></span>  
 [<span data-ttu-id="d7631-121">Eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="d7631-121">Extended Events</span></span>](../relational-databases/extended-events/extended-events.md)  
  
  
