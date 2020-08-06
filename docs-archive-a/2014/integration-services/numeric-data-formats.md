---
title: Formatos de datos numéricos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- integer data types [Integration Services]
- numeric data formats for fast parse
- locale-sensitive parsing [Integration Services]
- fast parse [Integration Services]
ms.assetid: fa3975ce-9d21-408a-857d-f85e30af27b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc54a331c3762e31ba9d9a431aaca7eda6374d8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673086"
---
# <a name="numeric-data-formats"></a><span data-ttu-id="3aedd-102">Formatos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="3aedd-102">Numeric Data Formats</span></span>
  <span data-ttu-id="3aedd-103">El análisis rápido ofrece un conjunto rápido y simple de rutinas, que no distinguen la configuración regional, para analizar datos.</span><span class="sxs-lookup"><span data-stu-id="3aedd-103">Fast parse provides a fast, simple, locale-insensitive set of routines for parsing data.</span></span> <span data-ttu-id="3aedd-104">El análisis rápido admite solo un conjunto limitado de formatos para tipos de datos enteros.</span><span class="sxs-lookup"><span data-stu-id="3aedd-104">Fast parse supports only a limited set of formats for integer data types.</span></span>  
  
## <a name="integer-data-types"></a><span data-ttu-id="3aedd-105">Tipos de datos enteros</span><span class="sxs-lookup"><span data-stu-id="3aedd-105">Integer Data Types</span></span>  
 <span data-ttu-id="3aedd-106">Los tipos de datos enteros que proporciona [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] son DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8 y DT_UI8.</span><span class="sxs-lookup"><span data-stu-id="3aedd-106">The integer data types that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides are DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8, and DT_UI8.</span></span> <span data-ttu-id="3aedd-107">Para obtener más información, vea [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3aedd-107">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="3aedd-108">El análisis rápido admite los siguientes formatos para tipos de datos enteros:</span><span class="sxs-lookup"><span data-stu-id="3aedd-108">Fast parse supports the following formats for integer data types:</span></span>  
  
-   <span data-ttu-id="3aedd-109">Espacios iniciales y finales de cero o superiores o tabulaciones.</span><span class="sxs-lookup"><span data-stu-id="3aedd-109">Zero or more leading and trailing spaces or tab stops.</span></span> <span data-ttu-id="3aedd-110">Por ejemplo, el valor " 123  " es válido.</span><span class="sxs-lookup"><span data-stu-id="3aedd-110">For example, the value "  123  " is valid.</span></span> <span data-ttu-id="3aedd-111">El valor que todo él es espacios equivale a cero.</span><span class="sxs-lookup"><span data-stu-id="3aedd-111">A value that is all spaces evaluates to zero.</span></span>  
  
-   <span data-ttu-id="3aedd-112">Un signo más o menos inicial, o ningún signo inicial.</span><span class="sxs-lookup"><span data-stu-id="3aedd-112">A leading plus sign, minus sign, or neither.</span></span> <span data-ttu-id="3aedd-113">Por ejemplo, los valores +123, -123 y 123 son válidos.</span><span class="sxs-lookup"><span data-stu-id="3aedd-113">For example, the values +123, -123, and 123 are valid.</span></span>  
  
-   <span data-ttu-id="3aedd-114">Uno o más numerales indo-árabes (0-9).</span><span class="sxs-lookup"><span data-stu-id="3aedd-114">One or more Hindu-Arabic numerals (0-9).</span></span> <span data-ttu-id="3aedd-115">Por ejemplo, el valor 345 es válido.</span><span class="sxs-lookup"><span data-stu-id="3aedd-115">For example, the value 345 is valid.</span></span> <span data-ttu-id="3aedd-116">No se admiten numerales de otros idiomas.</span><span class="sxs-lookup"><span data-stu-id="3aedd-116">Other language numerals are not supported.</span></span>  
  
 <span data-ttu-id="3aedd-117">Entre los formatos de datos no admitidos se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3aedd-117">Non-supported data formats include the following:</span></span>  
  
-   <span data-ttu-id="3aedd-118">Caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="3aedd-118">Special characters.</span></span> <span data-ttu-id="3aedd-119">Por ejemplo, el carácter de moneda $ no se admite y el valor $20 no puede analizarse.</span><span class="sxs-lookup"><span data-stu-id="3aedd-119">For example, the currency character $ is not supported, and the value $20 cannot be parsed.</span></span>  
  
-   <span data-ttu-id="3aedd-120">Los caracteres de espacios en blanco como avance de línea, retorno de carro y espacios de no separación.</span><span class="sxs-lookup"><span data-stu-id="3aedd-120">White-space characters such as line feed, carriage returns, and non-breaking spaces.</span></span> <span data-ttu-id="3aedd-121">Por ejemplo, el valor " 123" no puede analizarse.</span><span class="sxs-lookup"><span data-stu-id="3aedd-121">For example, the value " 123" cannot be parsed.</span></span>  
  
-   <span data-ttu-id="3aedd-122">Representaciones hexadecimales de números enteros.</span><span class="sxs-lookup"><span data-stu-id="3aedd-122">Hexadecimal representations of integers.</span></span> <span data-ttu-id="3aedd-123">Por ejemplo, el valor 2EE no puede analizarse.</span><span class="sxs-lookup"><span data-stu-id="3aedd-123">For example, the value 2EE cannot be parsed.</span></span>  
  
-   <span data-ttu-id="3aedd-124">Representaciones en notación científica de números enteros.</span><span class="sxs-lookup"><span data-stu-id="3aedd-124">Scientific notation representation of integers.</span></span> <span data-ttu-id="3aedd-125">Por ejemplo, el valor 1E+10 no puede analizarse.</span><span class="sxs-lookup"><span data-stu-id="3aedd-125">For example, the value 1E+10 cannot be parsed.</span></span>  
  
 <span data-ttu-id="3aedd-126">Los siguientes formatos son datos de salida para números enteros:</span><span class="sxs-lookup"><span data-stu-id="3aedd-126">The following formats are output data formats for integers:</span></span>  
  
-   <span data-ttu-id="3aedd-127">Un signo menos para números negativos y nada para números positivos.</span><span class="sxs-lookup"><span data-stu-id="3aedd-127">A minus sign for negative numbers and nothing for positive ones.</span></span>  
  
-   <span data-ttu-id="3aedd-128">Ningún espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="3aedd-128">No white spaces.</span></span>  
  
-   <span data-ttu-id="3aedd-129">Uno o más numerales indo-árabes (0-9).</span><span class="sxs-lookup"><span data-stu-id="3aedd-129">One or more Hindu-Arabic numerals (0-9).</span></span>  
  
  
