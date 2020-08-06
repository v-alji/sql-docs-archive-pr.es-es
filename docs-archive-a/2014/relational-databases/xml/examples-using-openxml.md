---
title: 'Ejemplos: Uso de OPENXML | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ColPattern [XML in SQL Server]
- XML [SQL Server], mapping data
- OPENXML statement, about OPENXML statement
- overflow in XML document [SQL Server]
- mapping XML data [SQL Server]
- combining attribute-centric and element centric mapping
- unconsumed data
- attribute-centric mapping
- column patterns [XML in SQL Server]
- XML [SQL Server], overflow handling
- row patterns [XML in SQL Server]
- rowpattern [XML in SQL Server]
- flags parameter
- element-centric mapping [SQL Server]
- edge tables
ms.assetid: 689297f3-adb0-4d8d-bf62-cfda26210164
author: rothja
ms.author: jroth
ms.openlocfilehash: 09fc6ad073b12df2f9fbd8ebc6a59149f6154ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752010"
---
# <a name="examples-using-openxml"></a><span data-ttu-id="85770-102">Ejemplos: Uso de OPENXML</span><span class="sxs-lookup"><span data-stu-id="85770-102">Examples: Using OPENXML</span></span>
  <span data-ttu-id="85770-103">Los ejemplos de este tema muestran cómo se utiliza OPENXML para crear una vista de conjunto de filas de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="85770-103">The examples in this topic show how OPENXML is used to create a rowset view of an XML document.</span></span> <span data-ttu-id="85770-104">Para obtener más información sobre la sintaxis de OPENXML, vea [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85770-104">For information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span> <span data-ttu-id="85770-105">Los ejemplos muestran todos los aspectos de OPENXML, pero no especifican metapropiedades en OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-105">The examples show all aspects of OPENXML, but do not specify metaproperties in OPENXML.</span></span> <span data-ttu-id="85770-106">Para obtener más información sobre cómo especificar metapropiedades en OPENXML, vea [Especificar metapropiedades en OPENXML](specify-metaproperties-in-openxml.md).</span><span class="sxs-lookup"><span data-stu-id="85770-106">For more information about how to specify metaproperties in OPENXML, see [Specify Metaproperties in OPENXML](specify-metaproperties-in-openxml.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="85770-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="85770-107">Examples</span></span>  
 <span data-ttu-id="85770-108">Al recuperar los datos, se utiliza *rowpattern* para identificar los nodos del documento XML que determinan las filas.</span><span class="sxs-lookup"><span data-stu-id="85770-108">In retrieving the data, *rowpattern* is used to identify the nodes in the XML document that determine the rows.</span></span> <span data-ttu-id="85770-109">Además, *rowpattern* se expresa en el lenguaje del patrón XPath que se utiliza en la implementación XPath de MSXML.</span><span class="sxs-lookup"><span data-stu-id="85770-109">Additionally, *rowpattern* is expressed in the XPath pattern language that is used in the MSXML XPath implementation.</span></span> <span data-ttu-id="85770-110">Por ejemplo, si el patrón termina en un elemento o atributo, se crea una fila para cada nodo de elemento o atributo que *rowpattern*seleccione.</span><span class="sxs-lookup"><span data-stu-id="85770-110">For example, if the pattern ends in an element or an attribute, a row is created for each element or attribute node that is selected by *rowpattern*.</span></span>  
  
 <span data-ttu-id="85770-111">El valor *flags* proporciona una asignación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="85770-111">The *flags* value provides default mapping.</span></span> <span data-ttu-id="85770-112">Si no se especifica *ColPattern* en *SchemaDeclaration*, se asume la asignación especificada en *flags* .</span><span class="sxs-lookup"><span data-stu-id="85770-112">If no *ColPattern* is specified in the *SchemaDeclaration*, the mapping specified in *flags* is assumed.</span></span> <span data-ttu-id="85770-113">El valor *flags* se omite si se especifica *ColPattern* en *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="85770-113">The *flags* value is ignored if *ColPattern* is specified in *SchemaDeclaration*.</span></span> <span data-ttu-id="85770-114">La especificación *ColPattern* determina la asignación (centrada en atributos o elementos) y también el comportamiento para manejar los datos de desbordamiento y los no usados.</span><span class="sxs-lookup"><span data-stu-id="85770-114">The specified *ColPattern* determines the mapping, attribute-centric or element-centric, and also the behavior in dealing with overflow and unconsumed data.</span></span>  
  
### <a name="a-executing-a-simple-select-statement-with-openxml"></a><span data-ttu-id="85770-115">A.</span><span class="sxs-lookup"><span data-stu-id="85770-115">A.</span></span> <span data-ttu-id="85770-116">Ejecutar una instrucción SELECT simple con OPENXML</span><span class="sxs-lookup"><span data-stu-id="85770-116">Executing a simple SELECT statement with OPENXML</span></span>  
 <span data-ttu-id="85770-117">El documento XML de este ejemplo se compone de los elementos <`Customer`>, <`Order`> y <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="85770-117">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="85770-118">La instrucción OPENXML recupera información del cliente del documento XML en un conjunto de filas de dos columnas ( **CustomerID** y **ContactName**).</span><span class="sxs-lookup"><span data-stu-id="85770-118">The OPENXML statement retrieves customer information in a two-column rowset, **CustomerID** and **ContactName**, from the XML document.</span></span>  
  
 <span data-ttu-id="85770-119">Primero, para obtener un identificador de documento se llama al procedimiento almacenado **sp_xml_preparedocument** .</span><span class="sxs-lookup"><span data-stu-id="85770-119">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="85770-120">Este identificador de documento se pasa a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-120">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="85770-121">La instrucción OPENXML muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-121">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="85770-122">*rowpattern* (/ROOT/Customer) identifica los nodos <`Customer`> que se van a procesar.</span><span class="sxs-lookup"><span data-stu-id="85770-122">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="85770-123">El valor del parámetro *flags* se establece en **1** e indica una asignación centrada en atributos.</span><span class="sxs-lookup"><span data-stu-id="85770-123">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="85770-124">Como resultado, los atributos XML se asignan a las columnas del conjunto de filas definido en *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="85770-124">As a result, the XML attributes map to the columns in the rowset defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="85770-125">En *SchemaDeclaration*, en la cláusula WITH, los valores *ColName* especificados coinciden con los nombres de atributo XML correspondientes.</span><span class="sxs-lookup"><span data-stu-id="85770-125">In *SchemaDeclaration*, in the WITH clause, the specified *ColName* values match the corresponding XML attribute names.</span></span> <span data-ttu-id="85770-126">Por lo tanto, el parámetro *ColPattern* no se especifica en *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="85770-126">Therefore, the *ColPattern* parameter is not specified in *SchemaDeclaration*.</span></span>  
  
 <span data-ttu-id="85770-127">A continuación, la instrucción SELECT recupera todas las columnas del conjunto de filas que proporciona OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-127">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @DocHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @DocHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@DocHandle, '/ROOT/Customer',1)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @DocHandle  
```  
  
 <span data-ttu-id="85770-128">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-128">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="85770-129">Si se ejecuta la misma instrucción SELECT con el parámetro *flags* establecido en **2** para indicar una asignación centrada en elementos, puesto que los elementos <`Customer`> no disponen de subelementos, los valores de **CustomerID** y **ContactName** de ambos clientes se devuelven como NULL.</span><span class="sxs-lookup"><span data-stu-id="85770-129">Because the <`Customer`> elements do not have any subelements, if the same SELECT statement is executed with *flags* set to **2** to indicate element-centric mapping, the values of **CustomerID** and **ContactName** for both the customers are returned as NULL.</span></span>  
  
 <span data-ttu-id="85770-130">@xmlDocument también puede ser de tipo **xml** o de tipo **(n)varchar(max)**.</span><span class="sxs-lookup"><span data-stu-id="85770-130">The @xmlDocument can also be of **xml** type or of **(n)varchar(max)** type.</span></span>  
  
 <span data-ttu-id="85770-131">En el documento XML, si <`CustomerID`> y <`ContactName`> son subelementos, la asignación centrada en elementos recupera los valores.</span><span class="sxs-lookup"><span data-stu-id="85770-131">If <`CustomerID`> and <`ContactName`> in the XML document are subelements, the element-centric mapping retrieves the values.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer>  
   <CustomerID>VINET</CustomerID>  
   <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer>     
   <CustomerID>LILAS</CustomerID>  
   <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT    *  
FROM      OPENXML (@XmlDocumentHandle, '/ROOT/Customer',2)  
           WITH (CustomerID  varchar(10),  
                 ContactName varchar(20))  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="85770-132">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-132">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="85770-133">Observe que el identificador de documento devuelto por **sp_xml_preparedocument** es válido mientras dura el proceso por lotes y no la sesión.</span><span class="sxs-lookup"><span data-stu-id="85770-133">Note that the document handle returned by **sp_xml_preparedocument** is valid for the duration of the batch and not the session.</span></span>  
  
### <a name="b-specifying-colpattern-for-mapping-between-rowset-columns-and-the-xml-attributes-and-elements"></a><span data-ttu-id="85770-134">B.</span><span class="sxs-lookup"><span data-stu-id="85770-134">B.</span></span> <span data-ttu-id="85770-135">Especificar ColPattern para la asignación entre columnas del conjunto de filas y los atributos y elementos XML</span><span class="sxs-lookup"><span data-stu-id="85770-135">Specifying ColPattern for mapping between rowset columns and the XML attributes and elements</span></span>  
 <span data-ttu-id="85770-136">Este ejemplo muestra cómo se especifica el patrón XPath en el parámetro opcional *ColPattern* para proporcionar una asignación entre columnas del conjunto de filas y los atributos y elementos XML.</span><span class="sxs-lookup"><span data-stu-id="85770-136">This example shows how the XPath pattern is specified in the optional *ColPattern* parameter to provide mapping between rowset columns and the XML attributes and elements.</span></span>  
  
 <span data-ttu-id="85770-137">El documento XML de este ejemplo se compone de los elementos <`Customer`>, <`Order`> y <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="85770-137">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="85770-138">La instrucción OPENXML recupera información del cliente y del pedido del documento XML en forma de conjunto de filas (**CustomerID**, **OrderDate**, **ProdID**y **Qty**).</span><span class="sxs-lookup"><span data-stu-id="85770-138">The OPENXML statement retrieves customer and order information as a rowset (**CustomerID**, **OrderDate**, **ProdID**, and **Qty**) from the XML document.</span></span>  
  
 <span data-ttu-id="85770-139">Primero, para obtener un identificador de documento se llama al procedimiento almacenado **sp_xml_preparedocument** .</span><span class="sxs-lookup"><span data-stu-id="85770-139">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="85770-140">Este identificador de documento se pasa a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-140">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="85770-141">La instrucción OPENXML muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-141">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="85770-142">*rowpattern* (/ROOT/Customer/Order/OrderDetail) identifica los nodos <`OrderDetail`> que se van a procesar.</span><span class="sxs-lookup"><span data-stu-id="85770-142">*rowpattern* (/ROOT/Customer/Order/OrderDetail) identifies the <`OrderDetail`> nodes to process.</span></span>  
  
 <span data-ttu-id="85770-143">A modo de ilustración, el valor del parámetro *flags* se establece en **2** e indica una asignación centrada en elementos.</span><span class="sxs-lookup"><span data-stu-id="85770-143">For illustration, the *flags* parameter value is set to **2** and indicates element-centric mapping.</span></span> <span data-ttu-id="85770-144">Sin embargo, la asignación especificada en *ColPattern* sobrescribe esta asignación.</span><span class="sxs-lookup"><span data-stu-id="85770-144">However, the mapping specified in *ColPattern* overwrites this mapping.</span></span> <span data-ttu-id="85770-145">Es decir, el patrón XPath especificado en *ColPattern* asigna a atributos las columnas del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="85770-145">That is, the XPath pattern specified in *ColPattern* maps the columns in the rowset to attributes.</span></span> <span data-ttu-id="85770-146">El resultado es una asignación centrada en atributos.</span><span class="sxs-lookup"><span data-stu-id="85770-146">This results in attribute-centric mapping.</span></span>  
  
 <span data-ttu-id="85770-147">En *SchemaDeclaration*, en la cláusula WITH, también se especifica *ColPattern* con los parámetros *ColName* y *ColType* .</span><span class="sxs-lookup"><span data-stu-id="85770-147">In *SchemaDeclaration*, in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="85770-148">El parámetro opcional *ColPattern* es el patrón XPath especificado e indica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-148">The optional *ColPattern* is the XPath pattern specified and indicates the following:</span></span>  
  
-   <span data-ttu-id="85770-149">Las columnas **OrderID**, **CustomerID** y **OrderDate** del conjunto de filas se asignan a los atributos del elemento primario de los nodos identificados por *rowpattern*, y *rowpattern* identifica los nodos <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="85770-149">The **OrderID**, **CustomerID**, and **OrderDate** columns in the rowset map to the attributes of the parent of the nodes identified by *rowpattern*, and *rowpattern* identifies the <`OrderDetail`> nodes.</span></span> <span data-ttu-id="85770-150">Por lo tanto, las columnas **CustomerID** y **OrderDate** se asignan a los atributos **CustomerID** y **OrderDate** del elemento <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="85770-150">Therefore, the **CustomerID** and **OrderDate** columns map to **CustomerID** and **OrderDate** attributes of the <`Order`> element.</span></span>  
  
-   <span data-ttu-id="85770-151">Las columnas **ProdID** y **Qty** del conjunto de filas se asignan a los atributos **ProductID** y **Quantity** de los nodos identificados en *rowpattern*.</span><span class="sxs-lookup"><span data-stu-id="85770-151">The **ProdID** and **Qty** columns in the rowset map to the **ProductID** and **Quantity** attributes of the nodes identified in *rowpattern*.</span></span>  
  
 <span data-ttu-id="85770-152">A continuación, la instrucción SELECT recupera todas las columnas del conjunto de filas que proporciona OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-152">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
           OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
           OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT stmt using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@XmlDocumentHandle, '/ROOT/Customer/Order/OrderDetail',2)  
WITH (OrderID     int         '../@OrderID',  
      CustomerID  varchar(10) '../@CustomerID',  
      OrderDate   datetime    '../@OrderDate',  
      ProdID      int         '@ProductID',  
      Qty         int         '@Quantity')  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="85770-153">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-153">This is the result:</span></span>  
  
```  
OrderID CustomerID        OrderDate          ProdID    Qty  
-------------------------------------------------------------  
10248    VINET     1996-07-04 00:00:00.000     11       12  
10248    VINET     1996-07-04 00:00:00.000     42       10  
10283    LILAS     1996-08-16 00:00:00.000     72        3  
```  
  
 <span data-ttu-id="85770-154">El patrón XPath especificado como *ColPattern* también puede especificarse para asignar los elementos XML a las columnas del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="85770-154">The XPath pattern specified as *ColPattern* can also be specified to map the XML elements to the rowset columns.</span></span> <span data-ttu-id="85770-155">El resultado es una asignación centrada en elementos.</span><span class="sxs-lookup"><span data-stu-id="85770-155">This results in element-centric mapping.</span></span> <span data-ttu-id="85770-156">En el siguiente ejemplo, en el documento XML, <`CustomerID`> y <`OrderDate`> son subelementos del elemento <`Orders`>.</span><span class="sxs-lookup"><span data-stu-id="85770-156">In the following example, the XML document <`CustomerID`> and <`OrderDate`> are subelements of the <`Orders`> element.</span></span> <span data-ttu-id="85770-157">Dado que *ColPattern* sobrescribe la asignación especificada en el parámetro *flags*, este no se especifica en OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-157">Because *ColPattern* overwrites the mapping specified in the *flags* parameter, the *flags* parameter is not specified in OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order EmployeeID="5" >  
      <OrderID>10248</OrderID>  
      <CustomerID>VINET</CustomerID>  
      <OrderDate>1996-07-04T00:00:00</OrderDate>  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order  EmployeeID="3" >  
      <OrderID>10283</OrderID>  
      <CustomerID>LILAS</CustomerID>  
      <OrderDate>1996-08-16T00:00:00</OrderDate>  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail')  
WITH (CustomerID  varchar(10)   '../CustomerID',  
      OrderDate   datetime      '../OrderDate',  
      ProdID      int           '@ProductID',  
      Qty         int           '@Quantity')  
EXEC sp_xml_removedocument @docHandle  
```  
  
### <a name="c-combining-attribute-centric-and-element-centric-mapping"></a><span data-ttu-id="85770-158">C.</span><span class="sxs-lookup"><span data-stu-id="85770-158">C.</span></span> <span data-ttu-id="85770-159">Combinar asignaciones centradas en elementos y en atributos</span><span class="sxs-lookup"><span data-stu-id="85770-159">Combining attribute-centric and element-centric mapping</span></span>  
 <span data-ttu-id="85770-160">En este ejemplo, el parámetro *flags* se establece en **3** , lo que indica que se aplicarán tanto la asignación centrada en elementos como en atributos.</span><span class="sxs-lookup"><span data-stu-id="85770-160">In this example, the *flags* parameter is set to **3** and indicates that both attribute-centric and element-centric mapping will be applied.</span></span> <span data-ttu-id="85770-161">En este caso, primero se aplica la asignación centrada en atributos y, a continuación, la centrada en elementos, en todas las columnas donde aún no se ha hecho.</span><span class="sxs-lookup"><span data-stu-id="85770-161">In this case, the attribute-centric mapping is applied first, and then element-centric mapping is applied for all the columns not yet dealt with.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument =N'<ROOT>  
<Customer CustomerID="VINET"  >  
     <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" >   
     <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer',3)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="85770-162">El resultado es el siguiente</span><span class="sxs-lookup"><span data-stu-id="85770-162">This is the result</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="85770-163">La asignación centrada en atributos se aplica para **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="85770-163">The attribute-centric mapping is applied for **CustomerID**.</span></span> <span data-ttu-id="85770-164">No existe ningún atributo **ContactName** en el elemento <`Customer`>.</span><span class="sxs-lookup"><span data-stu-id="85770-164">There is no **ContactName** attribute in the <`Customer`> element.</span></span> <span data-ttu-id="85770-165">Por lo tanto, se aplica la asignación centrada en elementos.</span><span class="sxs-lookup"><span data-stu-id="85770-165">Therefore, element-centric mapping is applied.</span></span>  
  
### <a name="d-specifying-the-text-xpath-function-as-colpattern"></a><span data-ttu-id="85770-166">D.</span><span class="sxs-lookup"><span data-stu-id="85770-166">D.</span></span> <span data-ttu-id="85770-167">Especificar la función text() de XPath como ColPattern</span><span class="sxs-lookup"><span data-stu-id="85770-167">Specifying the text() XPath function as ColPattern</span></span>  
 <span data-ttu-id="85770-168">El documento XML de este ejemplo se compone de los elementos <`Customer`> y <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="85770-168">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="85770-169">La instrucción OPENXML recupera un conjunto de filas que está compuesto por el atributo **oid** del elemento <`Order`>, el identificador del elemento primario del nodo identificado por *rowpattern* y la cadena del valor de hoja del contenido de elemento.</span><span class="sxs-lookup"><span data-stu-id="85770-169">The OPENXML statement retrieves a rowset that is made up of the **oid** attribute from the <`Order`> element, the ID of the parent of the node identified by *rowpattern*, and the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="85770-170">Primero, para obtener un identificador de documento se llama al procedimiento almacenado **sp_xml_preparedocument** .</span><span class="sxs-lookup"><span data-stu-id="85770-170">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="85770-171">Este identificador de documento se pasa a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-171">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="85770-172">La instrucción OPENXML muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-172">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="85770-173">*rowpattern* (/root/Customer/Order) identifica los nodos <`Order`> que se van a procesar.</span><span class="sxs-lookup"><span data-stu-id="85770-173">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="85770-174">El valor del parámetro *flags* se establece en **1** e indica una asignación centrada en atributos.</span><span class="sxs-lookup"><span data-stu-id="85770-174">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="85770-175">Como resultado, los atributos XML se asignan a columnas del conjunto de filas definido en *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="85770-175">As a result, the XML attributes map to the rowset columns defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="85770-176">En *SchemaDeclaration* , en la cláusula WITH, los nombres de columna del conjunto de filas **oid** y **amount** coinciden con los nombres de atributo XML correspondientes.</span><span class="sxs-lookup"><span data-stu-id="85770-176">In *SchemaDeclaration* in the WITH clause, the **oid** and **amount** rowset column names match the corresponding XML attribute names.</span></span> <span data-ttu-id="85770-177">Por lo tanto, no se especifica el parámetro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="85770-177">Therefore, the *ColPattern* parameter is not specified.</span></span> <span data-ttu-id="85770-178">En la columna **comment** del conjunto de filas, la función **text()** de XPath se especifica como *ColPattern*.</span><span class="sxs-lookup"><span data-stu-id="85770-178">For the **comment** column in the rowset, the XPath function, **text()**, is specified as *ColPattern*.</span></span> <span data-ttu-id="85770-179">Esto sobrescribe la asignación centrada en atributos especificada en *flags*y la columna contiene la cadena del valor de hoja del contenido del elemento.</span><span class="sxs-lookup"><span data-stu-id="85770-179">This overwrites the attribute-centric mapping specified in *flags*, and the column contains the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="85770-180">A continuación, la instrucción SELECT recupera todas las columnas del conjunto de filas que proporciona OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-180">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied  
      </Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
            <Urgency>Important</Urgency>  
            Happy Customer.  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH (oid     char(5),   
           amount  float,   
           comment ntext 'text()')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="85770-181">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-181">This is the result:</span></span>  
  
```  
oid   amount        comment  
----- -----------   -----------------------------  
O1    3.5           NULL  
O2    13.4          Customer was very satisfied  
O3    100.0         Happy Customer.  
O4    10000.0       NULL  
```  
  
### <a name="e-specifying-tablename-in-the-with-clause"></a><span data-ttu-id="85770-182">E.</span><span class="sxs-lookup"><span data-stu-id="85770-182">E.</span></span> <span data-ttu-id="85770-183">Especificar TableName en la cláusula WITH</span><span class="sxs-lookup"><span data-stu-id="85770-183">Specifying TableName in the WITH clause</span></span>  
 <span data-ttu-id="85770-184">Este ejemplo especifica *TableName* en la cláusula WITH, en lugar de *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="85770-184">This example specifies *TableName* in the WITH clause instead of *SchemaDeclaration*.</span></span> <span data-ttu-id="85770-185">Resulta útil si dispone de una tabla con la estructura deseada y no se requieren patrones de columnas (parámetro *ColPattern* ).</span><span class="sxs-lookup"><span data-stu-id="85770-185">This is useful if you have a table that has the structure you want and no column patterns, *ColPattern* parameter, are required.</span></span>  
  
 <span data-ttu-id="85770-186">El documento XML de este ejemplo se compone de los elementos <`Customer`> y <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="85770-186">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="85770-187">La instrucción OPENXML recupera información del pedido en un conjunto de filas de tres columnas (**oid**, **date**y **amount**) del documento XML.</span><span class="sxs-lookup"><span data-stu-id="85770-187">The OPENXML statement retrieves order information in a three-column rowset (**oid**, **date**, and **amount**) from the XML document.</span></span>  
  
 <span data-ttu-id="85770-188">Primero, para obtener un identificador de documento se llama al procedimiento almacenado **sp_xml_preparedocument** .</span><span class="sxs-lookup"><span data-stu-id="85770-188">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="85770-189">Este identificador de documento se pasa a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-189">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="85770-190">La instrucción OPENXML muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-190">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="85770-191">*rowpattern* (/root/Customer/Order) identifica los nodos <`Order`> que se van a procesar.</span><span class="sxs-lookup"><span data-stu-id="85770-191">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="85770-192">No existe ninguna *SchemaDeclaration* en la cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="85770-192">There is no *SchemaDeclaration* in the WITH clause.</span></span> <span data-ttu-id="85770-193">En vez de eso, se especifica un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="85770-193">Instead, a table name is specified.</span></span> <span data-ttu-id="85770-194">Por lo tanto, el esquema de tabla se utiliza como esquema del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="85770-194">Therefore, the table schema is used as the rowset schema.</span></span>  
  
-   <span data-ttu-id="85770-195">El valor del parámetro *flags* se establece en **1** e indica una asignación centrada en atributos.</span><span class="sxs-lookup"><span data-stu-id="85770-195">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="85770-196">Por lo tanto, los atributos de los elementos, identificados por *rowpattern*, se asignan a las columnas del conjunto de filas con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="85770-196">Therefore, attributes of the elements, identified by *rowpattern*, map to the rowset columns with the same name.</span></span>  
  
 <span data-ttu-id="85770-197">A continuación, la instrucción SELECT recupera todas las columnas del conjunto de filas que proporciona OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-197">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
-- Create a test table. This table schema is used by OPENXML as the  
-- rowset schema.  
CREATE TABLE T1(oid char(5), date datetime, amount float)  
GO  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
-- Sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH T1  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="85770-198">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-198">This is the result:</span></span>  
  
```  
oid   date                        amount  
----- --------------------------- ----------  
O1    1996-01-20 00:00:00.000     3.5  
O2    1997-04-30 00:00:00.000     13.4  
O3    1999-07-14 00:00:00.000     100.0  
O4    1996-01-20 00:00:00.000     10000.0  
```  
  
### <a name="f-obtaining-the-result-in-an-edge-table-format"></a><span data-ttu-id="85770-199">F.</span><span class="sxs-lookup"><span data-stu-id="85770-199">F.</span></span> <span data-ttu-id="85770-200">Obtener el resultado en formato de tabla irregular</span><span class="sxs-lookup"><span data-stu-id="85770-200">Obtaining the result in an edge table format</span></span>  
 <span data-ttu-id="85770-201">En este ejemplo, no se especifica la cláusula WITH en la instrucción OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-201">In this example, the WITH clause is not specified in the OPENXML statement.</span></span> <span data-ttu-id="85770-202">Como resultado, el conjunto de filas que genera OPENXML tiene un formato de tabla irregular.</span><span class="sxs-lookup"><span data-stu-id="85770-202">As a result, the rowset generated by OPENXML has an edge table format.</span></span> <span data-ttu-id="85770-203">La instrucción SELECT devuelve todas las columnas de la tabla irregular.</span><span class="sxs-lookup"><span data-stu-id="85770-203">The SELECT statement returns all the columns in the edge table.</span></span>  
  
 <span data-ttu-id="85770-204">El documento XML del ejemplo se compone de los elementos <`Customer`>, <`Order`> y <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="85770-204">The sample XML document in the example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span>  
  
 <span data-ttu-id="85770-205">Primero, para obtener un identificador de documento se llama al procedimiento almacenado **sp_xml_preparedocument** .</span><span class="sxs-lookup"><span data-stu-id="85770-205">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="85770-206">Este identificador de documento se pasa a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-206">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="85770-207">La instrucción OPENXML muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-207">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="85770-208">*rowpattern* (/ROOT/Customer) identifica los nodos <`Customer`> que se van a procesar.</span><span class="sxs-lookup"><span data-stu-id="85770-208">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="85770-209">No se proporciona la cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="85770-209">The WITH clause is not provided.</span></span> <span data-ttu-id="85770-210">Por esta razón, OPENXML devuelve el conjunto de filas en un formato de tabla irregular.</span><span class="sxs-lookup"><span data-stu-id="85770-210">Therefore, OPENXML returns the rowset in an edge table format.</span></span>  
  
 <span data-ttu-id="85770-211">A continuación, la instrucción SELECT recupera todas las columnas de la tabla irregular.</span><span class="sxs-lookup"><span data-stu-id="85770-211">The SELECT statement then retrieves all the columns in the edge table.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
SET @xmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail OrderID="10248" ProductID="11" Quantity="12"/>  
      <OrderDetail OrderID="10248" ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail OrderID="10283" ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer')  
  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="85770-212">El resultado se devuelve como una tabla irregular.</span><span class="sxs-lookup"><span data-stu-id="85770-212">The result is returned as an edge table.</span></span> <span data-ttu-id="85770-213">Puede escribir consultas con la tabla irregular para obtener información.</span><span class="sxs-lookup"><span data-stu-id="85770-213">You can write queries against the edge table to obtain information.</span></span> <span data-ttu-id="85770-214">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="85770-214">For example:</span></span>  
  
-   <span data-ttu-id="85770-215">La siguiente consulta devuelve el número de nodos **Customer** del documento.</span><span class="sxs-lookup"><span data-stu-id="85770-215">The following query returns the number of **Customer** nodes in the document.</span></span> <span data-ttu-id="85770-216">Dado que no se especifica la cláusula WITH, OPENXML devuelve una tabla irregular.</span><span class="sxs-lookup"><span data-stu-id="85770-216">Because the WITH clause is not specified, OPENXML returns an edge table.</span></span> <span data-ttu-id="85770-217">La instrucción SELECT consulta la tabla irregular.</span><span class="sxs-lookup"><span data-stu-id="85770-217">The SELECT statement queries the edge table.</span></span>  
  
    ```  
    SELECT count(*)  
    FROM OPENXML(@docHandle, '/')  
    WHERE localname = 'Customer'  
    ```  
  
-   <span data-ttu-id="85770-218">La siguiente consulta devuelve los nombres locales de los nodos XML del tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="85770-218">The following query returns the local names of XML nodes of element type.</span></span>  
  
    ```  
    SELECT distinct localname   
    FROM OPENXML(@docHandle, '/')   
    WHERE nodetype = 1   
    ORDER BY localname  
    ```  
  
### <a name="g-specifying-rowpattern-ending-with-an-attribute"></a><span data-ttu-id="85770-219">G.</span><span class="sxs-lookup"><span data-stu-id="85770-219">G.</span></span> <span data-ttu-id="85770-220">Especificar rowpattern con final en atributo</span><span class="sxs-lookup"><span data-stu-id="85770-220">Specifying rowpattern ending with an attribute</span></span>  
 <span data-ttu-id="85770-221">El documento XML de este ejemplo se compone de los elementos <`Customer`>, <`Order`> y <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="85770-221">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="85770-222">La instrucción OPENXML recupera información detallada del pedido en un conjunto de filas de tres columnas (**ProductID**, **Quantity**y **OrderID**) del documento XML.</span><span class="sxs-lookup"><span data-stu-id="85770-222">The OPENXML statement retrieves information about the order details in a three-column rowset (**ProductID**, **Quantity**, and **OrderID**) from the XML document.</span></span>  
  
 <span data-ttu-id="85770-223">Primero, para obtener un identificador de documento se llama a **sp_xml_preparedocument** .</span><span class="sxs-lookup"><span data-stu-id="85770-223">First, the **sp_xml_preparedocument** is called to obtain a document handle.</span></span> <span data-ttu-id="85770-224">Este identificador de documento se pasa a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-224">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="85770-225">La instrucción OPENXML muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-225">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="85770-226">*rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) termina en un atributo XML: **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="85770-226">*rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) ends with an XML attribute, **ProductID**.</span></span> <span data-ttu-id="85770-227">En el conjunto de filas resultante, se crea una fila por cada nodo de atributo seleccionado en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="85770-227">In the resulting rowset, a row is created for each attribute node selected in the XML document.</span></span>  
  
