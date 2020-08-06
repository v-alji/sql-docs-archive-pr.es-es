---
title: Copia de seguridad no actualizada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 307a4ad0-675a-4f97-9a3c-cedd61bdfae5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c6a944b08b15d591a9bbce47a0c0c6a8de3eb54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674767"
---
# <a name="outdated-backup"></a><span data-ttu-id="ade1c-102">Copia de seguridad no actualizada</span><span class="sxs-lookup"><span data-stu-id="ade1c-102">Outdated Backup</span></span>
  <span data-ttu-id="ade1c-103">Esta regla comprueba que una base de datos tiene copias de seguridad recientes.</span><span class="sxs-lookup"><span data-stu-id="ade1c-103">This rule checks that a database has recent backups.</span></span> <span data-ttu-id="ade1c-104">Programar copias de seguridad regulares es importante para proteger las bases de datos contra la pérdida de datos que provocan numerosos errores diferentes.</span><span class="sxs-lookup"><span data-stu-id="ade1c-104">Scheduling regular backups is important for protecting your databases against data loss from many different failures.</span></span> <span data-ttu-id="ade1c-105">La frecuencia adecuada para la copia de seguridad de los datos depende del modelo de recuperación de la base de datos, de los requisitos comerciales sobre la pérdida de datos potencial y de la frecuencia con que se actualiza la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ade1c-105">The appropriate frequency for backing up data depends on the recovery model of the database, on business requirements about potential data loss, and on how frequently the database is updated.</span></span> <span data-ttu-id="ade1c-106">En una base de datos actualizada frecuentemente, el riesgo de perder parte del trabajo aumenta con bastante rapidez entre las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ade1c-106">In a frequently updated database, the work-loss exposure increases fairly quickly between backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="ade1c-107">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="ade1c-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="ade1c-108">Recomendamos que realice frecuentemente suficientes copias de seguridad para proteger las bases de datos contra la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="ade1c-108">We recommend that you perform backups frequently enough to protect databases against data loss.</span></span>  
  
 <span data-ttu-id="ade1c-109">El modelo de recuperación simple y el modelo de recuperación completa requieren ambos copias de seguridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="ade1c-109">The simple recovery model and full recovery model both require data backups.</span></span> <span data-ttu-id="ade1c-110">En cualquier modelo de recuperación puede complementar las copias de seguridad completas con copias de seguridad diferenciales para reducir eficazmente el riesgo de pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="ade1c-110">For either recovery model, you can supplement your full backups with differential backups to efficiently reduce the risk of data loss.</span></span>  
  
 <span data-ttu-id="ade1c-111">En una base de datos que use el modelo de recuperación completa, recomendamos que realice copias de seguridad del registro con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="ade1c-111">For a database that uses the full recovery model, we recommend that you take frequent log backups.</span></span> <span data-ttu-id="ade1c-112">En una base de datos de producción que contiene datos muy importantes, las copias de seguridad del registro normalmente se realizarían en intervalos de entre uno y quince minutos.</span><span class="sxs-lookup"><span data-stu-id="ade1c-112">For a production database that contains very important data, log backups would typically be taken every one to fifteen minutes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ade1c-113">El método recomendado para programar las copias de seguridad es un plan de mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ade1c-113">The recommended method for scheduling backups is a database maintenance plan.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ade1c-114">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="ade1c-114">For More Information</span></span>  
 [<span data-ttu-id="ade1c-115">Realizar copias de seguridad y restaurar bases de datos del sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ade1c-115">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="ade1c-116">Modelos de recuperación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ade1c-116">Recovery Models &#40;SQL Server&#41;</span></span>](../backup-restore/recovery-models-sql-server.md)  
  
 [<span data-ttu-id="ade1c-117">Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ade1c-117">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 [<span data-ttu-id="ade1c-118">Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ade1c-118">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
 [<span data-ttu-id="ade1c-119">Planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="ade1c-119">Maintenance Plans</span></span>](../maintenance-plans/maintenance-plans.md)  
  
 [<span data-ttu-id="ade1c-120">Copias de seguridad de registros de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ade1c-120">Transaction Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/transaction-log-backups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ade1c-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ade1c-121">See Also</span></span>  
 [<span data-ttu-id="ade1c-122">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="ade1c-122">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
