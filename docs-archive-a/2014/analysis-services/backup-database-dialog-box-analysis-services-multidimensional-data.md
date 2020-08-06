---
title: Cuadro de diálogo copia de seguridad de base de datos (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Backup.f1
ms.assetid: 7811ce7d-6c37-4189-bfa6-ef36fb4932db
author: minewiskan
ms.author: owend
ms.openlocfilehash: 48cf094353c53213864dae656af94ae791442105
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670153"
---
# <a name="backup-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="aa5a0-102">Cuadro de diálogo Copia de seguridad de la base de datos (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="aa5a0-102">Backup Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="aa5a0-103">Use el cuadro de diálogo **Copia de seguridad de la base de datos** de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para hacer una copia de seguridad de una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en un archivo de copia de seguridad con el formato de copia de seguridad de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (.abf).</span><span class="sxs-lookup"><span data-stu-id="aa5a0-103">Use the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to back up an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aa5a0-104">Para cada archivo de copia de seguridad, el usuario que ejecuta el comando de copia de seguridad debe tener permiso para escribir en la ubicación de copia de seguridad especificada.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-104">For each backup file, the user who runs the backup command must have permission to write to the backup location specified for each file.</span></span> <span data-ttu-id="aa5a0-105">Además, el usuario debe tener uno de los roles siguientes: miembro de un rol de servidor para la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o miembro de un rol de base de datos con permisos de Control total (Administrador) en la base de datos de la que se va a hacer una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-105">Also, the user must have one of the following roles: a member of a server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be backed up.</span></span>  
  
 <span data-ttu-id="aa5a0-106">**Para mostrar el cuadro de diálogo Copia de seguridad de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-106">**To display the Backup Database dialog box**</span></span>  
  
-   <span data-ttu-id="aa5a0-107">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], haga clic con el botón derecho en la carpeta **Bases de datos** de una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o en una base de datos del **Explorador de objetos**y, a continuación, haga clic en **Copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-107">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Backup**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aa5a0-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="aa5a0-108">Options</span></span>  
 <span data-ttu-id="aa5a0-109">**Script**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-109">**Script**</span></span>  
 <span data-ttu-id="aa5a0-110">Crea un script de copia de seguridad basado en las opciones seleccionadas en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-110">Creates a backup script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="aa5a0-111">El script de restauración se escribe en el lenguaje de scripting de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ASSL).</span><span class="sxs-lookup"><span data-stu-id="aa5a0-111">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="aa5a0-112">Al hacer clic en el icono **Script** , se envía el script de copia de seguridad a una nueva ventana de consulta, de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-112">Clicking the **Script** icon sends the backup script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="aa5a0-113">Al hacer clic en la flecha **Script** , se muestra un menú que permite elegir dónde enviar el script de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="aa5a0-113">Clicking the **Script** arrow displays a menu that allows you to choose where to send the backup script:</span></span>  
  
-   <span data-ttu-id="aa5a0-114">A una nueva ventana de consulta (predeterminada)</span><span class="sxs-lookup"><span data-stu-id="aa5a0-114">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="aa5a0-115">A un archivo</span><span class="sxs-lookup"><span data-stu-id="aa5a0-115">To a file.</span></span>  
  
-   <span data-ttu-id="aa5a0-116">Al Portapapeles</span><span class="sxs-lookup"><span data-stu-id="aa5a0-116">To the clipboard.</span></span>  
  
