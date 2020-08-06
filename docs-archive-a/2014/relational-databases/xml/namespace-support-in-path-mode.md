---
title: Compatibilidad con elementos de espacio de nombres en el modo PATH | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, namespace support
- namespaces [XML in SQL Server]
ms.assetid: 5f128ea2-0ceb-4b23-bce7-c8b3fd615466
author: rothja
ms.author: jroth
ms.openlocfilehash: abd6cd1f5590bffcd841b07897c9685faed4726f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744534"
---
# <a name="namespace-support-in-path-mode"></a><span data-ttu-id="c1a60-102">Compatibilidad con elementos de espacio de nombres en el modo PATH</span><span class="sxs-lookup"><span data-stu-id="c1a60-102">Namespace Support in PATH Mode</span></span>
  <span data-ttu-id="c1a60-103">Se incluye la compatibilidad con elementos de espacio de nombres en el modo PATH mediante WITH NAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="c1a60-103">Namespace support in the PATH mode is provided by using WITH NAMESPACES.</span></span> <span data-ttu-id="c1a60-104">Por ejemplo, la consulta siguiente muestra la sintaxis WITH NAMESPACES para declarar un espacio de nombres ("a:") que se puede usar a continuación en la instrucción SELECT posterior:</span><span class="sxs-lookup"><span data-stu-id="c1a60-104">For example, the following query demonstrates the WITH NAMESPACES syntax to declare a namespace ("a:") that can then be used in the subsequent SELECT statement:</span></span>  
  
```  
WITH XMLNAMESPACES('a' as a)  
SELECT 1 as 'a:b'  
FOR XML PATH  
```  
  
## <a name="examples"></a><span data-ttu-id="c1a60-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c1a60-105">Examples</span></span>  
 <span data-ttu-id="c1a60-106">Estas muestras ilustran la utilización del modo PATH en la creación de XML a partir de una consulta SELECT.</span><span class="sxs-lookup"><span data-stu-id="c1a60-106">These samples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="c1a60-107">Muchas de estas consultas se especifican usando los documentos XML de instrucciones de fabricación de bicicletas almacenados en la columna Instructions de la tabla ProductModel.</span><span class="sxs-lookup"><span data-stu-id="c1a60-107">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a60-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1a60-108">See Also</span></span>  
 [<span data-ttu-id="c1a60-109">Usar el modo PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="c1a60-109">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
