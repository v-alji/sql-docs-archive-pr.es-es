---
title: Configurar un contenedor de bucles for | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: b9cd7ea7-b198-4a35-8b16-6acf09611ca5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cb33ea5b7f3f59baad3c94f6bc845c281613ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663635"
---
# <a name="configure-a-for-loop-container"></a><span data-ttu-id="8214b-102">Configurar un contenedor de bucles For</span><span class="sxs-lookup"><span data-stu-id="8214b-102">Configure a For Loop Container</span></span>
  <span data-ttu-id="8214b-103">En este procedimiento se describe cómo configurar un contenedor de bucles For mediante el cuadro de diálogo **Editor de bucles For** .</span><span class="sxs-lookup"><span data-stu-id="8214b-103">This procedure describes how to configure a For Loop container by using the **For Loop Editor** dialog box.</span></span>  
  
### <a name="to-configure-the-for-loop-container"></a><span data-ttu-id="8214b-104">Para configurar el contenedor de bucles For</span><span class="sxs-lookup"><span data-stu-id="8214b-104">To configure the For Loop container</span></span>  
  
1.  <span data-ttu-id="8214b-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], haga doble clic en el contenedor de bucles For para abrir el **Editor de bucles For**.</span><span class="sxs-lookup"><span data-stu-id="8214b-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], double-click the For Loop container to open the **For Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="8214b-106">Opcionalmente, modifique el nombre y la descripción del contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="8214b-106">Optionally, modify the name and description of the For Loop container.</span></span>  
  
3.  <span data-ttu-id="8214b-107">También puede escribir una expresión de inicialización en el cuadro de texto **InitExpression** .</span><span class="sxs-lookup"><span data-stu-id="8214b-107">Optionally, type an initialization expression in the **InitExpression** text box.</span></span>  
  
4.  <span data-ttu-id="8214b-108">Escriba una expresión de evaluación en el cuadro de texto **EvalExpression** .</span><span class="sxs-lookup"><span data-stu-id="8214b-108">Type an evaluation expression in the **EvalExpression** text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8214b-109">La expresión debe evaluarse como un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="8214b-109">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="8214b-110">Cuando la expresión se evalúa como `false`, el bucle deja de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="8214b-110">When the expression evaluates to `false`, the loop stops running.</span></span>  
  
5.  <span data-ttu-id="8214b-111">Opcionalmente, escriba una expresión de asignación en el cuadro de texto **AssignExpression** .</span><span class="sxs-lookup"><span data-stu-id="8214b-111">Optionally, type an assignment expression in the **AssignExpression** text box.</span></span>  
  
6.  <span data-ttu-id="8214b-112">También puede hacer clic en **Expresiones** y, en la página **Expresiones** , crear expresiones de propiedades para las propiedades del contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="8214b-112">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the For Loop container.</span></span> <span data-ttu-id="8214b-113">Para más información, vea [Agregar o cambiar una expresión de propiedad](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="8214b-113">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="8214b-114">Haga clic en **Aceptar** para cerrar el **Editor de bucles For**.</span><span class="sxs-lookup"><span data-stu-id="8214b-114">Click **OK** to close the **For Loop Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8214b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8214b-115">See Also</span></span>  
 <span data-ttu-id="8214b-116">[Contenedor de bucles for](control-flow/for-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="8214b-116">[For Loop Container](control-flow/for-loop-container.md) </span></span>  
 <span data-ttu-id="8214b-117">[Integration Services &#40;expresiones de&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="8214b-117">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="8214b-118">Usar expresiones de propiedad en paquetes</span><span class="sxs-lookup"><span data-stu-id="8214b-118">Use Property Expressions in Packages</span></span>](expressions/use-property-expressions-in-packages.md)  
  
  
