---
title: Columnas sin nombre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns without
ms.assetid: 440de44e-3a56-4531-b4e4-1533ca933cac
author: rothja
ms.author: jroth
ms.openlocfilehash: 43d1cbce816e4666e6dab52fdffe5850e65740e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745087"
---
# <a name="columns-without-a-name"></a><span data-ttu-id="abbf9-102">Columnas sin nombre</span><span class="sxs-lookup"><span data-stu-id="abbf9-102">Columns without a Name</span></span>
  <span data-ttu-id="abbf9-103">Las columnas sin nombre se insertarán entre líneas.</span><span class="sxs-lookup"><span data-stu-id="abbf9-103">Any column without a name will be inlined.</span></span> <span data-ttu-id="abbf9-104">Por ejemplo, las columnas calculadas o las consultas escalares anidadas que no especifiquen alias de columna generarán columnas sin nombre.</span><span class="sxs-lookup"><span data-stu-id="abbf9-104">For example, computed columns or nested scalar queries that do not specify column alias will generate columns without any name.</span></span> <span data-ttu-id="abbf9-105">Si la columna es de tipo `xml`, se insertará el contenido de esa instancia de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="abbf9-105">If the column is of `xml` type, the content of that data type instance is inserted.</span></span> <span data-ttu-id="abbf9-106">De lo contrario, el contenido de la columna se insertará como un nodo de texto.</span><span class="sxs-lookup"><span data-stu-id="abbf9-106">Otherwise, the column content is inserted as a text node.</span></span>  
  
```  
SELECT 2+2  
FOR XML PATH  
```  
  
 <span data-ttu-id="abbf9-107">Cree este XML.</span><span class="sxs-lookup"><span data-stu-id="abbf9-107">Produce this XML.</span></span> <span data-ttu-id="abbf9-108">De forma predeterminada, por cada fila del conjunto de filas, se genera un elemento <`row`> en el XML resultante.</span><span class="sxs-lookup"><span data-stu-id="abbf9-108">By default, for each row in the rowset, a <`row`> element is generated in the resulting XML.</span></span> <span data-ttu-id="abbf9-109">Ocurre lo mismo que en el modo RAW.</span><span class="sxs-lookup"><span data-stu-id="abbf9-109">This is the same as RAW mode.</span></span>  
  
 `<row>4</row>`  
  
 <span data-ttu-id="abbf9-110">La consulta siguiente devuelve un conjunto de filas de tres columnas.</span><span class="sxs-lookup"><span data-stu-id="abbf9-110">The following query returns a three-column rowset.</span></span> <span data-ttu-id="abbf9-111">La tercera columna sin nombre incluye los datos XML.</span><span class="sxs-lookup"><span data-stu-id="abbf9-111">The third column without a name has XML data.</span></span> <span data-ttu-id="abbf9-112">El modo PATH inserta una instancia de tipo xml.</span><span class="sxs-lookup"><span data-stu-id="abbf9-112">The PATH mode inserts an instance of the xml type.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ;  
GO  
```  
  
 <span data-ttu-id="abbf9-113">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="abbf9-113">This is the partial result:</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location ...LocationID="10" ...></MI:Location>`  
  
 `<MI:Location ...LocationID="20" ...></MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="abbf9-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="abbf9-114">See Also</span></span>  
 [<span data-ttu-id="abbf9-115">Usar el modo PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="abbf9-115">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
