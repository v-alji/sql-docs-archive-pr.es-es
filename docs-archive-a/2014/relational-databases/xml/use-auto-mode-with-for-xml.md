---
title: Usar el modo AUTO con FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, AUTO mode
- ELEMENTS option
- FOR XML AUTO mode
- AUTO FOR XML mode
ms.assetid: 7140d656-1d42-4f01-a533-5251429f4450
author: rothja
ms.author: jroth
ms.openlocfilehash: 232cc046667c6d31cb9657a7abdc862204507d23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673558"
---
# <a name="use-auto-mode-with-for-xml"></a><span data-ttu-id="8d659-102">Usar el modo AUTO con FOR XML</span><span class="sxs-lookup"><span data-stu-id="8d659-102">Use AUTO Mode with FOR XML</span></span>
  <span data-ttu-id="8d659-103">Tal como se describe en [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md), el modo AUTO devuelve los resultados de la consulta como elementos XML anidados.</span><span class="sxs-lookup"><span data-stu-id="8d659-103">As described in [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md), AUTO mode returns query results as nested XML elements.</span></span> <span data-ttu-id="8d659-104">Esto no ofrece un gran control sobre la forma del XML generado a partir del resultado de una consulta.</span><span class="sxs-lookup"><span data-stu-id="8d659-104">This does not provide much control over the shape of the XML generated from a query result.</span></span> <span data-ttu-id="8d659-105">Las consultas en modo AUTO son útiles si desea generar jerarquías sencillas.</span><span class="sxs-lookup"><span data-stu-id="8d659-105">The AUTO mode queries are useful if you want to generate simple hierarchies.</span></span> <span data-ttu-id="8d659-106">Pero [Usar el modo EXPLICIT con FOR XML](use-explicit-mode-with-for-xml.md) y [Usar el modo PATH con FOR XML](use-path-mode-with-for-xml.md) ofrecen mayor control y flexibilidad a la hora de decidir la forma del XML procedente del resultado de una consulta.</span><span class="sxs-lookup"><span data-stu-id="8d659-106">However, [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) and [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) provide more control and flexibility in deciding the shape of the XML from a query result.</span></span>  
  
 <span data-ttu-id="8d659-107">Cada tabla de la cláusula FROM, de la que al menos se presenta una columna en la cláusula SELECT, se representa como un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8d659-107">Each table in the FROM clause, from which at least one column is listed in the SELECT clause, is represented as an XML element.</span></span> <span data-ttu-id="8d659-108">Las columnas que se incluyen en la cláusula SELECT se asignan a atributos o subelementos, si se especifica la opción ELEMENTS en la cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="8d659-108">The columns listed in the SELECT clause are mapped to attributes or subelements, if the optional ELEMENTS option is specified in the FOR XML clause.</span></span>  
  
 <span data-ttu-id="8d659-109">La jerarquía XML, anidamiento de los elementos, del XML resultante está basada en el orden de las tablas identificadas por las columnas especificadas en la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="8d659-109">The XML hierarchy, nesting of the elements, in the resulting XML is based on the order of tables identified by the columns specified in the SELECT clause.</span></span> <span data-ttu-id="8d659-110">Por tanto, el orden en que se especifican los nombres de columna en la cláusula SELECT es importante.</span><span class="sxs-lookup"><span data-stu-id="8d659-110">Therefore, the order in which column names are specified in the SELECT clause is significant.</span></span> <span data-ttu-id="8d659-111">La primera, la tabla situada más a la izquierda que se identifica, constituye el elemento superior del documento XML resultante.</span><span class="sxs-lookup"><span data-stu-id="8d659-111">The first, leftmost table that is identified forms the top element in the resulting XML document.</span></span> <span data-ttu-id="8d659-112">La segunda tabla situada más a la izquierda, identificada por las columnas de la instrucción SELECT, constituye un subelemento del elemento superior, etc.</span><span class="sxs-lookup"><span data-stu-id="8d659-112">The second leftmost table, identified by columns in the SELECT statement, forms a subelement within the top element, and so on.</span></span>  
  
 <span data-ttu-id="8d659-113">Si un nombre de columna que aparece en la cláusula SELECT procede de una tabla ya identificada por una columna especificada anteriormente en la cláusula SELECT, la columna se agrega como atributo del elemento ya creado, en lugar de abrir un nuevo nivel de jerarquía.</span><span class="sxs-lookup"><span data-stu-id="8d659-113">If a column name listed in the SELECT clause is from a table that is already identified by a previously specified column in the SELECT clause, the column is added as an attribute of the element already created, instead of opening a new level of hierarchy.</span></span> <span data-ttu-id="8d659-114">Si se especifica la opción ELEMENTS, la columna se agrega como atributo.</span><span class="sxs-lookup"><span data-stu-id="8d659-114">If the ELEMENTS option is specified, the column is added as an attribute.</span></span>  
  
 <span data-ttu-id="8d659-115">Por ejemplo, ejecute esta consulta:</span><span class="sxs-lookup"><span data-stu-id="8d659-115">For example, execute this query:</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO  
