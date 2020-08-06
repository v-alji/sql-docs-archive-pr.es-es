---
title: Editor de la tarea ejecutar paquete | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executepackagetask.parameter.F1
- sql12.dts.designer.executepackagetask.package.f1
- sql12.dts.designer.executepackagetask.general.f1
ms.assetid: c2c96b4f-eb10-4d8b-be34-88edfd0785fb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9b2e18516e1f5c1b7af56bd1e84ef875557fd49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673788"
---
# <a name="execute-package-task-editor"></a><span data-ttu-id="d6739-102">Editor de la tarea Ejecutar paquete</span><span class="sxs-lookup"><span data-stu-id="d6739-102">Execute Package Task Editor</span></span>
  <span data-ttu-id="d6739-103">Utilice el Editor de la tarea Ejecutar paquete para configurar la tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="d6739-103">Use the Execute Package Task Editor to configure the Execute Package Task.</span></span> <span data-ttu-id="d6739-104">La tarea Ejecutar paquete amplía las capacidades empresariales de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , ya que permite que los paquetes ejecuten otros paquetes como parte de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d6739-104">The Execute Package task extends the enterprise capabilities of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by letting packages run other packages as part of a workflow.</span></span>  
  
 <span data-ttu-id="d6739-105">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="d6739-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="d6739-106">Abrir el Editor de la tarea Ejecutar paquete</span><span class="sxs-lookup"><span data-stu-id="d6739-106">Open the Execute Package Task Editor</span></span>](#open)  
  
