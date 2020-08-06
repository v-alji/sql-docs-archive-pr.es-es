---
title: Usar operadores en expresiones (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d22dc8b6-4353-40e7-91a1-65e8dae6325d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa8042df39e535425a05414c1e39ee6a12ff2f39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672727"
---
# <a name="operators-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="40a59-102">Usar operadores en expresiones (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="40a59-102">Operators in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="40a59-103">Un operador es un símbolo que representa las acciones que se aplican a uno o a varios términos de una expresión.</span><span class="sxs-lookup"><span data-stu-id="40a59-103">An operator is a symbol that represents actions applied to one or more terms in an expression.</span></span> <span data-ttu-id="40a59-104">En una expresión, se pueden usar las categorías de operadores siguientes: aritméticos, de comparación, de concatenación, lógicos o bit a bit, y de desplazamiento de bits.</span><span class="sxs-lookup"><span data-stu-id="40a59-104">The following categories of operators are supported in an expression: arithmetic, comparison, concatenation, logical or bitwise, and bit shift.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="arithmetic"></a><span data-ttu-id="40a59-105">Aritméticos</span><span class="sxs-lookup"><span data-stu-id="40a59-105">Arithmetic</span></span>  
 <span data-ttu-id="40a59-106">Los operadores aritméticos realizan operaciones matemáticas entre dos términos numéricos de una expresión.</span><span class="sxs-lookup"><span data-stu-id="40a59-106">Arithmetic operators perform mathematical operations on two numeric terms in an expression.</span></span>  
  
|<span data-ttu-id="40a59-107">Operator</span><span class="sxs-lookup"><span data-stu-id="40a59-107">Operator</span></span>|<span data-ttu-id="40a59-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="40a59-108">Description</span></span>|  
|--------------|-----------------|  
|^|<span data-ttu-id="40a59-109">Eleva un número a la potencia de otro número.</span><span class="sxs-lookup"><span data-stu-id="40a59-109">Raises a number to the power of another number.</span></span>|  
|*|<span data-ttu-id="40a59-110">Multiplica dos números.</span><span class="sxs-lookup"><span data-stu-id="40a59-110">Multiplies two numbers.</span></span>|  
|/|<span data-ttu-id="40a59-111">Divide dos números y devuelve un resultado de coma flotante.</span><span class="sxs-lookup"><span data-stu-id="40a59-111">Divides two numbers and returns a floating-point result.</span></span>|  
|<span data-ttu-id="40a59-112">\|Divide dos números y devuelve un resultado de número entero.</span><span class="sxs-lookup"><span data-stu-id="40a59-112">\|Divides two numbers and returns an integer result.</span></span>|  
|<span data-ttu-id="40a59-113">Mod</span><span class="sxs-lookup"><span data-stu-id="40a59-113">Mod</span></span>|<span data-ttu-id="40a59-114">Devuelve el resto entero de una división.</span><span class="sxs-lookup"><span data-stu-id="40a59-114">Returns the integer remainder of a division.</span></span> <span data-ttu-id="40a59-115">Por ejemplo, 7 Mod 5 = 2 porque el resto de 7 dividido entre 5 es 2.</span><span class="sxs-lookup"><span data-stu-id="40a59-115">For example, 7 Mod 5 = 2 because the remainder of 7 divided by 5 is 2.</span></span>|  
|+|<span data-ttu-id="40a59-116">Suma dos números.</span><span class="sxs-lookup"><span data-stu-id="40a59-116">Adds two numbers together.</span></span>|  
|-|<span data-ttu-id="40a59-117">Devuelve la diferencia entre dos números o indica el valor negativo de un término numérico.</span><span class="sxs-lookup"><span data-stu-id="40a59-117">Returns the difference between two numbers or indicates the negative value of a numeric term.</span></span>|  
  
### <a name="comparison"></a><span data-ttu-id="40a59-118">De comparación</span><span class="sxs-lookup"><span data-stu-id="40a59-118">Comparison</span></span>  
 <span data-ttu-id="40a59-119">Los operadores de comparación comprueban si dos expresiones son iguales.</span><span class="sxs-lookup"><span data-stu-id="40a59-119">Comparison operators test whether two expressions are the same.</span></span>  
  
|<span data-ttu-id="40a59-120">Operator</span><span class="sxs-lookup"><span data-stu-id="40a59-120">Operator</span></span>|<span data-ttu-id="40a59-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="40a59-121">Description</span></span>|  
|--------------|-----------------|  
|<|<span data-ttu-id="40a59-122">Menor que.</span><span class="sxs-lookup"><span data-stu-id="40a59-122">Less than.</span></span>|  
|\<=|<span data-ttu-id="40a59-123">Menor o igual que.</span><span class="sxs-lookup"><span data-stu-id="40a59-123">Less than or equal to.</span></span>|  
|>|<span data-ttu-id="40a59-124">Mayor que.</span><span class="sxs-lookup"><span data-stu-id="40a59-124">Greater than.</span></span>|  
|>=|<span data-ttu-id="40a59-125">Mayor o igual que.</span><span class="sxs-lookup"><span data-stu-id="40a59-125">Greater than or equal to.</span></span>|  
|=|<span data-ttu-id="40a59-126">Igual que.</span><span class="sxs-lookup"><span data-stu-id="40a59-126">Equal to.</span></span>|  
|<>|<span data-ttu-id="40a59-127">Diferente de.</span><span class="sxs-lookup"><span data-stu-id="40a59-127">Not equal to.</span></span>|  
|<span data-ttu-id="40a59-128">Like</span><span class="sxs-lookup"><span data-stu-id="40a59-128">Like</span></span>|<span data-ttu-id="40a59-129">Determina si una cadena de caracteres específica coincide con un patrón especificado.</span><span class="sxs-lookup"><span data-stu-id="40a59-129">Determines whether a specific character string matches a specified pattern.</span></span> <span data-ttu-id="40a59-130">Un patrón puede contener caracteres normales y caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="40a59-130">A pattern can include regular characters and wildcard characters.</span></span> <span data-ttu-id="40a59-131">Durante la operación de búsqueda de coincidencias de patrón, los caracteres normales deben coincidir exactamente con los caracteres especificados en la cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="40a59-131">During pattern matching, regular characters must exactly match the characters specified in the character string.</span></span> <span data-ttu-id="40a59-132">Sin embargo, los caracteres comodín pueden coincidir con fragmentos arbitrarios de la cadena.</span><span class="sxs-lookup"><span data-stu-id="40a59-132">However, wildcard characters can be matched with arbitrary fragments of the character string.</span></span> <span data-ttu-id="40a59-133">El uso de caracteres comodín hace que el operador LIKE sea más flexible que los operadores de comparación de cadenas = y !=.</span><span class="sxs-lookup"><span data-stu-id="40a59-133">Using wildcard characters makes the LIKE operator more flexible than using the = and != string comparison operators.</span></span><br /><br /> <span data-ttu-id="40a59-134">A continuación se enumeran los caracteres que se pueden usar como caracteres comodín:</span><span class="sxs-lookup"><span data-stu-id="40a59-134">The following lists characters that can be used as wildcards:</span></span><br /><br /> <span data-ttu-id="40a59-135">**%**: Cualquier cadena de cero o más caracteres.</span><span class="sxs-lookup"><span data-stu-id="40a59-135">**%**: Any string of zero or more characters.</span></span><br /><br /> <span data-ttu-id="40a59-136">**_**: Cualquier carácter individual.</span><span class="sxs-lookup"><span data-stu-id="40a59-136">**_**: Any single character.</span></span><br /><br /> <span data-ttu-id="40a59-137">**[]**: Cualquier carácter individual del intervalo especificado (por ejemplo, [a-f]) o conjunto (por ejemplo, [aeiou]).</span><span class="sxs-lookup"><span data-stu-id="40a59-137">**[ ]**: Any single character within the specified range (for example, [a-f]) or set (for example, [aeiou]).</span></span><br /><br /> <span data-ttu-id="40a59-138">**[^]**: Cualquier carácter individual que no esté dentro del intervalo especificado (por ejemplo, [^ a-f]) o establecido (por ejemplo, [^ aeiou]).</span><span class="sxs-lookup"><span data-stu-id="40a59-138">**[^]**: Any single character not within the specified range (for example, [^a-f]) or set (for example, [^aeiou]).</span></span>|  
|<span data-ttu-id="40a59-139">Is</span><span class="sxs-lookup"><span data-stu-id="40a59-139">Is</span></span>|<span data-ttu-id="40a59-140">Compara dos referencias a objeto.</span><span class="sxs-lookup"><span data-stu-id="40a59-140">Compares two object references.</span></span>|  
  
### <a name="string-concatenation"></a><span data-ttu-id="40a59-141">Concatenación de cadenas</span><span class="sxs-lookup"><span data-stu-id="40a59-141">String Concatenation</span></span>  
 <span data-ttu-id="40a59-142">Los operadores de concatenación de cadenas anexan la segunda cadena a la primera en una expresión.</span><span class="sxs-lookup"><span data-stu-id="40a59-142">String concatenation appends the second string to the first string in an expression.</span></span> <span data-ttu-id="40a59-143">Para las demás operaciones de cadena, use las funciones integradas.</span><span class="sxs-lookup"><span data-stu-id="40a59-143">For other string operations, use built-in functions.</span></span>  
  
|<span data-ttu-id="40a59-144">Operator</span><span class="sxs-lookup"><span data-stu-id="40a59-144">Operator</span></span>|<span data-ttu-id="40a59-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="40a59-145">Description</span></span>|  
|--------------|-----------------|  
|&|<span data-ttu-id="40a59-146">Concatena dos cadenas</span><span class="sxs-lookup"><span data-stu-id="40a59-146">Concatenates two strings</span></span>|  
|+|<span data-ttu-id="40a59-147">Concatena dos cadenas</span><span class="sxs-lookup"><span data-stu-id="40a59-147">Concatenates two strings</span></span>|  
  
### <a name="logical-and-bitwise"></a><span data-ttu-id="40a59-148">Lógicos y bit a bit</span><span class="sxs-lookup"><span data-stu-id="40a59-148">Logical and Bitwise</span></span>  
 <span data-ttu-id="40a59-149">Los operadores lógicos y bit a bit realizan manipulaciones lógicas entre dos términos enteros de una expresión.</span><span class="sxs-lookup"><span data-stu-id="40a59-149">Logical and bitwise operators perform logical manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="40a59-150">Operator</span><span class="sxs-lookup"><span data-stu-id="40a59-150">Operator</span></span>|<span data-ttu-id="40a59-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="40a59-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="40a59-152">And</span><span class="sxs-lookup"><span data-stu-id="40a59-152">And</span></span>|<span data-ttu-id="40a59-153">Realiza una conjunción lógica entre dos expresiones booleanas o una conjunción bit a bit entre dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="40a59-153">Performs a logical conjunction on two Boolean expressions, or bitwise conjunction on two numeric expressions.</span></span>|  
|<span data-ttu-id="40a59-154">Not</span><span class="sxs-lookup"><span data-stu-id="40a59-154">Not</span></span>|<span data-ttu-id="40a59-155">Realiza una negación lógica de una expresión booleana o una negación bit a bit de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="40a59-155">Performs logical negation on a Boolean expression, or bitwise negation on a numeric expression.</span></span>|  
|<span data-ttu-id="40a59-156">Or</span><span class="sxs-lookup"><span data-stu-id="40a59-156">Or</span></span>|<span data-ttu-id="40a59-157">Realiza una disyunción lógica entre dos expresiones booleanas o una disyunción bit a bit entre dos valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="40a59-157">Performs a logical disjunction on two Boolean expressions, or bitwise disjunction on two numeric values.</span></span>|  
|<span data-ttu-id="40a59-158">Xor</span><span class="sxs-lookup"><span data-stu-id="40a59-158">Xor</span></span>|<span data-ttu-id="40a59-159">Realiza una operación de exclusión lógica entre dos expresiones booleanas o una exclusión bit a bit entre dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="40a59-159">Performs a logical exclusion operation on two Boolean expressions, or a bitwise exclusion on two numeric expressions.</span></span>|  
|<span data-ttu-id="40a59-160">AndAlso</span><span class="sxs-lookup"><span data-stu-id="40a59-160">AndAlso</span></span>|<span data-ttu-id="40a59-161">Realiza una conjunción lógica entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="40a59-161">Performs logical conjunction on two expressions.</span></span>|  
|<span data-ttu-id="40a59-162">OrElse</span><span class="sxs-lookup"><span data-stu-id="40a59-162">OrElse</span></span>|<span data-ttu-id="40a59-163">Realiza una disyunción lógica entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="40a59-163">Performs logical disjunction on two expressions.</span></span>|  
  
### <a name="bit-shift"></a><span data-ttu-id="40a59-164">Desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="40a59-164">Bit Shift</span></span>  
 <span data-ttu-id="40a59-165">Los operadores de desplazamiento de bits realizan manipulaciones de bits entre dos términos enteros de una expresión.</span><span class="sxs-lookup"><span data-stu-id="40a59-165">Bitwise operators perform bit manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="40a59-166">Operator</span><span class="sxs-lookup"><span data-stu-id="40a59-166">Operator</span></span>|<span data-ttu-id="40a59-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="40a59-167">Description</span></span>|  
|--------------|-----------------|  
|<\<|<span data-ttu-id="40a59-168">Realiza un desplazamiento aritmético a la izquierda en un patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="40a59-168">Performs an arithmetic left-shift on a bit pattern.</span></span>|  
|>>|<span data-ttu-id="40a59-169">Realiza un desplazamiento aritmético a la derecha en un patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="40a59-169">Performs an arithmetic right-shift on a bit pattern.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40a59-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40a59-170">See Also</span></span>  
 <span data-ttu-id="40a59-171">[Expresión (cuadro de diálogo)](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="40a59-171">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="40a59-172">[Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40a59-172">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="40a59-173">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40a59-173">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="40a59-174">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40a59-174">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="40a59-175">Expresión &#40;cuadro de diálogo del Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="40a59-175">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
