---
title: Consultas XPath de ejemplo (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- examples [SQLXML], XPath
- sample applications [SQLXML]
- sample XPath queries [SQLXML]
- mapping schema [SQLXML], queries
- XPath queries [SQLXML], samples
ms.assetid: 1595c2d4-0e9c-4969-84c8-a793a32df57d
author: rothja
ms.author: jroth
ms.openlocfilehash: 08ed32433e9bed4cc1542d6700ad73dc96f3c2dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662758"
---
# <a name="sample-xpath-queries-sqlxml-40"></a><span data-ttu-id="ddcac-102">Consultas XPath de ejemplo (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ddcac-102">Sample XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="ddcac-103">En esta sección se proporcionan ejemplos de consultas XPath para SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="ddcac-103">This section provides examples of XPath queries for SQLXML 4.0.</span></span> <span data-ttu-id="ddcac-104">Con fines meramente ilustrativos, estas consultas XPath de ejemplo se especifican en una plantilla ejecutada con ADO.</span><span class="sxs-lookup"><span data-stu-id="ddcac-104">For illustration purposes, these example XPath queries are specified in a template executed using ADO.</span></span> <span data-ttu-id="ddcac-105">Por lo tanto, deberá usar un archivo de esquema de asignación, SampleSchema1.xml, que también se proporciona en esta sección.</span><span class="sxs-lookup"><span data-stu-id="ddcac-105">Therefore, you must use a mapping schema file, SampleSchema1.xml, which is also provided in this section.</span></span> <span data-ttu-id="ddcac-106">Guarde este archivo en el directorio donde estén almacenadas sus plantillas.</span><span class="sxs-lookup"><span data-stu-id="ddcac-106">Save this file in the directory where your templates are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ddcac-107">Las consultas de ejemplo de esta sección están agrupadas por el tipo de operación XPath que realiza la consulta.</span><span class="sxs-lookup"><span data-stu-id="ddcac-107">The sample queries in this section are grouped by the type of XPath operation that is performed by the query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ddcac-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ddcac-108">In This Section</span></span>  
 [<span data-ttu-id="ddcac-109">Esquema XSD anotado de ejemplo para los ejemplos de XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ddcac-109">Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;</span></span>](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md)  
 <span data-ttu-id="ddcac-110">Use este archivo con los ejemplos de consultas XPath que se proporcionan en esta sección.</span><span class="sxs-lookup"><span data-stu-id="ddcac-110">Use this file with the XPath query examples provided in this section.</span></span>  
  
 [<span data-ttu-id="ddcac-111">Especificar ejes en consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ddcac-111">Specifying Axes in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-axes-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ddcac-112">Muestra cómo se especifican los ejes en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="ddcac-112">Illustrates how axes are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ddcac-113">Especificar predicados con valores booleanos en consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ddcac-113">Specifying Boolean-Valued Predicates in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ddcac-114">Muestra cómo se especifican los predicados con valores booleanos en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="ddcac-114">Illustrates how Boolean-valued predicates are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ddcac-115">Especificar operadores relacionales en consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ddcac-115">Specifying Relational Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-relational-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ddcac-116">Muestra cómo se especifican los operadores relacionales en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="ddcac-116">Illustrates how relational operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ddcac-117">Especificar operadores aritméticos en consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ddcac-117">Specifying Arithmetic Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-arithmetic-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ddcac-118">Muestra cómo se especifican los operadores aritméticos en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="ddcac-118">Illustrates how arithmetic operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ddcac-119">Especificar funciones de conversión explícitas en consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ddcac-119">Specifying Explicit Conversion Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ddcac-120">Muestra cómo se especifican las funciones de conversión explícita en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="ddcac-120">Illustrates how explicit conversion functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ddcac-121">Especificar operadores booleanos en consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ddcac-121">Specifying Boolean Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ddcac-122">Muestra cómo se especifican los operadores booleanos en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="ddcac-122">Illustrates how Boolean operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ddcac-123">Especificar funciones booleanas en consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ddcac-123">Specifying Boolean Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ddcac-124">Muestra cómo se especifican las funciones booleanas en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="ddcac-124">Illustrates how Boolean functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ddcac-125">Especificar variables XPath en consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ddcac-125">Specifying XPath Variables in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-xpath-variables-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ddcac-126">Muestra cómo se especifican las variables XPath en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="ddcac-126">Illustrates how XPath variables are specified in XPath queries.</span></span>  
  
  
