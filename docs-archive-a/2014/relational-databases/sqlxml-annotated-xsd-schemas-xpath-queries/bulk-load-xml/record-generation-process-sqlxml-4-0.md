---
title: Proceso de generación de registros (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], record generation process
- node scopes [SQLXML]
- record subsets [SQLXML]
- scope [SQLXML]
- key ordering rules [SQLXML]
- record generation process for bulk loads [SQLXML]
- entering node scope [SQLXML]
- bulk load [SQLXML], record generation process
- leaving node scope [SQLXML]
- schema mapping [SQLXML]
ms.assetid: d8885bbe-6f15-4fb9-9684-ca7883cfe9ac
author: rothja
ms.author: jroth
ms.openlocfilehash: 5734776864aecbda7adaf0b9b16180b5ebd55ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744027"
---
# <a name="record-generation-process-sqlxml-40"></a><span data-ttu-id="d3786-102">Proceso de generación de registros (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d3786-102">Record Generation Process (SQLXML 4.0)</span></span>
  <span data-ttu-id="d3786-103">La carga masiva XML procesa los datos de entrada XML y prepara los registros para las tablas adecuadas de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3786-103">XML Bulk Load processes the XML input data and prepares records for the appropriate tables in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d3786-104">La lógica de la carga masiva XML determina cuándo generar un nuevo registro, qué elemento secundario o valores de atributo copiar en los campos del registro y cuándo está completo y preparado el registro para enviarse a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para su inserción.</span><span class="sxs-lookup"><span data-stu-id="d3786-104">The logic in XML Bulk Load determines when to generate a new record, what child element or attribute values to copy into the fields of the record, and when the record is complete and ready to be sent to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="d3786-105">La carga masiva XML no carga los datos de entrada XML completos en la memoria y no genera conjuntos de registros completos antes de enviar los datos a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3786-105">XML Bulk Load does not load the entire XML input data into memory, and does not produce complete record sets before sending data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d3786-106">Esto ocurre porque los datos de entrada XML pueden ser un documento de gran tamaño y cargar todo el documento en la memoria puede resultar costoso.</span><span class="sxs-lookup"><span data-stu-id="d3786-106">This is because XML input data can be a large document and loading the entire document in memory can be expensive.</span></span> <span data-ttu-id="d3786-107">En lugar de ello, la carga masiva XML hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3786-107">Instead, XML Bulk Load does the following:</span></span>  
  
1.  <span data-ttu-id="d3786-108">Analiza el esquema de asignación y prepara el plan de ejecución necesario.</span><span class="sxs-lookup"><span data-stu-id="d3786-108">Analyzes the mapping schema and prepares the necessary execution plan.</span></span>  
  
2.  <span data-ttu-id="d3786-109">Aplica el plan de ejecución a los datos del flujo de entrada.</span><span class="sxs-lookup"><span data-stu-id="d3786-109">Applies the execution plan to the data in the input stream.</span></span>  
  
 <span data-ttu-id="d3786-110">Este procesamiento secuencial hace que sea importante proporcionar los datos de entrada XML de un modo específico.</span><span class="sxs-lookup"><span data-stu-id="d3786-110">This sequential processing makes it important to provide the XML input data in a specific way.</span></span> <span data-ttu-id="d3786-111">Debe entender la forma en que la carga masiva XML analiza el esquema de asignación y la forma en que se produce el proceso de generación de registros.</span><span class="sxs-lookup"><span data-stu-id="d3786-111">You must understand how XML Bulk Load analyzes the mapping schema and how the record generation process occurs.</span></span> <span data-ttu-id="d3786-112">Sabiendo esto, podrá proporcionar un esquema de asignación para la carga masiva XML que genere los resultados que desee.</span><span class="sxs-lookup"><span data-stu-id="d3786-112">With this understanding, you can provide a mapping schema to XML Bulk Load that produces the results you want.</span></span>  
  
 <span data-ttu-id="d3786-113">La carga masiva XML administra anotaciones comunes del esquema de asignación, incluidas las asignaciones de columna y tabla (que se especifican de forma explícita mediante anotaciones o de forma implícita a través de la asignación predeterminada), así como relaciones de unión.</span><span class="sxs-lookup"><span data-stu-id="d3786-113">XML Bulk Load handles common mapping schema annotations, including column and table mappings (specified explicitly by using annotations or implicitly through the default mapping), and join relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3786-114">Se supone que está familiarizado con los esquemas de asignación XSD o XDR anotados.</span><span class="sxs-lookup"><span data-stu-id="d3786-114">It is assumed that you are familiar with annotated XSD or XDR mapping schemas.</span></span> <span data-ttu-id="d3786-115">Para obtener más información acerca de los esquemas, vea [Introducción a los esquemas XSD anotados &#40;sqlxml 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) o [esquemas XDR anotados &#40;en desuso en SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="d3786-115">For more information about schemas, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) or [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="d3786-116">Para entender el proceso de generación de registros es necesario comprender los conceptos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3786-116">Understanding record generation requires understanding the following concepts:</span></span>  
  
