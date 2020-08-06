---
title: '&lt;= (Menor o igual que) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- <= (less than or equal to operator)
- less than or equal to operator (<=)
ms.assetid: 946c5630-dccf-4dae-9cfd-6ea823641ab2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1c0b5ef0a8467cedbc5e390b42f3307cceb7c75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671590"
---
# <a name="lt-less-than-or-equal-to-ssis-expression"></a><span data-ttu-id="1107c-102">&lt;= (Menor o igual que) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="1107c-102">&lt;= (Less Than or Equal To) (SSIS Expression)</span></span>
  <span data-ttu-id="1107c-103">Realiza una comparación para determinar si la primera expresión es menor o igual que la segunda.</span><span class="sxs-lookup"><span data-stu-id="1107c-103">Performs a comparison to determine if the first expression is less than or equal to the second one.</span></span> <span data-ttu-id="1107c-104">El evaluador de expresiones convierte automáticamente muchos tipos de datos antes de realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="1107c-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1107c-105">Este operador no admite comparaciones que usen los tipos de datos DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="1107c-105">This operator does not support comparisons that use the DT_TEXT, DT_NTEXT, or DT_IMAGE data types.</span></span>  
  
 <span data-ttu-id="1107c-106">Sin embargo, algunos tipos de datos requieren que la expresión incluya una conversión explícita para que se pueda evaluar correctamente.</span><span class="sxs-lookup"><span data-stu-id="1107c-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="1107c-107">Para más información sobre conversiones válidas entre tipos de datos, vea [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="1107c-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1107c-108">No hay espacios entre los dos caracteres de este operador.</span><span class="sxs-lookup"><span data-stu-id="1107c-108">There are no spaces between the two characters in this operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1107c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1107c-109">Syntax</span></span>  
  
