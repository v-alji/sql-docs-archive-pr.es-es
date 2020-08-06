---
title: General (cuadro de diálogo restaurar base de datos) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.restoredbdialog.f1
ms.assetid: 319e7ef5-c9c7-4e50-8690-02a90aed006f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25a49e17227fc2ed6b7b18d2e0964cd8812cbdcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677276"
---
# <a name="general-restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="3cf35-102">General (cuadro de diálogo Restaurar base de datos) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="3cf35-102">General (Restore Database Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="3cf35-103">Use la página **General** del cuadro de diálogo **Restaurar base de datos** en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para especificar el archivo de copia de seguridad y la configuración general que se utilizará al restaurar una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cf35-103">Use the **General** page of the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to specify the backup file and general settings to use when restoring an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3cf35-104">Para cada archivo de copia de seguridad, el usuario que ejecuta el comando de restauración debe tener permiso para leer desde la ubicación de la copia de seguridad especificada.</span><span class="sxs-lookup"><span data-stu-id="3cf35-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="3cf35-105">Para restaurar una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que no está instalada en el servidor, el usuario también debe ser miembro del rol de servidor para dicha instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cf35-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="3cf35-106">Para sobrescribir una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , el usuario debe tener uno de los roles siguientes: miembro del rol de servidor para la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o miembro de un rol de base de datos con permisos de Control total (Administrador) en la base de datos que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="3cf35-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3cf35-107">Después de restaurar una base de datos existente, el usuario que restauró la base de datos podría perder el acceso a la base de datos restaurada.</span><span class="sxs-lookup"><span data-stu-id="3cf35-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="3cf35-108">Esta pérdida de acceso puede producirse si, en el momento en que se realizó la copia de seguridad, el usuario no era miembro del rol de servidor o no era miembro de rol de base de datos con permisos de Control total (Administrador).</span><span class="sxs-lookup"><span data-stu-id="3cf35-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="3cf35-109">**Para mostrar la página General en el cuadro de diálogo Restaurar base de datos**</span><span class="sxs-lookup"><span data-stu-id="3cf35-109">**To display the General page in the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="3cf35-110">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], haga clic con el botón derecho o en la carpeta **Bases de datos** de una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o en una base de datos en el **Explorador de objetos**, haga clic en **Restaurar**y, luego, en **Seleccionar una página**, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="3cf35-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, click **Restore**, and then under **Select a page**, click **General**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3cf35-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="3cf35-111">Options</span></span>  
 <span data-ttu-id="3cf35-112">**Script**</span><span class="sxs-lookup"><span data-stu-id="3cf35-112">**Script**</span></span>  
 <span data-ttu-id="3cf35-113">Crea un script de restauración basado en las opciones seleccionadas en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3cf35-113">Creates a restore script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="3cf35-114">El script de restauración se escribe en el lenguaje de scripting de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ASSL).</span><span class="sxs-lookup"><span data-stu-id="3cf35-114">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="3cf35-115">Al hacer clic en el icono **Script** , se envía el script de restauración a una nueva ventana de consulta, de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3cf35-115">Clicking the **Script** icon sends the restore script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="3cf35-116">Al hacer clic en la flecha **Script** , se muestra un menú que le permite elegir dónde enviar el script de restauración:</span><span class="sxs-lookup"><span data-stu-id="3cf35-116">Clicking the **Script** arrow displays a menu that allows you to choose where to send the restore script:</span></span>  
  
-   <span data-ttu-id="3cf35-117">A una nueva ventana de consulta (predeterminada)</span><span class="sxs-lookup"><span data-stu-id="3cf35-117">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="3cf35-118">A un archivo</span><span class="sxs-lookup"><span data-stu-id="3cf35-118">To a file.</span></span>  
  
-   <span data-ttu-id="3cf35-119">Al Portapapeles</span><span class="sxs-lookup"><span data-stu-id="3cf35-119">To the clipboard.</span></span>  
  
