---
title: Tarea Limpieza de mantenimiento (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.cleanup.f1
helpviewer_keywords:
- Maintenance Cleanup Task dialog box
ms.assetid: 022b679c-6799-4c13-9185-814224a20412
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9023881ff5cf5ba5ddd8c61aa179c5881162bf44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673671"
---
# <a name="maintenance-cleanup-task-maintenance-plan"></a><span data-ttu-id="df2c6-102">Tarea Limpieza de mantenimiento (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="df2c6-102">Maintenance Cleanup Task (Maintenance Plan)</span></span>
  <span data-ttu-id="df2c6-103">Utilice la **Tarea Limpieza de mantenimiento** para quitar archivos antiguos que estén relacionados con los planes de mantenimiento, incluidos los informes de texto creados por planes de mantenimiento y archivos de copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="df2c6-103">Use the **Maintenance Cleanup Task** to remove old files related to maintenance plans, including text reports created by maintenance plans and database backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df2c6-104">La tarea Limpieza de mantenimiento no elimina automáticamente archivos incluidos en las subcarpetas del directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="df2c6-104">The Maintenance Cleanup task does not automatically delete files in the subfolders of the specified directory.</span></span> <span data-ttu-id="df2c6-105">Esta característica reduce la posibilidad de un ataque malintencionado que utilice la tarea Limpieza de mantenimiento para eliminar archivos.</span><span class="sxs-lookup"><span data-stu-id="df2c6-105">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span> <span data-ttu-id="df2c6-106">Si quiere eliminar archivos en las subcarpetas de primer nivel, hay que seleccionar **Incluir subcarpetas de primer nivel**.</span><span class="sxs-lookup"><span data-stu-id="df2c6-106">If you want to delete files in first-level subfolders, you must select **Include first-level subfolders**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="df2c6-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="df2c6-107">Options</span></span>  
 <span data-ttu-id="df2c6-108">**Connection**</span><span class="sxs-lookup"><span data-stu-id="df2c6-108">**Connection**</span></span>  
 <span data-ttu-id="df2c6-109">Muestra la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="df2c6-109">Displays the current connection.</span></span>  
  
 <span data-ttu-id="df2c6-110">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="df2c6-110">**New**</span></span>  
 <span data-ttu-id="df2c6-111">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="df2c6-111">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="df2c6-112">El cuadro de diálogo **Nueva conexión** se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="df2c6-112">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="df2c6-113">**Archivos de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="df2c6-113">**Backup files**</span></span>  
 <span data-ttu-id="df2c6-114">Elimina archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="df2c6-114">Delete backup files.</span></span>  
  
 <span data-ttu-id="df2c6-115">**Informes de texto de plan de mantenimiento**</span><span class="sxs-lookup"><span data-stu-id="df2c6-115">**Maintenance Plan text reports**</span></span>  
 <span data-ttu-id="df2c6-116">Elimina informes de texto de planes de mantenimientos ejecutados con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="df2c6-116">Delete text reports of previously run maintenance plans.</span></span>  
  
 <span data-ttu-id="df2c6-117">**Eliminar archivo específico**</span><span class="sxs-lookup"><span data-stu-id="df2c6-117">**Delete specific file**</span></span>  
 <span data-ttu-id="df2c6-118">Elimina el archivo específico que se indica en el cuadro **Nombre de archivo** .</span><span class="sxs-lookup"><span data-stu-id="df2c6-118">Delete the specific file provided in the **File name** box.</span></span>  
  
 <span data-ttu-id="df2c6-119">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="df2c6-119">**File name**</span></span>  
 <span data-ttu-id="df2c6-120">Ruta de acceso y nombre del archivo que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="df2c6-120">Path and name of the file to be deleted.</span></span>  
  
 <span data-ttu-id="df2c6-121">**Buscar en carpeta y eliminar archivos según su extensión**</span><span class="sxs-lookup"><span data-stu-id="df2c6-121">**Search folder and delete files based on an extension**</span></span>  
 <span data-ttu-id="df2c6-122">Elimina todos los archivos con la extensión especificada de la carpeta indicada.</span><span class="sxs-lookup"><span data-stu-id="df2c6-122">Delete all files with the specified extension in the specified folder.</span></span> <span data-ttu-id="df2c6-123">Utilice esta opción para eliminar varios archivos a la vez, como todos los archivos de copia de seguridad con la extensión .bak, en la carpeta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="df2c6-123">Use this to delete multiple files at once, such as all backup files with the .bak extension, in the Tuesday folder.</span></span>  
  
 <span data-ttu-id="df2c6-124">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="df2c6-124">**Folder**</span></span>  
 <span data-ttu-id="df2c6-125">Ruta de acceso y nombre de la carpeta que contiene los archivos que se van a eliminar.</span><span class="sxs-lookup"><span data-stu-id="df2c6-125">Path and name of the folder containing the files to be deleted.</span></span>  
  
 <span data-ttu-id="df2c6-126">**Extensión de archivo**</span><span class="sxs-lookup"><span data-stu-id="df2c6-126">**File extension**</span></span>  
 <span data-ttu-id="df2c6-127">Indique la extensión de archivo de los archivos que se van a eliminar.</span><span class="sxs-lookup"><span data-stu-id="df2c6-127">Provide the file extension of the files to be deleted.</span></span>  
  
 <span data-ttu-id="df2c6-128">**Incluir subcarpetas de primer nivel**</span><span class="sxs-lookup"><span data-stu-id="df2c6-128">**Include first-level subfolders**</span></span>  
 <span data-ttu-id="df2c6-129">Elimina archivos con la extensión especificada para **Extensión del archivo** en las subcarpetas de primer nivel, en **Carpeta**.</span><span class="sxs-lookup"><span data-stu-id="df2c6-129">Delete files with the extension specified for **File extension** from first-level subfolders under **Folder**.</span></span>  
  
 <span data-ttu-id="df2c6-130">**Eliminar archivos en función de la antigüedad del archivo en el tiempo de ejecución de la tarea**</span><span class="sxs-lookup"><span data-stu-id="df2c6-130">**Delete files based on the age of the file at task run time**</span></span>  
 <span data-ttu-id="df2c6-131">Especifique la antigüedad mínima que deben tener los archivos que quiere eliminar; para ello, especifique un número y una unidad de tiempo en el cuadro **Eliminar archivos anteriores a** .</span><span class="sxs-lookup"><span data-stu-id="df2c6-131">Specify the minimum age of the files that you want to delete by providing a number, and unit of time in the **Delete files older than the following** box.</span></span>  
  
 <span data-ttu-id="df2c6-132">**Eliminar archivos anteriores a**</span><span class="sxs-lookup"><span data-stu-id="df2c6-132">**Delete files older than the following**</span></span>  
 <span data-ttu-id="df2c6-133">Especifique la antigüedad mínima que deben tener los archivos que desea eliminar; para ello, especifique un número y una unidad de tiempo (Día, Semana, Mes o Año).</span><span class="sxs-lookup"><span data-stu-id="df2c6-133">Specify the minimum age of the files that you want to delete by providing a number, and unit of time (Day, Week, Month, or Year).</span></span> <span data-ttu-id="df2c6-134">Se eliminarán los archivos con una antigüedad mayor que el intervalo de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="df2c6-134">Files older than the time frame specified will be deleted.</span></span>  
  
 <span data-ttu-id="df2c6-135">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="df2c6-135">**View T-SQL**</span></span>  
 <span data-ttu-id="df2c6-136">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="df2c6-136">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df2c6-137">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="df2c6-137">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="df2c6-138">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="df2c6-138">New Connection Dialog Box</span></span>  
 <span data-ttu-id="df2c6-139">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="df2c6-139">**Connection name**</span></span>  
 <span data-ttu-id="df2c6-140">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="df2c6-140">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="df2c6-141">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="df2c6-141">**Select or enter a server name**</span></span>  
 <span data-ttu-id="df2c6-142">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="df2c6-142">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="df2c6-143">**...**</span><span class="sxs-lookup"><span data-stu-id="df2c6-143">**...**</span></span>  
 <span data-ttu-id="df2c6-144">Seleccione esta opción para ver la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="df2c6-144">Select to view the list of available servers.</span></span>  
  
 <span data-ttu-id="df2c6-145">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="df2c6-145">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="df2c6-146">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="df2c6-146">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="df2c6-147">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="df2c6-147">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="df2c6-148">Se conecta a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con la autenticación de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="df2c6-148">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="df2c6-149">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="df2c6-149">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="df2c6-150">Se conecta a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con la autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="df2c6-150">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="df2c6-151">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="df2c6-151">This option is not available.</span></span>  
  
 <span data-ttu-id="df2c6-152">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="df2c6-152">**User name**</span></span>  
 <span data-ttu-id="df2c6-153">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="df2c6-153">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="df2c6-154">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="df2c6-154">This option is not available.</span></span>  
  
 <span data-ttu-id="df2c6-155">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="df2c6-155">**Password**</span></span>  
 <span data-ttu-id="df2c6-156">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="df2c6-156">Provide a password to use when authenticating.</span></span> <span data-ttu-id="df2c6-157">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="df2c6-157">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2c6-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df2c6-158">See Also</span></span>  
 [<span data-ttu-id="df2c6-159">Planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="df2c6-159">Maintenance Plans</span></span>](maintenance-plans.md)  
  
  
