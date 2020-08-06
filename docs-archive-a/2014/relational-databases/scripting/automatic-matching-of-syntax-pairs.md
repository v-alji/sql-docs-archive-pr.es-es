---
title: Coincidencia automática de pares en la sintaxis
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], delimiter highlighting
- IntelliSense [SQL Server], syntax pair matching
ms.assetid: bfc54cda-bfd6-4545-a5b9-f9db2ae13769
author: rothja
ms.author: jroth
ms.openlocfilehash: d1237eeb9aaec39e3210b00c880c0005ef3d95bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671457"
---
# <a name="automatic-matching-of-syntax-pairs"></a><span data-ttu-id="492a9-102">Coincidencia automática de pares en la sintaxis</span><span class="sxs-lookup"><span data-stu-id="492a9-102">Automatic Matching of Syntax Pairs</span></span>
  <span data-ttu-id="492a9-103">La coincidencia automática de pares en la sintaxis informa de manera inmediata sobre si están escritos correctamente los elementos de sintaxis que deben ir emparejados en el código.</span><span class="sxs-lookup"><span data-stu-id="492a9-103">Automatic matching of syntax pairs gives you immediate feedback on whether syntax elements that must be coded in pairs are correctly paired.</span></span> <span data-ttu-id="492a9-104">Esto se conoce como coincidencia de delimitadores en el Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] , coincidencia de llaves en el Editor de consultas XMLA de Analysis Services y coincidencia de paréntesis en los editores MDX y DMX.</span><span class="sxs-lookup"><span data-stu-id="492a9-104">This is known as delimiter matching in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor, brace matching in the Analysis Services XMLA Query Editor, and parenthesis matching in the MDX and DMX editors.</span></span>  
  
## <a name="database-engine-query-editor-delimiter-matching"></a><span data-ttu-id="492a9-105">Coincidencia de delimitadores del Editor de consultas de Database Engine</span><span class="sxs-lookup"><span data-stu-id="492a9-105">Database Engine Query Editor Delimiter Matching</span></span>  
 <span data-ttu-id="492a9-106">El Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] comprueba si coinciden los delimitadores que identifican los límites de los bloques de código.</span><span class="sxs-lookup"><span data-stu-id="492a9-106">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor matches the delimiters that identify the boundaries of code blocks.</span></span> <span data-ttu-id="492a9-107">La comprobación de coincidencia se hace de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="492a9-107">The matching is done in two ways:</span></span>  
  
-   <span data-ttu-id="492a9-108">El editor resalta los dos delimitadores de un par cuando se termina de escribir el segundo delimitador del par.</span><span class="sxs-lookup"><span data-stu-id="492a9-108">The editor highlights both delimiters in a pair when you finish typing the second delimiter in the pair.</span></span>  
  
-   <span data-ttu-id="492a9-109">Siempre que el cursor está en uno de los delimitadores de un par, puede utilizar el método abreviado de teclado CTRL+] para saltar al delimitador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="492a9-109">Anytime the cursor is in one of the delimiters in a pair, you can use the CTRL+] keyboard shortcut to jump to the matching delimiter.</span></span>  
  
### <a name="delimiter-pairs"></a><span data-ttu-id="492a9-110">Pares de delimitadores</span><span class="sxs-lookup"><span data-stu-id="492a9-110">Delimiter Pairs</span></span>  
 <span data-ttu-id="492a9-111">La coincidencia automática de delimitadores reconoce los conjuntos de delimitadores siguientes:</span><span class="sxs-lookup"><span data-stu-id="492a9-111">Automatic delimiter matching recognizes the following sets of delimiters:</span></span>  
  
