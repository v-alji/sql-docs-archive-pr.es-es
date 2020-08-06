---
title: Elementos protegibles | Microsoft Docs
ms.custom: ''
ms.date: 10/14/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectobject.f1
helpviewer_keywords:
- securables [SQL Server]
- schemas [SQL Server], securables
- database securables [SQL Server]
- hierarchies [SQL Server], securables
- server securables [SQL Server]
ms.assetid: bfa748f0-70b0-453c-870a-04b7b205b9ff
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ff2aaba72e2e5489694d31b35e594622c099acab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745127"
---
# <a name="securables"></a><span data-ttu-id="4b78c-102">Elementos protegibles</span><span class="sxs-lookup"><span data-stu-id="4b78c-102">Securables</span></span>
  <span data-ttu-id="4b78c-103">Los elementos protegibles son los recursos cuyo acceso es regulado por el sistema de autorización del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b78c-103">Securables are the resources to which the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] authorization system regulates access.</span></span> <span data-ttu-id="4b78c-104">Por ejemplo, una tabla es un elemento protegible.</span><span class="sxs-lookup"><span data-stu-id="4b78c-104">For example, a table is a securable.</span></span> <span data-ttu-id="4b78c-105">Algunos elementos protegibles pueden estar incluidos en otros, con lo que se crean jerarquías anidadas denominadas "ámbitos" que a su vez se pueden proteger.</span><span class="sxs-lookup"><span data-stu-id="4b78c-105">Some securables can be contained within others, creating nested hierarchies called "scopes" that can themselves be secured.</span></span> <span data-ttu-id="4b78c-106">Los ámbitos protegibles son **servidor**, **base de datos**y **esquema**.</span><span class="sxs-lookup"><span data-stu-id="4b78c-106">The securable scopes are **server**, **database**, and **schema**.</span></span>  
  
## <a name="securable-scope-server"></a><span data-ttu-id="4b78c-107">Ámbito protegible: Server</span><span class="sxs-lookup"><span data-stu-id="4b78c-107">Securable scope: Server</span></span>  
 <span data-ttu-id="4b78c-108">El ámbito protegible **servidor** contiene los siguientes valores que puede proteger:</span><span class="sxs-lookup"><span data-stu-id="4b78c-108">The **server** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="4b78c-109">grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="4b78c-109">Availability group</span></span>  
  
-   <span data-ttu-id="4b78c-110">Punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4b78c-110">Endpoint</span></span>  
  
-   <span data-ttu-id="4b78c-111">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="4b78c-111">Login</span></span>  
  
-   <span data-ttu-id="4b78c-112">Rol de servidor</span><span class="sxs-lookup"><span data-stu-id="4b78c-112">Server role</span></span>  
  
-   <span data-ttu-id="4b78c-113">Base de datos</span><span class="sxs-lookup"><span data-stu-id="4b78c-113">Database</span></span>  
  
## <a name="securable-scope-database"></a><span data-ttu-id="4b78c-114">Ámbito protegible: Base de datos</span><span class="sxs-lookup"><span data-stu-id="4b78c-114">Securable scope: Database</span></span>  
 <span data-ttu-id="4b78c-115">El ámbito protegible **base de datos** contiene los siguientes valores que puede proteger:</span><span class="sxs-lookup"><span data-stu-id="4b78c-115">The **database** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="4b78c-116">Rol de aplicación</span><span class="sxs-lookup"><span data-stu-id="4b78c-116">Application role</span></span>  
  
-   <span data-ttu-id="4b78c-117">Assembly</span><span class="sxs-lookup"><span data-stu-id="4b78c-117">Assembly</span></span>  
  
-   <span data-ttu-id="4b78c-118">Clave asimétrica</span><span class="sxs-lookup"><span data-stu-id="4b78c-118">Asymmetric key</span></span>  
  
-   <span data-ttu-id="4b78c-119">Certificado</span><span class="sxs-lookup"><span data-stu-id="4b78c-119">Certificate</span></span>  
  
-   <span data-ttu-id="4b78c-120">Contrato</span><span class="sxs-lookup"><span data-stu-id="4b78c-120">Contract</span></span>  
  
-   <span data-ttu-id="4b78c-121">Catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="4b78c-121">Fulltext catalog</span></span>  
  
-   <span data-ttu-id="4b78c-122">Lista de palabras irrelevantes de texto completo</span><span class="sxs-lookup"><span data-stu-id="4b78c-122">Fulltext stoplist</span></span>  
  
-   <span data-ttu-id="4b78c-123">Tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="4b78c-123">Message type</span></span>  
  
-   <span data-ttu-id="4b78c-124">Enlace de servicio remoto</span><span class="sxs-lookup"><span data-stu-id="4b78c-124">Remote Service Binding</span></span>  
  
-   <span data-ttu-id="4b78c-125">(Base de datos) Rol</span><span class="sxs-lookup"><span data-stu-id="4b78c-125">(Database) Role</span></span>  
  
-   <span data-ttu-id="4b78c-126">Enrutar</span><span class="sxs-lookup"><span data-stu-id="4b78c-126">Route</span></span>  
  
-   <span data-ttu-id="4b78c-127">Schema</span><span class="sxs-lookup"><span data-stu-id="4b78c-127">Schema</span></span>  
  
