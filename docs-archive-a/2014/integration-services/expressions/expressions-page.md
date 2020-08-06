---
title: Página Expresiones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionspage.f1
helpviewer_keywords:
- Expressions Page dialog box
ms.assetid: c9016ec6-11c1-4ebd-b2a7-0fa6631fd9e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba4e73ea495456e8f9e452108ab09106a65543ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672210"
---
# <a name="expressions-page"></a><span data-ttu-id="6b04f-102">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="6b04f-102">Expressions Page</span></span>
  <span data-ttu-id="6b04f-103">Utilice la página **Expresiones** para editar expresiones de propiedad y obtener acceso a los cuadros de diálogo **Editor de expresiones de propiedad** y **Generador de expresiones** .</span><span class="sxs-lookup"><span data-stu-id="6b04f-103">Use the **Expressions** page to edit property expressions and to access the **Property Expressions Editor** and **Property Expression Builder** dialog boxes.</span></span>  
  
 <span data-ttu-id="6b04f-104">Las expresiones de propiedad actualizan los valores de las propiedades cuando se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="6b04f-104">Property expressions update the values of properties when the package is run.</span></span> <span data-ttu-id="6b04f-105">Se pueden utilizar expresiones de propiedad con las propiedades de paquetes, tareas, contenedores, administradores de conexión y algunos componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6b04f-105">Property expressions can be used with the properties of packages, tasks, containers, connection managers, as well as some data flow components.</span></span> <span data-ttu-id="6b04f-106">Las expresiones se evalúan y se usan los resultados en lugar de los valores en los que se han establecido las propiedades al configurar el paquete y los objetos de paquete.</span><span class="sxs-lookup"><span data-stu-id="6b04f-106">The expressions are evaluated and their results are used instead of the values to which you set the properties when you configured the package and package objects.</span></span> <span data-ttu-id="6b04f-107">Las expresiones pueden incluir variables y las funciones y los operadores que proporciona el lenguaje de expresiones.</span><span class="sxs-lookup"><span data-stu-id="6b04f-107">The expressions can include variables and the functions and operators that the expression language provides.</span></span> <span data-ttu-id="6b04f-108">Por ejemplo, se puede generar la línea de asunto de la tarea Enviar correo mediante la concatenación del valor de una variable que contenga la cadena "Pronóstico meteorológico para" y los resultados devueltos de la función GETDATE() para crear la cadena "Pronóstico meteorológico para 5/4/2006".</span><span class="sxs-lookup"><span data-stu-id="6b04f-108">For example, you can generate the subject line for the Send Mail task by concatenating the value of a variable that contains the string "Weather forecast for " and the return results of the GETDATE() function to make the string "Weather forecast for 4/5/2006".</span></span>  
  
 <span data-ttu-id="6b04f-109">Para obtener más información sobre cómo se escriben las expresiones y cómo se usan las expresiones de propiedad, vea [Expresiones de Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md) y [Usar expresiones de propiedad en paquetes](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6b04f-109">To learn more about writing expressions and using property expressions, see [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) and [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6b04f-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="6b04f-110">Options</span></span>  
 <span data-ttu-id="6b04f-111">**Expresiones (…)**</span><span class="sxs-lookup"><span data-stu-id="6b04f-111">**Expressions (...)**</span></span>  
 <span data-ttu-id="6b04f-112">Haga clic en los puntos suspensivos para abrir el cuadro de diálogo **Editor de expresiones de propiedad** .</span><span class="sxs-lookup"><span data-stu-id="6b04f-112">Click the ellipsis to open the **Property Expressions Editor** dialog box.</span></span> <span data-ttu-id="6b04f-113">Para más información, consulte [Property Expressions Editor](property-expressions-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6b04f-113">For more information, see [Property Expressions Editor](property-expressions-editor.md).</span></span>  
  
 **\<property name>**  
 <span data-ttu-id="6b04f-114">Haga clic en los puntos suspensivos para abrir el cuadro de diálogo **Generador de expresiones** .</span><span class="sxs-lookup"><span data-stu-id="6b04f-114">Click the ellipsis to open the **Expression Builder** dialog box.</span></span> <span data-ttu-id="6b04f-115">Para más información, consulte [Expression Builder](expression-builder.md).</span><span class="sxs-lookup"><span data-stu-id="6b04f-115">For more information, see [Expression Builder](expression-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b04f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b04f-116">See Also</span></span>  
 <span data-ttu-id="6b04f-117">[Variables de Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6b04f-117">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="6b04f-118">[Variables del sistema](../system-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6b04f-118">[System Variables](../system-variables.md) </span></span>  
 [<span data-ttu-id="6b04f-119">Expresiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="6b04f-119">Integration Services &#40;SSIS&#41; Expressions</span></span>](integration-services-ssis-expressions.md)  
  
  
