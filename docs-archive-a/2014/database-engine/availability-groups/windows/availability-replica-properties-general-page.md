---
title: Propiedades de las réplicas de disponibilidad (página General) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilityreplicaproperties.general.f1
ms.assetid: 8318fefb-e045-4fab-8507-e1951fc7cec6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 313314baf009cdfb6109e63e9b65e369ac314f60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750225"
---
# <a name="availability-replica-properties-general-page"></a><span data-ttu-id="40bb0-102">Propiedades de las réplicas de disponibilidad (página General)</span><span class="sxs-lookup"><span data-stu-id="40bb0-102">Availability Replica Properties (General Page)</span></span>
  <span data-ttu-id="40bb0-103">Use este cuadro de diálogo para ver las propiedades de una réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="40bb0-103">Use this dialog box to viewthe properties of an availability replica.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="40bb0-104">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="40bb0-104">Task List</span></span>  
 <span data-ttu-id="40bb0-105">**Para ver las propiedades de una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="40bb0-105">**To view availability replica properties**</span></span>  
  
-   [<span data-ttu-id="40bb0-106">Ver las propiedades de una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40bb0-106">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="40bb0-107">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="40bb0-107">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="40bb0-108">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="40bb0-108">UI element list</span></span>  
 <span data-ttu-id="40bb0-109">**Nombre del grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="40bb0-109">**Availability group name**</span></span>  
 <span data-ttu-id="40bb0-110">Nombre del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="40bb0-110">Name of the availability group.</span></span> <span data-ttu-id="40bb0-111">Es un nombre definido por el usuario que debe ser único dentro del clúster de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="40bb0-111">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
 <span data-ttu-id="40bb0-112">**Instancia del servidor**</span><span class="sxs-lookup"><span data-stu-id="40bb0-112">**Server instance**</span></span>  
 <span data-ttu-id="40bb0-113">Nombre de servidor de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda esta réplica y, para una instancia no predeterminada, su nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="40bb0-113">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="40bb0-114">**Rol**</span><span class="sxs-lookup"><span data-stu-id="40bb0-114">**Role**</span></span>  
 <span data-ttu-id="40bb0-115">**Principal**</span><span class="sxs-lookup"><span data-stu-id="40bb0-115">**Primary**</span></span>  
 <span data-ttu-id="40bb0-116">Actualmente la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="40bb0-116">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="40bb0-117">**Secundario**</span><span class="sxs-lookup"><span data-stu-id="40bb0-117">**Secondary**</span></span>  
 <span data-ttu-id="40bb0-118">Actualmente una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="40bb0-118">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="40bb0-119">**Resolver**</span><span class="sxs-lookup"><span data-stu-id="40bb0-119">**Resolving**</span></span>  
 <span data-ttu-id="40bb0-120">Actualmente el rol de la réplica están en proceso de resolverse al rol principal o al rol secundario.</span><span class="sxs-lookup"><span data-stu-id="40bb0-120">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="40bb0-121">**Modo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="40bb0-121">**Availability mode**</span></span>  
 <span data-ttu-id="40bb0-122">Modo de disponibilidad de la réplica, que puede ser alguno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="40bb0-122">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="40bb0-123">**Confirmación asincrónica**</span><span class="sxs-lookup"><span data-stu-id="40bb0-123">**Asynchronous commit**</span></span>  
 <span data-ttu-id="40bb0-124">La réplica principal puede confirmar transacciones sin esperar a que la réplica secundaria escriba el registro en disco.</span><span class="sxs-lookup"><span data-stu-id="40bb0-124">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="40bb0-125">**Confirmación sincrónica**</span><span class="sxs-lookup"><span data-stu-id="40bb0-125">**Synchronous commit**</span></span>  
 <span data-ttu-id="40bb0-126">La réplica principal espera para confirmar una determinada transacción hasta que la réplica secundaria escribe la transacción en el disco.</span><span class="sxs-lookup"><span data-stu-id="40bb0-126">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="40bb0-127">Para obtener más información, vea [modos de disponibilidad (grupos de disponibilidad AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="40bb0-127">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="40bb0-128">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="40bb0-128">**Failover mode**</span></span>  
 <span data-ttu-id="40bb0-129">Modo de conmutación por error de la réplica, que puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="40bb0-129">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="40bb0-130">**Automático**</span><span class="sxs-lookup"><span data-stu-id="40bb0-130">**Automatic**</span></span>  
 <span data-ttu-id="40bb0-131">Conmutación por error automática.</span><span class="sxs-lookup"><span data-stu-id="40bb0-131">Automatic failover.</span></span> <span data-ttu-id="40bb0-132">La réplica es un destino de las conmutaciones por error automáticas.</span><span class="sxs-lookup"><span data-stu-id="40bb0-132">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="40bb0-133">Esto solo se admite si el modo de disponibilidad se establece en confirmación sincrónica.</span><span class="sxs-lookup"><span data-stu-id="40bb0-133">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="40bb0-134">**Manual**</span><span class="sxs-lookup"><span data-stu-id="40bb0-134">**Manual**</span></span>  
 <span data-ttu-id="40bb0-135">Conmutación por error manual.</span><span class="sxs-lookup"><span data-stu-id="40bb0-135">Manual failover.</span></span> <span data-ttu-id="40bb0-136">La réplica solo puede ser objeto de conmutación por error manual por parte del administrador de base de datos.</span><span class="sxs-lookup"><span data-stu-id="40bb0-136">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="40bb0-137">**Conexiones el en rol principal**</span><span class="sxs-lookup"><span data-stu-id="40bb0-137">**Connections in primary role**</span></span>  
 <span data-ttu-id="40bb0-138">El tipo de conexiones de cliente admitidas cuando la réplica posee el rol principal.</span><span class="sxs-lookup"><span data-stu-id="40bb0-138">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="40bb0-139">**Permitir todas las conexiones**</span><span class="sxs-lookup"><span data-stu-id="40bb0-139">**Allow all connections**</span></span>  
 <span data-ttu-id="40bb0-140">Se permiten todas las conexiones con las bases de datos de la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="40bb0-140">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="40bb0-141">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="40bb0-141">This is the default setting.</span></span>  
  
 <span data-ttu-id="40bb0-142">**Permitir conexiones de lectura o escritura**</span><span class="sxs-lookup"><span data-stu-id="40bb0-142">**Allow read/write connections**</span></span>  
 <span data-ttu-id="40bb0-143">No se permiten las conexiones en las que la propiedad de conexión Application Intent esté establecida en **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="40bb0-143">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="40bb0-144">Cuando la propiedad Application Intent está establecida en **ReadWrite** o la propiedad Application Intent Connection no tiene ningún valor, se permite la conexión.</span><span class="sxs-lookup"><span data-stu-id="40bb0-144">When the Application Intent property is set to **ReadWrite** or the application intent connection property is not set, the connection is allowed.</span></span>  
  
 <span data-ttu-id="40bb0-145">**Secundario legible**</span><span class="sxs-lookup"><span data-stu-id="40bb0-145">**Readable Secondary**</span></span>  
 <span data-ttu-id="40bb0-146">Si una réplica de disponibilidad que está realizando el rol secundario (es decir, una réplica secundaria) puede aceptar conexiones de clientes; puede tener uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="40bb0-146">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="40bb0-147">**No**</span><span class="sxs-lookup"><span data-stu-id="40bb0-147">**No**</span></span>  
 <span data-ttu-id="40bb0-148">No se permiten conexiones directas a las bases de datos secundarias de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="40bb0-148">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="40bb0-149">No están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="40bb0-149">They are not available for read access.</span></span> <span data-ttu-id="40bb0-150">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="40bb0-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="40bb0-151">**Solo intento de lectura**</span><span class="sxs-lookup"><span data-stu-id="40bb0-151">**Read-intent only**</span></span>  
 <span data-ttu-id="40bb0-152">Únicamente se permiten conexiones directas de solo lectura a las bases de datos secundarias de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="40bb0-152">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="40bb0-153">Todas las bases de datos secundarias están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="40bb0-153">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="40bb0-154">**Sí**</span><span class="sxs-lookup"><span data-stu-id="40bb0-154">**Yes**</span></span>  
 <span data-ttu-id="40bb0-155">Se permiten todas las conexiones a las bases de datos secundarias de esta réplica, pero solo para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="40bb0-155">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="40bb0-156">Todas las bases de datos secundarias están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="40bb0-156">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="40bb0-157">Para obtener más información, vea secundarias [activas: réplicas secundarias legibles (grupos de disponibilidad AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="40bb0-157">For more information, see [Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="40bb0-158">**Tiempo de espera de sesión (segundos)**</span><span class="sxs-lookup"><span data-stu-id="40bb0-158">**Session timeout (seconds)**</span></span>  
 <span data-ttu-id="40bb0-159">Período de tiempo de espera, en segundos.</span><span class="sxs-lookup"><span data-stu-id="40bb0-159">The time-out period, in seconds.</span></span> <span data-ttu-id="40bb0-160">El período de tiempo de espera es el tiempo máximo que la réplica espera hasta recibir un mensaje de otra réplica antes de considerar que se ha producido un error en la conexión entre la réplica principal y la secundaria.</span><span class="sxs-lookup"><span data-stu-id="40bb0-160">The time-out period is the maximum time that the replica waits to receive a message from another replica before considering connection between the primary and secondary replica have failed.</span></span> <span data-ttu-id="40bb0-161">El tiempo de espera de la sesión detecta si las réplicas secundarias están conectadas a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="40bb0-161">Session timeout detects whether secondaries are connected the primary replica.</span></span> <span data-ttu-id="40bb0-162">Al detectar un error en la conexión con una réplica secundaria, la réplica principal considera que la réplica secundaria no se ha sincronizado (NOT_SYNCHRONIZED).</span><span class="sxs-lookup"><span data-stu-id="40bb0-162">On detecting a failed connection with a secondary replica, the primary replica considers the secondary replica to be NOT_SYNCHRONIZED.</span></span> <span data-ttu-id="40bb0-163">Al detectar un error en la conexión con la réplica principal, la réplica secundaria intenta volver a conectarse.</span><span class="sxs-lookup"><span data-stu-id="40bb0-163">On detecting a failed connection with the primary replica, a secondary replica simply attempts to reconnect.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40bb0-164">Cuando se agota el tiempo de espera de la sesión, no se realiza una conmutación por error automática.</span><span class="sxs-lookup"><span data-stu-id="40bb0-164">Session timeouts do not cause automatic failovers.</span></span>  
  
 <span data-ttu-id="40bb0-165">**Dirección URL del extremo**</span><span class="sxs-lookup"><span data-stu-id="40bb0-165">**Endpoint URL**</span></span>  
 <span data-ttu-id="40bb0-166">Representación en forma de cadena de la base de datos definida por el usuario que crea un reflejo del extremo usado por las conexiones entre las réplicas principal y secundaria para la sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="40bb0-166">String representation of the user-specified database mirroring endpoint that is used by connections between primary and secondary replicas for data synchronization.</span></span> <span data-ttu-id="40bb0-167">Para obtener más información sobre la sintaxis de las direcciones URL del punto de conexión, vea [Especificar la dirección URL del punto de conexión al agregar o modificar una réplica de disponibilidad &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="40bb0-167">For information about the syntax of endpoint URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40bb0-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40bb0-168">See Also</span></span>  
 [<span data-ttu-id="40bb0-169">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40bb0-169">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