```  
  
expression1 <= expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1107c-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1107c-110">Arguments</span></span>  
 <span data-ttu-id="1107c-111">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="1107c-111">*expression1, expression2*</span></span>  
 <span data-ttu-id="1107c-112">Es cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="1107c-112">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1107c-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="1107c-113">Result Types</span></span>  
 <span data-ttu-id="1107c-114">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="1107c-114">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1107c-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1107c-115">Remarks</span></span>  
 <span data-ttu-id="1107c-116">Si una de las expresiones de la comparación es NULL, el resultado de la comparación es NULL.</span><span class="sxs-lookup"><span data-stu-id="1107c-116">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="1107c-117">Si ambas expresiones son NULL, el resultado es NULL.</span><span class="sxs-lookup"><span data-stu-id="1107c-117">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="1107c-118">El conjunto de expresiones *expression1* y *expression2*debe cumplir una de las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="1107c-118">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="1107c-119">\**Numeric\*\*\*expression1* y *expression2* deben ser un tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="1107c-119">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="1107c-120">La intersección de los tipos de datos debe ser un tipo de datos numérico, tal como se especifica en las reglas para las conversiones numéricas implícitas que realiza el evaluador de expresiones.</span><span class="sxs-lookup"><span data-stu-id="1107c-120">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="1107c-121">La intersección de dos tipos de datos numéricos no puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="1107c-121">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="1107c-122">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1107c-122">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="1107c-123">\**Character\*\*\*expression1* y *expression2* deben devolver un tipo de datos DT_STR o DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="1107c-123">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="1107c-124">Las dos expresiones pueden tener tipos de datos de cadena distintos.</span><span class="sxs-lookup"><span data-stu-id="1107c-124">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1107c-125">En las comparaciones de cadenas se distingue mayúsculas de minúsculas, caracteres acentuados, tipos de kana y el ancho.</span><span class="sxs-lookup"><span data-stu-id="1107c-125">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="1107c-126">\**Date, Time o Date/Time\*\*\*expression1* y *expression2* deben devolver uno de los siguientes tipos de datos: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET o DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="1107c-126">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1107c-127">El sistema no admite comparaciones entre una expresión que devuelve un tipo de datos de hora y una expresión que devuelve un tipo de datos de fecha o de fecha/hora.</span><span class="sxs-lookup"><span data-stu-id="1107c-127">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="1107c-128">El sistema genera un error.</span><span class="sxs-lookup"><span data-stu-id="1107c-128">The system generates an error.</span></span>  
  
     <span data-ttu-id="1107c-129">Al comparar expresiones, el sistema aplica las reglas de conversión siguientes en el orden enumerado:</span><span class="sxs-lookup"><span data-stu-id="1107c-129">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="1107c-130">Cuando las dos expresiones devuelven el mismo tipo de datos, se realiza una comparación de ese tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="1107c-130">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="1107c-131">Si una expresión es un tipo de datos DT_DBTIMESTAMPOFFSET, la otra expresión se convierte en DT_DBTIMESTAMPOFFSET implícitamente y se realiza una comparación de DT_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="1107c-131">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="1107c-132">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1107c-132">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="1107c-133">Si una expresión es un tipo de datos DT_DBTIMESTAMP2, la otra expresión se convierte en DT_DBTIMESTAMP2 implícitamente y se realiza una comparación de DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="1107c-133">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="1107c-134">Si una expresión es un tipo de datos DT_DBTIME2, la otra expresión se convierte en DT_DBTIME2 implícitamente y se realiza una comparación de DT_DBTIME2.</span><span class="sxs-lookup"><span data-stu-id="1107c-134">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="1107c-135">Si una expresión es de un tipo de datos que no es DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 o DT_DBTIME2, las expresiones se convierten en el tipo de datos DT_DBTIMESTAMP antes de compararse.</span><span class="sxs-lookup"><span data-stu-id="1107c-135">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="1107c-136">Al comparar las expresiones, el sistema hace las suposiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1107c-136">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="1107c-137">Si cada expresión es un tipo de datos que incluye fracciones de segundo, el sistema supone que el tipo de datos con el menor número de dígitos por fracciones de segundo tiene ceros para los dígitos restantes.</span><span class="sxs-lookup"><span data-stu-id="1107c-137">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="1107c-138">Si cada expresión es un tipo de datos de fecha, pero solo una tiene un ajuste de zona horaria, el sistema supone que el tipo de datos de fecha sin ajuste de zona horaria está en hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="1107c-138">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="1107c-139">Para obtener más información acerca de los tipos de datos, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1107c-139">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="1107c-140">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="1107c-140">Expression Examples</span></span>  
 <span data-ttu-id="1107c-141">Este ejemplo devuelve TRUE si la fecha actual es el 4 de julio de 2003 o una fecha posterior.</span><span class="sxs-lookup"><span data-stu-id="1107c-141">This example evaluates to TRUE if the current date is July 4, 2003 or later.</span></span> <span data-ttu-id="1107c-142">Para obtener más información, consulte [GETDATE &#40;expresión de SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="1107c-142">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" <= GETDATE()  
```  
  
 <span data-ttu-id="1107c-143">Este ejemplo devuelve TRUE si el valor de la columna **ListPrice** es menor o igual que 500.</span><span class="sxs-lookup"><span data-stu-id="1107c-143">This example evaluates to TRUE if the value in the **ListPrice** column is less than or equal to 500.</span></span>  
  
```  
ListPrice <= 500  
```  
  
 <span data-ttu-id="1107c-144">Este ejemplo evalúa la variable **LPrice** y devuelve TRUE si su valor es menor o igual que 500.</span><span class="sxs-lookup"><span data-stu-id="1107c-144">This example evaluates the variable **LPrice** and evaluates to TRUE if the value is less than or equal to 500.</span></span> <span data-ttu-id="1107c-145">El tipo de datos de la variable **LPrice** debe ser numérico para que se pueda analizar la expresión.</span><span class="sxs-lookup"><span data-stu-id="1107c-145">The data type of **LPrice** must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice <= 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="1107c-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1107c-146">See Also</span></span>  
 <span data-ttu-id="1107c-147">[&#62; &#40;Mayor que&#41; &#40;expresión de SSIS&#41;](greater-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1107c-147">[&#62; &#40;Greater Than&#41; &#40;SSIS Expression&#41;](greater-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="1107c-148">[&#60; &#40;Menor que&#41; &#40;expresión de SSIS&#41;](less-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1107c-148">[&#60; &#40;Less Than&#41; &#40;SSIS Expression&#41;](less-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="1107c-149">[&#62;= &#40;Mayor o igual que&#41; &#40;expresión de SSIS&#41;](greater-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1107c-149">[&#62;= &#40;Greater Than or Equal To&#41; &#40;SSIS Expression&#41;](greater-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="1107c-150">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="1107c-150">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="1107c-151">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1107c-151">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  