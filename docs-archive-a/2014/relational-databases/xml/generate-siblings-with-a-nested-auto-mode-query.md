---
title: Generar elementos del mismo nivel con una consulta de modo AUTO anidada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- queries [XML in SQL Server], nested AUTO mode
- nested AUTO mode query
ms.assetid: 748d9899-589d-4420-8048-1258e9e67c20
author: rothja
ms.author: jroth
ms.openlocfilehash: 20362942bdd0f7e7537433b664e5e63461ded499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751958"
---
# <a name="generate-siblings-with-a-nested-auto-mode-query"></a><span data-ttu-id="d8e4e-102">Generar elementos del mismo nivel con una consulta de modo AUTO anidada</span><span class="sxs-lookup"><span data-stu-id="d8e4e-102">Generate Siblings with a Nested AUTO Mode Query</span></span>
  <span data-ttu-id="d8e4e-103">En el siguiente ejemplo se muestra cómo generar elementos del mismo nivel utilizando una consulta en modo AUTO anidada.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-103">The following example shows how to generate siblings by using a nested AUTO mode query.</span></span> <span data-ttu-id="d8e4e-104">Solo hay otra forma de generar este XML, que es utilizar el modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-104">The only other way to generate such XML is to use the EXPLICIT mode.</span></span> <span data-ttu-id="d8e4e-105">Sin embargo, esto puede ser tedioso.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-105">However, this can be cumbersome.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8e4e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8e4e-106">Example</span></span>  
 <span data-ttu-id="d8e4e-107">Esta consulta genera XML que proporciona información de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-107">This query constructs XML that provides sales order information.</span></span> <span data-ttu-id="d8e4e-108">Incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8e4e-108">This includes the following:</span></span>  
  
-   <span data-ttu-id="d8e4e-109">Información de encabezado de pedidos de ventas, `SalesOrderID`, `SalesPersonID`y `OrderDate`.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-109">Sales order header information, `SalesOrderID`, `SalesPersonID`, and `OrderDate`.</span></span> [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="d8e4e-110">almacena esta información en la tabla `SalesOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="d8e4e-110">stores this information in the `SalesOrderHeader` table.</span></span>  
  
-   <span data-ttu-id="d8e4e-111">Información detallada de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-111">Sales order detail information.</span></span> <span data-ttu-id="d8e4e-112">Esto incluye uno o varios productos pedidos, el precio por unidad y la cantidad pedida.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-112">This includes one or more products ordered, the unit price, and the quantity ordered.</span></span> <span data-ttu-id="d8e4e-113">Esta información se almacena en la tabla `SalesOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="d8e4e-113">This information is stored in the `SalesOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="d8e4e-114">Información del vendedor.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-114">Sales person information.</span></span> <span data-ttu-id="d8e4e-115">Es el vendedor que tomó el pedido.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-115">This is the salesperson who took the order.</span></span> <span data-ttu-id="d8e4e-116">En la tabla `SalesPerson` se proporciona el valor `SalesPersonID`.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-116">The `SalesPerson` table provides the `SalesPersonID`.</span></span> <span data-ttu-id="d8e4e-117">Para esta consulta, tiene que combinar esta tabla con la tabla `Employee` para buscar el nombre del vendedor.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-117">For this query, you have to join this table to the `Employee` table to find the name of the sales person.</span></span>  
  
 <span data-ttu-id="d8e4e-118">Las dos consultas `SELECT` siguientes generan XML con una pequeña diferencia en la forma.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-118">The two distinct `SELECT` queries that follow generate XML with a small difference in shape.</span></span>  
  
 <span data-ttu-id="d8e4e-119">La primera consulta genera XML en el que <`SalesPerson`> y <`SalesOrderHeader`> aparecen como elementos secundarios iguales de <`SalesOrder`>:</span><span class="sxs-lookup"><span data-stu-id="d8e4e-119">The first query generates XML in which <`SalesPerson`> and <`SalesOrderHeader`> appear as sibling children of <`SalesOrder`>:</span></span>  
  
