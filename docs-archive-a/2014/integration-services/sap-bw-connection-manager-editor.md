---
title: SAP BW editor del administrador de conexiones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ec970319-e749-4753-8675-9cf76ed99669
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 527af979fc9c92062f24e1fe161b93e88ed4ab4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745373"
---
# <a name="sap-bw-connection-manager-editor"></a><span data-ttu-id="e8543-102">Editor del administrador de conexiones SAP BW</span><span class="sxs-lookup"><span data-stu-id="e8543-102">SAP BW Connection Manager Editor</span></span>
  <span data-ttu-id="e8543-103">Use el **Editor del administrador de conexiones de SAP BW** para especificar las propiedades que se van a usar para establecer una conexión con la versión 7 del sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e8543-103">Use the **SAP BW Connection Manager Editor** to specify the properties to use to connect to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="e8543-104">El administrador de conexiones de SAP BW aporta conectividad a cualquier sistema SAP Netweaver BW de la versión 7 que use el origen o destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e8543-104">The SAP BW connection manager provides connectivity to an SAP Netweaver BW 7 system for use by the SAP BW source or destination.</span></span> <span data-ttu-id="e8543-105">Para más información sobre el administrador de conexiones de SAP BW de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Administrador de conexiones de SAP BW](connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e8543-105">To learn more about the SAP BW connection manager of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Connection Manager](connection-manager/sap-bw-connection-manager.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8543-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e8543-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="e8543-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="e8543-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="e8543-108">**Para abrir el Editor del administrador de conexiones de SAP BW**</span><span class="sxs-lookup"><span data-stu-id="e8543-108">**To open the SAP BW Connection Manager Editor**</span></span>  
  
1.  <span data-ttu-id="e8543-109">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el administrador de conexiones de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e8543-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that contains the SAP BW connection manager.</span></span>  
  
2.  <span data-ttu-id="e8543-110">En el área Administradores de conexión, en la pestaña **Flujo de control** , lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="e8543-110">In the Connection Managers area on the **Control Flow** tab, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="e8543-111">Haga doble clic en administrador de conexiones de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e8543-111">Double-click the SAP BW connection manager.</span></span>  
  
         <span data-ttu-id="e8543-112">O bien</span><span class="sxs-lookup"><span data-stu-id="e8543-112">-or-</span></span>  
  
    -   <span data-ttu-id="e8543-113">Haga clic con el botón derecho en el administrador de conexiones de SAP BW y, después, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e8543-113">Right-click the SAP BW connection manager, and then select **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e8543-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="e8543-114">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8543-115">Si no conoce todos los valores necesarios para configurar el administrador de conexiones, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="e8543-115">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="e8543-116">**Cliente**</span><span class="sxs-lookup"><span data-stu-id="e8543-116">**Client**</span></span>  
 <span data-ttu-id="e8543-117">Especifique el número de cliente del sistema.</span><span class="sxs-lookup"><span data-stu-id="e8543-117">Specify the client number of the system.</span></span>  
  
 <span data-ttu-id="e8543-118">**Lenguaje**</span><span class="sxs-lookup"><span data-stu-id="e8543-118">**Language**</span></span>  
 <span data-ttu-id="e8543-119">Permite especificar el idioma que usa el sistema.</span><span class="sxs-lookup"><span data-stu-id="e8543-119">Specify the language that the system uses.</span></span> <span data-ttu-id="e8543-120">Por ejemplo, especifique **EN** para inglés.</span><span class="sxs-lookup"><span data-stu-id="e8543-120">For example, specify **EN** for English.</span></span>  
  
 <span data-ttu-id="e8543-121">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="e8543-121">**User name**</span></span>  
 <span data-ttu-id="e8543-122">Permite especificar el nombre de usuario que se va a utilizar para establecer la conexión al sistema.</span><span class="sxs-lookup"><span data-stu-id="e8543-122">Specify the user name that will be used to connect to the system.</span></span>  
  
 <span data-ttu-id="e8543-123">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="e8543-123">**Password**</span></span>  
 <span data-ttu-id="e8543-124">Permite especificar la contraseña que se va a usar con el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="e8543-124">Specify the password that will be used with the user name.</span></span>  
  
 <span data-ttu-id="e8543-125">**Usar un solo servidor de aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="e8543-125">**Use single application server**</span></span>  
 <span data-ttu-id="e8543-126">Permite conectarse a un único servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e8543-126">Connect to a single application server.</span></span>  
  
 <span data-ttu-id="e8543-127">Para conectarse a un grupo de servidores con equilibrio de carga, use en su lugar la opción **Usar equilibrio de carga** .</span><span class="sxs-lookup"><span data-stu-id="e8543-127">To connect to a group of load-balanced servers, use the **Use load balancing** option instead.</span></span>  
  
 <span data-ttu-id="e8543-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="e8543-128">**Host**</span></span>  
 <span data-ttu-id="e8543-129">Si se va a conectar a un único servidor de aplicaciones, especifique el nombre de host.</span><span class="sxs-lookup"><span data-stu-id="e8543-129">If connecting to a single application server, specify the host name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8543-130">Esta opción solo está disponible si ha seleccionado la opción **Usar un solo servidor de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="e8543-130">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="e8543-131">**Número del sistema**</span><span class="sxs-lookup"><span data-stu-id="e8543-131">**System number**</span></span>  
 <span data-ttu-id="e8543-132">Si se va a conectar a un único servidor de aplicaciones, especifique el número del sistema.</span><span class="sxs-lookup"><span data-stu-id="e8543-132">If connecting to a single application server, specify the system number.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8543-133">Esta opción solo está disponible si ha seleccionado la opción **Usar un solo servidor de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="e8543-133">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="e8543-134">**Usar equilibrio de carga**</span><span class="sxs-lookup"><span data-stu-id="e8543-134">**Use load balancing**</span></span>  
 <span data-ttu-id="e8543-135">Permite conectarse a un grupo de servidores con equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="e8543-135">Connect to a group of load-balanced servers.</span></span>  
  
 <span data-ttu-id="e8543-136">Para conectarse a un único servidor de aplicaciones, use en su lugar la opción **Usar un solo servidor de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="e8543-136">To connect to a single application server, use the **Use single application server** option instead.</span></span>  
  
 <span data-ttu-id="e8543-137">**Servidor de mensajes**</span><span class="sxs-lookup"><span data-stu-id="e8543-137">**Message server**</span></span>  
 <span data-ttu-id="e8543-138">Si se conecta a un grupo de servidores con equilibrio de carga, especifique el nombre del servidor del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e8543-138">If connecting to a group of load-balanced servers, specify the name of the message server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8543-139"> Esta opción solo está disponible si ha seleccionado la opción **Usar equilibrio de carga** .</span><span class="sxs-lookup"><span data-stu-id="e8543-139">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="e8543-140">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="e8543-140">**Group**</span></span>  
 <span data-ttu-id="e8543-141">Si se conecta a un grupo de servidores con equilibrio de carga, especifique el nombre del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="e8543-141">If connecting to a group of load-balanced servers, specify the name of the server group name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8543-142"> Esta opción solo está disponible si ha seleccionado la opción **Usar equilibrio de carga** .</span><span class="sxs-lookup"><span data-stu-id="e8543-142">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="e8543-143">**Junction**</span><span class="sxs-lookup"><span data-stu-id="e8543-143">**SID**</span></span>  
 <span data-ttu-id="e8543-144">Si se conecta a un grupo de servidores con equilibrio de carga, especifique el identificador del sistema para la conexión.</span><span class="sxs-lookup"><span data-stu-id="e8543-144">If connecting to a group of load-balanced servers, specify the System ID for the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8543-145"> Esta opción solo está disponible si ha seleccionado la opción **Usar equilibrio de carga** .</span><span class="sxs-lookup"><span data-stu-id="e8543-145">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="e8543-146">**Directorio de registro**</span><span class="sxs-lookup"><span data-stu-id="e8543-146">**Log directory**</span></span>  
 <span data-ttu-id="e8543-147">Permite habilitar el registro para los componentes de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e8543-147">Enable logging for the components of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 <span data-ttu-id="e8543-148">Para habilitar el registro, debe especificar un directorio para los archivos de registro que se crean antes y después de cada llamada a funciones RFC.</span><span class="sxs-lookup"><span data-stu-id="e8543-148">To enable logging, specify a directory for the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="e8543-149">(Esta característica de registro crea múltiples archivos de registro en formato XML.</span><span class="sxs-lookup"><span data-stu-id="e8543-149">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="e8543-150">Dado que estos archivos de registro también contienen todas las filas de datos que se transfieren, es posible que los archivos de registro consuman gran cantidad de espacio en disco).</span><span class="sxs-lookup"><span data-stu-id="e8543-150">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8543-151">Si los datos que se transfieren contienen información confidencial, los archivos de registro también contendrán esa información confidencial.</span><span class="sxs-lookup"><span data-stu-id="e8543-151">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
 <span data-ttu-id="e8543-152">Para especificar el directorio de registro, puede escribir la ruta de acceso manualmente o bien, haga clic en **Examinar** y busque el directorio de registro.</span><span class="sxs-lookup"><span data-stu-id="e8543-152">To specify the log directory, you can either enter the directory path manually, or click **Browse** and browse to the log directory.</span></span>  
  
 <span data-ttu-id="e8543-153">Si no selecciona un directorio de registro, el registro no estará habilitado.</span><span class="sxs-lookup"><span data-stu-id="e8543-153">If you do not select a log directory, logging is not enabled.</span></span>  
  
 <span data-ttu-id="e8543-154">**Browse**</span><span class="sxs-lookup"><span data-stu-id="e8543-154">**Browse**</span></span>  
 <span data-ttu-id="e8543-155">Permite examinar para seleccionar una carpeta para el directorio de registro.</span><span class="sxs-lookup"><span data-stu-id="e8543-155">Browse to select a folder for the log directory.</span></span>  
  
 <span data-ttu-id="e8543-156">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="e8543-156">**Test Connection**</span></span>  
 <span data-ttu-id="e8543-157">Permite probar la conexión con los valores que ha especificado.</span><span class="sxs-lookup"><span data-stu-id="e8543-157">Test the connection using the values that you have provided.</span></span> <span data-ttu-id="e8543-158">Después de hacer clic en **Probar conexión**, aparecerá un cuadro de mensaje que indica si la conexión se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="e8543-158">After clicking **Test Connection**, a message box appears and indicates whether the connection succeeded or failed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8543-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8543-159">See Also</span></span>  
 [<span data-ttu-id="e8543-160">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="e8543-160">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
  
  
