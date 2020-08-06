---
title: MSSQL_ENG024070 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG024070 error
ms.assetid: 23ac7e00-fab6-429b-9f85-2736a322aa65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fcfcb96b284d46d46f63af4a650f925ef2de73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745201"
---
# <a name="mssql_eng024070"></a><span data-ttu-id="cbd51-102">MSSQL_ENG024070</span><span class="sxs-lookup"><span data-stu-id="cbd51-102">MSSQL_ENG024070</span></span>
    
## <a name="message-details"></a><span data-ttu-id="cbd51-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="cbd51-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cbd51-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="cbd51-104">Product Name</span></span>|<span data-ttu-id="cbd51-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cbd51-105">SQL Server</span></span>|  
|<span data-ttu-id="cbd51-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cbd51-106">Event ID</span></span>|<span data-ttu-id="cbd51-107">24070</span><span class="sxs-lookup"><span data-stu-id="cbd51-107">24070</span></span>|  
|<span data-ttu-id="cbd51-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="cbd51-108">Event Source</span></span>|<span data-ttu-id="cbd51-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cbd51-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cbd51-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cbd51-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="cbd51-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cbd51-111">Symbolic Name</span></span>||  
|<span data-ttu-id="cbd51-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cbd51-112">Message Text</span></span>|<span data-ttu-id="cbd51-113">El cliente no dispone de un privilegio requerido.</span><span class="sxs-lookup"><span data-stu-id="cbd51-113">A required privilege is not held by the client.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cbd51-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="cbd51-114">Explanation</span></span>  
 <span data-ttu-id="cbd51-115">Se trata de un error general que puede producirse independientemente de que se esté usando replicación o no.</span><span class="sxs-lookup"><span data-stu-id="cbd51-115">This is a general error that can be raised regardless of whether replication is being used.</span></span> <span data-ttu-id="cbd51-116">Para un servidor de una topología de replicación, el error suele producirse porque la cuenta del servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se cambia con el Administrador de control de servicios de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows en lugar del Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbd51-116">For a server in a replication topology, the error is typically raised because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account is changed by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Service Control Manager instead of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="cbd51-117">Si intenta ejecutar un trabajo de agente después de cambiar la cuenta de servicio, es posible que el trabajo no progrese y aparezca un mensaje de error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="cbd51-117">When you try to run an agent job after changing the service account, the job might fail with an error message that is similar to the following:</span></span>  
  
 <span data-ttu-id="cbd51-118">"Ejecutado como usuario: \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="cbd51-118">"Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="cbd51-119">Replicación: subsistema de instantánea de replicación: error del agente \<AgentName> .</span><span class="sxs-lookup"><span data-stu-id="cbd51-119">Replication-Replication Snapshot Subsystem: agent \<AgentName> failed.</span></span> <span data-ttu-id="cbd51-120">Ejecutado como usuario: \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="cbd51-120">Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="cbd51-121">El cliente no dispone de un privilegio requerido.</span><span class="sxs-lookup"><span data-stu-id="cbd51-121">A required privilege is not held by the client.</span></span> <span data-ttu-id="cbd51-122">Error en el paso.</span><span class="sxs-lookup"><span data-stu-id="cbd51-122">The step failed.</span></span> <span data-ttu-id="cbd51-123">`[SQLSTATE 42000] (Error 14151)`.</span><span class="sxs-lookup"><span data-stu-id="cbd51-123">`[SQLSTATE 42000] (Error 14151)`.</span></span> <span data-ttu-id="cbd51-124">Error en el paso."</span><span class="sxs-lookup"><span data-stu-id="cbd51-124">The step failed."</span></span>  
  
 <span data-ttu-id="cbd51-125">Este problema se produce porque el Administrador de control de servicios de Windows no puede conceder los permisos necesarios a la nueva cuenta de servicio para el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbd51-125">This problem occurs because the Windows Service Control Manager cannot grant the required permissions to the new service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cbd51-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cbd51-126">User Action</span></span>  
 <span data-ttu-id="cbd51-127">Para evitar este problema en el futuro, utilice siempre el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en lugar del Administrador de control de servicios de Windows para cambiar las cuentas de servicio y las contraseñas.</span><span class="sxs-lookup"><span data-stu-id="cbd51-127">To avoid this problem in the future, always use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager instead of the Windows Service Control Manager to change service accounts and passwords.</span></span>  
  
 <span data-ttu-id="cbd51-128">Para resolver este problema, utilice el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para cambiar la cuenta de servicio a la cuenta original.</span><span class="sxs-lookup"><span data-stu-id="cbd51-128">To resolve this problem, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change the service account back to the original account.</span></span> <span data-ttu-id="cbd51-129">A continuación, use el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para cambiar a la nueva cuenta.</span><span class="sxs-lookup"><span data-stu-id="cbd51-129">Then, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change to the new account.</span></span> <span data-ttu-id="cbd51-130">Al hacer esto, el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agrega la nueva cuenta al siguiente grupo de seguridad:</span><span class="sxs-lookup"><span data-stu-id="cbd51-130">When you do this, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager adds the new account to the following security group:</span></span>  
  
 <span data-ttu-id="cbd51-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span><span class="sxs-lookup"><span data-stu-id="cbd51-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span></span>  
  
 <span data-ttu-id="cbd51-132">Como miembro de este grupo de seguridad, se conceden a la nueva cuenta los permisos necesarios para ejecutar el trabajo del agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="cbd51-132">Being a member of this security group grants to the new account the required permissions to run the replication agent job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd51-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cbd51-133">See Also</span></span>  
 <span data-ttu-id="cbd51-134">[Referencia de errores y eventos &#40;replicación&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="cbd51-134">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="cbd51-135">[Administrar inicios de sesión y contraseñas en la replicación](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="cbd51-135">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 [<span data-ttu-id="cbd51-136">Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="cbd51-136">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  
