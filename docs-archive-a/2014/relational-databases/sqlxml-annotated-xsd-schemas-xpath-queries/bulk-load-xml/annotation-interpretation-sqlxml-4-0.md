---
title: Interpretación de anotaciones (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, XML Bulk Load
- XML Bulk Load [SQLXML], annotation intepretations
- annotations [SQLXML]
- bulk load [SQLXML], annotation interpretations
- annotated XDR schemas, XML Bulk Load
ms.assetid: 1c46bdb6-2812-4a13-b60b-7101c04b299f
author: rothja
ms.author: jroth
ms.openlocfilehash: c31d56f7dd577b4b5a5b582eb0e3b1db312109a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674749"
---
# <a name="annotation-interpretation-sqlxml-40"></a><span data-ttu-id="4cdd7-102">Interpretación de anotaciones (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4cdd7-102">Annotation Interpretation (SQLXML 4.0)</span></span>
  <span data-ttu-id="4cdd7-103">Los temas de esta sección describen la forma en que la carga masiva XML interpreta las anotaciones del esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="4cdd7-103">The topics in this section describe how XML Bulk Load interprets annotations in the XSD schema.</span></span> <span data-ttu-id="4cdd7-104">El comportamiento que aquí se describe también se aplica a las anotaciones del esquema XDR.</span><span class="sxs-lookup"><span data-stu-id="4cdd7-104">The behavior described here also applies to the annotations in the XDR schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4cdd7-105">La información de estos temas describe únicamente las anotaciones que la carga masiva XML utiliza en su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4cdd7-105">The information in these topics describes only the annotations used by XML Bulk Load in its processing.</span></span> <span data-ttu-id="4cdd7-106">Para obtener una lista completa de anotaciones para el esquema XSD que son compatibles con SQLXML 4,0, vea [utilizar anotaciones en esquemas xsd &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4cdd7-106">For a complete list of annotations for the XSD schema that are supported by SQLXML 4.0, see [Using Annotations in XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="4cdd7-107">Para obtener una lista de las anotaciones admitidas para los esquemas XDR, consulte [esquemas XDR anotados &#40;en desuso en SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4cdd7-107">For a list of supported annotations for XDR schemas, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4cdd7-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4cdd7-108">In This Section</span></span>  
 [<span data-ttu-id="4cdd7-109">SQL: Relationship y la regla de ordenación de claves &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4cdd7-109">sql:relationship and the Key Ordering Rule &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-relationship-and-key-ordering-rule.md)  
 <span data-ttu-id="4cdd7-110">Describe la forma en que se interpreta la anotación `sql:relationship` en la carga masiva XML.</span><span class="sxs-lookup"><span data-stu-id="4cdd7-110">Describes how the `sql:relationship` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="4cdd7-111">SQL: asignado &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4cdd7-111">sql:mapped &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-mapped.md)  
 <span data-ttu-id="4cdd7-112">Describe la forma en que se interpreta la anotación `sql:mapped` en la carga masiva XML.</span><span class="sxs-lookup"><span data-stu-id="4cdd7-112">Describes how the `sql:mapped` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="4cdd7-113">SQL: Limit-Field y SQL: Limit-Value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4cdd7-113">sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="4cdd7-114">Describe la forma en que se interpretan las anotaciones `sql:limit-field` y `sql:limit-value` en la carga masiva XML.</span><span class="sxs-lookup"><span data-stu-id="4cdd7-114">Describes how the `sql:limit-field` and `sql:limit-value` annotations are interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="4cdd7-115">SQL: Overflow-Field &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4cdd7-115">sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="4cdd7-116">Describe la forma en que se interpreta la anotación `sql:overflow` en la carga masiva XML.</span><span class="sxs-lookup"><span data-stu-id="4cdd7-116">Describes how the `sql:overflow` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="4cdd7-117">Otras anotaciones &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4cdd7-117">Other Annotations &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-other-annotations.md)  
 <span data-ttu-id="4cdd7-118">Describe la forma en que se interpretan las siguientes anotaciones en la carga masiva XML: `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="4cdd7-118">Describes how the following annotations are interpreted in XML Bulk Load: `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span></span>  
  
  
