---
title: Jerarquía de permisos (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.server.permissions.f1--May use common.permissions
helpviewer_keywords:
- security [SQL Server], denying access
- hierarchies [SQL Server], permissions
- securables [SQL Server]
- security [SQL Server], permissions
- permissions [SQL Server], hierarchy
- security [SQL Server], granting access
ms.assetid: f6d20a55-ef03-4e14-85f9-009902889866
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9a04e5595e509de63b362b31b240e113e635581d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745145"
---
# <a name="permissions-hierarchy-database-engine"></a><span data-ttu-id="9114d-102">Jerarquía de permisos (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="9114d-102">Permissions Hierarchy (Database Engine)</span></span>
  <span data-ttu-id="9114d-103">El [!INCLUDE[ssDE](../../../includes/ssde-md.md)] administra un conjunto jerárquico de entidades que se pueden proteger mediante permisos.</span><span class="sxs-lookup"><span data-stu-id="9114d-103">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] manages a hierarchical collection of entities that can be secured with permissions.</span></span> <span data-ttu-id="9114d-104">Estas entidades se conocen como *elementos protegibles*.</span><span class="sxs-lookup"><span data-stu-id="9114d-104">These entities are known as *securables*.</span></span> <span data-ttu-id="9114d-105">Los protegibles más prominentes son los servidores y las bases de datos, pero los permisos discretos se pueden establecer en un nivel mucho más específico.</span><span class="sxs-lookup"><span data-stu-id="9114d-105">The most prominent securables are servers and databases, but discrete permissions can be set at a much finer level.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9114d-106">regula las acciones de las entidades de seguridad en los elementos protegibles comprobando que se les ha concedido los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="9114d-106">regulates the actions of principals on securables by verifying that they have been granted appropriate permissions.</span></span>

 <span data-ttu-id="9114d-107">En la ilustración siguiente se muestran las relaciones entre las jerarquías de permisos del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9114d-107">The following illustration shows the relationships among the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions hierarchies.</span></span>

 <span data-ttu-id="9114d-108">![Diagrama de jerarquías de permisos del motor de base de datos](../../database-engine/media/wj-security-layers.gif "Diagrama de jerarquías de permisos del motor de base de datos")</span><span class="sxs-lookup"><span data-stu-id="9114d-108">![Diagram of Database Engine permissions hierarchies](../../database-engine/media/wj-security-layers.gif "Diagram of Database Engine permissions hierarchies")</span></span>

## <a name="chart-of-sql-server-permissions"></a><span data-ttu-id="9114d-109">Gráfico de los permisos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9114d-109">Chart of SQL Server Permissions</span></span>
 <span data-ttu-id="9114d-110">Para ver un gráfico de tamaño cartel de todos los permisos del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] en formato PDF, vea [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span><span class="sxs-lookup"><span data-stu-id="9114d-110">For a poster sized chart of all [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions in pdf format, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>

## <a name="working-with-permissions"></a><span data-ttu-id="9114d-111">Trabajar con permisos</span><span class="sxs-lookup"><span data-stu-id="9114d-111">Working with Permissions</span></span>
 <span data-ttu-id="9114d-112">Los permisos se pueden manipular con las conocidas consultas GRANT, DENY y REVOKE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9114d-112">Permissions can be manipulated with the familiar [!INCLUDE[tsql](../../includes/tsql-md.md)] queries GRANT, DENY, and REVOKE.</span></span> <span data-ttu-id="9114d-113">La información sobre los permisos está visible en las vistas de catálogo [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) y [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="9114d-113">Information about permissions is visible in the [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) and [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) catalog views.</span></span> <span data-ttu-id="9114d-114">También hay información sobre la compatibilidad con permisos para consultas mediante el uso de las funciones integradas.</span><span class="sxs-lookup"><span data-stu-id="9114d-114">There is also support for querying permissions information by using built-in functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="9114d-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9114d-115">See Also</span></span>
 <span data-ttu-id="9114d-116">[Proteger SQL Server](securing-sql-server.md) [permisos &#40;motor de base de datos&#41;entidades](permissions-database-engine.md) [protegibles](securables.md) [&#40;](authentication-access/principals-database-engine.md) motor de base de datos&#41;[Grant &#40;TRANSACT-](/sql/t-sql/statements/grant-transact-sql) sql&#41;[revocación &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) [Deny &#40;transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) [HAS_PERMS_BY_NAME &#40;transact-SQL&#41;](/sql/t-sql/functions/has-perms-by-name-transact-sql) [Sys. fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) [Sys. server_permissions &#40;Transact-](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) SQL&#41;[Sys. database_permissions &#40;Transact-](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9114d-116">[Securing SQL Server](securing-sql-server.md) [Permissions &#40;Database Engine&#41;](permissions-database-engine.md) [Securables](securables.md) [Principals &#40;Database Engine&#41;](authentication-access/principals-database-engine.md) [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) [HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/has-perms-by-name-transact-sql) [sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) [sys.server_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) [sys.database_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql)</span></span>


