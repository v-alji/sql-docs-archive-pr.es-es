---
title: Origen de SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 749afb64-3567-4dc9-8431-783d650c25db
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d64af5e0d881e3b7dbbd2cc4e005aa3dbef3c43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676112"
---
# <a name="sap-bw-source"></a><span data-ttu-id="1a45d-102">Origen de SAP BW</span><span class="sxs-lookup"><span data-stu-id="1a45d-102">SAP BW Source</span></span>
  <span data-ttu-id="1a45d-103">El origen de SAP BW es el componente de origen de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1a45d-103">The SAP BW source is the source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="1a45d-104">Así, el origen de SAP BW extrae datos de un sistema SAP Netweaver BW de la versión 7 y hace que estos datos estén disponibles para el flujo de datos en un paquete de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a45d-104">Thus, the SAP BW source extracts data from an SAP Netweaver BW version 7 system and makes this data available to the data flow in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="1a45d-105">Este origen tiene una salida y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="1a45d-105">This source has one output and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1a45d-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1a45d-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="1a45d-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="1a45d-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1a45d-108">La extracción de datos de SAP Netweaver BW requiere una licencia SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="1a45d-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="1a45d-109">Póngase en contacto con SAP para comprobar estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="1a45d-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="1a45d-110">Para usar un origen de SAP BW, deberá realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1a45d-110">To use the SAP BW source, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="1a45d-111">Preparar los objetos de SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="1a45d-111">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="1a45d-112">Conectarse al sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="1a45d-112">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="1a45d-113">Configurar el origen de SAP BW</span><span class="sxs-lookup"><span data-stu-id="1a45d-113">Configure the SAP BW source</span></span>](#bkmk_Configure_Source)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-source-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="1a45d-114">Preparar los objetos SAP Netweaver BW que requiera el origen</span><span class="sxs-lookup"><span data-stu-id="1a45d-114">Preparing the SAP Netweaver BW Objects That the Source Requires</span></span>  
 <span data-ttu-id="1a45d-115">El origen de SAP BW requiere que ciertos objetos estén en el sistema SAP Netweaver BW antes de que pueda funcionar el origen.</span><span class="sxs-lookup"><span data-stu-id="1a45d-115">The SAP BW source requires that certain objects are in the SAP Netweaver BW system before the source can function.</span></span> <span data-ttu-id="1a45d-116">Si estos objetos no existen aún, debe seguir estos pasos para crear y configurar estos objetos en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1a45d-116">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a45d-117">Para obtener detalles adicionales sobre estos objetos y pasos de configuración, vea la documentación sobre SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1a45d-117">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="1a45d-118">Inicie sesión en SAP Netweaver BW MDX a través de la GUI de SAP, escriba el código SM59 de transacciones y cree un destino RFC:</span><span class="sxs-lookup"><span data-stu-id="1a45d-118">Log on to SAP Netweaver BW through the SAP GUI, enter transaction code SM59, and create an RFC destination:</span></span>  
  
    1.  <span data-ttu-id="1a45d-119">Para **Tipo de conexión**, seleccione **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="1a45d-119">For **Connection Type**, select **TCP/IP**.</span></span>  
  
    2.  <span data-ttu-id="1a45d-120">Para **Tipo de activación**, seleccione **Programa de servidor registrado**.</span><span class="sxs-lookup"><span data-stu-id="1a45d-120">For **Activation Type**, select **Registered Server Program**.</span></span>  
  
    3.  <span data-ttu-id="1a45d-121">Para **Tipo de comunicación con sistema de destino**, seleccione **No Unicode (valores inactivos de MDMP)** .</span><span class="sxs-lookup"><span data-stu-id="1a45d-121">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    4.  <span data-ttu-id="1a45d-122">Asignar un identificador de programa adecuado</span><span class="sxs-lookup"><span data-stu-id="1a45d-122">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="1a45d-123">Crear un destino de concentrador abierto:</span><span class="sxs-lookup"><span data-stu-id="1a45d-123">Create an Open Hub Destination:</span></span>  
  
    1.  <span data-ttu-id="1a45d-124">Vaya al área de trabajo del administrador (código de transacción RSA1) y, en el panel izquierdo, seleccione **Open Hub Destination**(Destino de concentrador abierto).</span><span class="sxs-lookup"><span data-stu-id="1a45d-124">Go to the Administrator Workbench (transaction code RSA1) and, in the left pane, select **Open Hub Destination**.</span></span>  
  
    2.  <span data-ttu-id="1a45d-125">En el panel central, haga clic con el botón derecho en un elemento InfoArea y, después, seleccione **Create Open Hub Destination**(Crear destino de concentrador abierto).</span><span class="sxs-lookup"><span data-stu-id="1a45d-125">In the middle pane, right-click an InfoArea, and then select **"Create Open Hub Destination"**.</span></span>  
  
    3.  <span data-ttu-id="1a45d-126">Para **Tipo de destino**, seleccione **“Herramienta de terceros”** y, a continuación, especifique el destino RFC que había creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1a45d-126">For **Destination Type**, select **"Third Party Tool"**, and then enter the previously created RFC Destination.</span></span>  
  
    4.  <span data-ttu-id="1a45d-127">Guarde y active el nuevo destino de concentrador abierto.</span><span class="sxs-lookup"><span data-stu-id="1a45d-127">Save and activate the new Open Hub Destination.</span></span>  
  
3.  <span data-ttu-id="1a45d-128">Cree un proceso de transferencia de datos (DTP):</span><span class="sxs-lookup"><span data-stu-id="1a45d-128">Create a Data Transfer Process (DTP):</span></span>  
  
    1.  <span data-ttu-id="1a45d-129">En el panel central del elemento InfoArea, haga clic con el botón derecho en el destino que creó anteriormente y, después, seleccione **Create data transfer process**(Crear proceso de transferencia de datos).</span><span class="sxs-lookup"><span data-stu-id="1a45d-129">In the middle pane of the InfoArea, right-click the previously created destination, and then select **"Create data transfer process"**.</span></span>  
  
    2.  <span data-ttu-id="1a45d-130">Configure, guarde y active el DTP.</span><span class="sxs-lookup"><span data-stu-id="1a45d-130">Configure, save, and activate the DTP.</span></span>  
  
    3.  <span data-ttu-id="1a45d-131">En el menú, haga clic en **Ir a** y, a continuación, haga clic en **Configuración del administrador de lotes**.</span><span class="sxs-lookup"><span data-stu-id="1a45d-131">On the menu, click **Goto**, and then click **Settings for Batch Manager**.</span></span>  
  
    4.  <span data-ttu-id="1a45d-132">Actualice **Número de procesos** a 1 para el procesamiento en serie.</span><span class="sxs-lookup"><span data-stu-id="1a45d-132">Update **Number of processes** to 1 for serial processing.</span></span>  
  
4.  <span data-ttu-id="1a45d-133">Cree una cadena de procesos:</span><span class="sxs-lookup"><span data-stu-id="1a45d-133">Create a process chain:</span></span>  
  
    1.  <span data-ttu-id="1a45d-134">Al configurar la cadena de procesos, seleccione **Comenzar a usar cadena de metadatos o API** como las **Opciones de programación** del **Proceso de inicio**y, a continuación, agregue el DTP que había creado anteriormente como nodo subsiguiente.</span><span class="sxs-lookup"><span data-stu-id="1a45d-134">When configuring the process chain, select the **Start Using Metadata Chain or API** as the **Scheduling Options** of the **Start Process**, and then add the previously created DTP as the subsequent node.</span></span>  
  
    2.  <span data-ttu-id="1a45d-135">Guarde y active la cadena de procesos.</span><span class="sxs-lookup"><span data-stu-id="1a45d-135">Save and activate the process chain.</span></span>  
  
     <span data-ttu-id="1a45d-136">El origen de SAP BW puede llamar a la cadena de procesos para activar el proceso de transferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="1a45d-136">The SAP BW source can call the process chain to activate the data transfer process.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="1a45d-137">Conectarse al sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="1a45d-137">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="1a45d-138">Para conectarse al sistema SAP Netweaver BW de la versión 7, el origen de SAP BW usa un administrador de conexiones para SAP BW que forma parte del paquete [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1a45d-138">To connect to the SAP Netweaver BW version 7 system, the SAP BW source uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="1a45d-139">El administrador de conexiones de SAP BW es el único administrador de conexiones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que puede usar el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1a45d-139">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW source can use.</span></span>  
  
 <span data-ttu-id="1a45d-140">Para obtener más información sobre el administrador de conexiones de SAP BW, vea [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1a45d-140">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-source"></a><a name="bkmk_Configure_Source"></a> <span data-ttu-id="1a45d-141">Configurar el origen de SAP BW</span><span class="sxs-lookup"><span data-stu-id="1a45d-141">Configuring the SAP BW Source</span></span>  
 <span data-ttu-id="1a45d-142">Puede configurar el origen de SAP BW de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="1a45d-142">You can configure the SAP BW source in the following ways:</span></span>  
  
-   <span data-ttu-id="1a45d-143">Busque y seleccione el destino del servicio de concentrador abierto (OHS) que se usará para extraer datos.</span><span class="sxs-lookup"><span data-stu-id="1a45d-143">Look up and select the Open Hub Service (OHS) destination to use to extract data.</span></span>  
  
-   <span data-ttu-id="1a45d-144">Seleccione uno de los métodos siguientes para extraer datos:</span><span class="sxs-lookup"><span data-stu-id="1a45d-144">Select one of the following methods for extracting data:</span></span>  
  
    -   <span data-ttu-id="1a45d-145">Desencadene una cadena de procesos.</span><span class="sxs-lookup"><span data-stu-id="1a45d-145">Trigger a process chain.</span></span> <span data-ttu-id="1a45d-146">En este caso, el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inicia el proceso de extracción.</span><span class="sxs-lookup"><span data-stu-id="1a45d-146">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="1a45d-147">Espere a recibir la notificación del sistema SAP Netweaver BW para comenzar una extracción.</span><span class="sxs-lookup"><span data-stu-id="1a45d-147">Wait for notification from the SAP Netweaver BW system to begin an extraction.</span></span> <span data-ttu-id="1a45d-148">En este caso, el sistema SAP Netweaver BW inicia el proceso de extracción.</span><span class="sxs-lookup"><span data-stu-id="1a45d-148">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="1a45d-149">Recupere los datos asociados a un identificador de solicitud determinado.</span><span class="sxs-lookup"><span data-stu-id="1a45d-149">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="1a45d-150">En este caso, el sistema SAP Netweaver BW ha extraído ya los datos a una tabla interna y el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solo lee los datos.</span><span class="sxs-lookup"><span data-stu-id="1a45d-150">In this case, the SAP Netweaver BW system has already extracted the data to an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>  
  
-   <span data-ttu-id="1a45d-151">En función del método seleccionado para extraer datos, proporcione la información adicional siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a45d-151">Depending on the method selected for extracting data, provide the following additional information:</span></span>  
  
    -   <span data-ttu-id="1a45d-152">Para la opción **P - Desencadenar cadena de procesos** , proporcione el nombre de host de puerta de enlace, el nombre del servicio de la puerta de enlace, el identificador de programa para el destino RFC y el nombre de la cadena de procesos.</span><span class="sxs-lookup"><span data-stu-id="1a45d-152">For the **P - Trigger Process Chain** option, provide the gateway host name, gateway service name, program ID for the RFC destination, and name of the process chain.</span></span>  
  
    -   <span data-ttu-id="1a45d-153">Para la opción **W - Esperar notificación** , proporcione el nombre de host de puerta de enlace, el nombre del servidor de la puerta de enlace y el identificador de programa para el destino de RFC.</span><span class="sxs-lookup"><span data-stu-id="1a45d-153">For the **W - Wait for Notify** option, provide the gateway host name, the gateway server name, and the program ID for the RFC destination.</span></span> <span data-ttu-id="1a45d-154">Asimismo, puede especificar el tiempo de espera (en segundos).</span><span class="sxs-lookup"><span data-stu-id="1a45d-154">You can also specify the timeout (in seconds).</span></span> <span data-ttu-id="1a45d-155">El tiempo de espera es el periodo de tiempo máximo que esperará el origen para recibir la notificación.</span><span class="sxs-lookup"><span data-stu-id="1a45d-155">The timeout is the maximum period of time that the source will wait to be notified.</span></span>  
  
    -   <span data-ttu-id="1a45d-156">Para la opción **E - Extraer únicamente** , proporcione el identificador de solicitud.</span><span class="sxs-lookup"><span data-stu-id="1a45d-156">For the **E - Extract Only** option, provide the Request ID.</span></span>  
  
-   <span data-ttu-id="1a45d-157">Especifique las reglas de conversión de cadenas.</span><span class="sxs-lookup"><span data-stu-id="1a45d-157">Specify rules for string conversion.</span></span> <span data-ttu-id="1a45d-158">(Por ejemplo, convierta todas las cadenas en función de si el sistema SAP Netweaver BW es Unicode o no o convierta todas las cadenas a `varchar` o a `nvarchar`).</span><span class="sxs-lookup"><span data-stu-id="1a45d-158">(For example, convert all strings depending on whether the SAP Netweaver BW system is Unicode or not, or convert all strings to `varchar` or `nvarchar`).</span></span>  
  
-   <span data-ttu-id="1a45d-159">Use las opciones que ha seleccionado para obtener una vista previa de los datos que se van a extraer.</span><span class="sxs-lookup"><span data-stu-id="1a45d-159">Use the options that you have selected to preview the data to be extracted.</span></span>  
  
 <span data-ttu-id="1a45d-160">También puede habilitar el registro de las llamadas del origen a funciones RFC.</span><span class="sxs-lookup"><span data-stu-id="1a45d-160">You can also enable logging of RFC function calls by the source.</span></span> <span data-ttu-id="1a45d-161">(Este registro es independiente del registro opcional que puede habilitar en los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ). Las llamadas a funciones RFC se habilitan cuando se configura el administrador de conexiones SAP BW que va a usar el origen.</span><span class="sxs-lookup"><span data-stu-id="1a45d-161">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the source will use.</span></span> <span data-ttu-id="1a45d-162">Para obtener más información sobre cómo configurar el administrador de conexiones de SAP BW, vea [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1a45d-162">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="1a45d-163">Si no conoce todos los valores necesarios para configurar el origen, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="1a45d-163">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="1a45d-164">Para obtener instrucciones sobre cómo configurar y utilizar el administrador de conexiones, el origen y el destino de SAP BW, vea las notas del producto, [Usar SQL Server 2008 Integration Services con SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="1a45d-164">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="1a45d-165">Estas notas del producto también muestran cómo configurar los objetos necesarios en SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1a45d-165">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="1a45d-166">Usar el Diseñador SSIS para configurar el origen</span><span class="sxs-lookup"><span data-stu-id="1a45d-166">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="1a45d-167">Para obtener más información sobre las propiedades del origen de SAP BW que puede establecer en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1a45d-167">For more information about the properties of the SAP BW source that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="1a45d-168">Editor de origen de SAP BW &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="1a45d-168">SAP BW Source Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="1a45d-169">Editor de origen de SAP BW &#40;página Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="1a45d-169">SAP BW Source Editor &#40;Columns Page&#41;</span></span>](sap-bw-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="1a45d-170">Editor de origen de SAP BW &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="1a45d-170">SAP BW Source Editor &#40;Error Output Page&#41;</span></span>](sap-bw-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="1a45d-171">Editor de origen de SAP BW &#40;página Avanzadas&#41;</span><span class="sxs-lookup"><span data-stu-id="1a45d-171">SAP BW Source Editor &#40;Advanced Page&#41;</span></span>](sap-bw-source-editor-advanced-page.md)  
  
 <span data-ttu-id="1a45d-172">Mientras configura el origen de SAP BW, también puede usar varios cuadros de diálogo para buscar los objetos de SAP Netweaver BW o para obtener una vista previa de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="1a45d-172">While you are configuring the SAP BW source, you can also use various dialog boxes to look up SAP Netweaver BW objects or to preview the source data.</span></span> <span data-ttu-id="1a45d-173">Para obtener más información sobre estos cuadros de diálogo, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1a45d-173">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="1a45d-174">Buscar destino RFC</span><span class="sxs-lookup"><span data-stu-id="1a45d-174">Look Up RFC Destination</span></span>](look-up-rfc-destination.md)  
  
-   [<span data-ttu-id="1a45d-175">Buscar cadena de procesos</span><span class="sxs-lookup"><span data-stu-id="1a45d-175">Look Up Process Chain</span></span>](look-up-process-chain.md)  
  
-   [<span data-ttu-id="1a45d-176">Registro de solicitudes</span><span class="sxs-lookup"><span data-stu-id="1a45d-176">Request Log</span></span>](request-log.md)  
  
-   [<span data-ttu-id="1a45d-177">Versión preliminar</span><span class="sxs-lookup"><span data-stu-id="1a45d-177">Preview</span></span>](preview.md)  
  
## <a name="see-also"></a><span data-ttu-id="1a45d-178">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1a45d-178">See Also</span></span>  
 [<span data-ttu-id="1a45d-179">Componentes de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="1a45d-179">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
