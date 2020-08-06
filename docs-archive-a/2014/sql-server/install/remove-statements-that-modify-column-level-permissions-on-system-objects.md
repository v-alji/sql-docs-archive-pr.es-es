---
title: Quitar instrucciones que modifican permisos de nivel de columna en objetos del sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- column-level permissions [SQL Server]
- removed statement permissions [SQL Server]
ms.assetid: 7f4fbbef-2696-4911-903b-63f6d9e4484a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e55af3dca0c55c2babd09bc6cfc48ed0ddf3ad7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675145"
---
# <a name="remove-statements-that-modify-column-level-permissions-on-system-objects"></a><span data-ttu-id="df575-102">Eliminar instrucciones que modifican los permisos de nivel de columna en los objetos del sistema</span><span class="sxs-lookup"><span data-stu-id="df575-102">Remove statements that modify column-level permissions on system objects</span></span>
  <span data-ttu-id="df575-103">El Asesor de actualizaciones ha detectado permisos de nivel de columna no estándar en objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="df575-103">The Upgrade Advisor detected nonstandard column-level permissions on system objects.</span></span> <span data-ttu-id="df575-104">No se mantendrán estos cambios en los permisos cuando se lleve a cabo la actualización.</span><span class="sxs-lookup"><span data-stu-id="df575-104">These permission changes will not be maintained when you upgrade.</span></span> <span data-ttu-id="df575-105">Además, ya no se admite el uso de permisos de nivel de columna en objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="df575-105">Additionally, column-level permissions on system objects are no longer supported.</span></span> <span data-ttu-id="df575-106">Elimine aquellas instrucciones de sus aplicaciones que establezcan permisos de nivel de columna en objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="df575-106">Remove statements from your applications that set column-level permissions on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="df575-107">Componente</span><span class="sxs-lookup"><span data-stu-id="df575-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="df575-108">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="df575-108">Corrective Action</span></span>  
 <span data-ttu-id="df575-109">Elimine todas aquellas instrucciones de sus aplicaciones que concedan, denieguen o revoquen permisos de nivel de columna para objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="df575-109">Remove statements from your application that grant, deny, or revoke column-level permissions on system objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df575-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df575-110">See Also</span></span>  
 <span data-ttu-id="df575-111">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="df575-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="df575-112">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="df575-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
