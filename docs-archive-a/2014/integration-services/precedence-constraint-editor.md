---
title: Editor de restricciones de precedencia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.precedenceconstraint.f1
helpviewer_keywords:
- Precedence Constraint Editor dialog box
ms.assetid: b10d4330-6e35-4037-b309-ef56efcd60c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6853d1974f4276361d60e1d73b34c72a366a7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670420"
---
# <a name="precedence-constraint-editor"></a><span data-ttu-id="fcbae-102">Editor de restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="fcbae-102">Precedence Constraint Editor</span></span>
  <span data-ttu-id="fcbae-103">Utilice el cuadro de diálogo **Editor de restricciones de precedencia** para configurar restricciones de precedencia.</span><span class="sxs-lookup"><span data-stu-id="fcbae-103">Use the **Precedence Constraint Editor** dialog box to configure precedence constraints.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fcbae-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="fcbae-104">Options</span></span>  
 <span data-ttu-id="fcbae-105">**Operación de evaluación**</span><span class="sxs-lookup"><span data-stu-id="fcbae-105">**Evaluation operation**</span></span>  
 <span data-ttu-id="fcbae-106">Permite especificar la operación de evaluación que utiliza la restricción de precedencia.</span><span class="sxs-lookup"><span data-stu-id="fcbae-106">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="fcbae-107">Las operaciones son: **Restricción**, **Expresión**, **Expresión y restricción** y **Expresión o restricción**.</span><span class="sxs-lookup"><span data-stu-id="fcbae-107">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
 <span data-ttu-id="fcbae-108">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fcbae-108">**Value**</span></span>  
 <span data-ttu-id="fcbae-109">Especifique el valor de restricción: **Correcto**, **Error** o **Finalización**.</span><span class="sxs-lookup"><span data-stu-id="fcbae-109">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcbae-110"> La línea de restricción de precedencia es verde para **Correcto**, resaltada para **Error**y azul para **Conclusión**.</span><span class="sxs-lookup"><span data-stu-id="fcbae-110">The precedence constraint line is green for **Success**, highlighted for **Failure**, and blue for **Completion**.</span></span>  
  
 <span data-ttu-id="fcbae-111">**Expression**</span><span class="sxs-lookup"><span data-stu-id="fcbae-111">**Expression**</span></span>  
 <span data-ttu-id="fcbae-112">Si usa las operaciones **Expresión**, **Expresión y restricción**o **Expresión o restricción**, escriba una expresión o inicie el Generador de expresiones para crear la expresión.</span><span class="sxs-lookup"><span data-stu-id="fcbae-112">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression or launch the Expression Builder to create the expression.</span></span> <span data-ttu-id="fcbae-113">La expresión debe evaluarse como un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="fcbae-113">The expression must evaluate to a Boolean.</span></span>  
  
 <span data-ttu-id="fcbae-114">**Test**</span><span class="sxs-lookup"><span data-stu-id="fcbae-114">**Test**</span></span>  
 <span data-ttu-id="fcbae-115">Permite validar la expresión.</span><span class="sxs-lookup"><span data-stu-id="fcbae-115">Validate the expression.</span></span>  
  
 <span data-ttu-id="fcbae-116">**Y lógico**</span><span class="sxs-lookup"><span data-stu-id="fcbae-116">**Logical AND**</span></span>  
 <span data-ttu-id="fcbae-117">Seleccione esta opción para indicar que varias restricciones de precedencia en el mismo archivo ejecutable deben evaluarse de forma conjunta.</span><span class="sxs-lookup"><span data-stu-id="fcbae-117">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="fcbae-118">Todas las restricciones deben evaluarse como `True`.</span><span class="sxs-lookup"><span data-stu-id="fcbae-118">All constraints must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcbae-119">Este tipo de restricción de precedencia se muestra como una línea sólida verde, resaltada o azul.</span><span class="sxs-lookup"><span data-stu-id="fcbae-119">This type of precedence constraint appears as a solid green, highlighted or blue line.</span></span>  
  
 <span data-ttu-id="fcbae-120">**O lógico**</span><span class="sxs-lookup"><span data-stu-id="fcbae-120">**Logical OR**</span></span>  
 <span data-ttu-id="fcbae-121">Seleccione esta opción para indicar que varias restricciones de precedencia en el mismo archivo ejecutable deben evaluarse de forma conjunta.</span><span class="sxs-lookup"><span data-stu-id="fcbae-121">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="fcbae-122">Al menos una restricción debe evaluarse como `True`.</span><span class="sxs-lookup"><span data-stu-id="fcbae-122">At least one constraint must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcbae-123">Este tipo de restricción de precedencia se muestra como una línea de puntos verde, resaltada o azul.</span><span class="sxs-lookup"><span data-stu-id="fcbae-123">This type of precedence constraint appears as a dotted green, highlighted, or blue line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcbae-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcbae-124">See Also</span></span>  
 <span data-ttu-id="fcbae-125">[Restricciones de precedencia](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="fcbae-125">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="fcbae-126">[Tareas de Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="fcbae-126">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="fcbae-127">[Contenedores de Integration Services](control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="fcbae-127">[Integration Services Containers](control-flow/integration-services-containers.md) </span></span>  
 [<span data-ttu-id="fcbae-128">Expresiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="fcbae-128">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
