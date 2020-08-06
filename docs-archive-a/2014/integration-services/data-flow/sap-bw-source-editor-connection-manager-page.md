---
title: Editor de origen de SAP BW (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2a6dc531-85ca-43c5-a65f-3ad3f7d537c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c6b1782daf8c00b3b3d3a7d13b5ffa00adeeba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744227"
---
# <a name="sap-bw-source-editor-connection-manager-page"></a><span data-ttu-id="ec433-102">Editor de origen de SAP BW (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="ec433-102">SAP BW Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="ec433-103">Use la página **Administrador de conexiones** del cuadro de diálogo **Editor de origen de SAP BW** para seleccionar el administrador de conexiones de SAP BW para el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ec433-103">Use the **Connection Manager** page of the **SAP BW Source Editor** to select the SAP BW connection manager for the SAP BW source.</span></span> <span data-ttu-id="ec433-104">En esta página, puede seleccionar el modo de ejecución y los parámetros para extraer los datos del sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ec433-104">On this page, you also select the execution mode and the parameters for extracting the data from the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="ec433-105">Para obtener más información sobre el componente de origen de SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Origen de SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="ec433-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ec433-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ec433-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="ec433-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="ec433-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ec433-108">La extracción de datos de SAP Netweaver BW requiere una licencia SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="ec433-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="ec433-109">Póngase en contacto con SAP para comprobar estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="ec433-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="ec433-110">**Para abrir la página Administrador de conexiones**</span><span class="sxs-lookup"><span data-stu-id="ec433-110">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="ec433-111">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ec433-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="ec433-112">En la pestaña **Flujo de datos** , haga doble clic en el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ec433-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="ec433-113">En **Editor de origen de SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="ec433-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="ec433-114">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="ec433-114">Static Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec433-115">Si no conoce todos los valores necesarios para configurar el origen, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="ec433-115">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="ec433-116">**Administrador de conexiones de SAP BW**</span><span class="sxs-lookup"><span data-stu-id="ec433-116">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="ec433-117">Seleccione un administrador de conexiones de la lista o cree una conexión haciendo clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ec433-117">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="ec433-118">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="ec433-118">**New**</span></span>  
 <span data-ttu-id="ec433-119">Cree un administrador de conexiones con el cuadro de diálogo **Administrador de conexiones de SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="ec433-119">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="ec433-120">Para obtener más información sobre este cuadro de diálogo, vea [SAP BW Connection Manager Editor](../sap-bw-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="ec433-120">For more information about this dialog box, see [SAP BW Connection Manager Editor](../sap-bw-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="ec433-121">**Destino OHS**</span><span class="sxs-lookup"><span data-stu-id="ec433-121">**OHS destination**</span></span>  
 <span data-ttu-id="ec433-122">Permite seleccionar el destino del servicio de concentrador abierto (OHS) que se usará para extraer los datos del origen.</span><span class="sxs-lookup"><span data-stu-id="ec433-122">Select the Open Hub Service (OHS) destination to use to extract data from the source.</span></span>  
  
 <span data-ttu-id="ec433-123">**Modo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="ec433-123">**Execution mode**</span></span>  
 <span data-ttu-id="ec433-124">Permite especificar el método para la extracción de datos desde el origen.</span><span class="sxs-lookup"><span data-stu-id="ec433-124">Specify the method for extracting data from the source.</span></span>  
  
|<span data-ttu-id="ec433-125">Opción</span><span class="sxs-lookup"><span data-stu-id="ec433-125">Option</span></span>|<span data-ttu-id="ec433-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec433-126">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ec433-127">**P -Desencadenar cadena de procesos**</span><span class="sxs-lookup"><span data-stu-id="ec433-127">**P - Trigger Process Chain**</span></span>|<span data-ttu-id="ec433-128">Desencadene una cadena de procesos.</span><span class="sxs-lookup"><span data-stu-id="ec433-128">Trigger a process chain.</span></span> <span data-ttu-id="ec433-129">En este caso, el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inicia el proceso de extracción.</span><span class="sxs-lookup"><span data-stu-id="ec433-129">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>|  
|<span data-ttu-id="ec433-130">**W - Esperar notificación**</span><span class="sxs-lookup"><span data-stu-id="ec433-130">**W - Wait for Notify**</span></span>|<span data-ttu-id="ec433-131">Permite esperar para recibir la notificación del sistema SAP Netweaver BW para comenzar a extraer datos.</span><span class="sxs-lookup"><span data-stu-id="ec433-131">Wait for notification from the SAP Netweaver BW system to begin extracting the data.</span></span> <span data-ttu-id="ec433-132">En este caso, el sistema SAP Netweaver BW inicia el proceso de extracción.</span><span class="sxs-lookup"><span data-stu-id="ec433-132">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>|  
|<span data-ttu-id="ec433-133">**E - Extraer únicamente**</span><span class="sxs-lookup"><span data-stu-id="ec433-133">**E - Extract Only**</span></span>|<span data-ttu-id="ec433-134">Recupere los datos asociados a un identificador de solicitud determinado.</span><span class="sxs-lookup"><span data-stu-id="ec433-134">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="ec433-135">En este caso, el sistema SAP Netweaver BW ha extraído ya los datos a una tabla interna y el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solo lee los datos.</span><span class="sxs-lookup"><span data-stu-id="ec433-135">In this case, the SAP Netweaver BW system has already extracted the data into an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>|  
  
 <span data-ttu-id="ec433-136">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="ec433-136">**Preview**</span></span>  
 <span data-ttu-id="ec433-137">Permite abrir el cuadro de diálogo **Vista previa** , donde podrá obtener una vista previa de los resultados.</span><span class="sxs-lookup"><span data-stu-id="ec433-137">Open the **Preview** dialog box in which you can preview results.</span></span> <span data-ttu-id="ec433-138">Para más información, consulte [Preview](preview.md).</span><span class="sxs-lookup"><span data-stu-id="ec433-138">For more information, see [Preview](preview.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ec433-139">La opción de **Vista previa** , que está disponible en la página de **Administrador de conexiones** del editor de origen de SAP BW, extrae los datos.</span><span class="sxs-lookup"><span data-stu-id="ec433-139">The **Preview** option, that is available on the **Connection Manager** page of the SAP BW Source Editor, actually extracts data.</span></span> <span data-ttu-id="ec433-140">Si ha configurado SAP Netweaver BW para extraer solamente los datos que han cambiado desde la extracción anterior, si selecciona **Vista previa** , excluirá datos de la vista previa de la extracción siguiente.</span><span class="sxs-lookup"><span data-stu-id="ec433-140">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="ec433-141">Al hacer clic en **Vista previa**, también se abre el cuadro de diálogo **Registro de solicitudes** .</span><span class="sxs-lookup"><span data-stu-id="ec433-141">When you click **Preview**, you also open the **Request Log** dialog box.</span></span> <span data-ttu-id="ec433-142">Puede usar este cuadro de diálogo para ver los eventos que se registran durante la solicitud que se efectúa al sistema SAP Netweaver BW sobre datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ec433-142">You can use this dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="ec433-143">Para más información, consulte [Request Log](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="ec433-143">For more information, see [Request Log](request-log.md).</span></span>  
  
## <a name="execution-mode-dynamic-options"></a><span data-ttu-id="ec433-144">Opciones dinámicas del modo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ec433-144">Execution Mode Dynamic Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec433-145">Si no conoce todos los valores necesarios para configurar el origen, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="ec433-145">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
### <a name="execution-mode--p---trigger-process-chain"></a><span data-ttu-id="ec433-146">Modo de ejecución = P - Desencadenar cadena de procesos</span><span class="sxs-lookup"><span data-stu-id="ec433-146">Execution Mode = P - Trigger Process Chain</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="ec433-147">Opciones de destino RFC</span><span class="sxs-lookup"><span data-stu-id="ec433-147">RFC Destination Options</span></span>  
 <span data-ttu-id="ec433-148">No es necesario que conozca y especifique estos valores previamente.</span><span class="sxs-lookup"><span data-stu-id="ec433-148">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="ec433-149">Utilice el botón de **Buscar** para buscar y seleccionar el destino RFC adecuado.</span><span class="sxs-lookup"><span data-stu-id="ec433-149">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="ec433-150">Después de seleccionar un destino RFC, el componente especifica los valores adecuados para estas opciones.</span><span class="sxs-lookup"><span data-stu-id="ec433-150">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="ec433-151">**Host de puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="ec433-151">**Gateway host**</span></span>  
 <span data-ttu-id="ec433-152">Permite escribir el nombre del servidor o la dirección IP del host de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="ec433-152">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="ec433-153">Normalmente, el nombre o la dirección IP es el mismo que el del servidor de aplicaciones SAP.</span><span class="sxs-lookup"><span data-stu-id="ec433-153">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="ec433-154">**Servicio de puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="ec433-154">**Gateway service**</span></span>  
 <span data-ttu-id="ec433-155">Escriba el nombre del servicio de puerta de enlace, con el formato `sapgwNN`, donde `NN` es el número del sistema.</span><span class="sxs-lookup"><span data-stu-id="ec433-155">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="ec433-156">**Id. de programa**</span><span class="sxs-lookup"><span data-stu-id="ec433-156">**Program ID**</span></span>  
 <span data-ttu-id="ec433-157">Permite escribir el identificador de programa asociado al destino RFC.</span><span class="sxs-lookup"><span data-stu-id="ec433-157">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="ec433-158">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="ec433-158">**Look up**</span></span>  
 <span data-ttu-id="ec433-159">Permite buscar el destino RFC con el cuadro de diálogo **Buscar destino RFC** .</span><span class="sxs-lookup"><span data-stu-id="ec433-159">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="ec433-160">Para obtener más información sobre este cuadro de diálogo, vea [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ec433-160">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
#### <a name="process-chain-options"></a><span data-ttu-id="ec433-161">Opciones de la cadena de procesos</span><span class="sxs-lookup"><span data-stu-id="ec433-161">Process Chain Options</span></span>  
 <span data-ttu-id="ec433-162">No es necesario que conozca y especifique estos valores previamente.</span><span class="sxs-lookup"><span data-stu-id="ec433-162">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="ec433-163">Use el botón de **Buscar** para buscar y seleccionar la cadena de procesos adecuada.</span><span class="sxs-lookup"><span data-stu-id="ec433-163">Use the **Look up** button to find and select the appropriate process chain.</span></span> <span data-ttu-id="ec433-164">Después de seleccionar una cadena de procesos, el componente especifica los valores adecuados para la opción.</span><span class="sxs-lookup"><span data-stu-id="ec433-164">After you select a process chain, the component enters the appropriate value for the option.</span></span>  
  
 <span data-ttu-id="ec433-165">**Cadena de procesos**</span><span class="sxs-lookup"><span data-stu-id="ec433-165">**Process chain**</span></span>  
 <span data-ttu-id="ec433-166">Permite escribir el nombre de la cadena de procesos que va a desencadenar el origen.</span><span class="sxs-lookup"><span data-stu-id="ec433-166">Enter the name of the process chain to be triggered by the source.</span></span>  
  
 <span data-ttu-id="ec433-167">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="ec433-167">**Look up**</span></span>  
 <span data-ttu-id="ec433-168">Permite buscar la cadena de procesos con el cuadro de diálogo **Buscar cadena de procesos** .</span><span class="sxs-lookup"><span data-stu-id="ec433-168">Look up the process chain by using the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="ec433-169">Para obtener más información sobre este cuadro de diálogo, vea [Look Up Process Chain](look-up-process-chain.md).</span><span class="sxs-lookup"><span data-stu-id="ec433-169">For more information about this dialog box, see [Look Up Process Chain](look-up-process-chain.md).</span></span>  
  
### <a name="execution-mode--w---wait-for-notify"></a><span data-ttu-id="ec433-170">Modo de ejecución = W - Esperar notificación</span><span class="sxs-lookup"><span data-stu-id="ec433-170">Execution Mode = W - Wait for Notify</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="ec433-171">Opciones de destino RFC</span><span class="sxs-lookup"><span data-stu-id="ec433-171">RFC Destination Options</span></span>  
 <span data-ttu-id="ec433-172">No es necesario que conozca y especifique estos valores previamente.</span><span class="sxs-lookup"><span data-stu-id="ec433-172">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="ec433-173">Utilice el botón de **Buscar** para buscar y seleccionar el destino RFC adecuado.</span><span class="sxs-lookup"><span data-stu-id="ec433-173">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="ec433-174">Después de seleccionar un destino RFC, el componente especifica los valores adecuados para las opciones.</span><span class="sxs-lookup"><span data-stu-id="ec433-174">After you select an RFC destination, the component enters the appropriate values for the options.</span></span>  
  
 <span data-ttu-id="ec433-175">**Host de puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="ec433-175">**Gateway host**</span></span>  
 <span data-ttu-id="ec433-176">Permite escribir el nombre del servidor o la dirección IP del host de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="ec433-176">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="ec433-177">Normalmente, el nombre o la dirección IP es el mismo que el del servidor de aplicaciones SAP.</span><span class="sxs-lookup"><span data-stu-id="ec433-177">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="ec433-178">**Servicio de puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="ec433-178">**Gateway service**</span></span>  
 <span data-ttu-id="ec433-179">Escriba el nombre del servicio de puerta de enlace, con el formato `sapgwNN`, donde `NN` es el número del sistema.</span><span class="sxs-lookup"><span data-stu-id="ec433-179">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="ec433-180">**Id. de programa**</span><span class="sxs-lookup"><span data-stu-id="ec433-180">**Program ID**</span></span>  
 <span data-ttu-id="ec433-181">Permite escribir el identificador de programa asociado al destino RFC.</span><span class="sxs-lookup"><span data-stu-id="ec433-181">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="ec433-182">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="ec433-182">**Look up**</span></span>  
 <span data-ttu-id="ec433-183">Permite buscar el destino RFC con el cuadro de diálogo **Buscar destino RFC** .</span><span class="sxs-lookup"><span data-stu-id="ec433-183">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="ec433-184">Para obtener más información sobre este cuadro de diálogo, vea [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ec433-184">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="execution-mode--e---extract-only"></a><span data-ttu-id="ec433-185">Modo de ejecución = E - Extraer únicamente</span><span class="sxs-lookup"><span data-stu-id="ec433-185">Execution Mode = E - Extract Only</span></span>  
 <span data-ttu-id="ec433-186">**Id. de solicitud**</span><span class="sxs-lookup"><span data-stu-id="ec433-186">**Request ID**</span></span>  
 <span data-ttu-id="ec433-187">Permite escribir el identificador de solicitud asociado a la extracción.</span><span class="sxs-lookup"><span data-stu-id="ec433-187">Enter the Request ID that is associated with the extraction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec433-188">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec433-188">See Also</span></span>  
 <span data-ttu-id="ec433-189">[Editor de origen de SAP BW &#40;página Columnas&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="ec433-189">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="ec433-190">[Editor de origen de SAP BW &#40;página Salida de error&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="ec433-190">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="ec433-191">[Editor de origen de SAP BW &#40;página Opciones avanzadas&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="ec433-191">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="ec433-192">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="ec433-192">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
