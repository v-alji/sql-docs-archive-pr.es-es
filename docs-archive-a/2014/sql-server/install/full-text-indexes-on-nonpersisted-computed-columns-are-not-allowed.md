---
title: No se permiten índices de texto completo en columnas calculadas no persistentes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: cba737f7-b187-47d0-8458-23dc18d18aca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: de153d45e2f652bfea6e9dce68428af84be68b6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678037"
---
# <a name="full-text-indexes-on-nonpersisted-computed-columns-are-not-allowed"></a><span data-ttu-id="1b7f7-102">Los índices de texto completo no están permitidos en columnas calculadas no persistentes</span><span class="sxs-lookup"><span data-stu-id="1b7f7-102">Full-text indexes on nonpersisted, computed columns are not allowed</span></span>
  <span data-ttu-id="1b7f7-103">No puede crear índices de texto completo en columnas calculadas no deterministas e imprecisas.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-103">You cannot create full-text indexes on nondeterministic and imprecise computed columns.</span></span> <span data-ttu-id="1b7f7-104">Estas columnas no se pueden usar como columnas de tipo o de clave de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-104">Such columns cannot be used as type columns or as full-text key columns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1b7f7-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b7f7-105">Description</span></span>  
 <span data-ttu-id="1b7f7-106">En [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], se puede crear un índice de texto completo utilizando una columna calculada imprecisa y no determinista como columna de tipo o como columna de clave de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-106">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a full-text index can be created by using a nondeterministic and imprecise computed column as the type column or the full-text key column.</span></span> <span data-ttu-id="1b7f7-107">No se admite esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-107">This functionality is not supported.</span></span> <span data-ttu-id="1b7f7-108">Al actualizar, quedarán deshabilitados los índices de texto completo antiguos, incompatibles o no admitidos.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-108">When you upgrade, older, incompatible, and unsupported full-text indexes are disabled.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="1b7f7-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="1b7f7-109">Corrective Action</span></span>  
 <span data-ttu-id="1b7f7-110">Para habilitar estos índices de texto completo, modifique las definiciones de las columnas para que estas sean precisas y deterministas.</span><span class="sxs-lookup"><span data-stu-id="1b7f7-110">To enable these full-text indexes, modify the column definitions so that the columns are deterministic and precise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b7f7-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b7f7-111">See Also</span></span>  
 [<span data-ttu-id="1b7f7-112">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="1b7f7-112">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
