---
title: Marcadores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bookmarks [OLE DB]
- SQL Server Native Client OLE DB provider, bookmarks
- rowsets [OLE DB], bookmarks
- OLE DB rowsets, bookmarks
ms.assetid: 7d9076f2-bf9c-452e-b816-70371a0c1644
author: rothja
ms.author: jroth
ms.openlocfilehash: be8e5486e5a442ddafa133a9cbd3f408d30a50d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748748"
---
# <a name="bookmarks"></a><span data-ttu-id="b6eaf-102">Marcadores</span><span class="sxs-lookup"><span data-stu-id="b6eaf-102">Bookmarks</span></span>
  <span data-ttu-id="b6eaf-103">Los marcadores permiten a los consumidores volver rápidamente a una fila.</span><span class="sxs-lookup"><span data-stu-id="b6eaf-103">Bookmarks let consumers quickly return to a row.</span></span> <span data-ttu-id="b6eaf-104">Gracias a los marcadores, los consumidores pueden tener acceso de forma aleatoria a las filas en función del valor de marcador.</span><span class="sxs-lookup"><span data-stu-id="b6eaf-104">With bookmarks, consumers can access rows randomly based on the bookmark value.</span></span> <span data-ttu-id="b6eaf-105">La columna de marcador es la columna 0 en el conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="b6eaf-105">The bookmark column is column 0 in the rowset.</span></span> <span data-ttu-id="b6eaf-106">El consumidor establece el valor de campo dwFlag de la estructura de enlace en DBCOLUMNSINFO_ISBOOKMARK para indicar que la columna se utiliza de marcador.</span><span class="sxs-lookup"><span data-stu-id="b6eaf-106">The consumer sets the dwFlag field value of the binding structure to DBCOLUMNSINFO_ISBOOKMARK to indicate that the column is used as a bookmark.</span></span> <span data-ttu-id="b6eaf-107">El consumidor establece también la propiedad de conjunto de filas DBPROP_BOOKMARKS en VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="b6eaf-107">The consumer also sets the rowset property DBPROP_BOOKMARKS to VARIANT_TRUE.</span></span> <span data-ttu-id="b6eaf-108">Esto permite que la columna 0 esté presente en el conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="b6eaf-108">This lets column 0 be present in the rowset.</span></span> <span data-ttu-id="b6eaf-109">Después, se usa el método **IRowsetLocate::GetRowsAt** para capturar las filas, empezando por la fila especificada como desplazamiento desde un marcador.</span><span class="sxs-lookup"><span data-stu-id="b6eaf-109">The **IRowsetLocate::GetRowsAt** method is then used to fetch rows, starting with the row specified as an offset from a bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6eaf-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6eaf-110">See Also</span></span>  
 [<span data-ttu-id="b6eaf-111">Conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="b6eaf-111">Rowsets</span></span>](rowsets.md)  
  
  