---
title: '!= (Diferente) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- unequal operator (!=)
- '!= (not equal to)'
ms.assetid: fad20e85-c0e6-42bf-af70-2bc80ee09be5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: be3eadbac77d76a2b3aac9555d9f40cb56e38949
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746335"
---
# <a name="-unequal-ssis-expression"></a><span data-ttu-id="73449-102">!= (Diferente) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="73449-102">!= (Unequal) (SSIS Expression)</span></span>
  <span data-ttu-id="73449-103">Realiza una comparación para determinar si dos expresiones con tipos de datos compatibles no son iguales.</span><span class="sxs-lookup"><span data-stu-id="73449-103">Performs a comparison to determine if two expressions with compatible data types are not equal.</span></span> <span data-ttu-id="73449-104">El evaluador de expresiones convierte automáticamente muchos tipos de datos antes de realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="73449-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
 <span data-ttu-id="73449-105">Sin embargo, algunos tipos de datos requieren que la expresión incluya una conversión explícita para que se pueda evaluar correctamente.</span><span class="sxs-lookup"><span data-stu-id="73449-105">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="73449-106">Para más información sobre conversiones válidas entre tipos de datos, vea [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="73449-106">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73449-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73449-107">Syntax</span></span>  
  
```  
  
expression1 != expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="73449-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="73449-108">Arguments</span></span>  
 <span data-ttu-id="73449-109">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="73449-109">*expression1, expression2*</span></span>  
 <span data-ttu-id="73449-110">Es cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="73449-110">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="73449-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="73449-111">Result Types</span></span>  
 <span data-ttu-id="73449-112">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="73449-112">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73449-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73449-113">Remarks</span></span>  
 <span data-ttu-id="73449-114">Si una de las expresiones de la comparación es NULL, el resultado de la comparación es NULL.</span><span class="sxs-lookup"><span data-stu-id="73449-114">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="73449-115">Si ambas expresiones son NULL, el resultado es NULL.</span><span class="sxs-lookup"><span data-stu-id="73449-115">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="73449-116">El conjunto de expresiones *expression1* y *expression2*debe cumplir una de las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="73449-116">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="73449-117">\**Numeric\*\*\*expression1* y *expression2* deben ser un tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="73449-117">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="73449-118">La intersección de los tipos de datos debe ser un tipo de datos numérico, tal como se especifica en las reglas para las conversiones numéricas implícitas que realiza el evaluador de expresiones.</span><span class="sxs-lookup"><span data-stu-id="73449-118">The intersection of the data types must be a numeric data type, as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="73449-119">La intersección de dos tipos de datos numéricos no puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="73449-119">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="73449-120">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="73449-120">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="73449-121">\**Character\*\*\*expression1* y *expression2* deben devolver un tipo de datos DT_STR o DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="73449-121">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="73449-122">Las dos expresiones pueden tener tipos de datos de cadena distintos.</span><span class="sxs-lookup"><span data-stu-id="73449-122">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="73449-123">En las comparaciones de cadenas se distingue mayúsculas de minúsculas, caracteres acentuados, tipos de kana y el ancho.</span><span class="sxs-lookup"><span data-stu-id="73449-123">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="73449-124">\**Date, Time o Date/Time\*\*\*expression1* y *expression2* deben devolver uno de los siguientes tipos de datos: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET o DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="73449-124">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="73449-125">El sistema no admite comparaciones entre una expresión que devuelve un tipo de datos de hora y una expresión que devuelve un tipo de datos de fecha o de fecha/hora.</span><span class="sxs-lookup"><span data-stu-id="73449-125">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="73449-126">El sistema genera un error.</span><span class="sxs-lookup"><span data-stu-id="73449-126">The system generates an error.</span></span>  
  
     <span data-ttu-id="73449-127">Al comparar expresiones, el sistema aplica las reglas de conversión siguientes en el orden enumerado:</span><span class="sxs-lookup"><span data-stu-id="73449-127">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="73449-128">Cuando las dos expresiones devuelven el mismo tipo de datos, se realiza una comparación de ese tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="73449-128">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="73449-129">Si una expresión es un tipo de datos DT_DBTIMESTAMPOFFSET, la otra expresión se convierte en DT_DBTIMESTAMPOFFSET implícitamente y se realiza una comparación de DT_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="73449-129">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="73449-130">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="73449-130">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="73449-131">Si una expresión es un tipo de datos DT_DBTIMESTAMP2, la otra expresión se convierte en DT_DBTIMESTAMP2 implícitamente y se realiza una comparación de DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="73449-131">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="73449-132">Si una expresión es un tipo de datos DT_DBTIME2, la otra expresión se convierte en DT_DBTIME2 implícitamente y se realiza una comparación de DT_DBTIME2.</span><span class="sxs-lookup"><span data-stu-id="73449-132">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="73449-133">Si una expresión es de un tipo de datos que no es DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 o DT_DBTIME2, las expresiones se convierten en el tipo de datos DT_DBTIMESTAMP antes de compararse.</span><span class="sxs-lookup"><span data-stu-id="73449-133">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="73449-134">Al comparar las expresiones, el sistema hace las suposiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="73449-134">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="73449-135">Si cada expresión es un tipo de datos que incluye fracciones de segundo, el sistema supone que el tipo de datos con el menor número de dígitos por fracciones de segundo tiene ceros para los dígitos restantes.</span><span class="sxs-lookup"><span data-stu-id="73449-135">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="73449-136">Si cada expresión es un tipo de datos de fecha, pero solo una tiene un ajuste de zona horaria, el sistema supone que el tipo de datos de fecha sin ajuste de zona horaria está en hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="73449-136">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
-   <span data-ttu-id="73449-137">\**Logical\*\*\*expression1* y *expression2* deben devolver un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="73449-137">**Logical** Both *expression1* and *expression2* must evaluate to a Boolean.</span></span>  
  
-   <span data-ttu-id="73449-138">\**GUID\*\*\*expression1* y *expression2* han de devolver un tipo de datos DT_GUID.</span><span class="sxs-lookup"><span data-stu-id="73449-138">**GUID** Both *expression1* and *expression2* must evaluate to the DT_GUID data type.</span></span>  
  
-   <span data-ttu-id="73449-139">\**Binario\*\*\*expression1* y *expression2* han de devolver un tipo de datos DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="73449-139">**Binary** Both *expression1* and *expression2* must evaluate to the DT_BYTES data type.</span></span>  
  
-   <span data-ttu-id="73449-140">\**BLOB\*\*\*expression1* y *expression2* han de devolver el mismo tipo de datos de bloque de objetos binarios grandes (BLOB): DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="73449-140">**BLOB** Both *expression1* and *expression2* must evaluate to the same Binary Large Object Block (BLOB) data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="73449-141">Para obtener más información acerca de los tipos de datos, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="73449-141">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="73449-142">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="73449-142">Expression Examples</span></span>  
 <span data-ttu-id="73449-143">Este ejemplo devuelve TRUE únicamente si la fecha actual no es el 4 de julio de 2003.</span><span class="sxs-lookup"><span data-stu-id="73449-143">This example evaluates to TRUE only if the current date is not July 4, 2003.</span></span> <span data-ttu-id="73449-144">Para obtener más información, consulte [GETDATE &#40;expresión de SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="73449-144">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" != GETDATE()  
```  
  
 <span data-ttu-id="73449-145">Este ejemplo devuelve TRUE si el valor de la columna **ListPrice** no es 500.</span><span class="sxs-lookup"><span data-stu-id="73449-145">This example evaluates to TRUE if the value in the **ListPrice** column is not 500.</span></span>  
  
```  
ListPrice != 500  
```  
  
 <span data-ttu-id="73449-146">Este ejemplo usa la variable **LPrice**.</span><span class="sxs-lookup"><span data-stu-id="73449-146">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="73449-147">Se devuelve TRUE si el valor de **LPrice** no es 500.</span><span class="sxs-lookup"><span data-stu-id="73449-147">It evaluates to TRUE if the value of **LPrice** is not 500.</span></span> <span data-ttu-id="73449-148">El tipo de los datos contenidos en la variable debe ser numérico para que se pueda analizar la expresión.</span><span class="sxs-lookup"><span data-stu-id="73449-148">The data type on the variable must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice != 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="73449-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73449-149">See Also</span></span>  
 <span data-ttu-id="73449-150">[== &#40;Igual&#41; &#40;expresión de SSIS&#41;](equal-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="73449-150">[== &#40;Equal&#41; &#40;SSIS Expression&#41;](equal-ssis-expression.md) </span></span>  
 <span data-ttu-id="73449-151">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="73449-151">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="73449-152">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="73449-152">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
