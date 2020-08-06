---
title: Dispositivo de copia de seguridad (página Contenido de los medios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.contents.f1
ms.assetid: 5fc7bd22-b6d8-4af1-8a58-2e7d0b994d08
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 07204b5e05ce9fc17e6ea23450066f9f58b7cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673729"
---
# <a name="backup-device-media-contents-page"></a><span data-ttu-id="2c312-102">Dispositivo de copia de seguridad (página Contenido de los medios)</span><span class="sxs-lookup"><span data-stu-id="2c312-102">Backup Device (Media Contents Page)</span></span>
  <span data-ttu-id="2c312-103">Utilice el cuadro de diálogo **Dispositivo de copia de seguridad** para ver la información acerca de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c312-103">Use the **Backup Device** dialog box to view the backup information.</span></span> <span data-ttu-id="2c312-104">Esta información describe el dispositivo, el medio, el conjunto de medios y los conjuntos de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c312-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="2c312-105">**Para utilizar SQL Server Management Studio a fin de ver el contenido de un dispositivo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="2c312-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="2c312-106">Ver el contenido de una cinta o un archivo de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="2c312-107">Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="2c312-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="2c312-108">Options</span></span>  
 <span data-ttu-id="2c312-109">Vea la información acerca del medio individual, el conjunto de medios y los conjuntos de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c312-109">View information about the individual media, media set, and backup sets.</span></span>  
  
 <span data-ttu-id="2c312-110">**Elementos multimedia**</span><span class="sxs-lookup"><span data-stu-id="2c312-110">**Media**</span></span>  
 <span data-ttu-id="2c312-111">Disco o conjunto de cintas donde se almacena la información de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c312-111">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="2c312-112">**Secuencia del medio**</span><span class="sxs-lookup"><span data-stu-id="2c312-112">**Media sequence**</span></span>  
 <span data-ttu-id="2c312-113">Proporciona el número de secuencia del medio, el número de secuencia de la familia y el identificador del reflejo, si existe alguno.</span><span class="sxs-lookup"><span data-stu-id="2c312-113">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="2c312-114">El medio físico de copia de seguridad se etiqueta con un número de secuencia que indica el orden en el que se utilizó el medio.</span><span class="sxs-lookup"><span data-stu-id="2c312-114">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="2c312-115">El medio de copia de seguridad inicial se etiqueta con 1, el segundo (la primera cinta de continuación) se etiqueta con 2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="2c312-115">The initial backup media is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="2c312-116">Cuando restaure el conjunto de copias de seguridad, asegúrese de que el operador que restaura la copia de seguridad coloca los medios correctos en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="2c312-116">When the backup set is restored, the media sequence numbers ensure that the operator restoring the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="2c312-117">**Creado el**</span><span class="sxs-lookup"><span data-stu-id="2c312-117">**Created on**</span></span>  
 <span data-ttu-id="2c312-118">Muestra la fecha y la hora de creación del conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="2c312-118">Displays the creation date and time of the media set.</span></span>  
  
 <span data-ttu-id="2c312-119">**Conjunto de medios**</span><span class="sxs-lookup"><span data-stu-id="2c312-119">**Media Set**</span></span>  
 <span data-ttu-id="2c312-120">Un conjunto de medios es una colección ordenada de medios de copia de seguridad en la que se han grabado una o más operaciones de copia de seguridad mediante un número constante de dispositivos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="2c312-120">A media set is an ordered collection of backup media to which one or more backup operations have written by using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="2c312-121">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2c312-121">**Name**</span></span>  
 <span data-ttu-id="2c312-122">Muestra el nombre del conjunto de medios, si existe alguno.</span><span class="sxs-lookup"><span data-stu-id="2c312-122">Displays the name of the media set, if any.</span></span>  
  
 <span data-ttu-id="2c312-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2c312-123">**Description**</span></span>  
 <span data-ttu-id="2c312-124">Muestra la descripción del conjunto de medios, si existe alguno.</span><span class="sxs-lookup"><span data-stu-id="2c312-124">Displays the description of the media set, if any.</span></span>  
  
 <span data-ttu-id="2c312-125">**Recuento de la familia de medios**</span><span class="sxs-lookup"><span data-stu-id="2c312-125">**Media family count**</span></span>  
 <span data-ttu-id="2c312-126">Muestra el número de familias del conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="2c312-126">Displays the number of families in the media set.</span></span> <span data-ttu-id="2c312-127">Cada conjunto de medios es una colección de una o más familias de medios.</span><span class="sxs-lookup"><span data-stu-id="2c312-127">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="2c312-128">Toda la salida a un único dispositivo de copia de seguridad determinado (o grupo de dispositivos de copia de seguridad reflejados) forma una única familia de medios.</span><span class="sxs-lookup"><span data-stu-id="2c312-128">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="2c312-129">Cada conjunto de medios contiene una familia de medios por dispositivo (o grupo de dispositivos reflejados); por ejemplo, si un conjunto de medios utiliza dos dispositivos de copia de seguridad no reflejos, el conjunto de medios contiene dos familias de medios.</span><span class="sxs-lookup"><span data-stu-id="2c312-129">Each media set contains one media family per separate device (or group of mirrored devices); for instance, if a media set uses two non-mirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="2c312-130">**Conjuntos de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="2c312-130">**Backup sets**</span></span>  
 <span data-ttu-id="2c312-131">Muestra la información acerca del conjunto o conjuntos de copia de seguridad que contiene el medio.</span><span class="sxs-lookup"><span data-stu-id="2c312-131">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="2c312-132">Un conjunto de copia de seguridad es el resultado de una operación de copia de seguridad correcta, cuyo contenido se distribuye entre los medios del conjunto de dispositivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c312-132">A backup set is the result of a successful backup operation, whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="2c312-133">Encabezado</span><span class="sxs-lookup"><span data-stu-id="2c312-133">Header</span></span>|<span data-ttu-id="2c312-134">Valores</span><span class="sxs-lookup"><span data-stu-id="2c312-134">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="2c312-135">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2c312-135">**Name**</span></span>|<span data-ttu-id="2c312-136">Nombre del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c312-136">The name of the backup set.</span></span>|  
|<span data-ttu-id="2c312-137">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2c312-137">**Type**</span></span>|<span data-ttu-id="2c312-138">Objeto del que se ha realizado una copia de seguridad: base de datos, archivo o *\<blank>* (para registros de transacciones).</span><span class="sxs-lookup"><span data-stu-id="2c312-138">The backed-up object: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="2c312-139">**Componente**</span><span class="sxs-lookup"><span data-stu-id="2c312-139">**Component**</span></span>|<span data-ttu-id="2c312-140">Tipo de copia de seguridad realizada: Completa, Diferencial o Registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="2c312-140">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="2c312-141">**Server**</span><span class="sxs-lookup"><span data-stu-id="2c312-141">**Server**</span></span>|<span data-ttu-id="2c312-142">Nombre de la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que realizó la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c312-142">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="2c312-143">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="2c312-143">**Database**</span></span>|<span data-ttu-id="2c312-144">Nombre de la base de datos de la que se realizó la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c312-144">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="2c312-145">**Posición**</span><span class="sxs-lookup"><span data-stu-id="2c312-145">**Position**</span></span>|<span data-ttu-id="2c312-146">Posición del conjunto de copias de seguridad en el volumen.</span><span class="sxs-lookup"><span data-stu-id="2c312-146">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="2c312-147">**Date**</span><span class="sxs-lookup"><span data-stu-id="2c312-147">**Date**</span></span>|<span data-ttu-id="2c312-148">Fecha y hora en la que finalizó la operación de copia de seguridad, presentadas en la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="2c312-148">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="2c312-149">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="2c312-149">**Size**</span></span>|<span data-ttu-id="2c312-150">Tamaño del conjunto de copias de seguridad, en bytes.</span><span class="sxs-lookup"><span data-stu-id="2c312-150">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="2c312-151">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="2c312-151">**User Name**</span></span>|<span data-ttu-id="2c312-152">Nombre del usuario que realizó la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c312-152">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="2c312-153">**Expiración**</span><span class="sxs-lookup"><span data-stu-id="2c312-153">**Expiration**</span></span>|<span data-ttu-id="2c312-154">Fecha y hora de expiración del conjunto de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c312-154">The date and time the backup set expires.</span></span>|  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2c312-155">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2c312-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2c312-156">Definir un dispositivo lógico de copia de seguridad para un archivo de disco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-156">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="2c312-157">Definir un dispositivo lógico de copia de seguridad en una unidad de cinta &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-157">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="2c312-158">Especificar un disco o una cinta como destino de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-158">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="2c312-159">Eliminar un dispositivo de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-159">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="2c312-160">Establecer la fecha de expiración de una copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-160">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="2c312-161">Ver el contenido de una cinta o un archivo de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-161">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="2c312-162">Ver los archivos de datos y de registro en un conjunto de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-162">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="2c312-163">Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-163">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="2c312-164">Restaurar una copia de seguridad desde un dispositivo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-164">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="2c312-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c312-165">See Also</span></span>  
 <span data-ttu-id="2c312-166">[Dispositivos de copia de seguridad &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2c312-166">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="2c312-167">Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c312-167">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