-   <span data-ttu-id="d3786-117">Ámbito de un nodo</span><span class="sxs-lookup"><span data-stu-id="d3786-117">Scope of a node</span></span>  
  
-   <span data-ttu-id="d3786-118">Regla de generación de registros</span><span class="sxs-lookup"><span data-stu-id="d3786-118">Record Generation Rule</span></span>  
  
-   <span data-ttu-id="d3786-119">Subconjunto de registros y la regla de orden de clave</span><span class="sxs-lookup"><span data-stu-id="d3786-119">Record subset and the Key Ordering Rule</span></span>  
  
-   <span data-ttu-id="d3786-120">Excepciones a la regla de generación de registros</span><span class="sxs-lookup"><span data-stu-id="d3786-120">Exceptions to the Record Generation Rule</span></span>  
  
## <a name="scope-of-a-node"></a><span data-ttu-id="d3786-121">Ámbito de un nodo</span><span class="sxs-lookup"><span data-stu-id="d3786-121">Scope of a Node</span></span>  
 <span data-ttu-id="d3786-122">Un nodo (un elemento o un atributo) de un documento XML entra *en el ámbito* cuando la carga masiva XML lo encuentra en el flujo de datos de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="d3786-122">A node (an element or an attribute) in an XML document enters *into scope* when XML Bulk Load encounters it in the XML input data stream.</span></span> <span data-ttu-id="d3786-123">En el caso de un nodo de elemento, la etiqueta inicial del elemento introduce el elemento en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="d3786-123">For an element node, the start tag of the element brings the element in scope.</span></span> <span data-ttu-id="d3786-124">En el caso de un nodo de atributo, el nombre de atributo introduce el atributo en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="d3786-124">For an attribute node, the attribute name brings the attribute in scope.</span></span>  
  
 <span data-ttu-id="d3786-125">Un nodo sale del ámbito cuando no hay más datos de él, ya sea en la etiqueta final (en el caso de un nodo de elemento) o al final de un valor de atributo (en el caso de un nodo de atributo).</span><span class="sxs-lookup"><span data-stu-id="d3786-125">A node leaves scope when there is no more data for it: either at the end tag (in the case of an element node) or at the end of an attribute value (in the case of an attribute node).</span></span>  
  
## <a name="record-generation-rule"></a><span data-ttu-id="d3786-126">Regla de generación de registros</span><span class="sxs-lookup"><span data-stu-id="d3786-126">Record Generation Rule</span></span>  
 <span data-ttu-id="d3786-127">Cuando un nodo (elemento o atributo) entra en el ámbito, significa que existe el potencial de generar un registro a partir de ese nodo.</span><span class="sxs-lookup"><span data-stu-id="d3786-127">When a node (element or attribute) enters into scope, there is a potential for generating a record from that node.</span></span> <span data-ttu-id="d3786-128">El período de vida del registro termina cuando el nodo asociado sale del ámbito.</span><span class="sxs-lookup"><span data-stu-id="d3786-128">The record lives as long as the associated node is in scope.</span></span> <span data-ttu-id="d3786-129">Cuando el nodo sale del ámbito, la carga masiva XML considera que el registro generado está completo (de datos) y lo envía a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para insertarlo.</span><span class="sxs-lookup"><span data-stu-id="d3786-129">When the node goes out of scope, XML Bulk Load considers the generated record complete (with data) and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="d3786-130">Por ejemplo, fíjese en el siguiente fragmento de esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="d3786-130">For example, consider the following XSD schema fragment:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Customers" >  
   <xsd:complexType>  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
     <xsd:attribute name="CompanyName" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="d3786-131">El esquema especifica un **\<Customer>** elemento con los atributos **CustomerID** y **CompanyName** .</span><span class="sxs-lookup"><span data-stu-id="d3786-131">The schema specifies a **\<Customer>** element with **CustomerID** and **CompanyName** attributes.</span></span> <span data-ttu-id="d3786-132">La `sql:relation` anotación asigna el **\<Customer>** elemento a la tabla customers.</span><span class="sxs-lookup"><span data-stu-id="d3786-132">The `sql:relation` annotation maps the **\<Customer>** element to the Customers table.</span></span>  
  
 <span data-ttu-id="d3786-133">Fíjese en este fragmento de un documento XML:</span><span class="sxs-lookup"><span data-stu-id="d3786-133">Consider this fragment of an XML document:</span></span>  
  
