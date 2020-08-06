---
title: Editor de la tarea transferir bases de datos (página bases de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.database.f1
helpviewer_keywords:
- Transfer Database Task Editor
ms.assetid: ccdb74d0-4bea-420c-a726-2e0eb8957e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df4452e28a32463a7825e9c64cfd053f98c53ee8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743599"
---
# <a name="transfer-database-task-editor-databases-page"></a><span data-ttu-id="47f62-102">Editor de la tarea Transferir bases de datos (página Bases de datos)</span><span class="sxs-lookup"><span data-stu-id="47f62-102">Transfer Database Task Editor (Databases Page)</span></span>
  <span data-ttu-id="47f62-103">Utilice la página **Bases de datos** del cuadro de diálogo **Editor de la tarea Transferir bases de datos** para especificar propiedades para las bases de datos de origen y destino implicadas en la tarea Transferir bases de datos.</span><span class="sxs-lookup"><span data-stu-id="47f62-103">Use the **Databases** page of the **Transfer Database Task Editor** dialog box to specify properties for the source and destination databases involved in the Transfer Database task.</span></span> <span data-ttu-id="47f62-104">La tarea Transferir bases de datos copia o mueve una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] entre dos instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47f62-104">The Transfer Database task copies or moves a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database between two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="47f62-105">Esta tarea también puede utilizarse para copiar una base de datos en el mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="47f62-105">This task can also be used to copy a database within the same server.</span></span> <span data-ttu-id="47f62-106">Para obtener más información sobre esta tarea, vea [Tarea Transferir bases de datos](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="47f62-106">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="47f62-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="47f62-107">Options</span></span>  
 <span data-ttu-id="47f62-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="47f62-108">**SourceConnection**</span></span>  
 <span data-ttu-id="47f62-109">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una nueva conexión al servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="47f62-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="47f62-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="47f62-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="47f62-111">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una nueva conexión al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="47f62-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="47f62-112">**DestinationDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="47f62-112">**DestinationDatabaseName**</span></span>  
 <span data-ttu-id="47f62-113">Especifique el nombre de la base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="47f62-113">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database on the destination server.</span></span>  
  
 <span data-ttu-id="47f62-114">Para rellenar automáticamente este campo con el nombre de la base de datos de origen, especifique los parámetros **SourceConnection** y **SourceDatabaseName** primero.</span><span class="sxs-lookup"><span data-stu-id="47f62-114">To automatically populate this field with the source database name, specify the **SourceConnection** and **SourceDatabaseName** first.</span></span>  
  
 <span data-ttu-id="47f62-115">Para cambiar el nombre de la base de datos en el servidor de destino, escriba el nuevo nombre en este campo.</span><span class="sxs-lookup"><span data-stu-id="47f62-115">To rename the database on the destination server, type the new name in this field.</span></span>  
  
 <span data-ttu-id="47f62-116">**DestinationDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="47f62-116">**DestinationDatabaseFiles**</span></span>  
 <span data-ttu-id="47f62-117">Especifica los nombres y ubicaciones de los archivos de la base de datos en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="47f62-117">Specifies the names and locations of the database files on the destination server.</span></span>  
  
 <span data-ttu-id="47f62-118">Para rellenar automáticamente este campo con los nombres y ubicaciones de los archivos de la base de datos de origen, especifique los parámetros **SourceConnection**, **SourceDatabaseName**y **SourceDatabaseFiles** primero.</span><span class="sxs-lookup"><span data-stu-id="47f62-118">To automatically populate this field with the source database file names and locations, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first.</span></span>  
  
 <span data-ttu-id="47f62-119">Para cambiar el nombre de los archivos de la base de datos o especificar las nuevas ubicaciones en el servidor de destino, rellene este campo con la información de la base de datos de origen y, a continuación, haga clic en el botón Examinar.</span><span class="sxs-lookup"><span data-stu-id="47f62-119">To rename the database files or to specify the new locations on the destination server, populate this field with the source database information, and then click the browse button.</span></span> <span data-ttu-id="47f62-120">En el cuadro de diálogo **Archivos de base de datos de destino** , edite el **archivo de destino**, la **carpeta de destino**o el **recurso compartido de archivos de red**.</span><span class="sxs-lookup"><span data-stu-id="47f62-120">In the **Destination database files** dialog box, edit the **Destination File**, **Destination Folder**, or **Network File Share**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47f62-121">Si busca los archivos de la base de datos mediante el botón Examinar, la ubicación de los archivos se especifica con la notación de la unidad local; por ejemplo, c:\\.</span><span class="sxs-lookup"><span data-stu-id="47f62-121">If you locate the database files by using the browse button, the file location is entered using the local drive notation: for example, c:\\.</span></span> <span data-ttu-id="47f62-122">Debe reemplazar ésta por la notación del recurso compartido de red, incluidos los nombres del equipo y del recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="47f62-122">You must replace this with the network share notation, including the computer name and share name.</span></span> <span data-ttu-id="47f62-123">Si se utiliza el recurso compartido administrativo predeterminado, debe usar la notación $ y tener acceso administrativo al recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="47f62-123">If the default administrative share is used, you must use the $ notation, and have administrative access to the share.</span></span>  
  
 <span data-ttu-id="47f62-124">**DestinationOverwrite**</span><span class="sxs-lookup"><span data-stu-id="47f62-124">**DestinationOverwrite**</span></span>  
 <span data-ttu-id="47f62-125">Especifique si la base de datos del servidor de destino se puede sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="47f62-125">Specify whether the database on the destination server can be overwritten.</span></span>  
  
 <span data-ttu-id="47f62-126">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="47f62-126">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="47f62-127">Value</span><span class="sxs-lookup"><span data-stu-id="47f62-127">Value</span></span>|<span data-ttu-id="47f62-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="47f62-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="47f62-129">**True**</span><span class="sxs-lookup"><span data-stu-id="47f62-129">**True**</span></span>|<span data-ttu-id="47f62-130">Sobrescribir la base de datos del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="47f62-130">Overwrite destination server database.</span></span>|  
