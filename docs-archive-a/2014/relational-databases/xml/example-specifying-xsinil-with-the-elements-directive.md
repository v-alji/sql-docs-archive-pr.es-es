---
title: 'Ejemplo: Especificar XSINIL con la directiva ELEMENTS | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, specifying XSINIL example
ms.assetid: 07c873ff-1f9d-480e-8536-862c39eb8249
author: rothja
ms.author: jroth
ms.openlocfilehash: 7817d2c72909ca66fb9fac10f8fcb32a759faf56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744008"
---
# <a name="example-specifying-xsinil-with-the-elements-directive"></a><span data-ttu-id="6433f-102">Ejemplo: Especificación de XSINIL con la directiva ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="6433f-102">Example: Specifying XSINIL with the ELEMENTS Directive</span></span>
  <span data-ttu-id="6433f-103">En esta consulta se especifica la directiva `ELEMENTS` para generar XML centrado en elementos a partir del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="6433f-103">The following query specifies the `ELEMENTS` directive to generate element-centric XML from the query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6433f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6433f-104">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductID, Name, Color  
FROM Production.Product  
FOR XML RAW, ELEMENTS;  
GO  
```  
  
 <span data-ttu-id="6433f-105">El resultado parcial es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="6433f-105">This is the partial result.</span></span>  
  
```  
<row>  
  <ProductID>1</ProductID>  
  <Name>Adjustable Race</Name>  
</row>  
...  
<row>  
  <ProductID>317</ProductID>  
  <Name>LL Crankarm</Name>  
  <Color>Black</Color>  
</row>  
```  
  
 <span data-ttu-id="6433f-106">Dado que la columna `Color` tiene valores NULL para algunos productos, el XML resultante no generará el elemento <`Color`> correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6433f-106">Because the `Color` column has null values for some products, the resulting XML will not generate the corresponding <`Color`> element.</span></span> <span data-ttu-id="6433f-107">Al agregar la directiva `XSINIL` junto con `ELEMENTS`, se puede generar el elemento <`Color`> incluso para los valores de color NULL del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="6433f-107">By adding the `XSINIL` directive with `ELEMENTS`, you can generate the <`Color`> element even for NULL color values in the result set.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductID, Name, Color  
FROM Production.Product  
FOR XML RAW, ELEMENTS XSINIL ;  
```  
  
 <span data-ttu-id="6433f-108">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="6433f-108">This is the partial result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <ProductID>1</ProductID>  
  <Name>Adjustable Race</Name>  
  <Color xsi:nil="true" />  
</row>  
...  
<row>  
  <ProductID>317</ProductID>  
  <Name>LL Crankarm</Name>  
  <Color>Black</Color>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6433f-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6433f-109">See Also</span></span>  
 [<span data-ttu-id="6433f-110">Usar el modo RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="6433f-110">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
