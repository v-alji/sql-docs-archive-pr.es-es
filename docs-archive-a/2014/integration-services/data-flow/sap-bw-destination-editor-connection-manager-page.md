---
title: Editor de destino de SAP BW (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 04ae38f8-5287-45a3-826a-8aac5dd15a91
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd628f1a0fec09490e0d3720610d1232882ed92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744233"
---
# <a name="sap-bw-destination-editor-connection-manager-page"></a><span data-ttu-id="a9b8e-102">Editor de destino de SAP BW (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="a9b8e-102">SAP BW Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="a9b8e-103">Use la página **Administrador de conexiones** del cuadro de diálogo **Editor de destino de SAP BW** para seleccionar un administrador de conexiones de SAP BW que va a usar el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-103">Use the **Connection Manager** page of the **SAP BW Destination Editor** to select the SAP BW connection manager that the SAP BW destination will use.</span></span> <span data-ttu-id="a9b8e-104">En esta página, puede seleccionar los parámetros para cargar los datos en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-104">On this page, you also select the parameters for loading the data into the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="a9b8e-105">Para obtener más información sobre el destino SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Destino de SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a9b8e-105">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a9b8e-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a9b8e-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="a9b8e-108">**Para abrir la página Administrador de conexiones**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-108">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="a9b8e-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="a9b8e-110">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="a9b8e-111">En **Editor de destino SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a9b8e-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="a9b8e-112">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9b8e-113">Si no conoce todos los valores necesarios para configurar el destino, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-113">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="a9b8e-114">**Administrador de conexiones de SAP BW**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-114">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="a9b8e-115">Seleccione un administrador de conexiones de la lista o cree una conexión haciendo clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-115">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="a9b8e-116">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-116">**New**</span></span>  
 <span data-ttu-id="a9b8e-117">Cree un administrador de conexiones con el cuadro de diálogo **Administrador de conexiones de SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="a9b8e-117">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="a9b8e-118">**Probar carga**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-118">**Test Load**</span></span>  
 <span data-ttu-id="a9b8e-119">Realice una prueba del proceso de carga que use los valores que haya seleccionado y cargue cero filas.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-119">Perform a test of the loading process that uses the settings that you have selected and loads zero rows.</span></span>  
  
### <a name="infopackageinfosource-options"></a><span data-ttu-id="a9b8e-120">Opciones InfoPackage/InfoSource</span><span class="sxs-lookup"><span data-stu-id="a9b8e-120">InfoPackage/InfoSource Options</span></span>  
 <span data-ttu-id="a9b8e-121">No es necesario que conozca y especifique estos valores previamente.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-121">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="a9b8e-122">Utilice el botón de **Buscar** para buscar y seleccionar el InfoPackage adecuado.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-122">Use the **Look up** button to find and select the appropriate InfoPackage.</span></span> <span data-ttu-id="a9b8e-123">Después de seleccionar un InfoPackage, el componente especifica los valores adecuados para estas opciones.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-123">After you select an InfoPackage, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="a9b8e-124">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-124">**InfoPackage**</span></span>  
 <span data-ttu-id="a9b8e-125">Escriba el nombre del InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-125">Enter the name of the InfoPackage.</span></span>  
  
 <span data-ttu-id="a9b8e-126">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-126">**InfoSource**</span></span>  
 <span data-ttu-id="a9b8e-127">Escriba el nombre del InfoSource.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-127">Enter the name of the InfoSource.</span></span>  
  
 <span data-ttu-id="a9b8e-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-128">**Type**</span></span>  
 <span data-ttu-id="a9b8e-129">Escriba el carácter único que identifique el tipo del InfoSource.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-129">Enter the single-character that identifies the type of the InfoSource.</span></span> <span data-ttu-id="a9b8e-130">La tabla siguiente enumera los valores aceptables de un solo carácter.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-130">The following table lists the acceptable single-character values.</span></span>  
  
|<span data-ttu-id="a9b8e-131">Value</span><span class="sxs-lookup"><span data-stu-id="a9b8e-131">Value</span></span>|<span data-ttu-id="a9b8e-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9b8e-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a9b8e-133">**D**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-133">**D**</span></span>|<span data-ttu-id="a9b8e-134">Datos de transacción</span><span class="sxs-lookup"><span data-stu-id="a9b8e-134">Transaction data</span></span>|  
|<span data-ttu-id="a9b8e-135">**M**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-135">**M**</span></span>|<span data-ttu-id="a9b8e-136">Datos maestros</span><span class="sxs-lookup"><span data-stu-id="a9b8e-136">Master data</span></span>|  
|<span data-ttu-id="a9b8e-137">**T**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-137">**T**</span></span>|<span data-ttu-id="a9b8e-138">Textos</span><span class="sxs-lookup"><span data-stu-id="a9b8e-138">Texts</span></span>|  
|<span data-ttu-id="a9b8e-139">**H**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-139">**H**</span></span>|<span data-ttu-id="a9b8e-140">Datos de jerarquía</span><span class="sxs-lookup"><span data-stu-id="a9b8e-140">Hierarchy data</span></span>|  
  
 <span data-ttu-id="a9b8e-141">**Sistema lógico**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-141">**Logical system**</span></span>  
 <span data-ttu-id="a9b8e-142">Escriba el nombre del sistema lógico que esté asociado con el InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-142">Enter the name of the logical system that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="a9b8e-143">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-143">**Look up**</span></span>  
 <span data-ttu-id="a9b8e-144">Busque el InfoPackage con el cuadro de diálogo **Buscar InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="a9b8e-144">Look up the InfoPackage by using the **Look Up InfoPackage** dialog box.</span></span> <span data-ttu-id="a9b8e-145">Para obtener más información sobre este cuadro de diálogo, vea [Look Up InfoPackage](look-up-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="a9b8e-145">For more information about this dialog box, see [Look Up InfoPackage](look-up-infopackage.md).</span></span>  
  
### <a name="rfc-destination-options"></a><span data-ttu-id="a9b8e-146">Opciones de destino RFC</span><span class="sxs-lookup"><span data-stu-id="a9b8e-146">RFC Destination Options</span></span>  
 <span data-ttu-id="a9b8e-147">No es necesario que conozca y especifique estos valores previamente.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-147">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="a9b8e-148">Utilice el botón de **Buscar** para buscar y seleccionar el destino RFC adecuado.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-148">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="a9b8e-149">Después de seleccionar un destino RFC, el componente especifica los valores adecuados para estas opciones.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-149">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="a9b8e-150">**Host de puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-150">**Gateway host**</span></span>  
 <span data-ttu-id="a9b8e-151">Permite escribir el nombre del servidor o la dirección IP del host de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-151">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="a9b8e-152">Normalmente, el nombre o la dirección IP es el mismo que el del servidor de aplicaciones SAP.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-152">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="a9b8e-153">**Servicio de puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-153">**Gateway service**</span></span>  
 <span data-ttu-id="a9b8e-154">Escriba el nombre del servicio de puerta de enlace, con el formato `sapgwNN`, donde `NN` es el número del sistema.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-154">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="a9b8e-155">**Id. de programa**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-155">**Program ID**</span></span>  
 <span data-ttu-id="a9b8e-156">Permite escribir el identificador de programa asociado al destino RFC.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-156">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="a9b8e-157">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-157">**Look up**</span></span>  
 <span data-ttu-id="a9b8e-158">Permite buscar el destino RFC con el cuadro de diálogo **Buscar destino RFC** .</span><span class="sxs-lookup"><span data-stu-id="a9b8e-158">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="a9b8e-159">Para obtener más información sobre este cuadro de diálogo, vea [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a9b8e-159">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="create-sap-bw-objects-options"></a><span data-ttu-id="a9b8e-160">Crear opciones de objetos de SAP BW</span><span class="sxs-lookup"><span data-stu-id="a9b8e-160">Create SAP BW Objects Options</span></span>  
 <span data-ttu-id="a9b8e-161">**Seleccionar tipo de objeto**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-161">**Select object type**</span></span>  
 <span data-ttu-id="a9b8e-162">Seleccione el tipo de objeto SAP Netweaver BW que desea crear.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-162">Select the type of SAP Netweaver BW object that you want to create.</span></span> <span data-ttu-id="a9b8e-163">Puede seleccionar uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="a9b8e-163">You can select one of the following types:</span></span>  
  
-   <span data-ttu-id="a9b8e-164">InfoObject</span><span class="sxs-lookup"><span data-stu-id="a9b8e-164">InfoObject</span></span>  
  
-   <span data-ttu-id="a9b8e-165">InfoCube</span><span class="sxs-lookup"><span data-stu-id="a9b8e-165">InfoCube</span></span>  
  
-   <span data-ttu-id="a9b8e-166">InfoSource</span><span class="sxs-lookup"><span data-stu-id="a9b8e-166">InfoSource</span></span>  
  
-   <span data-ttu-id="a9b8e-167">InfoPackage</span><span class="sxs-lookup"><span data-stu-id="a9b8e-167">InfoPackage</span></span>  
  
 <span data-ttu-id="a9b8e-168">**Creación**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-168">**Create**</span></span>  
 <span data-ttu-id="a9b8e-169">Cree el tipo seleccionado de objeto SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a9b8e-169">Create the selected type of SAP Netweaver BW object.</span></span>  
  
|<span data-ttu-id="a9b8e-170">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="a9b8e-170">Object Type</span></span>|<span data-ttu-id="a9b8e-171">Resultado</span><span class="sxs-lookup"><span data-stu-id="a9b8e-171">Result</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="a9b8e-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-172">**InfoObject**</span></span>|<span data-ttu-id="a9b8e-173">Cree un InfoObject nuevo con el cuadro de diálogo **Crear nuevo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a9b8e-173">Create a new InfoObject by using the **Create New InfoObject** dialog box.</span></span> <span data-ttu-id="a9b8e-174">Para obtener más información sobre este cuadro de diálogo, vea [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="a9b8e-174">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>|  
|<span data-ttu-id="a9b8e-175">**InfoCube**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-175">**InfoCube**</span></span>|<span data-ttu-id="a9b8e-176">Cree un InfoCube nuevo con el cuadro de diálogo **Crear InfoCube para los datos de transacción** .</span><span class="sxs-lookup"><span data-stu-id="a9b8e-176">Create a new InfoCube by using the **Create InfoCube for Transaction Data** dialog box.</span></span> <span data-ttu-id="a9b8e-177">Para obtener más información sobre este cuadro de diálogo, vea [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="a9b8e-177">For more information about this dialog box, see [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span></span>|  
|<span data-ttu-id="a9b8e-178">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-178">**InfoSource**</span></span>|<span data-ttu-id="a9b8e-179">Cree un InfoSource nuevo con el cuadro de diálogo **Crear InfoSource** y, a continuación, use **Crear InfoSource para datos de transacción** o el cuadro de diálogo **Crear InfoSource para datos maestros** .</span><span class="sxs-lookup"><span data-stu-id="a9b8e-179">Create a new InfoSource by using the **Create InfoSource** dialog box, and then by using the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span> <span data-ttu-id="a9b8e-180">Para obtener más información sobre estos cuadros de diálogo, vea [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) y [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="a9b8e-180">For more information about these dialog boxes, see [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) and [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>|  
|<span data-ttu-id="a9b8e-181">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="a9b8e-181">**InfoPackage**</span></span>|<span data-ttu-id="a9b8e-182">Cree un InfoPackage nuevo con el cuadro de diálogo **Crear InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="a9b8e-182">Create a new InfoPackage by using the **Create InfoPackage** dialog box.</span></span> <span data-ttu-id="a9b8e-183">Para obtener más información sobre este cuadro de diálogo, vea [Create InfoPackage](create-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="a9b8e-183">For more information about this dialog box, see [Create InfoPackage](create-infopackage.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9b8e-184">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9b8e-184">See Also</span></span>  
 <span data-ttu-id="a9b8e-185">[Editor de destino de SAP BW &#40;página Asignaciones&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="a9b8e-185">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="a9b8e-186">[Editor de destino de SAP BW &#40;página Salida de error&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="a9b8e-186">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="a9b8e-187">[Editor de destino de SAP BW &#40;página Opciones avanzadas&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="a9b8e-187">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="a9b8e-188">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="a9b8e-188">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
