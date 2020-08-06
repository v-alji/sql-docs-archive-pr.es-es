---
title: 'Ejemplo: Especificación de las directivas ID e IDREFS | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- IDREFS directive
- ID directive
ms.assetid: 99b9f0d8-ecbb-4225-859f-881066c09785
author: rothja
ms.author: jroth
ms.openlocfilehash: c21ba1bd19691014f179801421322970a3dd6dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676386"
---
# <a name="example-specifying-the-id-and-idrefs-directives"></a><span data-ttu-id="58db7-102">Ejemplo: Especificación de las directivas ID e IDREFS</span><span class="sxs-lookup"><span data-stu-id="58db7-102">Example: Specifying the ID and IDREFS Directives</span></span>
  <span data-ttu-id="58db7-103">El atributo de un elemento se puede especificar como un atributo de tipo `ID` y el atributo `IDREFS` puede usarse para hacer referencia a él.</span><span class="sxs-lookup"><span data-stu-id="58db7-103">An element attribute can be specified as an `ID` type attribute, and the `IDREFS` attribute can then be used to refer to it.</span></span> <span data-ttu-id="58db7-104">De esta forma se habilitan vínculos dentro de los documentos; esto es similar a las relaciones entre la clave principal y la clave externa en las bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="58db7-104">This enables intra-document links and is similar to the primary key and foreign key relationships in relational databases.</span></span>  
  
 <span data-ttu-id="58db7-105">Este ejemplo ilustra cómo se pueden usar las directivas `ID` e `IDREFS` para crear atributos de tipos `ID` e `IDREFS`.</span><span class="sxs-lookup"><span data-stu-id="58db7-105">This example illustrates how the `ID` and `IDREFS` directives can be used to create attributes of `ID` and `IDREFS` types.</span></span> <span data-ttu-id="58db7-106">Dado que los identificadores no pueden contener valores enteros, los valores ID de este ejemplo se convierten.</span><span class="sxs-lookup"><span data-stu-id="58db7-106">Because IDs cannot be integer values, the ID values in this example are converted.</span></span> <span data-ttu-id="58db7-107">Dicho de otro modo, se realiza una conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="58db7-107">In other words, they are type casted.</span></span> <span data-ttu-id="58db7-108">Para los valores ID se utilizan prefijos.</span><span class="sxs-lookup"><span data-stu-id="58db7-108">Prefixes are used for the ID values.</span></span>  
  
 <span data-ttu-id="58db7-109">Suponga que desea crear XML como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="58db7-109">Assume that you want to construct XML as shown in the following:</span></span>  
  
```  
<Customer CustomerID="C1" SalesOrderIDList=" O11 O22 O33..." >  
    <SalesOrder SalesOrderID="O11" OrderDate="..." />  
    <SalesOrder SalesOrderID="O22" OrderDate="..." />  
    <SalesOrder SalesOrderID="O33" OrderDate="..." />  
    ...  
</Customer>  
```  
  
 <span data-ttu-id="58db7-110">El atributo `SalesOrderIDList` del elemento < `Customer` > es un atributo con varios valores que hace referencia al atributo `SalesOrderID` del elemento < `SalesOrder` >.</span><span class="sxs-lookup"><span data-stu-id="58db7-110">The `SalesOrderIDList` attribute of the < `Customer` > element is a multivalued attribute that refers to the `SalesOrderID` attribute of the < `SalesOrder` > element.</span></span> <span data-ttu-id="58db7-111">Para establecer este vínculo, el atributo `SalesOrderID` debe declararse de tipo `ID` y el atributo `SalesOrderIDList` del elemento < `Customer`> debe declararse de tipo `IDREFS`.</span><span class="sxs-lookup"><span data-stu-id="58db7-111">To establish this link, the `SalesOrderID` attribute must be declared of `ID` type, and the `SalesOrderIDList` attribute of the < `Customer`> element must be declared of `IDREFS` type.</span></span> <span data-ttu-id="58db7-112">Dado que un cliente puede solicitar varios pedidos, se utiliza el tipo `IDREFS` .</span><span class="sxs-lookup"><span data-stu-id="58db7-112">Because a customer can request several orders, the `IDREFS` type is used.</span></span>  
  
 <span data-ttu-id="58db7-113">Los elementos del tipo `IDREFS` también tienen más de un valor.</span><span class="sxs-lookup"><span data-stu-id="58db7-113">Elements of `IDREFS` type also have more than one value.</span></span> <span data-ttu-id="58db7-114">Por lo tanto, se tiene que utilizar una cláusula SELECT independiente, que volverá a utilizar la misma información de columna de clave, etiqueta y elemento primario.</span><span class="sxs-lookup"><span data-stu-id="58db7-114">Therefore, you have to use a separate select clause that will reuse the same tag, parent, and key column information.</span></span> <span data-ttu-id="58db7-115">A continuación, `ORDER BY` tiene que asegurarse de que la secuencia de filas que componen los valores de `IDREFS` aparezca agrupada bajo el elemento primario.</span><span class="sxs-lookup"><span data-stu-id="58db7-115">The `ORDER BY` then has to ensure that the sequence of rows that make up the `IDREFS` values appears grouped together under their parent element.</span></span>  
  
 <span data-ttu-id="58db7-116">Esta es la consulta que genera el XML deseado.</span><span class="sxs-lookup"><span data-stu-id="58db7-116">This is the query that produces the XML you want.</span></span> <span data-ttu-id="58db7-117">La consulta utiliza las directivas `ID` e `IDREFS` para sobrescribir los tipos en los nombres de columna (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span><span class="sxs-lookup"><span data-stu-id="58db7-117">The query uses the `ID` and `IDREFS` directives to overwrite the types in the column names (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID       [Customer!1!CustomerID],  
        NULL               [Customer!1!SalesOrderIDList!IDREFS],  
        NULL               [SalesOrder!2!SalesOrderID!ID],  
        NULL               [SalesOrder!2!OrderDate]  
FROM   Sales.Customer C   
UNION ALL   
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID,  
        'O-'+CAST(SalesOrderID as varchar(10)),   
        NULL,  
        NULL  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
        C.CustomerID,  
        NULL,  
        'O-'+CAST(SalesOrderID as varchar(10)),  
        OrderDate  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerIDORDER BY [Customer!1!CustomerID] ,  
         [SalesOrder!2!SalesOrderID!ID],  
         [Customer!1!SalesOrderIDList!IDREFS]  
FOR XML EXPLICIT;  
```  
  
## <a name="see-also"></a><span data-ttu-id="58db7-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58db7-118">See Also</span></span>  
 [<span data-ttu-id="58db7-119">Usar el modo EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="58db7-119">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
