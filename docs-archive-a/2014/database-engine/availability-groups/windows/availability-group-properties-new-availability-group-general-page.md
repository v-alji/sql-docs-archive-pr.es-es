---
title: Propiedades de grupo de disponibilidad y nuevo grupo de disponibilidad (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.general.f1
ms.assetid: 9af5379f-91b8-4729-9f75-4a80242a30e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 876b9d0948b7cd0d01c21b0ec1d64c51a55fa157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663125"
---
# <a name="availability-group-properties-and-new-availability-group-general-page"></a><span data-ttu-id="3f617-102">Propiedades de grupo de disponibilidad y nuevo grupo de disponibilidad (página General)</span><span class="sxs-lookup"><span data-stu-id="3f617-102">Availability Group Properties and New Availability Group (General Page)</span></span>
  <span data-ttu-id="3f617-103">Este tema se aplica a la pestaña **General** del cuadro de diálogo de **Nuevo grupo de disponibilidad** y el cuadro de diálogo de **Propiedades de grupo de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="3f617-103">This topic applies to the **General** tab of both the **New Availability Group** dialog box and the **Availability Group Properties** dialog box.</span></span>  <span data-ttu-id="3f617-104">El cuadro de diálogo **Nuevo grupo de disponibilidad** permite crear un nuevo grupo de disponibilidad sin utilizar [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f617-104">The **New Availability Group** dialog box enables you to create a new availability group without using the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span></span> <span data-ttu-id="3f617-105">El cuadro de diálogo **Propiedades de grupo de disponibilidad** permite ver y modificar la configuración de un grupo de disponibilidad existente.</span><span class="sxs-lookup"><span data-stu-id="3f617-105">The **Availability Group Properties** dialog box enables you to view and alter the configuration of an existing availability group.</span></span>  
  
 <span data-ttu-id="3f617-106">**Para ver las propiedades del grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="3f617-106">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="3f617-107">Ver las propiedades del grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3f617-107">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="3f617-108">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3f617-108">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="3f617-109">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3f617-109">UI element list</span></span>  
 <span data-ttu-id="3f617-110">**Nombre del grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="3f617-110">**Availability group name**</span></span>  
 <span data-ttu-id="3f617-111">Nombre del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="3f617-111">Name of the availability group.</span></span> <span data-ttu-id="3f617-112">Es un nombre definido por el usuario que debe ser único dentro del clúster de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="3f617-112">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
## <a name="availability-databases"></a><span data-ttu-id="3f617-113">Bases de datos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="3f617-113">Availability Databases</span></span>  
 <span data-ttu-id="3f617-114">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="3f617-114">**Database Name**</span></span>  
 <span data-ttu-id="3f617-115">Nombre de una base de datos que se ha agregado al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="3f617-115">Name of a database that has been added to the availability group.</span></span>  
  
 <span data-ttu-id="3f617-116">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="3f617-116">**Add**</span></span>  
 <span data-ttu-id="3f617-117">Haga clic para agregar una base de datos al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="3f617-117">Click to add a database to the availability group.</span></span>  
  
 <span data-ttu-id="3f617-118">**Remove**</span><span class="sxs-lookup"><span data-stu-id="3f617-118">**Remove**</span></span>  
 <span data-ttu-id="3f617-119">Haga clic para quitar una base de datos seleccionada del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="3f617-119">Click to remove a selected database from the availability group.</span></span>  
  
## <a name="availability-replicas"></a><span data-ttu-id="3f617-120">Réplicas de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="3f617-120">Availability Replicas</span></span>  
 <span data-ttu-id="3f617-121">**Instancia del servidor**</span><span class="sxs-lookup"><span data-stu-id="3f617-121">**Server instance**</span></span>  
 <span data-ttu-id="3f617-122">Nombre de servidor de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda esta réplica y, para una instancia no predeterminada, su nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="3f617-122">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="3f617-123">**Rol**</span><span class="sxs-lookup"><span data-stu-id="3f617-123">**Role**</span></span>  
 <span data-ttu-id="3f617-124">**Principal**</span><span class="sxs-lookup"><span data-stu-id="3f617-124">**Primary**</span></span>  
 <span data-ttu-id="3f617-125">Actualmente la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3f617-125">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="3f617-126">**Secundario**</span><span class="sxs-lookup"><span data-stu-id="3f617-126">**Secondary**</span></span>  
 <span data-ttu-id="3f617-127">Actualmente una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="3f617-127">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="3f617-128">**Resolver**</span><span class="sxs-lookup"><span data-stu-id="3f617-128">**Resolving**</span></span>  
 <span data-ttu-id="3f617-129">Actualmente el rol de la réplica están en proceso de resolverse al rol principal o al rol secundario.</span><span class="sxs-lookup"><span data-stu-id="3f617-129">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="3f617-130">**Modo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="3f617-130">**Availability Mode**</span></span>  
 <span data-ttu-id="3f617-131">Modo de disponibilidad de la réplica, que puede ser alguno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f617-131">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="3f617-132">**Confirmación asincrónica**</span><span class="sxs-lookup"><span data-stu-id="3f617-132">**Asynchronous commit**</span></span>  
 <span data-ttu-id="3f617-133">La réplica principal puede confirmar transacciones sin esperar a que la réplica secundaria escriba el registro en disco.</span><span class="sxs-lookup"><span data-stu-id="3f617-133">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="3f617-134">**Confirmación sincrónica**</span><span class="sxs-lookup"><span data-stu-id="3f617-134">**Synchronous commit**</span></span>  
 <span data-ttu-id="3f617-135">La réplica principal espera para confirmar una determinada transacción hasta que la réplica secundaria escribe la transacción en el disco.</span><span class="sxs-lookup"><span data-stu-id="3f617-135">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="3f617-136">Para obtener más información, vea [modos de disponibilidad (grupos de disponibilidad AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="3f617-136">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="3f617-137">**Modo de conmutación por error**</span><span class="sxs-lookup"><span data-stu-id="3f617-137">**Failover Mode**</span></span>  
 <span data-ttu-id="3f617-138">Modo de conmutación por error de la réplica, que puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f617-138">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="3f617-139">**Automático**</span><span class="sxs-lookup"><span data-stu-id="3f617-139">**Automatic**</span></span>  
 <span data-ttu-id="3f617-140">Conmutación por error automática.</span><span class="sxs-lookup"><span data-stu-id="3f617-140">Automatic failover.</span></span> <span data-ttu-id="3f617-141">La réplica es un destino de las conmutaciones por error automáticas.</span><span class="sxs-lookup"><span data-stu-id="3f617-141">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="3f617-142">Esto solo se admite si el modo de disponibilidad se establece en confirmación sincrónica.</span><span class="sxs-lookup"><span data-stu-id="3f617-142">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="3f617-143">**Manual**</span><span class="sxs-lookup"><span data-stu-id="3f617-143">**Manual**</span></span>  
 <span data-ttu-id="3f617-144">Conmutación por error manual.</span><span class="sxs-lookup"><span data-stu-id="3f617-144">Manual failover.</span></span> <span data-ttu-id="3f617-145">La réplica solo puede ser objeto de conmutación por error manual por parte del administrador de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3f617-145">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="3f617-146">**Conexiones el en rol principal**</span><span class="sxs-lookup"><span data-stu-id="3f617-146">**Connections in Primary Role**</span></span>  
 <span data-ttu-id="3f617-147">El tipo de conexiones de cliente admitidas cuando la réplica posee el rol principal.</span><span class="sxs-lookup"><span data-stu-id="3f617-147">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="3f617-148">**Permitir todas las conexiones**</span><span class="sxs-lookup"><span data-stu-id="3f617-148">**Allow all connections**</span></span>  
 <span data-ttu-id="3f617-149">Se permiten todas las conexiones con las bases de datos de la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3f617-149">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="3f617-150">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f617-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="3f617-151">**Permitir conexiones de lectura o escritura**</span><span class="sxs-lookup"><span data-stu-id="3f617-151">**Allow read/write connections**</span></span>  
 <span data-ttu-id="3f617-152">No se permiten las conexiones en las que la propiedad de conexión Application Intent esté establecida en **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="3f617-152">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="3f617-153">Cuando la propiedad Application Intent está establecida en **ReadWrite** o no tiene ningún valor, se permite la conexión.</span><span class="sxs-lookup"><span data-stu-id="3f617-153">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="3f617-154">Para obtener más información sobre propiedad de conexión Application Intent, vea [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="3f617-154">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="3f617-155">**Secundario legible**</span><span class="sxs-lookup"><span data-stu-id="3f617-155">**Readable Secondary**</span></span>  
 <span data-ttu-id="3f617-156">Si una réplica de disponibilidad que está realizando el rol secundario (es decir, una réplica secundaria) puede aceptar conexiones de clientes; puede tener uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f617-156">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="3f617-157">**No**</span><span class="sxs-lookup"><span data-stu-id="3f617-157">**No**</span></span>  
 <span data-ttu-id="3f617-158">No se permiten conexiones directas a las bases de datos secundarias de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="3f617-158">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="3f617-159">No están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="3f617-159">They are not available for read access.</span></span> <span data-ttu-id="3f617-160">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f617-160">This is the default setting.</span></span>  
  
 <span data-ttu-id="3f617-161">**Solo intento de lectura**</span><span class="sxs-lookup"><span data-stu-id="3f617-161">**Read-intent only**</span></span>  
 <span data-ttu-id="3f617-162">Únicamente se permiten conexiones directas de solo lectura a las bases de datos secundarias de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="3f617-162">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="3f617-163">Todas las bases de datos secundarias están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="3f617-163">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="3f617-164">**Sí**</span><span class="sxs-lookup"><span data-stu-id="3f617-164">**Yes**</span></span>  
 <span data-ttu-id="3f617-165">Se permiten todas las conexiones a las bases de datos secundarias de esta réplica, pero solo para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="3f617-165">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="3f617-166">Todas las bases de datos secundarias están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="3f617-166">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="3f617-167">**Tiempo de espera de sesión (segundos)**</span><span class="sxs-lookup"><span data-stu-id="3f617-167">**Session Timeout (seconds)**</span></span>  
 <span data-ttu-id="3f617-168">El número de segundos del período de tiempo de espera de la sesión en esta réplica.</span><span class="sxs-lookup"><span data-stu-id="3f617-168">The number of seconds for the session-timeout period on this replica.</span></span>  
  
 <span data-ttu-id="3f617-169">**Dirección URL del extremo**</span><span class="sxs-lookup"><span data-stu-id="3f617-169">**Endpoint URL**</span></span>  
 <span data-ttu-id="3f617-170">La dirección URL del extremo.</span><span class="sxs-lookup"><span data-stu-id="3f617-170">The URL of the endpoint.</span></span> <span data-ttu-id="3f617-171">Para obtener más información sobre el formato de estas direcciones URL, vea [Especificar la dirección URL del punto de conexión al agregar o modificar una réplica de disponibilidad &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="3f617-171">For information the format of these URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
 <span data-ttu-id="3f617-172">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="3f617-172">**Add**</span></span>  
 <span data-ttu-id="3f617-173">Haga clic para agregar una réplica secundaria al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="3f617-173">Click to add a secondary replica to the availability group.</span></span>  
  
 <span data-ttu-id="3f617-174">**Remove**</span><span class="sxs-lookup"><span data-stu-id="3f617-174">**Remove**</span></span>  
 <span data-ttu-id="3f617-175">Haga clic para quitar una réplica secundaria del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="3f617-175">Click to remove a secondary replica from the availability group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f617-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f617-176">See Also</span></span>  
 [<span data-ttu-id="3f617-177">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3f617-177">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
