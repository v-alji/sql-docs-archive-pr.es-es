---
title: Dispositivo de copia de seguridad (página General) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.general.f1
ms.assetid: c557e37d-319e-4adb-a0c1-94189b15d2ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d73bdf3ce4b88214286b5f232924d811716a247e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663538"
---
# <a name="backup-device-general-page"></a><span data-ttu-id="689b4-102">Dispositivo de copia de seguridad (página General)</span><span class="sxs-lookup"><span data-stu-id="689b4-102">Backup Device (General Page)</span></span>
  <span data-ttu-id="689b4-103">Utilice la página **General** para especificar o ver las propiedades generales de un dispositivo lógico de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="689b4-103">Use the **General** page to specify or view the general properties of a logical backup device.</span></span>  
  
 <span data-ttu-id="689b4-104">**Para utilizar SQL Server Management Studio a fin de ver el contenido de un dispositivo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="689b4-104">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="689b4-105">Ver el contenido de una cinta o un archivo de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-105">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="689b4-106">Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-106">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="689b4-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="689b4-107">Options</span></span>  
 <span data-ttu-id="689b4-108">**Nombre de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="689b4-108">**Device name**</span></span>  
 <span data-ttu-id="689b4-109">Muestra el nombre de un dispositivo lógico de copia de seguridad existente o especifica el nombre de un dispositivo lógico de copia de seguridad nuevo.</span><span class="sxs-lookup"><span data-stu-id="689b4-109">View the name of an existing logical backup device or specify the name of a new logical backup device.</span></span>  
  
 <span data-ttu-id="689b4-110">**Cinta**</span><span class="sxs-lookup"><span data-stu-id="689b4-110">**Tape**</span></span>  
 <span data-ttu-id="689b4-111">Muestra o selecciona el dispositivo de cinta de destino en la lista **Cinta** .</span><span class="sxs-lookup"><span data-stu-id="689b4-111">View or select the destination tape device in the **Tape** list.</span></span> <span data-ttu-id="689b4-112">Esta opción solo está disponible si hay una unidad de cinta conectada al equipo que ejecuta la instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="689b4-112">This option is available only if a tape drive is attached to the computer that is running the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="689b4-113">Los dispositivos de copia de seguridad en cinta de equipos remotos no son destinos de copia de seguridad válidos.</span><span class="sxs-lookup"><span data-stu-id="689b4-113">Tape backup devices on remote computers are not valid backup destinations.</span></span>  
  
 <span data-ttu-id="689b4-114">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="689b4-114">**File**</span></span>  
 <span data-ttu-id="689b4-115">Muestra el archivo de destino de un dispositivo lógico de copia de seguridad existente o especifica un archivo de destino para un dispositivo lógico de copia de seguridad nuevo.</span><span class="sxs-lookup"><span data-stu-id="689b4-115">View the destination file of an existing logical backup device, or specify a destination file for a new logical backup device.</span></span>  
  
-   <span data-ttu-id="689b4-116">En un dispositivo lógico de copia de seguridad existente, se muestra la ruta de acceso del archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="689b4-116">For an existing logical backup device, the path of the backup file is displayed.</span></span> <span data-ttu-id="689b4-117">El campo **Archivo** no se puede editar y el botón Examinar no está disponible.</span><span class="sxs-lookup"><span data-stu-id="689b4-117">The **File** field is not editable, and the Browse button is unavailable.</span></span>  
  
