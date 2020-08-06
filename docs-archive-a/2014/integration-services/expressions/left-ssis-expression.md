---
title: LEFT (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5634dbfb-740d-4c93-8fd5-2854cc741327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f21d134988414c7d8579d720877feec45383270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676058"
---
# <a name="left-ssis-expression"></a><span data-ttu-id="3d283-102">LEFT (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="3d283-102">LEFT (SSIS Expression)</span></span>
  <span data-ttu-id="3d283-103">Devuelve el número de caracteres especificado de la parte más a la izquierda de la expresión de caracteres dada.</span><span class="sxs-lookup"><span data-stu-id="3d283-103">Returns the specified number of characters from the leftmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d283-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d283-104">Syntax</span></span>  
  
```  
  
LEFT(character_expression,number)  
```  
  
## <a name="arguments"></a><span data-ttu-id="3d283-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3d283-105">Arguments</span></span>  
 <span data-ttu-id="3d283-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="3d283-106">*character_expression*</span></span>  
 <span data-ttu-id="3d283-107">Expresión de caracteres de la que se van a extraer caracteres.</span><span class="sxs-lookup"><span data-stu-id="3d283-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="3d283-108">*número*</span><span class="sxs-lookup"><span data-stu-id="3d283-108">*number*</span></span>  
 <span data-ttu-id="3d283-109">Expresión entera que indica el número de caracteres que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="3d283-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3d283-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="3d283-110">Result Types</span></span>  
 <span data-ttu-id="3d283-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="3d283-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d283-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3d283-112">Remarks</span></span>  
 <span data-ttu-id="3d283-113">Si *number* es mayor que la longitud de *character_expression*, la función devuelve *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="3d283-113">If *number* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="3d283-114">Si el valor de *number* es cero, la función devuelve una cadena de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="3d283-114">If *number* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="3d283-115">Si el valor de *number* es un número negativo, la función devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="3d283-115">If *number* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="3d283-116">El argumento *number* admite variables y columnas.</span><span class="sxs-lookup"><span data-stu-id="3d283-116">The *number* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="3d283-117">LEFT solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="3d283-117">LEFT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="3d283-118">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR se convertirá implícitamente al tipo de datos DT_WSTR antes de que LEFT realice su operación.</span><span class="sxs-lookup"><span data-stu-id="3d283-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LEFT performs its operation.</span></span> <span data-ttu-id="3d283-119">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="3d283-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="3d283-120">Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="3d283-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="3d283-121">LEFT devuelve un resultado NULL si alguno de los argumentos es NULL.</span><span class="sxs-lookup"><span data-stu-id="3d283-121">LEFT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3d283-122">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="3d283-122">Expression Examples</span></span>  
 <span data-ttu-id="3d283-123">En el siguiente ejemplo se utiliza un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="3d283-123">The following example uses a string literal.</span></span> <span data-ttu-id="3d283-124">El resultado devuelto es `"Mountain"`.</span><span class="sxs-lookup"><span data-stu-id="3d283-124">The return result is `"Mountain"`.</span></span>  
  
```  
LEFT("Mountain Bike", 8)  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d283-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d283-125">See Also</span></span>  
 <span data-ttu-id="3d283-126">[RIGHT &#40;expresión de SSIS&#41;](right-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="3d283-126">[RIGHT &#40;SSIS Expression&#41;](right-ssis-expression.md) </span></span>  
 [<span data-ttu-id="3d283-127">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3d283-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
