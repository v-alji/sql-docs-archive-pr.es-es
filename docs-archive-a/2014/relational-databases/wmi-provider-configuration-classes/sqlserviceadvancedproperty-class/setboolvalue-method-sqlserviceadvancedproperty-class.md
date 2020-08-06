---
title: Establecer puntos de interrupción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.setbreakpoints.f1
helpviewer_keywords:
- Set Breakpoints dialog box
ms.assetid: 876e61b7-875c-43f4-bbce-d7eeb90f6730
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8115fcd845ee5ff415d13aa4fe36230234e33ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748701"
---
# <a name="set-breakpoints"></a><span data-ttu-id="bda0d-102">Establecer puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="bda0d-102">Set Breakpoints</span></span>
  <span data-ttu-id="bda0d-103">Utilice el cuadro de diálogo **Establecer puntos de interrupción** para especificar los eventos en los que se deben habilitar puntos de interrupción y para controlar el comportamiento del punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="bda0d-103">Use the **Set Breakpoints** dialog box to specify the events on which to enable breakpoints and to control the behavior of the breakpoint.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bda0d-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="bda0d-104">Options</span></span>  
 <span data-ttu-id="bda0d-105">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="bda0d-105">**Enabled**</span></span>  
 <span data-ttu-id="bda0d-106">Seleccione esta opción para habilitar un punto de interrupción en un evento.</span><span class="sxs-lookup"><span data-stu-id="bda0d-106">Select to enable a breakpoint on an event.</span></span>  
  
 <span data-ttu-id="bda0d-107">**Break Condition**</span><span class="sxs-lookup"><span data-stu-id="bda0d-107">**Break Condition**</span></span>  
 <span data-ttu-id="bda0d-108">Vea una lista de los eventos disponibles en los que se establecen puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="bda0d-108">View a list of available events on which to set breakpoints.</span></span>  
  
 <span data-ttu-id="bda0d-109">**Hit Count Type**</span><span class="sxs-lookup"><span data-stu-id="bda0d-109">**Hit Count Type**</span></span>  
 <span data-ttu-id="bda0d-110">Especifique el momento en el que el punto de interrupción surte efecto.</span><span class="sxs-lookup"><span data-stu-id="bda0d-110">Specify when the breakpoint takes effect.</span></span>  
  
|<span data-ttu-id="bda0d-111">Value</span><span class="sxs-lookup"><span data-stu-id="bda0d-111">Value</span></span>|<span data-ttu-id="bda0d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bda0d-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bda0d-113">**Siempre**</span><span class="sxs-lookup"><span data-stu-id="bda0d-113">**Always**</span></span>|<span data-ttu-id="bda0d-114">La ejecución se suspende siempre cuando se alcanza el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="bda0d-114">Execution is always suspended when the breakpoint is hit.</span></span>|  
|<span data-ttu-id="bda0d-115">**Número de llamadas igual a**</span><span class="sxs-lookup"><span data-stu-id="bda0d-115">**Hit count equals**</span></span>|<span data-ttu-id="bda0d-116">La ejecución se suspende cuando el número de veces que ha ocurrido el punto de interrupción es igual al número de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bda0d-116">Execution is suspended when the number of times the breakpoint has occurred is equal to the hit count.</span></span>|  
|<span data-ttu-id="bda0d-117">**Recuento de visitas mayor que o igual a**</span><span class="sxs-lookup"><span data-stu-id="bda0d-117">**Hit greater or equal**</span></span>|<span data-ttu-id="bda0d-118">La ejecución se suspende cuando el número de veces que ha ocurrido el punto de interrupción es igual a o mayor que el número de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bda0d-118">Execution is suspended when the number of times the breakpoint has occurred is equal to or greater than the hit count.</span></span>|  
|<span data-ttu-id="bda0d-119">**Múltiplo del número de llamadas**</span><span class="sxs-lookup"><span data-stu-id="bda0d-119">**Hit count multiple**</span></span>|<span data-ttu-id="bda0d-120">La ejecución se suspende cuando se produce un múltiplo de número de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bda0d-120">Execution is suspended when a multiple of the hit count occurs.</span></span> <span data-ttu-id="bda0d-121">Por ejemplo, si establece esta opción en 5, la ejecución se suspende cada cinco veces.</span><span class="sxs-lookup"><span data-stu-id="bda0d-121">For example, if you set this option to 5, execution is suspended every fifth time.</span></span>|  
  
 <span data-ttu-id="bda0d-122">**Número de llamadas**</span><span class="sxs-lookup"><span data-stu-id="bda0d-122">**Hit Count**</span></span>  
 <span data-ttu-id="bda0d-123">Especifique el número de visitas en el que se desencadena una interrupción.</span><span class="sxs-lookup"><span data-stu-id="bda0d-123">Specify the number of hits at which to trigger a break.</span></span> <span data-ttu-id="bda0d-124">Esta opción no está disponible si la interrupción está siempre activa.</span><span class="sxs-lookup"><span data-stu-id="bda0d-124">This option is not available if the breakpoint is always in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda0d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bda0d-125">See Also</span></span>  
 [<span data-ttu-id="bda0d-126">Depurar el flujo de control</span><span class="sxs-lookup"><span data-stu-id="bda0d-126">Debugging Control Flow</span></span>](../../../integration-services/troubleshooting/debugging-control-flow.md)  
  
  
