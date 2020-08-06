---
title: Modificar datos (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data [MDX]
- Multidimensional Expressions [Analysis Services], data modifications
- MDX [Analysis Services], data modifications
- data modifications [MDX]
ms.assetid: 363b662c-b839-4971-bbd7-1842f73ce141
author: minewiskan
ms.author: owend
ms.openlocfilehash: 01df67471753922e3e7db39c56a9ed50aae900dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673919"
---
# <a name="modifying-data-mdx"></a><span data-ttu-id="7b507-102">Modificar datos (MDX)</span><span class="sxs-lookup"><span data-stu-id="7b507-102">Modifying Data (MDX)</span></span>
  <span data-ttu-id="7b507-103">Además de usar las expresiones multidimensionales (MDX) para recuperar y administrar los datos de las dimensiones y los cubos, MDX también permite actualizar o *reescribir* los datos de las dimensiones y los cubos.</span><span class="sxs-lookup"><span data-stu-id="7b507-103">Besides using Multidimensional Expressions (MDX) to retrieve and handle data from dimensions and cubes, you can use MDX to update or *writeback* dimension and cube data.</span></span> <span data-ttu-id="7b507-104">Dichas actualizaciones pueden ser temporales, como los análisis especulativos o de escenarios condicionales, o permanentes (cuando los cambios se producen a partir del análisis de los datos).</span><span class="sxs-lookup"><span data-stu-id="7b507-104">These updates can be temporary, as with speculative, or "what if", analysis, or permanent, as when changes must occur based upon data analysis.</span></span>  
  
 <span data-ttu-id="7b507-105">La actualización de los datos puede realizarse en los niveles de dimensión o de cubo:</span><span class="sxs-lookup"><span data-stu-id="7b507-105">Updates to data can occur at the dimension or cube level:</span></span>  
  
 <span data-ttu-id="7b507-106">**Reescritura de dimensiones**</span><span class="sxs-lookup"><span data-stu-id="7b507-106">**Dimension writebacks**</span></span>  
 <span data-ttu-id="7b507-107">[ALTER CUBE (Instrucción, MDX)](/sql/mdx/mdx-data-definition-alter-cube) permite cambiar los datos de una dimensión habilitada para escritura y [REFRESH CUBE (Instrucción, MDX)](/sql/mdx/mdx-data-definition-refresh-cube) permite reflejar la eliminación, creación y actualización de los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="7b507-107">You use the [ALTER CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-alter-cube) statement to change a write-enabled dimension's data and the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to reflect the deletion, creation, and updating of attribute values.</span></span> <span data-ttu-id="7b507-108">La instrucción ALTER CUBE también se puede utilizar para realizar operaciones complejas como la eliminación de todo un subárbol de una jerarquía y la promoción de los elementos secundarios de un miembro eliminado.</span><span class="sxs-lookup"><span data-stu-id="7b507-108">You can also use the ALTER CUBE statement to perform complex operations, such as deleting a whole sub-tree in a hierarchy and promoting the children of a deleted member.</span></span>  
  
 <span data-ttu-id="7b507-109">**Reescritura de cubos**</span><span class="sxs-lookup"><span data-stu-id="7b507-109">**Cube writebacks**</span></span>  
 <span data-ttu-id="7b507-110">La instrucción [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) permite efectuar actualizaciones en un cubo habilitado para escritura.</span><span class="sxs-lookup"><span data-stu-id="7b507-110">You use the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement to make updates to a write-enabled cube.</span></span> <span data-ttu-id="7b507-111">Esta instrucción permite actualizar una tupla con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="7b507-111">The UPDATE CUBE statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="7b507-112">[REFRESH CUBE (Instrucción, MDX)](/sql/mdx/mdx-data-definition-refresh-cube) permite actualizar los datos de una sesión de cliente con datos actualizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="7b507-112">You use the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to refresh data in a client session with updated data from the server.</span></span>  
  
 <span data-ttu-id="7b507-113">Para más información, vea [Usar reescrituras de cubos &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span><span class="sxs-lookup"><span data-stu-id="7b507-113">For more information, see [Using Cube Writebacks &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b507-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b507-114">See Also</span></span>  
 [<span data-ttu-id="7b507-115">Aspectos básicos de las consultas MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7b507-115">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
