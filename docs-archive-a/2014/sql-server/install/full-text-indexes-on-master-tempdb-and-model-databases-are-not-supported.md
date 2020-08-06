---
title: No se admiten los índices de texto completo en las bases de datos maestra, tempdb y modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: f7992965-42c1-4eb8-a7fb-afb38b67c740
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fbd5e3133ed87fed9bdaf6d668df62c6471df766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678038"
---
# <a name="full-text-indexes-on-master-tempdb-and-model-databases-are-not-supported"></a><span data-ttu-id="b6d1e-102">Los índices de texto completo no se admiten en bases de datos maestras, tempdb ni modelo</span><span class="sxs-lookup"><span data-stu-id="b6d1e-102">Full-text indexes on master, tempdb and model databases are not supported</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b6d1e-103">no admite índices de texto completo en ninguna base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="b6d1e-103">does not allow full-text indexes on any system database.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b6d1e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6d1e-104">Description</span></span>  
 <span data-ttu-id="b6d1e-105">En [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], se admitían índices de texto completo en las bases de datos maestras, tempdb y modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d1e-105">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], full-text indexes were supported on the master, tempdb, and model databases.</span></span>  
  
 <span data-ttu-id="b6d1e-106">Los catálogos de texto completo de las bases de datos maestra, tempdb y modelo se quitan durante la actualización.</span><span class="sxs-lookup"><span data-stu-id="b6d1e-106">Any full-text catalogs in the master, tempdb, and model databases are removed during the upgrade.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d1e-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6d1e-107">See Also</span></span>  
 [<span data-ttu-id="b6d1e-108">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="b6d1e-108">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
