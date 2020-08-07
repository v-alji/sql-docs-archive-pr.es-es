---
title: + (Concatenar) (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- concatenation [Integration Services]
- + (concatenate operator)
- concatenate operator (+)
ms.assetid: 0fed6334-7a4f-42dc-a611-191fcaa0e443
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1c01f82a50962f42862db836171b0ad683c97453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746390"
---
# <a name="-concatenate-ssis-expression"></a><span data-ttu-id="f724e-102">+ (Concatenar) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="f724e-102">+ (Concatenate) (SSIS Expression)</span></span>
  <span data-ttu-id="f724e-103">Concatena dos expresiones en una expresión.</span><span class="sxs-lookup"><span data-stu-id="f724e-103">Concatenates two expressions into one expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f724e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f724e-104">Syntax</span></span>  
  
```  
  
character_expression1 + character_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f724e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f724e-105">Arguments</span></span>  
 <span data-ttu-id="f724e-106">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="f724e-106">*expression1, expression2*</span></span>  
 <span data-ttu-id="f724e-107">Cualquier expresión válida con tipo de datos DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="f724e-107">Is any valid DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f724e-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="f724e-108">Result Types</span></span>  
 <span data-ttu-id="f724e-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="f724e-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f724e-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f724e-110">Remarks</span></span>  
 <span data-ttu-id="f724e-111">La expresión puede usar los tipos de datos DT_STR y DT_WSTR, o uno de los dos.</span><span class="sxs-lookup"><span data-stu-id="f724e-111">The expression can use either or both of the DT_STR and DT_WSTR data types.</span></span>  
  
 <span data-ttu-id="f724e-112">La concatenación de los tipos de datos DT_STR y DT_WSTR devuelve un resultado de tipo DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="f724e-112">The concatenation of the DT_STR and DT_WSTR data types returns a result of the DT_WSTR type.</span></span> <span data-ttu-id="f724e-113">La longitud de la cadena es la suma de las longitudes de las cadenas originales expresadas en caracteres.</span><span class="sxs-lookup"><span data-stu-id="f724e-113">The length of the string is the sum of the lengths of the original strings expressed in characters.</span></span>  
  
 <span data-ttu-id="f724e-114">Solo se pueden concatenar datos con los tipos de datos de cadena DT_STR y DT_WSTR o con los tipos de datos de bloque de objetos binarios grandes (BLOB) DT_TEXT, DT_NTEXT y DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="f724e-114">Only data with the string data types DT_STR and DT_WSTR or the Binary Large Object Block (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE can be concatenated.</span></span> <span data-ttu-id="f724e-115">Los otros tipos de datos deben convertirse explícitamente en uno de estos tipos de datos antes de que se produzca la concatenación.</span><span class="sxs-lookup"><span data-stu-id="f724e-115">Other data types must be explicitly converted to one of these data types before concatenation occurs.</span></span> <span data-ttu-id="f724e-116">Para más información sobre conversiones válidas entre tipos de datos, vea [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f724e-116">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="f724e-117">Ambas expresiones deben tener el mismo tipo de datos o una expresión debe poder convertirse implícitamente al tipo de datos de la otra expresión.</span><span class="sxs-lookup"><span data-stu-id="f724e-117">Both expressions must be of the same data type, or one expression must be implicitly convertible to the data type of the other expression.</span></span> <span data-ttu-id="f724e-118">Por ejemplo, si se concatena la cadena "Order date is " y la columna **OrderDate** , los valores de **OrderDate** se convierten implícitamente a un tipo de datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="f724e-118">For example, if the string "Order date is " and the column **OrderDate** are concatenated, the values in **OrderDate** are implicitly converted to a string data type.</span></span> <span data-ttu-id="f724e-119">Para concatenar dos valores numéricos, ambos valores deben convertirse explícitamente a un tipo de datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="f724e-119">To concatenate two numeric values, both numeric values must be explicitly cast to a string data type.</span></span>  
  
 <span data-ttu-id="f724e-120">En una concatenación solo se puede usar un tipo de datos BLOB: DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="f724e-120">A concatenation can use only one BLOB data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="f724e-121">Si alguno de los elementos es NULL, el resultado será NULL.</span><span class="sxs-lookup"><span data-stu-id="f724e-121">If either element is null, the result is null.</span></span>  
  
 <span data-ttu-id="f724e-122">Los literales de cadena deben escribirse entre comillas.</span><span class="sxs-lookup"><span data-stu-id="f724e-122">String literals must be enclosed in quotation marks.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="f724e-123">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="f724e-123">Expression Examples</span></span>  
 <span data-ttu-id="f724e-124">Este ejemplo concatena los valores de las columnas **FirstName** y **LastName** e inserta un espacio entre ellos.</span><span class="sxs-lookup"><span data-stu-id="f724e-124">This example concatenates the values in the **FirstName** and **LastName** columns and inserts a space between them.</span></span>  
  
```  
FirstName + ' ' + LastName  
```  
  
 <span data-ttu-id="f724e-125">En este ejemplo se concatenan las variables **ZIPCode** y **ZIPCode+4**.</span><span class="sxs-lookup"><span data-stu-id="f724e-125">This example concatenates the variables **ZIPCode** and **ZIPCode+4**.</span></span> <span data-ttu-id="f724e-126">Ambas variables tienen un tipo de datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="f724e-126">Both variables have a string data type.</span></span> <span data-ttu-id="f724e-127">**ZIPCode+4** debe escribirse entre corchetes porque el nombre de la variable incluye el carácter +.</span><span class="sxs-lookup"><span data-stu-id="f724e-127">**ZIPCode+4** must be enclosed in brackets because the variable name includes the + character.</span></span>  
  
```  
@ZIPCcode + "-" + @[ZipCode+4]  
```  
  
## <a name="see-also"></a><span data-ttu-id="f724e-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f724e-128">See Also</span></span>  
 <span data-ttu-id="f724e-129">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="f724e-129">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="f724e-130">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f724e-130">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