```  
<Customer CustomerID="1" CompanyName="xyz" />  
<Customer CustomerID="2" CompanyName="abc" />  
...  
```  
  
 <span data-ttu-id="d3786-134">Cuando la carga masiva XML se proporciona con el esquema descrito en los párrafos anteriores y con datos XML como entrada, procesa los nodos (elementos y atributos) en los datos de origen, tal y como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="d3786-134">When XML Bulk Load is provided with the schema described in the preceding paragraphs and XML data as input, it processes the nodes (elements and attributes) in the source data as follows:</span></span>  
  
-   <span data-ttu-id="d3786-135">La etiqueta inicial del primer **\<Customer>** elemento coloca ese elemento en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="d3786-135">The start tag of the first **\<Customer>** element brings that element in scope.</span></span> <span data-ttu-id="d3786-136">Este nodo se asigna a la tabla Customers.</span><span class="sxs-lookup"><span data-stu-id="d3786-136">This node maps to the Customers table.</span></span> <span data-ttu-id="d3786-137">Por lo tanto, la carga masiva XML genera un registro para la tabla Customers.</span><span class="sxs-lookup"><span data-stu-id="d3786-137">Therefore, XML Bulk Load generates a record for the Customers table.</span></span>  
  
-   <span data-ttu-id="d3786-138">En el esquema, todos los atributos del **\<Customer>** elemento se asignan a las columnas de la tabla customers.</span><span class="sxs-lookup"><span data-stu-id="d3786-138">In the schema, all attributes of the **\<Customer>** element map to columns of the Customers table.</span></span> <span data-ttu-id="d3786-139">A medida que estos atributos entran en el ámbito, la carga masiva XML copia sus valores en el registro del cliente ya generado por el ámbito primario.</span><span class="sxs-lookup"><span data-stu-id="d3786-139">As these attributes enter into scope, XML Bulk Load copies their values to the customer record that is already generated by the parent scope.</span></span>  
  
-   <span data-ttu-id="d3786-140">Cuando la carga masiva XML alcanza la etiqueta final del **\<Customer>** elemento, el elemento sale del ámbito.</span><span class="sxs-lookup"><span data-stu-id="d3786-140">When XML Bulk Load reaches the end tag for the **\<Customer>** element, the element goes out of scope.</span></span> <span data-ttu-id="d3786-141">Esto hace que la carga masiva XML considere el registro completo y lo envíe a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3786-141">This causes XML Bulk Load to consider the record complete and send it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d3786-142">La carga masiva XML sigue este proceso para cada **\<Customer>** elemento subsiguiente.</span><span class="sxs-lookup"><span data-stu-id="d3786-142">XML Bulk Load follows this process for each subsequent **\<Customer>** element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3786-143">En este modelo, dado que se inserta un registro cuando se alcanza la etiqueta final (o cuando el nodo sale del ámbito), deberá definir todos los datos asociados al registro dentro del ámbito del nodo.</span><span class="sxs-lookup"><span data-stu-id="d3786-143">In this model, because a record is inserted when the end tag is reached (or the node is out of scope), you must define all of the data that is associated with the record within the scope of the node.</span></span>  
  
