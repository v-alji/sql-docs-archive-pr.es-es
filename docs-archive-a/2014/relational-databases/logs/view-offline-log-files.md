---
title: Ver archivos de registro sin conexión | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, viewing offline logs
- offline log files
ms.assetid: 9223e474-f224-4907-a4f2-081e11db58f5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2afc1992b54c78f69bfae1fc152b41c20bcd4ea1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675361"
---
# <a name="view-offline-log-files"></a><span data-ttu-id="0517d-102">Ver sin conexión archivos de registro</span><span class="sxs-lookup"><span data-stu-id="0517d-102">View Offline Log Files</span></span>
  <span data-ttu-id="0517d-103">A partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], los archivos de registro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se pueden ver desde una instancia local o remota de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuando la instancia de destino está sin conexión o no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="0517d-103">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span>  
  
 <span data-ttu-id="0517d-104">Puede tener acceso a los archivos de registro sin conexión de servidores registrados o mediante programación a través de consultas WMI y WQL (Lenguaje de la consulta de WMI).</span><span class="sxs-lookup"><span data-stu-id="0517d-104">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0517d-105">También puede utilizar estos métodos para conectar a una instancia que está en línea, pero por el motivo que sea no puede conectarse a través de una conexión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0517d-105">You can also use these methods to connect to an instance that is online, but for some reason, you cannot connect through a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="0517d-106">Introducción</span><span class="sxs-lookup"><span data-stu-id="0517d-106">Before you Begin</span></span>  
 <span data-ttu-id="0517d-107">Para conectarse a los archivos de registro sin conexión, debe haber una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalada en el equipo que está utilizando para ver los archivos de registro sin conexión y en el equipo donde se encuentran los archivos de registro que desea ver.</span><span class="sxs-lookup"><span data-stu-id="0517d-107">To connect to offline log files, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be installed on the computer that you are using to view the offline log files, and on the computer where the log files that you want to view are located.</span></span> <span data-ttu-id="0517d-108">Si hay una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalada en los dos equipos, puede ver los archivos sin conexión para las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]y para las instancias que ejecutan versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en cualquiera de los dos equipos.</span><span class="sxs-lookup"><span data-stu-id="0517d-108">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on both computers, you can view offline files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and for instances that are running earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on either computer.</span></span>  
  
 <span data-ttu-id="0517d-109">Si utiliza servidores registrados, la instancia a la que desea conectarse debe estar registrada en **Grupos de servidores locales** o en **Servidores de administración central**.</span><span class="sxs-lookup"><span data-stu-id="0517d-109">If you are using Registered Servers, the instance that you want to connect to must be registered under **Local Server Groups** or under **Central Management Servers**.</span></span> <span data-ttu-id="0517d-110">La instancia se puede registrar sola o pertenecer a un grupo de servidores. Para obtener más información acerca de cómo agregar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a servidores registrados, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="0517d-110">(The instance can be registered on its own or be a member of a server group.) For more information about how to add an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to Registered Servers, see the following topics:</span></span>  
  
