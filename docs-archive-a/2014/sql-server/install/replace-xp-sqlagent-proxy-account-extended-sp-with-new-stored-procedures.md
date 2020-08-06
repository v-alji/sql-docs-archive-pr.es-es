---
title: Reemplazar el uso del procedimiento almacenado extendido xp_sqlagent_proxy_account por los procedimientos almacenados nuevos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- xp_sqlagent_proxy_account
ms.assetid: 0e3cc931-6237-41dd-bf0d-0c03f4d8fff2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d124ab73f4b4315550134f28ffad232b4a1c0ec2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675132"
---
# <a name="replace-usage-of-the-xp_sqlagent_proxy_account-extended-stored-procedure-with-new-stored-procedures"></a><span data-ttu-id="9a591-102">Reemplazar el uso del procedimiento almacenado extendido xp_sqlagent_proxy_account con nuevos procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="9a591-102">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>
  <span data-ttu-id="9a591-103">El Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite varios servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="9a591-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent supports multiple proxies.</span></span> <span data-ttu-id="9a591-104">Puede definir estos servidores proxy utilizando un nuevo conjunto de procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="9a591-104">You define these proxies by using a new set of stored procedures.</span></span> <span data-ttu-id="9a591-105">Para obtener más información sobre los nuevos procedimientos almacenados del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea los temas siguientes en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9a591-105">For more information about the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   <span data-ttu-id="9a591-106">"sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-106">"sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="9a591-107">"sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-107">"sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="9a591-108">"sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-108">"sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="9a591-109">"sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-109">"sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="9a591-110">"sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-110">"sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="9a591-111">"sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-111">"sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="9a591-112">"sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-112">"sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="9a591-113">"sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-113">"sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="9a591-114">"sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-114">"sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="9a591-115">"sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-115">"sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="9a591-116">"sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="9a591-116">"sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a591-117">Después de actualizar a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , no funcionarán las instrucciones que utilicen el **xp_sqlagent_proxy_account** procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="9a591-117">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], any statements that use the **xp_sqlagent_proxy_account** extended stored procedure will not work.</span></span> <span data-ttu-id="9a591-118">Use **sp_xp_cmdshell_proxy_account** en lugar de **xp_sqlagent_proxy_account** para establecer el proxy para **xp_cmdshell**.</span><span class="sxs-lookup"><span data-stu-id="9a591-118">Use **sp_xp_cmdshell_proxy_account** instead of **xp_sqlagent_proxy_account** to set the proxy for **xp_cmdshell**.</span></span>  
  
## <a name="component"></a><span data-ttu-id="9a591-119">Componente</span><span class="sxs-lookup"><span data-stu-id="9a591-119">Component</span></span>  
 <span data-ttu-id="9a591-120">e[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a591-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a591-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a591-121">See Also</span></span>  
 [<span data-ttu-id="9a591-122">Problemas de actualización del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a591-122">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
