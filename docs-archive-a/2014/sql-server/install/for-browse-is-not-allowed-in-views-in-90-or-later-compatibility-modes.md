---
title: FOR BROWSE no se permite en vistas en los modos de compatibilidad 90 o posteriores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], FOR BROWSE clause
- FOR BROWSE clause
ms.assetid: 8f49b1c1-d877-4c46-b988-f8cdd8ac0925
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 251e0ae2ff6f19dfcff3b0f8056f6697c1bfc40d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675170"
---
# <a name="for-browse-is-not-allowed-in-views-in-90-or-later-compatibility-modes"></a><span data-ttu-id="8e1a5-102">No se permite FOR BROWSE en vistas en modo de compatibilidad 90 o posteriores</span><span class="sxs-lookup"><span data-stu-id="8e1a5-102">FOR BROWSE is not allowed in views in 90 or later compatibility modes</span></span>
  <span data-ttu-id="8e1a5-103">El Asesor de actualizaciones ha detectado el uso de la cláusula FOR BROWSE en una vista.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-103">Upgrade Advisor detected the use of the FOR BROWSE clause in a view.</span></span> <span data-ttu-id="8e1a5-104">Se permite el uso de la cláusula FOR BROWSE (pero no se tiene en cuenta) en las vistas cuando el modo de compatibilidad de la base de datos está establecido en 80.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-104">The FOR BROWSE clause is allowed (and ignored) in views when the database compatibility mode is set to 80.</span></span> <span data-ttu-id="8e1a5-105">No se permite el uso de la cláusula FOR BROWSE en las vistas cuando el modo de compatibilidad de la base de datos está establecido en 90 o más.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-105">The FOR BROWSE clause is not allowed in views when the database compatibility mode is set to 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="8e1a5-106">Componente</span><span class="sxs-lookup"><span data-stu-id="8e1a5-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="8e1a5-107">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="8e1a5-107">Corrective Action</span></span>  
 <span data-ttu-id="8e1a5-108">Cuando actualiza, las bases de datos de usuarios conservan su modo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-108">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="8e1a5-109">Antes de cambiar el modo de compatibilidad de la base de datos a 90 o más, elimine la cláusula FOR BROWSE de las definiciones de la vista.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-109">Before you change the database compatibility mode to 90 or later, remove the FOR BROWSE clause from view definitions.</span></span> <span data-ttu-id="8e1a5-110">Para obtener más información, vea "sp_dbcmptlevel" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e1a5-110">For more information, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e1a5-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e1a5-111">See Also</span></span>  
 <span data-ttu-id="8e1a5-112">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8e1a5-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="8e1a5-113">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="8e1a5-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
