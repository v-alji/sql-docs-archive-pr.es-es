---
title: Recuperar y consultar datos XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], retrieving
- XML instance retrieval
ms.assetid: 24a28760-1225-42b3-9c89-c9c0332d9c51
author: rothja
ms.author: jroth
ms.openlocfilehash: d387d1b96a57dcc7100368779f8ec6078fad5c7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745073"
---
# <a name="retrieve-and-query-xml-data"></a><span data-ttu-id="b756e-102">Recuperar y consultar datos XML</span><span class="sxs-lookup"><span data-stu-id="b756e-102">Retrieve and Query XML Data</span></span>
  <span data-ttu-id="b756e-103">En este tema se describen las opciones de consulta que se tienen que especificar para consultar datos XML.</span><span class="sxs-lookup"><span data-stu-id="b756e-103">This topic describes the query options that you have to specify to query XML data.</span></span> <span data-ttu-id="b756e-104">También describe las partes de las instancias XML que no se conservan cuando se almacenan en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="b756e-104">It also describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>  
  
##  <a name="features-of-an-xml-instance-that-are-not-preserved"></a><a name="features"></a> <span data-ttu-id="b756e-105">Características de una instancia de XML que no se mantienen</span><span class="sxs-lookup"><span data-stu-id="b756e-105">Features of an XML Instance That Are Not Preserved</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b756e-106">conserva el contenido de la instancia XML, pero no conserva los aspectos de la instancia XML que no se consideran significativos en el modelo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="b756e-106">preserves the content of the XML instance, but does not preserve aspects of the XML instance that are not considered to be significant in the XML data model.</span></span> <span data-ttu-id="b756e-107">Esto significa que una instancia XML recuperada no podría ser idéntica a la instancia que se almacenó en el servidor pero contendrá la misma información.</span><span class="sxs-lookup"><span data-stu-id="b756e-107">This means that a retrieved XML instance might not be identical to the instance that was stored in the server, but will contain the same information.</span></span>  
  
### <a name="xml-declaration"></a><span data-ttu-id="b756e-108">Declaración XML</span><span class="sxs-lookup"><span data-stu-id="b756e-108">XML Declaration</span></span>  
 <span data-ttu-id="b756e-109">La declaración XML de una instancia no se conserva cuando la instancia está almacenada en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b756e-109">The XML declaration in an instance is not preserved when the instance is stored in the database.</span></span> <span data-ttu-id="b756e-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b756e-110">For example:</span></span>  
  
```  
CREATE TABLE T1 (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T1 values (1, '<?xml version="1.0" encoding="windows-1252" ?><doc></doc>')  
GO  
SELECT Col2  
FROM T1  
```  
  
 <span data-ttu-id="b756e-111">El resultado es `<doc/>`.</span><span class="sxs-lookup"><span data-stu-id="b756e-111">The result is `<doc/>`.</span></span>  
  
 <span data-ttu-id="b756e-112">No se conserva la declaración XML, como `<?xml version='1.0'?>`, al almacenar los datos XML en una instancia de tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="b756e-112">The XML declaration, such as `<?xml version='1.0'?>`, is not preserved when storing XML data in an `xml` data type instance.</span></span> <span data-ttu-id="b756e-113">es así por diseño.</span><span class="sxs-lookup"><span data-stu-id="b756e-113">This is by design.</span></span> <span data-ttu-id="b756e-114">La declaración XML () y sus atributos (versión/codificación/independiente) se pierden cuando los datos se convierten al tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="b756e-114">The XML declaration () and its attributes (version/encoding/stand-alone) are lost after data is converted to type `xml`.</span></span> <span data-ttu-id="b756e-115">La declaración XML se trata como una directiva del analizador XML.</span><span class="sxs-lookup"><span data-stu-id="b756e-115">The XML declaration is treated as a directive to the XML parser.</span></span> <span data-ttu-id="b756e-116">Los datos XML se almacenan internamente como ucs-2.</span><span class="sxs-lookup"><span data-stu-id="b756e-116">The XML data is stored internally as ucs-2.</span></span> <span data-ttu-id="b756e-117">Se conservan todos los demás PI en la instancia XML.</span><span class="sxs-lookup"><span data-stu-id="b756e-117">All other PIs in the XML instance are preserved.</span></span>  
  
  
### <a name="order-of-attributes"></a><span data-ttu-id="b756e-118">Orden de atributos</span><span class="sxs-lookup"><span data-stu-id="b756e-118">Order of Attributes</span></span>  
 <span data-ttu-id="b756e-119">El orden de los atributos de una instancia XML no se conserva.</span><span class="sxs-lookup"><span data-stu-id="b756e-119">The order of attributes in an XML instance is not preserved.</span></span> <span data-ttu-id="b756e-120">Al consultar la instancia XML almacenada en la columna de tipo `xml`, el orden de los atributos del XML resultante puede diferir con respecto a la instancia XML original.</span><span class="sxs-lookup"><span data-stu-id="b756e-120">When you query the XML instance stored in the `xml` type column, the order of attributes in the resulting XML may be different from the original XML instance.</span></span>  
  
  
