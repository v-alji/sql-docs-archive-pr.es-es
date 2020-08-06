---
title: Destino de SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a612ed91-b89b-4173-a0b1-0bce381e1e28
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a0d7c5b75da89e665dbe60bbd7e29ce74da67db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674975"
---
# <a name="sap-bw-destination"></a><span data-ttu-id="77027-102">Destino de SAP BW</span><span class="sxs-lookup"><span data-stu-id="77027-102">SAP BW Destination</span></span>
  <span data-ttu-id="77027-103">El destino de SAP BW es el componente de destino de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="77027-103">The SAP BW destination is the destination component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="77027-104">De esta forma, el destino de SAP BW carga los datos desde el flujo de datos de un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en la versión 7 del sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="77027-104">Thus, the SAP BW destination loads data from the data flow in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package into an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="77027-105">Este destino tienen una entrada y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="77027-105">This destination has one input and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="77027-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="77027-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="77027-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="77027-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="77027-108">Para usar el destino de SAP BW, deberá realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="77027-108">To use the SAP BW destination, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="77027-109">Preparar los objetos de SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="77027-109">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="77027-110">Conectarse al sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="77027-110">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="77027-111">Configurar el destino de SAP BW</span><span class="sxs-lookup"><span data-stu-id="77027-111">Configure the SAP BW destination</span></span>](#bkmk_Configure_Destination)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-destination-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="77027-112">Preparar los objetos SAP Netweaver BW que requiera el destino</span><span class="sxs-lookup"><span data-stu-id="77027-112">Preparing the SAP Netweaver BW Objects That the Destination Requires</span></span>  
 <span data-ttu-id="77027-113">El destino de SAP BW requiere que ciertos objetos estén en el sistema SAP Netweaver BW antes de que pueda funcionar el destino.</span><span class="sxs-lookup"><span data-stu-id="77027-113">The SAP BW destination requires that certain objects are in the SAP Netweaver BW system before the destination can function.</span></span> <span data-ttu-id="77027-114">Si estos objetos no existen aún, debe seguir estos pasos para crear y configurar estos objetos en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="77027-114">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77027-115">Para obtener detalles adicionales sobre estos objetos y pasos de configuración, vea la documentación sobre SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="77027-115">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="77027-116">Crear un nuevo sistema de origen:</span><span class="sxs-lookup"><span data-stu-id="77027-116">Create a new Source System:</span></span>  
  
    1.  <span data-ttu-id="77027-117">Seleccione el tipo **"Terceros/BAPI de almacenamiento provisional"** .</span><span class="sxs-lookup"><span data-stu-id="77027-117">Select the type, **"Third Party/Staging BAPIs"**.</span></span>  
  
    2.  <span data-ttu-id="77027-118">Para **Tipo de comunicación con sistema de destino**, seleccione **No Unicode (valores inactivos de MDMP)** .</span><span class="sxs-lookup"><span data-stu-id="77027-118">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    3.  <span data-ttu-id="77027-119">Asignar un identificador de programa adecuado</span><span class="sxs-lookup"><span data-stu-id="77027-119">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="77027-120">Asigne el sistema de origen a un InfoSource.</span><span class="sxs-lookup"><span data-stu-id="77027-120">Assign the Source System to an InfoSource.</span></span>  
  
3.  <span data-ttu-id="77027-121">Cree un InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="77027-121">Create an InfoPackage.</span></span>  
  
     <span data-ttu-id="77027-122">El InfoPackage es el objeto más importante que requiere el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="77027-122">The InfoPackage is the most important object that is required by the SAP BW destination.</span></span>  
  
 <span data-ttu-id="77027-123">También puede crear InfoObjects, InfoCubes, InfoSources e InfoPackages adicionales según sean necesarios para respaldar la carga de datos en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="77027-123">You can also create additional InfoObjects, InfoCubes, InfoSources, and InfoPackages that are required to support loading data into the SAP Netweaver BW system.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="77027-124">Conectarse al sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="77027-124">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="77027-125">Para conectarse al sistema SAP Netweaver BW de la versión 7, el destino de SAP BW usa un administrador de conexiones para SAP BW que forma parte del paquete [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="77027-125">To connect to the SAP Netweaver BW version 7 system, the SAP BW destination uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="77027-126">El administrador de conexiones de SAP BW es el único administrador de conexiones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que puede usar el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="77027-126">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW destination can use.</span></span>  
  
 <span data-ttu-id="77027-127">Para obtener más información sobre el administrador de conexiones de SAP BW, vea [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="77027-127">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-destination"></a><a name="bkmk_Configure_Destination"></a> <span data-ttu-id="77027-128">Configurar el destino de SAP BW</span><span class="sxs-lookup"><span data-stu-id="77027-128">Configuring the SAP BW Destination</span></span>  
 <span data-ttu-id="77027-129">Puede configurar el destino de SAP BW de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="77027-129">You can configure the SAP BW destination in the following ways:</span></span>  
  
-   <span data-ttu-id="77027-130">Busque y seleccione el InfoPackage que se va a usar para cargar datos.</span><span class="sxs-lookup"><span data-stu-id="77027-130">Look up and select the InfoPackage to use to load data.</span></span>  
  
-   <span data-ttu-id="77027-131">Asigne cada columna del flujo de datos al InfoObject correcto en el InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="77027-131">Map each column in the data flow to the appropriate InfoObject in the InfoPackage.</span></span>  
  
-   <span data-ttu-id="77027-132">Especifique cuántas filas de datos se transfieren a la vez mediante la configuración de la propiedad `PackageSize`.</span><span class="sxs-lookup"><span data-stu-id="77027-132">Specify how many rows of data will be transferred at a time by configuring the `PackageSize` property.</span></span>  
  
-   <span data-ttu-id="77027-133">Elija esperar hasta el sistema SAP Netweaver BW haya completado la carga de datos.</span><span class="sxs-lookup"><span data-stu-id="77027-133">Choose to wait until the loading of data is completed by the SAP Netweaver BW system.</span></span>  
  
-   <span data-ttu-id="77027-134">Elija que no se desencadene el InfoPackage, pero que espere a recibir la notificación de que el sistema SAP Netweaver BW ha comenzado a cargar datos.</span><span class="sxs-lookup"><span data-stu-id="77027-134">Choose not to trigger the InfoPackage, but to wait for notification that the SAP Netweaver BW system has started the loading of data.</span></span>  
  
-   <span data-ttu-id="77027-135">Opcionalmente, desencadene otra cadena de procesos después de haber completado la carga de los datos.</span><span class="sxs-lookup"><span data-stu-id="77027-135">Optionally, trigger another process chain after the loading of data is completed.</span></span>  
  
-   <span data-ttu-id="77027-136">Opcionalmente, puede crear los objetos de SAP Netweaver BW que necesita el destino.</span><span class="sxs-lookup"><span data-stu-id="77027-136">Optionally, create the SAP Netweaver BW objects that are required by the destination.</span></span> <span data-ttu-id="77027-137">Lo cual incluye la creación de InfoObjects, InfoCubes, InfoSources e InfoPackages.</span><span class="sxs-lookup"><span data-stu-id="77027-137">This includes creating InfoObjects, InfoCubes, InfoSources, and InfoPackages.</span></span>  
  
-   <span data-ttu-id="77027-138">Pruebe la carga de datos con las opciones que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="77027-138">Test the loading of data with the options that you have selected.</span></span>  
  
 <span data-ttu-id="77027-139">También puede habilitar el registro de las llamadas por parte del destino.</span><span class="sxs-lookup"><span data-stu-id="77027-139">You can also enable logging of RFC function calls by the destination.</span></span> <span data-ttu-id="77027-140">(Este registro es independiente del registro opcional que puede habilitar en los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ). Las llamadas a funciones RFC se habilitan cuando se configura el administrador de conexiones SAP BW que va a usar el destino.</span><span class="sxs-lookup"><span data-stu-id="77027-140">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the destination will use.</span></span> <span data-ttu-id="77027-141">Para obtener más información sobre cómo configurar el administrador de conexiones de SAP BW, vea [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="77027-141">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="77027-142">Si no conoce todos los valores necesarios para configurar el destino, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="77027-142">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="77027-143">Para obtener instrucciones sobre cómo configurar y utilizar el administrador de conexiones, el origen y el destino de SAP BW, vea las notas del producto, [Usar SQL Server 2008 Integration Services con SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="77027-143">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="77027-144">Estas notas del producto también muestran cómo configurar los objetos necesarios en SAP BW.</span><span class="sxs-lookup"><span data-stu-id="77027-144">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-destination"></a><span data-ttu-id="77027-145">Usar el Diseñador SSIS para configurar el destino</span><span class="sxs-lookup"><span data-stu-id="77027-145">Using the SSIS Designer to Configure the Destination</span></span>  
 <span data-ttu-id="77027-146">Para obtener más información sobre las propiedades del destino de SAP BW que puede establecer en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="77027-146">For more information about the properties of the SAP BW destination that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="77027-147">Editor de destino de SAP BW &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="77027-147">SAP BW Destination Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="77027-148">Editor de destino de SAP BW &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="77027-148">SAP BW Destination Editor &#40;Mappings Page&#41;</span></span>](sap-bw-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="77027-149">Editor de destino de SAP BW &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="77027-149">SAP BW Destination Editor &#40;Error Output Page&#41;</span></span>](sap-bw-destination-editor-error-output-page.md)  
  
-   [<span data-ttu-id="77027-150">Editor de destino de SAP BW &#40;página Avanzadas&#41;</span><span class="sxs-lookup"><span data-stu-id="77027-150">SAP BW Destination Editor &#40;Advanced Page&#41;</span></span>](sap-bw-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="77027-151">Mientras configura el destino de SAP BW, también puede usar varios cuadros de diálogo para buscar o crear objetos de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="77027-151">While you are configuring the SAP BW destination, you can also use various dialog boxes to look up or to create SAP Netweaver BW objects.</span></span> <span data-ttu-id="77027-152">Para obtener más información sobre estos cuadros de diálogo, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="77027-152">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="77027-153">Buscar InfoPackage</span><span class="sxs-lookup"><span data-stu-id="77027-153">Look Up InfoPackage</span></span>](look-up-infopackage.md)  
  
-   [<span data-ttu-id="77027-154">Crear InfoObject</span><span class="sxs-lookup"><span data-stu-id="77027-154">Create New InfoObject</span></span>](create-new-infoobject.md)  
  
-   [<span data-ttu-id="77027-155">Crear InfoCube para datos de transacción</span><span class="sxs-lookup"><span data-stu-id="77027-155">Create InfoCube for Transaction Data</span></span>](create-infocube-for-transaction-data.md)  
  
-   [<span data-ttu-id="77027-156">Buscar InfoObject</span><span class="sxs-lookup"><span data-stu-id="77027-156">Look Up InfoObject</span></span>](look-up-infoobject.md)  
  
-   [<span data-ttu-id="77027-157">Crear InfoSource</span><span class="sxs-lookup"><span data-stu-id="77027-157">Create InfoSource</span></span>](create-infosource.md)  
  
-   [<span data-ttu-id="77027-158">Crear InfoSource para datos de transacción</span><span class="sxs-lookup"><span data-stu-id="77027-158">Create InfoSource for Transaction Data</span></span>](create-infosource-for-transaction-data.md)  
  
-   [<span data-ttu-id="77027-159">Crear InfoSource para datos maestros</span><span class="sxs-lookup"><span data-stu-id="77027-159">Create InfoSource for Master Data</span></span>](create-infosource-for-master-data.md)  
  
-   [<span data-ttu-id="77027-160">Crear InfoPackage</span><span class="sxs-lookup"><span data-stu-id="77027-160">Create InfoPackage</span></span>](create-infopackage.md)  
  
## <a name="see-also"></a><span data-ttu-id="77027-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77027-161">See Also</span></span>  
 [<span data-ttu-id="77027-162">Componentes de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="77027-162">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
