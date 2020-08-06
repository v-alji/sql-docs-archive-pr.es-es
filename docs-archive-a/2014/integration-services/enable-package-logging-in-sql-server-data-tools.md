---
title: Habilitar el registro de paquetes en SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], enabling
ms.assetid: b69a8593-5bb0-4f04-87d2-f8e7bd7eb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d73dbca034047e853669dd503a62e105d1dd7b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673808"
---
# <a name="enable-package-logging-in-sql-server-data-tools"></a><span data-ttu-id="c0a10-102">Habilitar el registro de paquetes en SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="c0a10-102">Enable Package Logging in SQL Server Data Tools</span></span>
  <span data-ttu-id="c0a10-103">Este procedimiento describe cómo agregar registros a un paquete, configurar el registro en el nivel de paquete y guardar la configuración de registro en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="c0a10-103">This procedure describes how to add logs to a package, configure package-level logging, and save the logging configuration to an XML file.</span></span> <span data-ttu-id="c0a10-104">Solo puede agregar registros en el nivel de paquete, pero el paquete no tiene que realizar registros para habilitar el registro en los contenedores que incluye.</span><span class="sxs-lookup"><span data-stu-id="c0a10-104">You can add logs only at the package level, but the package does not have to perform logging to enable logging in the containers that the package includes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c0a10-105">Si implementa el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en el servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , el nivel de registro que establezca para la ejecución de paquetes invalidará el registro de paquetes que se configura mediante [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0a10-105">If you deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the logging level that you set for the package execution overrides the package logging that you configure using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c0a10-106">De manera predeterminada, los contenedores del paquete utilizan la misma configuración de registro que el contenedor principal.</span><span class="sxs-lookup"><span data-stu-id="c0a10-106">By default, the containers in the package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="c0a10-107">Para obtener información sobre la configuración de las opciones de registro para contenedores concretos, vea [Configurar el registro utilizando un archivo de configuración guardado](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="c0a10-107">For information about setting logging options for individual containers, see [Configure Logging by Using a Saved Configuration File](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span></span>  
  
### <a name="to-enable-logging-in-a-package"></a><span data-ttu-id="c0a10-108">Para habilitar el registro en un paquete</span><span class="sxs-lookup"><span data-stu-id="c0a10-108">To enable logging in a package</span></span>  
  
1.  <span data-ttu-id="c0a10-109">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="c0a10-109">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="c0a10-110">En el menú **SSIS** , haga clic en **Registro**.</span><span class="sxs-lookup"><span data-stu-id="c0a10-110">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="c0a10-111">Seleccione un proveedor de registro en la lista **Tipo de proveedor** y a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c0a10-111">Select a log provider in the **Provider type** list, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="c0a10-112">En la columna **Configuración**, seleccione un administrador de conexiones o haga clic en **\<New connection>** para crear un nuevo administrador de conexiones del tipo apropiado para el proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="c0a10-112">In the **Configuration** column, select a connection manager or click **\<New connection>** to create a new connection manager of the appropriate type for the log provider.</span></span> <span data-ttu-id="c0a10-113">En función del proveedor seleccionado, utilice uno de los siguientes administradores de conexión:</span><span class="sxs-lookup"><span data-stu-id="c0a10-113">Depending on the selected provider, use one of the following connection managers:</span></span>  
  
    -   <span data-ttu-id="c0a10-114">Para archivos de texto, utilice un administrador de conexiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="c0a10-114">For Text files, use a File connection manager.</span></span> <span data-ttu-id="c0a10-115">Para más información, vea [File Connection Manager](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="c0a10-115">For more information, see [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
    -   <span data-ttu-id="c0a10-116">Para el [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], utilice un administrador de conexiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="c0a10-116">For [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use a File connection manager.</span></span>  
  
    -   <span data-ttu-id="c0a10-117">Para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], utilice un administrador de conexiones OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c0a10-117">For [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use an OLE DB connection manager.</span></span> <span data-ttu-id="c0a10-118">Para más información, consulte [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c0a10-118">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
    -   <span data-ttu-id="c0a10-119">Para el registro de eventos de Windows no haga nada.</span><span class="sxs-lookup"><span data-stu-id="c0a10-119">For Windows Event Log, do nothing.</span></span> [!INCLUDE[ssIS](../includes/ssis-md.md)] <span data-ttu-id="c0a10-120">crea automáticamente el registro.</span><span class="sxs-lookup"><span data-stu-id="c0a10-120">automatically creates the log.</span></span>  
  
    -   <span data-ttu-id="c0a10-121">Para archivos XML, utilice un administrador de conexiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="c0a10-121">For XML files, use a File connection manager.</span></span>  
  
5.  <span data-ttu-id="c0a10-122">Repita los pasos 3 y 4 para cada registro que desee utilizar en el paquete.</span><span class="sxs-lookup"><span data-stu-id="c0a10-122">Repeat steps 3 and 4 for each log to use in the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0a10-123">Un paquete puede utilizar más de un registro de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="c0a10-123">A package can use more than one log of each type.</span></span>  
  
6.  <span data-ttu-id="c0a10-124">Opcionalmente, active la casilla de nivel de paquete, seleccione los registros que quiera usar para el registro de nivel de paquete y, después, haga clic en la pestaña **Detalles** .</span><span class="sxs-lookup"><span data-stu-id="c0a10-124">Optionally, select the package-level check box, select the logs to use for package-level logging, and then click the **Details** tab.</span></span>  
  
7.  <span data-ttu-id="c0a10-125">En la pestaña **Detalles** , seleccione **Eventos** para registrar todas las entradas del registro o bien, borre **Eventos** para seleccionar eventos concretos.</span><span class="sxs-lookup"><span data-stu-id="c0a10-125">On the **Details** tab, select **Events** to log all log entries, or clear **Events** to select individual events.</span></span>  
  
8.  <span data-ttu-id="c0a10-126">Opcionalmente, haga clic en **Avanzada** para especificar la información que desee registrar.</span><span class="sxs-lookup"><span data-stu-id="c0a10-126">Optionally, click **Advanced** to specify which information to log.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0a10-127">De manera predeterminada, se registra toda la información.</span><span class="sxs-lookup"><span data-stu-id="c0a10-127">By default, all information is logged.</span></span>  
  
9. <span data-ttu-id="c0a10-128">En la pestaña **Detalles** , haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c0a10-128">On the **Details** tab, click **Save.**</span></span> <span data-ttu-id="c0a10-129">Aparece el cuadro de diálogo **Guardar como** .</span><span class="sxs-lookup"><span data-stu-id="c0a10-129">The **Save As** dialog box appears.</span></span> <span data-ttu-id="c0a10-130">Localice la carpeta en la que desee guardar la configuración de registro, escriba un nombre de archivo para la nueva configuración de registro y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c0a10-130">Locate the folder in which to save the logging configuration, type a file name for the new log configuration, and then click **Save**.</span></span>  
  
10. <span data-ttu-id="c0a10-131">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0a10-131">Click **OK**.</span></span>  
  
11. <span data-ttu-id="c0a10-132">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="c0a10-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0a10-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0a10-133">See Also</span></span>  
 <span data-ttu-id="c0a10-134">[Integration Services &#40;SSIS&#41; registro](performance/integration-services-ssis-logging.md) </span><span class="sxs-lookup"><span data-stu-id="c0a10-134">[Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md) </span></span>  
 [<span data-ttu-id="c0a10-135">Registro de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c0a10-135">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
