---
title: MSSQL_ENG021797 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021797 error
ms.assetid: 54d83a1e-43fd-449c-a2b2-fdda2609a534
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d33ade7e7eea9fa9e95453a5b232447f7b222b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745205"
---
# <a name="mssql_eng021797"></a><span data-ttu-id="f59aa-102">MSSQL_ENG021797</span><span class="sxs-lookup"><span data-stu-id="f59aa-102">MSSQL_ENG021797</span></span>
    
## <a name="message-details"></a><span data-ttu-id="f59aa-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="f59aa-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f59aa-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="f59aa-104">Product Name</span></span>|<span data-ttu-id="f59aa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f59aa-105">SQL Server</span></span>|  
|<span data-ttu-id="f59aa-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f59aa-106">Event ID</span></span>|<span data-ttu-id="f59aa-107">21797</span><span class="sxs-lookup"><span data-stu-id="f59aa-107">21797</span></span>|  
|<span data-ttu-id="f59aa-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="f59aa-108">Event Source</span></span>|<span data-ttu-id="f59aa-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f59aa-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f59aa-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f59aa-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="f59aa-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f59aa-111">Symbolic Name</span></span>||  
|<span data-ttu-id="f59aa-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f59aa-112">Message Text</span></span>|<span data-ttu-id="f59aa-113">"%s" debe ser un inicio de sesión de Windows válido en el formato: "MACHINE\Login" o "DOMAIN\Login".</span><span class="sxs-lookup"><span data-stu-id="f59aa-113">'%s' must be a valid Windows Login in the form: 'MACHINE\Login' or 'DOMAIN\Login'.</span></span> <span data-ttu-id="f59aa-114">Vea la documentación de '%s'.</span><span class="sxs-lookup"><span data-stu-id="f59aa-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f59aa-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="f59aa-115">Explanation</span></span>  
 <span data-ttu-id="f59aa-116">Este error lo generan los siguientes procedimientos almacenados de replicación si el valor especificado para el **@job_login** parámetro es null o no es válido.</span><span class="sxs-lookup"><span data-stu-id="f59aa-116">This error is raised by the following replication stored procedures if the value specified for the **@job_login** parameter is null or not valid.</span></span> <span data-ttu-id="f59aa-117">Este error puede producirse si un miembro del rol fijo de base de datos **db_owner** ejecuta scripts de versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f59aa-117">This error can occur if a member of the **db_owner** fixed database role runs scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f59aa-118">El modelo de seguridad de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]ha cambiado, por lo que dichos scripts deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="f59aa-118">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   [<span data-ttu-id="f59aa-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f59aa-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql)  
  
-   [<span data-ttu-id="f59aa-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f59aa-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql)  
  
-   [<span data-ttu-id="f59aa-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f59aa-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql)  
  
-   [<span data-ttu-id="f59aa-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f59aa-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="f59aa-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f59aa-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="f59aa-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f59aa-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="f59aa-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f59aa-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepullsubscription-agent-transact-sql)  
  
 <span data-ttu-id="f59aa-126">Estos procedimientos almacenados pueden ser ejecutados por un miembro del rol fijo de servidor **sysadmin** del servidor correspondiente o por un miembro del rol fijo de base de datos **db_owner** de la base de datos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f59aa-126">These stored procedures can be executed by a member of the **sysadmin** fixed server role on the appropriate server or a member of the **db_owner** fixed database role in the appropriate database.</span></span> <span data-ttu-id="f59aa-127">Cada uno de los procedimientos almacenados crea un trabajo de agente y permite especificar la cuenta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con la que se ejecuta el agente.</span><span class="sxs-lookup"><span data-stu-id="f59aa-127">The stored procedures each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="f59aa-128">Para los usuarios del rol **sysadmin** , los trabajos de agente se crean de forma implícita, aun cuando no se especifique ninguna cuenta de Windows (si se especifica una cuenta, ésta debe ser válida); los agentes se ejecutan en el contexto de la cuenta de servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el servidor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f59aa-128">For users in the **sysadmin** role, agent jobs are created implicitly even if a Windows account is not specified (if an account is specified, it must be valid); agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the appropriate server.</span></span> <span data-ttu-id="f59aa-129">Aunque la cuenta no es necesaria, por motivos de seguridad se recomienda especificar una cuenta independiente para los agentes.</span><span class="sxs-lookup"><span data-stu-id="f59aa-129">Although the account is not required, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="f59aa-130">Para más información, consulte [Modelo de seguridad del agente de replicación](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="f59aa-130">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f59aa-131">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f59aa-131">User Action</span></span>  
 <span data-ttu-id="f59aa-132">Asegúrese de especificar una cuenta de Windows válida para el **@job_login** parámetro de cada procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f59aa-132">Ensure you specify a valid Windows account for the **@job_login** parameter of each procedure.</span></span> <span data-ttu-id="f59aa-133">Si tiene scripts de replicación de versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], actualice dichos scripts para incluir los procedimientos almacenados y los parámetros requeridos por [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f59aa-133">If you have replication scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="f59aa-134">Para obtener más información, vea [Actualizar scripts de replicación &#40;programación de la replicación con Transact-SQL&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="f59aa-134">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f59aa-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f59aa-135">See Also</span></span>  
 [<span data-ttu-id="f59aa-136">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="f59aa-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
