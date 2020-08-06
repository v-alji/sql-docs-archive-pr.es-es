---
title: Conjuntos de medios de copia de seguridad reflejados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server], mirrored backups
- mirrored media sets [SQL Server]
- backup mirrors [SQL Server]
- duplicate backup copies
- interchangeable backup copies [SQL Server]
- media sets [SQL Server], mirrored backup media sets
- backup media [SQL Server], mirrored media
ms.assetid: 05a0b8d1-3585-4f77-972f-69d1c0d4aa9b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ce3513c67a0087dd00021de75f360b19819b46db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677165"
---
# <a name="mirrored-backup-media-sets-sql-server"></a><span data-ttu-id="14241-102">Conjuntos de medios de copia de seguridad reflejados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="14241-102">Mirrored Backup Media Sets (SQL Server)</span></span>
    
> [!NOTE]  
>  <span data-ttu-id="14241-103">Los conjuntos de medios de copia de seguridad reflejados solo se admiten en la edición Enterprise de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14241-103">Mirrored backup media sets are supported only in the Enterprise edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="14241-104">El hecho de crear un reflejo de un medio de copia de seguridad aumenta la confiabilidad de las copias de seguridad al reducir el impacto de los errores de funcionamiento de los dispositivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="14241-104">Mirroring a media set increases backup reliability by reducing the impact of backup-device malfunctions.</span></span> <span data-ttu-id="14241-105">Los errores de funcionamiento son muy graves porque las copias de seguridad son el último recurso para evitar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="14241-105">These malfunctions are very serious because backups are the last line of defense against data loss.</span></span> <span data-ttu-id="14241-106">A medida que crecen las bases de datos, aumentan las posibilidades de que un error de un dispositivo o medio de copia de seguridad provoque que no se pueda restaurar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="14241-106">As databases grow, the probability increases that a failure of a backup device or media will make a backup nonrestorable.</span></span> <span data-ttu-id="14241-107">El hecho de crear un reflejo de los medios de copia de seguridad aumenta la confiabilidad de las copias de seguridad al proporcionar redundancia.</span><span class="sxs-lookup"><span data-stu-id="14241-107">Mirroring backup media increases the reliability of backups by providing redundancy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14241-108">Para obtener información sobre los conjuntos de medios en general, vea [Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14241-108">For information about media sets in general, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="14241-109">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="14241-109">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="14241-110">Información general sobre conjuntos de medios reflejados</span><span class="sxs-lookup"><span data-stu-id="14241-110">Overview of Mirrored Media Sets</span></span>](#OverviewofMirroredMediaSets)  
  
-   [<span data-ttu-id="14241-111">Requisitos de hardware para reflejos de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="14241-111">Hardware Requirements for Backup Mirrors</span></span>](#HardwareReqs)  
  
-   [<span data-ttu-id="14241-112">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="14241-112">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="overview-of-mirrored-media-sets"></a><a name="OverviewofMirroredMediaSets"></a> <span data-ttu-id="14241-113">Información general sobre conjuntos de medios reflejados</span><span class="sxs-lookup"><span data-stu-id="14241-113">Overview of Mirrored Media Sets</span></span>  
 <span data-ttu-id="14241-114">La creación de reflejos de medios es una propiedad del conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="14241-114">Media mirroring is a property of the media set.</span></span> <span data-ttu-id="14241-115">Un *conjunto de medios reflejado* consta de varias copias (*reflejos*) de los conjuntos de medios.</span><span class="sxs-lookup"><span data-stu-id="14241-115">A *mirrored media set* consists of multiple copies (*mirrors*) of the media set.</span></span> <span data-ttu-id="14241-116">Un conjunto de medios incluye una o varias familias de medios, cada una de las cuales se corresponde con un dispositivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="14241-116">A media set contains one or more media families, each of which corresponds to a backup device.</span></span> <span data-ttu-id="14241-117">Por ejemplo, si la cláusula TO de una instrucción BACKUP DATABASE incluye tres dispositivos, BACKUP reparte los datos entre las tres familias de medios, una por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14241-117">For example, if the TO clause of a BACKUP DATABASE statement lists three devices, BACKUP spreads the data among three media families, one per device.</span></span> <span data-ttu-id="14241-118">El número de familias de medios y reflejos se define al crear el conjunto de medios (mediante una instrucción BACKUP DATABASE que especifica WITH FORMAT).</span><span class="sxs-lookup"><span data-stu-id="14241-118">The number of media families and mirrors is defined when the media set is created (by a BACKUP DATABASE statement that specifies WITH FORMAT).</span></span>  
  
 <span data-ttu-id="14241-119">Un conjunto de medios reflejado contiene entre dos y cuatro reflejos.</span><span class="sxs-lookup"><span data-stu-id="14241-119">A mirrored media set possesses from two to four mirrors.</span></span> <span data-ttu-id="14241-120">Cada reflejo incluye todas las familias de medios del conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="14241-120">Each mirror contains all the media families in the media set.</span></span> <span data-ttu-id="14241-121">Los reflejos requieren el mismo número de dispositivos, uno por familia de medios.</span><span class="sxs-lookup"><span data-stu-id="14241-121">The mirrors require the same number of devices, one per media family.</span></span> <span data-ttu-id="14241-122">Cada reflejo requiere un dispositivo de copia de seguridad diferente por cada familia de medios.</span><span class="sxs-lookup"><span data-stu-id="14241-122">Each mirror requires a separate backup device for each media family.</span></span> <span data-ttu-id="14241-123">Por ejemplo, un conjunto de medios reflejado que consta de cuatro familias de medios con tres reflejos requiere doce dispositivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="14241-123">For example, a mirrored media set that consists of four media families with three mirrors requires twelve backup devices.</span></span> <span data-ttu-id="14241-124">Todos estos dispositivos deben ser equivalentes.</span><span class="sxs-lookup"><span data-stu-id="14241-124">All of these devices must be equivalent.</span></span> <span data-ttu-id="14241-125">Por ejemplo, unidades de cinta que tienen el mismo número de modelo del mismo fabricante.</span><span class="sxs-lookup"><span data-stu-id="14241-125">For example, tape drives that have the same model number from the same manufacturer.</span></span>  
  
 <span data-ttu-id="14241-126">En la siguiente ilustración se muestra un ejemplo de un conjunto de medios reflejado que incluye dos familias de medios con dos reflejos.</span><span class="sxs-lookup"><span data-stu-id="14241-126">The following illustration shows an example of a mirrored media set that consists of two media families with two mirrors.</span></span> <span data-ttu-id="14241-127">Cada familia de medios incluye tres volúmenes de medios, de los cuales se realiza una copia de seguridad por reflejo cada vez.</span><span class="sxs-lookup"><span data-stu-id="14241-127">Each media family contains three media volumes, which are backed up one time per mirror.</span></span>  
  
 <span data-ttu-id="14241-128">![Conjunto de medios reflejado: dos familias con dos reflejos](../../database-engine/media/bnr-backup-media-mirror.gif "Conjunto de medios reflejado: dos familias con dos reflejos")</span><span class="sxs-lookup"><span data-stu-id="14241-128">![Mirrored media set: two families with two mirrors](../../database-engine/media/bnr-backup-media-mirror.gif "Mirrored media set: two families with two mirrors")</span></span>  
  
 <span data-ttu-id="14241-129">Los volúmenes correspondientes en los reflejos tienen un contenido idéntico.</span><span class="sxs-lookup"><span data-stu-id="14241-129">Corresponding volumes on the mirrors have identical contents.</span></span> <span data-ttu-id="14241-130">De este modo, serán intercambiables en el momento de la restauración.</span><span class="sxs-lookup"><span data-stu-id="14241-130">This makes them interchangeable at restore time.</span></span> <span data-ttu-id="14241-131">Por ejemplo, en la ilustración anterior, el tercer volumen de tape2 es intercambiable con el tercer volumen de tape0.</span><span class="sxs-lookup"><span data-stu-id="14241-131">For example, in the previous illustration, the third volume of tape2 is interchangeable with the third volume of tape0.</span></span>  
  
 <span data-ttu-id="14241-132">[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] garantiza que el contenido de los medios reflejados es idéntico mediante la sincronización de las escrituras en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="14241-132">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] guarantees that the mirrored media have identical contents by synchronizing writes to the devices.</span></span> <span data-ttu-id="14241-133">Cuando se llena uno de los reflejos, se extienden todos los reflejos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="14241-133">When any one of the mirrors fills, all the mirrors are spanned at one time.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="14241-134">Un conjunto de medios reflejado no se puede dividir implícitamente eliminando un reflejo.</span><span class="sxs-lookup"><span data-stu-id="14241-134">A mirrored media set cannot be implicitly broken (split) by removing a mirror.</span></span> <span data-ttu-id="14241-135">Si una cinta o un disco resulta dañado o cambia de formato, no se podrá utilizar el reflejo para nuevas copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="14241-135">If any tape or disk in a mirror is damaged or reformatted, the mirror is no longer usable for additional backups.</span></span> <span data-ttu-id="14241-136">Si al menos un reflejo permanece intacto, se podrá leer el conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="14241-136">If at least one full mirror remains intact, the media set can be read.</span></span> <span data-ttu-id="14241-137">Si cada reflejo pierde una familia de medios determinada, no se podrá usar el conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="14241-137">If every mirror loses a given media family, the media set is useless.</span></span>  
  
 <span data-ttu-id="14241-138">Las operaciones de copias de seguridad y restauración imponen distintos requisitos sobre la presencia de todos los reflejos.</span><span class="sxs-lookup"><span data-stu-id="14241-138">Backup and restore operations impose different requirements on whether all the mirrors must be present.</span></span> <span data-ttu-id="14241-139">Para que una operación de copia de seguridad escriba (es decir, cree o extienda) un conjunto de medios reflejado, todos los reflejos deben estar presentes.</span><span class="sxs-lookup"><span data-stu-id="14241-139">For a backup operation to write (that is, to create or extend) a mirrored media set, all the mirrors must be present.</span></span> <span data-ttu-id="14241-140">Por el contrario, si se restaura una copia de seguridad desde un conjunto de medios reflejado, solo puede especificar un reflejo para cada familia de medios.</span><span class="sxs-lookup"><span data-stu-id="14241-140">In contrast, when you are restoring a backup from a mirrored media set, you can specify only a single mirror for each media family.</span></span> <span data-ttu-id="14241-141">Puede realizar restauraciones a partir de menos dispositivos que familias, pero cada familia de medios se procesará una sola vez.</span><span class="sxs-lookup"><span data-stu-id="14241-141">You can restore from fewer devices than families, but each media family is processed only one time.</span></span> <span data-ttu-id="14241-142">No obstante, si hay errores, el hecho de tener otros reflejos habilita la resolución de algunos problemas de restauración rápidamente.</span><span class="sxs-lookup"><span data-stu-id="14241-142">In the presence of errors, however, having the other mirrors enables some restore problems to be resolved quickly.</span></span> <span data-ttu-id="14241-143">Puede sustituir un volumen de medios dañado con el volumen correspondiente de otro reflejo.</span><span class="sxs-lookup"><span data-stu-id="14241-143">You can substitute a damaged media volume with the corresponding volume from another mirror.</span></span> <span data-ttu-id="14241-144">Esto se debe a que RESTORE y RESTORE VERIFYONLY admiten la sustitución de medios dañados por el volumen de medios de copia de seguridad correspondiente de otro reflejo.</span><span class="sxs-lookup"><span data-stu-id="14241-144">This is because RESTORE and RESTORE VERIFYONLY support substitution of damaged media with the corresponding backup-media volume from another mirror.</span></span>  
  
##  <a name="hardware-requirements-for-backup-mirrors"></a><a name="HardwareReqs"></a> <span data-ttu-id="14241-145">Requisitos de hardware para reflejos de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="14241-145">Hardware Requirements for Backup Mirrors</span></span>  
 <span data-ttu-id="14241-146">La creación de reflejos se aplica tanto a los discos como a las cintas (los discos no admiten cintas de continuación).</span><span class="sxs-lookup"><span data-stu-id="14241-146">Mirroring applies both to disk and tape (disks do not support continuation tapes).</span></span> <span data-ttu-id="14241-147">Todos los dispositivos de copia de seguridad de una sola operación de copia de seguridad o restauración deben ser del mismo tipo, disco o cinta.</span><span class="sxs-lookup"><span data-stu-id="14241-147">All backup devices for a single backup or restore operation must be of the same type, disk or tape.</span></span>  
  
 <span data-ttu-id="14241-148">Dentro de estas clases generales, se deben utilizar dispositivos similares con las mismas propiedades.</span><span class="sxs-lookup"><span data-stu-id="14241-148">Within these broader classes, you must use similar devices that have the same properties.</span></span> <span data-ttu-id="14241-149">Si los dispositivos no son lo suficientemente parecidos, aparecerá el mensaje de error 3212.</span><span class="sxs-lookup"><span data-stu-id="14241-149">Insufficiently similar devices generate an error message (3212).</span></span> <span data-ttu-id="14241-150">Para evitar problemas de disparidad, use dispositivos equivalentes, como unidades con el mismo número de modelo del mismo fabricante.</span><span class="sxs-lookup"><span data-stu-id="14241-150">To avoid the risk of a device mismatch, use devices that are equivalent, such as, only drives with the same model number from the same manufacturer.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="14241-151">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="14241-151">Related Tasks</span></span>  
 <span data-ttu-id="14241-152">**Para realizar copias de seguridad en dispositivos de copia de seguridad reflejados**</span><span class="sxs-lookup"><span data-stu-id="14241-152">**To back up to mirrored backup devices**</span></span>  
  
-   [<span data-ttu-id="14241-153">Realizar una copia de seguridad en un conjunto de medios reflejado &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="14241-153">Back Up to a Mirrored Media Set &#40;Transact-SQL&#41;</span></span>](back-up-to-a-mirrored-media-set-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="14241-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14241-154">See Also</span></span>  
 <span data-ttu-id="14241-155">[Errores posibles de medios durante copia de seguridad y restauración &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="14241-155">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 <span data-ttu-id="14241-156">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14241-156">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="14241-157">[Dispositivos de copia de seguridad &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="14241-157">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="14241-158">Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="14241-158">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  