-   <span data-ttu-id="4b78c-128">Lista de propiedades de búsqueda</span><span class="sxs-lookup"><span data-stu-id="4b78c-128">Search property list</span></span>  
  
-   <span data-ttu-id="4b78c-129">Servicio</span><span class="sxs-lookup"><span data-stu-id="4b78c-129">Service</span></span>  
  
-   <span data-ttu-id="4b78c-130">Clave simétrica</span><span class="sxs-lookup"><span data-stu-id="4b78c-130">Symmetric key</span></span>  
  
-   <span data-ttu-id="4b78c-131">Usuario</span><span class="sxs-lookup"><span data-stu-id="4b78c-131">User</span></span>  
  
## <a name="securable-scope-schema"></a><span data-ttu-id="4b78c-132">Ámbito protegible: Schema</span><span class="sxs-lookup"><span data-stu-id="4b78c-132">Securable scope: Schema</span></span>  
 <span data-ttu-id="4b78c-133">El ámbito protegible **esquema** contiene los siguientes valores que se pueden proteger:</span><span class="sxs-lookup"><span data-stu-id="4b78c-133">The **schema** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="4b78c-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="4b78c-134">Type</span></span>  
  
-   <span data-ttu-id="4b78c-135">Colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="4b78c-135">XML schema collection</span></span>  
  
-   <span data-ttu-id="4b78c-136">Objeto: la clase de objeto tiene los miembros siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b78c-136">Object - The object class has the following members:</span></span>  
  
    -   <span data-ttu-id="4b78c-137">Agregado</span><span class="sxs-lookup"><span data-stu-id="4b78c-137">Aggregate</span></span>  
  
    -   <span data-ttu-id="4b78c-138">Función</span><span class="sxs-lookup"><span data-stu-id="4b78c-138">Function</span></span>  
  
    -   <span data-ttu-id="4b78c-139">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="4b78c-139">Procedure</span></span>  
  
    -   <span data-ttu-id="4b78c-140">Cola</span><span class="sxs-lookup"><span data-stu-id="4b78c-140">Queue</span></span>  
  
    -   <span data-ttu-id="4b78c-141">Synonym (Sinónimo)</span><span class="sxs-lookup"><span data-stu-id="4b78c-141">Synonym</span></span>  
  
    -   <span data-ttu-id="4b78c-142">Tabla</span><span class="sxs-lookup"><span data-stu-id="4b78c-142">Table</span></span>  
  
    -   <span data-ttu-id="4b78c-143">Ver</span><span class="sxs-lookup"><span data-stu-id="4b78c-143">View</span></span>  
  
## <a name="controlling-access-to-a-securable"></a><span data-ttu-id="4b78c-144">Controlar el acceso a un elemento protegible</span><span class="sxs-lookup"><span data-stu-id="4b78c-144">Controlling Access to a Securable</span></span>  
 <span data-ttu-id="4b78c-145">La entidad que recibe el permiso para un elemento protegible se denomina "entidad de seguridad".</span><span class="sxs-lookup"><span data-stu-id="4b78c-145">The entity that receives permission to a securable is called a principal.</span></span> <span data-ttu-id="4b78c-146">Las entidades de seguridad más comunes son inicios de sesión y usuarios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4b78c-146">The most common principals are logins and database users.</span></span> <span data-ttu-id="4b78c-147">El acceso a elementos protegibles se controla mediante la concesión o denegación de permisos o añadiendo los inicios de sesión y el usuario a roles con acceso.</span><span class="sxs-lookup"><span data-stu-id="4b78c-147">Access to securables is controlled by granting or denying permissions, or by adding logins and user to roles which have access.</span></span> <span data-ttu-id="4b78c-148">Para obtener más información sobre cómo controlar los permisos, vea [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) y [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b78c-148">For information about controlling permissions, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql), and [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4b78c-149">Los permisos predeterminados que se conceden a objetos del sistema en el momento de la instalación se evalúan detenidamente frente a posibles amenazas y no necesitan modificarse como parte de la protección de la instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b78c-149">The default permissions that are granted to system objects at the time of setup are carefully evaluated against possible threats and need not be altered as part of hardening the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="4b78c-150">Los cambios a los permisos de los objetos del sistema podrían limitar o interrumpir la funcionalidad y dejar potencialmente a su instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en un estado no admitido.</span><span class="sxs-lookup"><span data-stu-id="4b78c-150">Any changes to the permissions on the system objects could limit or break the functionality and could potentially leave your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation in an unsupported state.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="4b78c-151">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="4b78c-151">Related Content</span></span>  
 [<span data-ttu-id="4b78c-152">Proteger SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b78c-152">Securing SQL Server</span></span>](securing-sql-server.md)  
  
 [<span data-ttu-id="4b78c-153">sys.database_principals &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b78c-153">sys.database_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql)  
  
 [<span data-ttu-id="4b78c-154">sys.database_role_members &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b78c-154">sys.database_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql)  
  
 [<span data-ttu-id="4b78c-155">sys.server_principals &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b78c-155">sys.server_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql)  
  
 [<span data-ttu-id="4b78c-156">sys.server_role_members &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b78c-156">sys.server_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-role-members-transact-sql)  
  
 [<span data-ttu-id="4b78c-157">sys.sql_logins &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b78c-157">sys.sql_logins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql)  
  
  
