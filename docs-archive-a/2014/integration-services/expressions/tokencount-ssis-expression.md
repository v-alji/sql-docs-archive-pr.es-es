---
title: TOKENCOUNT (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c0efed1-c2b3-4f20-a3a1-ad91283b7c0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9068e4958570a0222bc8e1a4c90d34acc5bdf3dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746340"
---
# <a name="tokencount-ssis-expression"></a><span data-ttu-id="4df60-102">TOKENCOUNT (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="4df60-102">TOKENCOUNT (SSIS Expression)</span></span>
  <span data-ttu-id="4df60-103">Devuelve el número de tokens en una cadena que contiene los tokens separados por los delimitadores especificados.</span><span class="sxs-lookup"><span data-stu-id="4df60-103">Returns the number of tokens in a string that contains tokens separated by the specified delimiters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4df60-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4df60-104">Syntax</span></span>  
  
```  
TOKENCOUNT(character_expression, delimiter_string)  
```  
  
## <a name="arguments"></a><span data-ttu-id="4df60-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4df60-105">Arguments</span></span>  
 <span data-ttu-id="4df60-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="4df60-106">*character_expression*</span></span>  
 <span data-ttu-id="4df60-107">Cadena que contiene los tokens separados por delimitadores.</span><span class="sxs-lookup"><span data-stu-id="4df60-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="4df60-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="4df60-108">*delimiter_string*</span></span>  
 <span data-ttu-id="4df60-109">Cadena que contiene caracteres delimitadores.</span><span class="sxs-lookup"><span data-stu-id="4df60-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="4df60-110">Por ejemplo, “; ,” contiene tres caracteres delimitadores: punto y coma, un espacio en blanco y una coma.</span><span class="sxs-lookup"><span data-stu-id="4df60-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4df60-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="4df60-111">Result Types</span></span>  
 <span data-ttu-id="4df60-112">DT_I4</span><span class="sxs-lookup"><span data-stu-id="4df60-112">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4df60-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4df60-113">Remarks</span></span>  
 <span data-ttu-id="4df60-114">Las observaciones siguientes se aplican a la función TOKEN:</span><span class="sxs-lookup"><span data-stu-id="4df60-114">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="4df60-115">La cadena delimitadora puede contener uno o más caracteres delimitadores.</span><span class="sxs-lookup"><span data-stu-id="4df60-115">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="4df60-116">Los delimitadores iniciales se omiten.</span><span class="sxs-lookup"><span data-stu-id="4df60-116">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="4df60-117">TOKENCOUNT funciona solo con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="4df60-117">TOKENCOUNT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="4df60-118">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR se convertirá implícitamente al tipo de datos DT_WSTR antes de que TOKEN realice su operación.</span><span class="sxs-lookup"><span data-stu-id="4df60-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="4df60-119">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="4df60-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="4df60-120">TOKENCOUNT devuelve 0 (cero) si character_expression es NULL.</span><span class="sxs-lookup"><span data-stu-id="4df60-120">TOKENCOUNT returns 0 (zero) if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="4df60-121">Puede usar variables y columnas como argumentos de esta expresión.</span><span class="sxs-lookup"><span data-stu-id="4df60-121">You can use variables and columns as arguments for this expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="4df60-122">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="4df60-122">Expression Examples</span></span>  
 <span data-ttu-id="4df60-123">En el ejemplo siguiente, la función TOKENCOUNT devuelve 3 porque la cadena contiene tres tokens: “01”, “12”, “2011”.</span><span class="sxs-lookup"><span data-stu-id="4df60-123">In the following example, the TOKENCOUNT function returns 3 because the string contains three tokens: "01", "12", "2011".</span></span>  
  
```  
TOKENCOUNT("01/12/2011", "/")  
```  
  
 <span data-ttu-id="4df60-124">En el ejemplo siguiente, la función TOKENCOUNT devuelve 4 porque hay cuatro tokens (“a”, “little”, “white”, “dog”).</span><span class="sxs-lookup"><span data-stu-id="4df60-124">In the following example, the TOKENCOUNT function returns 4 because there are four tokens ("a", "little", "white", "dog").</span></span>  
  
```  
TOKENCOUNT("a little white dog"," ")  
```  
  
 <span data-ttu-id="4df60-125">En el ejemplo siguiente, la función TOKENCOUNT devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="4df60-125">In the following example, the TOKENCOUNT function returns 1.</span></span> <span data-ttu-id="4df60-126">La función analiza la cadena de entrada para los delimitadores y, como hay ninguno en la cadena, simplemente agrega la cadena completa como primer token.</span><span class="sxs-lookup"><span data-stu-id="4df60-126">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKENCOUNT("a little white dog","|")  
```  
  
 <span data-ttu-id="4df60-127">En el ejemplo siguiente, la función TOKENCOUNT devuelve 4.</span><span class="sxs-lookup"><span data-stu-id="4df60-127">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="4df60-128">La cadena delimitadora en este ejemplo contiene 5 delimitadores.</span><span class="sxs-lookup"><span data-stu-id="4df60-128">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="4df60-129">La cadena de entrada contiene 4 tokens: “a”, “little”, “white”, “dog”.</span><span class="sxs-lookup"><span data-stu-id="4df60-129">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKENCOUNT("a:little|white dog","| ,.:")  
```  
  
 <span data-ttu-id="4df60-130">En el ejemplo siguiente, la función TOKENCOUNT devuelve 4.</span><span class="sxs-lookup"><span data-stu-id="4df60-130">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="4df60-131">Omite todos los caracteres de espacio iniciales.</span><span class="sxs-lookup"><span data-stu-id="4df60-131">It ignores all the leading space characters.</span></span>  
  
```  
TOKENCOUNT("        a little white dog", " ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="4df60-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4df60-132">See Also</span></span>  
 [<span data-ttu-id="4df60-133">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="4df60-133">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
