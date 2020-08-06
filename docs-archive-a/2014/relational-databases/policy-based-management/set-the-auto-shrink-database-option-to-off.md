---
title: Establecer la opción de base de datos AUTO_SHRINK en OFF | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 16403850-d745-4754-b84f-5f01aaecd24e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 42d79ed13a691c3d39a28e7ab35a740a9f613fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749742"
---
# <a name="set-the-auto_shrink-database-option-to-off"></a><span data-ttu-id="431b9-102">Establecer la opción de base de datos AUTO_SHRINK en OFF</span><span class="sxs-lookup"><span data-stu-id="431b9-102">Set the AUTO_SHRINK Database Option to OFF</span></span>
  <span data-ttu-id="431b9-103">Esta regla comprueba si la opción de base de datos AUTO_SHRINK está establecida en OFF.</span><span class="sxs-lookup"><span data-stu-id="431b9-103">This rule checks whether the AUTO_SHRINK database option is set to OFF.</span></span> <span data-ttu-id="431b9-104">Si se reduce y se expande con frecuencia una base de datos, puede provocar la fragmentación física.</span><span class="sxs-lookup"><span data-stu-id="431b9-104">Frequently shrinking and expanding a database can lead to physical fragmentation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="431b9-105">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="431b9-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="431b9-106">Establezca la opción de base de datos AUTO_SHRINK en OFF.</span><span class="sxs-lookup"><span data-stu-id="431b9-106">Set the AUTO_SHRINK database option to OFF.</span></span> <span data-ttu-id="431b9-107">Si sabe que el espacio que está reclamando no se va a necesitar en el futuro, puede reclamarlo reduciendo manualmente la base de datos.</span><span class="sxs-lookup"><span data-stu-id="431b9-107">If you know that the space that you are reclaiming will not be needed in the future, you can reclaim the space by manually shrinking the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="431b9-108">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="431b9-108">For More Information</span></span>  
 <span data-ttu-id="431b9-109">Artículo [315512](https://go.microsoft.com/fwlink/?linkid=117750)de Microsoft Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="431b9-109">Microsoft Knowledge Base article [315512](https://go.microsoft.com/fwlink/?linkid=117750)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="431b9-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="431b9-110">See Also</span></span>  
 [<span data-ttu-id="431b9-111">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="431b9-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
