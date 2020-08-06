---
title: Requisitos del rol de seguridad para la replicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- security [SQL Server replication], roles
- roles [SQL Server], replication
ms.assetid: b324a80f-4319-4cb2-847b-1910c49d90e0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7eeea09a8dd580870b1d7d5514878172325fe9fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748028"
---
# <a name="security-role-requirements-for-replication"></a><span data-ttu-id="110eb-102">Security Role Requirements for Replication</span><span class="sxs-lookup"><span data-stu-id="110eb-102">Security Role Requirements for Replication</span></span>
  <span data-ttu-id="110eb-103">La replicación restringe las acciones específicas que puede llevar a cabo un usuario, basándose en los roles a los que está asignado el nombre de inicio de sesión del usuario.</span><span class="sxs-lookup"><span data-stu-id="110eb-103">Replication restricts the specific actions that a user can perform based on the roles to which the user's login is mapped.</span></span> <span data-ttu-id="110eb-104">La replicación ha concedido ciertos permisos al rol fijo de servidor **sysadmin** , al rol fijo de base de datos **db_owner** y a los inicios de sesión de la lista de acceso a la publicación (PAL).</span><span class="sxs-lookup"><span data-stu-id="110eb-104">Replication has granted certain permissions to the **sysadmin** fixed server role, the **db_owner** fixed database role, and the logins in the publication access list (PAL).</span></span>  
  
## <a name="security-role-requirements-for-replication-setup"></a><span data-ttu-id="110eb-105">Requisitos del rol de seguridad para la configuración de la replicación</span><span class="sxs-lookup"><span data-stu-id="110eb-105">Security Role Requirements for Replication Setup</span></span>  
 <span data-ttu-id="110eb-106">En la tabla siguiente se resume el nivel de autenticación necesario para las tareas comunes de configuración de la replicación:</span><span class="sxs-lookup"><span data-stu-id="110eb-106">The following table summarizes the authentication level necessary for common replication setup tasks:</span></span>  
  
|<span data-ttu-id="110eb-107">Tarea de configuración</span><span class="sxs-lookup"><span data-stu-id="110eb-107">Setup task</span></span>|<span data-ttu-id="110eb-108">Requisito de pertenencia</span><span class="sxs-lookup"><span data-stu-id="110eb-108">Membership requirement</span></span>|  
|----------------|----------------------------|  
|<span data-ttu-id="110eb-109">Habilitar un distribuidor, publicador o suscriptor.</span><span class="sxs-lookup"><span data-stu-id="110eb-109">Enable a Distributor, Publisher, or Subscriber.</span></span>|<span data-ttu-id="110eb-110">Rol de servidor**sysadmin** en el publicador.</span><span class="sxs-lookup"><span data-stu-id="110eb-110">**sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="110eb-111">Habilitar una base de datos para replicación.</span><span class="sxs-lookup"><span data-stu-id="110eb-111">Enable a database for replication.</span></span>|<span data-ttu-id="110eb-112">Rol de servidor**sysadmin** en el publicador.</span><span class="sxs-lookup"><span data-stu-id="110eb-112">**sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="110eb-113">Crear una publicación.</span><span class="sxs-lookup"><span data-stu-id="110eb-113">Create a publication.</span></span>|<span data-ttu-id="110eb-114">Rol de base de datos**db_owner** en la base de datos de publicaciones del publicador o rol de servidor **sysadmin** en el publicador.</span><span class="sxs-lookup"><span data-stu-id="110eb-114">**db_owner** database role on the publication database at the Publisher or **sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="110eb-115">Ver propiedades de publicación.</span><span class="sxs-lookup"><span data-stu-id="110eb-115">View publication properties.</span></span>|<span data-ttu-id="110eb-116">Miembro de la PAL en el publicador, rol de base de datos **db_owner** en la base de datos de publicaciones del publicador o rol de servidor **sysadmin** en el publicador.</span><span class="sxs-lookup"><span data-stu-id="110eb-116">Member of the PAL at the Publisher, **db_owner** database role on the publication database at the Publisher, or **sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="110eb-117">Crear una suscripción.</span><span class="sxs-lookup"><span data-stu-id="110eb-117">Create a subscription.</span></span>|<span data-ttu-id="110eb-118">Rol de base de datos**db_owner** en la base de datos de publicaciones del publicador o rol de servidor **sysadmin** en el publicador.</span><span class="sxs-lookup"><span data-stu-id="110eb-118">**db_owner** database role on the publication database at the Publisher or **sysadmin** server role on the Publisher.</span></span><br /><br /> <span data-ttu-id="110eb-119">Rol de base de datos**db_owner** en la base de datos de suscripciones del suscriptor o rol de servidor **sysadmin** en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="110eb-119">**db_owner** database role on the subscription database at the Subscriber or **sysadmin** server role on the Subscriber.</span></span>|  
|<span data-ttu-id="110eb-120">Configurar perfiles de agente.</span><span class="sxs-lookup"><span data-stu-id="110eb-120">Configure agent profiles.</span></span>|<span data-ttu-id="110eb-121">Rol de servidor**sysadmin** en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="110eb-121">**sysadmin** server role on the Distributor.</span></span>|  
  
