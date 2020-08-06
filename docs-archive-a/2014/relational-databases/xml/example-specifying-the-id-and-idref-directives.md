---
title: 'Ejemplo: Especificación de las directivas ID e IDREF | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- IDREF directive
- ID directive
ms.assetid: 7ff1ea73-71ca-4786-bd42-564f1b5de2d9
author: rothja
ms.author: jroth
ms.openlocfilehash: 864acbbe55037f1760bbb0e62557e3e80d3628c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676387"
---
# <a name="example-specifying-the-id-and-idref-directives"></a><span data-ttu-id="f64d9-102">Ejemplo: Especificación de las directivas ID e IDREF</span><span class="sxs-lookup"><span data-stu-id="f64d9-102">Example: Specifying the ID and IDREF Directives</span></span>
  <span data-ttu-id="f64d9-103">Este ejemplo es casi idéntico al ejemplo [Especificar la directiva ELEMENTXSINIL](example-specifying-the-elementxsinil-directive.md) .</span><span class="sxs-lookup"><span data-stu-id="f64d9-103">This example is almost the same the [Specifying the ELEMENTXSINIL Directive](example-specifying-the-elementxsinil-directive.md) example.</span></span> <span data-ttu-id="f64d9-104">La única diferencia consiste en que la consulta especifica las directivas **ID** e **IDREF** .</span><span class="sxs-lookup"><span data-stu-id="f64d9-104">The only difference is that the query specifies the **ID** and **IDREF** directives.</span></span> <span data-ttu-id="f64d9-105">Estas directivas sobrescriben los tipos del atributo **SalesPersonID** en los elementos <`OrderHeader`> y <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="f64d9-105">These directives overwrite the types of the **SalesPersonID** attribute in the <`OrderHeader`> and <`OrderDetail`> elements.</span></span> <span data-ttu-id="f64d9-106">De este modo, se forman vínculos dentro de los documentos.</span><span class="sxs-lookup"><span data-stu-id="f64d9-106">This forms intra-document links.</span></span> <span data-ttu-id="f64d9-107">Para ver los tipos sobrescritos, se necesita el esquema.</span><span class="sxs-lookup"><span data-stu-id="f64d9-107">You need the schema to see the overwritten types.</span></span> <span data-ttu-id="f64d9-108">Por lo tanto, la consulta especifica la opción **XMLDATA** en la cláusula FOR XML para recuperar el esquema.</span><span class="sxs-lookup"><span data-stu-id="f64d9-108">Therefore, the query specifies the **XMLDATA** option in the FOR XML clause to retrieve the schema.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        SalesOrderID  as [OrderHeader!1!SalesOrderID!id],  
        OrderDate     as [OrderHeader!1!OrderDate],  
        CustomerID    as [OrderHeader!1!CustomerID],  
        NULL          as [SalesPerson!2!SalesPersonID],  
        NULL          as [OrderDetail!3!SalesOrderID!idref],  
        NULL          as [OrderDetail!3!LineTotal],  
        NULL          as [OrderDetail!3!ProductID],  
        NULL          as [OrderDetail!3!OrderQty]  
FROM   Sales.SalesOrderHeader  
WHERE  SalesOrderID=43659 or SalesOrderID=43661  
UNION ALL   
SELECT 2 as Tag,  
       1 as Parent,  
        SalesOrderID,   
        NULL,  
        NULL,  
        SalesPersonID,    
        NULL,           
        NULL,           
        NULL,  
        NULL           
FROM   Sales.SalesOrderHeader  
WHERE  SalesOrderID=43659 or SalesOrderID=43661  
UNION ALL  
SELECT 3 as Tag,  
       1 as Parent,  
        SOD.SalesOrderID,  
        NULL,  
        NULL,  
        SalesPersonID,  
        SOH.SalesOrderID,  
        LineTotal,  
        ProductID,  
        OrderQty     
FROM    Sales.SalesOrderHeader SOH,Sales.SalesOrderDetail SOD  
WHERE   SOH.SalesOrderID = SOD.SalesOrderID  
AND     (SOH.SalesOrderID=43659 or SOH.SalesOrderID=43661)  
ORDER BY [OrderHeader!1!SalesOrderID!id], [SalesPerson!2!SalesPersonID],  
         [OrderDetail!3!SalesOrderID!idref],[OrderDetail!3!LineTotal]  
FOR XML EXPLICIT, XMLDATA  
```  
  
 <span data-ttu-id="f64d9-109">El resultado parcial es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="f64d9-109">This is the partial result.</span></span> <span data-ttu-id="f64d9-110">En el esquema, observe que las directivas **ID** e **IDREF** han sobrescrito los tipos de datos del atributo **SalesOrderID** en los elementos <`OrderHeader`> y <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="f64d9-110">In the schema, note that the **ID** and **IDREF** directives have overwritten the data types of the **SalesOrderID** attribute in the <`OrderHeader`> and <`OrderDetail`> elements.</span></span> <span data-ttu-id="f64d9-111">Si quita estas directivas, el esquema devuelve los tipos originales de estos atributos.</span><span class="sxs-lookup"><span data-stu-id="f64d9-111">If you remove these directives, the schema returns original types of these attributes.</span></span>  
  
```  
<Schema name="Schema1" xmlns="urn:schemas-microsoft-com:xml-data" xmlns:dt="urn:schemas-microsoft-com:datatypes">  
  <ElementType name="OrderHeader" content="mixed" model="open">  
    <AttributeType name="SalesOrderID" dt:type="id" />  
    <AttributeType name="OrderDate" dt:type="dateTime" />  
    <AttributeType name="CustomerID" dt:type="i4" />  
    <attribute type="SalesOrderID" />  
    <attribute type="OrderDate" />  
    <attribute type="CustomerID" />  
  </ElementType>  
  <ElementType name="SalesPerson" content="mixed" model="open">  
    <AttributeType name="SalesPersonID" dt:type="i4" />  
    <attribute type="SalesPersonID" />  
  </ElementType>  
  <ElementType name="OrderDetail" content="mixed" model="open">  
    <AttributeType name="SalesOrderID" dt:type="idref" />  
    <AttributeType name="LineTotal" dt:type="number" />  
    <AttributeType name="ProductID" dt:type="i4" />  
    <AttributeType name="OrderQty" dt:type="i2" />  
    <attribute type="SalesOrderID" />  
    <attribute type="LineTotal" />  
    <attribute type="ProductID" />  
    <attribute type="OrderQty" />  
  </ElementType>  
</Schema>  
<OrderHeader xmlns="x-schema:#Schema1" SalesOrderID="43659" OrderDate="2001-07-01T00:00:00" CustomerID="676">  
  <SalesPerson SalesPersonID="279" />  
  <OrderDetail SalesOrderID="43659" LineTotal="10.373000" ProductID="712" OrderQty="2" />  
  ...  
</OrderHeader>  
...  
```  
  
## <a name="see-also"></a><span data-ttu-id="f64d9-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f64d9-112">See Also</span></span>  
 [<span data-ttu-id="f64d9-113">Usar el modo EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="f64d9-113">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  