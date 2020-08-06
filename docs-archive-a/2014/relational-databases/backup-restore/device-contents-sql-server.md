---
title: Contenido del dispositivo (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.bnrdevicecontents.f1
ms.assetid: 95e1902e-8c7a-4830-bdf9-1a6aca414a24
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c904718eca671b1965a95d0d400f3f6fa075b500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672129"
---
# <a name="device-contents-sql-server"></a><span data-ttu-id="143a7-102">Contenido del dispositivo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="143a7-102">Device Contents (SQL Server)</span></span>
  <span data-ttu-id="143a7-103">Utilice este cuadro de diálogo para ver la información de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="143a7-103">Use this dialog box to view the backup information.</span></span> <span data-ttu-id="143a7-104">Esta información describe el dispositivo, el medio, el conjunto de medios y los conjuntos de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="143a7-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="143a7-105">**Para utilizar SQL Server Management Studio a fin de ver el contenido de un dispositivo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="143a7-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="143a7-106">Ver el contenido de una cinta o un archivo de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="143a7-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="143a7-107">Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="143a7-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="143a7-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="143a7-108">Options</span></span>  
 <span data-ttu-id="143a7-109">**Elementos multimedia**</span><span class="sxs-lookup"><span data-stu-id="143a7-109">**Media**</span></span>  
 <span data-ttu-id="143a7-110">Disco o conjunto de cintas donde se almacena la información de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="143a7-110">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="143a7-111">**Secuencia del medio**</span><span class="sxs-lookup"><span data-stu-id="143a7-111">**Media sequence**</span></span>  
 <span data-ttu-id="143a7-112">Proporciona el número de secuencia del medio, el número de secuencia de la familia y el identificador del reflejo, si existe alguno.</span><span class="sxs-lookup"><span data-stu-id="143a7-112">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="143a7-113">El medio físico de copia de seguridad se etiqueta con un número de secuencia que indica el orden en el que se utilizó el medio.</span><span class="sxs-lookup"><span data-stu-id="143a7-113">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="143a7-114">El medio de copia de seguridad inicial se etiqueta con 1, el segundo (la primera cinta de continuación) se etiqueta con 2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="143a7-114">The initial backup medium is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="143a7-115">Cuando restaure el conjunto de copias de seguridad, asegúrese de que el operador que restaura la copia de seguridad coloca los medios correctos en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="143a7-115">When the backup set is restored, the media sequence numbers ensure that the operator that restores the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="143a7-116">**Creado el**</span><span class="sxs-lookup"><span data-stu-id="143a7-116">**Created on**</span></span>  
 <span data-ttu-id="143a7-117">Muestra la fecha de los medios.</span><span class="sxs-lookup"><span data-stu-id="143a7-117">Displays the media date.</span></span>  
  
 <span data-ttu-id="143a7-118">**Conjunto de medios**</span><span class="sxs-lookup"><span data-stu-id="143a7-118">**Media Set**</span></span>  
 <span data-ttu-id="143a7-119">Un conjunto de medios es una colección ordenada de medios de copia de seguridad en la que se han grabado una o más operaciones de copia de seguridad mediante un número constante de dispositivos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="143a7-119">A media set is an ordered collection of backup media to which one or more backup operations have written using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="143a7-120">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="143a7-120">**Name**</span></span>  
 <span data-ttu-id="143a7-121">Muestra el nombre del conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="143a7-121">Displays the name of the media set.</span></span>  
  
 <span data-ttu-id="143a7-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="143a7-122">**Description**</span></span>  
 <span data-ttu-id="143a7-123">Muestra la descripción del conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="143a7-123">Displays the description media set.</span></span>  
  
 <span data-ttu-id="143a7-124">**Recuento de la familia de medios**</span><span class="sxs-lookup"><span data-stu-id="143a7-124">**Media family count**</span></span>  
 <span data-ttu-id="143a7-125">Muestra el recuento de la familia de medios.</span><span class="sxs-lookup"><span data-stu-id="143a7-125">Displays the media family count.</span></span> <span data-ttu-id="143a7-126">Cada conjunto de medios es una colección de una o más familias de medios.</span><span class="sxs-lookup"><span data-stu-id="143a7-126">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="143a7-127">Toda la salida a un único dispositivo de copia de seguridad determinado (o grupo de dispositivos de copia de seguridad reflejados) forma una única familia de medios.</span><span class="sxs-lookup"><span data-stu-id="143a7-127">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="143a7-128">Cada conjunto de medios contiene una familia de medios por dispositivo (o grupo de dispositivos reflejados); por ejemplo, si un conjunto de medios utiliza dos dispositivos de copia de seguridad no reflejados, el conjunto de medios contiene dos familias de medios.</span><span class="sxs-lookup"><span data-stu-id="143a7-128">Each media set contains one media family per separate device (or group of mirrored devices); for example, if a media set uses two nonmirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="143a7-129">**Conjuntos de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="143a7-129">**Backup sets**</span></span>  
 <span data-ttu-id="143a7-130">Muestra la información acerca del conjunto o conjuntos de copia de seguridad que contiene el medio.</span><span class="sxs-lookup"><span data-stu-id="143a7-130">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="143a7-131">Un conjunto de copia de seguridad es el resultado de una operación de copia de seguridad correcta, cuyo contenido se distribuye entre los medios del conjunto de dispositivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="143a7-131">A backup set is the result of a successful backup operation whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="143a7-132">Encabezado</span><span class="sxs-lookup"><span data-stu-id="143a7-132">Header</span></span>|<span data-ttu-id="143a7-133">Valores</span><span class="sxs-lookup"><span data-stu-id="143a7-133">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="143a7-134">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="143a7-134">**Name**</span></span>|<span data-ttu-id="143a7-135">Nombre del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="143a7-135">The name of the backup set.</span></span>|  
|<span data-ttu-id="143a7-136">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="143a7-136">**Type**</span></span>|<span data-ttu-id="143a7-137">Tipo de copia de seguridad realizada: Completa, Diferencial o Registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="143a7-137">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="143a7-138">**Componente**</span><span class="sxs-lookup"><span data-stu-id="143a7-138">**Component**</span></span>|<span data-ttu-id="143a7-139">Componente del que se ha realizado una copia de seguridad: Base de datos, Archivo o *\<blank>* (para registros de transacciones).</span><span class="sxs-lookup"><span data-stu-id="143a7-139">The backed-up component: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="143a7-140">**Server**</span><span class="sxs-lookup"><span data-stu-id="143a7-140">**Server**</span></span>|<span data-ttu-id="143a7-141">Nombre de la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que realizó la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="143a7-141">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="143a7-142">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="143a7-142">**Database**</span></span>|<span data-ttu-id="143a7-143">Nombre de la base de datos de la que se realizó la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="143a7-143">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="143a7-144">**Posición**</span><span class="sxs-lookup"><span data-stu-id="143a7-144">**Position**</span></span>|<span data-ttu-id="143a7-145">Posición del conjunto de copias de seguridad en el volumen.</span><span class="sxs-lookup"><span data-stu-id="143a7-145">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="143a7-146">**Date**</span><span class="sxs-lookup"><span data-stu-id="143a7-146">**Date**</span></span>|<span data-ttu-id="143a7-147">Fecha y hora en la que finalizó la operación de copia de seguridad, presentadas en la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="143a7-147">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="143a7-148">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="143a7-148">**Size**</span></span>|<span data-ttu-id="143a7-149">Tamaño del conjunto de copias de seguridad, en bytes.</span><span class="sxs-lookup"><span data-stu-id="143a7-149">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="143a7-150">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="143a7-150">**User Name**</span></span>|<span data-ttu-id="143a7-151">Nombre del usuario que realizó la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="143a7-151">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="143a7-152">**Expiración**</span><span class="sxs-lookup"><span data-stu-id="143a7-152">**Expiration**</span></span>|<span data-ttu-id="143a7-153">Fecha y hora de expiración del conjunto de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="143a7-153">The date and time the backup set expires.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="143a7-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="143a7-154">See Also</span></span>  
 [<span data-ttu-id="143a7-155">Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="143a7-155">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