```  
SELECT   
      (SELECT top 2 SalesOrderID, SalesPersonID, CustomerID,  
         (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
           from Sales.SalesOrderDetail  
            WHERE  SalesOrderDetail.SalesOrderID =   
                   SalesOrderHeader.SalesOrderID  
            FOR XML AUTO, TYPE)  
        FROM  Sales.SalesOrderHeader  
        WHERE SalesOrderHeader.SalesOrderID = SalesOrder.SalesOrderID  
        for xml auto, type),  
        (SELECT *   
         FROM  (SELECT SalesPersonID, EmployeeID  
              FROM Sales.SalesPerson, HumanResources.Employee  
              WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As   
                     SalesPerson  
         WHERE  SalesPerson.SalesPersonID = SalesOrder.SalesPersonID  
       FOR XML AUTO, TYPE)  
FROM (SELECT SalesOrderHeader.SalesOrderID, SalesOrderHeader.SalesPersonID  
      FROM Sales.SalesOrderHeader, Sales.SalesPerson  
      WHERE SalesOrderHeader.SalesPersonID = SalesPerson.SalesPersonID  
     ) as SalesOrder  
ORDER BY SalesOrder.SalesOrderID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="d8e4e-120">En la consulta anterior, la instrucción `SELECT` más externa realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d8e4e-120">In the previous query, the outermost `SELECT` statement does the following:</span></span>  
  
-   <span data-ttu-id="d8e4e-121">Consulta el conjunto de filas, `SalesOrder`, especificado en la cláusula `FROM`.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-121">Queries the rowset, `SalesOrder`, specified in the `FROM` clause.</span></span> <span data-ttu-id="d8e4e-122">El resultado es un XML con uno o varios elementos <`SalesOrder`>.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-122">The result is an XML with one or more <`SalesOrder`> elements.</span></span>  
  
-   <span data-ttu-id="d8e4e-123">Especifica el modo `AUTO` y la directiva `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="d8e4e-123">Specifies `AUTO` mode and the `TYPE` directive.</span></span> <span data-ttu-id="d8e4e-124">`AUTO`el modo transforma el resultado de la consulta en XML y la `TYPE` Directiva devuelve el resultado como `xml` tipo.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-124">`AUTO` mode transforms the query result into XML, and the `TYPE` directive returns the result as `xml` type.</span></span>  
  
-   <span data-ttu-id="d8e4e-125">Incluye dos instrucciones `SELECT` anidadas separadas por una coma.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-125">Includes two nested `SELECT` statements separated by a comma.</span></span> <span data-ttu-id="d8e4e-126">La primera instrucción `SELECT` anidada recupera información de pedidos de ventas, encabezado y detalles, y la segunda instrucción `SELECT` anidada recupera información del vendedor.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-126">The first nested `SELECT` retrieves sales order information, header and details, and the second nested `SELECT` statement retrieves salesperson information.</span></span>  
  
    -   <span data-ttu-id="d8e4e-127">La instrucción `SELECT` que recupera `SalesOrderID`, `SalesPersonID`y `CustomerID` incluye otra instrucción `SELECT ... FOR XML` anidada (con el modo `AUTO` y la directiva `TYPE` ) que devuelve información de detalles de pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-127">The `SELECT` statement that retrieves `SalesOrderID`, `SalesPersonID`, and `CustomerID` itself includes another nested `SELECT ... FOR XML` statement (with `AUTO` mode and `TYPE` directive) that returns sales order detail information.</span></span>  
  
 <span data-ttu-id="d8e4e-128">La instrucción `SELECT` que recupera información del vendedor consulta un conjunto de filas, `SalesPerson`, creado en la cláusula `FROM` .</span><span class="sxs-lookup"><span data-stu-id="d8e4e-128">The `SELECT` statement that retrieves the sales person information queries a rowset, `SalesPerson`, created in the `FROM` clause.</span></span> <span data-ttu-id="d8e4e-129">Para que las consultas `FOR XML` funcionen, debe proporcionar un nombre para el conjunto de filas anónimo generado en la cláusula `FROM` .</span><span class="sxs-lookup"><span data-stu-id="d8e4e-129">For `FOR XML` queries to work, you must provide a name for the anonymous rowset generated in the `FROM` clause.</span></span> <span data-ttu-id="d8e4e-130">En este caso, el nombre proporcionado es `SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-130">In this case, the name provided is `SalesPerson`.</span></span>  
  
 <span data-ttu-id="d8e4e-131">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="d8e4e-131">This is the partial result:</span></span>  
  
```  
<SalesOrder>  
  <Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  </Sales.SalesOrderHeader>  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</SalesOrder>  
