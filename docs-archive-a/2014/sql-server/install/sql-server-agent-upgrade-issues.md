---
title: Problemas de actualización de Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server Agent
- SQL Server Agent, upgrades
ms.assetid: 77e303ff-febd-4103-ae5d-6e5b85bc8009
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ac234a757510af5ebfac261ea6d3e7e57d2f426f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746102"
---
# <a name="sql-server-agent-upgrade-issues"></a><span data-ttu-id="878ff-102">Problemas de actualización del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="878ff-102">SQL Server Agent Upgrade Issues</span></span>
  <span data-ttu-id="878ff-103">Los temas siguientes describen los problemas del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que pueden afectar a una actualización.</span><span class="sxs-lookup"><span data-stu-id="878ff-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent issues that might affect an upgrade.</span></span> <span data-ttu-id="878ff-104">Los temas describen acciones que se pueden llevar a cabo para reducir el efecto de estos cambios en el entorno de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="878ff-104">The topics describe actions that you can take to help reduce the effect of these changes on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="878ff-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="878ff-105">In This Section</span></span>  
  
-   [<span data-ttu-id="878ff-106">Se han reemplazado los planes de mantenimiento de bases de datos</span><span class="sxs-lookup"><span data-stu-id="878ff-106">Database maintenance plans superseded</span></span>](../../../2014/sql-server/install/database-maintenance-plans-superseded.md)  
  
-   [<span data-ttu-id="878ff-107">Los administradores del sistema son los únicos usuarios que pueden escribir archivos de registro de paso de trabajo en el sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="878ff-107">Only sysadmin users can write job step log files to the file system</span></span>](../../../2014/sql-server/install/only-sysadmin-users-can-write-job-step-log-files-to-the-file-system.md)  
  
-   [<span data-ttu-id="878ff-108">Reemplazar el uso del procedimiento almacenado extendido xp_sqlagent_proxy_account con nuevos procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="878ff-108">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>](../../../2014/sql-server/install/replace-xp-sqlagent-proxy-account-extended-sp-with-new-stored-procedures.md)  
  
-   [<span data-ttu-id="878ff-109">La categoría del trabajo de trasvase de registros del Agente SQL Server provoca errores en la actualización</span><span class="sxs-lookup"><span data-stu-id="878ff-109">SQL Server Agent log shipping job category causes upgrade to fail</span></span>](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md)  
  
-   [<span data-ttu-id="878ff-110">El servicio del Agente SQL Server no puede utilizar la autenticación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="878ff-110">SQL Server Agent Service cannot use SQL Server Authentication</span></span>](../../../2014/sql-server/install/sql-server-agent-service-cannot-use-sql-server-authentication.md)  
  
-   [<span data-ttu-id="878ff-111">Actualizar la sintaxis de tokens en los pasos de trabajo del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="878ff-111">Update token syntax in SQL Server Agent job steps</span></span>](../../../2014/sql-server/install/update-token-syntax-in-sql-server-agent-job-steps.md)  
  
-   [<span data-ttu-id="878ff-112">Actualizar todos los servidores de destino antes de actualizar el servidor maestro</span><span class="sxs-lookup"><span data-stu-id="878ff-112">Upgrade all target servers before upgrading the master server</span></span>](../../../2014/sql-server/install/upgrade-all-target-servers-before-upgrading-the-master-server.md)  
  
-   [<span data-ttu-id="878ff-113">La actualización cambiará la cuenta de proxy de usuario del Agente SQL Server a la cuenta temporal UpgradedProxyAccount</span><span class="sxs-lookup"><span data-stu-id="878ff-113">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md)  
  
## <a name="see-also"></a><span data-ttu-id="878ff-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="878ff-114">See Also</span></span>  
 <span data-ttu-id="878ff-115">[SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="878ff-115">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="878ff-116">Resolver problemas de la actualización</span><span class="sxs-lookup"><span data-stu-id="878ff-116">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
