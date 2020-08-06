---
title: Utilizar puntos de interrupción de Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoints
ms.assetid: c234430f-bd94-4d0d-9e74-2bf11681fa50
author: rothja
ms.author: jroth
ms.openlocfilehash: c9595c9627ac3cc445b1193881c2d5b772e9b71d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675791"
---
# <a name="transact-sql-breakpoints"></a><span data-ttu-id="17f8e-102">Utilizar puntos de interrupción de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17f8e-102">Transact-SQL Breakpoints</span></span>
  <span data-ttu-id="17f8e-103">Los puntos de interrupción especifican que el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] pausa la ejecución en una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] específica, puede ver el estado de los elementos de código en ese momento.</span><span class="sxs-lookup"><span data-stu-id="17f8e-103">Breakpoints specify that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, you can then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="17f8e-104">Puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="17f8e-104">Breakpoints</span></span>  
 <span data-ttu-id="17f8e-105">Al ejecutar el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] , puede alternar un punto de interrupción en instrucciones concretas.</span><span class="sxs-lookup"><span data-stu-id="17f8e-105">When running the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can toggle a breakpoint on specific statements.</span></span> <span data-ttu-id="17f8e-106">Cuando la ejecución llegue a una instrucción con un punto de interrupción, el depurador pausa la ejecución para que se pueda ver información de depuración, como los valores presentes en variables y parámetros.</span><span class="sxs-lookup"><span data-stu-id="17f8e-106">When execution reaches a statement with a breakpoint, the debugger pauses execution so you can view debugging information, such as the values present in variables and parameters.</span></span>  
  
 <span data-ttu-id="17f8e-107">Puede administrar los puntos de interrupción individualmente en la ventana del editor, o colectivamente mediante la ventana de **Puntos de interrupción** .</span><span class="sxs-lookup"><span data-stu-id="17f8e-107">You can manage breakpoints individually in the editor window, or collectively by using the **Breakpoints** window.</span></span> <span data-ttu-id="17f8e-108">Puede modificar los puntos de interrupción para especificar elementos como las condiciones particulares en las que la acción debe pausar, o las acciones que deben realizarse si ejecuta el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="17f8e-108">You can edit breakpoints to specify items such as specific conditions under which execution should pause, or the actions to be taken if the breakpoint is executed.</span></span>  
  
## <a name="breakpoint-tasks"></a><span data-ttu-id="17f8e-109">Tareas de punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="17f8e-109">Breakpoint Tasks</span></span>  
  
|<span data-ttu-id="17f8e-110">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="17f8e-110">Task Description</span></span>|<span data-ttu-id="17f8e-111">Tema</span><span class="sxs-lookup"><span data-stu-id="17f8e-111">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="17f8e-112">Describe cómo especificar la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] en la que desea que el depurador en pause.</span><span class="sxs-lookup"><span data-stu-id="17f8e-112">Describes how to specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement on which you want the debugger to pause.</span></span>|[<span data-ttu-id="17f8e-113">Alternar un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="17f8e-113">Toggle a Breakpoint</span></span>](../spatial/point.md)|  
|<span data-ttu-id="17f8e-114">Describe cómo desactivar temporalmente un punto de interrupción y reactivarlo posteriormente.</span><span class="sxs-lookup"><span data-stu-id="17f8e-114">Describes how to temporarily deactivate a breakpoint, and later reactivate it.</span></span> <span data-ttu-id="17f8e-115">También se describe cómo eliminar un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="17f8e-115">Also describes how to delete a breakpoint.</span></span>|[<span data-ttu-id="17f8e-116">Habilitar, deshabilitar y eliminar puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="17f8e-116">Enable, Disable, and Delete Breakpoints</span></span>](enable-disable-and-delete-breakpoints.md)|  
|<span data-ttu-id="17f8e-117">Describe cómo especificar una condición, que define si el punto de interrupción interrumpe basándose en la evaluación de una expresión de Transact SQL especificada.</span><span class="sxs-lookup"><span data-stu-id="17f8e-117">Describes how to specify a condition, which defines whether breakpoint breaks based on the evaluation of a specified Transact-SQL expression.</span></span>|[<span data-ttu-id="17f8e-118">Especificar una condición de punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="17f8e-118">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)|  
|<span data-ttu-id="17f8e-119">Describe como especificar un número de llamadas, que causa que un punto de interrupción se interrumpa solo cuando la instrucción que lo contiene se ha ejecutado un número de veces especificado.</span><span class="sxs-lookup"><span data-stu-id="17f8e-119">Describes how to specify a hit count, which causes a breakpoint to break only when the statement containing the breakpoint has been executed a specified number of times.</span></span>|[<span data-ttu-id="17f8e-120">Especificar un número de llamadas</span><span class="sxs-lookup"><span data-stu-id="17f8e-120">Specify a Hit Count</span></span>](specify-a-hit-count.md)|  
|<span data-ttu-id="17f8e-121">Describe cómo especificar un filtro, que hace que un punto de interrupción interrumpa únicamente en procesos o subprocesos especificados.</span><span class="sxs-lookup"><span data-stu-id="17f8e-121">Describes how to specify a filter, which causes a breakpoint to break for only specified processes or threads.</span></span>|[<span data-ttu-id="17f8e-122">Especificar un filtro del punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="17f8e-122">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)|  
|<span data-ttu-id="17f8e-123">Describe cómo especificar una acción **Cuándo se llama** , una operación personalizada que se realiza cuando se ejecuta la instrucción de punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="17f8e-123">Describes how to specify a **When Hit** action, which is a custom operation that is performed when the breakpoint statement is executed.</span></span> <span data-ttu-id="17f8e-124">Un ejemplo de lo anterior sería imprimir un mensaje.</span><span class="sxs-lookup"><span data-stu-id="17f8e-124">An example would be to print a message.</span></span>|[<span data-ttu-id="17f8e-125">Especificar una acción del punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="17f8e-125">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)|  
|<span data-ttu-id="17f8e-126">Describe cómo editar la ubicación de un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="17f8e-126">Describes how to edit the location of a breakpoint.</span></span>|[<span data-ttu-id="17f8e-127">Modificar la ubicación de un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="17f8e-127">Edit a Breakpoint Location</span></span>](edit-a-breakpoint-location.md)|  
  
## <a name="see-also"></a><span data-ttu-id="17f8e-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17f8e-128">See Also</span></span>  
 [<span data-ttu-id="17f8e-129">Ver información del depurador de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17f8e-129">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