-   <span data-ttu-id="85770-228">En este ejemplo, no se especifica el parámetro *flags* .</span><span class="sxs-lookup"><span data-stu-id="85770-228">In this example, the *flags* parameter is not specified.</span></span> <span data-ttu-id="85770-229">En su lugar, las asignaciones se especifican con el parámetro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="85770-229">Instead, the mappings are specified by the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="85770-230">En *SchemaDeclaration* , en la cláusula WITH, también se especifica *ColPattern* con los parámetros *ColName* y *ColType* .</span><span class="sxs-lookup"><span data-stu-id="85770-230">In *SchemaDeclaration* in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="85770-231">El parámetro opcional *ColPattern* es el patrón XPath especificado para indicar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-231">The optional *ColPattern* is the XPath pattern specified to indicate the following:</span></span>  
  
-   <span data-ttu-id="85770-232">El patrón XPath ( **.** ) especificado como *ColPattern* en la columna **ProdID** del conjunto de filas identifica el nodo de contexto (nodo actual).</span><span class="sxs-lookup"><span data-stu-id="85770-232">The XPath pattern (**.**) specified as *ColPattern* for the **ProdID** column in the rowset identifies the context node, current node.</span></span> <span data-ttu-id="85770-233">En cuanto al valor *rowpattern* especificado, es el atributo **ProductID** del elemento <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="85770-233">As per the *rowpattern* specified, it is the **ProductID** attribute of the <`OrderDetail`> element.</span></span>  
  
