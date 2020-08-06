---
title: Editor de transformación extracción de términos (pestaña avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.advanced.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 87118281-6e3c-499e-bac4-fa4c24bb12c6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4be56f8ac2deeab49e43071a07894a466019287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747102"
---
# <a name="term-extraction-transformation-editor-advanced-tab"></a><span data-ttu-id="aa0cc-102">Editor de transformación Extracción de términos (pestaña Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="aa0cc-102">Term Extraction Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="aa0cc-103">Use la pestaña **Avanzadas** del cuadro de diálogo **Editor de transformación Extracción de términos** para especificar las propiedades de la extracción, tales como la frecuencia, la longitud y si deben extraerse palabras o frases.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-103">Use the **Advanced** tab of the **Term Extraction Transformation Editor** dialog box to specify properties for the extraction such as frequency, length, and whether to extract words or phrases.</span></span>  
  
 <span data-ttu-id="aa0cc-104">Para obtener más información acerca de la transformación Extracción de términos, vea [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="aa0cc-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="aa0cc-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="aa0cc-105">Options</span></span>  
 <span data-ttu-id="aa0cc-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="aa0cc-106">**Noun**</span></span>  
 <span data-ttu-id="aa0cc-107">Especifica que la transformación extrae únicamente nombres individuales.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-107">Specify that the transformation extracts individual nouns only.</span></span>  
  
 <span data-ttu-id="aa0cc-108">**Frase**</span><span class="sxs-lookup"><span data-stu-id="aa0cc-108">**Noun phrase**</span></span>  
 <span data-ttu-id="aa0cc-109">Especifica que la transformación extrae únicamente frases.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-109">Specify that the transformation extracts noun phrases only.</span></span>  
  
 <span data-ttu-id="aa0cc-110">**Nombre y frase**</span><span class="sxs-lookup"><span data-stu-id="aa0cc-110">**Noun and noun phrase**</span></span>  
 <span data-ttu-id="aa0cc-111">Especifica que la transformación extrae nombres y frases.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-111">Specify that the transformation extracts both nouns and noun phrases.</span></span>  
  
 <span data-ttu-id="aa0cc-112">**Frecuencia**</span><span class="sxs-lookup"><span data-stu-id="aa0cc-112">**Frequency**</span></span>  
 <span data-ttu-id="aa0cc-113">Especifica que la puntuación está determinada por la frecuencia del término.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-113">Specify that the score is the frequency of the term.</span></span>  
  
 <span data-ttu-id="aa0cc-114">**TFIDF**</span><span class="sxs-lookup"><span data-stu-id="aa0cc-114">**TFIDF**</span></span>  
 <span data-ttu-id="aa0cc-115">Mediante esta opción se indica que la puntuación está determinada por el valor TFIDF del término.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-115">Specify that the score is the TFIDF value of the term.</span></span> <span data-ttu-id="aa0cc-116">La puntuación TFIDF es el producto de la frecuencia del término y la frecuencia inversa del documento, definida de esta forma: TFIDF de un término T = (frecuencia de T) \* log( (n.º de filas de entrada) / (n.º de filas con T) )</span><span class="sxs-lookup"><span data-stu-id="aa0cc-116">The TFIDF score is the product of Term Frequency and Inverse Document Frequency, defined as: TFIDF of a Term T = (frequency of T) \* log( (#rows in Input) / (#rows having T) )</span></span>  
  
 <span data-ttu-id="aa0cc-117">**Umbral de frecuencia**</span><span class="sxs-lookup"><span data-stu-id="aa0cc-117">**Frequency threshold**</span></span>  
 <span data-ttu-id="aa0cc-118">Permite especificar el número de veces que una palabra o frase debe aparecer antes de extraerla.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-118">Specify the number of times a word or phrase must occur before extracting it.</span></span> <span data-ttu-id="aa0cc-119">El valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-119">The default value is 2.</span></span>  
  
 <span data-ttu-id="aa0cc-120">**Longitud máxima del término**</span><span class="sxs-lookup"><span data-stu-id="aa0cc-120">**Maximum length of term**</span></span>  
 <span data-ttu-id="aa0cc-121">Permite especificar la longitud máxima de una frase en palabras.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-121">Specify the maximum length of a phrase in words.</span></span> <span data-ttu-id="aa0cc-122">Esta opción afecta únicamente a frases.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-122">This option affects noun phrases only.</span></span> <span data-ttu-id="aa0cc-123">El valor predeterminado es 12.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-123">The default value is 12.</span></span>  
  
 <span data-ttu-id="aa0cc-124">**Utilizar extracción de términos con distinción de mayúsculas y minúsculas**</span><span class="sxs-lookup"><span data-stu-id="aa0cc-124">**Use case-sensitive term extraction**</span></span>  
 <span data-ttu-id="aa0cc-125">Permite especificar si la extracción distinguirá mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-125">Specify whether to make the extraction case-sensitive.</span></span> <span data-ttu-id="aa0cc-126">El valor predeterminado es `False`.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-126">The default is `False`.</span></span>  
  
 <span data-ttu-id="aa0cc-127">**Configurar la salida de errores**</span><span class="sxs-lookup"><span data-stu-id="aa0cc-127">**Configure Error Output**</span></span>  
 <span data-ttu-id="aa0cc-128">Use el cuadro de diálogo [Configurar la salida de errores](../../2014/integration-services/configure-error-output.md) para especificar las opciones de control de errores para las filas que provocan errores.</span><span class="sxs-lookup"><span data-stu-id="aa0cc-128">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa0cc-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa0cc-129">See Also</span></span>  
 <span data-ttu-id="aa0cc-130">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="aa0cc-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="aa0cc-131">[Editor de transformación extracción de términos &#40;pestaña extracción de términos&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="aa0cc-131">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="aa0cc-132">[Editor de transformación extracción de términos &#40;pestaña exclusión&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span><span class="sxs-lookup"><span data-stu-id="aa0cc-132">[Term Extraction Transformation Editor &#40;Exclusion Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span></span>  
 [<span data-ttu-id="aa0cc-133">Transformación Búsqueda de términos</span><span class="sxs-lookup"><span data-stu-id="aa0cc-133">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
