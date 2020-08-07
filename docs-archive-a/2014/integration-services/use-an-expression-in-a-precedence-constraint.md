---
title: Usar una expresión en una restricción de precedencia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- precedence constraints [Integration Services], adding expressions
- expressions [Integration Services], adding
ms.assetid: 601038bb-3b17-42ac-b09d-5b3a82fb6564
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a997efa448a8381cc8251cd4cbf69dc59f8968e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746324"
---
# <a name="use-an-expression-in-a-precedence-constraint"></a><span data-ttu-id="b7d5b-102">Usar una expresión en una restricción de precedencia</span><span class="sxs-lookup"><span data-stu-id="b7d5b-102">Use an Expression in a Precedence Constraint</span></span>
  <span data-ttu-id="b7d5b-103">Este procedimiento describe cómo agregar una expresión a una restricción de precedencia mediante el cuadro de diálogo **Editor de restricciones de precedencia** .</span><span class="sxs-lookup"><span data-stu-id="b7d5b-103">This procedure describes how to add an expression to a precedence constraint by using the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="b7d5b-104">Antes de poder agregar una expresión a una restricción de precedencia, el paquete debe incluir por lo menos dos ejecutables, ya sean tareas o contenedores, y deben estar conectados por una restricción de precedencia.</span><span class="sxs-lookup"><span data-stu-id="b7d5b-104">Before you can add an expression to a precedence constraint, the package must include at least two executables, either tasks or containers, and they must be connected by a precedence constraint.</span></span>  
  
### <a name="to-add-an-expression-to-a-precedence-constraint"></a><span data-ttu-id="b7d5b-105">Para agregar una expresión a una restricción de precedencia</span><span class="sxs-lookup"><span data-stu-id="b7d5b-105">To add an expression to a precedence constraint</span></span>  
  
1.  <span data-ttu-id="b7d5b-106">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="b7d5b-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b7d5b-107">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="b7d5b-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b7d5b-108">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="b7d5b-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="b7d5b-109">En la superficie de diseño de la pestaña **Flujo de control** , haga doble clic en la restricción de precedencia.</span><span class="sxs-lookup"><span data-stu-id="b7d5b-109">On the design surface of the **Control Flow** tab, double-click the precedence constraint.</span></span> <span data-ttu-id="b7d5b-110">Se abre el **Editor de restricciones de precedencia** .</span><span class="sxs-lookup"><span data-stu-id="b7d5b-110">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="b7d5b-111">Seleccione **Expresión**, **Expresión y restricción**, o **Expresión o restricción** en la lista **Operación de evaluación** .</span><span class="sxs-lookup"><span data-stu-id="b7d5b-111">Select **Expression**, **Expression and Constraint**, or **Expression or Constraint** in the **Evaluation operation** list.</span></span>  
  
6.  <span data-ttu-id="b7d5b-112">Escriba una expresión o haga clic en el cuadro **Expresión** o inicie el Generador de expresiones para crear una expresión.</span><span class="sxs-lookup"><span data-stu-id="b7d5b-112">Type an expression in the **Expression** text box or launch the Expression Builder to create an expression.</span></span>  
  
7.  <span data-ttu-id="b7d5b-113">Para validar la sintaxis de expresión, haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="b7d5b-113">To validate the expression syntax, click **Test**.</span></span>  
  
8.  <span data-ttu-id="b7d5b-114">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="b7d5b-114">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d5b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7d5b-115">See Also</span></span>  
 <span data-ttu-id="b7d5b-116">[Restricciones de precedencia](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="b7d5b-116">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="b7d5b-117">[Conectar tareas y contenedores mediante una restricción de precedencia predeterminada](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="b7d5b-117">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="b7d5b-118">[Establecer el valor de una restricción de precedencia mediante el menú contextual](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="b7d5b-118">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="b7d5b-119">[Establecer las propiedades de una restricción de precedencia](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="b7d5b-119">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="b7d5b-120">Expresiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d5b-120">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
