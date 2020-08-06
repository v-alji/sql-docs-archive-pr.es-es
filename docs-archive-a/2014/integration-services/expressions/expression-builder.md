---
title: Generador de expresiones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionbuilder.f1
helpviewer_keywords:
- Expression Builder dialog box
ms.assetid: 4717ce33-bd4e-44bc-81e0-002de075b4d1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 812b0d744d415d5419d54176359ddcd5837dd206
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672209"
---
# <a name="expression-builder"></a><span data-ttu-id="6ae78-102">Generador de expresiones</span><span class="sxs-lookup"><span data-stu-id="6ae78-102">Expression Builder</span></span>
  <span data-ttu-id="6ae78-103">Use el cuadro de diálogo **Generador de expresiones** para crear y editar una expresión de propiedad, o bien para escribir la expresión que establece el valor de una variable con una interfaz gráfica de usuario que incluye variables y proporciona una referencia integrada para las funciones, conversiones de tipo y operadores del lenguaje de expresiones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ae78-103">Use the **Expression Builder** dialog box to create and edit a property expression or write the expression that sets the value of a variable using a graphical user interface that lists variables and provides a built-in reference to the functions, type casts, and operators that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language includes.</span></span>  
  
 <span data-ttu-id="6ae78-104">Una expresión de propiedad es una expresión asignada a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="6ae78-104">A property expression is an expression that is assigned to a property.</span></span> <span data-ttu-id="6ae78-105">Cuando se evalúa la expresión, la propiedad se actualiza dinámicamente para utilizar el resultado de la evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="6ae78-105">When the expression is evaluated, the property is dynamically updated to use the evaluation result of the expression.</span></span> <span data-ttu-id="6ae78-106">De manera similar, una expresión que se utiliza en una variable permite que el valor de la variable se actualice con el resultado de la evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="6ae78-106">Likewise, an expression that is used in a variable enables the variable value to be updated with the evaluation result of the expression.</span></span>  
  
 <span data-ttu-id="6ae78-107">Existen varias formas de utilizar expresiones:</span><span class="sxs-lookup"><span data-stu-id="6ae78-107">There are many ways to use expressions:</span></span>  
  
-   <span data-ttu-id="6ae78-108">**Tareas** Puede actualizar la línea Para que usa una tarea Enviar correo. Para hacerlo, inserte una dirección de correo electrónico almacenada en una variable, o bien actualice la línea de asunto con la concatenación de una cadena como "Ventas para:" y la fecha actual devuelta por la función GETDATE.</span><span class="sxs-lookup"><span data-stu-id="6ae78-108">**Tasks** Update the To line that a Send Mail task uses by inserting an e-mail address that is stored in a variable; or update the Subject line by concatenating a string such as "Sales for: " and the current date returned by the GETDATE function.</span></span>  
  
-   <span data-ttu-id="6ae78-109">**Variables** Establecer el valor de una variable en el mes actual utilizando una expresión como `DATEPART("mm",GETDATE())`; o bien establecer el valor de una cadena mediante la concatenación del literal de cadena y la fecha actual utilizando la expresión `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span><span class="sxs-lookup"><span data-stu-id="6ae78-109">**Variables** Set the value of a variable to the current month by using an expression like `DATEPART("mm",GETDATE())`; or set the value of a string by concatenating the string literal and the current date by using the expression `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span></span>  
  
