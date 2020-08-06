---
title: Copiar objetos de paquete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- control flow [Integration Services], copying objects
- copying package objects [Integration Services]
- data flow [Integration Services], copying objects
- connection managers [Integration Services], copying
ms.assetid: 99b85e5c-d6bd-4e7c-afe4-51f6ce151c2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3219f0023c9a28ed270adeb6fd2b795e3459c3e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670494"
---
# <a name="copy-package-objects"></a><span data-ttu-id="86577-102">Copiar objetos de paquete</span><span class="sxs-lookup"><span data-stu-id="86577-102">Copy Package Objects</span></span>
  <span data-ttu-id="86577-103">Este tema describe el modo de copiar elementos de flujo de control, elementos de flujo de datos y administradores de conexión dentro de un paquete o entre paquetes.</span><span class="sxs-lookup"><span data-stu-id="86577-103">This topic describes how to copy control flow items, data flow items, and connection managers within a package or between packages.</span></span>  
  
### <a name="to-copy-control-and-data-flow-items"></a><span data-ttu-id="86577-104">Para copiar elementos de flujo de control y de datos</span><span class="sxs-lookup"><span data-stu-id="86577-104">To copy control and data flow items</span></span>  
  
1.  <span data-ttu-id="86577-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene los paquetes con los que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="86577-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the packages that you want work with.</span></span>  
  
2.  <span data-ttu-id="86577-106">En el Explorador de soluciones, haga doble clic en los paquetes entre los que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="86577-106">In Solution Explorer, double-click the packages that you want to copy between.</span></span>  
  
3.  <span data-ttu-id="86577-107">En el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , haga clic en la pestaña del paquete que contiene los elementos que desea copiar y haga clic en la pestaña **Flujo de control**, **Flujo de datos**o **Controladores de eventos** .</span><span class="sxs-lookup"><span data-stu-id="86577-107">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the tab for the package that contains the items to copy and click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="86577-108">Seleccione los elementos del flujo de control o del flujo de datos que desee copiar.</span><span class="sxs-lookup"><span data-stu-id="86577-108">Select the control flow or data flow items to copy.</span></span> <span data-ttu-id="86577-109">Puede seleccionar elementos de a uno por vez presionando la tecla Mayús y haciendo clic en el elemento, o puede seleccionar un grupo de elementos arrastrando el puntero a través de los elementos que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="86577-109">You can either select items one at a time by pressing the Shift key and clicking the item or select items as a group by dragging the pointer across the items you want to select.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="86577-110">Las restricciones de precedencia y rutas de acceso que conectan elementos no se seleccionan automáticamente cuando selecciona los dos elementos que conectan.</span><span class="sxs-lookup"><span data-stu-id="86577-110">The precedence constraints and paths that connect items are not selected automatically when you select the two items that they connect.</span></span> <span data-ttu-id="86577-111">Para copiar un flujo de trabajo ordenado (un segmento del flujo de control o de flujo de datos), asegúrese también de copiar las restricciones de precedencia y las rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="86577-111">To copy an ordered workflow-a segment of control flow or data flow-make sure to also copy the precedence constrains and the paths.</span></span>  
  
5.  <span data-ttu-id="86577-112">Haga clic con el botón derecho en un elemento seleccionado y, después, haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="86577-112">Right-click a selected item and click **Copy**.</span></span>  
  
6.  <span data-ttu-id="86577-113">Si va a copiar elementos a un paquete diferente, haga clic en el paquete al que desea copiar y luego haga clic en la pestaña correspondiente para el tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="86577-113">If copying items to a different package, click the package that you want to copy to, and then click the appropriate tab for the item type.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="86577-114">No puede copiar un flujo de datos a un paquete, a no ser que el paquete contenga al menos una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="86577-114">You cannot copy a data flow to a package unless the package contains at least one Data Flow task.</span></span>  
  
7.  <span data-ttu-id="86577-115">Haga clic con el botón derecho y, luego, haga clic en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="86577-115">Right-click and click **Paste**.</span></span>  
  
### <a name="to-copy-connection-managers"></a><span data-ttu-id="86577-116">Para copiar administradores de conexión</span><span class="sxs-lookup"><span data-stu-id="86577-116">To copy connection managers</span></span>  
  
1.  <span data-ttu-id="86577-117">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="86577-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to work with.</span></span>  
  
2.  <span data-ttu-id="86577-118">En el Explorador de soluciones, haga doble clic en el paquete.</span><span class="sxs-lookup"><span data-stu-id="86577-118">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="86577-119">En el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , haga clic en las pestañas **Flujo de control**, **Flujo de datos**o **Controlador de eventos** .</span><span class="sxs-lookup"><span data-stu-id="86577-119">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
4.  <span data-ttu-id="86577-120">En el área **Administradores de conexiones** , haga clic con el botón derecho en el administrador de conexiones y, luego, haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="86577-120">In the **Connection Managers** area, right-click the connection manager, and then click **Copy**.</span></span> <span data-ttu-id="86577-121">Solo puede copiar un administrador de conexiones cada vez.</span><span class="sxs-lookup"><span data-stu-id="86577-121">You can copy only one connection manager at a time.</span></span>  
  
5.  <span data-ttu-id="86577-122">Si va a copiar elementos a un paquete diferente, haga clic en el paquete que desea copiar y, a continuación, en la pestaña **Flujo de control**, **Flujo de datos**o **Controlador de eventos** .</span><span class="sxs-lookup"><span data-stu-id="86577-122">If you are copying items to a different package, click the package that you want to copy to and then click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
6.  <span data-ttu-id="86577-123">Haga clic con el botón derecho en el área **Administradores de conexiones** y, luego, haga clic en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="86577-123">Right-click in the **Connection Managers** area and click **Paste**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86577-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86577-124">See Also</span></span>  
 <span data-ttu-id="86577-125">[Flujo de control](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="86577-125">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="86577-126">[Flujo de datos](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="86577-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 <span data-ttu-id="86577-127">[Conexiones de Integration Services &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="86577-127">[Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="86577-128">Copiar los elementos de proyectos</span><span class="sxs-lookup"><span data-stu-id="86577-128">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
  