...  
```  
  
 <span data-ttu-id="d8e4e-132">La siguiente consulta genera la misma información de pedidos de ventas, pero en el XML resultante <`SalesPerson`> aparece como elemento de mismo nivel de <`SalesOrderDetail`>:</span><span class="sxs-lookup"><span data-stu-id="d8e4e-132">The following query generates the same sales order information, except that in the resulting XML, the <`SalesPerson`> appears as a sibling of <`SalesOrderDetail`>:</span></span>  
  
```  
<SalesOrder>  
    <SalesOrderHeader ...>  
          <SalesOrderDetail .../>  
          <SalesOrderDetail .../>  
          ...  
          <SalesPerson .../>  
    </SalesOrderHeader>  
  
</SalesOrder>  
<SalesOrder>  
  ...  
</SalesOrder>  
```  
  
 <span data-ttu-id="d8e4e-133">Esta es la consulta:</span><span class="sxs-lookup"><span data-stu-id="d8e4e-133">This is the query:</span></span>  
  
```  
SELECT SalesOrderID, SalesPersonID, CustomerID,  
             (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
              from Sales.SalesOrderDetail  
              WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
              FOR XML AUTO, TYPE),  
              (SELECT *   
               FROM  (SELECT SalesPersonID, EmployeeID  
                    FROM Sales.SalesPerson, HumanResources.Employee  
                    WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
               WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
         FOR XML AUTO, TYPE)  
FROM Sales.SalesOrderHeader  
WHERE SalesOrderID=43659 or SalesOrderID=43660  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="d8e4e-134">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8e4e-134">This is the result:</span></span>  
  
```  
<Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
<Sales.SalesOrderHeader SalesOrderID="43660" SalesPersonID="279" CustomerID="117">  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="762" OrderQty="1" UnitPrice="419.4589" />  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="758" OrderQty="1" UnitPrice="874.7940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
```  
  
 <span data-ttu-id="d8e4e-135">Puesto que la directiva `TYPE` devuelve un resultado de consulta de tipo `xml`, puede consultar el XML resultante utilizando varios métodos del tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-135">Because the `TYPE` directive returns a query result as `xml` type, you can query the resulting XML by using various `xml` data type methods.</span></span> <span data-ttu-id="d8e4e-136">Para obtener más información, vea [Métodos de tipo de datos xml](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="d8e4e-136">For more information, see [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span> <span data-ttu-id="d8e4e-137">En la siguiente consulta, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8e4e-137">In the following query, note the following:</span></span>  
  
-   <span data-ttu-id="d8e4e-138">La consulta anterior se agrega a la cláusula `FROM` .</span><span class="sxs-lookup"><span data-stu-id="d8e4e-138">The previous query is added in the `FROM` clause.</span></span> <span data-ttu-id="d8e4e-139">El resultado de la consulta se devuelve como una tabla.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-139">The query result is returned as a table.</span></span> <span data-ttu-id="d8e4e-140">Observe el alias `XmlCol` agregado.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-140">Note the `XmlCol` alias that is added.</span></span>  
  
-   <span data-ttu-id="d8e4e-141">La cláusula `SELECT` especifica una consulta XQuery en el `XmlCol` devuelto en la cláusula `FROM` .</span><span class="sxs-lookup"><span data-stu-id="d8e4e-141">The `SELECT` clause specifies an XQuery against the `XmlCol` returned in the `FROM` clause.</span></span> <span data-ttu-id="d8e4e-142">Para especificar la consulta XQuery se utiliza el método `query()` del tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="d8e4e-142">The `query()` method of the `xml` data type is used in specifying the XQuery.</span></span> <span data-ttu-id="d8e4e-143">Para obtener más información, vea [query&#40;&#41; &#40;método de tipo de datos xml&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="d8e4e-143">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
    ```  
    SELECT XmlCol.query('<Root> { /* } </Root>')  
    FROM (  
    SELECT SalesOrderID, SalesPersonID, CustomerID,  
                 (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
                  from Sales.SalesOrderDetail  
                  WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
                  FOR XML AUTO, TYPE),  
                  (SELECT *   
                   FROM  (SELECT SalesPersonID, EmployeeID  
                        FROM Sales.SalesPerson, HumanResources.Employee  
                        WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
                   WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
             FOR XML AUTO, TYPE)  
    FROM Sales.SalesOrderHeader  
    WHERE SalesOrderID='43659' or SalesOrderID='43660'  
    FOR XML AUTO, TYPE ) as T(XmlCol)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d8e4e-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8e4e-144">See Also</span></span>  
 [<span data-ttu-id="d8e4e-145">Usar consultas FOR XML anidadas</span><span class="sxs-lookup"><span data-stu-id="d8e4e-145">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
