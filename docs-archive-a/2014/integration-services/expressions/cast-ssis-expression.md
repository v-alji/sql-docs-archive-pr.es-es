---
title: Conversión (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CAST function
- cast operator
- converting data types [Integration Services]
- data types [Integration Services], expressions
- data types [Integration Services], converting
ms.assetid: d4e915cc-1c7b-4b2e-93b0-13a8b0cb9242
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65d60eca4340b65b8a82855c3f2b29a6cda56e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748218"
---
# <a name="cast-ssis-expression"></a><span data-ttu-id="c5f83-102">Conversión (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="c5f83-102">Cast (SSIS Expression)</span></span>
  <span data-ttu-id="c5f83-103">Convierte explícitamente una expresión de un tipo de datos a otro.</span><span class="sxs-lookup"><span data-stu-id="c5f83-103">Explicitly converts an expression from one data type to a different data type.</span></span> <span data-ttu-id="c5f83-104">El operador de conversión también puede funcionar como un operador de truncamiento.</span><span class="sxs-lookup"><span data-stu-id="c5f83-104">The cast operator can also function as a truncation operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="c5f83-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5f83-105">Syntax</span></span>

```

(type_spec) expression

```

## <a name="arguments"></a><span data-ttu-id="c5f83-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c5f83-106">Arguments</span></span>
 <span data-ttu-id="c5f83-107">*type_spec* Es un [!INCLUDE[ssIS](../../includes/ssis-md.md)] tipo de datos válido.</span><span class="sxs-lookup"><span data-stu-id="c5f83-107">*type_spec* Is a valid [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span>

 <span data-ttu-id="c5f83-108">*expresión* de Es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="c5f83-108">*expression* Is a valid expression.</span></span>

## <a name="result-types"></a><span data-ttu-id="c5f83-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="c5f83-109">Result Types</span></span>
 <span data-ttu-id="c5f83-110">El tipo de datos de *type_spec*.</span><span class="sxs-lookup"><span data-stu-id="c5f83-110">The data type of *type_spec*.</span></span> <span data-ttu-id="c5f83-111">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c5f83-111">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="c5f83-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c5f83-112">Remarks</span></span>
 <span data-ttu-id="c5f83-113">El siguiente diagrama muestra operaciones de conversión válidas.</span><span class="sxs-lookup"><span data-stu-id="c5f83-113">The following diagram shows legal cast operations.</span></span>

 <span data-ttu-id="c5f83-114">![Conversiones válidas y no válidas entre tipos de datos](../media/data-conversion.gif "Conversiones válidas y no válidas entre tipos de datos")</span><span class="sxs-lookup"><span data-stu-id="c5f83-114">![Legal and not legal casts between data types](../media/data-conversion.gif "Legal and not legal casts between data types")</span></span>

 <span data-ttu-id="c5f83-115">La conversión a algunos tipos de datos requiere parámetros.</span><span class="sxs-lookup"><span data-stu-id="c5f83-115">Casting to some data types requires parameters.</span></span> <span data-ttu-id="c5f83-116">En la tabla siguiente se muestran estos tipos de datos y sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="c5f83-116">The following table lists these data types and their parameters.</span></span>

|<span data-ttu-id="c5f83-117">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c5f83-117">Data type</span></span>|<span data-ttu-id="c5f83-118">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c5f83-118">Parameter</span></span>|<span data-ttu-id="c5f83-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5f83-119">Example</span></span>|
|---------------|---------------|-------------|
|<span data-ttu-id="c5f83-120">DT_STR</span><span class="sxs-lookup"><span data-stu-id="c5f83-120">DT_STR</span></span>|<span data-ttu-id="c5f83-121">*charCount*</span><span class="sxs-lookup"><span data-stu-id="c5f83-121">*charcount*</span></span><br /><br /> <span data-ttu-id="c5f83-122">*737*</span><span class="sxs-lookup"><span data-stu-id="c5f83-122">*codepage*</span></span>|<span data-ttu-id="c5f83-123">(DT_STR,30,1252) convierte 30 bytes, o 30 caracteres individuales, al tipo de datos DT_STR con la página de códigos 1252.</span><span class="sxs-lookup"><span data-stu-id="c5f83-123">(DT_STR,30,1252) casts 30 bytes, or 30 single characters, to the DT_STR data type using the 1252 code page.</span></span>|
|<span data-ttu-id="c5f83-124">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="c5f83-124">DT_WSTR</span></span>|<span data-ttu-id="c5f83-125">*CharCount*</span><span class="sxs-lookup"><span data-stu-id="c5f83-125">*Charcount*</span></span>|<span data-ttu-id="c5f83-126">(DT_WSTR,20) convierte 20 pares de bytes, o 20 caracteres Unicode, al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c5f83-126">(DT_WSTR,20) casts 20 byte pairs, or 20 Unicode characters, to the DT_WSTR data type.</span></span>|
|<span data-ttu-id="c5f83-127">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="c5f83-127">DT_BYTES</span></span>|<span data-ttu-id="c5f83-128">*ByteCount*</span><span class="sxs-lookup"><span data-stu-id="c5f83-128">*Bytecount*</span></span>|<span data-ttu-id="c5f83-129">(DT_BYTES,50) convierte 50 bytes al tipo de datos DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="c5f83-129">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|
|<span data-ttu-id="c5f83-130">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="c5f83-130">DT_DECIMAL</span></span>|<span data-ttu-id="c5f83-131">*Escala*</span><span class="sxs-lookup"><span data-stu-id="c5f83-131">*Scale*</span></span>|<span data-ttu-id="c5f83-132">(DT_DECIMAL,2) convierte un valor numérico al tipo de datos DT_DECIMAL con una escala de 2.</span><span class="sxs-lookup"><span data-stu-id="c5f83-132">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|
|<span data-ttu-id="c5f83-133">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="c5f83-133">DT_NUMERIC</span></span>|<span data-ttu-id="c5f83-134">*Precisión*</span><span class="sxs-lookup"><span data-stu-id="c5f83-134">*Precision*</span></span><br /><br /> <span data-ttu-id="c5f83-135">*Escala*</span><span class="sxs-lookup"><span data-stu-id="c5f83-135">*Scale*</span></span>|<span data-ttu-id="c5f83-136">(DT_NUMERIC,10,3) convierte un valor numérico al tipo de datos DT_NUMERIC con una precisión de 10 decimales y una escala de 3.</span><span class="sxs-lookup"><span data-stu-id="c5f83-136">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|
|<span data-ttu-id="c5f83-137">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="c5f83-137">DT_TEXT</span></span>|<span data-ttu-id="c5f83-138">*737*</span><span class="sxs-lookup"><span data-stu-id="c5f83-138">*Codepage*</span></span>|<span data-ttu-id="c5f83-139">(DT_TEXT,1252) convierte un valor al tipo de datos DT_TEXT con la página de códigos 1252.</span><span class="sxs-lookup"><span data-stu-id="c5f83-139">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|

 <span data-ttu-id="c5f83-140">Cuando se convierte una cadena al tipo de datos DT_DATE, o viceversa, se usa la configuración regional de la transformación.</span><span class="sxs-lookup"><span data-stu-id="c5f83-140">When a string is cast to a DT_DATE, or vice versa, the locale of the transformation is used.</span></span> <span data-ttu-id="c5f83-141">Sin embargo, la fecha está en el formato ISO de AAAA-MM-DD, sin tener en cuenta si la preferencia de la configuración regional utiliza el formato ISO.</span><span class="sxs-lookup"><span data-stu-id="c5f83-141">However, the date is in the ISO format of YYYY-MM-DD, regardless of whether the locale preference uses the ISO format.</span></span>

> [!NOTE]
>  <span data-ttu-id="c5f83-142">Para convertir una cadena en un tipo de datos de fecha que no sea DT_DATE, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c5f83-142">To convert a string to a date data type other than DT_DATE, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="c5f83-143">Si la página de códigos es una página de códigos de caracteres multibyte, el número de bytes y caracteres puede diferir.</span><span class="sxs-lookup"><span data-stu-id="c5f83-143">If the code page is a multibyte character code page, the number of bytes and characters may differ.</span></span> <span data-ttu-id="c5f83-144">La conversión de DT_WSTR a DT_STR con el mismo valor de *charcount* puede provocar el truncamiento de los caracteres finales de la cadena convertida.</span><span class="sxs-lookup"><span data-stu-id="c5f83-144">Casting from a DT_WSTR to a DT_STR with the same *charcount* value may cause truncation of the final characters in the converted string.</span></span> <span data-ttu-id="c5f83-145">Si hay suficiente espacio de almacenamiento en la columna de la tabla de destino, establezca el valor del parámetro *charcount* de modo que refleje el número de bytes requeridos por la página de códigos multibyte.</span><span class="sxs-lookup"><span data-stu-id="c5f83-145">If sufficient storage is available in the column of the destination table, set the value of the *charcount* parameter to reflect the number of bytes that the multibyte code page requires.</span></span> <span data-ttu-id="c5f83-146">Por ejemplo, si convierte datos de caracteres a un tipo de datos DT_STR con la página de códigos 936, debe establecer el valor de *charcount* en un valor hasta dos veces mayor que el número de caracteres que espera que contengan los datos; si convierte datos de caracteres mediante la página de códigos UTF-8, debe establecer *charcount* en un valor hasta cuatro veces mayor.</span><span class="sxs-lookup"><span data-stu-id="c5f83-146">For example, if you cast character data to a DT_STR data type using the 936 code page, you should set *charcount* to a value up to two times greater than the number of characters that you expect the data to contain; if you cast character data using the UTF-8 code page, you should set *charcount* to a value up to four times greater.</span></span>

 <span data-ttu-id="c5f83-147">Para obtener más información sobre la estructura de los tipos de datos de fecha, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c5f83-147">For more information about the structure of date data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="ssis-expression-examples"></a><span data-ttu-id="c5f83-148">Ejemplos de expresiones de SSIS</span><span class="sxs-lookup"><span data-stu-id="c5f83-148">SSIS Expression Examples</span></span>
 <span data-ttu-id="c5f83-149">Este ejemplo convierte un valor numérico en un entero.</span><span class="sxs-lookup"><span data-stu-id="c5f83-149">This example casts a numeric value to an integer.</span></span>

```
(DT_I4) 3.57
```

 <span data-ttu-id="c5f83-150">Este ejemplo convierte un entero en una cadena de caracteres con la página de códigos 1252.</span><span class="sxs-lookup"><span data-stu-id="c5f83-150">This example casts an integer to a character string using the 1252 code page.</span></span>

```
(DT_STR,1,1252)5
```

 <span data-ttu-id="c5f83-151">Este ejemplo convierte una cadena de tres caracteres en caracteres de doble byte.</span><span class="sxs-lookup"><span data-stu-id="c5f83-151">This example casts a three-character string to double-byte characters.</span></span>

```
(DT_WSTR,3)"Cat"
```

 <span data-ttu-id="c5f83-152">Este ejemplo convierte un entero en un decimal con una escala de dos.</span><span class="sxs-lookup"><span data-stu-id="c5f83-152">This example casts an integer to a decimal with a scale of two.</span></span>

```
(DT_DECIMAl,2)500
```

 <span data-ttu-id="c5f83-153">Este ejemplo convierte un entero en un valor numérico con una precisión de siete y una escala de tres.</span><span class="sxs-lookup"><span data-stu-id="c5f83-153">This example casts an integer to a numeric with a precision of seven and scale of three.</span></span>

```
(DT_NUMERIC,7,3)4000
```

 <span data-ttu-id="c5f83-154">En este ejemplo se convierten los valores de la columna **FirstName** , definida con un tipo de datos **nvarchar** y una longitud de 50, en una cadena de caracteres que usa la página de códigos 1252.</span><span class="sxs-lookup"><span data-stu-id="c5f83-154">This example casts values in the **FirstName** column, defined with an **nvarchar** data type and a length of 50, to a character string using the 1252 code page.</span></span>

```
(DT_STR,50,1252)FirstName
```

 <span data-ttu-id="c5f83-155">En este ejemplo se convierten valores de la columna **DateFirstPurchase** de tipo DT_DBDATE a una cadena de caracteres Unicode con una longitud de 20.</span><span class="sxs-lookup"><span data-stu-id="c5f83-155">This example casts values in the **DateFirstPurchase** column of type DT_DBDATE, to a Unicode character string with a length of 20.</span></span>

```
(DT_WSTR,20)DateFirstPurchase
```

 <span data-ttu-id="c5f83-156">Este ejemplo convierte el literal de cadena "True" en un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="c5f83-156">This example casts the string literal "True" to a Boolean.</span></span>

```
(DT_BOOL)"True"
```

 <span data-ttu-id="c5f83-157">En este ejemplo se convierte un literal de cadena en DT_DBDATE.</span><span class="sxs-lookup"><span data-stu-id="c5f83-157">This example casts a string literal to DT_DBDATE.</span></span>

```
(DT_DBDATE) "1999-10-11"
```

 <span data-ttu-id="c5f83-158">En este ejemplo se convierte un literal de cadena en el tipo de datos DT_DBTIME2 que utiliza 5 dígitos para las fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="c5f83-158">This example casts a string literal to the DT_DBTIME2 data type that uses 5 digits for fractional seconds.</span></span> <span data-ttu-id="c5f83-159">(El tipo de datos DT_DBTIME2 puede tener entre 0 y 7 dígitos especificados para las fracciones de segundo.)</span><span class="sxs-lookup"><span data-stu-id="c5f83-159">(The DT_DBTIME2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIME2, 5) "16:34:52.12345"
```

 <span data-ttu-id="c5f83-160">En este ejemplo se convierte un literal de cadena en el tipo de datos DT_DBTIMESTAMP2 que utiliza 4 dígitos para las fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="c5f83-160">This example casts a string literal to the DT_DBTIMESTAMP2 data type that uses 4 digits for fractional seconds.</span></span> <span data-ttu-id="c5f83-161">(El tipo de datos DT_DBTIMESTAMP2 puede tener entre 0 y 7 dígitos especificados para las fracciones de segundo.)</span><span class="sxs-lookup"><span data-stu-id="c5f83-161">(The DT_DBTIMESTAMP2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMP2, 4) "1999-10-11 16:34:52.1234"
```

 <span data-ttu-id="c5f83-162">En este ejemplo se convierte un literal de cadena en el tipo de datos DT_DBTIMESTAMPOFFSET que utiliza 7 dígitos para las fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="c5f83-162">This example casts a string literal to the DT_DBTIMESTAMPOFFSET data type that uses 7 digits for fractional seconds.</span></span> <span data-ttu-id="c5f83-163">(El tipo de datos DT_DBTIMESTAMPOFFSET puede tener entre 0 y 7 dígitos especificados para las fracciones de segundo.)</span><span class="sxs-lookup"><span data-stu-id="c5f83-163">(The DT_DBTIMESTAMPOFFSET data typecan have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMPOFFSET, 7) "1999-10-11 16:34:52.1234567 + 5:35"
```

## <a name="see-also"></a><span data-ttu-id="c5f83-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5f83-164">See Also</span></span>
 <span data-ttu-id="c5f83-165">Operadores de [precedencia y asociatividad de operadores](operator-precedence-and-associativity.md) [&#40;expresión de ssis&#41;](operators-ssis-expression.md) [Integration Services &#40;expresiones de&#41; de SSIS](integration-services-ssis-expressions.md) [Integration Services tipos de datos en expresiones](integration-services-data-types-in-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="c5f83-165">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md)</span></span>


