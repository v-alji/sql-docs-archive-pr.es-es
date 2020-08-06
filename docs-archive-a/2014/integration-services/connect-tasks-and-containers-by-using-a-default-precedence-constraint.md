---
title: Conectar tareas y contenedores mediante una restricción de precedencia predeterminada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- default precedence constraints
- containers [Integration Services], precedence constraints
ms.assetid: 8f31f15f-98ff-4c35-b41f-8b8cfd148d75
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 00207172babdb41b1030e77e71a2c8bc3b99799d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748867"
---
# <a name="connect-tasks-and-containers-by-using-a-default-precedence-constraint"></a><span data-ttu-id="cec38-102">Conectar tareas y contenedores mediante una restricción de precedencia predeterminada</span><span class="sxs-lookup"><span data-stu-id="cec38-102">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>
  <span data-ttu-id="cec38-103">Las restricciones de precedencia conectan dos ejecutables.</span><span class="sxs-lookup"><span data-stu-id="cec38-103">Precedence constraints connect two executables.</span></span> <span data-ttu-id="cec38-104">Un ejecutable puede ser cualquier tarea en un contenedor de bucles For, bucles Foreach o de secuencia.</span><span class="sxs-lookup"><span data-stu-id="cec38-104">An executable can be any task or a For Loop, Foreach Loop, or Sequence container.</span></span> <span data-ttu-id="cec38-105">Este procedimiento describe cómo se configura el comportamiento predeterminado para las restricciones de precedencia y cómo se conectan los ejecutables mediante las restricciones de precedencia predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="cec38-105">This procedure describes how to set the default behavior for precedence constraints, and how to connect executables using the default precedence constraints.</span></span>  
  
## <a name="creating-default-precedence-constraints"></a><span data-ttu-id="cec38-106">Crear restricciones de precedencia predeterminadas</span><span class="sxs-lookup"><span data-stu-id="cec38-106">Creating Default Precedence Constraints</span></span>  
 <span data-ttu-id="cec38-107">Cuando se usa por primera vez el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)], el valor predeterminado de una restricción de precedencia es `Success`.</span><span class="sxs-lookup"><span data-stu-id="cec38-107">When you first use [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the default value of a precedence constraint is `Success`.</span></span> <span data-ttu-id="cec38-108">Siga estos pasos para configurar el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] y usar un valor predeterminado diferente para las restricciones de precedencia.</span><span class="sxs-lookup"><span data-stu-id="cec38-108">Follow these steps to configure [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to use a different default value for precedence constraints.</span></span>  
  
#### <a name="to-set-the-default-value-for-precedence-constraints"></a><span data-ttu-id="cec38-109">Para establecer el valor predeterminado para las restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="cec38-109">To set the default value for precedence constraints</span></span>  
  
1.  <span data-ttu-id="cec38-110">Abra [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec38-110">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="cec38-111">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="cec38-111">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="cec38-112">En el cuadro de diálogo **Opciones** , expanda **Diseñadores de Business Intelligence** y, a continuación, **Diseñadores de Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="cec38-112">In the **Options** dialog box, expand **Business Intelligence Designers,** and then expand **Integration Services Designers**.</span></span>  
  
4.  <span data-ttu-id="cec38-113">Haga clic en **Conexión automática de flujo de control** y seleccione **Conectar una nueva forma a la forma seleccionada de manera predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="cec38-113">Click **Control Flow Auto Connect** and select **Connect a new shape to the selected shape by default**.</span></span>  
  
5.  <span data-ttu-id="cec38-114">En la lista desplegable, elija **Usar una restricción de error en la operación para la nueva forma** o **Usar una restricción de operación completada para la nueva forma**.</span><span class="sxs-lookup"><span data-stu-id="cec38-114">In the drop-down list, choose either **Use a Failure constraint for the new shape** or **Use a Completion constraint for the new shape**.</span></span>  
  
6.  <span data-ttu-id="cec38-115">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="cec38-115">Click **OK**.</span></span>  
  
#### <a name="to-create-a-default-precedence-constraint"></a><span data-ttu-id="cec38-116">Para crear una restricción de precedencia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cec38-116">To create a default precedence constraint</span></span>  
  
1.  <span data-ttu-id="cec38-117">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="cec38-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="cec38-118">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="cec38-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="cec38-119">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="cec38-119">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="cec38-120">En la superficie de diseño de la pestaña **Flujo de control** , haga clic en la tarea o contenedor y arrastre su conector al ejecutable al que desea aplicar la restricción de precedencia.</span><span class="sxs-lookup"><span data-stu-id="cec38-120">On the design surface of the **Control Flow** tab, click the task or container and drag its connector to the executable to which you want the precedence constraint to apply.</span></span>  
  
5.  <span data-ttu-id="cec38-121">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="cec38-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec38-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cec38-122">See Also</span></span>  
 <span data-ttu-id="cec38-123">[Restricciones de precedencia](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="cec38-123">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="cec38-124">[Establecer el valor de una restricción de precedencia mediante el menú contextual](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="cec38-124">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="cec38-125">[Establecer las propiedades de una restricción de precedencia](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="cec38-125">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="cec38-126">Usar una expresión en una restricción de precedencia</span><span class="sxs-lookup"><span data-stu-id="cec38-126">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
