---
title: 'Conversiones de tipos de datos y la anotación sql: DataType (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping data types [SQLXML]
- type attribute
- sql:datatype
- data types [SQLXML], converting
- annotated XSD schemas, mapping data types
- xsd:type
- datatype annotation
- converting data types [SQLXML]
- data types [SQLXML], mapping data types
- XSD schemas [SQLXML], mapping data types
ms.assetid: db192105-e8aa-4392-b812-9d727918c005
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f1b0af93e3b596d74bc107ab6947b9855a2cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672898"
---
# <a name="data-type-coercions-and-the-sqldatatype-annotation-sqlxml-40"></a><span data-ttu-id="89f99-102">Conversión de tipos de datos y la anotación sql:datatype (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="89f99-102">Data Type Coercions and the sql:datatype Annotation (SQLXML 4.0)</span></span>
  <span data-ttu-id="89f99-103">En un esquema XSD, el atributo `xsd:type` especifica el tipo de datos XSD de un elemento o atributo.</span><span class="sxs-lookup"><span data-stu-id="89f99-103">In an XSD schema, the `xsd:type` attribute specifies the XSD data type of an element or attribute.</span></span> <span data-ttu-id="89f99-104">Cuando se usa un esquema XSD para extraer datos de la base de datos, el tipo de datos especificado se usa para dar formato a los datos.</span><span class="sxs-lookup"><span data-stu-id="89f99-104">When an XSD schema is used to extract data from the database, the data type specified is used to format the data.</span></span>  
  
 <span data-ttu-id="89f99-105">Además de especificar un tipo XSD en un esquema, también puede especificar un tipo de datos de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando la anotación `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="89f99-105">In addition to specifying an XSD type in a schema, you can also specify a Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type by using the `sql:datatype` annotation.</span></span> <span data-ttu-id="89f99-106">Los atributos `xsd:type` y `sql:datatype` controlan la asignación entre los tipos de datos XSD y los tipos de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89f99-106">The `xsd:type` and `sql:datatype` attributes control the mapping between XSD data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
## <a name="xsdtype-attribute"></a><span data-ttu-id="89f99-107">Atributo xsd:type</span><span class="sxs-lookup"><span data-stu-id="89f99-107">xsd:type Attribute</span></span>  
 <span data-ttu-id="89f99-108">Puede usar el atributo `xsd:type` para especificar el tipo de datos XML de un atributo o elemento que se asigna a una columna.</span><span class="sxs-lookup"><span data-stu-id="89f99-108">You can use the `xsd:type` attribute to specify the XML data type of an attribute or element that maps to a column.</span></span> <span data-ttu-id="89f99-109">`xsd:type` afecta al documento que se devuelve del servidor y también a la consulta XPath que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="89f99-109">The `xsd:type` affects the document that is returned from the server and also the XPath query that is executed.</span></span> <span data-ttu-id="89f99-110">Cuando una consulta XPath se ejecuta en un esquema de asignación que contiene el atributo `xsd:type`, XPath usa el tipo de datos especificado al procesar la consulta.</span><span class="sxs-lookup"><span data-stu-id="89f99-110">When an XPath query is executed against a mapping schema that contains `xsd:type`, XPath uses the specified data type when it processes the query.</span></span> <span data-ttu-id="89f99-111">Para obtener más información sobre el uso de XPath `xsd:type` , vea [asignar tipos de datos XSD a tipos de datos de XPath &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="89f99-111">For more information about how XPath uses `xsd:type`, see [Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="89f99-112">En un documento devuelto, todos los tipos de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se convierten en representaciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="89f99-112">In a returned document, all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types are converted into string representations.</span></span> <span data-ttu-id="89f99-113">Algunos tipos de datos requieren conversiones adicionales.</span><span class="sxs-lookup"><span data-stu-id="89f99-113">Some data types require additional conversions.</span></span> <span data-ttu-id="89f99-114">En la tabla siguiente se indican las conversiones que se usan para distintos valores de `xsd:type`.</span><span class="sxs-lookup"><span data-stu-id="89f99-114">The following table lists the conversions that are used for various `xsd:type` values.</span></span>  
  
|<span data-ttu-id="89f99-115">Tipo de datos XSD</span><span class="sxs-lookup"><span data-stu-id="89f99-115">XSD data type</span></span>|<span data-ttu-id="89f99-116">Conversión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="89f99-116">SQL Server conversion</span></span>|  
|-------------------|---------------------------|  
|<span data-ttu-id="89f99-117">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f99-117">Boolean</span></span>|<span data-ttu-id="89f99-118">CONVERT(bit, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="89f99-118">CONVERT(bit, COLUMN)</span></span>|  
|<span data-ttu-id="89f99-119">Date</span><span class="sxs-lookup"><span data-stu-id="89f99-119">Date</span></span>|<span data-ttu-id="89f99-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span><span class="sxs-lookup"><span data-stu-id="89f99-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span></span>|  
|<span data-ttu-id="89f99-121">Decimal</span><span class="sxs-lookup"><span data-stu-id="89f99-121">decimal</span></span>|<span data-ttu-id="89f99-122">CONVERT(money, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="89f99-122">CONVERT(money, COLUMN)</span></span>|  
|<span data-ttu-id="89f99-123">id/idref/idrefs</span><span class="sxs-lookup"><span data-stu-id="89f99-123">id/idref/idrefs</span></span>|<span data-ttu-id="89f99-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="89f99-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="89f99-125">nmtoken/nmtokens</span><span class="sxs-lookup"><span data-stu-id="89f99-125">nmtoken/nmtokens</span></span>|<span data-ttu-id="89f99-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="89f99-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="89f99-127">Time</span><span class="sxs-lookup"><span data-stu-id="89f99-127">Time</span></span>|<span data-ttu-id="89f99-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span><span class="sxs-lookup"><span data-stu-id="89f99-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span></span>|  
|<span data-ttu-id="89f99-129">Todos los demás</span><span class="sxs-lookup"><span data-stu-id="89f99-129">All others</span></span>|<span data-ttu-id="89f99-130">Ninguna conversión adicional</span><span class="sxs-lookup"><span data-stu-id="89f99-130">No additional conversion</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="89f99-131">Es posible que algunos de los valores devueltos por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no sean compatibles con los tipos de datos XML especificados con `xsd:type`, ya sea porque la conversión no es posible (por ejemplo, convertir "XYZ" en un tipo de datos `decimal`) o porque el valor supera el intervalo de ese tipo de datos (por ejemplo, -100000 convertido en un tipo XSD `UnsignedShort`).</span><span class="sxs-lookup"><span data-stu-id="89f99-131">Some of the values returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might not be compatible with the XML data types that are specified by using `xsd:type`, either because the conversion is not possible (for example, converting "XYZ" to a `decimal` data type) or because the value exceeds the range of that data type (for example, -100000 converted to an `UnsignedShort` XSD type).</span></span> <span data-ttu-id="89f99-132">Las conversiones de tipos incompatibles pueden dar lugar a documentos XML no válidos o a errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89f99-132">Incompatible type conversions might result in XML documents that are not valid, or in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] errors.</span></span>  
  
## <a name="mapping-from-sql-server-data-types-to-xsd-data-types"></a><span data-ttu-id="89f99-133">Asignar tipos de datos SQL Server a tipos de datos XSD</span><span class="sxs-lookup"><span data-stu-id="89f99-133">Mapping from SQL Server Data Types to XSD Data Types</span></span>  
 <span data-ttu-id="89f99-134">En la tabla siguiente se muestra una asignación obvia de tipos de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a tipos de datos XSD.</span><span class="sxs-lookup"><span data-stu-id="89f99-134">The following table shows an obvious mapping from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types to XSD data types.</span></span> <span data-ttu-id="89f99-135">Si se conoce el tipo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], esta tabla proporciona el tipo XSD correspondiente que puede especificarse en el esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="89f99-135">If you know the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type, this table provides the corresponding XSD type that you can specify in the XSD schema.</span></span>  
  
|<span data-ttu-id="89f99-136">Tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="89f99-136">SQL Server data type</span></span>|<span data-ttu-id="89f99-137">Tipo de datos XSD</span><span class="sxs-lookup"><span data-stu-id="89f99-137">XSD data type</span></span>|  
|--------------------------|-------------------|  
|`bigint`|`long`|  
|`binary`|`base64Binary`|  
|`bit`|`boolean`|  
|`char`|`string`|  
|`datetime`|`dateTime`|  
|`decimal`|`decimal`|  
|`float`|`double`|  
|`image`|`base64Binary`|  
|`int`|`int`|  
|`money`|`decimal`|  
|`nchar`|`string`|  
|`ntext`|`string`|  
|`nvarchar`|`string`|  
|`numeric`|`decimal`|  
|`real`|`float`|  
|`smalldatetime`|`dateTime`|  
|`smallint`|`short`|  
|`smallmoney`|`decimal`|  
|`sql_variant`|`string`|  
|`sysname`|`string`|  
|`text`|`string`|  
|`timestamp`|`dateTime`|  
|`tinyint`|`unsignedByte`|  
|`varbinary`|`base64Binary`|  
|`varchar`|`string`|  
|`uniqueidentifier`|`string`|  
  
## <a name="sqldatatype-annotation"></a><span data-ttu-id="89f99-138">Anotación sql:datatype</span><span class="sxs-lookup"><span data-stu-id="89f99-138">sql:datatype Annotation</span></span>  
 <span data-ttu-id="89f99-139">La anotación `sql:datatype` se usa para especificar el tipo de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; esta anotación debe especificarse cuando:</span><span class="sxs-lookup"><span data-stu-id="89f99-139">The `sql:datatype` annotation is used to specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type; this annotation must be specified when:</span></span>  
  
-   <span data-ttu-id="89f99-140">Está cargando de forma masiva en una `dateTime` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columna de un `dateTime` tipo XSD, `date` o `time` .</span><span class="sxs-lookup"><span data-stu-id="89f99-140">You are bulk loading into a `dateTime`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column from an XSD `dateTime`, `date`, or `time` type.</span></span> <span data-ttu-id="89f99-141">En este caso, debe identificar el tipo de datos de la columna [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando `sql:datatype="dateTime"`.</span><span class="sxs-lookup"><span data-stu-id="89f99-141">In this case, you must identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column data type by using `sql:datatype="dateTime"`.</span></span> <span data-ttu-id="89f99-142">Esta regla también se aplica a los diagramas de actualización.</span><span class="sxs-lookup"><span data-stu-id="89f99-142">This rule also applies to updategrams.</span></span>  
  
-   <span data-ttu-id="89f99-143">Está cargando de forma masiva en una columna de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` tipo y el valor XSD es un GUID que incluye llaves ({y}).</span><span class="sxs-lookup"><span data-stu-id="89f99-143">You are bulk loading into a column of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` type and the XSD value is a GUID that includes braces ({ and }).</span></span> <span data-ttu-id="89f99-144">Cuando se especifica `sql:datatype="uniqueidentifier"`, las llaves se quitan del valor antes de insertarlo en la columna.</span><span class="sxs-lookup"><span data-stu-id="89f99-144">When you specify `sql:datatype="uniqueidentifier"`, the braces are removed from the value before it is inserted in the column.</span></span> <span data-ttu-id="89f99-145">Si no se especifica `sql:datatype`, el valor se envía con las llaves y se produce un error en la inserción o actualización.</span><span class="sxs-lookup"><span data-stu-id="89f99-145">If `sql:datatype` is not specified, the value is sent with the braces, and the insert or update fails.</span></span>  
  
-   <span data-ttu-id="89f99-146">El tipo de datos XML `base64Binary` se asigna a varios tipos de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (`binary`, `image` o `varbinary`).</span><span class="sxs-lookup"><span data-stu-id="89f99-146">The XML data type `base64Binary` maps to various [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types (`binary`, `image`, or `varbinary`).</span></span> <span data-ttu-id="89f99-147">Para asignar el tipo de datos XML `base64Binary` a un tipo de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concreto, use la anotación `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="89f99-147">To map the XML data type `base64Binary` to a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, use the `sql:datatype` annotation.</span></span> <span data-ttu-id="89f99-148">Esta anotación especifica el tipo de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explícito de la columna a la que asigna el atributo.</span><span class="sxs-lookup"><span data-stu-id="89f99-148">This annotation specifies the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the column to which the attribute maps.</span></span> <span data-ttu-id="89f99-149">Esto resulta de gran utilidad cuando los datos se almacenan en las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="89f99-149">This is useful when data is being stored in the databases.</span></span> <span data-ttu-id="89f99-150">Puede identificar el tipo de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explícito especificando la anotación `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="89f99-150">By specifying the `sql:datatype` annotation, you can identify the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="89f99-151">Generalmente, es recomendable especificar `sql:datatype` en el esquema.</span><span class="sxs-lookup"><span data-stu-id="89f99-151">It is generally recommended that you specify `sql:datatype` in the schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="89f99-152">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="89f99-152">Examples</span></span>  
 <span data-ttu-id="89f99-153">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="89f99-153">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="89f99-154">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="89f99-154">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-xsdtype"></a><span data-ttu-id="89f99-155">A.</span><span class="sxs-lookup"><span data-stu-id="89f99-155">A.</span></span> <span data-ttu-id="89f99-156">Especificar xsd:type</span><span class="sxs-lookup"><span data-stu-id="89f99-156">Specifying xsd:type</span></span>  
 <span data-ttu-id="89f99-157">En este ejemplo se muestra cómo un tipo `date` de XSD que se especifica mediante el atributo `xsd:type` en el esquema afecta al documento XML resultante.</span><span class="sxs-lookup"><span data-stu-id="89f99-157">This example shows how an XSD `date` type that is specified by using the `xsd:type` attribute in the schema affects the resulting XML document.</span></span> <span data-ttu-id="89f99-158">El esquema proporciona una vista XML de la tabla Sales.SalesOrderHeader de la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="89f99-158">The schema provides an XML view of the Sales.SalesOrderHeader table in the AdventureWorks database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader">  
     <xsd:complexType>  
       <xsd:attribute name="SalesOrderID" type="xsd:string" />   
       <xsd:attribute name="CustomerID"   type="xsd:string" />   
       <xsd:attribute name="OrderDate"    type="xsd:date" />   
       <xsd:attribute name="DueDate"  />   
       <xsd:attribute name="ShipDate"  type="xsd:time" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="89f99-159">En este esquema XSD, hay tres atributos que devuelven un valor de fecha de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89f99-159">In this XSD schema, there are three attributes that return a date value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="89f99-160">Cuando el esquema:</span><span class="sxs-lookup"><span data-stu-id="89f99-160">When the schema:</span></span>  
  
-   <span data-ttu-id="89f99-161">Especifica `xsd:type=date` en el atributo **OrderDate** , se muestra la parte de fecha del valor devuelto por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para el atributo **OrderDate** .</span><span class="sxs-lookup"><span data-stu-id="89f99-161">Specifies `xsd:type=date` on the **OrderDate** attribute, the date part of the value returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **OrderDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="89f99-162">Especifica `xsd:type=time` en el atributo **ShipDate** , se muestra la parte de hora del valor devuelto por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para el atributo **ShipDate** .</span><span class="sxs-lookup"><span data-stu-id="89f99-162">Specifies `xsd:type=time` on the **ShipDate** attribute, the time part of the value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **ShipDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="89f99-163">No especifica `xsd:type` en el atributo **DueDate** , se muestra el mismo valor devuelto por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="89f99-163">Does not specify `xsd:type` on the **DueDate** attribute, the same value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is displayed.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="89f99-164">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="89f99-164">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="89f99-165">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="89f99-165">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="89f99-166">Guarde el archivo como xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="89f99-166">Save the file as xsdType.xml.</span></span>  
  
2.  <span data-ttu-id="89f99-167">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="89f99-167">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="89f99-168">Guarde el archivo como xsdTypeT.xml en el mismo directorio donde guardó xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="89f99-168">Save the file as xsdTypeT.xml in the same directory where you saved xsdType.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="xsdType.xml">  
        /Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="89f99-169">La ruta de acceso al directorio especificada para el esquema de asignación (xsdType.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="89f99-169">The directory path specified for the mapping schema (xsdType.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="89f99-170">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="89f99-170">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\xsdType.xml"  
    ```  
  
