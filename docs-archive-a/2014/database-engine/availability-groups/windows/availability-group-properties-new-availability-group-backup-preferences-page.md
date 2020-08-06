---
title: 'Propiedades de grupo de disponibilidad: nuevo grupo de disponibilidad (página Preferencias de copia de seguridad) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.backuppreferences.f1
helpviewer_keywords:
- read-only routing
ms.assetid: 65fff22d-5963-4a8c-8b31-fe9ab247a03e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7914d4b1d7af06bcaf4f3fd05a260138e3edf5fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663130"
---
# <a name="availability-group-properties-new-availability-group-backup-preferences-page"></a><span data-ttu-id="e1c8d-102">Propiedades del grupo de disponibilidad: Nuevo grupo de disponibilidad (página Preferencias de copia de seguridad)</span><span class="sxs-lookup"><span data-stu-id="e1c8d-102">Availability Group Properties: New Availability Group (Backup Preferences Page)</span></span>
  <span data-ttu-id="e1c8d-103">Utilice este cuadro de diálogo para ver y cambiar las preferencias de copia de seguridad del grupo de disponibilidad seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-103">Use this dialog box to view and change the backup preferences of the selected availability group.</span></span>  
  
 <span data-ttu-id="e1c8d-104">**Para ver las propiedades del grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="e1c8d-104">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="e1c8d-105">Ver las propiedades del grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e1c8d-105">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="e1c8d-106">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e1c8d-106">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="where-should-backups-occur"></a><span data-ttu-id="e1c8d-107">¿Dónde deben realizarse las copias de seguridad?</span><span class="sxs-lookup"><span data-stu-id="e1c8d-107">Where should backups occur?</span></span>  
 <span data-ttu-id="e1c8d-108">**Preferir secundaria**</span><span class="sxs-lookup"><span data-stu-id="e1c8d-108">**Prefer Secondary**</span></span>  
 <span data-ttu-id="e1c8d-109">Especifica que las copias de seguridad se deben realizar en una réplica secundaria a menos que la réplica principal sea la única réplica en línea.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-109">Specifies that backups should occur on a secondary replica except when the primary replica is the only replica online.</span></span> <span data-ttu-id="e1c8d-110">En ese caso, la copia de seguridad se debe realizar en la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-110">In that case, the backup should occur on the primary replica.</span></span> <span data-ttu-id="e1c8d-111">Ésta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-111">This is the default option.</span></span>  
  
 <span data-ttu-id="e1c8d-112">**Solo secundaria**</span><span class="sxs-lookup"><span data-stu-id="e1c8d-112">**Secondary only**</span></span>  
 <span data-ttu-id="e1c8d-113">Especifica que las copias de seguridad no deben realizarse nunca en la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-113">Specifies that backups should never be performed on the primary replica.</span></span> <span data-ttu-id="e1c8d-114">Si la réplica principal es la única réplica en línea, no se debe realizar la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-114">If the primary replica is the only replica online, the backup should not occur.</span></span>  
  
 <span data-ttu-id="e1c8d-115">**Principal**</span><span class="sxs-lookup"><span data-stu-id="e1c8d-115">**Primary**</span></span>  
 <span data-ttu-id="e1c8d-116">Especifica que las copias de seguridad deben realizarse siempre en la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-116">Specifies that the backups should always occur on the primary replica.</span></span> <span data-ttu-id="e1c8d-117">Esta opción es útil si necesita usar características de copia de seguridad, como crear copias de seguridad diferenciales, que no se admiten cuando la copia de seguridad se ejecuta en una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-117">This option is useful if you need backup features, such as creating differential backups, that are not supported when backup is run on a secondary replica.</span></span>  
  
 <span data-ttu-id="e1c8d-118">**Cualquier réplica**</span><span class="sxs-lookup"><span data-stu-id="e1c8d-118">**Any Replica**</span></span>  
 <span data-ttu-id="e1c8d-119">Especifica que, de acuerdo con sus preferencias, los trabajos de copia de seguridad omitan el rol de las réplicas de disponibilidad cuando la réplica realiza copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-119">Specifies that you prefer that backup jobs ignore the role of the availability replicas when choosing the replica to perform backups.</span></span> <span data-ttu-id="e1c8d-120">Tenga en cuenta que los trabajos de copia de seguridad pueden evaluar otros factores, como la prioridad de copia de seguridad de cada réplica de disponibilidad junto con su estado operativo y de conexión.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-120">Note backup jobs might evaluate other factors such as backup priority of each availability replica in combination with its operational state and connected state.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e1c8d-121">No se aplica el valor de preferencia de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-121">There is no enforcement of the backup-preference setting.</span></span> <span data-ttu-id="e1c8d-122">La interpretación de esta preferencia depende de la lógica, si existe, del script con los trabajos de copia de seguridad ejecutado para las bases de datos de un grupo de disponibilidad dado.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-122">The interpretation of this preference depends on the logic, if any, that you script into back jobs for the databases in a given availability group.</span></span> <span data-ttu-id="e1c8d-123">Para obtener más información, vea [secundarias activas: copia de seguridad en las réplicas secundarias (grupos de disponibilidad AlwaysOn)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e1c8d-123">For more information, see [Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
## <a name="replica-backup-priorities"></a><span data-ttu-id="e1c8d-124">Prioridades de copia de seguridad de réplica</span><span class="sxs-lookup"><span data-stu-id="e1c8d-124">Replica backup priorities</span></span>  
 <span data-ttu-id="e1c8d-125">Esta cuadrícula muestra la prioridad de copia de seguridad actual de cada instancia de servidor que hospeda una réplica para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-125">This grid displays the current backup priority of each server instance that hosts a replica for the availability group.</span></span> <span data-ttu-id="e1c8d-126">Utilice esta cuadrícula para cambiar la prioridad de copia de seguridad de una o varias réplicas de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-126">Use this grid to change the backup priority of one or more availability replicas.</span></span>  
  
 <span data-ttu-id="e1c8d-127">**Instancia del servidor**</span><span class="sxs-lookup"><span data-stu-id="e1c8d-127">**Server Instance**</span></span>  
 <span data-ttu-id="e1c8d-128">El nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-128">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span>  
  
 <span data-ttu-id="e1c8d-129">**Prioridad de copia de seguridad (Mínima=1, Máxima=100)**</span><span class="sxs-lookup"><span data-stu-id="e1c8d-129">**Backup Priority (Lowest=1, Highest=100)**</span></span>  
 <span data-ttu-id="e1c8d-130">Especifica la prioridad para realizar copias de seguridad en esta réplica en relación con las otras réplicas del mismo grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-130">Specifies your priority for performing backups on this replica relative to the other replicas in the same availability group.</span></span> <span data-ttu-id="e1c8d-131">El valor es un número entero en el intervalo de 0..100.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-131">The value is an integer in the range of 0..100.</span></span> <span data-ttu-id="e1c8d-132">1 indica la prioridad mínima y 100 indica la prioridad máxima.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-132">1 indicates the lowest priority, and 100 indicates the highest priority.</span></span> <span data-ttu-id="e1c8d-133">Si **Prioridad de copia de seguridad** = 1, la réplica de disponibilidad se elegiría para realizar copias de seguridad solamente si no hay disponibles actualmente réplicas de disponibilidad con mayor prioridad.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-133">If **Backup Priority** = 1, the availability replica would be chosen for performing backups only if no higher priority availability replicas are currently available.</span></span>  
  
 <span data-ttu-id="e1c8d-134">**Excluir réplica**</span><span class="sxs-lookup"><span data-stu-id="e1c8d-134">**Exclude Replica**</span></span>  
 <span data-ttu-id="e1c8d-135">Seleccione esta opción si no desea que nunca se elija esta réplica de disponibilidad para realizar copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-135">Select if you never want this availability replica to be chosen for performing backups.</span></span> <span data-ttu-id="e1c8d-136">Esto es útil, por ejemplo, para una réplica de disponibilidad remota en la que no desee nunca realizar la conmutación por error para las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e1c8d-136">This is useful, for example, for a remote availability replica to which you never want backups to fail over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c8d-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1c8d-137">See Also</span></span>  
 <span data-ttu-id="e1c8d-138">[Secundarias activas: copia de seguridad en las réplicas secundarias (Grupos de disponibilidad AlwaysOn)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="e1c8d-138">[Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="e1c8d-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e1c8d-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