|<span data-ttu-id="492a9-112">Delimitador de apertura</span><span class="sxs-lookup"><span data-stu-id="492a9-112">Lead Delimiter</span></span>|<span data-ttu-id="492a9-113">Delimitador de cierre</span><span class="sxs-lookup"><span data-stu-id="492a9-113">Closing Delimiter</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="492a9-114">**(**</span><span class="sxs-lookup"><span data-stu-id="492a9-114">**(**</span></span>|<span data-ttu-id="492a9-115">**)**</span><span class="sxs-lookup"><span data-stu-id="492a9-115">**)**</span></span>|  
|<span data-ttu-id="492a9-116">**BEGIN**</span><span class="sxs-lookup"><span data-stu-id="492a9-116">**BEGIN**</span></span>|<span data-ttu-id="492a9-117">**END**</span><span class="sxs-lookup"><span data-stu-id="492a9-117">**END**</span></span>|  
|<span data-ttu-id="492a9-118">**BEGIN TRY**</span><span class="sxs-lookup"><span data-stu-id="492a9-118">**BEGIN TRY**</span></span>|<span data-ttu-id="492a9-119">**END TRY**</span><span class="sxs-lookup"><span data-stu-id="492a9-119">**END TRY**</span></span>|  
|<span data-ttu-id="492a9-120">**BEGIN CATCH**</span><span class="sxs-lookup"><span data-stu-id="492a9-120">**BEGIN CATCH**</span></span>|<span data-ttu-id="492a9-121">**END CATCH**</span><span class="sxs-lookup"><span data-stu-id="492a9-121">**END CATCH**</span></span>|  
  
 <span data-ttu-id="492a9-122">La coincidencia automática de delimitadores no reconoce los delimitadores de los identificadores entre corchetes ([ObjectName]) ni los de los identificadores entre comillas ("ObjectName").</span><span class="sxs-lookup"><span data-stu-id="492a9-122">Automatic delimiter matching does not recognize the delimiters for bracketed identifiers ([ObjectName]), or quoted identifiers ("ObjectName").</span></span> <span data-ttu-id="492a9-123">La coincidencia de pares no hace coincidir los delimitadores de comillas simples para los literales de cadena ('cadena') porque la codificación en colores ya proporciona una indicación visual de si se ha delimitado la cadena.</span><span class="sxs-lookup"><span data-stu-id="492a9-123">Pair matching does not match the single quotation delimiters for string literals ('string') because color coding already gives a visual indication of whether the string has been delimited.</span></span>  
  
### <a name="delimiter-highlighting"></a><span data-ttu-id="492a9-124">Resaltado de delimitadores</span><span class="sxs-lookup"><span data-stu-id="492a9-124">Delimiter Highlighting</span></span>  
 <span data-ttu-id="492a9-125">La coincidencia resalta el elemento de apertura y el de cierre de un par de delimitadores.</span><span class="sxs-lookup"><span data-stu-id="492a9-125">Matching highlights both the lead and closing element of a pair of delimiters.</span></span> <span data-ttu-id="492a9-126">Esto permite identificar visualmente los bloques de código y comprobar si hay pares de delimitadores que no coinciden.</span><span class="sxs-lookup"><span data-stu-id="492a9-126">This lets you visually identify code blocks and check for mismatched pairs of delimiters.</span></span>  
  
 <span data-ttu-id="492a9-127">Los delimitadores se resaltan cuando se escribe la última letra que completa el par.</span><span class="sxs-lookup"><span data-stu-id="492a9-127">Delimiters are highlighted when you type the final letter that completes the pair.</span></span> <span data-ttu-id="492a9-128">Por ejemplo, para un par BEGIN END en el que se escribe primero BEGIN seguido de END, el resaltado se activa cuando se escribe la última letra de END.</span><span class="sxs-lookup"><span data-stu-id="492a9-128">For example, for a BEGIN END pair where you type BEGIN first followed by END, highlighting turns on when you type the final letter in END.</span></span> <span data-ttu-id="492a9-129">No es necesario escribir el delimitador de apertura seguido del delimitador de cierre para activar el resaltado.</span><span class="sxs-lookup"><span data-stu-id="492a9-129">You do not have to type the lead delimiter followed by the closing delimiter to turn on highlighting.</span></span> <span data-ttu-id="492a9-130">Si escribe primero END y, a continuación, se desplaza hacia arriba en el script y escribe BEGIN, el resaltado se activa en cuanto escriba la última letra de BEGIN.</span><span class="sxs-lookup"><span data-stu-id="492a9-130">If you type END first, then scroll back up the script and type BEGIN, highlighting is turned on when you type the final letter in BEGIN.</span></span> <span data-ttu-id="492a9-131">No es necesario que la última letra escrita sea la última letra del delimitador.</span><span class="sxs-lookup"><span data-stu-id="492a9-131">The final letter typed does not have to be the end letter in the delimiter.</span></span> <span data-ttu-id="492a9-132">Por ejemplo, si se equivoca y escribe BEIN en lugar de BEGIN, al insertar la G se resaltará el par BEGIN END.</span><span class="sxs-lookup"><span data-stu-id="492a9-132">For example, you could misspell BEGIN as BEIN, when you insert the final G the BEGIN END pair is highlighted.</span></span>  
  
 <span data-ttu-id="492a9-133">El par de delimitadores sigue estando resaltado hasta que mueva el cursor.</span><span class="sxs-lookup"><span data-stu-id="492a9-133">The delimiter pair remains highlighted until you move the cursor.</span></span> <span data-ttu-id="492a9-134">El resaltado se desactiva cuando se mueve el cursor, incluso si la nueva posición del cursor permanece en el mismo delimitador.</span><span class="sxs-lookup"><span data-stu-id="492a9-134">The highlighting is turned off when the cursor is moved, even if the new cursor position remains in the same delimiter.</span></span> <span data-ttu-id="492a9-135">Puede volver a activar el resaltado si borra y vuelve a escribir cualquier letra de cualquiera de los miembros del par.</span><span class="sxs-lookup"><span data-stu-id="492a9-135">You can turn the highlighting back on by deleting and retyping any letter in either member of the pair.</span></span>  
  
