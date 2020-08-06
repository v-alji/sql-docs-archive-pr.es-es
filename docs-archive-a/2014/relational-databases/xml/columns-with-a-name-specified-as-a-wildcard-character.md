---
title: Columnas con un nombre especificado como carácter comodín | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: d9551df1-5bb4-4c0b-880a-5bb049834884
author: rothja
ms.author: jroth
ms.openlocfilehash: 4b363baf8792628c2e17b1a695c19a6a338f4fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672831"
---
# <a name="columns-with-a-name-specified-as-a-wildcard-character"></a><span data-ttu-id="3ca09-102">Columnas con un nombre especificado como carácter comodín</span><span class="sxs-lookup"><span data-stu-id="3ca09-102">Columns with a Name Specified as a Wildcard Character</span></span>
  <span data-ttu-id="3ca09-103">Si el nombre de columna especificado es un carácter comodín (\*), su contenido se insertará como si no se hubiera especificado ningún nombre.</span><span class="sxs-lookup"><span data-stu-id="3ca09-103">If the column name specified is a wildcard character (\*), the content of that column is inserted as if there is no column name specified.</span></span> <span data-ttu-id="3ca09-104">Si esta columna no es del tipo `xml`, su contenido se insertará como un nodo de texto, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ca09-104">If this column is a non-`xml` type column, the column content is inserted as a text node, as shown in the following example:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
       FirstName "*",   
       MiddleName "*",   
       LastName "*"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
    ON E.BusinessEntityID = P.BusinessEntityID  
WHERE E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="3ca09-105">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ca09-105">This is the result:</span></span>  
  
 `<row EmpID="1">KenJS??nchez</row>`  
  
 <span data-ttu-id="3ca09-106">Si la columna es de tipo `xml`, se inserta el árbol XML correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3ca09-106">If the column is of `xml` type, the corresponding XML tree is inserted.</span></span> <span data-ttu-id="3ca09-107">Por ejemplo, la consulta siguiente especifica "\*" para el nombre de columna que incluye el XML devuelto por XQuery con la columna Instructions.</span><span class="sxs-lookup"><span data-stu-id="3ca09-107">For example, the following query specifies "\*" for the column name that contains the XML returned by the XQuery against the Instructions column.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
                /MI:root/MI:Location   
              ') as "*"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH;   
GO  
```  
  
 <span data-ttu-id="3ca09-108">Éste es el resultado.</span><span class="sxs-lookup"><span data-stu-id="3ca09-108">This is the result.</span></span> <span data-ttu-id="3ca09-109">El XML devuelto por XQuery se insertará sin un elemento de ajuste.</span><span class="sxs-lookup"><span data-stu-id="3ca09-109">The XML returned by XQuery is inserted without a wrapping element.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location LocationID="10">...</MI:Location>`  
  
 `<MI:Location LocationID="20">...</MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="3ca09-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ca09-110">See Also</span></span>  
 [<span data-ttu-id="3ca09-111">Usar el modo PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="3ca09-111">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