### <a name="quotation-marks-around-attribute-values"></a><span data-ttu-id="b756e-121">Comillas alrededor de valores de atributo</span><span class="sxs-lookup"><span data-stu-id="b756e-121">Quotation Marks Around Attribute Values</span></span>  
 <span data-ttu-id="b756e-122">Alrededor de los valores de atributo no se conservan las comillas simples ni las comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="b756e-122">Single quotation marks and double quotations marks around attribute values are not preserved.</span></span> <span data-ttu-id="b756e-123">Los valores de atributo se almacenan en la base de datos como un par de nombre y valor.</span><span class="sxs-lookup"><span data-stu-id="b756e-123">The attribute values are stored in the database as a name and value pair.</span></span> <span data-ttu-id="b756e-124">Las comillas no se almacenan.</span><span class="sxs-lookup"><span data-stu-id="b756e-124">The quotation marks are not stored.</span></span> <span data-ttu-id="b756e-125">Cuando se ejecuta una consulta XQuery en una instancia XML, el XML resultante se serializa con comillas dobles alrededor de los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="b756e-125">When an XQuery is executed against an XML instance, the resulting XML is serialized with double quotation marks around the attribute values.</span></span>  
  
```  
DECLARE @x xml  
-- Use double quotation marks.  
SET @x = '<root a="1" />'  
SELECT @x  
GO  
DECLARE @x xml  
-- Use single quotation marks.  
SET @x = '<root a=''1'' />'  
SELECT @x  
GO  
```  
  
 <span data-ttu-id="b756e-126">Las dos consultas devuelven = `<root a="1" />`.</span><span class="sxs-lookup"><span data-stu-id="b756e-126">Both queries return = `<root a="1" />`.</span></span>  
  
  
### <a name="namespace-prefixes"></a><span data-ttu-id="b756e-127">Prefijos de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b756e-127">Namespace Prefixes</span></span>  
 <span data-ttu-id="b756e-128">No se conservan los prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b756e-128">Namespace prefixes are not preserved.</span></span> <span data-ttu-id="b756e-129">Cuando se especifica XQuery en una columna de tipo `xml`, el resultado XML serializado puede devolver distintos prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b756e-129">When you specify XQuery against an `xml` type column, the serialized XML result may return different namespace prefixes.</span></span>  
  
```  
DECLARE @x xml  
SET @x = '<ns1:root xmlns:ns1="abc" xmlns:ns2="abc">  
            <ns2:SomeElement/>  
          </ns1:root>'  
SELECT @x  
SELECT @x.query('/*')  
GO  
```  
  
 <span data-ttu-id="b756e-130">El prefijo de espacio de nombres del resultado puede ser distinto.</span><span class="sxs-lookup"><span data-stu-id="b756e-130">The namespace prefix in the result may be different.</span></span> <span data-ttu-id="b756e-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b756e-131">For example:</span></span>  
  
```  
<p1:root xmlns:p1="abc"><p1:SomeElement/></p1:root>  
```  
  
  
##  <a name="setting-required-query-options"></a><a name="query"></a> <span data-ttu-id="b756e-132">Establecer opciones de consulta necesarias</span><span class="sxs-lookup"><span data-stu-id="b756e-132">Setting Required Query Options</span></span>  
 <span data-ttu-id="b756e-133">Al consultar las `xml` columnas de tipo o las variables mediante `xml` métodos de tipo de datos, se deben establecer las siguientes opciones como se muestra.</span><span class="sxs-lookup"><span data-stu-id="b756e-133">When querying `xml` type columns or variables using `xml` data type methods, the following options must be set as shown.</span></span>  
  
|<span data-ttu-id="b756e-134">Opciones de SET</span><span class="sxs-lookup"><span data-stu-id="b756e-134">SET Options</span></span>|<span data-ttu-id="b756e-135">Valores requeridos</span><span class="sxs-lookup"><span data-stu-id="b756e-135">Required Values</span></span>|  
|-----------------|---------------------|  
|<span data-ttu-id="b756e-136">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="b756e-136">ANSI_NULLS</span></span>|<span data-ttu-id="b756e-137">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="b756e-137">ON</span></span>|  
|<span data-ttu-id="b756e-138">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="b756e-138">ANSI_PADDING</span></span>|<span data-ttu-id="b756e-139">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="b756e-139">ON</span></span>|  
|<span data-ttu-id="b756e-140">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="b756e-140">ANSI_WARNINGS</span></span>|<span data-ttu-id="b756e-141">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="b756e-141">ON</span></span>|  
|<span data-ttu-id="b756e-142">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="b756e-142">ARITHABORT</span></span>|<span data-ttu-id="b756e-143">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="b756e-143">ON</span></span>|  
|<span data-ttu-id="b756e-144">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="b756e-144">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="b756e-145">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="b756e-145">ON</span></span>|  
|<span data-ttu-id="b756e-146">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="b756e-146">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="b756e-147">Apagado</span><span class="sxs-lookup"><span data-stu-id="b756e-147">OFF</span></span>|  
|<span data-ttu-id="b756e-148">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="b756e-148">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="b756e-149">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="b756e-149">ON</span></span>|  
  
 <span data-ttu-id="b756e-150">Si no se establecen las opciones como se muestra, las consultas y modificaciones de `xml` los métodos de tipo de datos generarán un error.</span><span class="sxs-lookup"><span data-stu-id="b756e-150">If the options are not set as shown, queries and modifications on `xml` data type methods will fail.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="b756e-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b756e-151">See Also</span></span>  
 [<span data-ttu-id="b756e-152">Crear instancias de datos XML</span><span class="sxs-lookup"><span data-stu-id="b756e-152">Create Instances of XML Data</span></span>](create-instances-of-xml-data.md)  
  
  
