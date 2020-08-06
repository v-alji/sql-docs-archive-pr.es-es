---
title: MSSQL_ENG021798 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021798 error
ms.assetid: 596f5092-75ab-4a19-8582-588687c7b089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 327b4a373c28376701ea12400215ab00367df66a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745203"
---
# <a name="mssql_eng021798"></a><span data-ttu-id="225e6-102">MSSQL_ENG021798</span><span class="sxs-lookup"><span data-stu-id="225e6-102">MSSQL_ENG021798</span></span>
    
## <a name="message-details"></a><span data-ttu-id="225e6-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="225e6-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="225e6-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="225e6-104">Product Name</span></span>|<span data-ttu-id="225e6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="225e6-105">SQL Server</span></span>|  
|<span data-ttu-id="225e6-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="225e6-106">Event ID</span></span>|<span data-ttu-id="225e6-107">21798</span><span class="sxs-lookup"><span data-stu-id="225e6-107">21798</span></span>|  
|<span data-ttu-id="225e6-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="225e6-108">Event Source</span></span>|<span data-ttu-id="225e6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="225e6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="225e6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="225e6-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="225e6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="225e6-111">Symbolic Name</span></span>||  
|<span data-ttu-id="225e6-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="225e6-112">Message Text</span></span>|<span data-ttu-id="225e6-113">Debe agregar el trabajo de agente '%s' a través de '%s' antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="225e6-113">The '%s' agent job must be added through '%s' before continuing.</span></span> <span data-ttu-id="225e6-114">Vea la documentación de '%s'.</span><span class="sxs-lookup"><span data-stu-id="225e6-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="225e6-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="225e6-115">Explanation</span></span>  
 <span data-ttu-id="225e6-116">Para crear una publicación hay que ser miembro del rol fijo de servidor **sysadmin** en el publicador o miembro del rol fijo de base de datos **db_owner** de la base de datos de la publicación.</span><span class="sxs-lookup"><span data-stu-id="225e6-116">To create a publication, you must be a member of the **sysadmin** fixed server role on the Publisher or a member of the **db_owner** fixed database role in the publication database.</span></span> <span data-ttu-id="225e6-117">Si es miembro del rol **db_owner** , este error se produce cuando:</span><span class="sxs-lookup"><span data-stu-id="225e6-117">If you are a member of the **db_owner** role, this error is raised if:</span></span>  
  
-   <span data-ttu-id="225e6-118">Se ejecutan scripts desde [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="225e6-118">You run scripts from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="225e6-119">El modelo de seguridad de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]ha cambiado, por lo que dichos scripts deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="225e6-119">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   <span data-ttu-id="225e6-120">El procedimiento almacenado **sp_addpublication** se ejecuta antes de ejecutar [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="225e6-120">The stored procedure **sp_addpublication** is executed before executing [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span></span> <span data-ttu-id="225e6-121">Esto es aplicable a todas las publicaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="225e6-121">This applies to all transactional publications.</span></span>  
  
-   <span data-ttu-id="225e6-122">El procedimiento almacenado **sp_addpublication** se ejecuta antes de ejecutar [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="225e6-122">The stored procedure **sp_addpublication** is executed before executing [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span></span> <span data-ttu-id="225e6-123">Esto se aplica a las publicaciones transaccionales que están habilitadas para las suscripciones de actualización en cola (un valor de TRUE para el **@allow_queued_tran** parámetro de **sp_addpublication**).</span><span class="sxs-lookup"><span data-stu-id="225e6-123">This applies to transactional publications that are enabled for queued updating subscriptions (a value of TRUE for the **@allow_queued_tran** parameter of **sp_addpublication**).</span></span>  
  
 <span data-ttu-id="225e6-124">Cada uno de los procedimientos almacenados **sp_addlogreader_agent** y **sp_addqreader_agent** crea un trabajo de agente y permite especificar la cuenta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con la que se ejecuta el agente.</span><span class="sxs-lookup"><span data-stu-id="225e6-124">The stored procedures **sp_addlogreader_agent** and **sp_addqreader_agent** each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="225e6-125">Para los usuarios del rol **sysadmin** , los trabajos de agente se crean de forma implícita si **sp_addlogreader_agent** y **sp_addqreader_agent** no se ejecutan; los agentes se ejecutan en el contexto de la cuenta de servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="225e6-125">For users in the **sysadmin** role, agent jobs are created implicitly if **sp_addlogreader_agent** and **sp_addqreader_agent** are not executed; agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the Distributor.</span></span> <span data-ttu-id="225e6-126">Aunque **sp_addlogreader_agent** y **sp_addqreader_agent** no son necesarios para los usuarios del rol **sysadmin** , por motivos de seguridad se recomienda especificar una cuenta independiente para los agentes.</span><span class="sxs-lookup"><span data-stu-id="225e6-126">Although **sp_addlogreader_agent** and **sp_addqreader_agent** are not required for users in the **sysadmin** role, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="225e6-127">Para más información, consulte [Modelo de seguridad del agente de replicación](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="225e6-127">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="225e6-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="225e6-128">User Action</span></span>  
 <span data-ttu-id="225e6-129">Asegúrese de ejecutar los procedimientos en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="225e6-129">Ensure you execute procedures in the correct order.</span></span> <span data-ttu-id="225e6-130">Para obtener más información, vea [crear una publicación](publish/create-a-publication.md), actualizar estos scripts para incluir los procedimientos almacenados y los parámetros requeridos por [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="225e6-130">For more information, see [Create a Publication](publish/create-a-publication.md), update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="225e6-131">Para obtener más información, vea [Actualizar scripts de replicación &#40;programación de la replicación con Transact-SQL&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="225e6-131">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="225e6-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="225e6-132">See Also</span></span>  
 [<span data-ttu-id="225e6-133">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="225e6-133">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
