---
title: 'Ejemplo: Consulta de columnas de tipo XML | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, querying XML example
ms.assetid: d9f3710d-7a2e-4abe-9c02-3e3c0df4d620
author: rothja
ms.author: jroth
ms.openlocfilehash: 0eedfa5a5a265f3715a76a6ca80d489bbec199bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662694"
---
# <a name="example-querying-xmltype-columns"></a><span data-ttu-id="c0b05-102">Ejemplo: Consulta de columnas de tipo XML</span><span class="sxs-lookup"><span data-stu-id="c0b05-102">Example: Querying XMLType Columns</span></span>
  <span data-ttu-id="c0b05-103">La consulta siguiente incluye columnas de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="c0b05-103">The following query includes columns of `xml` type.</span></span> <span data-ttu-id="c0b05-104">La consulta recupera el identificador, nombre y pasos de fabricación del modelo de producto en la primera ubicación de la columna `Instructions` de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="c0b05-104">The query retrieves product model ID, name, and manufacturing steps at the first location from the `Instructions` column of the `xml` type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0b05-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0b05-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
')   
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
GO  
```  
  
 <span data-ttu-id="c0b05-106">A continuación se muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="c0b05-106">The following is the result.</span></span> <span data-ttu-id="c0b05-107">Tenga en cuenta que la tabla almacena las instrucciones de fabricación solo de algunos modelos de productos.</span><span class="sxs-lookup"><span data-stu-id="c0b05-107">Note that the table stores manufacturing instructions for only some product models.</span></span> <span data-ttu-id="c0b05-108">Los pasos de fabricación se devuelven como subelementos del elemento <`ProductModelData`> en el resultado.</span><span class="sxs-lookup"><span data-stu-id="c0b05-108">The manufacturing steps are returned as subelements of the <`ProductModelData`> element in the result.</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
    <MI:step> ... </MI:step>  
    <MI:step> ... </MI:step>  
 </ProductModelData>  
```  
  
 <span data-ttu-id="c0b05-109">Si la consulta especifica un nombre de columna para el XML devuelto por la consulta XQuery, como se especifica en la siguiente instrucción `SELECT` , los pasos de fabricación se incluyen en el elemento que tiene el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="c0b05-109">If the query specifies a column name for the XML returned by the XQuery, as specified in the following `SELECT` statement, the manufacturing steps are wrapped in the element that has the specified name.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
go  
```  
  
 <span data-ttu-id="c0b05-110">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0b05-110">This is the result:</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
  <ManuSteps>  
    <MI:step ... </MI:step>  
    <MI:step ... </MI:step>  
  </ManuSteps>  
</ProductModelData>  
```  
  
 <span data-ttu-id="c0b05-111">En la consulta siguiente se especifica la directiva `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="c0b05-111">The following query specifies the `ELEMENTS` directive.</span></span> <span data-ttu-id="c0b05-112">Por tanto, el resultado devuelto está centrado en elementos.</span><span class="sxs-lookup"><span data-stu-id="c0b05-112">Therefore, the result returned is element-centric.</span></span> <span data-ttu-id="c0b05-113">La opción `XSINIL` especificada junto con la directiva `ELEMENTS` devuelve los elementos <`ManuSteps`>, aunque la columna correspondiente del conjunto de resultados sea NULL.</span><span class="sxs-lookup"><span data-stu-id="c0b05-113">The `XSINIL` option specified with the `ELEMENTS` directive returns the <`ManuSteps`> elements, even if the corresponding column in the rowset is NULL.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData'), root('MyRoot'), ELEMENTS XSINIL  
go  
```  
  
 <span data-ttu-id="c0b05-114">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0b05-114">This is the result:</span></span>  
  
```  
<MyRoot xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   ...  
  <ProductModelData>  
    <ProductModelID>6</ProductModelID>  
    <Name>HL Road Frame</Name>  
    <ManuSteps xsi:nil="true" />  
  </ProductModelData>  
  <ProductModelData>  
    <ProductModelID>7</ProductModelID>  
    <Name>HL Touring Frame</Name>  
    <ManuSteps>  
      <MI:step ... </MI:step>  
      <MI:step ...</MI:step>  
       ...  
    </ManuSteps>  
  </ProductModelData>  
</MyRoot>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0b05-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0b05-115">See Also</span></span>  
 [<span data-ttu-id="c0b05-116">Usar el modo RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="c0b05-116">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