## <a name="record-subset-and-the-key-ordering-rule"></a><span data-ttu-id="d3786-144">Subconjunto de registros y regla de ordenación de claves</span><span class="sxs-lookup"><span data-stu-id="d3786-144">Record Subset and the Key Ordering Rule</span></span>  
 <span data-ttu-id="d3786-145">Cuando se especifica un esquema de asignación que usa `<sql:relationship>`, el término subconjunto hace referencia al conjunto de registros generado en el lado externo de la relación.</span><span class="sxs-lookup"><span data-stu-id="d3786-145">When you specify a mapping schema that uses `<sql:relationship>`, the subset term refers to the set of records that is generated on the foreign side of the relationship.</span></span> <span data-ttu-id="d3786-146">En el ejemplo siguiente, los registros de CustOrder están en el lado externo, `<sql:relationship>`.</span><span class="sxs-lookup"><span data-stu-id="d3786-146">In the following example, the CustOrder records are on the foreign side, `<sql:relationship>`.</span></span>  
  
 <span data-ttu-id="d3786-147">Por ejemplo, supongamos que una base de datos contiene las tablas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3786-147">For example, suppose a database contains the following tables:</span></span>  
  
-   <span data-ttu-id="d3786-148">Cust (CustomerID, CompanyName, City)</span><span class="sxs-lookup"><span data-stu-id="d3786-148">Cust (CustomerID, CompanyName, City)</span></span>  
  
-   <span data-ttu-id="d3786-149">CustOrder (CustomerID, OrderID)</span><span class="sxs-lookup"><span data-stu-id="d3786-149">CustOrder (CustomerID, OrderID)</span></span>  
  
 <span data-ttu-id="d3786-150">La columna CustomerID de la tabla CustOrder es una clave externa que hace referencia a la clave principal CustomerID de la tabla Cust.</span><span class="sxs-lookup"><span data-stu-id="d3786-150">The CustomerID in the CustOrder table is a foreign key that refers to the CustomerID primary key in the Cust table.</span></span>  
  
 <span data-ttu-id="d3786-151">Ahora, fíjese en la vista XML tal y como se especifica en el siguiente esquema XSD anotado.</span><span class="sxs-lookup"><span data-stu-id="d3786-151">Now, consider the XML view as specified in the following annotated XSD schema.</span></span> <span data-ttu-id="d3786-152">Este esquema usa `<sql:relationship>` para especificar la relación entre las tablas Cust y CustOrder.</span><span class="sxs-lookup"><span data-stu-id="d3786-152">This schema uses `<sql:relationship>` to specify the relationship between the Cust and CustOrder tables.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="d3786-153">Los datos XML de ejemplo y los pasos para crear un ejemplo funcional se proporcionan a continuación.</span><span class="sxs-lookup"><span data-stu-id="d3786-153">The sample XML data and the steps to create a working sample are given below.</span></span>  
  
-   <span data-ttu-id="d3786-154">Cuando un **\<Customer>** nodo de elemento del archivo de datos XML entra en el ámbito, la carga masiva XML genera un registro para la tabla Cust.</span><span class="sxs-lookup"><span data-stu-id="d3786-154">When a **\<Customer>** element node in the XML data file enters into scope, XML Bulk Load generates a record for the Cust table.</span></span> <span data-ttu-id="d3786-155">A continuación, la carga masiva XML copia los valores de columna necesarios (CustomerID, CompanyName y City) de los **\<CustomerID>** **\<CompanyName>** elementos secundarios, y a **\<City>** medida que estos elementos entran en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="d3786-155">XML Bulk Load then copies the necessary column values (CustomerID, CompanyName, and City) from the **\<CustomerID>**, **\<CompanyName>**, and the **\<City>** child elements as these elements enter into scope.</span></span>  
  
