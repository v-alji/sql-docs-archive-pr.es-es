---
title: Usar la opción BINARY BASE64 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, BINARY BASE64 option
ms.assetid: 86a7bb85-7f83-412a-b775-d2c379702fe9
author: rothja
ms.author: jroth
ms.openlocfilehash: 090d6a91ee56707a4eb1d545aa5a05bc25999fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748675"
---
# <a name="use-the-binary-base64-option"></a><span data-ttu-id="ac760-102">Usar la opción BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="ac760-102">Use the BINARY BASE64 Option</span></span>
  <span data-ttu-id="ac760-103">Si en la consulta se especifica la opción BINARY BASE64, los datos binarios se devuelven en formato de codificación en base64.</span><span class="sxs-lookup"><span data-stu-id="ac760-103">If the BINARY BASE64 option is specified in the query, the binary data is returned in base64 encoding format.</span></span> <span data-ttu-id="ac760-104">De manera predeterminada, si no se especifica la opción BINARY BASE64, el modo AUTO admite la codificación URL de datos binarios.</span><span class="sxs-lookup"><span data-stu-id="ac760-104">By default, if the BINARY BASE64 option is not specified, AUTO mode supports URL encoding of binary data.</span></span> <span data-ttu-id="ac760-105">Es decir, en lugar de datos binarios, se devuelve una referencia a una dirección URL relativa a la raíz virtual de la base de datos donde se ejecutó la consulta.</span><span class="sxs-lookup"><span data-stu-id="ac760-105">That is, instead of binary data, a reference to a relative URL to the virtual root of the database where the query was executed is returned.</span></span> <span data-ttu-id="ac760-106">Esta referencia se puede utilizar para obtener acceso a los datos binarios reales en operaciones posteriores mediante la consulta dbobject SQLXML ISAPI.</span><span class="sxs-lookup"><span data-stu-id="ac760-106">This reference can be used to access the actual binary data in subsequent operations by using the SQLXML ISAPI dbobject query.</span></span> <span data-ttu-id="ac760-107">La consulta debe proporcionar suficiente información, como las columnas de clave principal, para identificar la imagen.</span><span class="sxs-lookup"><span data-stu-id="ac760-107">The query must provide enough information, such as primary key columns, to identify the image.</span></span>  
  
 <span data-ttu-id="ac760-108">Al especificar una consulta, si se utiliza un alias para la columna binaria de la vista, se devuelve el alias en la codificación URL de los datos binarios.</span><span class="sxs-lookup"><span data-stu-id="ac760-108">In specifying a query, if an alias is used for the binary column of the view, the alias is returned in the URL encoding of the binary data.</span></span> <span data-ttu-id="ac760-109">En operaciones posteriores, el alias no tiene ningún significado y no es posible utilizar la codificación de dirección URL para recuperar la imagen.</span><span class="sxs-lookup"><span data-stu-id="ac760-109">In subsequent operations, the alias is meaningless, and the URL encoding cannot be used to retrieve the image.</span></span> <span data-ttu-id="ac760-110">Por consiguiente, no utilice alias si consulta una vista con el modo FOR XML AUTO.</span><span class="sxs-lookup"><span data-stu-id="ac760-110">Therefore, do not use aliases when querying a view using FOR XML AUTO mode.</span></span>  
  
 <span data-ttu-id="ac760-111">Por ejemplo, en una consulta SELECT, la conversión de una columna en un objeto binario grande (BLOB) convierte a la columna en una entidad temporal en la que pierde su nombre asociado de tabla y de columna.</span><span class="sxs-lookup"><span data-stu-id="ac760-111">For example, in a SELECT query, casting any column to a binary large object (BLOB) makes it a temporary entity in that it loses its associated table name and column name.</span></span> <span data-ttu-id="ac760-112">Esto hace que las consultas en modo AUTO generen un error, ya que no sabe dónde colocar este valor en la jerarquía XML.</span><span class="sxs-lookup"><span data-stu-id="ac760-112">This causes AUTO mode queries to generate an error, because it does not know where to put this value in the XML hierarchy.</span></span> <span data-ttu-id="ac760-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ac760-113">For example:</span></span>  
  
```  
CREATE TABLE MyTable (Col1 int PRIMARY KEY, Col2 binary)  
INSERT INTO MyTable VALUES (1, 0x7);  
```  
  
 <span data-ttu-id="ac760-114">Esta consulta produce un error debido a la conversión en un objeto binario grande (BLOB):</span><span class="sxs-lookup"><span data-stu-id="ac760-114">This query produces an error, because of the casting to a binary large object (BLOB):</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO;  
```  
  
 <span data-ttu-id="ac760-115">La solución consiste en agregar la opción BINARY BASE64 a la cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="ac760-115">The solution is to add the BINARY BASE64 option to the FOR XML clause.</span></span> <span data-ttu-id="ac760-116">Si se quita la conversión, la consulta produce los resultados esperados:</span><span class="sxs-lookup"><span data-stu-id="ac760-116">If you remove the casting, the query produces the results as expected:</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO, BINARY BASE64;  
```  
  
 <span data-ttu-id="ac760-117">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac760-117">This is the result:</span></span>  
  
```  
<MyTable Col1="1" Col2="Bw==" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac760-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac760-118">See Also</span></span>  
 [<span data-ttu-id="ac760-119">Usar el modo AUTO con FOR XML</span><span class="sxs-lookup"><span data-stu-id="ac760-119">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