3.  <span data-ttu-id="89f99-171">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="89f99-171">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="89f99-172">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="89f99-172">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="89f99-173">Éste es el conjunto de resultados parciales:</span><span class="sxs-lookup"><span data-stu-id="89f99-173">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43659"   
         CustomerID="676"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
  <Order SalesOrderID="43660"   
         CustomerID="117"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
 ...  
</ROOT>  
```  
  
 <span data-ttu-id="89f99-174">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="89f99-174">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader">  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="CustomerID"  />  
    <AttributeType name="OrderDate" dt:type="date" />  
    <AttributeType name="DueDate" />  
    <AttributeType name="ShipDate" dt:type="time" />  
  
    <attribute type="SalesOrderID" sql:field="OrderID" />  
    <attribute type="CustomerID" sql:field="CustomerID" />  
    <attribute type="OrderDate" sql:field="OrderDate" />  
    <attribute type="DueDate" sql:field="DueDate" />  
    <attribute type="ShipDate" sql:field="ShipDate" />  
</ElementType>  
</Schema>  
```  
  
### <a name="b-specifying-sql-data-type-using-sqldatatype"></a><span data-ttu-id="89f99-175">B.</span><span class="sxs-lookup"><span data-stu-id="89f99-175">B.</span></span> <span data-ttu-id="89f99-176">Especificar el tipo de datos SQL usando sql:datatype</span><span class="sxs-lookup"><span data-stu-id="89f99-176">Specifying SQL data type using sql:datatype</span></span>  
 <span data-ttu-id="89f99-177">Para obtener un ejemplo funcional, vea el ejemplo G en [ejemplos de carga masiva XML &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="89f99-177">For a working sample, see Example G in [XML Bulk Load Examples &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span></span> <span data-ttu-id="89f99-178">En este ejemplo, se carga de forma masiva un valor GUID que incluye "{" y "}".</span><span class="sxs-lookup"><span data-stu-id="89f99-178">In this example, a GUID value including "{" and "}" is bulk loaded.</span></span> <span data-ttu-id="89f99-179">El esquema de este ejemplo especifica `sql:datatype` para identificar el tipo de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como `uniqueidentifier`.</span><span class="sxs-lookup"><span data-stu-id="89f99-179">The schema in this example specifies `sql:datatype` to identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as `uniqueidentifier`.</span></span> <span data-ttu-id="89f99-180">En este ejemplo se muestra cuándo debe especificarse `sql:datatype` en el esquema.</span><span class="sxs-lookup"><span data-stu-id="89f99-180">This example illustrate when `sql:datatype` must be specified in the schema.</span></span>  
  
  