```  
  
 <span data-ttu-id="8d659-116">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="8d659-116">This is the partial result:</span></span>  
  
```  
<Cust CustomerID="1" CustomerType="S">  
  <OrderHeader CustomerID="1" SalesOrderID="43860" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="44501" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="45283" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="46042" Status="5" />  
</Cust>  
...  
```  
  
 <span data-ttu-id="8d659-117">Observe lo siguiente en la cláusula SELECT:</span><span class="sxs-lookup"><span data-stu-id="8d659-117">Note the following in the SELECT clause:</span></span>  
  
-   <span data-ttu-id="8d659-118">CustomerID hace referencia a la tabla Cust.</span><span class="sxs-lookup"><span data-stu-id="8d659-118">The CustomerID references the Cust table.</span></span> <span data-ttu-id="8d659-119">Por tanto, se crea un elemento <`Cust`> y se agrega CustomerID como su atributo.</span><span class="sxs-lookup"><span data-stu-id="8d659-119">Therefore, a <`Cust`> element is created and CustomerID is added as its attribute.</span></span>  
  
-   <span data-ttu-id="8d659-120">A continuación, tres columnas, OrderHeader.CustomerID, OrderHeader.SaleOrderID y OrderHeader.Status, hacen referencia a la tabla OrderHeader.</span><span class="sxs-lookup"><span data-stu-id="8d659-120">Next, three columns, OrderHeader.CustomerID, OrderHeader.SaleOrderID, and OrderHeader.Status, reference the OrderHeader table.</span></span> <span data-ttu-id="8d659-121">Por tanto, se agrega un elemento <`OrderHeader`> como subelemento del elemento <`Cust`> y las tres columnas se agregan como atributos de <`OrderHeader`>.</span><span class="sxs-lookup"><span data-stu-id="8d659-121">Therefore, an <`OrderHeader`> element is added as a subelement of the <`Cust`> element and the three columns are added as attributes of <`OrderHeader`>.</span></span>  
  
-   <span data-ttu-id="8d659-122">A continuación, la columna Cust.CustomerType hace referencia de nuevo a la tabla Cust, que ya se había identificado con la columna Cust.CustomerID.</span><span class="sxs-lookup"><span data-stu-id="8d659-122">Next, the Cust.CustomerType column again references the Cust table that was already identified by the Cust.CustomerID column.</span></span> <span data-ttu-id="8d659-123">Por tanto, no se crea ningún elemento nuevo.</span><span class="sxs-lookup"><span data-stu-id="8d659-123">Therefore, no new element is created.</span></span> <span data-ttu-id="8d659-124">En su lugar, se agrega el atributo CustomerType al elemento <`Cust`> que se había creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8d659-124">Instead, the CustomerType attribute is added to the <`Cust`> element that was previously created.</span></span>  
  
-   <span data-ttu-id="8d659-125">La consulta especifica alias para los nombres de tabla.</span><span class="sxs-lookup"><span data-stu-id="8d659-125">The query specifies aliases for the table names.</span></span> <span data-ttu-id="8d659-126">Estos alias aparecen como nombres de los elementos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8d659-126">These aliases appear as corresponding element names.</span></span>  
  
-   <span data-ttu-id="8d659-127">ORDER BY es necesario para agrupar todos los elementos secundarios en un único elemento primario.</span><span class="sxs-lookup"><span data-stu-id="8d659-127">ORDER BY is required to group all children under one parent.</span></span>  
  
 <span data-ttu-id="8d659-128">Esta consulta es similar a la anterior, pero la cláusula SELECT especifica columnas en la tabla OrderHeader antes de las columnas de la tabla Cust.</span><span class="sxs-lookup"><span data-stu-id="8d659-128">This query is similar to the previous one, except the SELECT clause specifies columns in the OrderHeader table before the columns in the Cust table.</span></span> <span data-ttu-id="8d659-129">Por tanto, se crea primero el elemento <`OrderHeader`> y después se le agrega el elemento secundario <`Cust`>.</span><span class="sxs-lookup"><span data-stu-id="8d659-129">Therefore, first <`OrderHeader`> element is created and then the <`Cust`> child element is added to it.</span></span>  
  
```  
select OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerID,   
       Cust.CustomerType  
from Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
where Cust.CustomerID = OrderHeader.CustomerID  
for xml auto  
```  
  
 <span data-ttu-id="8d659-130">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="8d659-130">This is the partial result:</span></span>  
  
```  
<OrderHeader CustomerID="1" SalesOrderID="43860" Status="5">  
  <Cust CustomerID="1" CustomerType="S" />  
