---
title: Agente SQL Server categoría de trabajo de trasvase de registros causa un error de actualización | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
- job categories [SQL Server Agent]
ms.assetid: ef05ce53-c6ce-42ec-9df8-46c951626424
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2f5947e8fc8d459388fe35d86c75666e25b5d907
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751677"
---
# <a name="sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail"></a><span data-ttu-id="5099b-102">La categoría del trabajo de trasvase de registros del Agente SQL Server provoca errores en la actualización</span><span class="sxs-lookup"><span data-stu-id="5099b-102">SQL Server Agent log shipping job category causes upgrade to fail</span></span>
  <span data-ttu-id="5099b-103">Se producirá un error en el proceso de actualización si existe una categoría de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] denominada Trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="5099b-103">The upgrade process will fail if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category named Log Shipping exists.</span></span>  
  
## <a name="component"></a><span data-ttu-id="5099b-104">Componente</span><span class="sxs-lookup"><span data-stu-id="5099b-104">Component</span></span>  
 <span data-ttu-id="5099b-105">e[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5099b-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="5099b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5099b-106">Description</span></span>  
 <span data-ttu-id="5099b-107">Hay una categoría de trabajo de sistema denominada Trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="5099b-107">There is a system job category named Log Shipping.</span></span> <span data-ttu-id="5099b-108">Si una instalación que se está actualizando ya contiene una categoría de trabajo creada por el usuario denominada Trasvase de registros, deberá cambiar el nombre de dicha categoría antes de llevar a cabo la actualización; de lo contrario, se producirá un error en el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="5099b-108">If an installation that is being upgraded already contains a user-created job category named Log Shipping, you must rename the job category before you upgrade; otherwise, the upgrade process will fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5099b-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5099b-109">See Also</span></span>  
 <span data-ttu-id="5099b-110">[El trasvase de registros no se ejecutará después de la actualización](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md) </span><span class="sxs-lookup"><span data-stu-id="5099b-110">[Log shipping will not run after upgrading](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md) </span></span>  
 <span data-ttu-id="5099b-111">[La actualización cambiará la Agente SQL Server cuenta de proxy de usuario a la UpgradedProxyAccount temporal](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span><span class="sxs-lookup"><span data-stu-id="5099b-111">[Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span></span>  
 [<span data-ttu-id="5099b-112">Problemas de actualización del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="5099b-112">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
