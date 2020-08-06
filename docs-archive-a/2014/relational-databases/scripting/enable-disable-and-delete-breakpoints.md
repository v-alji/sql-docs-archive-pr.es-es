---
title: Habilitar, deshabilitar y eliminar puntos de interrupción
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 357b5874-273f-43a9-8e30-83872bdea5dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 17e83c6488b9d9026fb78e5fb8f50e22533fa61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677019"
---
# <a name="enable-disable-and-delete-breakpoints"></a><span data-ttu-id="e58a9-102">Habilitar, deshabilitar y eliminar puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="e58a9-102">Enable, Disable, and Delete Breakpoints</span></span>
  <span data-ttu-id="e58a9-103">Para ver y administrar todos los puntos de interrupción abiertos, puede usar la ventana **Puntos de interrupción** .</span><span class="sxs-lookup"><span data-stu-id="e58a9-103">To view and manage all the open breakpoints, you can use the **Breakpoints** window.</span></span> <span data-ttu-id="e58a9-104">Use la ventana para ver la información de punto de interrupción y para realizar acciones tales como eliminar, deshabilitar o habilitar puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e58a9-104">Use the window to view breakpoint information and to take actions such as deleting, disabling, or enabling breakpoints.</span></span>  
  
## <a name="the-breakpoints-window"></a><span data-ttu-id="e58a9-105">Ventana Puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="e58a9-105">The Breakpoints Window</span></span>  
 <span data-ttu-id="e58a9-106">La ventana **Puntos de interrupción** muestra información como la línea de código en la que está ubicado el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e58a9-106">The **Breakpoints** window lists information such as which line of code the breakpoint is located on.</span></span> <span data-ttu-id="e58a9-107">Además en **Puntos de interrupción** , puede eliminar, deshabilitar y habilitar los puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e58a9-107">In the **Breakpoints** window, you can also delete, disable, and enable breakpoints.</span></span> <span data-ttu-id="e58a9-108">Para obtener más información sobre la ventana **Puntos de interrupción** , vea [Breakpoints Window](transact-sql-debugger-breakpoints-window.md)</span><span class="sxs-lookup"><span data-stu-id="e58a9-108">For more information about the **Breakpoints** window, see [Breakpoints Window](transact-sql-debugger-breakpoints-window.md)</span></span>  
  
 <span data-ttu-id="e58a9-109">Al deshabilitar un punto de interrupción, se evita que detenga la ejecución, pero deja la definición en su lugar en caso de que desee habilitar el punto de interrupción posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e58a9-109">Disabling a breakpoint prevents it from pausing execution, but leaves the definition in place in case you want to enable the breakpoint later.</span></span> <span data-ttu-id="e58a9-110">Al eliminar un punto de interrupción se quita permanentemente.</span><span class="sxs-lookup"><span data-stu-id="e58a9-110">Deleting a breakpoint removes it permanently.</span></span> <span data-ttu-id="e58a9-111">Debe alternar un nuevo punto de interrupción para pausar la ejecución de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="e58a9-111">You must toggle a new breakpoint to pause execution on the statement.</span></span>  
  
## <a name="to-open-the-breakpoints-window"></a><span data-ttu-id="e58a9-112">Para abrir la ventana Puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="e58a9-112">To Open the Breakpoints Window</span></span>  
 <span data-ttu-id="e58a9-113">**To open the Breakpoints window**</span><span class="sxs-lookup"><span data-stu-id="e58a9-113">**To open the Breakpoints window**</span></span>  
  
 <span data-ttu-id="e58a9-114">Puede abrir la ventana **Puntos de interrupción** de una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="e58a9-114">You can open the **Breakpoints** window in one of the following ways:</span></span>  
  
-   <span data-ttu-id="e58a9-115">En el menú **Depurar** , haga clic en **Ventanas**y, a continuación, haga clic en **Puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="e58a9-115">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
-   <span data-ttu-id="e58a9-116">En la barra de herramientas **Depurar** , haga clic en el botón **Puntos de interrupción** .</span><span class="sxs-lookup"><span data-stu-id="e58a9-116">On the **Debug** toolbar, click the **Breakpoints** button.</span></span>  
  
-   <span data-ttu-id="e58a9-117">Presione CTRL+ALT+B.</span><span class="sxs-lookup"><span data-stu-id="e58a9-117">Press CTRL+ALT+B.</span></span>  
  
## <a name="to-disable-a-single-breakpoint"></a><span data-ttu-id="e58a9-118">Para deshabilitar un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="e58a9-118">To Disable a Single Breakpoint</span></span>  
 <span data-ttu-id="e58a9-119">**To disable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="e58a9-119">**To disable a single breakpoint**</span></span>  
  
 <span data-ttu-id="e58a9-120">Puede deshabilitar un punto de interrupción de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="e58a9-120">You can disable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="e58a9-121">En la ventana del Editor de consultas, haga clic con el botón derecho en el punto de interrupción y, luego, haga clic en **Deshabilitar punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="e58a9-121">In the Query Editor window, right-click the breakpoint, and then click **Disable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="e58a9-122">En la ventana Puntos de interrupción, desactive la casilla situada a la izquierda del punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e58a9-122">In the Breakpoints window, clear the check box to the left of the breakpoint.</span></span>  
  