-   <span data-ttu-id="85770-234">*ColPattern*, **../\@Quantity**, especificado para la columna **Qty** del conjunto de filas, identifica el atributo **Quantity** del nodo principal <`OrderDetail`> del nodo de contexto \<ProductID>.</span><span class="sxs-lookup"><span data-stu-id="85770-234">The *ColPattern*, **../\@Quantity**, specified for the **Qty** column in the rowset identifies the **Quantity** attribute of the parent, <`OrderDetail`>, node of the context node, \<ProductID>.</span></span>  
  
-   <span data-ttu-id="85770-235">Del mismo modo, *ColPattern*, **../../\@OrderID**, especificado para la columna **OID** del conjunto de filas, identifica el atributo **OrderID** del elemento primario (`Order`) del nodo principal del nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="85770-235">Similarly, the *ColPattern*, **../../\@OrderID**, specified for the **OID** column in the rowset identifies the **OrderID** attribute of the parent, <`Order`>, of the parent node of the context node.</span></span> <span data-ttu-id="85770-236">El nodo principal es <`OrderDetail`> y el nodo de contexto es <`ProductID`>.</span><span class="sxs-lookup"><span data-stu-id="85770-236">The parent node is <`OrderDetail`>, and the context node is <`ProductID`>.</span></span>  
  
 <span data-ttu-id="85770-237">A continuación, la instrucción SELECT recupera todas las columnas del conjunto de filas que proporciona OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-237">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--Sample XML document  