-   [<span data-ttu-id="d6739-107">Establecer las opciones de la página General</span><span class="sxs-lookup"><span data-stu-id="d6739-107">Set the Options on the General Page</span></span>](#general)  
  
-   [<span data-ttu-id="d6739-108">Establecer las opciones de la página Paquete</span><span class="sxs-lookup"><span data-stu-id="d6739-108">Set the Options on the Package Page</span></span>](#package)  
  
-   [<span data-ttu-id="d6739-109">Establecer las opciones de la página Enlaces de parámetro</span><span class="sxs-lookup"><span data-stu-id="d6739-109">Set the Options on the Parameter Bindings Page</span></span>](#parameter)  
  
##  <a name="open-the-execute-package-task-editor"></a><a name="open"></a> <span data-ttu-id="d6739-110">Abrir el Editor de la tarea Ejecutar paquete</span><span class="sxs-lookup"><span data-stu-id="d6739-110">Open the Execute Package Task Editor</span></span>  
  
1.  <span data-ttu-id="d6739-111">Abra un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] que contenga una tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="d6739-111">Open an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] that contains an Execute Package task.</span></span>  
  
2.  <span data-ttu-id="d6739-112">Haga clic con el botón derecho en la tarea en el Diseñador SSIS y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d6739-112">Right-click the task in the SSIS Designer, and then click **Edit**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="d6739-113">Establecer las opciones de la página General</span><span class="sxs-lookup"><span data-stu-id="d6739-113">Set the Options on the General Page</span></span>  
 <span data-ttu-id="d6739-114">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="d6739-114">**Name**</span></span>  
 <span data-ttu-id="d6739-115">Escriba un nombre único para la tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="d6739-115">Provide a unique name for the Execute Package task.</span></span> <span data-ttu-id="d6739-116">Este nombre se utiliza como etiqueta en el icono de tarea.</span><span class="sxs-lookup"><span data-stu-id="d6739-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6739-117">Los nombres de tarea deben ser únicos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="d6739-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="d6739-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d6739-118">**Description**</span></span>  
 <span data-ttu-id="d6739-119">Escriba una descripción de la tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="d6739-119">Type a description of the Execute Package task.</span></span>  
  
##  <a name="set-the-options-on-the-package-page"></a><a name="package"></a> <span data-ttu-id="d6739-120">Establecer las opciones de la página Paquete</span><span class="sxs-lookup"><span data-stu-id="d6739-120">Set the Options on the Package Page</span></span>  
 <span data-ttu-id="d6739-121">**ReferenceType**</span><span class="sxs-lookup"><span data-stu-id="d6739-121">**ReferenceType**</span></span>  
 <span data-ttu-id="d6739-122">Seleccione **Referencia de proyecto** para los paquetes secundarios que están en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6739-122">Select **Project Reference** for child packages that are in the project.</span></span> <span data-ttu-id="d6739-123">Seleccione **Referencia externa** para los paquetes secundarios que se encuentran fuera del paquete</span><span class="sxs-lookup"><span data-stu-id="d6739-123">Select **External Reference** for child packages that are located outside the package</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6739-124">La opción **ReferenceType** es de solo lectura y se establece en **Referencia externa** si el proyecto que contiene el paquete no se ha convertido al modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="d6739-124">The **ReferenceType** option is ready-only and set to **External Reference** if the project that contains the package has not been converted to the project deployment model.</span></span> <span data-ttu-id="d6739-125">Para más información sobre la conversión, vea [Implementación de paquetes en el servidor de Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="d6739-125">For more information about conversion, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="d6739-126">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="d6739-126">**Password**</span></span>  
 <span data-ttu-id="d6739-127">Si el paquete secundario está protegido con contraseña, tiene que proporcionar esta contraseña o hacer clic en el botón de puntos suspensivos (…) y crear una contraseña.</span><span class="sxs-lookup"><span data-stu-id="d6739-127">If the child package is password protected, provide the password for the child package, or click the ellipsis button (...) and create a new password for the child package.</span></span>  
  
 `ExecuteOutOfProcess`  
 <span data-ttu-id="d6739-128">Especifique si el paquete secundario se ejecuta en el proceso del paquete primario o en un proceso independiente.</span><span class="sxs-lookup"><span data-stu-id="d6739-128">Specify whether the child package runs in the process of the parent package or in a separate process.</span></span> <span data-ttu-id="d6739-129">De forma predeterminada, la propiedad ExecuteOutOfProcess de la tarea ejecutar paquete se establece en `False` y el paquete secundario se ejecuta en el mismo proceso que el paquete primario.</span><span class="sxs-lookup"><span data-stu-id="d6739-129">By default, the ExecuteOutOfProcess property of the Execute Package task is set to `False`, and the child package runs in the same process as the parent package.</span></span> <span data-ttu-id="d6739-130">Si establece esta propiedad en `true`, el paquete secundario se ejecuta en un proceso independiente.</span><span class="sxs-lookup"><span data-stu-id="d6739-130">If you set this property to `true`, the child package runs in a separate process.</span></span> <span data-ttu-id="d6739-131">Esto puede ralentizar el inicio del paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="d6739-131">This may slow down the launching of the child package.</span></span> <span data-ttu-id="d6739-132">Además, si se establece la propiedad en `true`, no se podrá depurar el paquete si realizó únicamente una instalación de herramientas; deberá instalar el producto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6739-132">In addition, if set the property to `true`, you cannot debug the package in a tools-only install; you must install the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] product.</span></span> <span data-ttu-id="d6739-133">Para más información, vea [Instalar Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="d6739-133">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
### <a name="referencetype-dynamic-options"></a><span data-ttu-id="d6739-134">Opciones dinámicas de ReferenceType</span><span class="sxs-lookup"><span data-stu-id="d6739-134">ReferenceType Dynamic Options</span></span>  
  
#### <a name="referencetype--external-reference"></a><span data-ttu-id="d6739-135">ReferenceType = Referencia externa</span><span class="sxs-lookup"><span data-stu-id="d6739-135">ReferenceType = External Reference</span></span>  
 <span data-ttu-id="d6739-136">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="d6739-136">**Location**</span></span>  
 <span data-ttu-id="d6739-137">Seleccione la ubicación del paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="d6739-137">Select the location of the child package.</span></span> <span data-ttu-id="d6739-138">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="d6739-138">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d6739-139">Value</span><span class="sxs-lookup"><span data-stu-id="d6739-139">Value</span></span>|<span data-ttu-id="d6739-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6739-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6739-141">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d6739-141">**SQL Server**</span></span>|<span data-ttu-id="d6739-142">Establezca la ubicación de una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6739-142">Set the location to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="d6739-143">**Sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="d6739-143">**File system**</span></span>|<span data-ttu-id="d6739-144">Permite establecer como ubicación el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="d6739-144">Set the location to the file system.</span></span>|  
  
 <span data-ttu-id="d6739-145">**Connection**</span><span class="sxs-lookup"><span data-stu-id="d6739-145">**Connection**</span></span>  
 <span data-ttu-id="d6739-146">Seleccione el tipo de ubicación de almacenamiento para el paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="d6739-146">Select the type of storage location for the child package.</span></span>  
  
 <span data-ttu-id="d6739-147">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="d6739-147">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="d6739-148">Muestra el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="d6739-148">Displays the package name.</span></span>  
  
#### <a name="referencetype--project-reference"></a><span data-ttu-id="d6739-149">ReferenceType = Referencia de proyecto</span><span class="sxs-lookup"><span data-stu-id="d6739-149">ReferenceType = Project Reference</span></span>  
 <span data-ttu-id="d6739-150">**PackageNameFromProjectReference**</span><span class="sxs-lookup"><span data-stu-id="d6739-150">**PackageNameFromProjectReference**</span></span>  
 <span data-ttu-id="d6739-151">Seleccione un paquete incluido en el proyecto para que sea el paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="d6739-151">Select a package contained in the project, to be the child package.</span></span>  
  
### <a name="location-dynamic-options"></a><span data-ttu-id="d6739-152">Opciones dinámicas de ubicación</span><span class="sxs-lookup"><span data-stu-id="d6739-152">Location Dynamic Options</span></span>  
  
#### <a name="location--sql-server"></a><span data-ttu-id="d6739-153">Ubicación = SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6739-153">Location = SQL Server</span></span>  
 <span data-ttu-id="d6739-154">**Connection**</span><span class="sxs-lookup"><span data-stu-id="d6739-154">**Connection**</span></span>  
 <span data-ttu-id="d6739-155">Seleccione un administrador de conexiones OLE DB de la lista o haga clic en \<**New connection...**> para crear un administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="d6739-155">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="d6739-156">**Temas relacionados:** [Administrador de conexiones OLE DB](connection-manager/ole-db-connection-manager.md), [Configurar el administrador de conexiones OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="d6739-156">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="d6739-157">**PackageName**</span><span class="sxs-lookup"><span data-stu-id="d6739-157">**PackageName**</span></span>  
 <span data-ttu-id="d6739-158">Escriba el nombre del paquete secundario, o bien haga clic en los puntos suspensivos (…) y, después, busque el paquete.</span><span class="sxs-lookup"><span data-stu-id="d6739-158">Type the name of the child package, or click the ellipsis (...) and then locate the package.</span></span>  
  
#### <a name="location--file-system"></a><span data-ttu-id="d6739-159">Ubicación = Sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="d6739-159">Location = File system</span></span>  
 <span data-ttu-id="d6739-160">**Connection**</span><span class="sxs-lookup"><span data-stu-id="d6739-160">**Connection**</span></span>  
 <span data-ttu-id="d6739-161">Seleccione un administrador de conexiones de archivos de la lista o haga clic en \<**New connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="d6739-161">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="d6739-162">**Temas relacionados:** [Administrador de conexiones de archivos](connection-manager/file-connection-manager.md), [Editor de administrador de conexiones de archivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="d6739-162">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="d6739-163">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="d6739-163">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="d6739-164">Muestra el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="d6739-164">Displays the package name.</span></span>  
  
##  <a name="set-the-options-on-the-parameter-bindings-page"></a><a name="parameter"></a> <span data-ttu-id="d6739-165">Establecer las opciones de la página Enlaces de parámetro</span><span class="sxs-lookup"><span data-stu-id="d6739-165">Set the Options on the Parameter Bindings Page</span></span>  
 <span data-ttu-id="d6739-166">Puede pasar valores del paquete primario o del proyecto al paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="d6739-166">You can pass values from the parent package or the project, to the child package.</span></span> <span data-ttu-id="d6739-167">El proyecto debe utilizar el modelo de implementación del proyecto y el paquete secundario debe estar incluido en el mismo proyecto que contiene el paquete primario.</span><span class="sxs-lookup"><span data-stu-id="d6739-167">The project must use the project deployment model and the child package must be contained in the same project that contains the parent package.</span></span>  
  
 <span data-ttu-id="d6739-168">Para obtener información sobre cómo convertir un proyecto al modelo de implementación de proyectos, vea [Implementación de paquetes en el servidor de Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="d6739-168">For information about converting projects to the project deployment model, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="d6739-169">**Parámetro de paquete secundario**</span><span class="sxs-lookup"><span data-stu-id="d6739-169">**Child package parameter**</span></span>  
 <span data-ttu-id="d6739-170">Escriba o seleccione un nombre para el parámetro de paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="d6739-170">Enter or select a name for the child package parameter.</span></span>  
  
 <span data-ttu-id="d6739-171">**Enlazar un parámetro o variable**</span><span class="sxs-lookup"><span data-stu-id="d6739-171">**Binding parameter or variable**</span></span>  
 <span data-ttu-id="d6739-172">Seleccione el parámetro o variable que contiene el valor que desea pasar al paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="d6739-172">Select the parameter or variable that contains the value that you want to pass to the child package.</span></span>  
  
 <span data-ttu-id="d6739-173">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="d6739-173">**Add**</span></span>  
 <span data-ttu-id="d6739-174">Haga clic para asignar un parámetro o variable a un parámetro de paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="d6739-174">Click to map a parameter or variable to a child package parameter.</span></span>  
  
 <span data-ttu-id="d6739-175">**Remove**</span><span class="sxs-lookup"><span data-stu-id="d6739-175">**Remove**</span></span>  
 <span data-ttu-id="d6739-176">Haga clic para quitar una asignación entre un parámetro o variable y un parámetro de paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="d6739-176">Click to remove a mapping between a parameter or variable and a child package parameter.</span></span>  
  
  
