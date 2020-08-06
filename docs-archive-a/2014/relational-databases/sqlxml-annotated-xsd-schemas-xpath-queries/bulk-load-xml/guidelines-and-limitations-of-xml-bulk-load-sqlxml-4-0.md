---
title: Instrucciones y limitaciones de la carga masiva XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], about XML Bulk Load
- bulk load [SQLXML], about bulk load
ms.assetid: c5885d14-c7c1-47b3-a389-455e99a7ece1
author: rothja
ms.author: jroth
ms.openlocfilehash: 08c0020ac7b28702f5a573c6158ec9d50c735b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674747"
---
# <a name="guidelines-and-limitations-of-xml-bulk-load-sqlxml-40"></a><span data-ttu-id="7102a-102">Instrucciones y limitaciones de la carga masiva XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7102a-102">Guidelines and Limitations of XML Bulk Load (SQLXML 4.0)</span></span>
  <span data-ttu-id="7102a-103">Antes de usar la carga masiva XML, debe familiarizarse con las siguientes limitaciones e instrucciones:</span><span class="sxs-lookup"><span data-stu-id="7102a-103">When you use XML Bulk Load, you should be familiar with the following guidelines and limitations:</span></span>  
  
-   <span data-ttu-id="7102a-104">No se admiten los esquemas insertados.</span><span class="sxs-lookup"><span data-stu-id="7102a-104">Inline schemas are not supported.</span></span>  
  
     <span data-ttu-id="7102a-105">Si tiene un esquema insertado en el documento XML de origen, la carga masiva XML omite dicho esquema.</span><span class="sxs-lookup"><span data-stu-id="7102a-105">If you have an inline schema in the source XML document, XML Bulk Load ignores that schema.</span></span> <span data-ttu-id="7102a-106">Debe especificar el esquema de asignación para la carga masiva XML de forma externa con respecto a los datos XML.</span><span class="sxs-lookup"><span data-stu-id="7102a-106">You specify the mapping schema for XML Bulk Load external to the XML data.</span></span> <span data-ttu-id="7102a-107">No se puede especificar el esquema de asignación en un nodo mediante el atributo **xmlns = "x:Schema"** .</span><span class="sxs-lookup"><span data-stu-id="7102a-107">You cannot specify the mapping schema at a node by using the **xmlns="x:schema"** attribute.</span></span>  
  
-   <span data-ttu-id="7102a-108">Se comprueba que el formato de un documento XML sea correcto, pero no se valida el documento.</span><span class="sxs-lookup"><span data-stu-id="7102a-108">An XML document is checked for being well-formed, but it is not validated.</span></span>  
  
     <span data-ttu-id="7102a-109">La carga masiva XML comprueba el documento XML para determinar si está bien formada; es decir, para asegurarse de que el XML cumple los requisitos de sintaxis de la recomendación 1,0 de XML del World Wide Web Consortium.</span><span class="sxs-lookup"><span data-stu-id="7102a-109">XML Bulk Load checks the XML document to determine whether it is well-formed-that is, to ensure that the XML conforms to the syntax requirements of the World Wide Web Consortium's XML 1.0 recommendation.</span></span> <span data-ttu-id="7102a-110">Si el documento no tiene el formato correcto, la carga masiva XML cancela el procesamiento y devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="7102a-110">If the document is not well-formed, XML Bulk Load cancels processing and returns an error.</span></span> <span data-ttu-id="7102a-111">La única excepción a esta regla es que el documento sea un fragmento (por ejemplo, el documento no tiene ningún elemento raíz único), en cuyo caso la carga masiva XML cargará el documento.</span><span class="sxs-lookup"><span data-stu-id="7102a-111">The only exception to this is when the document is a fragment (for example, the document has no single root element), in which case XML Bulk Load will load the document.</span></span>  
  
     <span data-ttu-id="7102a-112">La carga masiva XML no valida el documento con respecto a cualquier esquema de datos XML o esquema DTD que se defina o al que se haga referencia dentro del archivo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="7102a-112">XML Bulk Load does not validate the document with respect to any XML-Data or DTD schema that is defined or referenced within the XML data file.</span></span> <span data-ttu-id="7102a-113">Además, la carga masiva XML no valida el archivo de datos XML en el esquema de asignación proporcionado.</span><span class="sxs-lookup"><span data-stu-id="7102a-113">In addition, XML Bulk Load does not validate the XML data file against the mapping schema supplied.</span></span>  
  