SET @xmlDocument =N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail/@ProductID')  
       WITH ( ProdID  int '.',  
              Qty     int '../@Quantity',  
              OID     int '../../@OrderID')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="85770-238">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-238">This is the result:</span></span>  
  
```  
ProdID      Qty         OID  
----------- ----------- -------   
11          12          10248  
42          10          10248  
72          3           10283  
```  
  
### <a name="h-specifying-an-xml-document-that-has-multiple-text-nodes"></a><span data-ttu-id="85770-239">H.</span><span class="sxs-lookup"><span data-stu-id="85770-239">H.</span></span> <span data-ttu-id="85770-240">Especificar un documento XML con varios nodos de texto</span><span class="sxs-lookup"><span data-stu-id="85770-240">Specifying an XML document that has multiple text nodes</span></span>  
 <span data-ttu-id="85770-241">Si dispone de varios nodos de texto en un documento XML, una instrucción SELECT con *ColPattern*, **text()** , solamente devuelve el primer nodo de texto en lugar de todos.</span><span class="sxs-lookup"><span data-stu-id="85770-241">If you have multiple text nodes in an XML document, a SELECT statement with a *ColPattern*, **text()**, returns only the first text node, instead of all of them.</span></span> <span data-ttu-id="85770-242">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="85770-242">For example:</span></span>  
  
