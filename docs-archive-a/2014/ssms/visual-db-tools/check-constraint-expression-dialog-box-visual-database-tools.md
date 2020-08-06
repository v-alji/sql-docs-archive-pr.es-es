---
title: Cuadro de diálogo de la expresión de restricción CHECK (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraintexpression
ms.assetid: beb6ce43-3913-4d66-8826-8e885335b790
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38268d4e49a9c674c100bc22c0782e3e61477967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661759"
---
# <a name="check-constraint-expression-dialog-box-visual-database-tools"></a><span data-ttu-id="aea1e-102">Expresión de restricción CHECK (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="aea1e-102">Check Constraint Expression Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="aea1e-103">Cuando asocie una restricción CHECK a una tabla o columna, debe incluir una expresión SQL.</span><span class="sxs-lookup"><span data-stu-id="aea1e-103">When you attach a check constraint to a table or column, you must include an SQL expression.</span></span> <span data-ttu-id="aea1e-104">Escriba la expresión de restricción CHECK en el cuadro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="aea1e-104">Type the check constraint expression in the box provided.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="aea1e-105">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="aea1e-105">UI element list</span></span>  
 <span data-ttu-id="aea1e-106">Expression</span><span class="sxs-lookup"><span data-stu-id="aea1e-106">Expression</span></span>  
 <span data-ttu-id="aea1e-107">Escriba la expresión.</span><span class="sxs-lookup"><span data-stu-id="aea1e-107">Enter the expression</span></span>  
  
 <span data-ttu-id="aea1e-108">Puede crear una expresión de restricción sencilla para comprobar una condición sencilla en los datos o puede crear una expresión compleja mediante operadores booleanos para comprobar varias condiciones en los datos.</span><span class="sxs-lookup"><span data-stu-id="aea1e-108">You can create a simple constraint expression to check data for a simple condition; or you can create a complex expression, using Boolean operators, to check data for several conditions.</span></span> <span data-ttu-id="aea1e-109">Por ejemplo, supongamos que la tabla authors tiene una columna zip que requiere una cadena de caracteres de 5 dígitos.</span><span class="sxs-lookup"><span data-stu-id="aea1e-109">For example, suppose the authors table has a zip column where a 5-digit character string is required.</span></span> <span data-ttu-id="aea1e-110">Esta expresión de restricción de ejemplo garantiza que solo se permitan números de 5 dígitos:</span><span class="sxs-lookup"><span data-stu-id="aea1e-110">This sample constraint expression guarantees that only 5-digit numbers are allowed:</span></span>  
  
```  
zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
```  
  
 <span data-ttu-id="aea1e-111">O bien, supongamos que la tabla sales tiene una columna llamada qty que requiere un valor mayor que 0.</span><span class="sxs-lookup"><span data-stu-id="aea1e-111">Or suppose the sales table has a column called qty which requires a value greater than 0.</span></span> <span data-ttu-id="aea1e-112">Esta restricción de muestra garantiza que solo se permitan los valores positivos:</span><span class="sxs-lookup"><span data-stu-id="aea1e-112">This sample constraint guarantees that only positive values are allowed:</span></span>  
  
```  
qty > 0  
```  
  
 <span data-ttu-id="aea1e-113">Supongamos también que la tabla orders limita el tipo de tarjetas de crédito admitidas para todos los pedidos de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="aea1e-113">Or suppose the orders table limits the type of credit cards accepted for all credit card orders.</span></span> <span data-ttu-id="aea1e-114">Esta restricción de ejemplo garantiza que si el pedido se realiza con una tarjeta de crédito, solo se aceptará Visa, MasterCard o American Express:</span><span class="sxs-lookup"><span data-stu-id="aea1e-114">This sample constraint guarantees that if the order is placed on a credit card, then only Visa, MasterCard, or American Express is accepted:</span></span>  
  
```  
NOT (payment_method = 'credit card') OR  
   (card_type IN ('VISA', 'MASTERCARD', 'AMERICAN EXPRESS'))  
```  
  
## <a name="to-define-a-constraint-expression"></a><span data-ttu-id="aea1e-115">Para definir una expresión de restricción</span><span class="sxs-lookup"><span data-stu-id="aea1e-115">To define a constraint expression</span></span>  
 <span data-ttu-id="aea1e-116">En la pestaña Restricciones CHECK de las páginas de propiedades, escriba una expresión en el cuadro de diálogo Expresión de restricción CHECK utilizando la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="aea1e-116">In the Check Constraints tab of the property pages, type an expression in the Constraint expression box using the following syntax:</span></span>  
  
 `{constant | column_name | function | (subquery)}`  
  
 `[{operator | AND | OR | NOT}`  
  
 `{constant | column_name | function | (subquery)}...]`  
  
 <span data-ttu-id="aea1e-117">La sintaxis de SQL está formada por los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="aea1e-117">The SQL syntax is made up of the following parameters:</span></span>  
  
|<span data-ttu-id="aea1e-118">Parámetro</span><span class="sxs-lookup"><span data-stu-id="aea1e-118">Parameter</span></span>|<span data-ttu-id="aea1e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="aea1e-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aea1e-120">constant</span><span class="sxs-lookup"><span data-stu-id="aea1e-120">constant</span></span>|<span data-ttu-id="aea1e-121">Valor literal, como un valor numérico o una cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="aea1e-121">A literal value, such as numeric or character data.</span></span> <span data-ttu-id="aea1e-122">Los datos de caracteres deben escribirse entre comillas sencillas (').</span><span class="sxs-lookup"><span data-stu-id="aea1e-122">Character data must be enclosed within single quotation marks (').</span></span>|  
|<span data-ttu-id="aea1e-123">column_name</span><span class="sxs-lookup"><span data-stu-id="aea1e-123">column_name</span></span>|<span data-ttu-id="aea1e-124">Especifica una columna.</span><span class="sxs-lookup"><span data-stu-id="aea1e-124">Specifies a column.</span></span>|  
|<span data-ttu-id="aea1e-125">function</span><span class="sxs-lookup"><span data-stu-id="aea1e-125">function</span></span>|<span data-ttu-id="aea1e-126">Función integrada.</span><span class="sxs-lookup"><span data-stu-id="aea1e-126">A built-in function.</span></span>|  
|<span data-ttu-id="aea1e-127">operator</span><span class="sxs-lookup"><span data-stu-id="aea1e-127">operator</span></span>|<span data-ttu-id="aea1e-128">Operadores aritméticos, bit a bit, de comparación o de cadena.</span><span class="sxs-lookup"><span data-stu-id="aea1e-128">Arithmetic, bitwise, comparison, or string operators.</span></span>|  
|<span data-ttu-id="aea1e-129">y</span><span class="sxs-lookup"><span data-stu-id="aea1e-129">AND</span></span>|<span data-ttu-id="aea1e-130">Se utiliza en expresiones booleanas para conectar dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="aea1e-130">Use in Boolean expressions to connect two expressions.</span></span> <span data-ttu-id="aea1e-131">Se devuelven resultados cuando las dos expresiones son verdaderas.</span><span class="sxs-lookup"><span data-stu-id="aea1e-131">Results are returned when both expressions are true.</span></span><br /><br /> <span data-ttu-id="aea1e-132">Cuando se utilizan los operadores AND y OR en una instrucción, se procesará primero el operador AND.</span><span class="sxs-lookup"><span data-stu-id="aea1e-132">When AND and OR are both used in a statement, AND is processed first.</span></span> <span data-ttu-id="aea1e-133">Puede cambiar el orden de ejecución utilizando paréntesis.</span><span class="sxs-lookup"><span data-stu-id="aea1e-133">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="aea1e-134">O BIEN</span><span class="sxs-lookup"><span data-stu-id="aea1e-134">OR</span></span>|<span data-ttu-id="aea1e-135">Se utiliza en expresiones booleanas para conectar dos o más condiciones.</span><span class="sxs-lookup"><span data-stu-id="aea1e-135">Use in Boolean expressions to connect two or more conditions.</span></span> <span data-ttu-id="aea1e-136">Se devuelven resultados cuando al menos una de las condiciones sea verdadera.</span><span class="sxs-lookup"><span data-stu-id="aea1e-136">Results are returned when either condition is true.</span></span><br /><br /> <span data-ttu-id="aea1e-137">Cuando se utilizan los operadores AND y OR en una instrucción, OR se evaluará después de AND.</span><span class="sxs-lookup"><span data-stu-id="aea1e-137">When AND and OR are both used in a statement, OR is evaluated after AND.</span></span> <span data-ttu-id="aea1e-138">Puede cambiar el orden de ejecución utilizando paréntesis.</span><span class="sxs-lookup"><span data-stu-id="aea1e-138">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="aea1e-139">NOT</span><span class="sxs-lookup"><span data-stu-id="aea1e-139">NOT</span></span>|<span data-ttu-id="aea1e-140">Niega cualquier expresión booleana (que puede incluir palabras clave como LIKE, NULL, BETWEEN, IN y EXISTS).</span><span class="sxs-lookup"><span data-stu-id="aea1e-140">Negates any Boolean expression (which can include keywords, such as LIKE, NULL, BETWEEN, IN, and EXISTS).</span></span><br /><br /> <span data-ttu-id="aea1e-141">Cuando se utiliza más de un operador lógico en una instrucción, se procesará primero el operador NOT.</span><span class="sxs-lookup"><span data-stu-id="aea1e-141">When more than one logical operator is used in a statement, NOT is processed first.</span></span> <span data-ttu-id="aea1e-142">Puede cambiar el orden de ejecución utilizando paréntesis.</span><span class="sxs-lookup"><span data-stu-id="aea1e-142">You can change the order of execution by using parentheses.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aea1e-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aea1e-143">See Also</span></span>  
 <span data-ttu-id="aea1e-144">[Restricciones UNIQUE y restricciones check](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="aea1e-144">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="aea1e-145">Crear restricciones UNIQUE</span><span class="sxs-lookup"><span data-stu-id="aea1e-145">Create Unique Constraints</span></span>](../../relational-databases/tables/create-unique-constraints.md)  
  
  
