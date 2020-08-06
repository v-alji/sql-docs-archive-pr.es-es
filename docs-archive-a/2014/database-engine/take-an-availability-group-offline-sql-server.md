---
title: Alter Availability Group offline
description: Pasos para configurar el grupo de disponibilidad de Always On sin conexión
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], take offline
ms.assetid: 50f5aad8-0dff-45ef-8350-f9596d3db898
author: rothja
ms.author: jroth
ms.openlocfilehash: db2f56befe6905b9c3de6bd1ab6a2e5a4a00b1b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673872"
---
# <a name="take-an-availability-group-offline-sql-server"></a><span data-ttu-id="f52fc-103">Poner sin conexión un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f52fc-103">Take an Availability Group Offline (SQL Server)</span></span>
  <span data-ttu-id="f52fc-104">En este tema se describe cómo pasar un grupo de disponibilidad AlwaysOn del estado ONLINE el estado OFFLINE mediante [!INCLUDE[tsql](../includes/tsql-md.md)] en [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f52fc-104">This topic describes how to take an AlwaysOn availability group from the ONLINE state to the OFFLINE state by using [!INCLUDE[tsql](../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="f52fc-105">No se produce ninguna pérdida de datos en las bases de datos con confirmación sincrónica porque si alguna réplica con confirmación sincrónica no está sincronizada, la operación OFFLINE produce un error y deja el grupo de disponibilidad en el estado ONLINE.</span><span class="sxs-lookup"><span data-stu-id="f52fc-105">There is no data loss for synchronous-commit databases because if any synchronous-commit replica is not synchronized, the OFFLINE operation raises an error and leaves the availability group ONLINE.</span></span> <span data-ttu-id="f52fc-106">Mantener el grupo de disponibilidad en línea protege las bases de datos con confirmación sincrónica no sincronizadas frente a posibles pérdidas de datos.</span><span class="sxs-lookup"><span data-stu-id="f52fc-106">Keeping the availability group online protects unsynchronized synchronous-commit databases from possible data loss.</span></span> <span data-ttu-id="f52fc-107">Cuando un grupo de disponibilidad pasa a estar sin conexión, sus bases de datos dejan de estar disponibles para los clientes y no puede volver a poner el grupo de disponibilidad en línea.</span><span class="sxs-lookup"><span data-stu-id="f52fc-107">After an availability group goes offline, its databases become unavailable to clients and you cannot bring the availability group back online.</span></span> <span data-ttu-id="f52fc-108">Por tanto, ponga un grupo de disponibilidad sin conexión únicamente para migrar los recursos del grupo de disponibilidad de un clúster de WSFC a otro.</span><span class="sxs-lookup"><span data-stu-id="f52fc-108">Therefore, take an availability group offline only to migrate the availability group resources from one WSFC cluster to another.</span></span>  
  
 <span data-ttu-id="f52fc-109">Si durante una migración entre clústeres de [!INCLUDE[ssHADR](../includes/sshadr-md.md)]algunas aplicaciones se conectan directamente a la réplica principal de un grupo de disponibilidad, se debe poner sin conexión el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f52fc-109">During a cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)], if any applications connect directly to the primary replica of an availability group, the availability group must be taken offline.</span></span> <span data-ttu-id="f52fc-110">La migración entre clústeres de [!INCLUDE[ssHADR](../includes/sshadr-md.md)] admite la actualización del sistema operativo con un tiempo de inactividad mínimo de los grupos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f52fc-110">Cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] supports OS upgrade with minimal downtime of availability groups.</span></span> <span data-ttu-id="f52fc-111">El escenario habitual es usar la migración entre clústeres de [!INCLUDE[ssHADR](../includes/sshadr-md.md)] para actualizar el sistema operativo a [!INCLUDE[win8](../includes/win8-md.md)] o a [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f52fc-111">The typical scenario is to use cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] for OS upgrade to [!INCLUDE[win8](../includes/win8-md.md)] or [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span></span> <span data-ttu-id="f52fc-112">Para obtener más información, vea [Migración entre clústeres de grupos de disponibilidad AlwaysOn para la actualización del sistema operativo](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="f52fc-112">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f52fc-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f52fc-113">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f52fc-114">Use la opción OFFLINE solo para realizar una migración entre clústeres de los recursos de un grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f52fc-114">Use the OFFLINE option only for a cross-cluster migration of availability group resources.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f52fc-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f52fc-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="f52fc-116">La instancia de servidor en la que se escribe el comando OFFLINE debe ejecutar [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] o superior (edición Enterprise o superior).</span><span class="sxs-lookup"><span data-stu-id="f52fc-116">The server instance on which you enter the OFFLINE command must be running [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="f52fc-117">El grupo de disponibilidad debe estar actualmente en línea.</span><span class="sxs-lookup"><span data-stu-id="f52fc-117">The availability group must currently be online.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f52fc-118">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="f52fc-118">Recommendations</span></span>  
 <span data-ttu-id="f52fc-119">Antes de poner el grupo de disponibilidad sin conexión, elimine el agente o los agentes de escucha del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f52fc-119">Before you take the availability group offline, delete the availability group listener or listeners.</span></span> <span data-ttu-id="f52fc-120">Para obtener más información, vea [Quitar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f52fc-120">For more information, see [Remove an Availability Group Listener &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f52fc-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f52fc-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f52fc-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="f52fc-122">Permissions</span></span>  
 <span data-ttu-id="f52fc-123">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="f52fc-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f52fc-124">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f52fc-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="f52fc-125">**Para poner sin conexión un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="f52fc-125">**To take an availability group offline**</span></span>  
  
1.  <span data-ttu-id="f52fc-126">Conéctese a una instancia de servidor que hospede una réplica de disponibilidad para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f52fc-126">Connect to a server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="f52fc-127">Esta réplica puede ser la réplica principal o una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="f52fc-127">This replica can be the primary replica or a secondary replica.</span></span>  
  
2.  <span data-ttu-id="f52fc-128">Use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="f52fc-128">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="f52fc-129">ALTER AVAILABILITY GROUP *group_name* OFFLINE</span><span class="sxs-lookup"><span data-stu-id="f52fc-129">ALTER AVAILABILITY GROUP *group_name* OFFLINE</span></span>  
  
     <span data-ttu-id="f52fc-130">donde *group_name* es el nombre del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f52fc-130">where *group_name* is the name of the availability group.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f52fc-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f52fc-131">Example</span></span>  
 <span data-ttu-id="f52fc-132">En el ejemplo siguiente se pone sin conexión el grupo de disponibilidad `AccountsAG` .</span><span class="sxs-lookup"><span data-stu-id="f52fc-132">The following example takes the `AccountsAG` availability group offline.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AccountsAG OFFLINE;  
```  
  
##  <a name="follow-up-after-the-availability-group-goes-offline"></a><a name="FollowUp"></a> <span data-ttu-id="f52fc-133">Seguimiento: Después de que el grupo de disponibilidad esté sin conexión</span><span class="sxs-lookup"><span data-stu-id="f52fc-133">Follow Up: After the Availability Group Goes Offline</span></span>  
  
-   <span data-ttu-id="f52fc-134">**Registro de operación OFFLINE:**  La identidad del nodo de WSFC donde se ha iniciado la operación OFFLINE se almacena tanto en el registro de clúster de WSFC como en el registro de errores de SQL.</span><span class="sxs-lookup"><span data-stu-id="f52fc-134">**Logging of OFFLINE operation:**  The identity of the WSFC node where the OFFLINE operation was initiated is stored in both the WSFC cluster log and the SQL ERRORLOG.</span></span>  
  
-   <span data-ttu-id="f52fc-135">**En el caso de que no se eliminara la escucha del grupo de disponibilidad antes de dejar a este último sin conexión:**  si va a migrar el grupo de disponibilidad a otro clúster WSFC, elimine el VNN y el VIP del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="f52fc-135">**If you did not delete the availability group listener before taking the group offline:**  If you are migrating the availability group to another WSFC cluster, delete the VNN and VIP of the listener.</span></span> <span data-ttu-id="f52fc-136">Puede eliminarlos mediante la consola Administración del clúster de conmutación por error, el cmdlet [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) de PowerShell o [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="f52fc-136">You can delete them by using either the Failover Cluster Management console, the [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) PowerShell cmdlet, or [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span></span> <span data-ttu-id="f52fc-137">Tenga en cuenta que cluster.exe está desusado en Windows 8.</span><span class="sxs-lookup"><span data-stu-id="f52fc-137">Note that cluster.exe is deprecated on Windows 8.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f52fc-138">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="f52fc-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f52fc-139">Quitar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f52fc-139">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](availability-groups/windows/remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="f52fc-140">Cambiar el contexto de clúster de HADR de la instancia de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f52fc-140">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](availability-groups/windows/change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="f52fc-141">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f52fc-141">Related Content</span></span>  
  
-   <span data-ttu-id="f52fc-142">[Artículos técnicos de SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f52fc-142">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="f52fc-143">Blog del equipo de AlwaysOn de SQL Server: el blog del equipo de AlwaysOn oficial de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f52fc-143">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
## <a name="see-also"></a><span data-ttu-id="f52fc-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f52fc-144">See Also</span></span>  
 [<span data-ttu-id="f52fc-145">Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f52fc-145">AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/always-on-availability-groups-sql-server.md)  