</OrderHeader>  
...  
```  
  
 <span data-ttu-id="8d659-131">Si se agrega la opción ELEMENTS a la cláusula FOR XML, se devuelve XML centrado en elementos.</span><span class="sxs-lookup"><span data-stu-id="8d659-131">If the ELEMENTS option is added in the FOR XML clause, element-centric XML is returned.</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="8d659-132">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="8d659-132">This is the partial result:</span></span>  
  
```  
<Cust>  
  <CustomerID>1</CustomerID>  
  <CustomerType>S</CustomerType>  
  <OrderHeader>  
    <CustomerID>1</CustomerID>  
    <SalesOrderID>43860</SalesOrderID>  
    <Status>5</Status>  
  </OrderHeader>  
   ...  
</Cust>  
...  
```  
  
 <span data-ttu-id="8d659-133">En esta consulta, los valores CustomerID de una fila se comparan con los de la siguiente al crear elementos \<Cust>, porque CustomerID es la clave principal de la tabla.</span><span class="sxs-lookup"><span data-stu-id="8d659-133">In this query, the CustomerID values are compared from one row to the next in creating the \<Cust> elements, because CustomerID is the primary key of the table.</span></span> <span data-ttu-id="8d659-134">Si no se identifica CustomerID como clave principal de la tabla, todos los valores de columna (CustomerID, CustomerType en esta consulta) de una fila se comparan con los de la siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d659-134">If CustomerID is not identified as the primary key for the table, all the column values (CustomerID, CustomerType in this query) are compared from one row to the next.</span></span> <span data-ttu-id="8d659-135">Si los valores difieren, se agrega un nuevo elemento \<Cust> al XML.</span><span class="sxs-lookup"><span data-stu-id="8d659-135">If the values differ, a new \<Cust> element is added to the XML.</span></span>  
  
 <span data-ttu-id="8d659-136">Cuando se comparan estos valores de columna, si algunas de las columnas que se comparan son de tipo **text**, **ntext**, **image**o **xml**, FOR XML asume que los valores son diferentes y no los compara, incluso si son los mismos.</span><span class="sxs-lookup"><span data-stu-id="8d659-136">When comparing these column values, if any of the columns to be compared are of type **text**, **ntext**, **image**, or **xml**, FOR XML assumes that the values are different and not compared, even though they may be the same.</span></span> <span data-ttu-id="8d659-137">Esto se debe a que no se admite la comparación de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="8d659-137">This is because comparing large objects is not supported.</span></span> <span data-ttu-id="8d659-138">Se agregan elementos al resultado para cada fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8d659-138">Elements are added to the result for each row selected.</span></span> <span data-ttu-id="8d659-139">Tenga en cuenta que se comparan las columnas de **(n)varchar(max)** y **varbinary(max)** .</span><span class="sxs-lookup"><span data-stu-id="8d659-139">Note that columns of **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="8d659-140">Si no se puede asociar una columna de la cláusula SELECT con ninguna de las tablas identificadas en la cláusula FROM, como en el caso de una columna de agregado o una columna calculada, se agrega la columna en el documento XML en el nivel de anidamiento más profundo cuando se encuentra en la lista.</span><span class="sxs-lookup"><span data-stu-id="8d659-140">When a column in the SELECT clause cannot be associated with any of the tables identified in the FROM clause, as in the case of an aggregate column or computed column, the column is added in the XML document in the deepest nesting level in place when it is encountered in the list.</span></span> <span data-ttu-id="8d659-141">Si esa columna aparece como la primera de la cláusula SELECT, la columna se agrega al elemento superior.</span><span class="sxs-lookup"><span data-stu-id="8d659-141">If such a column appears as the first column in the SELECT clause, the column is added to the top element.</span></span>  
  
 <span data-ttu-id="8d659-142">Si se especifica el carácter comodín \* (asterisco) en la cláusula SELECT, el anidamiento se determina del mismo modo que se ha explicado anteriormente, en función de las filas devueltas por el motor de consulta.</span><span class="sxs-lookup"><span data-stu-id="8d659-142">If the asterisk (\*) wildcard character is specified in the SELECT clause, the nesting is determined in the same way as previously described, based on the order that the rows are returned by the query engine.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d659-143">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8d659-143">In This Section</span></span>  
 <span data-ttu-id="8d659-144">Los temas siguientes proporcionan más información sobre el modo AUTO:</span><span class="sxs-lookup"><span data-stu-id="8d659-144">The following topics provide more information about AUTO mode:</span></span>  
  
-   [<span data-ttu-id="8d659-145">Usar la opción BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="8d659-145">Use the BINARY BASE64 Option</span></span>](use-the-binary-base64-option.md)  
  
-   [<span data-ttu-id="8d659-146">Heurística del modo AUTO para dar forma al XML devuelto</span><span class="sxs-lookup"><span data-stu-id="8d659-146">AUTO Mode Heuristics in Shaping Returned XML</span></span>](auto-mode-heuristics-in-shaping-returned-xml.md)  
  
-   [<span data-ttu-id="8d659-147">Ejemplos: Uso del modo AUTO</span><span class="sxs-lookup"><span data-stu-id="8d659-147">Examples: Using AUTO Mode</span></span>](examples-using-auto-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="8d659-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d659-148">See Also</span></span>  
 <span data-ttu-id="8d659-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8d659-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="8d659-150">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8d659-150">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
