---
title: Instrucciones y limitaciones de DiffGrams en SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: cf8689c4-2a63-4d05-b202-21b5ff187d7f
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f2901f02f8b4a8fc7b77dcb6c1cb166cb6af6ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673596"
---
# <a name="guidelines-and-limitations-of-diffgrams-in-sqlxml"></a><span data-ttu-id="70579-102">Instrucciones y limitaciones de DiffGrams en SQLXML</span><span class="sxs-lookup"><span data-stu-id="70579-102">Guidelines and Limitations of DiffGrams in SQLXML</span></span>
  <span data-ttu-id="70579-103">Recuerde lo siguiente al usar DiffGrams con SQLXML 4.0:</span><span class="sxs-lookup"><span data-stu-id="70579-103">Remember the following when using DiffGrams with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="70579-104">Los tipos de objeto binario de gran tamaño (BLOB) como `text/ntext` y las imágenes no se deben usar en el bloque `<diffgr:before>` al trabajar con DiffGrams, porque esto los incluiría para su uso en el control de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="70579-104">Binary large object (BLOB) types like `text/ntext` and images should not be used in the `<diffgr:before>` block in when working with DiffGrams, because this will include them for use in concurrency control.</span></span> <span data-ttu-id="70579-105">Esto puede producir problemas con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] debido a las limitaciones en la comparación para los tipos BLOB.</span><span class="sxs-lookup"><span data-stu-id="70579-105">This can cause problems with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="70579-106">Por ejemplo, la palabra clave LIKE se usa en la cláusula WHERE para comparar entre las columnas del tipo de datos `text`; sin embargo, se producirá un error en las comparaciones en el caso de los tipos BLOB donde el tamaño de los datos supere los 8 K.</span><span class="sxs-lookup"><span data-stu-id="70579-106">For example, the LIKE keyword is used in the WHERE clause for comparing between columns of the `text` data type; however, comparisons will fail in the case of BLOB types where the size of the data is greater than 8K.</span></span>  
  
-   <span data-ttu-id="70579-107">Los caracteres especiales en los datos `ntext` pueden producir problemas con SQLXML 4.0 debido a las limitaciones en la comparación para los tipos BLOB.</span><span class="sxs-lookup"><span data-stu-id="70579-107">Special characters in `ntext` data can cause problems with SQLXML 4.0 because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="70579-108">Por ejemplo, el uso de "[Serializable]" en el bloque `<diffgr:before>` de un DiffGram cuando se usa en la comprobación de simultaneidad de una columna de tipo `ntext` producirá un error con la descripción de error de SQLOLEDB siguiente:</span><span class="sxs-lookup"><span data-stu-id="70579-108">For example, the use of "[Serializable]" in the `<diffgr:before>` block of a DiffGram when used in concurrency checking of a column of `ntext` type will fail with the following SQLOLEDB error description:</span></span>  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
  