```  
DECLARE @h int  
EXEC sp_xml_preparedocument @h OUTPUT,  
         N'<root xmlns:a="urn:1">  
           <a:Elem abar="asdf">  
             T<a>a</a>U  
           </a:Elem>  
         </root>',  
         '<ns xmlns:b="urn:1" />'  
  
SELECT * FROM openxml(@h, '/root/b:Elem')  
      WITH (Col1 varchar(20) 'text()')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="85770-243">La instrucción SELECT devuelve **T** como resultado (y no **TaU**).</span><span class="sxs-lookup"><span data-stu-id="85770-243">The SELECT statement returns **T** as the result, and not **TaU**.</span></span>  
  
### <a name="i-specifying-the-xml-data-type-in-the-with-clause"></a><span data-ttu-id="85770-244">I.</span><span class="sxs-lookup"><span data-stu-id="85770-244">I.</span></span> <span data-ttu-id="85770-245">Especificar el tipo de datos xml en la cláusula WITH</span><span class="sxs-lookup"><span data-stu-id="85770-245">Specifying the xml data type in the WITH clause</span></span>  
 <span data-ttu-id="85770-246">En la cláusula WITH, un patrón de columna que se asigna a la columna de tipo de datos **xml** , tenga o no tenga tipo, debe devolver una secuencia vacía o una secuencia de elementos, instrucciones de procesamiento, nodos de texto y comentarios.</span><span class="sxs-lookup"><span data-stu-id="85770-246">In the WITH clause, a column pattern that is mapped to the **xml** data type column, whether typed or untyped, must return either an empty sequence or a sequence of elements, processing instructions, text nodes, and comments.</span></span> <span data-ttu-id="85770-247">Los datos se convierten a un tipo de datos **xml** .</span><span class="sxs-lookup"><span data-stu-id="85770-247">The data is cast to an **xml** data type.</span></span>  
  
 <span data-ttu-id="85770-248">En el siguiente ejemplo, la declaración de esquema de tabla en la cláusula WITH incluye columnas de tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="85770-248">In the following example, the table schema declaration in the WITH clause includes **xml** type columns.</span></span>  
  
```  
DECLARE @h int  
DECLARE @x xml  
set @x = '<Root>  
  <row id="1"><lname>Duffy</lname>  
   <Address>  
            <Street>111 Maple</Street>  
            <City>Seattle</City>  
   </Address>  
  </row>  
  <row id="2"><lname>Wang</lname>  
   <Address>  
            <Street>222 Pine</Street>  
            <City>Bothell</City>  
   </Address>  
  </row>  
