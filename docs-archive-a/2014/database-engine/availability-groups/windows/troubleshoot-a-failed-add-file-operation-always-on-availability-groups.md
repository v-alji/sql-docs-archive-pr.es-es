---
title: Solucionar problemas de una operación de agregar archivos con error (Grupos de disponibilidad AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary databases [SQL Server], Availability Groups
- Availability Groups [SQL Server], troubleshooting
ms.assetid: 31ceaebf-864b-4dd0-9112-0d047b0316ad
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2551080c214f18473caa71a3e17797c34fcc943a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750169"
---
# <a name="troubleshoot-a-failed-add-file-operation-alwayson-availability-groups"></a><span data-ttu-id="0fa3f-102">Solucionar problemas relativos a una operación de agregar archivos con error (grupos de disponibilidad AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="0fa3f-102">Troubleshoot a Failed Add-File Operation (AlwaysOn Availability Groups)</span></span>
  <span data-ttu-id="0fa3f-103">En algunas implementaciones de grupos de disponibilidad AlwaysOn, las rutas de acceso difieren entre el sistema que hospeda la réplica principal y los sistemas que hospedan una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-103">In some AlwaysOn availability group deployments, file paths differ between the system that hosts the primary replica and systems that host a secondary replica.</span></span> <span data-ttu-id="0fa3f-104">Si la ruta de acceso a un archivo de una operación add-file no existe en una replicación secundaria, la operación add-file se realizará correctamente en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-104">If the file path of an add-file operation does not exist on a secondary replica, the add-file operation will succeed on the primary database.</span></span> <span data-ttu-id="0fa3f-105">Pero la operación add-file ocasionará la suspensión de la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-105">But the add-file operation will cause the secondary database to be suspended.</span></span> <span data-ttu-id="0fa3f-106">Esto, a su vez, hace que la réplica secundaria entre en el estado NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-106">This, in turn, causes the secondary replica to enter the NOT SYNCHRONIZING state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0fa3f-107">Se recomienda que, si es posible, la ruta de acceso de archivo (incluida la letra de unidad) de una base de datos secundaria determinada sea idéntica a la de la base de datos principal correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-107">We recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span>  
  
## <a name="problem-resolution"></a><span data-ttu-id="0fa3f-108">Resolución de problemas</span><span class="sxs-lookup"><span data-stu-id="0fa3f-108">Problem Resolution</span></span>  
 <span data-ttu-id="0fa3f-109">Para resolver este problema, el propietario debe completar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0fa3f-109">To resolve this problem the database owner must complete the following steps:</span></span>  
  
1.  <span data-ttu-id="0fa3f-110">Quitar la base de datos secundaria del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-110">Remove the secondary database from the availability group.</span></span> <span data-ttu-id="0fa3f-111">Para obtener más información, vea [Quitar una base de datos secundaria de un grupo de disponibilidad &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0fa3f-111">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="0fa3f-112">En la base de datos secundaria existente, restaurar una copia de seguridad completa del grupo de archivos que contenga el archivo agregado a la base de datos secundaria, mediante WITH NORECOVERY y WITH MOVE (que especifica la ruta de acceso en la instancia del servidor que hospeda la réplica secundaria).</span><span class="sxs-lookup"><span data-stu-id="0fa3f-112">On the existing secondary database, restore a full backup of the filegroup that contains the added file to the secondary database, using WITH NORECOVERY and WITH MOVE (specifying the file path on the server instance that hosts the secondary replica).</span></span> <span data-ttu-id="0fa3f-113">Para obtener más información, vea [Restaurar una base de datos a una nueva ubicación &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0fa3f-113">For more information, see [Restore a Database to a New Location &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="0fa3f-114">Realizar una copia de seguridad del registro de transacciones que contenga la operación de agregar archivos en la base de datos principal, y restaurar manualmente la copia de seguridad de registros en la base de datos secundaria mediante WITH NORECOVERY y WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-114">Back up the transaction log that contains the add-file operation on the primary database, and manually restore the log backup on the secondary database using WITH NORECOVERY and WITH MOVE.</span></span>  
  
4.  <span data-ttu-id="0fa3f-115">Preparar la base de datos secundaria para volver a unirse al grupo de disponibilidad, restaurando, WITH NO RECOVERY, cualquier otra copia de seguridad de registros pendiente de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-115">Prepare the secondary database for re-joining the availability group, by restoring, WITH NO RECOVERY, any other outstanding log backups from the primary database.</span></span>  
  
5.  <span data-ttu-id="0fa3f-116">Volver a unir la base de datos secundaria al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-116">Rejoin the secondary database to the availability group.</span></span> <span data-ttu-id="0fa3f-117">Para obtener más información, vea [Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0fa3f-117">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa3f-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0fa3f-118">See Also</span></span>  
 <span data-ttu-id="0fa3f-119">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0fa3f-119">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="0fa3f-120">[Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0fa3f-120">[Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="0fa3f-121">[Solucionar problemas de usuarios huérfanos &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0fa3f-121">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 [<span data-ttu-id="0fa3f-122">Solucionar problemas de Grupos de disponibilidad AlwaysOn &#40;de configuración de SQL Server&#41;eliminado</span><span class="sxs-lookup"><span data-stu-id="0fa3f-122">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
  