-   <span data-ttu-id="d3786-156">Cuando un **\<Order>** nodo de elemento entra en el ámbito, la carga masiva XML genera un registro para la tabla CustOrder.</span><span class="sxs-lookup"><span data-stu-id="d3786-156">When an **\<Order>** element node enters into scope, XML Bulk Load generates a record for the CustOrder table.</span></span> <span data-ttu-id="d3786-157">La carga masiva XML copia el valor del atributo **OrderID** en este registro.</span><span class="sxs-lookup"><span data-stu-id="d3786-157">XML Bulk Load copies the value of the **OrderID** attribute to this record.</span></span> <span data-ttu-id="d3786-158">El valor necesario para la columna CustomerID se obtiene del **\<CustomerID>** elemento secundario del **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="d3786-158">The value required for the CustomerID column is obtained from the **\<CustomerID>** child element of the **\<Customer>** element.</span></span> <span data-ttu-id="d3786-159">La carga masiva XML usa la información que se especifica en `<sql:relationship>` para obtener el valor de clave externa CustomerID para este registro, a menos que se haya especificado el atributo **CustomerID** en el **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="d3786-159">XML Bulk Load uses the information that is specified in `<sql:relationship>` to obtain the CustomerID foreign key value for this record, unless the **CustomerID** attribute was specified in the **\<Order>** element.</span></span> <span data-ttu-id="d3786-160">La regla general es que si el elemento secundario especifica explícitamente un valor para el atributo de clave externa, la carga masiva XML usa ese valor y no obtiene el valor del elemento primario usando la etiqueta `<sql:relationship>` especificada.</span><span class="sxs-lookup"><span data-stu-id="d3786-160">The general rule is that if the child element explicitly specifies a value for the foreign key attribute, XML Bulk Load uses that value and does not obtain the value from the parent element by using the specified `<sql:relationship>`.</span></span> <span data-ttu-id="d3786-161">Como este **\<Order>** nodo de elemento sale del ámbito, la carga masiva XML envía el registro [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a y, a continuación, procesa todos los **\<Order>** nodos de elemento subsiguientes de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="d3786-161">As this **\<Order>** element node goes out of scope, XML Bulk Load sends the record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then processes all the subsequent **\<Order>** element nodes in the same manner.</span></span>  
  
-   <span data-ttu-id="d3786-162">Por último, el **\<Customer>** nodo de elemento sale del ámbito.</span><span class="sxs-lookup"><span data-stu-id="d3786-162">Finally, the **\<Customer>** element node goes out of scope.</span></span> <span data-ttu-id="d3786-163">En ese momento, la carga masiva XML envía el registro del cliente a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3786-163">At that time, XML Bulk Load sends the customer record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d3786-164">La carga masiva XML sigue este proceso para todos los clientes subsiguientes del flujo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="d3786-164">XML Bulk Load follows this process for all the subsequent customers in the XML data stream.</span></span>  
  
 <span data-ttu-id="d3786-165">A continuación se indican dos observaciones sobre el esquema de asignación:</span><span class="sxs-lookup"><span data-stu-id="d3786-165">Here are two observations about the mapping schema:</span></span>  
  
-   <span data-ttu-id="d3786-166">Cuando el esquema cumple la regla de "contención" (por ejemplo, todos los datos asociados al cliente y el pedido se define dentro del ámbito de los **\<Customer>** nodos de elemento y asociados **\<Order>** ), la carga masiva se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="d3786-166">When the schema satisfies the "containment" rule (for example, all data that is associated with the customer and the order is defined within the scope of the associated **\<Customer>** and **\<Order>** element nodes), the bulk load succeeds.</span></span>  
  
-   <span data-ttu-id="d3786-167">Al describir el **\<Customer>** elemento, sus elementos secundarios se especifican en el orden adecuado.</span><span class="sxs-lookup"><span data-stu-id="d3786-167">In describing the **\<Customer>** element, its child elements are specified in the appropriate order.</span></span> <span data-ttu-id="d3786-168">En este caso, el **\<CustomerID>** elemento secundario se especifica delante del **\<Order>** elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="d3786-168">In this case, the **\<CustomerID>** child element is specified before the **\<Order>** child element.</span></span> <span data-ttu-id="d3786-169">Esto significa que en el archivo de datos XML de entrada, el **\<CustomerID>** valor del elemento está disponible como valor de clave externa cuando el **\<Order>** elemento entra en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="d3786-169">This means that in the input XML data file, the **\<CustomerID>** element value is available as the foreign key value when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="d3786-170">Primero se especifican los atributos de clave; ésta es la "regla de orden de clave".</span><span class="sxs-lookup"><span data-stu-id="d3786-170">The key attributes are specified first; this is the "Key Ordering Rule."</span></span>  
  
     <span data-ttu-id="d3786-171">Si especifica el **\<CustomerID>** elemento secundario después del **\<Order>** elemento secundario, el valor no estará disponible cuando el **\<Order>** elemento entre en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="d3786-171">If you specify the **\<CustomerID>** child element after the **\<Order>** child element, the value is not available when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="d3786-172">Cuando **\</Order>** se lee la etiqueta de cierre, el registro de la tabla CustOrder se considera completo y se inserta en la tabla CustOrder con un valor null para la columna CustomerID, que no es el resultado deseado.</span><span class="sxs-lookup"><span data-stu-id="d3786-172">When the **\</Order>** end tag is then read, the record for CustOrder table is considered complete and is inserted in the CustOrder table with a NULL value for the CustomerID column, which is not the desired result.</span></span>  
  
#### <a name="to-create-a-working-sample"></a><span data-ttu-id="d3786-173">Para crear un ejemplo funcional</span><span class="sxs-lookup"><span data-stu-id="d3786-173">To create a working sample</span></span>  
  
1.  <span data-ttu-id="d3786-174">Guarde el esquema que se proporciona en este ejemplo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="d3786-174">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="d3786-175">Cree estas tablas:</span><span class="sxs-lookup"><span data-stu-id="d3786-175">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                 OrderID        int         PRIMARY KEY,  
                 CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID))  
    GO  
    ```  
  
3.  <span data-ttu-id="d3786-176">Guarde los siguientes datos de entrada XML de ejemplo como SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="d3786-176">Save the following sample XML input data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>   
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
        <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="d3786-177">Para ejecutar la carga masiva XML, guarde y ejecute el ejemplo de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) siguiente (BulkLoad.vbs):</span><span class="sxs-lookup"><span data-stu-id="d3786-177">To execute XML Bulk Load, save and execute the following [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example (BulkLoad.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
## <a name="exceptions-to-the-record-generation-rule"></a><span data-ttu-id="d3786-178">Excepciones a la regla de generación de registros</span><span class="sxs-lookup"><span data-stu-id="d3786-178">Exceptions to the Record Generation Rule</span></span>  
 <span data-ttu-id="d3786-179">La carga masiva XML no genera ningún registro para un nodo cuando entra en el ámbito si ese nodo es de tipo IDREF o IDREFS.</span><span class="sxs-lookup"><span data-stu-id="d3786-179">XML Bulk Load does not generate a record for a node when it enters into scope if that node is either an IDREF or IDREFS type.</span></span> <span data-ttu-id="d3786-180">Debe asegurarse de que se realice una descripción completa del registro en algún lugar del esquema.</span><span class="sxs-lookup"><span data-stu-id="d3786-180">You must make sure that a complete description of the record occurs at some place in the schema.</span></span> <span data-ttu-id="d3786-181">Las anotaciones `dt:type="nmtokens"` se omiten, al igual que el tipo IDREFS.</span><span class="sxs-lookup"><span data-stu-id="d3786-181">The `dt:type="nmtokens"` annotations are ignored just as the IDREFS type is ignored.</span></span>  
  
 <span data-ttu-id="d3786-182">Por ejemplo, considere el siguiente esquema XSD que describe **\<Customer>** **\<Order>** los elementos y.</span><span class="sxs-lookup"><span data-stu-id="d3786-182">For example, consider the following XSD schema that describes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="d3786-183">El **\<Customer>** elemento incluye un atributo **OrderList** del tipo IDREFS.</span><span class="sxs-lookup"><span data-stu-id="d3786-183">The **\<Customer>** element includes an **OrderList** attribute of the IDREFS type.</span></span> <span data-ttu-id="d3786-184">La etiqueta `<sql:relationship>` especifica la relación de uno a varios entre el cliente y lista de pedidos.</span><span class="sxs-lookup"><span data-stu-id="d3786-184">The `<sql:relationship>` tag specifies the one-to-many relationship between the customer and list of orders.</span></span>  
  
 <span data-ttu-id="d3786-185">Éste es el esquema:</span><span class="sxs-lookup"><span data-stu-id="d3786-185">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
                 parent="Cust"  
                 parent-key="CustomerID"  
                 child="CustOrder"  
                 child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="CompanyName" type="xsd:string" />  
    <xsd:attribute name="City" type="xsd:string" />  
    <xsd:attribute name="OrderList"   
                       type="xsd:IDREFS"   
                       sql:relation="CustOrder"   
                       sql:field="OrderID"  
                       sql:relationship="CustCustOrder" >  
    </xsd:attribute>  
  </xsd:complexType>  
 </xsd:element>  
  
  <xsd:element name="Order" sql:relation="CustOrder" >  
   <xsd:complexType>  
    <xsd:attribute name="OrderID" type="xsd:string" />  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="OrderDate" type="xsd:date" />  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="d3786-186">Dado que la carga masiva omite los nodos de tipo IDREFS, no hay ninguna generación de registros cuando el nodo de atributo **OrderList** entra en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="d3786-186">Because Bulk Load ignores the nodes of IDREFS type, there is no record generation when the **OrderList** attribute node enters into scope.</span></span> <span data-ttu-id="d3786-187">Por lo tanto, si desea que los registros de pedidos se agreguen a la tabla Orders, debe describir estos pedidos en alguna parte del esquema.</span><span class="sxs-lookup"><span data-stu-id="d3786-187">Therefore, if you want the order records added to the Orders table, you must describe those orders somewhere in the schema.</span></span> <span data-ttu-id="d3786-188">En este esquema, la especificación del **\<Order>** elemento garantiza que la carga masiva XML agrega los registros de pedido a la tabla Orders.</span><span class="sxs-lookup"><span data-stu-id="d3786-188">In this schema, specifying the **\<Order>** element ensures that XML Bulk Load adds the order records to the Orders table.</span></span> <span data-ttu-id="d3786-189">El **\<Order>** elemento describe todos los atributos necesarios para rellenar el registro de la tabla CustOrder.</span><span class="sxs-lookup"><span data-stu-id="d3786-189">The **\<Order>** element describes all the attributes that are required to fill the record for the CustOrder table.</span></span>  
  
 <span data-ttu-id="d3786-190">Debe asegurarse de que los valores **CustomerID** y **OrderID** en el **\<Customer>** elemento coinciden con los valores del **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="d3786-190">You must ensure that the **CustomerID** and **OrderID** values in the **\<Customer>** element match the values in the **\<Order>** element.</span></span> <span data-ttu-id="d3786-191">Mantener la integridad referencial es responsabilidad suya.</span><span class="sxs-lookup"><span data-stu-id="d3786-191">You are responsible for maintaining referential integrity.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="d3786-192">Para probar un ejemplo funcional</span><span class="sxs-lookup"><span data-stu-id="d3786-192">To test a working sample</span></span>  
  
1.  <span data-ttu-id="d3786-193">Cree estas tablas:</span><span class="sxs-lookup"><span data-stu-id="d3786-193">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int          PRIMARY KEY,  
                  CompanyName    varchar(20)  NOT NULL,  
                  City           varchar(20)  DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID        varchar(10) PRIMARY KEY,  
                  CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID),  
                  OrderDate      datetime DEFAULT '2000-01-01')  
    GO  
    ```  
  
2.  <span data-ttu-id="d3786-194">Guarde el esquema de asignación que se proporciona en este ejemplo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="d3786-194">Save the mapping schema provided in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="d3786-195">Guarde los siguientes datos XML de ejemplo como SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="d3786-195">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1111" CompanyName="Sean Chai" City="NY"  
                 OrderList="Ord1 Ord2" />  
      <Customers CustomerID="1112" CompanyName="Dont Know" City="LA"  
                 OrderList="Ord3 Ord4" />  
      <Order OrderID="Ord1" CustomerID="1111" OrderDate="1999-01-01" />  
      <Order OrderID="Ord2" CustomerID="1111" OrderDate="1999-02-01" />  
      <Order OrderID="Ord3" CustomerID="1112" OrderDate="1999-03-01" />  
      <Order OrderID="Ord4" CustomerID="1112" OrderDate="1999-04-01" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="d3786-196">Para ejecutar la carga masiva XML, guarde y ejecute este ejemplo de VBScript (SampleVB.vbs):</span><span class="sxs-lookup"><span data-stu-id="d3786-196">To execute XML Bulk Load, save and execute this VBScript example (SampleVB.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