</Root>'  
  
EXEC sp_xml_preparedocument @h output, @x  
SELECT *  
FROM   OPENXML (@h, '/Root/row', 10)  
      WITH (id int '@id',  
  
            lname    varchar(30),  
            xmlname  xml 'lname',  
            OverFlow xml '@mp:xmltext')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="85770-249">Específicamente, se está pasando una variable de tipo **xml** (\@x) a la función **sp_xml_preparedocument()** .</span><span class="sxs-lookup"><span data-stu-id="85770-249">Specifically, you are passing an **xml** type variable (\@x) to the **sp_xml_preparedocument()** function.</span></span>  
  
 <span data-ttu-id="85770-250">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-250">This is the result:</span></span>  
  
```  
id  lname   xmlname                   OverFlow  
--- ------- ------------------------------ -------------------------------  
1   Duffy   <lname>Duffy</lname>  <row><Address>  
                                   <Street>111 Maple</Street>  
                                   <City>Seattle</City>  
                                  </Address></row>  
2   Wang    <lname>Wang</lname>   <row><Address>  
                                    <Street>222 Pine</Street>  
                                    <City>Bothell</City>  
                                   </Address></row>  
```  
  
 <span data-ttu-id="85770-251">Tenga en cuenta las siguientes observaciones en cuanto al resultado:</span><span class="sxs-lookup"><span data-stu-id="85770-251">Note the following from the result:</span></span>  
  
-   <span data-ttu-id="85770-252">En el caso de la columna **lname** de tipo **varchar(30)** , su valor se recupera del elemento <`lname`> correspondiente.</span><span class="sxs-lookup"><span data-stu-id="85770-252">For the **lname** column of **varchar(30)** type, its value is retrieved from the corresponding <`lname`> element.</span></span>  
  
-   <span data-ttu-id="85770-253">En el caso de la columna **xmlname** de tipo **xml** , se devuelve el elemento del mismo nombre como su valor.</span><span class="sxs-lookup"><span data-stu-id="85770-253">For the **xmlname** column of **xml** type, the same name element is returned as its value.</span></span>  
  
-   <span data-ttu-id="85770-254">La marca se establece en 10.</span><span class="sxs-lookup"><span data-stu-id="85770-254">The flag is set to 10.</span></span> <span data-ttu-id="85770-255">El 10 significa 2 + 8, donde 2 indica asignación centrada en elementos y 8 indica que solo se pueden agregar datos XML no usados a la columna OverFlow definida en la cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="85770-255">The 10 means 2 + 8, where 2 indicates element-centric mapping and 8 indicates that only unconsumed XML data should be added to the OverFlow column defined in the WITH clause.</span></span> <span data-ttu-id="85770-256">Si la marca se establece en 2, el documento XML completo se copia en la columna OverFlow especificada en la cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="85770-256">If you set the flag to 2, the whole XML document is copied to the OverFlow column that is specified in the WITH clause.</span></span>  
  
-   <span data-ttu-id="85770-257">Si la columna con la cláusula WITH es una columna XML con tipo y la instancia XML no se ajusta al esquema, se devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="85770-257">In case the column in the WITH clause is a typed XML column and the XML instance does not confirm to the schema, an error is returned.</span></span>  
  
