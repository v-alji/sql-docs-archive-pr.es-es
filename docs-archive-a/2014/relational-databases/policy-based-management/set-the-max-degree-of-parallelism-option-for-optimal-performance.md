---
title: Establecer la opción Grado máximo de paralelismo para lograr un rendimiento óptimo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: ec908006-67ae-4674-9a61-25ea741d6197
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3043a656cbe1ac1ec40f0d0a67b6eac057005af4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749746"
---
# <a name="set-the-max-degree-of-parallelism-option-for-optimal-performance"></a><span data-ttu-id="2b057-102">Establecer la opción Grado máximo de paralelismo para lograr un rendimiento óptimo</span><span class="sxs-lookup"><span data-stu-id="2b057-102">Set the Max Degree of Parallelism Option for Optimal Performance</span></span>
  <span data-ttu-id="2b057-103">Esta regla determina si la opción Grado máximo de paralelismo (MAXDOP) tiene un valor mayor que 8.</span><span class="sxs-lookup"><span data-stu-id="2b057-103">This rule determines whether the max degree of parallelism (MAXDOP) option for a value greater than 8.</span></span> <span data-ttu-id="2b057-104">Establecer esta opción en un valor mayor a menudo causa un consumo de recursos no deseado y la degradación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2b057-104">Setting this option to a larger value often causes unwanted resource consumption and performance degradation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="2b057-105">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="2b057-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="2b057-106">Establezca la opción Grado máximo de paralelismo en 8, o menos, utilizando sp_configure.</span><span class="sxs-lookup"><span data-stu-id="2b057-106">Set the max degree of parallelism option to 8 or less by using sp_configure.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="2b057-107">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="2b057-107">For More Information</span></span>  
 [<span data-ttu-id="2b057-108">Artículo 329204 de Microsoft Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="2b057-108">Microsoft Knowledge Base article 329204</span></span>](https://go.microsoft.com/fwlink/?linkid=117786)  
  
 [<span data-ttu-id="2b057-109">Establecer la opción de configuración del servidor Grado máximo de paralelismo</span><span class="sxs-lookup"><span data-stu-id="2b057-109">Configure the max degree of parallelism Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md)  
  
 [<span data-ttu-id="2b057-110">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2b057-110">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
