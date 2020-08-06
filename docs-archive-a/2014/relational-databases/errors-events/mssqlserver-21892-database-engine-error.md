---
title: MSSQLSERVER_21892 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21892 (Database Engine error)
ms.assetid: 199818e8-28f4-440e-ad85-7bea88f51153
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd3bfa1213f0569293991d6bd759619c6e7b596
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749337"
---
# <a name="mssqlserver_21892"></a><span data-ttu-id="1c061-102">MSSQLSERVER_21892</span><span class="sxs-lookup"><span data-stu-id="1c061-102">MSSQLSERVER_21892</span></span>
    
## <a name="details"></a><span data-ttu-id="1c061-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1c061-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c061-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="1c061-104">Product Name</span></span>|<span data-ttu-id="1c061-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1c061-105">SQL Server</span></span>|  
|<span data-ttu-id="1c061-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1c061-106">Event ID</span></span>|<span data-ttu-id="1c061-107">21892</span><span class="sxs-lookup"><span data-stu-id="1c061-107">21892</span></span>|  
|<span data-ttu-id="1c061-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="1c061-108">Event Source</span></span>|<span data-ttu-id="1c061-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1c061-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1c061-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1c061-110">Component</span></span>|<span data-ttu-id="1c061-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1c061-111">SQLEngine</span></span>|  
|<span data-ttu-id="1c061-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1c061-112">Symbolic Name</span></span>|<span data-ttu-id="1c061-113">SQLErrorNum21892</span><span class="sxs-lookup"><span data-stu-id="1c061-113">SQLErrorNum21892</span></span>|  
|<span data-ttu-id="1c061-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1c061-114">Message Text</span></span>|<span data-ttu-id="1c061-115">No se puede consultar sys.availability_replicas en el principal de grupo de disponibilidad asociado con el nombre de red virtual '%s' para los nombres de servidor de las réplicas de miembro: error = %d, mensaje de error = %s.',</span><span class="sxs-lookup"><span data-stu-id="1c061-115">Unable to query sys.availability_replicas at the availability group primary associated with virtual network name '%s' for the server names of the member replicas: error = %d, error message = %s.',</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1c061-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1c061-116">Explanation</span></span>  
 <span data-ttu-id="1c061-117">`sp_validate_replica_hosts_as_publishers` consulta el principal actual del grupo de disponibilidad asociado con el publicador redireccionado para determinar las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospedan las réplicas de miembro.</span><span class="sxs-lookup"><span data-stu-id="1c061-117">`sp_validate_replica_hosts_as_publishers` queries the current primary of the availability group associated with the redirected publisher, to determine the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that host the member replicas.</span></span>  <span data-ttu-id="1c061-118">Cuando se produce un error en esta consulta, se devuelve el error 21892.</span><span class="sxs-lookup"><span data-stu-id="1c061-118">When this query fails, error 21892 is returned.</span></span>  
  
 <span data-ttu-id="1c061-119">`sp_validate_replica_hosts_as_publishers` está normalmente en el primer uso del servidor vinculado temporal, por lo que si hay problemas de conectividad, probablemente aparecerán primero con `sp_validate_replica_hosts_as_publishers`.</span><span class="sxs-lookup"><span data-stu-id="1c061-119">`sp_validate_replica_hosts_as_publishers` is typically on of the first use of the temporary linked server, so if there are connectivity problems they are likely to appear first with `sp_validate_replica_hosts_as_publishers`.</span></span> <span data-ttu-id="1c061-120">A diferencia de `sp_validate_redirected_publisher`, el servidor vinculado que usa `sp_validate_replica_hosts_as_publishers` siempre emplea las credenciales del autor de llamada al conectarse a cualquiera de los hosts de la réplica de grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1c061-120">Unlike `sp_validate_redirected_publisher`, the linked server used by `sp_validate_replica_hosts_as_publishers` always uses the credentials of the caller when connecting to any of the availability group replica hosts.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1c061-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1c061-121">User Action</span></span>  
 <span data-ttu-id="1c061-122">Al ejecutar este procedimiento almacenado, asegúrese de que se ejecutar desde un inicio de sesión que sea válido en todas las réplicas.</span><span class="sxs-lookup"><span data-stu-id="1c061-122">When running this stored procedure, made certain that you run from a login that is valid on all of the replicas.</span></span> <span data-ttu-id="1c061-123">El inicio de sesión requiere autorización suficiente para consultar las tablas de metadatos del grupo de disponibilidad, así como para consultar las tablas de metadatos de suscripción en la réplica de base de datos del publicador.</span><span class="sxs-lookup"><span data-stu-id="1c061-123">The login will require sufficient authorization to query availability group metadata tables as well as to query the subscription metadata tables in the publisher database replica.</span></span>  
  
 <span data-ttu-id="1c061-124">Examine el error de referencia original para determinar la causa del error y llevar a cabo la acción correctiva adecuada.</span><span class="sxs-lookup"><span data-stu-id="1c061-124">Examine the original referenced error to determine the cause of the failure and appropriate corrective action.</span></span>  
  
  
