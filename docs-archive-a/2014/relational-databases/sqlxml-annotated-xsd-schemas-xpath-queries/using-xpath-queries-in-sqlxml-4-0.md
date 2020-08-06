---
title: Usar consultas XPath en SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML]
- annotated XSD schemas, XPath queries
- queries [SQLXML], XPath
- XML views [SQLXML]
ms.assetid: 7814d099-81ec-4fb8-894a-729cdbb5015a
author: rothja
ms.author: jroth
ms.openlocfilehash: 80d82513b22d2a50aedb37955a210dd33746db86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674729"
---
# <a name="using-xpath-queries-in-sqlxml-40"></a><span data-ttu-id="f394e-102">Utilizar consultas XPath en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="f394e-102">Using XPath Queries in SQLXML 4.0</span></span>
  <span data-ttu-id="f394e-103">La compatibilidad de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con los esquemas XSD anotados le permite crear vistas XML de los datos relacionales almacenadas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f394e-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support for annotated XSD schemas allows you to create XML views of the relational data stored in the database.</span></span> <span data-ttu-id="f394e-104">Puede utilizar un subconjunto del lenguaje XPath para consultar las vistas XML creadas por un esquema XSD anotado.</span><span class="sxs-lookup"><span data-stu-id="f394e-104">You can use a subset of the XPath language to query the XML views created by an annotated XSD schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f394e-105">Para entender las consultas XPath en SQLXML 4.0, debe estar familiarizado con las vistas XML y otros conceptos relacionados, como las plantillas y el esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="f394e-105">To understand XPath queries in SQLXML 4.0, you must be familiar with XML views and related concepts such as templates and mapping schema.</span></span> <span data-ttu-id="f394e-106">Para obtener más información, vea [Introducción a los esquemas XSD anotados &#40;SQLXML 4,0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f394e-106">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="f394e-107">Para obtener más información sobre XPath, vea el estándar XPath definido por el World Wide Web Consortium (W3C) en http://www.w3.org/TR/xpath .</span><span class="sxs-lookup"><span data-stu-id="f394e-107">For more information about XPath, see the XPath standard defined by the World Wide Web Consortium (W3C) at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f394e-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f394e-108">In This Section</span></span>  
 [<span data-ttu-id="f394e-109">Introducción al uso de consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f394e-109">Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;</span></span>](introduction-to-using-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="f394e-110">Proporciona información preliminar sobre las consultas XPath en SQLXML 4.0, incluida la funcionalidad compatible y no compatible de acuerdo con la especificación XPath de W3C.</span><span class="sxs-lookup"><span data-stu-id="f394e-110">Provides introductory information about XPath queries in SQLXML 4.0, including supported and unsupported functionality from the W3C XPath specification.</span></span>  
  
 [<span data-ttu-id="f394e-111">Especificar una ruta de acceso de ubicación &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f394e-111">Specifying a Location Path &#40;SQLXML 4.0&#41;</span></span>](location-path/specifying-a-location-path-sqlxml-4-0.md)  
 <span data-ttu-id="f394e-112">Describe cómo especificar rutas de acceso de ubicación en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="f394e-112">Describes how to specify location paths in XPath queries.</span></span>  
  
 [<span data-ttu-id="f394e-113">Consultas XPath de ejemplo &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f394e-113">Sample XPath Queries &#40;SQLXML 4.0&#41;</span></span>](samples/sample-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="f394e-114">Proporciona consultas XPath de ejemplo para SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="f394e-114">Provides sample XPath queries for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="f394e-115">Tipos de datos de XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f394e-115">XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="f394e-116">Describe tipos de datos XPath, que son significativamente diferentes de los de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y XSD.</span><span class="sxs-lookup"><span data-stu-id="f394e-116">Describes XPath data types, which are significantly different from those of both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and XSD.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f394e-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f394e-117">See Also</span></span>  
 [<span data-ttu-id="f394e-118">Formato XML del lado cliente &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f394e-118">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
