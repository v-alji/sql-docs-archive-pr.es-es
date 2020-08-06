---
title: 'Ejemplo: Recuperación de datos binarios | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, retrieving binary data example
ms.assetid: 5cea5d49-58ac-403a-a933-c4fd91de400b
author: rothja
ms.author: jroth
ms.openlocfilehash: 516c7d91d0a6ebac7366b4bb3cbafe5d05aaa232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677449"
---
# <a name="example-retrieving-binary-data"></a><span data-ttu-id="72c35-102">Ejemplo: Recuperación de datos binarios</span><span class="sxs-lookup"><span data-stu-id="72c35-102">Example: Retrieving Binary Data</span></span>
  <span data-ttu-id="72c35-103">La consulta siguiente devuelve la fotografía del producto almacenada en una columna de tipo `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="72c35-103">The following query returns the product photo stored in a `varbinary(max)` type column.</span></span> <span data-ttu-id="72c35-104">En la consulta, se especifica la opción `BINARY BASE64` para devolver los datos binarios en formato codificado en base 64.</span><span class="sxs-lookup"><span data-stu-id="72c35-104">The `BINARY BASE64` option is specified in the query to return the binary data in base64-encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72c35-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72c35-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductPhotoID, ThumbNailPhoto  
FROM Production.ProductPhoto  
WHERE ProductPhotoID=1  
FOR XML RAW, BINARY BASE64 ;  
GO  
```  
  
 <span data-ttu-id="72c35-106">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="72c35-106">This is the result:</span></span>  
  
```  
<row ProductModelID="1" ThumbNailPhoto="base64 encoded binary data"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72c35-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72c35-107">See Also</span></span>  
 [<span data-ttu-id="72c35-108">Usar el modo RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="72c35-108">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  