|<span data-ttu-id="47f62-131">**False**</span><span class="sxs-lookup"><span data-stu-id="47f62-131">**False**</span></span>|<span data-ttu-id="47f62-132">No sobrescribir la base de datos del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="47f62-132">Do not overwrite destination server database.</span></span>|  
  
> [!CAUTION]  
>  <span data-ttu-id="47f62-133">Los datos de la base de datos del servidor de destino se sobrescribirán si especifica **True** para **DestinationOverwrite**, lo cual puede conllevar una pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="47f62-133">The data in the destination server database will be overwritten if you specify **True** for **DestinationOverwrite**, which may result in data loss.</span></span> <span data-ttu-id="47f62-134">Para evitar que ésta se produzca, realice una copia de seguridad de la base de datos del servidor de destino en otra ubicación antes de ejecutar la tarea Transferir bases de datos.</span><span class="sxs-lookup"><span data-stu-id="47f62-134">To avoid this, back up the destination server database to another location before executing the Transfer Database task.</span></span>  
  
 <span data-ttu-id="47f62-135">**Acción**</span><span class="sxs-lookup"><span data-stu-id="47f62-135">**Action**</span></span>  
 <span data-ttu-id="47f62-136">Permite especificar si la tarea **copiará** o **moverá** la base de datos al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="47f62-136">Specify whether the task will **Copy** or **Move** the database to the destination server.</span></span>  
  
 <span data-ttu-id="47f62-137">**Método**</span><span class="sxs-lookup"><span data-stu-id="47f62-137">**Method**</span></span>  
 <span data-ttu-id="47f62-138">Permite especificar si la tarea se ejecutará mientras la base de datos del servidor de origen esté en modo en línea o modo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="47f62-138">Specify whether the task will be executed while the database on the source server is in online or offline mode.</span></span>  
  
 <span data-ttu-id="47f62-139">Para transferir una base de datos en modo sin conexión, el usuario que ejecute el paquete debe ser miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="47f62-139">To transfer a database using offline mode, the user that runs the package must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="47f62-140">Para transferir una base de datos en modo en línea, el usuario que ejecute el paquete debe ser miembro del rol fijo de servidor **sysadmin** o el propietario de la base de datos seleccionada (**dbo**).</span><span class="sxs-lookup"><span data-stu-id="47f62-140">To transfer a database using the online mode, the user that runs the package must be a member of the **sysadmin** fixed server role, or the database owner (**dbo**) of the selected database.</span></span>  
  
 <span data-ttu-id="47f62-141">**SourceDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="47f62-141">**SourceDatabaseName**</span></span>  
 <span data-ttu-id="47f62-142">Permite seleccionar el nombre de la base de datos que se va a copiar o mover.</span><span class="sxs-lookup"><span data-stu-id="47f62-142">Select the name of the database to be copied or moved.</span></span>  
  
 <span data-ttu-id="47f62-143">**SourceDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="47f62-143">**SourceDatabaseFiles**</span></span>  
 <span data-ttu-id="47f62-144">Haga clic en el botón Examinar para seleccionar los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="47f62-144">Click the browse button to select the database files.</span></span>  
  
 <span data-ttu-id="47f62-145">**ReattachSourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="47f62-145">**ReattachSourceDatabase**</span></span>  
 <span data-ttu-id="47f62-146">Permite especificar si la tarea intentará volver a adjuntar la base de datos de origen en caso de error.</span><span class="sxs-lookup"><span data-stu-id="47f62-146">Specify whether the task will attempt to reattach the source database if a failure occurs.</span></span>  
  
 <span data-ttu-id="47f62-147">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="47f62-147">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="47f62-148">Value</span><span class="sxs-lookup"><span data-stu-id="47f62-148">Value</span></span>|<span data-ttu-id="47f62-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="47f62-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="47f62-150">**True**</span><span class="sxs-lookup"><span data-stu-id="47f62-150">**True**</span></span>|<span data-ttu-id="47f62-151">Volver a adjuntar la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="47f62-151">Reattach source database.</span></span>|  
|<span data-ttu-id="47f62-152">**False**</span><span class="sxs-lookup"><span data-stu-id="47f62-152">**False**</span></span>|<span data-ttu-id="47f62-153">No volver a adjuntar la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="47f62-153">Do not reattach source database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47f62-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47f62-154">See Also</span></span>  
 <span data-ttu-id="47f62-155">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="47f62-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="47f62-156">[Tareas de Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="47f62-156">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="47f62-157">[Editor de la tarea transferir bases de datos &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="47f62-157">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="47f62-158">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="47f62-158">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="47f62-159">Administrador de conexiones SMO</span><span class="sxs-lookup"><span data-stu-id="47f62-159">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