-   [<span data-ttu-id="0517d-111">Crear o editar un grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0517d-111">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="0517d-112">Registrar un servidor conectado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0517d-112">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="0517d-113">Crear un servidor de administración central y un grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0517d-113">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
 <span data-ttu-id="0517d-114">Para obtener más información sobre cómo ver archivos de registro sin conexión mediante programación con consultas WMI y WQL, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="0517d-114">For more information about how to view offline log files programmatically through WMI and WQL queries, see the following topics:</span></span>  
  
-   <span data-ttu-id="0517d-115">[SqlErrorLogEvent Class](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (en este tema se muestra cómo recuperar los valores de los eventos registrados en un archivo de registro especificado).</span><span class="sxs-lookup"><span data-stu-id="0517d-115">[SqlErrorLogEvent Class](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (This topic shows how to retrieve values for logged events in a specified log file.)</span></span>  
  
-   <span data-ttu-id="0517d-116">[SqlErrorLogFile Class](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (en este tema se muestra cómo recuperar información sobre todos los archivos de registro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de una instancia especificada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="0517d-116">[SqlErrorLogFile Class](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (This topic shows how to retrieve information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0517d-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="0517d-117">Permissions</span></span>  
 <span data-ttu-id="0517d-118">Para conectarse a un archivo de registro sin conexión, debe tener los siguientes permisos en los equipos local y remoto:</span><span class="sxs-lookup"><span data-stu-id="0517d-118">To connect to an offline log file, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="0517d-119">Acceso de lectura al espacio de nombres de WMI **raíz\Microsoft\SqlServer\ComputerManagement12** .</span><span class="sxs-lookup"><span data-stu-id="0517d-119">Read access to the **Root\Microsoft\SqlServer\ComputerManagement12** WMI namespace.</span></span> <span data-ttu-id="0517d-120">De forma predeterminada, todos tienen acceso de lectura mediante el permiso Habilitar cuenta.</span><span class="sxs-lookup"><span data-stu-id="0517d-120">By default, everyone has read access through the Enable Account permission.</span></span> <span data-ttu-id="0517d-121">Para obtener más información, vea el procedimiento sobre comprobación de permisos de WMI más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="0517d-121">For more information, see the "To verify WMI permissions" procedure later in this section.</span></span>  
  
-   <span data-ttu-id="0517d-122">Permiso de lectura a la carpeta que contiene los archivos de registro de errores.</span><span class="sxs-lookup"><span data-stu-id="0517d-122">Read permission to the folder that contains the error log files.</span></span> <span data-ttu-id="0517d-123">De forma predeterminada, los archivos de registro de errores se encuentran en la ruta de acceso siguiente (donde \<*Drive>\* representa la unidad en la que se ha instalado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y \<*InstanceName*> es el nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span><span class="sxs-lookup"><span data-stu-id="0517d-123">By default the error log files are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="0517d-124">**\<Drive>: \Archivos de Programa\microsoft SQL Server\MSSQL12. \<InstanceName> \Mssql\log.**</span><span class="sxs-lookup"><span data-stu-id="0517d-124">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="0517d-125">Para comprobar la configuración de seguridad del espacio de nombres WMI, puede utilizar el complemento Control WMI.</span><span class="sxs-lookup"><span data-stu-id="0517d-125">To verify WMI namespace security settings, you can use the WMI Control snap-in.</span></span>  
  
#### <a name="to-verify-wmi-permissions"></a><span data-ttu-id="0517d-126">Comprobar los permisos de WMI</span><span class="sxs-lookup"><span data-stu-id="0517d-126">To verify WMI permissions</span></span>  
  
1.  <span data-ttu-id="0517d-127">Abra el complemento Control WMI.</span><span class="sxs-lookup"><span data-stu-id="0517d-127">Open the WMI Control snap-in.</span></span> <span data-ttu-id="0517d-128">Para hacerlo, realice una de las operaciones siguientes, en función del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="0517d-128">To do this, do either of the following, depending on the operating system:</span></span>  
  
    -   <span data-ttu-id="0517d-129">Haga clic en **Inicio**, escriba `wmimgmt.msc` en el cuadro **Iniciar búsqueda** y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="0517d-129">Click **Start**, type `wmimgmt.msc` in the **Start Search** box, and then press ENTER.</span></span>  
  
    -   <span data-ttu-id="0517d-130">Haga clic en **Inicio**, haga clic en **Ejecutar**, escriba `wmimgmt.msc` y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="0517d-130">Click **Start**, click **Run**, type `wmimgmt.msc`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="0517d-131">De forma predeterminada, el complemento Control WMI administra el equipo local.</span><span class="sxs-lookup"><span data-stu-id="0517d-131">By default, the WMI Control snap-in manages the local computer.</span></span>  
  
     <span data-ttu-id="0517d-132">Si desea conectarse a un equipo remoto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0517d-132">If you want to connect to a remote computer, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="0517d-133">Haga clic con el botón derecho en **Control WMI (local)** y, luego, haga clic en **Conectarse a otro equipo**.</span><span class="sxs-lookup"><span data-stu-id="0517d-133">Right-click **WMI Control (Local)**, and then click **Connect to another computer**.</span></span>  
  
    2.  <span data-ttu-id="0517d-134">En el cuadro de diálogo **Cambiar equipo administrado** , haga clic en **Otro equipo**.</span><span class="sxs-lookup"><span data-stu-id="0517d-134">In the **Change managed computer** dialog box, click **Another computer**.</span></span>  
  
    3.  <span data-ttu-id="0517d-135">Escriba el nombre del equipo remoto y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0517d-135">Enter the remote computer name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="0517d-136">Haga clic con el botón secundario en **control WMI (local)** o **control WMI (***nombreDeEquipoRemoto***)** y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0517d-136">Right-click **WMI Control (Local)** or **WMI Control (***RemoteComputerName***)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0517d-137">En el cuadro de diálogo **Propiedades de Control WMIP** , haga clic en la pestaña **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="0517d-137">In the **WMI Control Properties** dialog box, click the **Security** tab.</span></span>  
  
5.  <span data-ttu-id="0517d-138">En el árbol de espacio de nombres, busque el siguiente espacio de nombres y haga clic en él:</span><span class="sxs-lookup"><span data-stu-id="0517d-138">In the namespace tree, locate and then click the following namespace:</span></span>  
  
     <span data-ttu-id="0517d-139">**Raíz\Microsoft\SqlServer\ComputerManagement10**</span><span class="sxs-lookup"><span data-stu-id="0517d-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span></span>  
  
6.  <span data-ttu-id="0517d-140">Haga clic en **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="0517d-140">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="0517d-141">Asegúrese de que la cuenta que se va a utilizar tiene el permiso **Habilitar cuenta** .</span><span class="sxs-lookup"><span data-stu-id="0517d-141">Make sure that the account that will be used has the **Enable Account** permission.</span></span> <span data-ttu-id="0517d-142">Este permiso permite el acceso de lectura a los objetos WMI.</span><span class="sxs-lookup"><span data-stu-id="0517d-142">This permission allows Read access to WMI objects.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="0517d-143">Ver archivos de registro</span><span class="sxs-lookup"><span data-stu-id="0517d-143">View Log Files</span></span>  
 <span data-ttu-id="0517d-144">El siguiente procedimiento indica cómo ver los archivos de registro sin conexión a través de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="0517d-144">The following procedure shows how to view offline log files through Registered Servers.</span></span> <span data-ttu-id="0517d-145">En el procedimiento se supone que:</span><span class="sxs-lookup"><span data-stu-id="0517d-145">The procedure assumes the following:</span></span>  
  
 <span data-ttu-id="0517d-146">La instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a la que desea conectarse ya está registrada en servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="0517d-146">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to is already registered in Registered Servers.</span></span>  
  
##### <a name="to-view-log-files-for-instances-that-are-offline"></a><span data-ttu-id="0517d-147">Ver los archivos de registro de las instancias que están sin conexión</span><span class="sxs-lookup"><span data-stu-id="0517d-147">To view log files for instances that are offline</span></span>  
  
1.  <span data-ttu-id="0517d-148">Si desea ver los archivos de registro sin conexión en una instancia local, asegúrese de que inicia [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="0517d-148">If you want to view offline log files on a local instance, make sure that you start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] with elevated permissions.</span></span> <span data-ttu-id="0517d-149">Para ello, al iniciar [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], haga clic con el botón derecho en **SQL Server Management Studio**y, después, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="0517d-149">To do this, when you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click **SQL Server Management Studio**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="0517d-150">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Ver** , haga clic en **Servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="0517d-150">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
3.  <span data-ttu-id="0517d-151">En el árbol de consola, busque la instancia en la que desea ver los archivos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="0517d-151">In the console tree, locate the instance on which you want to view the offline files.</span></span>  
  
4.  <span data-ttu-id="0517d-152">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0517d-152">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="0517d-153">Si la instancia está en **Grupos de servidor locales**, expanda **Grupos de servidor locales**, expanda el grupo de servidores (si la instancia pertenece a un grupo), haga clic con el botón derecho en la instancia y, después, haga clic en **Ver registro de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0517d-153">If the instance is under **Local Server Groups**, expand **Local Server Groups**, expand the server group (if the instance is a member of a group), right-click the instance, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="0517d-154">Si la instancia es el propio servidor de administración Central, expanda **Servidores de administración central**, haga clic con el botón derecho en la instancia, seleccione **Acciones del servidor de administración central**y, después, haga clic en **Ver registro de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0517d-154">If the instance is the Central Management Server itself, expand **Central Management Servers**, right-click the instance, point to **Central Management Server Actions**, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="0517d-155">Si la instancia está en **Servidores de administración central**, expanda **Servidores de administración central**, expanda el servidor de administración central, haga clic con el botón derecho en la instancia (o expanda un grupo de servidores y haga clic con el botón derecho en la instancia) y, después, haga clic en **Ver registro de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0517d-155">If the instance is under **Central Management Servers**, expand **Central Management Servers**, expand the Central Management Server, right-click the instance (or expand a server group and right-click the instance), and then click **View SQL Server Log**.</span></span>  
  
5.  <span data-ttu-id="0517d-156">Si se va a conectar a una instancia local, la conexión se realiza utilizando las credenciales de usuario actuales.</span><span class="sxs-lookup"><span data-stu-id="0517d-156">If you are connecting to a local instance, the connection is made using the current user credentials.</span></span>  
  
     <span data-ttu-id="0517d-157">Si se va a conectar a una instancia remota, en el cuadro de diálogo **Visor de archivos de registro - Conectar como** , realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0517d-157">If you are connecting to a remote instance, in the **Log File Viewer - Connect As** dialog box, do either of the following:</span></span>  
  
    -   <span data-ttu-id="0517d-158">Para conectarse como usuario actual, asegúrese de que la casilla **Conectar como otro usuario** está desactivada y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0517d-158">To connect as the current user, make sure that the **Connect as another user** check box is cleared, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="0517d-159">Para conectarse como otro usuario, active la casilla **Conectar como otro usuario** y, a continuación, haga clic en **Establecer usuario**.</span><span class="sxs-lookup"><span data-stu-id="0517d-159">To connect as another user, select the **Connect as another user** check box, and then click **Set User**.</span></span> <span data-ttu-id="0517d-160">Cuando se le pida, especifique las credenciales de usuario (con el nombre de usuario en el formato *nombre_dominio*\\*nombre_usuario*), haga clic en **Aceptar**y, después, de nuevo en **Aceptar** para conectarse.</span><span class="sxs-lookup"><span data-stu-id="0517d-160">When you are prompted, enter the user credentials (with the user name in the format *domain_name*\\*user_name*), click **OK**, and then click **OK** again to connect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0517d-161">Si los archivos de registro tardan demasiado en cargarse, puede hacer clic en **Detener** en la barra de herramientas del Visor del archivo de registros.</span><span class="sxs-lookup"><span data-stu-id="0517d-161">If the log files take too long to load, you can click **Stop** on the Log File Viewer toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0517d-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0517d-162">See Also</span></span>  
 [<span data-ttu-id="0517d-163">Visor de archivos de registro</span><span class="sxs-lookup"><span data-stu-id="0517d-163">Log File Viewer</span></span>](log-file-viewer.md)  
  
  
