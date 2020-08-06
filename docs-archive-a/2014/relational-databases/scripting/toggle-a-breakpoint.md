---
title: Alternar un punto de interrupción
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c477ab89-a1cd-4f2c-aa7c-40525041100f
author: rothja
ms.author: jroth
ms.openlocfilehash: 72e26e9b1d04bc2eced6bcb6d93d3c86a016d308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675792"
---
# <a name="toggle-a-breakpoint"></a><span data-ttu-id="39f4f-102">Alternar un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="39f4f-102">Toggle a Breakpoint</span></span>
  <span data-ttu-id="39f4f-103">El hecho de establecer un punto de interrupción en una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] se denomina alternar un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="39f4f-103">The act of setting a breakpoint on a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is called toggling a breakpoint.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="39f4f-104">Puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="39f4f-104">Breakpoints</span></span>  
 <span data-ttu-id="39f4f-105">Una vez establecido el punto de interrupción, se representa mediante un icono en la barra gris situada a la izquierda de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="39f4f-105">Once the breakpoint has been set, it is represented by an icon in the grey bar to the left of the statement.</span></span> <span data-ttu-id="39f4f-106">El icono se denomina glifo de punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="39f4f-106">The icon is called a breakpoint glyph.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="39f4f-107">se aplican a instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] completadas.</span><span class="sxs-lookup"><span data-stu-id="39f4f-107">breakpoints are applied to a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="39f4f-108">Cuando se alterna un punto de interrupción, el depurador resalta la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] asociada.</span><span class="sxs-lookup"><span data-stu-id="39f4f-108">When a breakpoint is toggled on, the debugger highlights the associated [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
 <span data-ttu-id="39f4f-109">Si hay varias instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] en una línea, puede alternar un punto de interrupción para cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="39f4f-109">If there are multiple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on a line, you can toggle a breakpoint for each statement.</span></span> <span data-ttu-id="39f4f-110">Al hacer clic en la barra gris de la izquierda de la ventana se alterna un punto de interrupción en la primera instrucción de la línea.</span><span class="sxs-lookup"><span data-stu-id="39f4f-110">Clicking in the grey bar on the left of the window toggles a breakpoint on the first statement on the line.</span></span> <span data-ttu-id="39f4f-111">Para alternar un punto de interrupción en una instrucción subsiguiente, resalte cualquier parte de la instrucción o mueva el cursor a la instrucción y, a continuación, presione F9 o haga clic en **Alternar punto de interrupción** en el menú **Depurar** .</span><span class="sxs-lookup"><span data-stu-id="39f4f-111">You can toggle a breakpoint in a subsequent statement by highlighting any part of the statement, or moving the cursor into the statement, and then either pressing F9 or clicking **Toggle Breakpoint** on the **Debug** menu.</span></span> <span data-ttu-id="39f4f-112">Si hay varios puntos de interrupción en una línea, solo hay un glifo de punto de interrupción en la barra gris de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="39f4f-112">If you have multiple breakpoints on a line, there is only one breakpoint glyph in the grey bar on the left.</span></span>  
  
 <span data-ttu-id="39f4f-113">Una vez que se ha alternado un punto de interrupción, puede realizar diversas acciones en el punto de interrupción, como editar sus propiedades o deshabilitarlo provisionalmente.</span><span class="sxs-lookup"><span data-stu-id="39f4f-113">After a breakpoint has been toggled, you can perform various actions on the breakpoint, such as editing its properties or temporarily disabling it.</span></span> <span data-ttu-id="39f4f-114">Para obtener más información, vea [Utilizar puntos de interrupción de Transact-SQL](transact-sql-breakpoints.md).</span><span class="sxs-lookup"><span data-stu-id="39f4f-114">For more information, see [Transact-SQL Breakpoints](transact-sql-breakpoints.md).</span></span>  
  
## <a name="toggle-a-breakpoint"></a><span data-ttu-id="39f4f-115">Alternar un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="39f4f-115">Toggle a Breakpoint</span></span>  
 <span data-ttu-id="39f4f-116">**Para alternar un punto de interrupción en una instrucción Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="39f4f-116">**To toggle a breakpoint on a Transact-SQL statement**</span></span>  
  
1.  <span data-ttu-id="39f4f-117">Haga clic en la barra deshabilitada situada a la izquierda de la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39f4f-117">Click the gray bar to the left side of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
2.  <span data-ttu-id="39f4f-118">Alternativamente, puede resaltar cualquier parte de la instrucción o mover el cursor a la instrucción y, a continuación, realizar cualquiera de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="39f4f-118">Alternatively, either highlight any part of the statement or move the cursor to the statement, and then perform either action:</span></span>  
  
    -   <span data-ttu-id="39f4f-119">Presione F9.</span><span class="sxs-lookup"><span data-stu-id="39f4f-119">Press F9.</span></span>  
  
    -   <span data-ttu-id="39f4f-120">En el menú **Depurar** , haga clic en **Alternar punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="39f4f-120">On the **Debug** menu, click **Toggle Breakpoint**.</span></span>  
  
  