-   <span data-ttu-id="6ae78-110">**Administradores de conexión** Establecer la página de códigos de un administrador de conexiones de archivos planos utilizando una variable que contenga un identificador de página de códigos diferente; o bien especificar el número de filas del archivo de datos que deben omitirse escribiendo en la expresión un entero positivo, como 3.</span><span class="sxs-lookup"><span data-stu-id="6ae78-110">**Connection Managers** Set the code page of a Flat File connection manager by using a variable that contains a different code page identifier; or specify the number of rows in the data file to skip by entering a positive integer like 3 in the expression.</span></span>  
  
 <span data-ttu-id="6ae78-111">Para más información sobre las expresiones de propiedad y las expresiones de escritura, vea [Usar expresiones de propiedad en paquetes](use-property-expressions-in-packages.md) y [Expresiones de Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6ae78-111">To learn more about property expressions and writing expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md) and [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6ae78-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="6ae78-112">Options</span></span>  
  
|<span data-ttu-id="6ae78-113">Término</span><span class="sxs-lookup"><span data-stu-id="6ae78-113">Term</span></span>|<span data-ttu-id="6ae78-114">Definición</span><span class="sxs-lookup"><span data-stu-id="6ae78-114">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="6ae78-115">**Variables**</span><span class="sxs-lookup"><span data-stu-id="6ae78-115">**Variables**</span></span>|<span data-ttu-id="6ae78-116">Expanda la carpeta **Variables** y arrastre las variables hasta el cuadro **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="6ae78-116">Expand the **Variables** folder and drag variables to the **Expression** box.</span></span>|  
|<span data-ttu-id="6ae78-117">**Funciones matemáticas**</span><span class="sxs-lookup"><span data-stu-id="6ae78-117">**Mathematical Functions**</span></span><br /><br /> <span data-ttu-id="6ae78-118">**Funciones de cadena**</span><span class="sxs-lookup"><span data-stu-id="6ae78-118">**String Functions**</span></span><br /><br /> <span data-ttu-id="6ae78-119">**Funciones de fecha y hora**</span><span class="sxs-lookup"><span data-stu-id="6ae78-119">**Date/Time Functions**</span></span><br /><br /> <span data-ttu-id="6ae78-120">**Funciones NULL**</span><span class="sxs-lookup"><span data-stu-id="6ae78-120">**NULL Functions**</span></span><br /><br /> <span data-ttu-id="6ae78-121">**Conversiones de tipo**</span><span class="sxs-lookup"><span data-stu-id="6ae78-121">**Type Casts**</span></span><br /><br /> <span data-ttu-id="6ae78-122">**Operadores**</span><span class="sxs-lookup"><span data-stu-id="6ae78-122">**Operators**</span></span>|<span data-ttu-id="6ae78-123">Expanda las carpetas y arrastre funciones, conversiones de tipo y operadores hasta el cuadro **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="6ae78-123">Expand the folders and drag functions, type casts, and operators to the **Expression** box.</span></span>|  
|<span data-ttu-id="6ae78-124">**Expression**</span><span class="sxs-lookup"><span data-stu-id="6ae78-124">**Expression**</span></span>|<span data-ttu-id="6ae78-125">Edite o escriba una expresión.</span><span class="sxs-lookup"><span data-stu-id="6ae78-125">Edit or type an expression.\`</span></span>|  
|<span data-ttu-id="6ae78-126">**Valor evaluado**</span><span class="sxs-lookup"><span data-stu-id="6ae78-126">**Evaluated value**</span></span>|<span data-ttu-id="6ae78-127">Muestra el resultado de evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="6ae78-127">Lists the evaluation result of the expression.</span></span>|  
|<span data-ttu-id="6ae78-128">**Evaluar expresión**</span><span class="sxs-lookup"><span data-stu-id="6ae78-128">**Evaluate Expression**</span></span>|<span data-ttu-id="6ae78-129">Haga clic en **Evaluar expresión** para ver el resultado de evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="6ae78-129">Click **Evaluate Expression** to view the evaluation result of the expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ae78-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ae78-130">See Also</span></span>  
 <span data-ttu-id="6ae78-131">[Página Expresiones](expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="6ae78-131">[Expressions Page](expressions-page.md) </span></span>  
 <span data-ttu-id="6ae78-132">[Editor de expresiones de propiedad](property-expressions-editor.md) </span><span class="sxs-lookup"><span data-stu-id="6ae78-132">[Property Expressions Editor](property-expressions-editor.md) </span></span>  
 <span data-ttu-id="6ae78-133">[Variables de Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6ae78-133">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="6ae78-134">Variables del sistema</span><span class="sxs-lookup"><span data-stu-id="6ae78-134">System Variables</span></span>](../system-variables.md)  
  
  
