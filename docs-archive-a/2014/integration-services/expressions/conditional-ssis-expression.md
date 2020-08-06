---
title: '? : (Condicional) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- conditional operator (?:)
- '?: (conditional operator)'
ms.assetid: d38e6890-7338-4ce0-a837-2dbb41823a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e607f9ed495184ef47ac2e4f1139b9a9566055ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677224"
---
# <a name="--conditional-ssis-expression"></a><span data-ttu-id="25b94-103">?</span><span class="sxs-lookup"><span data-stu-id="25b94-103">?</span></span> <span data-ttu-id="25b94-104">: (Condicional) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="25b94-104">: (Conditional) (SSIS Expression)</span></span>
  <span data-ttu-id="25b94-105">Devuelve una de dos expresiones en función del resultado de la evaluación de una expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="25b94-105">Returns one of two expressions based on the evaluation of a Boolean expression.</span></span> <span data-ttu-id="25b94-106">Si la evaluación de la expresión booleana devuelve TRUE, se evalúa la primera expresión y el resultado es el resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="25b94-106">If the Boolean expression evaluates to TRUE, then the first expression is evaluated and the result is the expression result.</span></span> <span data-ttu-id="25b94-107">Si devuelve FALSE, se evalúa la segunda expresión y el resultado es el resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="25b94-107">If the Boolean expression evaluates to FALSE then the second expression is evaluated and its result is the expression result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25b94-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25b94-108">Syntax</span></span>  
  
