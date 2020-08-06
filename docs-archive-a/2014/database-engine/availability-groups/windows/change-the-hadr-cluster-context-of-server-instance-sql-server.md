---
title: Cambiar el contexto de clúster de HADR de la instancia de servidor (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- Availability replicas [SQL Server], change WSFC cluster context
ms.assetid: ecd99f91-b9a2-4737-994e-507065a12f80
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbc29fa2ebaaf2bbc9e577b5bd303e8a0dd0ec4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750214"
---
# <a name="change-the-hadr-cluster-context-of-server-instance-sql-server"></a><span data-ttu-id="fe009-102">Cambiar el contexto de clúster de HADR de la instancia de servidor (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fe009-102">Change the HADR Cluster Context of Server Instance (SQL Server)</span></span>
  <span data-ttu-id="fe009-103">En este tema se describe cómo cambiar el contexto de clúster de HADR de una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante [!INCLUDE[tsql](../../../includes/tsql-md.md)] en [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="fe009-103">This topic describes how to switch the HADR cluster context of an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="fe009-104">El *contexto de clúster de HADR* determina qué clúster de Clústeres de conmutación por error de Windows Server (WSFC) administra los metadatos para las réplicas de disponibilidad hospedadas por la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="fe009-104">The *HADR cluster context* determines which Windows Server Failover Clustering (WSFC) cluster manages the metadata for availability replicas hosted by the server instance.</span></span>  
  
 <span data-ttu-id="fe009-105">Cambie el contexto de clúster de HADR solo durante una migración entre clústeres de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] a una instancia de [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] en un nuevo clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="fe009-105">Switch the HADR cluster context only during a cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] to an instance of [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] on a new WSFC cluster.</span></span> <span data-ttu-id="fe009-106">La migración entre clústeres de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] admite la actualización del sistema operativo a [!INCLUDE[win8](../../../includes/win8-md.md)] o [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] con un tiempo de inactividad mínimo de los grupos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fe009-106">Cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] supports OS upgrade to [!INCLUDE[win8](../../../includes/win8-md.md)] or [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] with minimal downtime of availability groups.</span></span> <span data-ttu-id="fe009-107">Para obtener más información, vea [Migración entre clústeres de grupos de disponibilidad AlwaysOn para la actualización del sistema operativo](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="fe009-107">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fe009-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fe009-108">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="fe009-109">Cambie el contexto de clúster de HADR solo durante la migración entre clústeres de implementaciones [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe009-109">Switch the HADR cluster context only during cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] deployments.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fe009-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fe009-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fe009-111">Solo puede cambiar el contexto de clúster de HADR desde el clúster local de WSFC a un clúster remoto y viceversa.</span><span class="sxs-lookup"><span data-stu-id="fe009-111">You can switch the HADR cluster context only from the local WSFC cluster to a remote cluster and then back from the remote cluster to the local cluster.</span></span> <span data-ttu-id="fe009-112">No puede cambiar el contexto de clúster de HADR desde un clúster remoto a otro clúster remoto.</span><span class="sxs-lookup"><span data-stu-id="fe009-112">You cannot switch the HADR cluster context from one remote cluster to another remote cluster.</span></span>  
  
-   <span data-ttu-id="fe009-113">El contexto de clúster de HADR se puede cambiar a un clúster remoto solo cuando la instancia de SQL Server no hospeda ninguna réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fe009-113">The HADR cluster context can be switched to a remote cluster only when the instance of SQL Server is not hosting any availability replicas.</span></span>  
  
-   <span data-ttu-id="fe009-114">Un contexto de clúster de HADR remoto se puede volver a cambiar al clúster local en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="fe009-114">A remote HADR cluster context can be switched back to the local cluster at any time.</span></span> <span data-ttu-id="fe009-115">Sin embargo, el contexto no se puede cambiar de nuevo si la instancia de servidor hospeda réplicas de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fe009-115">However, the context cannot be switched again as long as the server instance is hosting any availability replicas.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="fe009-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fe009-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="fe009-117">La instancia de servidor en la que se cambia el contexto de clúster de HADR debe ejecutar [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] o superior (edición Enterprise o superior).</span><span class="sxs-lookup"><span data-stu-id="fe009-117">The server instance on which you change the HADR cluster context must be running [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="fe009-118">La instancia de servidor debe estar habilitada para AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="fe009-118">The server instance must be enabled for AlwaysOn.</span></span> <span data-ttu-id="fe009-119">Para obtener más información, vea [Habilitar y deshabilitar grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fe009-119">For more information, see [Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="fe009-120">Para que se pueda cambiar de contexto de clúster local a un clúster remoto, una instancia de servidor no puede hospedar ninguna réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fe009-120">To be eligible to be switched from the local cluster context to a remote cluster cluster, a server instance cannot be hosting any availability replicas.</span></span> <span data-ttu-id="fe009-121">La vista de catálogo [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) no debe devolver ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="fe009-121">The [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) catalog view should not return any rows.</span></span>  
  
     <span data-ttu-id="fe009-122">Si existe alguna réplica de disponibilidad en la instancia de servidor, antes de poder cambiar el contexto de clúster de HADR debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe009-122">If any availability replicas exist on the server instance, before you can change the HADR cluster context, you must do one of the following:</span></span>  
  
    |<span data-ttu-id="fe009-123">Rol de réplica</span><span class="sxs-lookup"><span data-stu-id="fe009-123">Replica Role</span></span>|<span data-ttu-id="fe009-124">Acción</span><span class="sxs-lookup"><span data-stu-id="fe009-124">Action</span></span>|<span data-ttu-id="fe009-125">Vínculo</span><span class="sxs-lookup"><span data-stu-id="fe009-125">Link</span></span>|  
    |------------------|------------|----------|  
    |<span data-ttu-id="fe009-126">Principal</span><span class="sxs-lookup"><span data-stu-id="fe009-126">Primary</span></span>|<span data-ttu-id="fe009-127">Deja sin conexión el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fe009-127">Take the availability group offline.</span></span>|[<span data-ttu-id="fe009-128">Poner sin conexión un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe009-128">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)|  
    |<span data-ttu-id="fe009-129">Secundario</span><span class="sxs-lookup"><span data-stu-id="fe009-129">Secondary</span></span>|<span data-ttu-id="fe009-130">Quitar la réplica de su grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="fe009-130">Remove the replica from its availability group</span></span>|[<span data-ttu-id="fe009-131">Quitar una réplica secundaria de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe009-131">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)|  
  
-   <span data-ttu-id="fe009-132">Antes de poder cambiar de un clúster remoto al clúster local, todas las réplicas con confirmación sincrónica deben estar en el estado SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="fe009-132">Before you can switch from a remote cluster to the local cluster, all synchronous-commit replicas must be SYNCHRONIZED.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="fe009-133">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="fe009-133">Recommendations</span></span>  
  
-   <span data-ttu-id="fe009-134">Se recomienda especificar el nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="fe009-134">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="fe009-135">Esto es porque para buscar la dirección IP de destino de un nombre corto, ALTER SERVER CONFIGURATION usa la resolución de DNS.</span><span class="sxs-lookup"><span data-stu-id="fe009-135">This is because to find the target IP address of a short name, ALTER SERVER CONFIGURATION uses DNS resolution.</span></span> <span data-ttu-id="fe009-136">En algunas situaciones, en función del orden de búsqueda de DNS, el uso de un nombre corto puede producir confusiones.</span><span class="sxs-lookup"><span data-stu-id="fe009-136">Under some situations, depending on the DNS searching order, using a short name could cause confusion.</span></span> <span data-ttu-id="fe009-137">Por ejemplo, considere el comando siguiente, que se ejecuta en un nodo del dominio `abc` (`node1.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="fe009-137">For example, consider the following command, which is executed on a node in the `abc` domain, (`node1.abc.com`).</span></span> <span data-ttu-id="fe009-138">El clúster de destino previsto es el clúster `CLUS01` del dominio `xyz` (`clus01.xyz.com`).</span><span class="sxs-lookup"><span data-stu-id="fe009-138">The intended destination cluster is the `CLUS01` cluster in the `xyz` domain (`clus01.xyz.com`).</span></span> <span data-ttu-id="fe009-139">Sin embargo, el dominio local hospeda también un clúster denominado `CLUS01` (`clus01.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="fe009-139">However, the local  domain hosts also hosts a cluster named `CLUS01` (`clus01.abc.com`).</span></span>  
  
     <span data-ttu-id="fe009-140">Si se especificara el nombre corto del clúster de destino, `CLUS01`, la resolución de nombres DNS podría devolver la dirección IP del clúster erróneo, `clus01.abc.com`.</span><span class="sxs-lookup"><span data-stu-id="fe009-140">If the short name of the target cluster, `CLUS01`, were specified, DNS name resolution could return the IP address of the wrong cluster, `clus01.abc.com`.</span></span> <span data-ttu-id="fe009-141">Para evitar esa confusión, especifique el nombre completo del clúster de destino, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe009-141">To avoid such confusion, specify the full name of the target cluster, as in the following example:</span></span>  
  
    ```  
    ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com'  
    ```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fe009-142">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fe009-142">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fe009-143">Permisos</span><span class="sxs-lookup"><span data-stu-id="fe009-143">Permissions</span></span>  
  
-   <span data-ttu-id="fe009-144">**inicio de sesión de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="fe009-144">**SQL Server login**</span></span>  
  
     <span data-ttu-id="fe009-145">Requiere el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="fe009-145">Requires CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="fe009-146">**SQL Server cuenta de servicio**</span><span class="sxs-lookup"><span data-stu-id="fe009-146">**SQL Server service account**</span></span>  
  
     <span data-ttu-id="fe009-147">La cuenta de servicio de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de la instancia de servidor debe tener:</span><span class="sxs-lookup"><span data-stu-id="fe009-147">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account of the server instance must have:</span></span>  
  
    -   <span data-ttu-id="fe009-148">Permiso para abrir el clúster de destino de WSFC.</span><span class="sxs-lookup"><span data-stu-id="fe009-148">Permission to open the destination WSFC cluster.</span></span>  
  
    -   <span data-ttu-id="fe009-149">Acceso remoto de lectura y escritura de WSFC.</span><span class="sxs-lookup"><span data-stu-id="fe009-149">Remote WSFC read-write access.</span></span>  
  
 
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fe009-150">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe009-150">Using Transact-SQL</span></span>  
 <span data-ttu-id="fe009-151">**Para cambiar el contexto de clúster de WSFC de una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="fe009-151">**To change the WSFC cluster context of an availability replica**</span></span>  
  
1.  <span data-ttu-id="fe009-152">Conéctese a la instancia de servidor que hospeda la réplica principal o una réplica secundaria del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fe009-152">Connect to the server instance that hosts either the primary replica or a secondary replica of the availability group.</span></span>  
  
2.  <span data-ttu-id="fe009-153">Use la cláusula SET HADR CLUSTER CONTEXT de la instrucción [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) , de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe009-153">Use the SET HADR CLUSTER CONTEXT clause of the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="fe009-154">ALTER SERVER CONFIGURATION SET HADR CLUSTER context **=** { **' *`windows_cluster`* '** | LOCALIZAR</span><span class="sxs-lookup"><span data-stu-id="fe009-154">ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT **=** { **'*`windows_cluster`*'** | LOCAL }</span></span>  
  
     <span data-ttu-id="fe009-155">donde,</span><span class="sxs-lookup"><span data-stu-id="fe009-155">where,</span></span>  
  
     <span data-ttu-id="fe009-156">*windows_cluster*</span><span class="sxs-lookup"><span data-stu-id="fe009-156">*windows_cluster*</span></span>  
     <span data-ttu-id="fe009-157">Nombre de objeto de clúster (CON) de un clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="fe009-157">The cluster object name (CON) of a WSFC cluster.</span></span> <span data-ttu-id="fe009-158">Puede especificar el nombre corto o el nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="fe009-158">You can specify either the short name or the full domain name.</span></span> <span data-ttu-id="fe009-159">Se recomienda especificar el nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="fe009-159">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="fe009-160">Para obtener más información, vea [recomendaciones](#Recommendations), anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="fe009-160">For more information, see [Recommendations](#Recommendations), earlier in this topic.</span></span>  
  
     <span data-ttu-id="fe009-161">LOCAL</span><span class="sxs-lookup"><span data-stu-id="fe009-161">LOCAL</span></span>  
     <span data-ttu-id="fe009-162">Clúster local de WSFC.</span><span class="sxs-lookup"><span data-stu-id="fe009-162">The local WSFC cluster.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="fe009-163">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fe009-163">Examples</span></span>  
 <span data-ttu-id="fe009-164">En el ejemplo siguiente se cambia el contexto de clúster de HADR otro clúster diferente.</span><span class="sxs-lookup"><span data-stu-id="fe009-164">The following example changes the HADR cluster context to a different cluster.</span></span> <span data-ttu-id="fe009-165">Para identificar el clúster de destino de WSFC, `clus01`, el ejemplo especifica el nombre de objeto completo del clúster, `clus01.xyz.com`.</span><span class="sxs-lookup"><span data-stu-id="fe009-165">To identify the destination WSFC cluster, `clus01`, the example specifies the full cluster object name, `clus01.xyz.com`.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com';  
```  
  
 <span data-ttu-id="fe009-166">En el ejemplo siguiente se cambia el contexto de clúster de HADR al clúster local de WSFC.</span><span class="sxs-lookup"><span data-stu-id="fe009-166">The following example changes the HADR cluster context to the local WSFC cluster.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = LOCAL;  
```  
  

  
##  <a name="follow-up-after-switching-the-cluster-context-of-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="fe009-167">Seguimiento: Después de cambiar el contexto de clúster de una réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="fe009-167">Follow Up: After Switching the Cluster Context of an Availability Replica</span></span>  
 <span data-ttu-id="fe009-168">El nuevo contexto de clúster de HADR surte efecto inmediatamente, sin necesidad de reiniciar la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="fe009-168">The new HADR cluster context takes effect immediately, without restarting the server instance.</span></span> <span data-ttu-id="fe009-169">El valor de contexto del clúster de HADR es una configuración persistente de nivel de instancia que permanece sin modificar si se reinicia la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="fe009-169">The HADR cluster context setting is a persistent instance-level setting that remains unchanged if the server instance restarts.</span></span>  
  
 <span data-ttu-id="fe009-170">Confirme el nuevo contexto de clúster de HADR consultando la vista de administración dinámica [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) , de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe009-170">Confirm the new HADR cluster context by querying the [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) dynamic management view, as follows:</span></span>  
  
```  
SELECT cluster_name FROM sys.dm_hadr_cluster  
```  
  
 <span data-ttu-id="fe009-171">Esta consulta debe devolver el nombre del clúster al que se establece el contexto de clúster de HADR.</span><span class="sxs-lookup"><span data-stu-id="fe009-171">This query should return the name of the cluster to which you set the HADR cluster context.</span></span>  
  
 <span data-ttu-id="fe009-172">Cuando el contexto de clúster de HADR se cambia a un nuevo clúster:</span><span class="sxs-lookup"><span data-stu-id="fe009-172">When the HADR cluster context is switched to a new cluster:</span></span>  
  
-   <span data-ttu-id="fe009-173">Los metadatos se limpian para quitar cualquier réplicas de disponibilidad que están hospedadas actualmente en la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe009-173">The metadata is cleaned up for any availability replicas that are currently hosted by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="fe009-174">Todas las bases de datos que pertenecieron previamente a una réplica de disponibilidad están ahora en el estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="fe009-174">All the databases that previously belonged to an availability replica are now in the RESTORING state.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fe009-175">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="fe009-175">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fe009-176">Quitar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe009-176">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="fe009-177">Poner sin conexión un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe009-177">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
-   [<span data-ttu-id="fe009-178">Agregar una réplica secundaria a un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe009-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="fe009-179">Quitar una réplica secundaria de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe009-179">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="fe009-180">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe009-180">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="fe009-181">Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe009-181">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
 
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="fe009-182">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="fe009-182">Related Content</span></span>  
  
-   <span data-ttu-id="fe009-183">[Artículos técnicos de SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fe009-183">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="fe009-184">Blog del equipo de AlwaysOn de SQL Server: el blog del equipo de AlwaysOn oficial de SQL Server</span><span class="sxs-lookup"><span data-stu-id="fe009-184">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="fe009-185">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe009-185">See Also</span></span>  
 <span data-ttu-id="fe009-186">[Clústeres de conmutación por error de Windows Server de](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) [grupos de disponibilidad AlwaysOn (SQL Server)](always-on-availability-groups-sql-server.md) &#40;WSFC&#41; con SQL Server </span><span class="sxs-lookup"><span data-stu-id="fe009-186">[AlwaysOn Availability Groups (SQL Server)](always-on-availability-groups-sql-server.md) [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="fe009-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fe009-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-server-configuration-transact-sql)  
  
  
