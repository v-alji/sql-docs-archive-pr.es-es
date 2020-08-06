---
title: La actualización cambiará la Agente SQL Server cuenta de proxy de usuario a la UpgradedProxyAccount temporal | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
ms.assetid: cd2d08c3-4e56-4034-8b68-0c78df8b5471
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2bca80580a50f2acebed1b6fbea2dec1f6458dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662490"
---
# <a name="upgrading-will-change-the-sql-server-agent-user-proxy-account-to-the-temporary-upgradedproxyaccount"></a><span data-ttu-id="fee24-102">La actualización cambiará la cuenta de proxy de usuario del Agente SQL Server a la cuenta temporal UpgradedProxyAccount</span><span class="sxs-lookup"><span data-stu-id="fee24-102">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>
  <span data-ttu-id="fee24-103">Los planes de mantenimiento de bases de datos que tengan habilitado el trasvase de registros no estarán habilitados tras la actualización.</span><span class="sxs-lookup"><span data-stu-id="fee24-103">Database maintenance plans that have log shipping enabled will not be enabled after upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="fee24-104">Componente</span><span class="sxs-lookup"><span data-stu-id="fee24-104">Component</span></span>  
 <span data-ttu-id="fee24-105">e[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fee24-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="fee24-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fee24-106">Description</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fee24-107">proporciona un conjunto nuevo de funciones de trasvase de registros que no son directamente compatibles con los planes de mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="fee24-107">provides a new set of log shipping functions that are not directly compatible with database maintenance plans.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="fee24-108">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="fee24-108">Corrective Action</span></span>  
 <span data-ttu-id="fee24-109">Los usuarios de [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] que tienen planes de mantenimiento de bases de datos que contienen funciones de trasvase de registros deberían configurar el trasvase de registros utilizando las nuevas funciones.</span><span class="sxs-lookup"><span data-stu-id="fee24-109">[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] users that have database maintenance plans that contain log shipping functions should configure log shipping by using the new functions.</span></span> <span data-ttu-id="fee24-110">Para obtener más información, busque "trasvase de registros" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fee24-110">For more information, search on "log shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee24-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fee24-111">See Also</span></span>  
 <span data-ttu-id="fee24-112">[Agente SQL Server categoría de trabajo de trasvase de registros causa un error en la actualización](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span><span class="sxs-lookup"><span data-stu-id="fee24-112">[SQL Server Agent log shipping job category causes upgrade to fail](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span></span>  
 [<span data-ttu-id="fee24-113">El trasvase de registros no se ejecutará tras la actualización</span><span class="sxs-lookup"><span data-stu-id="fee24-113">Log shipping will not run after upgrading</span></span>](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md)  
  
  