```  
  
boolean_expression?expression1:expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="25b94-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="25b94-109">Arguments</span></span>  
 <span data-ttu-id="25b94-110">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="25b94-110">*boolean_expression*</span></span>  
 <span data-ttu-id="25b94-111">Cualquier expresión válida cuya evaluación devuelva TRUE, FALSE o NULL.</span><span class="sxs-lookup"><span data-stu-id="25b94-111">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
 <span data-ttu-id="25b94-112">*expression1*</span><span class="sxs-lookup"><span data-stu-id="25b94-112">*expression1*</span></span>  
 <span data-ttu-id="25b94-113">Es cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="25b94-113">Is any valid expression.</span></span>  
  
 <span data-ttu-id="25b94-114">*expression2*</span><span class="sxs-lookup"><span data-stu-id="25b94-114">*expression2*</span></span>  
 <span data-ttu-id="25b94-115">Es cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="25b94-115">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="25b94-116">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="25b94-116">Result Types</span></span>  
 <span data-ttu-id="25b94-117">Tipo de datos de *expression1* o *expression2*.</span><span class="sxs-lookup"><span data-stu-id="25b94-117">The data type of *expression1* or *expression2*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25b94-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="25b94-118">Remarks</span></span>  
 <span data-ttu-id="25b94-119">Si el valor *boolean_expression* se evalúa como NULL, el resultado de la expresión es NULL.</span><span class="sxs-lookup"><span data-stu-id="25b94-119">If the *boolean_expression* evaluates to NULL, the expression result is NULL.</span></span> <span data-ttu-id="25b94-120">Si una expresión seleccionada, *expression1* o *expression2* , es NULL, el resultado es NULL.</span><span class="sxs-lookup"><span data-stu-id="25b94-120">If a selected expression, either *expression1* or *expression2* is NULL, the result is NULL.</span></span> <span data-ttu-id="25b94-121">Si la expresión seleccionada no es NULL, pero la expresión no seleccionada es NULL, el resultado será el valor de la expresión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="25b94-121">If a selected expression is not NULL, but the one not selected is NULL, the result is the value of the selected expression.</span></span>  
  
 <span data-ttu-id="25b94-122">Si *expression1* y *expression2* tienen el mismo tipo de datos, el resultado será ese tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="25b94-122">If *expression1* and *expression2* have the same data type, the result is that data type.</span></span> <span data-ttu-id="25b94-123">Además, las reglas siguientes se aplican a los tipos de resultado:</span><span class="sxs-lookup"><span data-stu-id="25b94-123">The following additional rules apply to result types:</span></span>  
  
-   <span data-ttu-id="25b94-124">El tipo de datos DT_TEXT necesita que *expression1* y *expression2* tengan la misma página de código.</span><span class="sxs-lookup"><span data-stu-id="25b94-124">The DT_TEXT data type requires that *expression1* and *expression2* have the same code page.</span></span>  
  
-   <span data-ttu-id="25b94-125">La longitud de un resultado con el tipo de datos DT_BYTES es la del argumento más largo.</span><span class="sxs-lookup"><span data-stu-id="25b94-125">The length of a result with the DT_BYTES data type is the length of the longer argument.</span></span>  
  
 <span data-ttu-id="25b94-126">El conjunto de expresiones, *expression1* y *expression2*, debe tener como resultado tipos de datos válidos y seguir una de estas reglas:</span><span class="sxs-lookup"><span data-stu-id="25b94-126">The expression set, *expression1* and *expression2*, must evaluate to valid data types and follow one of these rules:</span></span>  
  
-   <span data-ttu-id="25b94-127">\**Numeric\*\*\*expression1* y *expression2* deben ser un tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="25b94-127">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="25b94-128">La intersección de los tipos de datos debe ser un tipo de datos numérico, tal como se especifica en las reglas para las conversiones numéricas implícitas que realiza el evaluador de expresiones.</span><span class="sxs-lookup"><span data-stu-id="25b94-128">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="25b94-129">La intersección de dos tipos de datos numéricos no puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="25b94-129">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="25b94-130">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="25b94-130">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="25b94-131">\**Cadena\*\*\*expression1* y *expression2* deben tener un tipo de datos de cadena: DT_STR o DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="25b94-131">**String** Both *expression1* and *expression2* must be a string data type: DT_STR or DT_WSTR.</span></span> <span data-ttu-id="25b94-132">Las dos expresiones pueden tener tipos de datos de cadena distintos.</span><span class="sxs-lookup"><span data-stu-id="25b94-132">The two expressions can evaluate to different string data types.</span></span> <span data-ttu-id="25b94-133">El resultado tiene el tipo de datos DT_WSTR con la longitud del argumento más largo.</span><span class="sxs-lookup"><span data-stu-id="25b94-133">The result has the DT_WSTR data type with a length of the longer argument.</span></span>  
  
-   <span data-ttu-id="25b94-134">\**Date, Time o Date/Time\*\*\*expression1* y *expression2* deben devolver uno de los siguientes tipos de datos: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET o DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="25b94-134">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="25b94-135">El sistema no admite comparaciones entre una expresión que devuelve un tipo de datos de hora y una expresión que devuelve un tipo de datos de fecha o de fecha/hora.</span><span class="sxs-lookup"><span data-stu-id="25b94-135">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="25b94-136">El sistema genera un error.</span><span class="sxs-lookup"><span data-stu-id="25b94-136">The system generates an error.</span></span>  
  
     <span data-ttu-id="25b94-137">Al comparar expresiones, el sistema aplica las reglas de conversión siguientes en el orden enumerado:</span><span class="sxs-lookup"><span data-stu-id="25b94-137">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="25b94-138">Cuando las dos expresiones devuelven el mismo tipo de datos, se realiza una comparación de ese tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="25b94-138">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="25b94-139">Si una expresión es un tipo de datos DT_DBTIMESTAMPOFFSET, la otra expresión se convierte en DT_DBTIMESTAMPOFFSET implícitamente y se realiza una comparación de DT_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="25b94-139">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="25b94-140">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="25b94-140">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="25b94-141">Si una expresión es un tipo de datos DT_DBTIMESTAMP2, la otra expresión se convierte en DT_DBTIMESTAMP2 implícitamente y se realiza una comparación de DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="25b94-141">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="25b94-142">Si una expresión es un tipo de datos DT_DBTIME2, la otra expresión se convierte en DT_DBTIME2 implícitamente y se realiza una comparación de DT_DBTIME2.</span><span class="sxs-lookup"><span data-stu-id="25b94-142">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="25b94-143">Si una expresión es de un tipo de datos que no es DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 o DT_DBTIME2, las expresiones se convierten en el tipo de datos DT_DBTIMESTAMP antes de compararse.</span><span class="sxs-lookup"><span data-stu-id="25b94-143">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="25b94-144">Al comparar las expresiones, el sistema hace las suposiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="25b94-144">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="25b94-145">Si cada expresión es un tipo de datos que incluye fracciones de segundo, el sistema supone que el tipo de datos con el menor número de dígitos por fracciones de segundo tiene ceros para los dígitos restantes.</span><span class="sxs-lookup"><span data-stu-id="25b94-145">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="25b94-146">Si cada expresión es un tipo de datos de fecha, pero solo una tiene un ajuste de zona horaria, el sistema supone que el tipo de datos de fecha sin ajuste de zona horaria está en hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="25b94-146">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="25b94-147">Para obtener más información acerca de los tipos de datos, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="25b94-147">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="25b94-148">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="25b94-148">Expression Examples</span></span>  
 <span data-ttu-id="25b94-149">En este ejemplo se muestra una expresión que se evalúa condicionalmente como `savannah` o `unknown`.</span><span class="sxs-lookup"><span data-stu-id="25b94-149">This example shows an expression that conditionally evaluates to `savannah` or `unknown`.</span></span>  
  
```  
@AnimalName == "Elephant"? "savannah": "unknown"  
```  
  
 <span data-ttu-id="25b94-150">En este ejemplo se muestra una expresión que hace referencia a una columna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="25b94-150">This example shows an expression that references a **ListPrice** column.</span></span> <span data-ttu-id="25b94-151">**ListPrice** tiene el tipo de datos DT_CY.</span><span class="sxs-lookup"><span data-stu-id="25b94-151">**ListPrice** has the DT_CY data type.</span></span> <span data-ttu-id="25b94-152">La expresión multiplica condicionalmente **ListPrice** por 0,2 o 0,1.</span><span class="sxs-lookup"><span data-stu-id="25b94-152">The expression conditionally multiplies **ListPrice** by .2 or .1.</span></span>  
  
```  
ListPrice < 350.00 ? ListPrice * .2 : ListPrice * .1  
```  
  
## <a name="see-also"></a><span data-ttu-id="25b94-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25b94-153">See Also</span></span>  
 <span data-ttu-id="25b94-154">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="25b94-154">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="25b94-155">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="25b94-155">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
