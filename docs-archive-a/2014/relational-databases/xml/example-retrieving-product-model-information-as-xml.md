---
title: 'Ejemplo: Recuperación de información de modelos de productos como XML | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, retrieving XML information example
ms.assetid: 3828b4ca-3ab2-444f-9c58-8be6e7f064a6
author: rothja
ms.author: jroth
ms.openlocfilehash: d580f53c4b5185a8b1b1467c75a08fc6929bdcf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673569"
---
# <a name="example-retrieving-product-model-information-as-xml"></a><span data-ttu-id="b8056-102">Ejemplo: Recuperación de información de modelos de productos como XML</span><span class="sxs-lookup"><span data-stu-id="b8056-102">Example: Retrieving Product Model Information as XML</span></span>
  <span data-ttu-id="b8056-103">En la siguiente consulta se devuelve información de modelos de productos.</span><span class="sxs-lookup"><span data-stu-id="b8056-103">The following query returns product model information.</span></span> <span data-ttu-id="b8056-104">`RAW` se especifica en la cláusula `FOR XML` .</span><span class="sxs-lookup"><span data-stu-id="b8056-104">`RAW` mode is specified in the `FOR XML` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8056-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8056-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW;  
GO  
```  
  
 <span data-ttu-id="b8056-106">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="b8056-106">This is the partial result:</span></span>  
  
 `<row ProductModelID="122" Name="All-Purpose Bike Stand" />`  
  
 `<row ProductModelID="119" Name="Bike Wash" />`  
  
 <span data-ttu-id="b8056-107">Se puede recuperar XML centrado en elementos si se especifica la directiva `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="b8056-107">You can retrieve element-centric XML by specifying the `ELEMENTS` directive.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, ELEMENTS;  
GO  
```  
  
 <span data-ttu-id="b8056-108">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8056-108">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</row>  
<row>  
  <ProductModelID>119</ProductModelID>  
  <Name>Bike Wash</Name>  
</row>  
```  
  
 <span data-ttu-id="b8056-109">Opcionalmente, se puede especificar la directiva `TYPE` para recuperar los resultados como de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="b8056-109">You can optionally specify the `TYPE` directive to retrieve the results as `xml` type.</span></span> <span data-ttu-id="b8056-110">La directiva `TYPE` no cambia el contenido de los resultados.</span><span class="sxs-lookup"><span data-stu-id="b8056-110">The `TYPE` directive does not change the content of the results.</span></span> <span data-ttu-id="b8056-111">Solo afecta al tipo de datos de los resultados.</span><span class="sxs-lookup"><span data-stu-id="b8056-111">Only the data type of the results is affected.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, TYPE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8056-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8056-112">See Also</span></span>  
 [<span data-ttu-id="b8056-113">Usar el modo RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="b8056-113">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
