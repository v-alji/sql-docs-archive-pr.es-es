---
title: Nombres de columna con la ruta de acceso especificada como data() | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: 0b738e44-6108-4417-a9a4-abeb7680d899
author: rothja
ms.author: jroth
ms.openlocfilehash: 61aa7f85c7ee2358ddcf99f81c87c1295fac8fb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662702"
---
# <a name="column-names-with-the-path-specified-as-data"></a><span data-ttu-id="b84fc-102">Nombres de columna con la ruta de acceso especificada como data()</span><span class="sxs-lookup"><span data-stu-id="b84fc-102">Column Names with the Path Specified as data()</span></span>
  <span data-ttu-id="b84fc-103">Si la ruta de acceso especificada como nombre de la columna es "data()", el valor se tratará como valor atómico en el XML generado.</span><span class="sxs-lookup"><span data-stu-id="b84fc-103">If the path specified as column name is "data()", the value is treated as an atomic value in the generated XML.</span></span> <span data-ttu-id="b84fc-104">Si el siguiente elemento de la serialización también es un valor atómico, se agregará un carácter de espacio al XML.</span><span class="sxs-lookup"><span data-stu-id="b84fc-104">A space character is added to the XML if the next item in the serialization is also an atomic value.</span></span> <span data-ttu-id="b84fc-105">Esto resulta útil cuando se crean valores de elementos y atributos del tipo lista.</span><span class="sxs-lookup"><span data-stu-id="b84fc-105">This is useful when you are creating list typed element and attribute values.</span></span> <span data-ttu-id="b84fc-106">La consulta siguiente recupera el Id. del modelo de producto, el nombre del producto y una lista de los productos de ese modelo.</span><span class="sxs-lookup"><span data-stu-id="b84fc-106">The following query retrieves the product model ID, name, and list of products in that product model.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID       AS "@ProductModelID",  
       Name                 AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
      FOR XML PATH (''))    AS "@ProductIDs"  
FROM  Production.ProductModel  
WHERE ProductModelID= 7   
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="b84fc-107">La instrucción SELECT anidada recupera una lista de Id. de productos.</span><span class="sxs-lookup"><span data-stu-id="b84fc-107">The nested SELECT retrieves a list of product IDs.</span></span> <span data-ttu-id="b84fc-108">Especificará "data()" como nombre de columna de los Id. de productos.</span><span class="sxs-lookup"><span data-stu-id="b84fc-108">It specifies "data()" as the column name for product IDs.</span></span> <span data-ttu-id="b84fc-109">El modo PATH especifica una cadena vacía para el nombre de elemento de fila, por lo que no se generará ningún elemento de fila.</span><span class="sxs-lookup"><span data-stu-id="b84fc-109">Because PATH mode specifies an empty string for the row element name, there is no row element generated.</span></span> <span data-ttu-id="b84fc-110">En su lugar, se devolverán los valores como asignados a un atributo ProductIDs del elemento de fila <`ProductModelData`> de la instrucción SELECT primaria.</span><span class="sxs-lookup"><span data-stu-id="b84fc-110">Instead, the values are returned as assigned to a ProductIDs attribute of the <`ProductModelData`> row element of the parent SELECT.</span></span> <span data-ttu-id="b84fc-111">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b84fc-111">This is the result:</span></span>  
  
 `<ProductModelData ProductModelID="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 888 889 890 891 892 893" />`  
  
## <a name="see-also"></a><span data-ttu-id="b84fc-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b84fc-112">See Also</span></span>  
 [<span data-ttu-id="b84fc-113">Usar el modo PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="b84fc-113">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
