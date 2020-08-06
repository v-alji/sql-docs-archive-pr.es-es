---
title: Usar anotaciones en esquemas XSD (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, about annotated XSD schemas
- annotations [SQLXML]
- relationships [SQLXML]
- relationships [SQLXML], hierarchical relationships
- hierarchical relationships [SQLXML]
- mapping schema [SQLXML], scenarios for using
ms.assetid: 78f318a4-7a36-473b-9852-a4bae6940ce5
author: rothja
ms.author: jroth
ms.openlocfilehash: e2be94aa5815593d7a5a2e0c00bcd8849e81484e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672891"
---
# <a name="using-annotations-in-xsd-schemas-sqlxml-40"></a><span data-ttu-id="c4c3c-102">Utilizar anotaciones en esquemas XSD (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c4c3c-102">Using Annotations in XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="c4c3c-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0, el lenguaje de esquemas XSD admite las anotaciones de un modo similar a las introducidas en el lenguaje de esquemas reducidos de datos XML (XDR).</span><span class="sxs-lookup"><span data-stu-id="c4c3c-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports annotations in a manner similar to the annotations introduced in the XML-Data Reduced (XDR) schema language.</span></span> <span data-ttu-id="c4c3c-104">Hay anotaciones adicionales introducidas en XSD que no se admiten en XDR.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-104">There are additional annotations introduced in XSD that are not supported in XDR.</span></span>  
  
 <span data-ttu-id="c4c3c-105">Estas anotaciones se pueden utilizar dentro del esquema XSD para especificar la asignación de XML a relacional.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-105">These annotations can be used within the XSD schema to specify XML-to-relational mapping.</span></span> <span data-ttu-id="c4c3c-106">Esto incluye la asignación entre los elementos y atributos del esquema XSD a las tablas (vistas) y columnas de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-106">This includes mapping between elements and attributes in the XSD schema to tables (views) and columns in the databases.</span></span>  
  
 <span data-ttu-id="c4c3c-107">Si no se especifican las anotaciones, se produce la asignación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-107">If you do not specify the annotations, default mapping takes place.</span></span> <span data-ttu-id="c4c3c-108">Un elemento XSD con un tipo complejo se asigna de forma predeterminada a un nombre de tabla (vista) de la base de datos especificada, mientras que un elemento o atributo con un tipo simple se asigna a la columna con el mismo nombre que el elemento o atributo.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-108">By default, an XSD element with a complex type maps to a table (view) name in the specified database, and an element or attribute with a simple type maps to the column with the same name as the element or attribute.</span></span>  
  
 <span data-ttu-id="c4c3c-109">Estas anotaciones también se pueden utilizar para especificar las relaciones jerárquicas en XML, lo que representa las relaciones de la base de datos, ya que un esquema XSD es simplemente una vista XML de los datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-109">These annotations can also be used to specify the hierarchical relationships in XML-thus representing the relationships in the database, because an XSD schema is simply an XML view of relational data.</span></span>  
  
 <span data-ttu-id="c4c3c-110">En esta sección se proporcionan descripciones de las anotaciones que puede usar con esquemas XSD y ejemplos de su uso.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-110">This section provides descriptions of the annotations you can use with XSD schemas and examples of their usage.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4c3c-111">Todos los ejemplos de esta sección especifican consultas XPath simples en el esquema XSD agregado descrito en cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-111">All the examples in this section specify simple XPath queries against the annotated XSD schema described in each example.</span></span> <span data-ttu-id="c4c3c-112">Se presupone el conocimiento del lenguaje XPath.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-112">Familiarity with the XPath language is assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4c3c-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c4c3c-113">In This Section</span></span>  
 [<span data-ttu-id="c4c3c-114">Anotaciones XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-114">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](xsd-annotations-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-115">Se enumeran las anotaciones que puede utilizar con esquemas XSD, sus descripciones y las anotaciones equivalentes para XDR.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-115">Lists the annotations you can use with XSD schemas, their descriptions, and the equivalent annotations for XDR.</span></span>  
  
 [<span data-ttu-id="c4c3c-116">Asignación predeterminada de elementos y atributos XSD a tablas y columnas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-116">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-117">Explica la asignación predeterminada y proporciona ejemplos de tareas relacionados con la asignación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-117">Explains default mapping and provides examples of tasks related to default mapping.</span></span>  
  
 [<span data-ttu-id="c4c3c-118">Asignación explícita de elementos y atributos XSD a tablas y columnas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-118">Explicit Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](explicit-mapping-xsd-elements-and-attributes-to-tables-and-columns.md)  
 <span data-ttu-id="c4c3c-119">Explica la asignación explícita con las anotaciones `sql:relation` y `sql:field` y proporciona ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-119">Explains explicit mapping with the `sql:relation` and `sql:field` annotations, and provides examples.</span></span>  
  
 [<span data-ttu-id="c4c3c-120">Especificar relaciones mediante SQL: Relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-120">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-121">Describe y proporciona ejemplos de la anotación `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-121">Describes and provides examples of the `sql:relationship` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-122">Especificar el atributo SQL: inverso en SQL: Relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-122">Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-123">Describe la anotación de `sql:inverse`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-123">Describes the `sql:inverse` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-124">Crear elementos constantes mediante SQL: is-Constant &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-124">Creating Constant Elements Using sql:is-constant &#40;SQLXML 4.0&#41;</span></span>](creating-constant-elements-using-sql-is-constant-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-125">Describe y proporciona ejemplos de la anotación `sql:is-constant`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-125">Describes and provides examples of the `sql:is-constant` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-126">Excluir elementos de esquema del documento XML resultante mediante SQL: asignado &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-126">Excluding Schema Elements from the Resulting XML Document Using sql:mapped &#40;SQLXML 4.0&#41;</span></span>](excluding-schema-elements-from-the-xml-document-using-sql-mapped.md)  
 <span data-ttu-id="c4c3c-127">Describe y proporciona ejemplos de la anotación `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-127">Describes and provides examples of the `sql:mapped` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-128">Filtrar valores mediante SQL: Limit-Field y SQL: Limit-Value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-128">Filtering Values Using sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="c4c3c-129">Describe y proporciona ejemplos de las anotaciones `sql:limit-field` y `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-129">Describes and provides examples of the `sql:limit-field` and `sql:limit-value` annotations.</span></span>  
  
 [<span data-ttu-id="c4c3c-130">Identificar columnas de clave mediante SQL: Key-Fields &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-130">Identifying Key Columns Using sql:key-fields &#40;SQLXML 4.0&#41;</span></span>](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-131">Describe y proporciona ejemplos de la anotación `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-131">Describes and provides examples of the `sql:key-fields` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-132">Especificar un espacio de nombres de destino mediante el atributo targetNamespace &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-132">Specifying a Target Namespace Using the targetNamespace Attribute &#40;SQLXML 4.0&#41;</span></span>](specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-133">Describe y proporciona ejemplos del atributo **targetNamespace** .</span><span class="sxs-lookup"><span data-stu-id="c4c3c-133">Describes and provides examples of the **targetNamespace** attribute.</span></span>  
  
 [<span data-ttu-id="c4c3c-134">Crear atributos válidos de tipo ID, IDREF e IDREFS mediante SQL: prefix &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-134">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix &#40;SQLXML 4.0&#41;</span></span>](creating-valid-id-idref-and-idrefs-type-attributes-using-sql-prefix-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-135">Describe y proporciona ejemplos de la anotación `sql:prefix`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-135">Describes and provides examples of the `sql:prefix` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-136">Las conversiones de tipos de datos y la anotación sql: DataType &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-136">Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;</span></span>](data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-137">Describe y proporciona ejemplos de la anotación `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-137">Describes and provides examples of the `sql:datatype` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-138">Asignar tipos de datos XSD a tipos de datos de XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-138">Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-139">Proporciona una tabla que compara XSD, XDR y tipos de datos XPath y enumera las conversiones [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pertinentes.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-139">Provides a table that compares XSD, XDR, and XPath datatypes and lists the relevant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conversions.</span></span>  
  
 [<span data-ttu-id="c4c3c-140">Crear secciones CDATA mediante SQL: Use-CDATA &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-140">Creating CDATA Sections Using sql:use-cdata &#40;SQLXML 4.0&#41;</span></span>](creating-cdata-sections-using-sql-use-cdata-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-141">Describe y proporciona ejemplos de la anotación `sql:use-data`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-141">Describes and provides examples of the `sql:use-data` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-142">Solicitar referencias URL a datos BLOB mediante SQL: encode &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-142">Requesting URL References to BLOB Data Using sql:encode &#40;SQLXML 4.0&#41;</span></span>](requesting-url-references-to-blob-data-using-sql-encode-sqlxml-4-0.md)  
 <span data-ttu-id="c4c3c-143">Describe y proporciona ejemplos de la anotación `sql:encode`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-143">Describes and provides examples of the `sql:encode` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-144">Recuperar datos no utilizados mediante SQL: Overflow-Field &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-144">Retrieving Unconsumed Data Using the sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="c4c3c-145">Describe y proporciona ejemplos de la anotación `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-145">Describes and provides examples of the `sql:overflow-field` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-146">Ocultar elementos y atributos mediante sql:hide</span><span class="sxs-lookup"><span data-stu-id="c4c3c-146">Hiding Elements and Attributes by Using sql:hide</span></span>](hiding-elements-and-attributes-by-using-sql-hide.md)  
 <span data-ttu-id="c4c3c-147">Describe y proporciona ejemplos de la anotación `sql:hide`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-147">Describes and provides examples of the `sql:hide` annotation.</span></span>  
  
 [<span data-ttu-id="c4c3c-148">Utilizar las anotaciones sql:guid y sql:identity</span><span class="sxs-lookup"><span data-stu-id="c4c3c-148">Using the sql:identity and sql:guid Annotations</span></span>](using-the-sql-identity-and-sql-guid-annotations.md)  
 <span data-ttu-id="c4c3c-149">Describe y proporciona ejemplos de las anotaciones `sql:identity` y `sql:guid`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-149">Describes and provides examples of the `sql:identity` and `sql:guid` annotations.</span></span>  
  
 [<span data-ttu-id="c4c3c-150">Especificar la profundidad en relaciones recursivas utilizando sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="c4c3c-150">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>](specifying-depth-in-recursive-relationships-by-using-sql-max-depth.md)  
 <span data-ttu-id="c4c3c-151">Describe y proporciona ejemplos de la anotación `sql:max-depth`.</span><span class="sxs-lookup"><span data-stu-id="c4c3c-151">Describes and provides examples of the `sql:max-depth` annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4c3c-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4c3c-152">See Also</span></span>  
 [<span data-ttu-id="c4c3c-153">Consideraciones sobre la seguridad del esquema anotado &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3c-153">Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md)  
  
  
