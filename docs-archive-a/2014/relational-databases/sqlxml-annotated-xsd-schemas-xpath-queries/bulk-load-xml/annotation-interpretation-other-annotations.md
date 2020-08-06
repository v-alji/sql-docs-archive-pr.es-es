---
title: Otras anotaciones (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- url-encode annotation
- sql:key-fields
- use-cdata annotation
- sql:is-mapping-schema
- sql:url-encode
- sql:id-prefix
- sql:use-cdata
- key-fields annotation
- id-prefix annotation [SQLXML]
- is-mapping-schema annotation
ms.assetid: f7b4d37b-d6d3-4ac3-b2fd-a0b534a924e4
author: rothja
ms.author: jroth
ms.openlocfilehash: b654568c93df0a0c3e08cf6eaa615b7026a9c18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672882"
---
# <a name="other-annotations-sqlxml-40"></a><span data-ttu-id="d9df0-102">Otras anotaciones (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d9df0-102">Other Annotations (SQLXML 4.0)</span></span>
  <span data-ttu-id="d9df0-103">Además de las anotaciones descritas en los temas anteriores de esta sección, la carga masiva de XML interpreta estas otras anotaciones del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9df0-103">In addition to the annotations discussed in the previous topics in this section, XML Bulk Load interprets these other annotations, as follows:</span></span>  
  
 `sql:id-prefix`  
 <span data-ttu-id="d9df0-104">Si el esquema especifica prefijos para los datos XML, la carga masiva de XML quita los prefijos antes de enviar los datos a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9df0-104">If the schema specifies prefixes to the XML data, XML Bulk Load removes the prefixes before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:use-cdata`  
 <span data-ttu-id="d9df0-105">La carga masiva de XML lee el texto que está almacenado en las secciones CDATA y lo envía a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9df0-105">XML Bulk Load reads the text that is stored in the CDATA sections and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:url-encode`  
 <span data-ttu-id="d9df0-106">La carga masiva de XML no admite esta anotación.</span><span class="sxs-lookup"><span data-stu-id="d9df0-106">XML Bulk Load does not support this annotation.</span></span> <span data-ttu-id="d9df0-107">Por ejemplo, no puede especificar una dirección URL en la entrada de datos XML y esperar que la carga masiva de XML lea los datos de esa ubicación para almacenarlos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d9df0-107">For example, you cannot specify a URL in the XML data input and expect XML Bulk Load to read data from that location to store it in the database.</span></span>  
  
 `sql:is-mapping-schema`  
 <span data-ttu-id="d9df0-108">La carga masiva de XML no admite esta anotación, ni tampoco admite `sql:id`.</span><span class="sxs-lookup"><span data-stu-id="d9df0-108">XML Bulk Load does not support this annotation, nor does it support `sql:id`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9df0-109">La carga masiva de XML no admite los esquemas de asignación insertados.</span><span class="sxs-lookup"><span data-stu-id="d9df0-109">XML Bulk Load does not support inline mapping schemas.</span></span>  
  
 `sql:key-fields`  
 <span data-ttu-id="d9df0-110">La carga masiva de XML omite siempre esta anotación.</span><span class="sxs-lookup"><span data-stu-id="d9df0-110">XML Bulk Load always ignores this annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9df0-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9df0-111">See Also</span></span>  
 [<span data-ttu-id="d9df0-112">Interpretación de anotaciones &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d9df0-112">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
  
  
