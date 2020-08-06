---
title: Columnas con el nombre de una prueba de nodo XPath | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
- XPath node test
ms.assetid: b48adccd-3b6b-486a-b326-20f57170186f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6555815d97308bed6e70d9fedb9858fc3abe7685
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745088"
---
# <a name="columns-with-the-name-of-an-xpath-node-test"></a><span data-ttu-id="02e87-102">Columnas con el nombre de una prueba de nodo XPath</span><span class="sxs-lookup"><span data-stu-id="02e87-102">Columns with the Name of an XPath Node Test</span></span>
  <span data-ttu-id="02e87-103">Si el nombre de columna es una de las pruebas de nodo XPath, se asignará el contenido tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="02e87-103">If the column name is one of the XPath node tests, the content is mapped as shown in the following table.</span></span> <span data-ttu-id="02e87-104">Cuando el nombre de la columna es una prueba de nodo XPath, se asigna el contenido al nodo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="02e87-104">When the column name is an XPath node test, the content is mapped to the corresponding node.</span></span> <span data-ttu-id="02e87-105">Si el tipo SQL de la columna es `xml`, se devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="02e87-105">If the SQL type of the column is `xml`, an error is returned.</span></span>  
  
|<span data-ttu-id="02e87-106">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="02e87-106">Column Name</span></span>|<span data-ttu-id="02e87-107">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="02e87-107">Behavior</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="02e87-108">text()</span><span class="sxs-lookup"><span data-stu-id="02e87-108">text()</span></span>|<span data-ttu-id="02e87-109">En el caso de las columnas con el nombre text(), el valor de cadena de la misma se agregará como un nodo de texto.</span><span class="sxs-lookup"><span data-stu-id="02e87-109">For a column with the name of text(), the string value in that column is added as a text node.</span></span>|  
|<span data-ttu-id="02e87-110">comment()</span><span class="sxs-lookup"><span data-stu-id="02e87-110">comment()</span></span>|<span data-ttu-id="02e87-111">En el caso de las columnas con el nombre comment(), el valor de cadena de la misma se agregará como un comentario XML.</span><span class="sxs-lookup"><span data-stu-id="02e87-111">For a column with the name of comment(), the string value in that column is added as an XML comment.</span></span>|  
|<span data-ttu-id="02e87-112">node()</span><span class="sxs-lookup"><span data-stu-id="02e87-112">node()</span></span>|<span data-ttu-id="02e87-113">En el caso de las columnas con el nombre node(), el resultado será el mismo que cuando el nombre de la columna es un carácter comodín (\*).</span><span class="sxs-lookup"><span data-stu-id="02e87-113">For a column with the name of node(), the result is the same as it is when the column name is a wildcard character (\*).</span></span>|  
|<span data-ttu-id="02e87-114">processing-instruction(name)</span><span class="sxs-lookup"><span data-stu-id="02e87-114">processing-instruction(name)</span></span>|<span data-ttu-id="02e87-115">En el caso de las columnas con el nombre de una instrucción de procesamiento, su valor de cadena se agregará como el valor PI para el nombre de destino de la instrucción de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="02e87-115">For a column with the name of a processing instruction, the string value in that column is added as the PI value for the processing instruction target name.</span></span>|  
  
 <span data-ttu-id="02e87-116">La siguiente consulta muestra el uso de las pruebas de nodo como nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="02e87-116">The following query shows the use of the node tests as column names.</span></span> <span data-ttu-id="02e87-117">Agrega nodos de texto y comentarios en el XML resultante.</span><span class="sxs-lookup"><span data-stu-id="02e87-117">It adds text nodes and comments in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
        'Example of using node tests such as text(), comment(), processing-instruction()'                as "comment()",  
        'Some PI'                   as "processing-instruction(PI)",  
        'Employee name and address data' as "text()",  
        'middle name is optional'        as "EmpName/text()",  
        FirstName                        as "EmpName/First",   
        MiddleName                       as "EmpName/Middle",   
        LastName                         as "EmpName/Last",  
        AddressLine1                     as "Address/AddrLine1",  
        AddressLine2                     as "Address/AddrLIne2",  
        City                             as "Address/City"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P   
    ON P.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.BusinessEntityAddress AS BAE  
    ON BAE.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.Address AS A  
    ON BAE.AddressID = A.AddressID  
WHERE  E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="02e87-118">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="02e87-118">This is the result:</span></span>  
  
 `<row EmpID="1">`  
  
 `<!--Example of using node tests such as text(), comment(), processing-instruction() -->`  
  
 `<?PI Some PI?>`  
  
 `Employee name and address data`  
  
 `<EmpName>middle name is optional`  
  
 `<First>Ken</First>`  
  
 `<Last>S??nchez</Last>`  
  
 `</EmpName>`  
  
 `<Address>`  
  
 `<AddrLine1>4350 Minute Dr.</AddrLine1>`  
  
 `<City>Minneapolis</City>`  
  
 `</Address>`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="02e87-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02e87-119">See Also</span></span>  
 [<span data-ttu-id="02e87-120">Usar el modo PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="02e87-120">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
