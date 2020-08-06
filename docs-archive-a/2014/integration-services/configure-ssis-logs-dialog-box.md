---
title: Cuadro de diálogo configurar registros de SSIS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.configuredtslogs.loggingdetails.f1
- sql12.dts.designer.configuredtslogs.providersandlogs.f1
- sql12.dts.designer.configuredtslogs.containers.f1
helpviewer_keywords:
- Configure SSIS Logs dialog box
ms.assetid: 4b980275-cd9a-4943-8c36-727d51f9a484
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 252b45765fb784790bcca0fb86e2e56e7e7baddc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671627"
---
# <a name="configure-ssis-logs-dialog-box"></a><span data-ttu-id="81d01-102">Configurar registros de SSIS, cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="81d01-102">Configure SSIS Logs Dialog Box</span></span>
  <span data-ttu-id="81d01-103">Use el cuadro de diálogo **Configurar registros de SSIS** para definir las opciones de registro de un paquete.</span><span class="sxs-lookup"><span data-stu-id="81d01-103">Use the **Configure SSIS Logs** dialog box to define logging options for a package.</span></span>  
  
 <span data-ttu-id="81d01-104">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="81d01-104">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="81d01-105">Abrir el cuadro de diálogo Configurar registros de SSIS</span><span class="sxs-lookup"><span data-stu-id="81d01-105">Open the Configure SSIS Logs Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="81d01-106">Configurar las opciones en el panel Contenedores</span><span class="sxs-lookup"><span data-stu-id="81d01-106">Configure the Options in the Containers Pane</span></span>](#container)  
  
3.  [<span data-ttu-id="81d01-107">Configurar las opciones en la pestaña Proveedores y registros</span><span class="sxs-lookup"><span data-stu-id="81d01-107">Configure the Options on the Providers and Logs Tab</span></span>](#provider)  
  
4.  [<span data-ttu-id="81d01-108">Configurar las opciones en la pestaña Detalles</span><span class="sxs-lookup"><span data-stu-id="81d01-108">Configure the Options on the Details Tab</span></span>](#detail)  
  
##  <a name="open-the-configure-ssis-logs-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="81d01-109">Abrir el cuadro de diálogo Configurar registros de SSIS</span><span class="sxs-lookup"><span data-stu-id="81d01-109">Open the Configure SSIS Logs Dialog Box</span></span>  
 <span data-ttu-id="81d01-110">**Para abrir el cuadro de diálogo Configurar registros de SSIS**</span><span class="sxs-lookup"><span data-stu-id="81d01-110">**To open the Configure SSIS Logs dialog box**</span></span>  
  
-   <span data-ttu-id="81d01-111">En el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , haga clic en **Registro** en el menú **SSIS** .</span><span class="sxs-lookup"><span data-stu-id="81d01-111">In the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click **Logging** on the **SSIS** menu.</span></span>  
  
##  <a name="configure-the-options-in-the-containers-pane"></a><a name="container"></a> <span data-ttu-id="81d01-112">Configurar las opciones en el panel Contenedores</span><span class="sxs-lookup"><span data-stu-id="81d01-112">Configure the Options in the Containers Pane</span></span>  
 <span data-ttu-id="81d01-113">Utilice el panel **Contenedores** del cuadro de diálogo **Configurar registros de SSIS** para habilitar el paquete y sus contenedores para registro.</span><span class="sxs-lookup"><span data-stu-id="81d01-113">Use the **Containers** pane of the **Configure SSIS Logs** dialog box to enable the package and its containers for logging.</span></span>  
  
### <a name="options"></a><span data-ttu-id="81d01-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="81d01-114">Options</span></span>  
 <span data-ttu-id="81d01-115">**Contenedores**</span><span class="sxs-lookup"><span data-stu-id="81d01-115">**Containers**</span></span>  
 <span data-ttu-id="81d01-116">Active las casillas en la vista jerárquica para habilitar el paquete y sus contenedores para registro:</span><span class="sxs-lookup"><span data-stu-id="81d01-116">Select the check boxes in the hierarchical view to enable the package and its containers for logging:</span></span>  
  
-   <span data-ttu-id="81d01-117">Si no se activan, el contenedor no está habilitado para el registro.</span><span class="sxs-lookup"><span data-stu-id="81d01-117">If cleared, the container is not enabled for logging.</span></span> <span data-ttu-id="81d01-118">Seleccione esta opción para habilitar el registro.</span><span class="sxs-lookup"><span data-stu-id="81d01-118">Select to enable logging.</span></span>  
  
-   <span data-ttu-id="81d01-119">Si esta casilla aparece atenuada, el contenedor utiliza las opciones de registro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="81d01-119">If dimmed, the container uses the logging options of its parent.</span></span> <span data-ttu-id="81d01-120">Esta opción no está disponible para el paquete.</span><span class="sxs-lookup"><span data-stu-id="81d01-120">This option is not available for the package.</span></span>  
  
-   <span data-ttu-id="81d01-121">Si se activa, el contenedor define sus propias opciones de registro.</span><span class="sxs-lookup"><span data-stu-id="81d01-121">If checked, the container defines its own logging options.</span></span>  
  
 <span data-ttu-id="81d01-122">Si un contenedor aparece atenuado y desea establecer opciones de registro en el contenedor, haga clic dos veces en la casilla.</span><span class="sxs-lookup"><span data-stu-id="81d01-122">If a container is dimmed and you want to set logging options on the container, click its check box twice.</span></span> <span data-ttu-id="81d01-123">El primer clic desactiva la casilla y el segundo la activa para permitirle que elija los proveedores de registro que desea utilizar y para seleccionar la información que desea registrar.</span><span class="sxs-lookup"><span data-stu-id="81d01-123">The first click clears the check box, and the second click selects it, enabling you to choose the log providers to use and select the information to log.</span></span>  
  
##  <a name="configure-the-options-on-the-providers-and-logs-tab"></a><a name="provider"></a> <span data-ttu-id="81d01-124">Configurar las opciones en la pestaña Proveedores y registros</span><span class="sxs-lookup"><span data-stu-id="81d01-124">Configure the Options on the Providers and Logs Tab</span></span>  
 <span data-ttu-id="81d01-125">Use la pestaña **Proveedores y registros** del cuadro de diálogo **Configurar registros de SSIS** con el fin de crear y configurar registros para la captura de eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="81d01-125">Use the **Providers and Logs** tab of the **Configure SSIS Logs** dialog box to create and configure logs for capturing run-time events.</span></span>  
  
### <a name="options"></a><span data-ttu-id="81d01-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="81d01-126">Options</span></span>  
 <span data-ttu-id="81d01-127">**Tipo de proveedor**</span><span class="sxs-lookup"><span data-stu-id="81d01-127">**Provider type**</span></span>  
 <span data-ttu-id="81d01-128">Seleccione un tipo de proveedor de registro de la lista.</span><span class="sxs-lookup"><span data-stu-id="81d01-128">Select a type of log provider from the list.</span></span>  
  
 <span data-ttu-id="81d01-129">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="81d01-129">**Add**</span></span>  
 <span data-ttu-id="81d01-130">Agregue un registro del tipo especificado a la colección de proveedores de registro del paquete.</span><span class="sxs-lookup"><span data-stu-id="81d01-130">Add a log of the specified type to the collection of log providers of the package.</span></span>  
  
 <span data-ttu-id="81d01-131">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="81d01-131">**Name**</span></span>  
 <span data-ttu-id="81d01-132">Use las casillas para habilitar o deshabilitar registros para contenedores o tareas que se han seleccionado en el panel **Contenedores** del cuadro de diálogo **Configurar registros de SSIS** .</span><span class="sxs-lookup"><span data-stu-id="81d01-132">Enable or disable logs for containers or tasks selected in the **Containers** pane of the **Configure SSIS Logs** dialog box, by using the check boxes.</span></span> <span data-ttu-id="81d01-133">El campo del nombre se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="81d01-133">The name field is editable.</span></span> <span data-ttu-id="81d01-134">Utilice el nombre predeterminado para el proveedor o escriba un nombre descriptivo único.</span><span class="sxs-lookup"><span data-stu-id="81d01-134">Use the default name for the provider, or type a unique descriptive name.</span></span>  
  
 <span data-ttu-id="81d01-135">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="81d01-135">**Description**</span></span>  
 <span data-ttu-id="81d01-136">El campo de la descripción se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="81d01-136">The description field is editable.</span></span> <span data-ttu-id="81d01-137">Haga clic en la descripción predeterminada del registro y, a continuación, modifíquela.</span><span class="sxs-lookup"><span data-stu-id="81d01-137">Click and then modify the default description of the log.</span></span>  
  
 <span data-ttu-id="81d01-138">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="81d01-138">**Configuration**</span></span>  
 <span data-ttu-id="81d01-139">Seleccione un administrador de conexiones existente de la lista o haga clic en \<**New connection...**> para crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="81d01-139">Select an existing connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span> <span data-ttu-id="81d01-140">En función del tipo de proveedor de registro, puede configurar un administrador de conexiones OLE DB o un administrador de conexiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="81d01-140">Depending on the type of log provider, you can configure an OLE DB connection manager or a File connection manager.</span></span> <span data-ttu-id="81d01-141">El proveedor de registro para Registro de eventos de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows no requiere conexión.</span><span class="sxs-lookup"><span data-stu-id="81d01-141">The log provider for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Event Log requires no connection.</span></span>  
  
 <span data-ttu-id="81d01-142">Temas relacionados: [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md) , [File Connection Manager](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="81d01-142">Related Topics: [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md) manager, [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
 <span data-ttu-id="81d01-143">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="81d01-143">**Delete**</span></span>  
 <span data-ttu-id="81d01-144">Seleccione un proveedor de registro y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="81d01-144">Select a log provider and then click **Delete**.</span></span>  
  
##  <a name="configure-the-options-on-the-details-tab"></a><a name="detail"></a> <span data-ttu-id="81d01-145">Configurar las opciones en la pestaña Detalles</span><span class="sxs-lookup"><span data-stu-id="81d01-145">Configure the Options on the Details Tab</span></span>  
 <span data-ttu-id="81d01-146">Utilice la pestaña **Detalles** del cuadro de diálogo **Configurar registros de SSIS** para especificar los eventos que se van a habilitar para el registro y los detalles de información que se van a registrar.</span><span class="sxs-lookup"><span data-stu-id="81d01-146">Use the **Details** tab of the **Configure SSIS Logs** dialog box to specify the events to enable for logging and the information details to log.</span></span> <span data-ttu-id="81d01-147">La información que selecciona se aplica a todos los proveedores de registro del paquete.</span><span class="sxs-lookup"><span data-stu-id="81d01-147">The information that you select applies to all the log providers in the package.</span></span> <span data-ttu-id="81d01-148">Por ejemplo, no puede escribir cierta información en la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e información diferente en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="81d01-148">For example, you cannot write some information to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and different information to a text file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="81d01-149">Opciones</span><span class="sxs-lookup"><span data-stu-id="81d01-149">Options</span></span>  
 <span data-ttu-id="81d01-150">**Eventos**</span><span class="sxs-lookup"><span data-stu-id="81d01-150">**Events**</span></span>  
 <span data-ttu-id="81d01-151">Habilite o deshabilite eventos para el registro.</span><span class="sxs-lookup"><span data-stu-id="81d01-151">Enable or disable events for logging.</span></span>  
  
 <span data-ttu-id="81d01-152">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="81d01-152">**Description**</span></span>  
 <span data-ttu-id="81d01-153">Vea una descripción del evento.</span><span class="sxs-lookup"><span data-stu-id="81d01-153">View a description of the event.</span></span>  
  
 <span data-ttu-id="81d01-154">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="81d01-154">**Advanced**</span></span>  
 <span data-ttu-id="81d01-155">Seleccione o borre eventos para el registro, y seleccione o borre información que se va a registrar para cada evento.</span><span class="sxs-lookup"><span data-stu-id="81d01-155">Select or clear events to log, and select or clear information to log for each event.</span></span> <span data-ttu-id="81d01-156">Haga clic en **Básicas** para ocultar todos los detalles de registro a excepción de la lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="81d01-156">Click **Basic** to hide all logging details, except the list of events.</span></span> <span data-ttu-id="81d01-157">La información siguiente está disponible para el registro:</span><span class="sxs-lookup"><span data-stu-id="81d01-157">The following information is available for logging:</span></span>  
  
|<span data-ttu-id="81d01-158">Value</span><span class="sxs-lookup"><span data-stu-id="81d01-158">Value</span></span>|<span data-ttu-id="81d01-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="81d01-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="81d01-160">**Equipo**</span><span class="sxs-lookup"><span data-stu-id="81d01-160">**Computer**</span></span>|<span data-ttu-id="81d01-161">Nombre del equipo en el que ha tenido lugar el evento registrado.</span><span class="sxs-lookup"><span data-stu-id="81d01-161">The name of the computer on which the logged event occurred.</span></span>|  
|<span data-ttu-id="81d01-162">**Operador**</span><span class="sxs-lookup"><span data-stu-id="81d01-162">**Operator**</span></span>|<span data-ttu-id="81d01-163">El nombre de usuario de la persona que ha iniciado el paquete.</span><span class="sxs-lookup"><span data-stu-id="81d01-163">The user name of the person who started the package.</span></span>|  
|<span data-ttu-id="81d01-164">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="81d01-164">**SourceName**</span></span>|<span data-ttu-id="81d01-165">El nombre del paquete, contenedor o tarea en la que ha tenido lugar el evento registrado.</span><span class="sxs-lookup"><span data-stu-id="81d01-165">The name of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="81d01-166">**SourceID**</span><span class="sxs-lookup"><span data-stu-id="81d01-166">**SourceID**</span></span>|<span data-ttu-id="81d01-167">El nombre del identificador único global (GUID) del paquete, la tarea o el contenedor en el que ha tenido lugar el evento registrado.</span><span class="sxs-lookup"><span data-stu-id="81d01-167">The global unique identifier (GUID) of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="81d01-168">**ExecutionID**</span><span class="sxs-lookup"><span data-stu-id="81d01-168">**ExecutionID**</span></span>|<span data-ttu-id="81d01-169">El identificador único global de la instancia de ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="81d01-169">The global unique identifier of the package execution instance.</span></span>|  
|<span data-ttu-id="81d01-170">**MessageText**</span><span class="sxs-lookup"><span data-stu-id="81d01-170">**MessageText**</span></span>|<span data-ttu-id="81d01-171">Mensaje asociado a la entrada del registro.</span><span class="sxs-lookup"><span data-stu-id="81d01-171">A message associated with the log entry.</span></span>|  
|<span data-ttu-id="81d01-172">**DataBytes**</span><span class="sxs-lookup"><span data-stu-id="81d01-172">**DataBytes**</span></span>|<span data-ttu-id="81d01-173">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="81d01-173">Reserved for future use.</span></span>|  
  
 <span data-ttu-id="81d01-174">**Basic**</span><span class="sxs-lookup"><span data-stu-id="81d01-174">**Basic**</span></span>  
 <span data-ttu-id="81d01-175">Seleccione o borre los eventos de registro.</span><span class="sxs-lookup"><span data-stu-id="81d01-175">Select or clear events to log.</span></span> <span data-ttu-id="81d01-176">Esta opción oculta los detalles de registro a excepción de la lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="81d01-176">This option hides logging details except the list of events.</span></span> <span data-ttu-id="81d01-177">Si selecciona un evento, se seleccionan todos los detalles de registro para el evento de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="81d01-177">If you select an event, all logging details are selected for the event by default.</span></span> <span data-ttu-id="81d01-178">Haga clic en **Avanzadas** para mostrar los detalles de registro.</span><span class="sxs-lookup"><span data-stu-id="81d01-178">Click **Advanced** to show all logging details.</span></span>  
  
 <span data-ttu-id="81d01-179">**Cargar**</span><span class="sxs-lookup"><span data-stu-id="81d01-179">**Load**</span></span>  
 <span data-ttu-id="81d01-180">Especifique un archivo XML existente para utilizarlo como una plantilla para establecer las opciones de registro.</span><span class="sxs-lookup"><span data-stu-id="81d01-180">Specify an existing XML file to use as a template for setting logging options.</span></span>  
  
 <span data-ttu-id="81d01-181">**Guardar**</span><span class="sxs-lookup"><span data-stu-id="81d01-181">**Save**</span></span>  
 <span data-ttu-id="81d01-182">Guarde los detalles de configuración como una plantilla para un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="81d01-182">Save configuration details as a template to an XML file.</span></span>  
  
  
