---
title: Esquemas XSD anotados en SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas
- SQLXML, annotated XSD schemas
- mapping schema [SQLXML]
- XSD schemas [SQLXML]
- XSD schemas [SQLXML], annotations
- schemas [SQLXML]
ms.assetid: eecd0d5f-d3dd-4d20-9586-19820410ad47
author: rothja
ms.author: jroth
ms.openlocfilehash: f97e01b0ade98edc432869c8772fbd4720df9a08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674720"
---
# <a name="annotated-xsd-schemas-in-sqlxml-40"></a><span data-ttu-id="6c388-102">Esquemas XSD anotados en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="6c388-102">Annotated XSD Schemas in SQLXML 4.0</span></span>
  <span data-ttu-id="6c388-103">Esta sección proporciona información sobre cómo utilizar esquemas XDR anotados en SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="6c388-103">This section provides information about using annotated XSD schemas in SQLXML 4.0.</span></span> <span data-ttu-id="6c388-104">En versiones anteriores de SQLXML, se proporcionaba funcionalidad similar con esquemas reducidos de datos XML (XDR).</span><span class="sxs-lookup"><span data-stu-id="6c388-104">In previous versions of SQLXML, similar functionality was provided with XML-Data Reduced (XDR) schemas.</span></span> <span data-ttu-id="6c388-105">En esta sección también se proporciona información XDR para aplicaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="6c388-105">This section also provides XDR information for legacy applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c388-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6c388-106">In This Section</span></span>  
 [<span data-ttu-id="6c388-107">Introducción a los esquemas XSD anotados &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6c388-107">Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;</span></span>](introduction-to-annotated-xsd-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="6c388-108">Proporciona información general sobre esquemas XSD anotados en SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="6c388-108">Provides an overview of annotated XSD schemas in SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="6c388-109">Usar anotaciones en esquemas XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6c388-109">Using Annotations in XSD Schemas &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="6c388-110">Describe cómo utilizar anotaciones en esquemas XSD en numerosos escenarios y proporciona ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6c388-110">Describes how to use annotations in XSD schemas in numerous scenarios, and provides examples.</span></span>  
  
 [<span data-ttu-id="6c388-111">Usar esquemas XSD anotados en consultas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6c388-111">Using Annotated XSD Schemas in Queries &#40;SQLXML 4.0&#41;</span></span>](using-annotated-xsd-schemas-in-queries-sqlxml-4-0.md)  
 <span data-ttu-id="6c388-112">Describe cómo utilizar esquemas XSD anotados en consultas.</span><span class="sxs-lookup"><span data-stu-id="6c388-112">Describes how to use annotated XSD schemas in queries.</span></span>  
  
 [<span data-ttu-id="6c388-113">Convertir esquemas XDR anotados en esquemas XSD equivalentes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6c388-113">Converting Annotated XDR Schemas to Equivalent XSD Schemas &#40;SQLXML 4.0&#41;</span></span>](converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="6c388-114">Describe cómo convertir esquemas XDR en los esquemas XSD equivalentes para SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="6c388-114">Describes how to convert XDR schemas to the equivalent XSD schemas for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="6c388-115">Los esquemas XDR anotados &#40;han quedado en desuso en SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6c388-115">Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;</span></span>](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md)  
 <span data-ttu-id="6c388-116">Las versiones anteriores de SQLXML admitían anotaciones en esquemas XDR.</span><span class="sxs-lookup"><span data-stu-id="6c388-116">Previous versions of SQLXML supported annotations in XDR schemas.</span></span> <span data-ttu-id="6c388-117">Los esquemas XDR anotados se dejan de utilizar en SQLXML 4.0, pero se proporciona esta sección como referencia para aplicaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="6c388-117">Annotated XDR schemas are deprecated in SQLXML 4.0, but this section is provided as a reference for legacy applications.</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="6c388-118">Otros recursos</span><span class="sxs-lookup"><span data-stu-id="6c388-118">Other Resources</span></span>  
 <span data-ttu-id="6c388-119">Puede buscar más información sobre el lenguaje de definición de esquemas XML (XSD), el lenguaje de rutas XML (XPath) y el lenguaje de transformación basado en hojas de estilo (XSLT) en los siguientes sitios web:</span><span class="sxs-lookup"><span data-stu-id="6c388-119">You can find more information about XML Schema Definition language (XSD), XML Path language (XPath), and Extensible Stylesheet Language Transformations (XSLT) at the following Web sites:</span></span>  
  
-   <span data-ttu-id="6c388-120">XML Schema Part 0: manual, recomendación de W3C (http://www.w3.org/TR/xmlschema-0/)</span><span class="sxs-lookup"><span data-stu-id="6c388-120">XML Schema Part 0: Primer, W3C Recommendation (http://www.w3.org/TR/xmlschema-0/)</span></span>  
  
-   <span data-ttu-id="6c388-121">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span><span class="sxs-lookup"><span data-stu-id="6c388-121">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span></span>  
  
-   <span data-ttu-id="6c388-122">Esquema XML parte 2: tipos de archivo, recomendación de W3C (http://www.w3.org/TR/xmlschema-2/)</span><span class="sxs-lookup"><span data-stu-id="6c388-122">XML Schema Part 2:Datatypes, W3C Recommendation (http://www.w3.org/TR/xmlschema-2/)</span></span>  
  
-   <span data-ttu-id="6c388-123">Lenguaje de rutas XML (XPath) (http://www.w3.org/TR/xpath)</span><span class="sxs-lookup"><span data-stu-id="6c388-123">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span></span>  
  
-   <span data-ttu-id="6c388-124">Transformaciones XSL (XSLT) (http://www.w3.org/TR/xslt)</span><span class="sxs-lookup"><span data-stu-id="6c388-124">XSL Transformations (XSLT) (http://www.w3.org/TR/xslt)</span></span>  
  
  