## <a name="security-role-requirements-for-replication-maintenance"></a><span data-ttu-id="110eb-122">Requisitos del rol de seguridad para el mantenimiento de la replicación</span><span class="sxs-lookup"><span data-stu-id="110eb-122">Security Role Requirements for Replication Maintenance</span></span>  
 <span data-ttu-id="110eb-123">En la tabla siguiente se resume el nivel de autenticación necesario para las tareas comunes de mantenimiento de la replicación:</span><span class="sxs-lookup"><span data-stu-id="110eb-123">The following table summarizes the authentication level necessary for common replication maintenance tasks:</span></span>  
  
|<span data-ttu-id="110eb-124">Tarea de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="110eb-124">Maintenance task</span></span>|<span data-ttu-id="110eb-125">Requisito de pertenencia</span><span class="sxs-lookup"><span data-stu-id="110eb-125">Membership requirement</span></span>|  
|----------------------|----------------------------|  
|<span data-ttu-id="110eb-126">Modificar o quitar un distribuidor, publicador o suscriptor.</span><span class="sxs-lookup"><span data-stu-id="110eb-126">Modify or drop a Distributor, Publisher, or Subscriber.</span></span>|<span data-ttu-id="110eb-127">Rol de servidor**sysadmin** en el servidor apropiado.</span><span class="sxs-lookup"><span data-stu-id="110eb-127">**sysadmin** server role on the appropriate server.</span></span>|  
|<span data-ttu-id="110eb-128">Modificar o quitar una publicación.</span><span class="sxs-lookup"><span data-stu-id="110eb-128">Modify or drop a publication.</span></span>|<span data-ttu-id="110eb-129">Rol de base de datos**db_owner** en la base de datos de publicaciones del publicador o rol de servidor **sysadmin** en el publicador.</span><span class="sxs-lookup"><span data-stu-id="110eb-129">**db_owner** database role on the publication database at the Publisher or **sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="110eb-130">Modificar o quitar una suscripción en el publicador.</span><span class="sxs-lookup"><span data-stu-id="110eb-130">Modify or drop a subscription at the Publisher.</span></span>|<span data-ttu-id="110eb-131">Rol de base de datos**db_owner** en la base de datos de publicaciones del publicador o rol de servidor **sysadmin** en el publicador.</span><span class="sxs-lookup"><span data-stu-id="110eb-131">**db_owner** database role on the publication database at the Publisher or **sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="110eb-132">Modificar o quitar una suscripción en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="110eb-132">Modify or drop a subscription at the Subscriber.</span></span>|<span data-ttu-id="110eb-133">Rol de base de datos**db_owner** en la base de datos de suscripciones del suscriptor o rol de servidor **sysadmin** en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="110eb-133">**db_owner** database role on the subscription database at the Subscriber or **sysadmin** server role on the Subscriber.</span></span>|  
|<span data-ttu-id="110eb-134">Marcar una suscripción para reinicializarla.</span><span class="sxs-lookup"><span data-stu-id="110eb-134">Mark a subscription for reinitialization.</span></span>|<span data-ttu-id="110eb-135">Suscripción de inserción: rol de base de datos **db_owner** en la base de datos de publicaciones del publicador o rol de servidor **sysadmin** en el publicador.</span><span class="sxs-lookup"><span data-stu-id="110eb-135">Push subscription: **db_owner** database role in the publication database at the Publisher or **sysadmin** server role on the Publisher.</span></span><br /><br /> <span data-ttu-id="110eb-136">Suscripción de extracción: rol de base de datos **db_owner** en la base de datos de suscripciones del suscriptor o rol de servidor **sysadmin** en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="110eb-136">Pull subscription: **db_owner** database role in the subscription database at the Subscriber or **sysadmin** server role on the Subscriber.</span></span>|  
|<span data-ttu-id="110eb-137">Ver la actividad de replicación, los errores y el historial con el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="110eb-137">View replication activity, errors, and history using Replication Monitor.</span></span> <span data-ttu-id="110eb-138">Un usuario no puede modificar perfiles de agente, programaciones, etc., a menos que sea miembro del rol de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="110eb-138">A user cannot modify agent profiles, schedules, and so on, unless the user is a member of the **sysadmin** server role.</span></span>|<span data-ttu-id="110eb-139">Rol de base de datos**replmonitor** en la base de datos de distribución del distribuidor o rol de servidor **sysadmin** en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="110eb-139">**replmonitor** database role on the distribution database at the Distributor or **sysadmin** server role on the Distributor.</span></span>|  
|<span data-ttu-id="110eb-140">Mantener agentes de replicación.</span><span class="sxs-lookup"><span data-stu-id="110eb-140">Maintain replication agents.</span></span>|<span data-ttu-id="110eb-141">Rol de base de datos**db_owner** en la base de datos correspondiente o rol de servidor **sysadmin** en el servidor apropiado.</span><span class="sxs-lookup"><span data-stu-id="110eb-141">**db_owner** database role in the appropriate database or **sysadmin** server role on the appropriate server.</span></span><br /><br /> <span data-ttu-id="110eb-142">Si un usuario creó el agente en el rol **sysadmin** y no especificó una cuenta de proxy para el agente, éste se ejecutará en el contexto de la cuenta del Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="110eb-142">If the agent was created by a user in the **sysadmin** role, and a proxy account was not specified for the agent, the agent runs under the context of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent account.</span></span> <span data-ttu-id="110eb-143">En este caso, un usuario con el rol **db_owner** no podrá modificar el trabajo asociado con el agente.</span><span class="sxs-lookup"><span data-stu-id="110eb-143">In this case, a user in the **db_owner** role cannot modify the job associated with the agent.</span></span>|  
|<span data-ttu-id="110eb-144">Iniciar o detener un agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="110eb-144">Start or stop a replication agent.</span></span>|<span data-ttu-id="110eb-145">Propietario del trabajo de agente o rol de servidor **sysadmin** en el servidor apropiado.</span><span class="sxs-lookup"><span data-stu-id="110eb-145">Owner of the agent job or **sysadmin** server role on the appropriate server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="110eb-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="110eb-146">See Also</span></span>  
 <span data-ttu-id="110eb-147">[Replication Security Best Practices](replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="110eb-147">[Replication Security Best Practices](replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="110eb-148">Seguridad de Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="110eb-148">SQL Server Replication Security</span></span>](view-and-modify-replication-security-settings.md)  
  
  