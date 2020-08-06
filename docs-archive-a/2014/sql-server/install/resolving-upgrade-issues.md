---
title: Resolver problemas de actualización | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Upgrade Advisor [SQL Server], reference
- component issue resolution [Upgrade Advisor]
- resolving upgrade issues
- upgrade blocks [Upgrade Advisor]
- detecting upgrade issues
- finding upgrade issues
- Upgrade Advisor [SQL Server], blocking issues
- configurations preventing upgrading [Upgrade Advisor]
- locating upgrade issues
- blocking issues [Upgrade Advisor]
- issues preventing upgrading [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, reference
- analyzing system [Upgrade Advisor], resolving issues
- settings preventing upgrading [Upgrade Advisor]
- upgrade issue reference [Upgrade Advisor]
- identifying upgrade issues
- fixing upgrade issues [Upgrade Advisor]
ms.assetid: 113eb435-8d36-4ed6-9790-b5e4c14809c8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c00b08d40bc8c17013e6af19b5d11b0b7ad78c4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677384"
---
# <a name="resolving-upgrade-issues"></a><span data-ttu-id="25747-102">Resolver problemas de la actualización</span><span class="sxs-lookup"><span data-stu-id="25747-102">Resolving Upgrade Issues</span></span>
  <span data-ttu-id="25747-103">En los temas de esta sección se describen problemas de actualización que se pueden detectar, así como los que no se pueden detectar, pero que podrían afectar a la actualización o al uso de la aplicación tras su actualización.</span><span class="sxs-lookup"><span data-stu-id="25747-103">The topics in this section describe upgrade issues that can be detected as well as those that cannot be detected, but that might affect the upgrade or post-upgrade experience.</span></span> <span data-ttu-id="25747-104">Los problemas se han organizado por componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25747-104">The issues are organized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25747-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="25747-105">In This Section</span></span>  
  
-   [<span data-ttu-id="25747-106">Problemas de actualización de última hora</span><span class="sxs-lookup"><span data-stu-id="25747-106">Late-Breaking Upgrade Issues</span></span>](../../../2014/sql-server/install/late-breaking-upgrade-issues.md)  
  
-   [<span data-ttu-id="25747-107">Problemas de actualización del motor de la base de datos</span><span class="sxs-lookup"><span data-stu-id="25747-107">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
-   [<span data-ttu-id="25747-108">Problema de actualización de búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="25747-108">Full-Text Search Upgrade Issues</span></span>](../../../2014/sql-server/install/full-text-search-upgrade-issues.md)  
  
-   [<span data-ttu-id="25747-109">Problemas de actualización de replicación</span><span class="sxs-lookup"><span data-stu-id="25747-109">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
-   [<span data-ttu-id="25747-110">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="25747-110">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
-   [<span data-ttu-id="25747-111">Problemas de actualización del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="25747-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
## <a name="issues-that-prevent-upgrading"></a><span data-ttu-id="25747-112">Problemas que impiden la actualización</span><span class="sxs-lookup"><span data-stu-id="25747-112">Issues That Prevent Upgrading</span></span>  
 <span data-ttu-id="25747-113">Algunas configuraciones o valores de una versión anterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueden impedir que se realice la actualización a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25747-113">A few configurations or settings in a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="25747-114">Si el programa de instalación detecta estos problemas cuando instala [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], detiene el proceso de actualización y le pide que ejecute el Asesor de actualizaciones para corregir cualquier problema de bloqueos.</span><span class="sxs-lookup"><span data-stu-id="25747-114">If Setup detects these issues when you install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Setup stops the upgrade process and requests that you run Upgrade Advisor and fix any blocking issues.</span></span>  
  
### [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
 <span data-ttu-id="25747-115">Si aparecen las siguientes tareas en el informe de actualización de [!INCLUDE[ssDE](../../includes/ssde-md.md)], deberá llevar a cabo las acciones necesarias antes de actualizar a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="25747-115">If the following tasks are listed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)] upgrade report, you must perform the required actions before you upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]:</span></span>  
  
-   [<span data-ttu-id="25747-116">Desasociar la base de datos ID 32767</span><span class="sxs-lookup"><span data-stu-id="25747-116">Detach database ID 32767</span></span>](../../../2014/sql-server/install/detach-database-id-32767.md)  
  
-   [<span data-ttu-id="25747-117">Cambiar el nombre de los inicios de sesión que coinciden con nombres de roles fijos de servidor</span><span class="sxs-lookup"><span data-stu-id="25747-117">Rename logins matching fixed server role names</span></span>](../../../2014/sql-server/install/rename-logins-matching-fixed-server-role-names.md)  
  
-   [<span data-ttu-id="25747-118">Cambiar el nombre de usuario del sistema</span><span class="sxs-lookup"><span data-stu-id="25747-118">Rename user sys</span></span>](../../../2014/sql-server/install/rename-user-sys.md)  
  
-   [<span data-ttu-id="25747-119">Utilizar sp_rename para cambiar el nombre de índice duplicado</span><span class="sxs-lookup"><span data-stu-id="25747-119">Use sp_rename to rename duplicate index name</span></span>](../../../2014/sql-server/install/use-sp-rename-to-rename-duplicate-index-name.md)  
  
## <a name="see-also"></a><span data-ttu-id="25747-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25747-120">See Also</span></span>  
 [<span data-ttu-id="25747-121">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="25747-121">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