-   <span data-ttu-id="689b4-118">En un dispositivo lógico de copia de seguridad nuevo, debe proporcionar la ruta de acceso del archivo de copia de seguridad para el que define dicho dispositivo lógico.</span><span class="sxs-lookup"><span data-stu-id="689b4-118">For a new logical backup device, you must supply the path of the backup file for which you are defining the logical backup device.</span></span> <span data-ttu-id="689b4-119">Este archivo no tiene por qué existir aún.</span><span class="sxs-lookup"><span data-stu-id="689b4-119">This file does not have to exist yet.</span></span>  
  
     <span data-ttu-id="689b4-120">Para especificar un archivo de copia de seguridad local, puede hacer clic en el botón Examinar, situado a la derecha del cuadro de texto **Archivo** .</span><span class="sxs-lookup"><span data-stu-id="689b4-120">To specify a local backup file, you can click the Browse button to the right of the **File** text box.</span></span> <span data-ttu-id="689b4-121">A continuación, en el cuadro de diálogo **Buscar archivos de base de datos** , puede navegar a cualquier ubicación de las unidades fijas del equipo que ejecuta la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="689b4-121">Then, in the **Locate Database Files** dialog box, you can navigate to any location on any of the fixed drives on the computer running the server instance.</span></span> <span data-ttu-id="689b4-122">Si el archivo de copia de seguridad no existe aún, debe escribir el nombre de archivo que desea utilizar en el campo **Nombre de archivo** del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="689b4-122">If the backup file does not exist yet, you must enter the filename you want to use in the **File name** field of that dialog box.</span></span>  
  
     <span data-ttu-id="689b4-123">Asimismo, puede editar el campo **Archivo** manualmente para reemplazar la ruta de acceso, el nombre de archivo y la extensión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="689b4-123">Alternatively, you can edit the **File** field manually to override the default path, file name, and extension.</span></span> <span data-ttu-id="689b4-124">Para especificar un archivo remoto como destino de copia de seguridad, escriba su nombre UNC (convención de nomenclatura universal) completo.</span><span class="sxs-lookup"><span data-stu-id="689b4-124">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="689b4-125">Para obtener más información, vea [Dispositivos de copia de seguridad &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="689b4-125">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="689b4-126">La realización de copias de seguridad de datos a través de una red está expuesta a errores; una vez completada, es recomendable comprobar la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="689b4-126">Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="689b4-127">Para obtener más información, vea [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="689b4-127">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="689b4-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="689b4-128">Remarks</span></span>  
 <span data-ttu-id="689b4-129">Las copias de seguridad de uno o varios dispositivos de copia de seguridad constituyen un solo conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="689b4-129">The backups on a set of one or more backup devices compose a single media set.</span></span> <span data-ttu-id="689b4-130">Un *conjunto de medios* es una colección ordenada de medios de copia de seguridad, cintas o archivos de disco en la que se han escrito una o más operaciones de copia de seguridad mediante un tipo y un número fijos de dispositivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="689b4-130">A *media set* is an ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span> <span data-ttu-id="689b4-131">Para obtener más información sobre los conjuntos de medios, vea [Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="689b4-131">For information about media sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="689b4-132">El dispositivo físico de copia de seguridad correspondiente a un dispositivo lógico de copia de seguridad se inicializa cuando la primera copia de seguridad del conjunto de medios se escribe en el dispositivo lógico.</span><span class="sxs-lookup"><span data-stu-id="689b4-132">The physical backup device corresponding to a logical backup device is initialized when the first backup in the media set is written to the logical backup device.</span></span> <span data-ttu-id="689b4-133">Si el dispositivo físico de copia de seguridad es un archivo que aún no existe, se crea en ese momento.</span><span class="sxs-lookup"><span data-stu-id="689b4-133">If the physical backup device is a file that does not exist yet, it is created at that time.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="689b4-134">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="689b4-134">Related Tasks</span></span>  
  
-   [<span data-ttu-id="689b4-135">Definir un dispositivo lógico de copia de seguridad para un archivo de disco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-135">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="689b4-136">Definir un dispositivo lógico de copia de seguridad en una unidad de cinta &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-136">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="689b4-137">Especificar un disco o una cinta como destino de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-137">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="689b4-138">Eliminar un dispositivo de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-138">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="689b4-139">Establecer la fecha de expiración de una copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-139">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="689b4-140">Ver el contenido de una cinta o un archivo de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-140">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="689b4-141">Ver los archivos de datos y de registro en un conjunto de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-141">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="689b4-142">Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-142">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="689b4-143">Restaurar una copia de seguridad desde un dispositivo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-143">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="689b4-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="689b4-144">See Also</span></span>  
 <span data-ttu-id="689b4-145">[Dispositivos de copia de seguridad &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="689b4-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="689b4-146">Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="689b4-146">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
