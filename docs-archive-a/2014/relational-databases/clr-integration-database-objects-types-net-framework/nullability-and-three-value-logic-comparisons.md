---
title: Nulabilidad y comparaciones lógicas de tres valores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- precision [CLR integration]
- overflow detections [CLR integration]
- null values [CLR integration]
- three-value logic comparisons [CLR integration]
- data types [CLR integration]
- SqlBoolean data type
ms.assetid: 13da4c7f-1010-4b2d-a63c-c69b6bfd96f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b8000c1c28d5a1d3d129b6e8d01c4ab2fbbbc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751170"
---
# <a name="nullability-and-three-value-logic-comparisons"></a><span data-ttu-id="f3798-102">Nulabilidad y comparaciones lógicas de tres valores</span><span class="sxs-lookup"><span data-stu-id="f3798-102">Nullability and Three-Value Logic Comparisons</span></span>
  <span data-ttu-id="f3798-103">Si está familiarizado con los tipos de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], observará una semántica y precisión similares en el espacio de nombres `System.Data.SqlTypes` de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3798-103">If you are familiar with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, you will find similar semantics and precision in the `System.Data.SqlTypes` namespace in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="f3798-104">No obstante, existen algunas diferencias, y en este tema se describen las más importantes.</span><span class="sxs-lookup"><span data-stu-id="f3798-104">There are some differences, however, and this topic covers the most important of these differences.</span></span>  
  
## <a name="null-values"></a><span data-ttu-id="f3798-105">Valores NULL</span><span class="sxs-lookup"><span data-stu-id="f3798-105">NULL Values</span></span>  
 <span data-ttu-id="f3798-106">Una de las diferencias principales que existen entre los tipos de datos nativos de Common Language Runtime (CLR) y los tipos de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es que los primeros no permiten valores NULL, mientras que los últimos proporcionan una semántica completa de valores NULL.</span><span class="sxs-lookup"><span data-stu-id="f3798-106">A primary difference between native common language runtime (CLR) data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types is that the former do not allow for NULL values, while the latter provide full NULL semantics.</span></span>  
  
 <span data-ttu-id="f3798-107">Los valores NULL afectan a las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="f3798-107">Comparisons are affected by NULL values.</span></span> <span data-ttu-id="f3798-108">Al comparar dos valores x e y, si alguno de los dos es NULL, hay una serie de comparaciones lógicas que se evalúan como un valor UNKNOWN en lugar de como True o False.</span><span class="sxs-lookup"><span data-stu-id="f3798-108">When comparing two values x and y, if either x or y is NULL, then some logical comparisons evaluate to an UNKNOWN value rather than true or false.</span></span>  
  
## <a name="sqlboolean-data-type"></a><span data-ttu-id="f3798-109">Tipo de datos SqlBoolean</span><span class="sxs-lookup"><span data-stu-id="f3798-109">SqlBoolean Data Type</span></span>  
 <span data-ttu-id="f3798-110">El espacio de nombres `System.Data.SqlTypes` introduce un tipo `SqlBoolean` para representar esta lógica de 3 valores.</span><span class="sxs-lookup"><span data-stu-id="f3798-110">The `System.Data.SqlTypes` namespace introduces a `SqlBoolean` type to represent this 3-value logic.</span></span> <span data-ttu-id="f3798-111">Las comparaciones entre `SqlTypes` devuelven un tipo de valor `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="f3798-111">Comparisons between any `SqlTypes` return a `SqlBoolean` value type.</span></span> <span data-ttu-id="f3798-112">El valor UNKNOWN se representa mediante un valor NULL de tipo `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="f3798-112">The UNKNOWN value is represented by the null value of the `SqlBoolean` type.</span></span> <span data-ttu-id="f3798-113">Las propiedades `IsTrue`, `IsFalse` e `IsNull` se proporcionan para comprobar el valor de un tipo `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="f3798-113">The properties `IsTrue`, `IsFalse`, and `IsNull` are provided to check the value of a `SqlBoolean` type.</span></span>  
  
## <a name="operations-functions-and-null-values"></a><span data-ttu-id="f3798-114">Operaciones, funciones y valores NULL</span><span class="sxs-lookup"><span data-stu-id="f3798-114">Operations, Functions, and NULL Values</span></span>  
 <span data-ttu-id="f3798-115">Todos los operadores aritméticos (+,-, \* ,/,%), los operadores bit a bit (~, & y |) y la mayoría de las funciones devuelven NULL si alguno de los operandos o argumentos de `SqlTypes` es NULL.</span><span class="sxs-lookup"><span data-stu-id="f3798-115">All arithmetic operators (+, -, \*, /, %), bitwise operators (~, &, and |), and most functions return NULL if any of the operands or arguments of `SqlTypes` are NULL.</span></span> <span data-ttu-id="f3798-116">La propiedad `IsNull` siempre devuelve un valor True o False.</span><span class="sxs-lookup"><span data-stu-id="f3798-116">The `IsNull` property always returns a true or false value.</span></span>  
  
## <a name="precision"></a><span data-ttu-id="f3798-117">Precisión</span><span class="sxs-lookup"><span data-stu-id="f3798-117">Precision</span></span>  
 <span data-ttu-id="f3798-118">Los tipos de datos decimales de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR tienen distintos valores máximos que los de los tipos de datos numéricos y decimales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3798-118">Decimal data types in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR have different maximum values than those of the numeric and decimal data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f3798-119">Además, en [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR, los tipos de datos decimales asumen la precisión máxima.</span><span class="sxs-lookup"><span data-stu-id="f3798-119">In addition, in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR decimal data types assume the maximum precision.</span></span> <span data-ttu-id="f3798-120">Sin embargo, en CLR para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SqlDecimal` proporciona la misma precisión máxima, la misma escala máxima y la misma semántica que el tipo de datos decimal de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3798-120">In the CLR for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], however, `SqlDecimal` provides the same maximum precision and scale, and the same semantics as the decimal data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="overflow-detection"></a><span data-ttu-id="f3798-121">Detección de desbordamiento</span><span class="sxs-lookup"><span data-stu-id="f3798-121">Overflow Detection</span></span>  
 <span data-ttu-id="f3798-122">En [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR, la suma de dos números muy grandes no puede iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="f3798-122">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR, the addition of two very large numbers may not throw an exception.</span></span> <span data-ttu-id="f3798-123">En lugar de ello, si no se ha utilizado ningún operador de comprobación, el resultado devuelto puede "ajustarse" como un número entero negativo.</span><span class="sxs-lookup"><span data-stu-id="f3798-123">Instead, if no check operator has been used, the returned result may "wrap around" as a negative integer.</span></span> <span data-ttu-id="f3798-124">En `System.Data.SqlTypes`, se inician excepciones para todos los errores de desbordamiento, subdesbordamiento y división por cero.</span><span class="sxs-lookup"><span data-stu-id="f3798-124">In `System.Data.SqlTypes`, exceptions are thrown for all overflow and underflow errors, and divide-by-zero errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3798-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3798-125">See Also</span></span>  
 [<span data-ttu-id="f3798-126">Tipos de datos de SQL Server en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3798-126">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