-   <span data-ttu-id="3cf35-120">A un trabajo</span><span class="sxs-lookup"><span data-stu-id="3cf35-120">To a job.</span></span>  
  
 <span data-ttu-id="3cf35-121">**Restaurar base de datos**</span><span class="sxs-lookup"><span data-stu-id="3cf35-121">**Restore database**</span></span>  
 <span data-ttu-id="3cf35-122">Seleccione la base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que se restaurará.</span><span class="sxs-lookup"><span data-stu-id="3cf35-122">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to restore.</span></span>  
  
 <span data-ttu-id="3cf35-123">**Del archivo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="3cf35-123">**From backup file**</span></span>  
 <span data-ttu-id="3cf35-124">Seleccione el archivo de copia de seguridad a partir del que se restaurará la base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3cf35-124">Select the backup file from which to restore the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="3cf35-125">**Browse**</span><span class="sxs-lookup"><span data-stu-id="3cf35-125">**Browse**</span></span>  
 <span data-ttu-id="3cf35-126">Haga clic para mostrar el cuadro de diálogo **Buscar archivos de base de datos** y seleccione la ruta de acceso y el nombre del archivo de copia de seguridad que se usará.</span><span class="sxs-lookup"><span data-stu-id="3cf35-126">Click to display the **Locate Database Files** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="3cf35-127">Para más información sobre el cuadro de diálogo **Buscar archivos de base de datos**, vea [Cuadro de diálogo Buscar archivos de la base de datos &#40;Analysis Services - Datos multidimensionales&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="3cf35-127">For more information about the **Locate Database Files** dialog box, see [Locate Database Files Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="3cf35-128">**Permitir sobrescritura de base de datos**</span><span class="sxs-lookup"><span data-stu-id="3cf35-128">**Allow database overwrite**</span></span>  
 <span data-ttu-id="3cf35-129">Seleccione esta opción para permitir a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] restaurar el contenido del archivo de copia de seguridad seleccionado sobre objetos existentes en la base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3cf35-129">Select to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to restore the contents of the selected backup file over any existing objects in the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="3cf35-130">**Incluir información de seguridad**</span><span class="sxs-lookup"><span data-stu-id="3cf35-130">**Include security information**</span></span>  
 <span data-ttu-id="3cf35-131">Seleccione esta opción para copiar la información de seguridad almacenada en el archivo de copia de seguridad en la base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cf35-131">Select to copy any security information stored in the backup file to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="3cf35-132">Si esta opción está seleccionada, puede elegir la cantidad de información de seguridad de la lista desplegable habilitada al seleccionar esta opción.</span><span class="sxs-lookup"><span data-stu-id="3cf35-132">If this option is selected, you can choose the amount of security information from the drop-down list enabled by selecting this option.</span></span> <span data-ttu-id="3cf35-133">Están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3cf35-133">The following options are available:</span></span>  
  
|<span data-ttu-id="3cf35-134">Opción</span><span class="sxs-lookup"><span data-stu-id="3cf35-134">Option</span></span>|<span data-ttu-id="3cf35-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cf35-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3cf35-136">**Copiar todo**</span><span class="sxs-lookup"><span data-stu-id="3cf35-136">**Copy All**</span></span>|<span data-ttu-id="3cf35-137">Restaura los roles de base de datos que contiene el archivo de copia de seguridad y también las cuentas de usuario asociadas a los roles.</span><span class="sxs-lookup"><span data-stu-id="3cf35-137">Restores the database roles contained in the backup file, as well as the user accounts associated with the roles.</span></span>|  
|<span data-ttu-id="3cf35-138">**Omitir pertenencia**</span><span class="sxs-lookup"><span data-stu-id="3cf35-138">**Skip Membership**</span></span>|<span data-ttu-id="3cf35-139">Restaura los roles de base de datos que contiene el archivo de copia de seguridad, pero no restaura las cuentas de usuario asociadas a los roles.</span><span class="sxs-lookup"><span data-stu-id="3cf35-139">Restores the database roles contained in the backup file, but does not restore the user accounts associated with the roles.</span></span>|  
  
 <span data-ttu-id="3cf35-140">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="3cf35-140">**Password**</span></span>  
 <span data-ttu-id="3cf35-141">Si el archivo de copia de seguridad está cifrado, escriba la contraseña usada para cifrarlo.</span><span class="sxs-lookup"><span data-stu-id="3cf35-141">If the backup file is encrypted, type the password used to encrypt the backup file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cf35-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3cf35-142">See Also</span></span>  
 <span data-ttu-id="3cf35-143">[Cuadro de diálogo restaurar base de datos &#40;Analysis Services-datos multidimensionales&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3cf35-143">[Restore Database Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3cf35-144">[Particiones &#40;cuadro de diálogo restaurar base de datos&#41; &#40;Analysis Services-datos multidimensionales&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3cf35-144">[Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3cf35-145">Realizar una copia de seguridad y restaurar las bases de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3cf35-145">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
