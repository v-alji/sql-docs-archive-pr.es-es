---
title: Varias restricciones de precedencia | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- multiple precedence constraints
- precedence executables [Integration Services]
- precedence constraints [Integration Services], multiple
- constrained executables [Integration Services]
ms.assetid: 71c53ead-3d19-4bc1-aafd-e5b32595b420
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16fefbbf886818989131710876564fc9e147a56a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673091"
---
# <a name="multiple-precedence-constraints"></a><span data-ttu-id="878ed-102">Varias restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="878ed-102">Multiple Precedence Constraints</span></span>
  <span data-ttu-id="878ed-103">Una restricción de precedencia conecta dos ejecutables: dos tareas, dos contenedores o uno de cada.</span><span class="sxs-lookup"><span data-stu-id="878ed-103">A precedence constraint connects two executables: two tasks, two containers, or one of each.</span></span> <span data-ttu-id="878ed-104">Se conocen como el ejecutable de precedencia y el ejecutable restringido.</span><span class="sxs-lookup"><span data-stu-id="878ed-104">They are known as the precedence executable and the constrained executable.</span></span> <span data-ttu-id="878ed-105">Un ejecutable restringido puede tener varias restricciones de precedencia.</span><span class="sxs-lookup"><span data-stu-id="878ed-105">A constrained executable can have multiple precedence constraints.</span></span> <span data-ttu-id="878ed-106">Para obtener más información, vea [Restricciones de precedencia](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="878ed-106">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="878ed-107">El ensamblaje de escenarios de restricciones complejas mediante la agrupación de restricciones le permite implementar un flujo de control complejo en paquetes.</span><span class="sxs-lookup"><span data-stu-id="878ed-107">Assembling complex constraint scenarios by grouping constraints enables you to implement complex control flow in packages.</span></span> <span data-ttu-id="878ed-108">Por ejemplo, en la siguiente ilustración, la tarea D se vincula a la tarea A mediante una restricción `Success`, la tarea D se vincula a la tarea B mediante una restricción `Failure`, y la tarea D se vincula a la tarea C mediante una restricción `Success`.</span><span class="sxs-lookup"><span data-stu-id="878ed-108">For example, in the following illustration, Task D is linked to Task A by a `Success` constraint, Task D is linked to Task B by a `Failure` constraint, and Task D is linked to Task C by a `Success` constraint.</span></span> <span data-ttu-id="878ed-109">Las restricciones de precedencia entre la tarea D y la tarea A, entre la tarea D y la tarea B, y entre la tarea D y la tarea C participan en una relación lógica *and* .</span><span class="sxs-lookup"><span data-stu-id="878ed-109">The precedence constraints between Task D and Task A, between Task D and Task B, and between Task D and Task C participate in a logical *and* relationship.</span></span> <span data-ttu-id="878ed-110">Por lo tanto, para que la tarea D se ejecute, la tarea A se debe ejecutar correctamente, la tarea B debe sufrir un error en su ejecución, y la tarea C se debe ejecutar correctamente.</span><span class="sxs-lookup"><span data-stu-id="878ed-110">Therefore, for Task D to run, Task A must run successfully, Task B must fail, and Task C must run successfully.</span></span>  
  
 <span data-ttu-id="878ed-111">![Tareas vinculadas por las restricciones de precedencia](media/precedenceconstraints.gif "Tareas vinculadas por las restricciones de precedencia")</span><span class="sxs-lookup"><span data-stu-id="878ed-111">![Tasks linked by precedence constraints](media/precedenceconstraints.gif "Tasks linked by precedence constraints")</span></span>  
  
## <a name="logicaland-property"></a><span data-ttu-id="878ed-112">Propiedad LogicalAnd</span><span class="sxs-lookup"><span data-stu-id="878ed-112">LogicalAnd Property</span></span>  
 <span data-ttu-id="878ed-113">Si una tarea o contenedor tiene varias restricciones, la propiedad `LogicalAnd` especifica si se evalúa una restricción de precedencia individualmente o en conjunto con otras restricciones.</span><span class="sxs-lookup"><span data-stu-id="878ed-113">If a task or a container has multiple constraints, the `LogicalAnd` property specifies whether a precedence constraint is evaluated singly or in concert with other constraints.</span></span>  
  
 <span data-ttu-id="878ed-114">Puede establecer la `LogicalAnd` propiedad mediante el **Editor de restricciones de precedencia** en [!INCLUDE[ssIS](../includes/ssis-md.md)] el diseñador o en el ventana Propiedades que [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] proporciona.</span><span class="sxs-lookup"><span data-stu-id="878ed-114">You can set the `LogicalAnd` property using the **Precedence Constraint Editor** in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, or in the Properties window that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] provides.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="878ed-115">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="878ed-115">Related Tasks</span></span>  
 [<span data-ttu-id="878ed-116">Establecer las propiedades de una restricción de precedencia</span><span class="sxs-lookup"><span data-stu-id="878ed-116">Set the Properties of a Precedence Constraint</span></span>](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md)  
  
  