## <a name="to-disable-all-breakpoints"></a><span data-ttu-id="e58a9-123">Para deshabilitar todos los puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="e58a9-123">To Disable All Breakpoints</span></span>  
 <span data-ttu-id="e58a9-124">**To disable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="e58a9-124">**To disable all breakpoints**</span></span>  
  
 <span data-ttu-id="e58a9-125">Puede deshabilitar todos los puntos de interrupción de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="e58a9-125">You can disable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="e58a9-126">En el menú **Depurar** , haga clic en **Deshabilitar todos los puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="e58a9-126">On the **Debug** menu, click **Disable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="e58a9-127">En la barra de herramientas de la ventana **Puntos de interrupción** , haga clic en el botón **Deshabilitar todos los puntos de interrupción** .</span><span class="sxs-lookup"><span data-stu-id="e58a9-127">On the toolbar of the **Breakpoints** window, click the **Disable All Breakpoints** button.</span></span>  
  
## <a name="to-enable-a-single-breakpoint"></a><span data-ttu-id="e58a9-128">Para habilitar un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="e58a9-128">To Enable a Single Breakpoint</span></span>  
 <span data-ttu-id="e58a9-129">**To enable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="e58a9-129">**To enable a single breakpoint**</span></span>  
  
 <span data-ttu-id="e58a9-130">Puede habilitar un punto de interrupción de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="e58a9-130">You can enable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="e58a9-131">En la ventana del Editor de consultas, haga clic con el botón derecho en el punto de interrupción y, luego, haga clic en **Habilitar punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="e58a9-131">In the Query Editor window, right-click the breakpoint, and then click **Enable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="e58a9-132">En la ventana Puntos de interrupción, active la casilla situada a la izquierda del punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e58a9-132">In the Breakpoints window, click the box to the left of the breakpoint.</span></span>  
  
## <a name="to-enable-all-breakpoints"></a><span data-ttu-id="e58a9-133">Para habilitar todos los puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="e58a9-133">To Enable All Breakpoints</span></span>  
 <span data-ttu-id="e58a9-134">**To enable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="e58a9-134">**To enable all breakpoints**</span></span>  
  
 <span data-ttu-id="e58a9-135">Puede habilitar todos los puntos de interrupción de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="e58a9-135">You can enable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="e58a9-136">En el menú **Depurar** , haga clic en **Habilitar todos los puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="e58a9-136">On the **Debug** menu, click **Enable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="e58a9-137">En la barra de herramientas de la ventana **Puntos de interrupción** , haga clic en el botón **Habilitar todos los puntos de interrupción** .</span><span class="sxs-lookup"><span data-stu-id="e58a9-137">On the toolbar of the **Breakpoints** window, click the **Enable All Breakpoints** button.</span></span>  
  
## <a name="to-delete-a-single-breakpoint"></a><span data-ttu-id="e58a9-138">Para eliminar un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="e58a9-138">To Delete a Single Breakpoint</span></span>  
 <span data-ttu-id="e58a9-139">**To delete a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="e58a9-139">**To delete a single breakpoint**</span></span>  
  
 <span data-ttu-id="e58a9-140">Puede eliminar un punto de interrupción de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="e58a9-140">You can delete a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="e58a9-141">En la ventana del Editor de consultas, haga clic con el botón derecho en el punto de interrupción y, luego, haga clic en **Eliminar punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="e58a9-141">In the Query Editor window, right-click the breakpoint, and then click **Delete Breakpoint**.</span></span>  
  
-   <span data-ttu-id="e58a9-142">En la ventana Puntos de interrupción, haga clic con el botón derecho en el punto de interrupción y, luego, haga clic en el comando **Eliminar** del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="e58a9-142">In the Breakpoints window, right-click the breakpoint, and then click **Delete** on the shortcut menu.</span></span>  
  
-   <span data-ttu-id="e58a9-143">En la ventana Puntos de interrupción, seleccione el punto de interrupción y, a continuación, presione SUPR.</span><span class="sxs-lookup"><span data-stu-id="e58a9-143">In the Breakpoints window, select the breakpoint, and then press DELETE.</span></span>  
  
## <a name="to-delete-all-breakpoints"></a><span data-ttu-id="e58a9-144">Para eliminar todos los puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="e58a9-144">To Delete All Breakpoints</span></span>  
 <span data-ttu-id="e58a9-145">**To delete all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="e58a9-145">**To delete all breakpoints**</span></span>  
  
 <span data-ttu-id="e58a9-146">Puede eliminar todos los puntos de interrupción de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="e58a9-146">You can delete all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="e58a9-147">En el menú **Depurar** , haga clic en **Eliminar todos los puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="e58a9-147">On the **Debug** menu, cllick **Delete All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="e58a9-148">En la barra de herramientas de la ventana **Puntos de interrupción** , haga clic en el botón **Eliminar todos los puntos de interrupción** .</span><span class="sxs-lookup"><span data-stu-id="e58a9-148">On the toolbar of the **Breakpoints** window, click the **Delete All Breakpoints** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e58a9-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e58a9-149">See Also</span></span>  
 [<span data-ttu-id="e58a9-150">Alternar un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="e58a9-150">Toggle a Breakpoint</span></span>](../spatial/point.md)  
  
  
