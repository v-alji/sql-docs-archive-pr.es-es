---
title: Editor de la tarea FTP (página transferencia de archivos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.filetransfer.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 37e52220-feb2-474c-ad88-fa1b1059acd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8094051e93c4165be6ae186bde394f9271d60669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670441"
---
# <a name="ftp-task-editor-file-transfer-page"></a><span data-ttu-id="d9890-102">Editor de la tarea FTP (página Transferencia de archivos)</span><span class="sxs-lookup"><span data-stu-id="d9890-102">FTP Task Editor (File Transfer Page)</span></span>
  <span data-ttu-id="d9890-103">Use la página **Transferencia de archivos** del cuadro de diálogo **Editor de la tarea FTP** para configurar la operación de FTP que realiza la tarea.</span><span class="sxs-lookup"><span data-stu-id="d9890-103">Use the **File Transfer** page of the **FTP Task Editor** dialog box to configure the FTP operation that the task performs.</span></span>  
  
 <span data-ttu-id="d9890-104">Para más información sobre esta tarea, vea [Tarea FTP](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="d9890-104">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d9890-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="d9890-105">Options</span></span>  
 <span data-ttu-id="d9890-106">**IsRemotePathVariable**</span><span class="sxs-lookup"><span data-stu-id="d9890-106">**IsRemotePathVariable**</span></span>  
 <span data-ttu-id="d9890-107">Indica si la ruta remota se almacena en una variable.</span><span class="sxs-lookup"><span data-stu-id="d9890-107">Indicate whether the remote path is stored in a variable.</span></span> <span data-ttu-id="d9890-108">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="d9890-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d9890-109">Value</span><span class="sxs-lookup"><span data-stu-id="d9890-109">Value</span></span>|<span data-ttu-id="d9890-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9890-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d9890-111">**True**</span><span class="sxs-lookup"><span data-stu-id="d9890-111">**True**</span></span>|<span data-ttu-id="d9890-112">La ruta de destino está almacenada en una variable.</span><span class="sxs-lookup"><span data-stu-id="d9890-112">The destination path is stored in a variable.</span></span> <span data-ttu-id="d9890-113">Al seleccionar este valor se muestra la opción dinámica **RemoteVariable**.</span><span class="sxs-lookup"><span data-stu-id="d9890-113">Selecting the value displays the dynamic option, **RemoteVariable**.</span></span>|  
|<span data-ttu-id="d9890-114">**False**</span><span class="sxs-lookup"><span data-stu-id="d9890-114">**False**</span></span>|<span data-ttu-id="d9890-115">La ruta de destino se especifica en un administrador de conexiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="d9890-115">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="d9890-116">Al seleccionar este valor se muestra la opción dinámica **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="d9890-116">Selecting the value displays the dynamic option, **RemotePath**.</span></span>|  
  
 <span data-ttu-id="d9890-117">**OverwriteFileAtDestination**</span><span class="sxs-lookup"><span data-stu-id="d9890-117">**OverwriteFileAtDestination**</span></span>  
 <span data-ttu-id="d9890-118">Especifica si se puede sobrescribir un archivo del destino.</span><span class="sxs-lookup"><span data-stu-id="d9890-118">Specify whether a file at the destination can be overwritten.</span></span>  
  
 <span data-ttu-id="d9890-119">**IsLocalPathVariable**</span><span class="sxs-lookup"><span data-stu-id="d9890-119">**IsLocalPathVariable**</span></span>  
 <span data-ttu-id="d9890-120">Indica si la ruta de acceso local está almacenada en una variable.</span><span class="sxs-lookup"><span data-stu-id="d9890-120">Indicate whether the local path is stored in a variable.</span></span> <span data-ttu-id="d9890-121">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="d9890-121">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d9890-122">Value</span><span class="sxs-lookup"><span data-stu-id="d9890-122">Value</span></span>|<span data-ttu-id="d9890-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9890-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d9890-124">**True**</span><span class="sxs-lookup"><span data-stu-id="d9890-124">**True**</span></span>|<span data-ttu-id="d9890-125">La ruta de destino está almacenada en una variable.</span><span class="sxs-lookup"><span data-stu-id="d9890-125">The destination path is stored in a variable.</span></span> <span data-ttu-id="d9890-126">Al seleccionar este valor se muestra la opción dinámica **LocalVariable**.</span><span class="sxs-lookup"><span data-stu-id="d9890-126">Selecting the value displays the dynamic option, **LocalVariable**.</span></span>|  
|<span data-ttu-id="d9890-127">**False**</span><span class="sxs-lookup"><span data-stu-id="d9890-127">**False**</span></span>|<span data-ttu-id="d9890-128">La ruta de destino se especifica en un administrador de conexiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="d9890-128">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="d9890-129">Al seleccionar este valor se muestra la opción dinámica **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="d9890-129">Selecting the value displays the dynamic option, **LocalPath**.</span></span>|  
  
 <span data-ttu-id="d9890-130">**operación**</span><span class="sxs-lookup"><span data-stu-id="d9890-130">**Operation**</span></span>  
 <span data-ttu-id="d9890-131">Seleccione la operación de FTP que se realizará.</span><span class="sxs-lookup"><span data-stu-id="d9890-131">Select the FTP operation to perform.</span></span> <span data-ttu-id="d9890-132">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="d9890-132">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d9890-133">Value</span><span class="sxs-lookup"><span data-stu-id="d9890-133">Value</span></span>|<span data-ttu-id="d9890-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9890-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d9890-135">**Enviar archivos**</span><span class="sxs-lookup"><span data-stu-id="d9890-135">**Send files**</span></span>|<span data-ttu-id="d9890-136">Envía archivos.</span><span class="sxs-lookup"><span data-stu-id="d9890-136">Send files.</span></span> <span data-ttu-id="d9890-137">Al seleccionar este valor se muestran las opciones dinámicas **LocalVariable**, **LocalPathRemoteVariable** y **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="d9890-137">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="d9890-138">**Recibir archivos**</span><span class="sxs-lookup"><span data-stu-id="d9890-138">**Receive files**</span></span>|<span data-ttu-id="d9890-139">Recibe archivos.</span><span class="sxs-lookup"><span data-stu-id="d9890-139">Receive files.</span></span> <span data-ttu-id="d9890-140">Al seleccionar este valor se muestran las opciones dinámicas **LocalVariable**, **LocalPathRemoteVariable** y **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="d9890-140">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="d9890-141">**Crear directorio local**</span><span class="sxs-lookup"><span data-stu-id="d9890-141">**Create local directory**</span></span>|<span data-ttu-id="d9890-142">Crea un directorio local.</span><span class="sxs-lookup"><span data-stu-id="d9890-142">Create a local directory.</span></span> <span data-ttu-id="d9890-143">Al seleccionar este valor se muestran las opciones dinámicas **LocalVariable** y **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="d9890-143">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="d9890-144">**Crear directorio remoto**</span><span class="sxs-lookup"><span data-stu-id="d9890-144">**Create remote directory**</span></span>|<span data-ttu-id="d9890-145">Crea un directorio remoto.</span><span class="sxs-lookup"><span data-stu-id="d9890-145">Create a remote directory.</span></span> <span data-ttu-id="d9890-146">Al seleccionar este valor se muestran las opciones dinámicas **RemoteVariable** y **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="d9890-146">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotelPath**.</span></span>|  
|<span data-ttu-id="d9890-147">**Quitar directorio local**</span><span class="sxs-lookup"><span data-stu-id="d9890-147">**Remove local directory**</span></span>|<span data-ttu-id="d9890-148">Quita un directorio local.</span><span class="sxs-lookup"><span data-stu-id="d9890-148">Removes a local directory.</span></span> <span data-ttu-id="d9890-149">Al seleccionar este valor se muestran las opciones dinámicas **LocalVariable** y **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="d9890-149">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="d9890-150">**Quitar directorio remoto**</span><span class="sxs-lookup"><span data-stu-id="d9890-150">**Remove remote directory**</span></span>|<span data-ttu-id="d9890-151">Quita un directorio remoto.</span><span class="sxs-lookup"><span data-stu-id="d9890-151">Remove a remote directory.</span></span> <span data-ttu-id="d9890-152">Al seleccionar este valor se muestran las opciones dinámicas **RemoteVariable** y **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="d9890-152">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="d9890-153">**Eliminar archivos locales**</span><span class="sxs-lookup"><span data-stu-id="d9890-153">**Delete local files**</span></span>|<span data-ttu-id="d9890-154">Elimina archivos locales.</span><span class="sxs-lookup"><span data-stu-id="d9890-154">Delete local files.</span></span> <span data-ttu-id="d9890-155">Al seleccionar este valor se muestran las opciones dinámicas **LocalVariable** y **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="d9890-155">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="d9890-156">**Eliminar archivos remotos**</span><span class="sxs-lookup"><span data-stu-id="d9890-156">**Delete remote files**</span></span>|<span data-ttu-id="d9890-157">Elimina archivos remotos.</span><span class="sxs-lookup"><span data-stu-id="d9890-157">Delete remote files.</span></span> <span data-ttu-id="d9890-158">Al seleccionar este valor se muestran las opciones dinámicas **RemoteVariable** y **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="d9890-158">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
  
 <span data-ttu-id="d9890-159">**IsTransferASCII**</span><span class="sxs-lookup"><span data-stu-id="d9890-159">**IsTransferASCII**</span></span>  
 <span data-ttu-id="d9890-160">Indica si los archivos transferidos a y desde el servidor FTP remoto deben transferirse en modo ASCII.</span><span class="sxs-lookup"><span data-stu-id="d9890-160">Indicate whether files transferred to and from the remote FTP server should be transferred in ASCII mode.</span></span>  
  
## <a name="isremotepathvariable-dynamic-options"></a><span data-ttu-id="d9890-161">Opciones dinámicas de IsRemotePathVariable</span><span class="sxs-lookup"><span data-stu-id="d9890-161">IsRemotePathVariable Dynamic Options</span></span>  
  
### <a name="isremotepathvariable--true"></a><span data-ttu-id="d9890-162">IsRemotePathVariable = True</span><span class="sxs-lookup"><span data-stu-id="d9890-162">IsRemotePathVariable = True</span></span>  
 <span data-ttu-id="d9890-163">**RemoteVariable**</span><span class="sxs-lookup"><span data-stu-id="d9890-163">**RemoteVariable**</span></span>  
 <span data-ttu-id="d9890-164">Seleccione una variable existente definida por el usuario o haga clic en \<**New variable...**> para crear una.</span><span class="sxs-lookup"><span data-stu-id="d9890-164">Select an existing user-defined variable, or click \<**New variable...**> to create a user-defined variable.</span></span>  
  
 <span data-ttu-id="d9890-165">**Temas relacionados:** [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), Agregar variable</span><span class="sxs-lookup"><span data-stu-id="d9890-165">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="isremotepathvariable--false"></a><span data-ttu-id="d9890-166">IsRemotePathVariable = False</span><span class="sxs-lookup"><span data-stu-id="d9890-166">IsRemotePathVariable = False</span></span>  
 <span data-ttu-id="d9890-167">**RemotePath**</span><span class="sxs-lookup"><span data-stu-id="d9890-167">**RemotePath**</span></span>  
 <span data-ttu-id="d9890-168">Seleccione un administrador de conexiones FTP existente o haga clic en \<**New connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="d9890-168">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="d9890-169">**Temas relacionados:** [Administrador de conexiones FTP](connection-manager/ftp-connection-manager.md), [Editor del administrador de conexiones FTP](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="d9890-169">**Related Topics:** [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
## <a name="islocalpathvariable-dynamic-options"></a><span data-ttu-id="d9890-170">Opciones dinámicas de IsLocalPathVariable</span><span class="sxs-lookup"><span data-stu-id="d9890-170">IsLocalPathVariable Dynamic Options</span></span>  
  
### <a name="islocalpathvariable--true"></a><span data-ttu-id="d9890-171">IsLocalPathVariable = True</span><span class="sxs-lookup"><span data-stu-id="d9890-171">IsLocalPathVariable = True</span></span>  
 <span data-ttu-id="d9890-172">**LocalVariable**</span><span class="sxs-lookup"><span data-stu-id="d9890-172">**LocalVariable**</span></span>  
 <span data-ttu-id="d9890-173">Seleccione una variable existente definida por el usuario o haga clic en \<**New variable...**> para crear una.</span><span class="sxs-lookup"><span data-stu-id="d9890-173">Select an existing user-defined variable, or click \<**New variable...**> to create a variable.</span></span>  
  
 <span data-ttu-id="d9890-174">**Temas relacionados:** [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), Agregar variable</span><span class="sxs-lookup"><span data-stu-id="d9890-174">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="islocalpathvariable--false"></a><span data-ttu-id="d9890-175">IsLocalPathVariable = False</span><span class="sxs-lookup"><span data-stu-id="d9890-175">IsLocalPathVariable = False</span></span>  
 <span data-ttu-id="d9890-176">**LocalPath**</span><span class="sxs-lookup"><span data-stu-id="d9890-176">**LocalPath**</span></span>  
 <span data-ttu-id="d9890-177">Seleccione un administrador de conexiones de archivos existente o haga clic en \<**New connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="d9890-177">Select an existing File connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="d9890-178">**Temas relacionados**: [Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="d9890-178">**Related Topics**: [Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9890-179">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9890-179">See Also</span></span>  
 <span data-ttu-id="d9890-180">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d9890-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d9890-181">[Editor de la tarea FTP &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d9890-181">[FTP Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="d9890-182">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="d9890-182">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
