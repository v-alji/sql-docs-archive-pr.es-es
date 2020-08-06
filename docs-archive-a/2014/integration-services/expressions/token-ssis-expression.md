---
title: TOKEN (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9fdd06bf-5bc9-445c-95bf-709e0ca5989b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5c0598c3832e4bf6f838087be4fee541663c8bff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746344"
---
# <a name="token--ssis-expression"></a><span data-ttu-id="471cd-102">TOKEN (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="471cd-102">TOKEN  (SSIS Expression)</span></span>
  <span data-ttu-id="471cd-103">Devuelve un token (subcadena) de una cadena basándose en los delimitadores especificados que separan los tokens en la cadena y el número del token que indica qué token se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="471cd-103">Returns a token (substring) from a string based on the specified delimiters that separate tokens in the string and the number of the token that denotes which token to be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="471cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="471cd-104">Syntax</span></span>  
  
```  
TOKEN(character_expression, delimiter_string, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="471cd-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="471cd-105">Arguments</span></span>  
 <span data-ttu-id="471cd-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="471cd-106">*character_expression*</span></span>  
 <span data-ttu-id="471cd-107">Cadena que contiene los tokens separados por delimitadores.</span><span class="sxs-lookup"><span data-stu-id="471cd-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="471cd-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="471cd-108">*delimiter_string*</span></span>  
 <span data-ttu-id="471cd-109">Cadena que contiene caracteres delimitadores.</span><span class="sxs-lookup"><span data-stu-id="471cd-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="471cd-110">Por ejemplo, “; ,” contiene tres caracteres delimitadores: punto y coma, un espacio en blanco y una coma.</span><span class="sxs-lookup"><span data-stu-id="471cd-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
 <span data-ttu-id="471cd-111">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="471cd-111">*occurrence*</span></span>  
 <span data-ttu-id="471cd-112">Entero con o sin signo que especifica el token que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="471cd-112">A signed or unsigned integer that specifies the token to be returned.</span></span> <span data-ttu-id="471cd-113">Por ejemplo, si especifica 3 como valor para este parámetro, se devuelve el tercer token de la cadena.</span><span class="sxs-lookup"><span data-stu-id="471cd-113">For example, if you specify 3 as a value for this parameter, the third token in the string is returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="471cd-114">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="471cd-114">Result Types</span></span>  
 <span data-ttu-id="471cd-115">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="471cd-115">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="471cd-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="471cd-116">Remarks</span></span>  
 <span data-ttu-id="471cd-117">Esta función divide la cadena <character_expression> en un conjunto de tokens separados por los delimitadores especificados en <delimiter_string> y devuelve el token número N, donde N es el número de aparición del token especificado por el parámetro \<occurrence>.</span><span class="sxs-lookup"><span data-stu-id="471cd-117">This function splits up the <character_expression> string into a set of tokens separated by the delimiters specified in the <delimiter_string> and then returns the Nth token where N is the number of occurrence of the token specified by the \<occurrence> parameter.</span></span> <span data-ttu-id="471cd-118">Vea la sección Ejemplos para los usos de ejemplo de esta función.</span><span class="sxs-lookup"><span data-stu-id="471cd-118">See Examples section for sample usages of this function.</span></span>  
  
 <span data-ttu-id="471cd-119">Las observaciones siguientes se aplican a la función TOKEN:</span><span class="sxs-lookup"><span data-stu-id="471cd-119">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="471cd-120">La cadena delimitadora puede contener uno o más caracteres delimitadores.</span><span class="sxs-lookup"><span data-stu-id="471cd-120">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="471cd-121">Si el valor del parámetro \<occurrence> es mayor que el número total de tokens de la cadena, la función devuelve NULL.</span><span class="sxs-lookup"><span data-stu-id="471cd-121">If the value of \<occurrence> parameter is higher than the total number of tokens in the string, the function returns NULL.</span></span>  
  
-   <span data-ttu-id="471cd-122">Los delimitadores iniciales se omiten.</span><span class="sxs-lookup"><span data-stu-id="471cd-122">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="471cd-123">TOKEN solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="471cd-123">TOKEN works only with the DT_WSTR data type.</span></span> <span data-ttu-id="471cd-124">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR se convertirá implícitamente al tipo de datos DT_WSTR antes de que TOKEN realice su operación.</span><span class="sxs-lookup"><span data-stu-id="471cd-124">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="471cd-125">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="471cd-125">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="471cd-126">TOKEN devuelve un resultado NULL si el valor de character_expression es NULL.</span><span class="sxs-lookup"><span data-stu-id="471cd-126">TOKEN returns a null result if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="471cd-127">Puede usar variables y columnas como valores de todos los argumentos de la expresión.</span><span class="sxs-lookup"><span data-stu-id="471cd-127">You can use variables and columns as values of all arguments in the expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="471cd-128">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="471cd-128">Expression Examples</span></span>  
 <span data-ttu-id="471cd-129">En el ejemplo siguiente, la función TOKEN devuelve "a".</span><span class="sxs-lookup"><span data-stu-id="471cd-129">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="471cd-130">La cadena “a little white dog” tiene 4 tokens (“a”, “little”, “white” y “dog”) separados por el delimitador “ ” (carácter de espacio).</span><span class="sxs-lookup"><span data-stu-id="471cd-130">The string "a little white dog" has 4 tokens "a", "little", "white", "dog" separated by the delimiter " " (space character).</span></span> <span data-ttu-id="471cd-131">El segundo argumento, una cadena delimitadora, especifica que solo un delimitador, el carácter de espacio, se utiliza en la división de la cadena de entrada en tokens.</span><span class="sxs-lookup"><span data-stu-id="471cd-131">The second argument, a delimiter string, specifies only one delimiter, the space character, to be used in splitting the input string into tokens.</span></span> <span data-ttu-id="471cd-132">El último argumento, 1, especifica que se va a devolver el primer token.</span><span class="sxs-lookup"><span data-stu-id="471cd-132">The last argument, 1, specifies that the first token to be returned.</span></span> <span data-ttu-id="471cd-133">El primer token es “a” en esta cadena de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="471cd-133">The first token is "a" in this sample string.</span></span>  
  
```  
TOKEN("a little white dog"," ",1)  
```  
  
 <span data-ttu-id="471cd-134">En el ejemplo siguiente, la función TOKEN devuelve "dog".</span><span class="sxs-lookup"><span data-stu-id="471cd-134">In the following example, the TOKEN function returns "dog".</span></span> <span data-ttu-id="471cd-135">La cadena delimitadora en este ejemplo contiene 5 delimitadores.</span><span class="sxs-lookup"><span data-stu-id="471cd-135">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="471cd-136">La cadena de entrada contiene 4 tokens: “a”, “little”, “white”, “dog”.</span><span class="sxs-lookup"><span data-stu-id="471cd-136">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKEN("a:little|white dog","| ,.:",4)  
```  
  
 <span data-ttu-id="471cd-137">En el ejemplo siguiente, la función TOKEN devuelve "" (una cadena vacía) porque no hay 99 tokens en la cadena.</span><span class="sxs-lookup"><span data-stu-id="471cd-137">In the following example, the TOKEN function returns "" (an empty string) because there are no 99 tokens in the string.</span></span>  
  
```  
TOKEN("a little white dog"," ",99)  
```  
  
 <span data-ttu-id="471cd-138">En el ejemplo siguiente, la función TOKEN devuelve la cadena completa.</span><span class="sxs-lookup"><span data-stu-id="471cd-138">In the following example, the TOKEN function returns the full string.</span></span> <span data-ttu-id="471cd-139">La función analiza la cadena de entrada para los delimitadores y, como hay ninguno en la cadena, simplemente agrega la cadena completa como primer token.</span><span class="sxs-lookup"><span data-stu-id="471cd-139">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKEN("a little white dog","|",1)  
```  
  
 <span data-ttu-id="471cd-140">En el ejemplo siguiente, la función TOKEN devuelve "a".</span><span class="sxs-lookup"><span data-stu-id="471cd-140">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="471cd-141">Omite todos los caracteres de espacio iniciales.</span><span class="sxs-lookup"><span data-stu-id="471cd-141">It ignores all the leading space characters.</span></span>  
  
```  
TOKEN("        a little white dog", " ", 1)  
```  
  
 <span data-ttu-id="471cd-142">En el ejemplo siguiente, la función TOKEN devuelve el año de una cadena de fecha.</span><span class="sxs-lookup"><span data-stu-id="471cd-142">In the following example, the TOKEN function returns the year from a date string.</span></span>  
  
```  
TOKEN("2009/01/01", "/"), 1  
```  
  
 <span data-ttu-id="471cd-143">En el ejemplo siguiente, la función TOKEN devuelve el nombre de archivo a partir de la ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="471cd-143">In the following example, the TOKEN function returns the file name from the specified path.</span></span> <span data-ttu-id="471cd-144">Por ejemplo, si el valor de User::Path es “C:\Archivos de programa\data\myfile.txt”, la función TOKEN devuelve “myfile.txt”.</span><span class="sxs-lookup"><span data-stu-id="471cd-144">For example, if the value of User::Path is "c:\program files\data\myfile.txt", the TOKEN function returns "myfile.txt".</span></span> <span data-ttu-id="471cd-145">La función TOKENCOUNT devuelve 4 y la función TOKEN devuelve el cuarto token, “myfile.txt”.</span><span class="sxs-lookup"><span data-stu-id="471cd-145">The TOKENCOUNT function returns 4 and the TOKEN function return the 4th token, "myfile.txt".</span></span>  
  
```  
TOKEN(@[User::Path], "\\", TOKENCOUNT(@[User::Path], "\\"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="471cd-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="471cd-146">See Also</span></span>  
 [<span data-ttu-id="471cd-147">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="471cd-147">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