### <a name="j-retrieving-individual-values-from-multivalued-attributes"></a><span data-ttu-id="85770-258">J.</span><span class="sxs-lookup"><span data-stu-id="85770-258">J.</span></span> <span data-ttu-id="85770-259">Recuperar valores individuales de atributos con varios valores</span><span class="sxs-lookup"><span data-stu-id="85770-259">Retrieving individual values from multivalued attributes</span></span>  
 <span data-ttu-id="85770-260">Un documento XML puede tener atributos que tienen varios valores.</span><span class="sxs-lookup"><span data-stu-id="85770-260">An XML document can have attributes that are multivalued.</span></span> <span data-ttu-id="85770-261">Por ejemplo, el atributo **IDREFS** puede tener varios valores.</span><span class="sxs-lookup"><span data-stu-id="85770-261">For example, the **IDREFS** attribute can be multivalued.</span></span> <span data-ttu-id="85770-262">En un documento XML, los valores de atributo con varios valores se especifican como una cadena con los valores separados por un espacio.</span><span class="sxs-lookup"><span data-stu-id="85770-262">In an XML document, the multivalued attribute values are specified as a string, with the values separated by a space.</span></span> <span data-ttu-id="85770-263">En el siguiente documento XML, el atributo **attends** del elemento \<Student> y el atributo **attendedBy** de \<Class> tienen varios valores.</span><span class="sxs-lookup"><span data-stu-id="85770-263">In the following XML document, the **attends** attribute of the \<Student> element and the **attendedBy** attribute of \<Class> are multivalued.</span></span> <span data-ttu-id="85770-264">Recuperar valores individuales de un atributo XML con varios valores y almacenar cada valor en una fila separada en la base de datos requiere un trabajo adicional.</span><span class="sxs-lookup"><span data-stu-id="85770-264">Retrieving individual values from a multivalued XML attribute and storing each value in a separate row in the database requires additional work.</span></span> <span data-ttu-id="85770-265">Este ejemplo muestra el proceso.</span><span class="sxs-lookup"><span data-stu-id="85770-265">This example shows the process.</span></span>  
  
 <span data-ttu-id="85770-266">Este documento XML de ejemplo consta de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="85770-266">This sample XML document is made up of the following elements:</span></span>  
  
-   \<Student>  
  
     <span data-ttu-id="85770-267">Los atributos **id** (identificador del estudiante), **name**y **attends** .</span><span class="sxs-lookup"><span data-stu-id="85770-267">The **id** (student ID), **name**, and **attends** attributes.</span></span> <span data-ttu-id="85770-268">El atributo **attends** es un atributo con varios valores.</span><span class="sxs-lookup"><span data-stu-id="85770-268">The **attends** attribute is a multivalued attribute.</span></span>  
  
-   \<Class>  
  
     <span data-ttu-id="85770-269">Los atributos **id** (identificador de la clase), **name**y **attendedBy** .</span><span class="sxs-lookup"><span data-stu-id="85770-269">The **id** (class ID), **name**, and **attendedBy** attributes.</span></span> <span data-ttu-id="85770-270">El atributo **attendedBy** es un atributo con varios valores.</span><span class="sxs-lookup"><span data-stu-id="85770-270">The **attendedBy** attribute is a multivalued attribute.</span></span>  
  
 <span data-ttu-id="85770-271">El atributo **attends** de \<Student> y el atributo **attendedBy** de \<Class> representan una relación **m:n** entre las tablas Student y Class.</span><span class="sxs-lookup"><span data-stu-id="85770-271">The **attends** attribute in \<Student> and the **attendedBy** attribute in \<Class> represent a **m:n** relationship between the Student and Class tables.</span></span> <span data-ttu-id="85770-272">Un estudiante puede tener muchas clases y una clase puede tener varios estudiantes.</span><span class="sxs-lookup"><span data-stu-id="85770-272">A student can take many classes and a class can have many students.</span></span>  
  
 <span data-ttu-id="85770-273">Suponga que desea dividir este documento y guardarlo en la base de datos de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="85770-273">Assume that you want to shred this document and save it in the database as shown in the following:</span></span>  
  
-   <span data-ttu-id="85770-274">Guarde los datos de \<Student> en la tabla Students.</span><span class="sxs-lookup"><span data-stu-id="85770-274">Save the \<Student> data in the Students table.</span></span>  
  
-   <span data-ttu-id="85770-275">Guarde los datos de \<Class> en la tabla Courses.</span><span class="sxs-lookup"><span data-stu-id="85770-275">Save the \<Class> data in the Courses table.</span></span>  
  
-   <span data-ttu-id="85770-276">Guarde los datos de la relación **m:n** (entre Student y Class) en la tabla CourseAttendence.</span><span class="sxs-lookup"><span data-stu-id="85770-276">Save the **m:n** relationship data, between Student and Class, in the CourseAttendence table.</span></span> <span data-ttu-id="85770-277">Para extraer los valores se requiere trabajo adicional.</span><span class="sxs-lookup"><span data-stu-id="85770-277">Additional work is required to extract the values.</span></span> <span data-ttu-id="85770-278">Para recuperar esta información y almacenarla en la tabla, utilice estos procedimientos almacenados:</span><span class="sxs-lookup"><span data-stu-id="85770-278">To retrieve this information and store it in the table, use these stored procedures:</span></span>  
  
    -   <span data-ttu-id="85770-279">**Insert_Idrefs_Values**</span><span class="sxs-lookup"><span data-stu-id="85770-279">**Insert_Idrefs_Values**</span></span>  
  
         <span data-ttu-id="85770-280">Inserta los valores de Id. de curso e Id. de estudiante en la tabla CourseAttendence.</span><span class="sxs-lookup"><span data-stu-id="85770-280">Inserts the values of course ID and student ID in the CourseAttendence table.</span></span>  
  
    -   <span data-ttu-id="85770-281">**Extract_idrefs_values**</span><span class="sxs-lookup"><span data-stu-id="85770-281">**Extract_idrefs_values**</span></span>  
  
         <span data-ttu-id="85770-282">Extrae los id. de alumnos individuales de cada elemento \<Course>.</span><span class="sxs-lookup"><span data-stu-id="85770-282">Extracts the individual student IDs from each \<Course> element.</span></span> <span data-ttu-id="85770-283">Para recuperar estos valores se utiliza una tabla irregular.</span><span class="sxs-lookup"><span data-stu-id="85770-283">An edge table is used to retrieve these values.</span></span>  
  
 <span data-ttu-id="85770-284">He aquí los pasos:</span><span class="sxs-lookup"><span data-stu-id="85770-284">Here are the steps:</span></span>  
  
