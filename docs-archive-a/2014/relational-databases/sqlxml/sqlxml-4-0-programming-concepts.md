---
title: Conceptos de programación de SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, about SQLXML
- SQLXML
ms.assetid: 5a11cda2-b8a3-4453-848f-641afdaa7024
author: rothja
ms.author: jroth
ms.openlocfilehash: 90a383d2a12e073f262d24a94abe1b094509713c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674700"
---
# <a name="sqlxml-40-programming-concepts"></a><span data-ttu-id="c2b60-102">Conceptos de programación en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c2b60-102">SQLXML 4.0 Programming Concepts</span></span>
  <span data-ttu-id="c2b60-103">SQLXML 3.0 se proporcionó como una versión web para facilitar funcionalidad XML adicional del lado cliente y mejoras en las características existentes, como esquemas XSD anotados, carga masiva XML, compatibilidad con los servicios web (SOAP) y diagramas de actualización.</span><span class="sxs-lookup"><span data-stu-id="c2b60-103">SQLXML 3.0 was offered as a Web release to provide additional client-side XML functionality and enhancements to existing features, such as annotated XSD schemas, XML bulk load, Web services (SOAP) support, and updategrams.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="c2b60-104">introdujo SQLXML 4.0, que continúa entregando la misma funcionalidad que SQLXML 3.0 además de actualizaciones adicionales proporcionadas para alojar las nuevas características introducidas con [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2b60-104">introduced SQLXML 4.0, which continues to deliver the same functionality as SQLXML 3.0 plus additional updates provided to accommodate new features introduced with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="c2b60-105">En esta sección se proporciona información sobre SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c2b60-105">This section provides information about SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="c2b60-106">SQLXML no se instala en SQL Server</span><span class="sxs-lookup"><span data-stu-id="c2b60-106">SQLXML Is Not Installed in SQL Server</span></span>](sqlxml-is-not-installed-in-sql-server.md)  
 <span data-ttu-id="c2b60-107">Describe cómo instalar SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c2b60-107">Describes how to install SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="c2b60-108">Novedades de SQLXML 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="c2b60-108">What's New in SQLXML 4.0 SP1</span></span>](what-s-new-in-sqlxml-4-0-sp1.md)  
 <span data-ttu-id="c2b60-109">Describe las actualizaciones y mejoras en SQLXML 4.0 y proporciona vínculos a los correspondientes temas de esta documentación.</span><span class="sxs-lookup"><span data-stu-id="c2b60-109">Describes the updates and enhancements in SQLXML 4.0, and provides links to relevant topics in this documentation.</span></span>  
  
 [<span data-ttu-id="c2b60-110">Utilizar ADO para ejecutar consultas SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c2b60-110">Using ADO to Execute SQLXML 4.0 Queries</span></span>](using-ado-to-execute-sqlxml-4-0-queries.md)  
 <span data-ttu-id="c2b60-111">Describe cómo utilizar ADO para las consultas SQLXML.</span><span class="sxs-lookup"><span data-stu-id="c2b60-111">Describes how to use ADO for SQLXML queries.</span></span> <span data-ttu-id="c2b60-112">ADO tiene más importancia en SQLXML 4.0 que en las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="c2b60-112">ADO is more prominent in SQLXML 4.0 than in previous versions.</span></span>  
  
 [<span data-ttu-id="c2b60-113">Compatibilidad con tipos de datos xml en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c2b60-113">xml Data Type Support in SQLXML 4.0</span></span>](xml-data-type-support-in-sqlxml-4-0.md)  
 <span data-ttu-id="c2b60-114">Describe la compatibilidad del tipo de datos xml agregado con SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c2b60-114">Describes the support for the xml data type that has been added for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="c2b60-115">Requisitos para ejecutar los ejemplos de SQLXML</span><span class="sxs-lookup"><span data-stu-id="c2b60-115">Requirements for Running SQLXML Examples</span></span>](requirements-for-running-sqlxml-examples.md)  
 <span data-ttu-id="c2b60-116">Describe los requisitos para crear ejemplos funcionales a partir de los ejemplos de SQLXML proporcionados.</span><span class="sxs-lookup"><span data-stu-id="c2b60-116">Describe the requirements for creating working samples from the SQLXML examples provided.</span></span>  
  
 [<span data-ttu-id="c2b60-117">Formato del lado cliente y del lado servidor &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c2b60-117">Client-side and Server-side Formatting &#40;SQLXML 4.0&#41;</span></span>](formatting/client-side-and-server-side-formatting-sqlxml-4-0.md)  
 <span data-ttu-id="c2b60-118">Proporciona información y comparaciones de formato en el cliente y en el servidor, incluido el comando FOR XML para construir los documentos XML.</span><span class="sxs-lookup"><span data-stu-id="c2b60-118">Provides information about and comparisons of client-side and server-side formatting, including the FOR XML command for constructing XML documents.</span></span>  
  
 [<span data-ttu-id="c2b60-119">Esquemas XSD anotados en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c2b60-119">Annotated XSD Schemas in SQLXML 4.0</span></span>](annotated-xsd-schemas/annotated-xsd-schemas-in-sqlxml-4-0.md)  
 <span data-ttu-id="c2b60-120">Proporciona información sobre cómo utilizar los esquemas XSD anotados en SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c2b60-120">Provides information about using annotated XSD schemas in SQLXML 4.0.</span></span> <span data-ttu-id="c2b60-121">También proporciona información sobre los esquemas XDR anotados para su uso en las aplicaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="c2b60-121">Also provides information about annotated XDR schemas for use in legacy applications.</span></span>  
  
 [<span data-ttu-id="c2b60-122">Utilizar consultas XPath en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c2b60-122">Using XPath Queries in SQLXML 4.0</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/using-xpath-queries-in-sqlxml-4-0.md)  
 <span data-ttu-id="c2b60-123">Describe cómo usar un subconjunto del lenguaje XPath para consultar las vistas XML creadas por un esquema XSD anotado y proporciona ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c2b60-123">Describes how to use a subset of the XPath language to query the XML views created by an annotated XSD schema, and provides examples.</span></span>  
  
 [<span data-ttu-id="c2b60-124">Utilizar los diagramas de actualización para modificar datos en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c2b60-124">Using Updategrams to Modify Data in SQLXML 4.0</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/using-updategrams-to-modify-data-in-sqlxml-4-0.md)  
 <span data-ttu-id="c2b60-125">Proporciona información sobre los diagramas de actualización, que modifican los datos de una base de datos trabajando con las vistas XML proporcionadas por los esquemas XSD (o XDR) anotados.</span><span class="sxs-lookup"><span data-stu-id="c2b60-125">Provides information about updategrams, which modify data in a database by working against the XML views provided by XSD (or XDR) annotated schemas.</span></span>  
  
 [<span data-ttu-id="c2b60-126">Carga masiva de datos XML &#40;SQLXML 4.0&#41;</span><span class="sxs-lookup"><span data-stu-id="c2b60-126">Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md)  
 <span data-ttu-id="c2b60-127">Describe cómo hacer una carga masiva de XML en SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c2b60-127">Describes how to bulk load XML in SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="c2b60-128">Componentes de acceso a datos de SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c2b60-128">SQLXML 4.0 Data Access Components</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/data-access-components-provider/sqlxml-4-0-data-access-components-sqlxmloledb-provider.md)  
 <span data-ttu-id="c2b60-129">Documenta el proveedor de SQLXMLOLEDB y proporciona vínculos a otros componentes de acceso a datos de SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c2b60-129">Documents the SQLXMLOLEDB Provider and provides links to other SQLXML 4.0 data access components.</span></span>  
  
 [<span data-ttu-id="c2b60-130">Compatibilidad de SQLXML 4.0 con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c2b60-130">SQLXML 4.0 .NET Framework Support</span></span>](../../database-engine/dev-guide/sqlxml-4-0-net-framework-support.md)  
 <span data-ttu-id="c2b60-131">Describe la compatibilidad de SQLXML 4.0 con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2b60-131">Describes the SQLXML 4.0 support for the .NET Framework.</span></span>  
  
 [<span data-ttu-id="c2b60-132">Plantillas de almacenamiento en caché, XSL y esquemas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c2b60-132">Caching Templates, XSL, and Schemas &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/caching-templates-xml-schemas/caching-templates-xsl-and-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="c2b60-133">Describe la funcionalidad de almacenamiento en caché proporcionada en SQLXML para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c2b60-133">Describes the caching functionality provided in SQLXML to improve performance.</span></span>  
  
 [<span data-ttu-id="c2b60-134">Consideraciones de seguridad de SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c2b60-134">SQLXML 4.0 Security Considerations</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/security/sqlxml-4-0-security-considerations.md)  
 <span data-ttu-id="c2b60-135">Describe los problemas de seguridad relativos a SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c2b60-135">Discusses security issues relevant to SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="c2b60-136">Instrucciones y limitaciones de SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c2b60-136">Guidelines and Limitations of SQLXML 4.0</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/guidelines-and-limitations-of-sqlxml-4-0.md)  
 <span data-ttu-id="c2b60-137">Enumera los problemas que se deben recordar al trabajar con SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c2b60-137">Lists issues to remember when working with SQLXML 4.0.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b60-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2b60-138">See Also</span></span>  
 [<span data-ttu-id="c2b60-139">Datos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c2b60-139">XML Data &#40;SQL Server&#41;</span></span>](../xml/xml-data-sql-server.md)  
  
  