-   <span data-ttu-id="aa5a0-117">A un trabajo</span><span class="sxs-lookup"><span data-stu-id="aa5a0-117">To a job.</span></span>  
  
 <span data-ttu-id="aa5a0-118">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-118">**Database**</span></span>  
 <span data-ttu-id="aa5a0-119">Muestra el nombre de la base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] seleccionada.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-119">Displays the name of the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="aa5a0-120">**Archivo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-120">**Backup file**</span></span>  
 <span data-ttu-id="aa5a0-121">Escriba la ruta de acceso completa y el nombre del archivo de copia de seguridad que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-121">Type the full path and file name of the backup file to use.</span></span>  
  
 <span data-ttu-id="aa5a0-122">**Browse**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-122">**Browse**</span></span>  
 <span data-ttu-id="aa5a0-123">Haga clic para mostrar el cuadro de diálogo **Guardar archivo como** y seleccione la ruta de acceso y el nombre del archivo de copia de seguridad que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-123">Click to display the **Save File As** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="aa5a0-124">Para obtener más información sobre el cuadro de diálogo **Guardar archivo como**, vea [Cuadro de diálogo Guardar archivo como &#40;Analysis Services - Datos multidimensionales&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="aa5a0-124">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="aa5a0-125">**Permitir la sobrescritura de archivos**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-125">**Allow file overwrite**</span></span>  
 <span data-ttu-id="aa5a0-126">Seleccione esta opción para sobrescribir un archivo de copia de seguridad existente o un archivo de copia de seguridad remoto, si existiese.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-126">Select to overwrite an existing backup file or remote backup file, if one exists.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa5a0-127">Si no selecciona esta opción y existe el archivo de seguridad especificado en **Archivo de copia de seguridad** o el archivo de copia de seguridad remoto en **Archivo de copia de seguridad remoto**, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-127">If this option is not selected and the backup file specified in **Backup file** or a remote backup file specified in **Remote backup file** exists, an error occurs.</span></span>  
  
 <span data-ttu-id="aa5a0-128">**Aplicar compresión**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-128">**Apply compression**</span></span>  
 <span data-ttu-id="aa5a0-129">Seleccione esta opción para comprimir el contenido de un archivo de copia de seguridad o los archivos de copia de seguridad remotos especificados.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-129">Select to compress the contents of the backup file and, if specified, remote backup files.</span></span>  
  
 <span data-ttu-id="aa5a0-130">**Cifrar archivo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-130">**Encrypt backup file**</span></span>  
 <span data-ttu-id="aa5a0-131">Seleccione esta opción para cifrar el archivo de copia de seguridad con la contraseña proporcionada en **Contraseña**.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-131">Select to encrypt the backup file using the password supplied in **Password**.</span></span>  
  
 <span data-ttu-id="aa5a0-132">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-132">**Password**</span></span>  
 <span data-ttu-id="aa5a0-133">Escriba la contraseña que desea utilizar para cifrar el archivo de copia de seguridad o los archivos de copia de seguridad remotos especificados.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-133">Type the password to use when encrypting the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa5a0-134"> Esta opción solo se habilita si se selecciona **Cifrar archivo de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="aa5a0-134">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="aa5a0-135">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-135">**Confirm Password**</span></span>  
 <span data-ttu-id="aa5a0-136">Escriba la contraseña proporcionada en **Contraseña** para confirmar la contraseña del archivo de copia de seguridad y los archivos de copia de seguridad remotos especificados.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-136">Type the password entered in **Password** to confirm the password for the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa5a0-137"> Esta opción solo se habilita si se selecciona **Cifrar archivo de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="aa5a0-137">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="aa5a0-138">**Copia de seguridad de particiones remotas**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-138">**Backup remote partition(s)**</span></span>  
 <span data-ttu-id="aa5a0-139">Seleccione esta opción para incluir información y datos de la ubicación para las particiones remotas del archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-139">Select to include location information and data for remote partitions in the backup file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa5a0-140">Esta opción solo se habilita si la base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] seleccionada usa particiones remotas.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-140">This option is enabled only if the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database uses remote partitions.</span></span>  
  
 <span data-ttu-id="aa5a0-141">**Ubicación de la copia de seguridad de la partición remota**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-141">**Remote partition backup location**</span></span>  
 <span data-ttu-id="aa5a0-142">Muestra la ubicación de las particiones remotas asociadas a la base de datos seleccionada, así como el archivo de copia de seguridad remoto usado para hacer una copia de seguridad de los datos y metadatos de las particiones remotas.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-142">Displays the location of remote partitions associated with the selected database, as well as the remote backup file used to back up the data and metadata for the remote partitions.</span></span> <span data-ttu-id="aa5a0-143">Están disponibles las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="aa5a0-143">The following columns are available:</span></span>  
  
|<span data-ttu-id="aa5a0-144">Columna</span><span class="sxs-lookup"><span data-stu-id="aa5a0-144">Column</span></span>|<span data-ttu-id="aa5a0-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa5a0-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="aa5a0-146">**Server**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-146">**Server**</span></span>|<span data-ttu-id="aa5a0-147">Muestra la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que administra las particiones remotas.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-147">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that manages the remote partitions.</span></span>|  
|<span data-ttu-id="aa5a0-148">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-148">**Database**</span></span>|<span data-ttu-id="aa5a0-149">Muestra la base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que contiene las particiones remotas.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-149">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that contains the remote partitions.</span></span>|  
|<span data-ttu-id="aa5a0-150">**Lista de particiones**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-150">**Partition List**</span></span>|<span data-ttu-id="aa5a0-151">Muestra la lista de particiones remotas contenidas en la base de datos que se muestra en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-151">Displays the list of remote partitions contained by the database displayed in **Database**.</span></span>|  
|<span data-ttu-id="aa5a0-152">**Archivo de copia de seguridad remoto**</span><span class="sxs-lookup"><span data-stu-id="aa5a0-152">**Remote backup file**</span></span>|<span data-ttu-id="aa5a0-153">Escriba la ruta de acceso completa y el nombre del archivo de copia de seguridad remoto que quiere usar o haga clic en el botón de puntos suspensivos (**…**) para mostrar el cuadro de diálogo **Guardar archivo como** y seleccione la ruta de acceso y el nombre del archivo de copia de seguridad remoto que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="aa5a0-153">Type the full path and file name of the remote backup file to use, or click the ellipsis button (**...**) to display the **Save File As** dialog box and select the path and file name of the remote backup file to use.</span></span> <span data-ttu-id="aa5a0-154">Para obtener más información sobre el cuadro de diálogo **Guardar archivo como**, vea [Cuadro de diálogo Guardar archivo como &#40;Analysis Services - Datos multidimensionales&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="aa5a0-154">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa5a0-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa5a0-155">See Also</span></span>  
 <span data-ttu-id="aa5a0-156">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="aa5a0-156">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="aa5a0-157">Realizar una copia de seguridad y restaurar las bases de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="aa5a0-157">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