```  
-- Create these tables:  
DROP TABLE CourseAttendance  
DROP TABLE Students  
DROP TABLE Courses  
GO  
CREATE TABLE Students(  
                id   varchar(5) primary key,  
                name varchar(30)  
                )  
GO  
CREATE TABLE Courses(  
               id       varchar(5) primary key,  
               name     varchar(30),  
               taughtBy varchar(5)  
)  
GO  
CREATE TABLE CourseAttendance(  
             id         varchar(5) references Courses(id),  
             attendedBy varchar(5) references Students(id),  
             constraint CourseAttendance_PK primary key (id, attendedBy)  
)  
go  
-- Create these stored procedures:  
DROP PROCEDURE f_idrefs  
GO  
CREATE PROCEDURE f_idrefs  
    @t      varchar(500),  
    @idtab  varchar(50),  
    @id     varchar(5)  
AS  
DECLARE @sp int  
DECLARE @att varchar(5)  
SET @sp = 0  
WHILE (LEN(@t) > 0)  
BEGIN   
    SET @sp = CHARINDEX(' ', @t+ ' ')  
    SET @att = LEFT(@t, @sp-1)  
    EXEC('INSERT INTO '+@idtab+' VALUES ('''+@id+''', '''+@att+''')')  
    SET @t = SUBSTRING(@t+ ' ', @sp+1, LEN(@t)+1-@sp)  
END  
Go  
  
DROP PROCEDURE fill_idrefs  
GO  
CREATE PROCEDURE fill_idrefs   
    @xmldoc     int,  
    @xpath      varchar(100),  
    @from       varchar(50),  
    @to         varchar(50),  
    @idtable    varchar(100)  
AS  
DECLARE @t varchar(500)  
DECLARE @id varchar(5)  
  
/* Temporary edge table */  
SELECT *   
INTO #TempEdge   
FROM OPENXML(@xmldoc, @xpath)  
  
DECLARE fillidrefs_cursor CURSOR FOR  
    SELECT CAST(iv.text AS nvarchar(200)) AS id,  
           CAST(av.text AS nvarchar(4000)) AS refs  
    FROM   #TempEdge c, #TempEdge i,  
           #TempEdge iv, #TempEdge a, #TempEdge av  
    WHERE  c.id = i.parentid  
    AND    UPPER(i.localname) = UPPER(@from)  
    AND    i.id = iv.parentid  
    AND    c.id = a.parentid  
    AND    UPPER(a.localname) = UPPER(@to)  
    AND    a.id = av.parentid  
  
OPEN fillidrefs_cursor  
FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
WHILE (@@FETCH_STATUS <> -1)  
BEGIN  
    IF (@@FETCH_STATUS <> -2)  
    BEGIN  
        execute f_idrefs @t, @idtable, @id  
    END  
    FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
END  
CLOSE fillidrefs_cursor  
DEALLOCATE fillidrefs_cursor  
Go  
-- This is the sample document that is shredded and the data is stored in the preceding tables.  
DECLARE @h int  
EXECUTE sp_xml_preparedocument @h OUTPUT, N'<Data>  
  <Student id = "s1" name = "Student1"  attends = "c1 c3 c6"  />  
  <Student id = "s2" name = "Student2"  attends = "c2 c4" />  
  <Student id = "s3" name = "Student3"  attends = "c2 c4 c6" />  
  <Student id = "s4" name = "Student4"  attends = "c1 c3 c5" />  
  <Student id = "s5" name = "Student5"  attends = "c1 c3 c5 c6" />  
  <Student id = "s6" name = "Student6" />  
  
  <Class id = "c1" name = "Intro to Programming"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c2" name = "Databases"   
         attendedBy = "s2 s3" />  
  <Class id = "c3" name = "Operating Systems"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c4" name = "Networks" attendedBy = "s2 s3" />  
  <Class id = "c5" name = "Algorithms and Graphs"   
         attendedBy =  "s4 s5"/>  
  <Class id = "c6" name = "Power and Pragmatism"   
         attendedBy = "s1 s3 s5" />  
</Data>'  
  
INSERT INTO Students SELECT * FROM OPENXML(@h, '//Student') WITH Students  
  
INSERT INTO Courses SELECT * FROM OPENXML(@h, '//Class') WITH Courses  
/* Using the edge table */  
EXECUTE fill_idrefs @h, '//Class', 'id', 'attendedby', 'CourseAttendance'  
  
SELECT * FROM Students  
SELECT * FROM Courses  
SELECT * FROM CourseAttendance  
  
EXECUTE sp_xml_removedocument @h  
```  
  
### <a name="k-retrieving-binary-from-base64-encoded-data-in-xml"></a><span data-ttu-id="85770-285">K.</span><span class="sxs-lookup"><span data-stu-id="85770-285">K.</span></span> <span data-ttu-id="85770-286">Recuperar datos binarios a partir de datos con codificación base64 en XML</span><span class="sxs-lookup"><span data-stu-id="85770-286">Retrieving binary from base64 encoded data in XML</span></span>  
 <span data-ttu-id="85770-287">Con frecuencia, se incluyen datos binarios en XML mediante codificación base64.</span><span class="sxs-lookup"><span data-stu-id="85770-287">Binary data is frequently included in XML using base64 encoding.</span></span> <span data-ttu-id="85770-288">Cuando este XML se divide mediante OPENXML, os datos se reciben con codificación base64.</span><span class="sxs-lookup"><span data-stu-id="85770-288">When you shred this XML by using OPENXML, you receive the base64 encoded data.</span></span> <span data-ttu-id="85770-289">En este ejemplo se muestra cómo se puede convertir en binarios los datos con codificación base64.</span><span class="sxs-lookup"><span data-stu-id="85770-289">This example shows how you can convert the base64 encoded data back to binary.</span></span>  
  
-   <span data-ttu-id="85770-290">Cree una tabla con datos binarios de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="85770-290">Create a table with sample binary data.</span></span>  
  
-   <span data-ttu-id="85770-291">Use una consulta FOR XML y la opción BINARY BASE64 para generar XML que tenga los datos binarios codificados como base64.</span><span class="sxs-lookup"><span data-stu-id="85770-291">Use a FOR XML query and the BINARY BASE64 option to construct XML that has the binary data encoded as base64.</span></span>  
  
-   <span data-ttu-id="85770-292">Divida el XML mediante OPENXML.</span><span class="sxs-lookup"><span data-stu-id="85770-292">Shred the XML by using OPENXML.</span></span> <span data-ttu-id="85770-293">Los datos devueltos por OPENXML tendrán codificación base64.</span><span class="sxs-lookup"><span data-stu-id="85770-293">The data returned by OPENXML will be base64 encoded data.</span></span> <span data-ttu-id="85770-294">A continuación, llame a la función .value para convertirlos de nuevo en binarios.</span><span class="sxs-lookup"><span data-stu-id="85770-294">Next, call the .value function to convert it back to binary.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 varbinary(100))  
go  
-- Insert sample binary data  
INSERT T VALUES(1, 0x1234567890)   
go  
 -- Create test XML document that has base64 encoded binary data (use FOR XML query and specify BINARY BASE64 option)  
SELECT * FROM T  
FOR XML AUTO, BINARY BASE64  
go  
-- result  
-- <T Col1="1" Col2="EjRWeJA="/>  
  
-- Now shredd the sample XML using OPENXML.   
-- Call the .value function to convert   
-- the base64 encoded data returned by OPENXML to binary.  
DECLARE @h int ;  
EXEC sp_xml_preparedocument @h OUTPUT, '<T Col1="1" Col2="EjRWeJA="/>' ;  
SELECT Col1,   
CAST('<binary>' + Col2 + '</binary>' AS XML).value('.', 'varbinary(max)') AS BinaryCol   
FROM openxml(@h, '/T')   
WITH (Col1 integer, Col2 varchar(max)) ;  
EXEC sp_xml_removedocument @h ;  
GO  
```  
  
 Éste es el resultado. <span data-ttu-id="85770-296">Los datos binarios devueltos son los datos binarios originales de la tabla T.</span><span class="sxs-lookup"><span data-stu-id="85770-296">The binary data returned is the original binary data in table T.</span></span>  
  
```  
Col1        BinaryCol  
----------- ---------------------  
1           0x1234567890  
```  
  
## <a name="see-also"></a><span data-ttu-id="85770-297">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85770-297">See Also</span></span>  
 <span data-ttu-id="85770-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85770-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span></span>  
 <span data-ttu-id="85770-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85770-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span></span>  
 <span data-ttu-id="85770-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85770-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="85770-301">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85770-301">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