-   <span data-ttu-id="7102a-114">Se omite cualquier información de prólogo XML.</span><span class="sxs-lookup"><span data-stu-id="7102a-114">Any XML prolog information is ignored.</span></span>  
  
     <span data-ttu-id="7102a-115">La carga masiva XML omite toda la información antes y después del \<root> elemento en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="7102a-115">XML Bulk Load ignores all the information before and after the \<root> element in the XML document.</span></span> <span data-ttu-id="7102a-116">Por ejemplo, la carga masiva XML omite todas las declaraciones XML, definiciones DTD internas, referencias DTD externas, todos los comentarios, etc.</span><span class="sxs-lookup"><span data-stu-id="7102a-116">For example, XML Bulk Load ignores any XML declarations, internal DTD definitions, external DTD references, comments, and so on.</span></span>  
  
-   <span data-ttu-id="7102a-117">Si tiene un esquema de asignación que define una relación de clave principal y clave externa entre dos tablas (como Customer y CustOrder), la tabla con la clave principal debe describirse en primer lugar en el esquema.</span><span class="sxs-lookup"><span data-stu-id="7102a-117">If you have a mapping schema that defines a primary key/foreign key relationship between two tables (such as between Customer and CustOrder), the table with the primary key must be described first in the schema.</span></span> <span data-ttu-id="7102a-118">La tabla con la columna de clave externa debe aparecer posteriormente en el esquema.</span><span class="sxs-lookup"><span data-stu-id="7102a-118">The table with the foreign key column must appear later in the schema.</span></span> <span data-ttu-id="7102a-119">El motivo es que el orden en el que se identifican las tablas en el esquema es el que se usa para cargarlos en la base de datos. Por ejemplo, el esquema XDR siguiente generará un error si se utiliza en la carga masiva XML porque el **\<Order>** elemento se describe antes que el **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="7102a-119">The reason for this is that the order in which the tables are identified in the schema is the order that is used to load them into the database.For example, the following XDR schema will produce an error when it is used in XML Bulk Load because the **\<Order>** element is described before the **\<Customer>** element.</span></span> <span data-ttu-id="7102a-120">La columna CustomerID de CustOrder es una columna de clave externa que hace referencia a la columna de clave principal CustomerID de la tabla Cust.</span><span class="sxs-lookup"><span data-stu-id="7102a-120">The CustomerID column in CustOrder is a foreign key column that refers to the CustomerID primary key column in the Cust table.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
        <ElementType name="Order" sql:relation="CustOrder" >  
          <AttributeType name="OrderID" />  
          <AttributeType name="CustomerID" />  
          <attribute type="OrderID" />  
          <attribute type="CustomerID" />  
        </ElementType>  
  
       <ElementType name="CustomerID" dt:type="int" />  
       <ElementType name="CompanyName" dt:type="string" />  
       <ElementType name="City" dt:type="string" />  
  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
       <ElementType name="Customers" sql:relation="Cust"   
                         sql:overflow-field="OverflowColumn"  >  
          <element type="CustomerID" sql:field="CustomerID" />  
          <element type="CompanyName" sql:field="CompanyName" />  
          <element type="City" sql:field="City" />  
          <element type="Order" >   
               <sql:relationship  
                   key-relation="Cust"  
                    key="CustomerID"  
                    foreign-key="CustomerID"  
                    foreign-relation="CustOrder" />  
          </element>  
       </ElementType>  
    </Schema>  
    ```  
  
-   <span data-ttu-id="7102a-121">Si el esquema no especifica las columnas de desbordamiento mediante la anotación `sql:overflow-field`, la carga masiva XML omite todos los datos presentes en el documento XML que no se describen en el esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="7102a-121">If the schema does not specify overflow columns by using the `sql:overflow-field` annotation, XML Bulk Load ignores any data that is present in the XML document but is not described in the mapping schema.</span></span>  
  
     <span data-ttu-id="7102a-122">La carga masiva XML aplica el esquema de asignación especificado cada vez que encuentra etiquetas conocidas en el flujo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="7102a-122">XML Bulk Load applies the mapping schema that you have specified whenever it encounters known tags in the XML data stream.</span></span> <span data-ttu-id="7102a-123">Omite los datos presentes en el documento XML que no se describen en el esquema.</span><span class="sxs-lookup"><span data-stu-id="7102a-123">It ignores data that is present in the XML document but is not described in the schema.</span></span> <span data-ttu-id="7102a-124">Por ejemplo, suponga que tiene un esquema de asignación que describe un **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="7102a-124">For example, assume you have a mapping schema that describes a **\<Customer>** element.</span></span> <span data-ttu-id="7102a-125">El archivo de datos XML tiene una **\<AllCustomers>** etiqueta raíz (que no se describe en el esquema) que incluye todos los **\<Customer>** elementos:</span><span class="sxs-lookup"><span data-stu-id="7102a-125">The XML data file has an **\<AllCustomers>** root tag (which is not described in the schema) that encloses all the **\<Customer>** elements:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
      <Customer>...</Customer>  
       ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="7102a-126">En este caso, la carga masiva XML omite el **\<AllCustomers>** elemento y comienza la asignación en el **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="7102a-126">In this case, XML Bulk Load ignores the **\<AllCustomers>** element and begins mapping at the **\<Customer>** element.</span></span> <span data-ttu-id="7102a-127">La carga masiva XML omite los elementos que no se describen en el esquema pero que están presentes en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="7102a-127">XML Bulk Load ignores the elements that are not described in the schema but are present in the XML document.</span></span>  
  
     <span data-ttu-id="7102a-128">Considere otro archivo de datos de origen XML que contenga **\<Order>** elementos.</span><span class="sxs-lookup"><span data-stu-id="7102a-128">Consider another XML source data file that contains **\<Order>** elements.</span></span> <span data-ttu-id="7102a-129">Estos elementos no se describen en el esquema de asignación:</span><span class="sxs-lookup"><span data-stu-id="7102a-129">These elements are not described in the mapping schema:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="7102a-130">La carga masiva XML omite estos **\<Order>** elementos.</span><span class="sxs-lookup"><span data-stu-id="7102a-130">XML Bulk Load ignores these **\<Order>** elements.</span></span> <span data-ttu-id="7102a-131">Pero si utiliza la `sql:overflow-field` anotación en el esquema para identificar una columna como una columna de desbordamiento, la carga masiva XML almacena todos los datos no consumidos en esta columna.</span><span class="sxs-lookup"><span data-stu-id="7102a-131">But if you use the `sql:overflow-field`annotation in the schema to identify a column as an overflow column, XML Bulk Load stores all unconsumed data in this column.</span></span>  
  
-   <span data-ttu-id="7102a-132">Las secciones CDATA y las referencias a entidades se traducen a sus cadenas equivalentes antes de almacenarse en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7102a-132">CDATA sections and entity references are translated to their string equivalents before they are stored in the database.</span></span>  
  
     <span data-ttu-id="7102a-133">En este ejemplo, una sección CDATA ajusta el valor del **\<City>** elemento.</span><span class="sxs-lookup"><span data-stu-id="7102a-133">In this example, a CDATA section wraps the value for the **\<City>** element.</span></span> <span data-ttu-id="7102a-134">La carga masiva XML extrae el valor de cadena ("NY") antes de insertar el **\<City>** elemento en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7102a-134">XML Bulk Load extracts the string value ("NY") before it inserts the **\<City>** element into the database.</span></span>  
  
    ```  
    <City><![CDATA[NY]]> </City>  
    ```  
  
     <span data-ttu-id="7102a-135">La carga masiva XML no conserva las referencias a entidades.</span><span class="sxs-lookup"><span data-stu-id="7102a-135">XML Bulk Load does not preserve entity references.</span></span>  
  
-   <span data-ttu-id="7102a-136">Si el esquema de asignación especifica el valor predeterminado de un atributo y los datos de origen XML no contienen dicho atributo, la carga masiva XML usa el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7102a-136">If the mapping schema specifies the default value for an attribute and the XML source data does not contain that attribute, XML Bulk Load uses the default value.</span></span>  
  
     <span data-ttu-id="7102a-137">El siguiente esquema XDR de ejemplo asigna un valor predeterminado al atributo **HireDate** :</span><span class="sxs-lookup"><span data-stu-id="7102a-137">The following sample XDR schema assigns a default value to the **HireDate** attribute:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
  
       <ElementType name="Customers" sql:relation="Cust3" >  
          <AttributeType name="CustomerID" dt:type="int"  />  
          <AttributeType name="HireDate"  default="2000-01-01" />  
          <AttributeType name="Salary"   />  
  
          <attribute type="CustomerID" sql:field="CustomerID" />  
          <attribute type="HireDate"   sql:field="HireDate"  />  
          <attribute type="Salary"     sql:field="Salary"    />  
       </ElementType>  
    </Schema>  
    ```  
  
     <span data-ttu-id="7102a-138">En estos datos XML, falta el atributo **HireDate** en el segundo **\<Customers>** elemento.</span><span class="sxs-lookup"><span data-stu-id="7102a-138">In this XML data, the **HireDate** attribute is missing from the second **\<Customers>** element.</span></span> <span data-ttu-id="7102a-139">Cuando la carga masiva XML inserta el segundo **\<Customers>** elemento en la base de datos, utiliza el valor predeterminado que se especifica en el esquema.</span><span class="sxs-lookup"><span data-stu-id="7102a-139">When XML Bulk Load inserts the second **\<Customers>** element into the database, it uses the default value that is specified in the schema.</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1" HireDate="1999-01-01" Salary="10000" />  
      <Customers CustomerID="2" Salary="10000" />  
    </ROOT>  
    ```  
  
-   <span data-ttu-id="7102a-140">No se admite la anotación `sql:url-encode`:</span><span class="sxs-lookup"><span data-stu-id="7102a-140">The `sql:url-encode` annotation is not supported:</span></span>  
  
     <span data-ttu-id="7102a-141">No puede especificar una dirección URL en la entrada de datos XML y esperar que la carga masiva lea los datos de dicha ubicación.</span><span class="sxs-lookup"><span data-stu-id="7102a-141">You cannot specify a URL in the XML data input and expect Bulk Load to read data from that location.</span></span>  
  
     <span data-ttu-id="7102a-142">Se crean las tablas que se identifican en el esquema de asignación (la base de datos debe existir).</span><span class="sxs-lookup"><span data-stu-id="7102a-142">The tables that are identified in the mapping schema are created (the database must exist).</span></span> <span data-ttu-id="7102a-143">Si una o más tablas ya existen en la base de datos, la propiedad SGDropTables determina si estas tablas preexistentes se van a quitar y volver a crear.</span><span class="sxs-lookup"><span data-stu-id="7102a-143">If one or more of the tables already exists in the database, the SGDropTables property determines whether these preexisting tables are to be dropped and re-created.</span></span>  
  
-   <span data-ttu-id="7102a-144">Si especifica la propiedad SchemaGen (por ejemplo, SchemaGen = true), se crean las tablas que se identifican en el esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="7102a-144">If you specify the SchemaGen property (for example, SchemaGen = true), the tables that are identified in the mapping schema are created.</span></span> <span data-ttu-id="7102a-145">Pero SchemaGen no crea ninguna restricción (como las restricciones de clave principal y clave externa) en estas tablas con una excepción: si los nodos XML que constituyen la clave principal de una relación se definen como si tuvieran un tipo XML de identificador (es decir, `type="xsd:ID"` para XSD) y la propiedad SGUseID se establece en true para SchemaGen, no solo se crean las claves principales a partir de los nodos con tipo ID, pero las relaciones de clave principal y clave externa se crean a partir de las relaciones de esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="7102a-145">But SchemaGen does not create any constraints (such as the PRIMARY KEY/FOREIGN KEY constraints) on these tables with one exception: If the XML nodes that constitute the primary key in a relationship are defined as having an XML type of ID (that is, `type="xsd:ID"` for XSD) AND the SGUseID property is set to True for SchemaGen, then not only are primary keys created from the ID typed nodes, but primary key/foreign key relationships are created from mapping schema relationships.</span></span>  
  
-   <span data-ttu-id="7102a-146">SchemaGen no utiliza las extensiones y las caras del esquema XSD para generar el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="7102a-146">SchemaGen does not use XSD schema facets and extensions to generate the relational [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] schema.</span></span>  
  
-   <span data-ttu-id="7102a-147">Si especifica la propiedad SchemaGen (por ejemplo, SchemaGen = true) en la carga masiva, solo se actualizarán las tablas (y no las vistas de nombre compartido) que se especifiquen.</span><span class="sxs-lookup"><span data-stu-id="7102a-147">If you specify the SchemaGen property (for example, SchemaGen = true) on Bulk Load, only tables (and not views of shared name) that are specified are updated.</span></span>  
  
-   <span data-ttu-id="7102a-148">SchemaGen solo proporciona la funcionalidad básica para generar el esquema relacional a partir de XSD anotado.</span><span class="sxs-lookup"><span data-stu-id="7102a-148">SchemaGen only provides basic functionality for generating the relational schema from annotated XSD.</span></span> <span data-ttu-id="7102a-149">El usuario debe modificar las tablas generadas manualmente si es preciso.</span><span class="sxs-lookup"><span data-stu-id="7102a-149">The user should modify the generated tables manually, if needed.</span></span>  
  
-   <span data-ttu-id="7102a-150">Cuando existe más de una relación entre las tablas, SchemaGen intenta crear una relación única que incluye todas las claves implicadas entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="7102a-150">Where more than relationship exists between tables,SchemaGen tries to create a single relationship that includes all the keys involved between the two tables.</span></span> <span data-ttu-id="7102a-151">Esta limitación podría dar lugar a un error [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7102a-151">This limitation might be the cause of a [!INCLUDE[tsql](../../../includes/tsql-md.md)] error.</span></span>  
  
-   <span data-ttu-id="7102a-152">Al realizar cargas masivas de datos XML en una base de datos, debe haber al menos un atributo o elemento secundario en el esquema de asignación que esté asignado a una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7102a-152">When you are bulk loading XML data into a database, there must be at least one attribute or child element in the mapping schema that is mapped to a database column.</span></span>  
  
-   <span data-ttu-id="7102a-153">Si está insertando valores de fecha mediante la carga masiva XML, estos valores deben especificarse con el formato (-)CCYY-MM-DD((+-)TZ).</span><span class="sxs-lookup"><span data-stu-id="7102a-153">If you are inserting date values by using XML Bulk Load, the values must be specified in the (-)CCYY-MM-DD((+-)TZ) format.</span></span> <span data-ttu-id="7102a-154">Se trata del formato XSD estándar para la fecha.</span><span class="sxs-lookup"><span data-stu-id="7102a-154">This is the standard XSD format for the date.</span></span>  
  
-   <span data-ttu-id="7102a-155">Algunas marcas de propiedad no son compatibles con otras.</span><span class="sxs-lookup"><span data-stu-id="7102a-155">Some property flags are not compatible with other property flags.</span></span> <span data-ttu-id="7102a-156">Por ejemplo, la carga masiva no admite `Ignoreduplicatekeys=true` junto con `Keepidentity=false`.</span><span class="sxs-lookup"><span data-stu-id="7102a-156">For example, bulk load does not support `Ignoreduplicatekeys=true` together with `Keepidentity=false`.</span></span> <span data-ttu-id="7102a-157">Cuando `Keepidentity=false`, la carga masiva espera que el servidor genere los valores clave.</span><span class="sxs-lookup"><span data-stu-id="7102a-157">When `Keepidentity=false`, bulk load expects the server to generate the key values.</span></span> <span data-ttu-id="7102a-158">Las tablas deberían tener una limitación de `IDENTITY` en la clave.</span><span class="sxs-lookup"><span data-stu-id="7102a-158">Tables should have an `IDENTITY` constraint on the key.</span></span> <span data-ttu-id="7102a-159">El servidor no generará claves duplicadas, lo que significa que no es necesario que `Ignoreduplicatekeys` se establezca en `true`.</span><span class="sxs-lookup"><span data-stu-id="7102a-159">The server will not generate duplicate keys, which means there is no need for `Ignoreduplicatekeys` to be set to `true`.</span></span> <span data-ttu-id="7102a-160">`Ignoreduplicatekeys` debe establecerse en `true` solo cuando se cargan valores de clave principales de los datos entrantes en una tabla que tiene filas y existe la posibilidad de un conflicto de los valores de clave principales.</span><span class="sxs-lookup"><span data-stu-id="7102a-160">`Ignoreduplicatekeys` should be set to `true` only when uploading primary key values from the incoming data into a table that has rows and there is a potential for conflict of primary key values.</span></span>  
  
  