## <a name="analysis-services-xmla-query-editor-brace-matching"></a><span data-ttu-id="492a9-136">Coincidencia de llaves del Editor de consultas XMLA de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="492a9-136">Analysis Services XMLA Query Editor Brace Matching</span></span>  
 <span data-ttu-id="492a9-137">La coincidencia de llaves del Editor de consultas XMLA de Analysis Services resalta las llaves de apertura y de cierre para indicar si se han cerrado correctamente los elementos.</span><span class="sxs-lookup"><span data-stu-id="492a9-137">The XMLA Query Editor brace matching shows if you have closed elements by highlighting opening and closing braces.</span></span> <span data-ttu-id="492a9-138">También puede utilizar el método abreviado de teclado CTRL+] para saltar de una llave a la llave correspondiente.</span><span class="sxs-lookup"><span data-stu-id="492a9-138">You can also use the CTRL+] keyboard shortcut to jump from one brace to the matching brace.</span></span>  
  
 <span data-ttu-id="492a9-139">El Editor de consultas XMLA comprueba si coinciden las llaves para los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="492a9-139">The XMLA Query Editor does brace matching for the following terms:</span></span>  
  
-   <span data-ttu-id="492a9-140">Etiquetas de inicio y de cierre coincidentes.</span><span class="sxs-lookup"><span data-stu-id="492a9-140">Matching start and end tags.</span></span>  
  
-   <span data-ttu-id="492a9-141">Cualquier par de \<" and "> corchetes angulares "".</span><span class="sxs-lookup"><span data-stu-id="492a9-141">Any pair of "\<" and ">" angle brackets.</span></span>  
  
-   <span data-ttu-id="492a9-142">Principio y final de los comentarios.</span><span class="sxs-lookup"><span data-stu-id="492a9-142">Start and end of comments.</span></span>  
  
-   <span data-ttu-id="492a9-143">Principio y final de las instrucciones de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="492a9-143">Start and end of processing instructions.</span></span>  
  
-   <span data-ttu-id="492a9-144">Principio y final de los bloques CDATA.</span><span class="sxs-lookup"><span data-stu-id="492a9-144">Start and end of CDATA blocks.</span></span>  
  
-   <span data-ttu-id="492a9-145">Principio y final de las declaraciones DTD.</span><span class="sxs-lookup"><span data-stu-id="492a9-145">Start and end of DTD declarations.</span></span>  
  
-   <span data-ttu-id="492a9-146">Comillas de apertura y de cierre en los atributos.</span><span class="sxs-lookup"><span data-stu-id="492a9-146">Opening and closing quotes on attributes.</span></span>  
  
## <a name="mdx-and-dmx-editor-parenthesis-matching"></a><span data-ttu-id="492a9-147">Coincidencia de paréntesis de los editores MDX y DMX</span><span class="sxs-lookup"><span data-stu-id="492a9-147">MDX and DMX Editor Parenthesis Matching</span></span>  
 <span data-ttu-id="492a9-148">El Editor MDX (Expresiones multidimensionales) y el Editor DMX (Expresiones de minería de datos) comprueban automáticamente la coincidencia de los pares de paréntesis en las funciones.</span><span class="sxs-lookup"><span data-stu-id="492a9-148">The Multi-Dimensional Expressions (MDX) and Data Mining Expressions (DMX) Editors automatically match parenthesis pairs in functions.</span></span>  
  
  
