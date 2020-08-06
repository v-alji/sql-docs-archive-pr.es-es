---
title: Configurar un servidor de informes para la administración remota | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- WMI provider [Reporting Services], remote configuration
- configuration management [WMI]
- report servers [Reporting Services], configuring
- remote server administration [Reporting Services]
ms.assetid: 8c7f145f-3ac2-4203-8cd6-2a4694395d09
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c34db5299fc1b82a7896a41519e55466c3b3b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674598"
---
# <a name="configure-a-report-server-for-remote-administration"></a><span data-ttu-id="ac902-102">Configurar un servidor de informes para la administración remota</span><span class="sxs-lookup"><span data-stu-id="ac902-102">Configure a Report Server for Remote Administration</span></span>
  <span data-ttu-id="ac902-103">En [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], puede configurar las instancias del servidor de informes local o remotamente.</span><span class="sxs-lookup"><span data-stu-id="ac902-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can configure report server instances locally or remotely.</span></span> <span data-ttu-id="ac902-104">Para configurar una instancia del servidor de informes remota, se puede utilizar la herramienta Configuración de Reporting Services o escribir código personalizado que utilice el proveedor de Instrumental de administración de Windows (WMI) de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac902-104">To configure a remote report server instance, you can use the Reporting Services Configuration tool or write custom code that uses the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider.</span></span> <span data-ttu-id="ac902-105">La herramienta de configuración de Reporting Services proporciona una interfaz gráfica para el proveedor WMI, de modo que se puede configurar un servidor de informes sin tener que escribir código.</span><span class="sxs-lookup"><span data-stu-id="ac902-105">The Reporting Services Configuration tool provides a graphical interface to the WMI provider so that you can configure a report server without having to write code.</span></span> <span data-ttu-id="ac902-106">Al iniciar la herramienta, se puede especificar el servidor remoto con el que se desea establecer la conexión.</span><span class="sxs-lookup"><span data-stu-id="ac902-106">When you start the tool, you can specify a remote server to connect to.</span></span>  
  
 <span data-ttu-id="ac902-107">Para poder utilizar la herramienta con el fin de configurar un servidor de informes remoto, debe seguir las instrucciones de este tema para habilitar los puertos en Firewall de Windows, habilitar las conexiones remotas y habilitar las solicitudes de WMI remotas.</span><span class="sxs-lookup"><span data-stu-id="ac902-107">Before you can use the tool to configure a remote report server, you must follow the instructions in this topic to enable ports in Windows Firewall, enable remote connections, and enable remote WMI requests.</span></span>  
  
 <span data-ttu-id="ac902-108">La configuración apropiada le ayuda a evitar el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac902-108">Proper configuration helps you avoid the following error:</span></span>  
  
 `The machine could not be found.`  
  
 `"The RPC server is unavailable. (Exception from HRESULT: 0x800706BA)".`  
  
## <a name="prerequisites"></a><span data-ttu-id="ac902-109">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="ac902-109">Prerequisites</span></span>  
 <span data-ttu-id="ac902-110">Para modificar la configuración del firewall, es necesario iniciar sesión de manera local y ser miembro del grupo local Administradores.</span><span class="sxs-lookup"><span data-stu-id="ac902-110">To modify firewall settings, you must be logged on locally and you must be a member of the local Administrators group.</span></span> <span data-ttu-id="ac902-111">No se puede modificar la configuración del firewall de Windows de un equipo remoto a través de una conexión remota.</span><span class="sxs-lookup"><span data-stu-id="ac902-111">You cannot modify the Windows firewall settings of a remote computer over a remote connection.</span></span>  
  
 <span data-ttu-id="ac902-112">Si se desea habilitar la administración remota para un usuario que no es administrador, es necesario conceder a la cuenta permisos para la activación remota del Modelo de objetos componentes distribuido (DCOM).</span><span class="sxs-lookup"><span data-stu-id="ac902-112">If you want to enable remote administration for a non-administrator user, you must grant the account Distributed Component Object Model (DCOM) Remote Activation permissions.</span></span> <span data-ttu-id="ac902-113">En este tema se ofrecen instrucciones para configurar el servidor para el acceso de usuarios que no son administradores.</span><span class="sxs-lookup"><span data-stu-id="ac902-113">Instructions for configuring the server for non-administrator access are provided in this topic.</span></span>  
  
 <span data-ttu-id="ac902-114">Algunas organizaciones tienen directivas de grupo que impiden la administración remota de servidores para algunos sistemas operativos o usuarios.</span><span class="sxs-lookup"><span data-stu-id="ac902-114">Some organizations have group policies that prevent remote server administration for certain operating systems or users.</span></span> <span data-ttu-id="ac902-115">Antes de modificar la configuración del firewall, pregunte al administrador de la red si existen restricciones en cuanto a la administración remota.</span><span class="sxs-lookup"><span data-stu-id="ac902-115">Before you begin modifying firewall settings, check with your network administrator to verify whether there are restrictions on remote administration.</span></span>  
  
 <span data-ttu-id="ac902-116">Para obtener más información, vea [Connecting Through Windows Firewall](https://go.microsoft.com/fwlink/?LinkId=63615) en la documentación de Plataform SDK en MSDN.</span><span class="sxs-lookup"><span data-stu-id="ac902-116">For more information, see [Connecting Through Windows Firewall](https://go.microsoft.com/fwlink/?LinkId=63615) in the Platform SDK documentation on MSDN.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="ac902-117">Tareas</span><span class="sxs-lookup"><span data-stu-id="ac902-117">Tasks</span></span>  
 <span data-ttu-id="ac902-118">Entre las tareas que habilitan la configuración del servidor de informes remoto figuran las siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac902-118">Tasks that enable remote report server configuration include the following:</span></span>  
  
-   <span data-ttu-id="ac902-119">Habilitar los puertos en Firewall de Windows para permitir solicitudes en los puertos que usa el servidor de informes y la instancia del Motor de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac902-119">Enable ports in Windows Firewall to allow requests on ports used by the report server and by the SQL Server Database Engine instance.</span></span>  
  
-   <span data-ttu-id="ac902-120">Habilitar las conexiones remotas a la instancia del Motor de base de datos que hospeda la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="ac902-120">Enable remote connections to the instance of the Database Engine instance that hosts the report server database.</span></span> <span data-ttu-id="ac902-121">La conexión remota es necesaria para configurar la conexión de la base de datos del servidor de informes y administrar las claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="ac902-121">A remote connection is necessary for configuring the report server database connection and managing the encryption keys.</span></span>  
  
-   <span data-ttu-id="ac902-122">Habilitar las solicitudes de WMI remotas para atravesar el Firewall de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="ac902-122">Enable remote WMI requests to pass through the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows firewall.</span></span>  
  
-   <span data-ttu-id="ac902-123">Si está configurando un servidor de informes remoto para que lo administre un usuario sin derechos administrativos, debe establecer los permisos DCOM para habilitar el acceso WMI remoto a una cuenta de usuario de Windows estándar.</span><span class="sxs-lookup"><span data-stu-id="ac902-123">If you are configuring a remote report server for administration by a non-administrative user, you must set DCOM permissions to enable remote WMI access to a standard Windows user account.</span></span> <span data-ttu-id="ac902-124">Debido a que WMI utiliza DCOM como transporte para las llamadas remotas, es necesario establecer los permisos de DCOM de manera que los usuarios que no inicien sesión como administrador local puedan configurar el servidor.</span><span class="sxs-lookup"><span data-stu-id="ac902-124">Because WMI uses DCOM as transport for remote calls, you must set the DCOM permissions so that users who are not logged on as the local administrator can configure the server.</span></span>  
  
-   <span data-ttu-id="ac902-125">Si está configurando un servidor de informes remoto para que lo administre un usuario sin derechos administrativos, también debe establecer los permisos WMI en el espacio de nombres WMI del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="ac902-125">If you are configuring a remote report server for administration by a non-administrative user, you must also set WMI permissions on the report server WMI namespace.</span></span> <span data-ttu-id="ac902-126">De manera predeterminada, todos los miembros del grupo local Administradores tienen acceso al espacio de nombres de WMI del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="ac902-126">By default, all members of the local Administrator group have access to the report server WMI namespace.</span></span> <span data-ttu-id="ac902-127">Si se desea conceder acceso a usuarios que no sean administradores, deben establecerse permisos.</span><span class="sxs-lookup"><span data-stu-id="ac902-127">If you want to grant access to non-administrators, you must set permissions.</span></span>  
  
 <span data-ttu-id="ac902-128">Las instrucciones para realizar estas tareas se proporcionan en este tema.</span><span class="sxs-lookup"><span data-stu-id="ac902-128">Instructions on how to perform these tasks are provided in this topic.</span></span>  
  
### <a name="to-open-ports-in-windows-firewall"></a><span data-ttu-id="ac902-129">Abrir puertos en Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="ac902-129">To open ports in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="ac902-130">[Configurar un firewall de Windows para el acceso a motor de base de datos](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span><span class="sxs-lookup"><span data-stu-id="ac902-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span></span>  
  
2.  <span data-ttu-id="ac902-131">[Configurar un firewall para el acceso al servidor de informes](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="ac902-131">[Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
### <a name="to-configure-remote-connections-to-the-report-server-database"></a><span data-ttu-id="ac902-132">Configurar las conexiones remotas a la base de datos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="ac902-132">To configure remote connections to the report server database</span></span>  
  
1.  <span data-ttu-id="ac902-133">Haga clic en **Inicio**, elija **Todos los programas**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Herramientas de configuración**y, finalmente, haga clic en **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ac902-133">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="ac902-134">En el panel izquierdo, expanda **Configuración de red de SQL Server**y, a continuación, haga clic en **Protocolos** para la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac902-134">In the left pane, expand **SQL Server Network Configuration**, and then click **Protocols** for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="ac902-135">En el panel de detalles, habilite los protocolos TCP/IP y Canalizaciones con nombre y, después, reinicie el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac902-135">In the details pane, enable the TCP/IP and Named Pipes protocols, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
### <a name="to-enable-remote-administration-in-windows-firewall"></a><span data-ttu-id="ac902-136">Para habilitar la administración remota en Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="ac902-136">To enable remote administration in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="ac902-137">Inicie sesión como administrador local en el equipo para el que desea habilitar la administración remota.</span><span class="sxs-lookup"><span data-stu-id="ac902-137">Log on as a local administrator to the computer for which you want to enable remote administration.</span></span>  
  
2.  <span data-ttu-id="ac902-138">Si el servidor de informes se ejecuta en Windows Vista, haga clic con el botón secundario en **símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="ac902-138">If the report server is running on Windows Vista, right-click **Command Prompt** and select **Run as administrator**.</span></span> <span data-ttu-id="ac902-139">En otros sistemas operativos, abra una ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="ac902-139">For other operating systems, open a command prompt window.</span></span>  
  
3.  <span data-ttu-id="ac902-140">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ac902-140">Run the following command:</span></span>  
  
    ```  
    netsh.exe firewall set service type=REMOTEADMIN mode=ENABLE scope=ALL  
    ```  
  
     <span data-ttu-id="ac902-141">Puede especificar varias opciones para Scope.</span><span class="sxs-lookup"><span data-stu-id="ac902-141">You can specify different options for Scope.</span></span> <span data-ttu-id="ac902-142">Para obtener más información, vea la documentación del producto Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="ac902-142">For more information, see the Windows Firewall product documentation.</span></span>  
  
4.  <span data-ttu-id="ac902-143">Compruebe que se ha habilitado la administración remota.</span><span class="sxs-lookup"><span data-stu-id="ac902-143">Verify that remote administration is enabled.</span></span> <span data-ttu-id="ac902-144">Puede ejecutar el comando siguiente para mostrar el estado:</span><span class="sxs-lookup"><span data-stu-id="ac902-144">You can run the following command to show the status:</span></span>  
  
    ```  
    netsh.exe firewall show state  
    ```  
  
5.  <span data-ttu-id="ac902-145">Reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="ac902-145">Reboot the computer.</span></span>  
  
### <a name="to-set-dcom-permissions-to-enable-remote-wmi-access-for-non-administrators"></a><span data-ttu-id="ac902-146">Para establecer permisos DCOM que habiliten el acceso remoto a WMI para usuarios que no son administradores</span><span class="sxs-lookup"><span data-stu-id="ac902-146">To set DCOM permissions to enable remote WMI access for non-administrators</span></span>  
  
1.  <span data-ttu-id="ac902-147">En el menú Inicio, seleccione **Herramientas administrativas**y haga clic en **Servicios de componente**.</span><span class="sxs-lookup"><span data-stu-id="ac902-147">On the Start menu, point to **Administrative Tools**, click **Component Services**.</span></span>  
  
     <span data-ttu-id="ac902-148">En Windows Vista, en el menú Inicio, haga clic en **todos los programas**, haga clic en **Ejecutar**y, a continuación, escriba `mmc comexp.msc` .</span><span class="sxs-lookup"><span data-stu-id="ac902-148">For Windows Vista, on the Start menu, click **All Programs**, click **Run**, and then enter `mmc comexp.msc`.</span></span>  
  
2.  <span data-ttu-id="ac902-149">Abra la carpeta Servicios de componente.</span><span class="sxs-lookup"><span data-stu-id="ac902-149">Open the Component Services folder.</span></span>  
  
3.  <span data-ttu-id="ac902-150">Abra la carpeta Equipos.</span><span class="sxs-lookup"><span data-stu-id="ac902-150">Open the Computers folder.</span></span>  
  
4.  <span data-ttu-id="ac902-151">Seleccione Mi PC.</span><span class="sxs-lookup"><span data-stu-id="ac902-151">Select My Computer.</span></span>  
  
5.  <span data-ttu-id="ac902-152">En el menú **Acción** , seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ac902-152">On the **Action** menu, and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="ac902-153">Haga clic en **Seguridad COM**.</span><span class="sxs-lookup"><span data-stu-id="ac902-153">Click **COM Security**.</span></span>  
  
7.  <span data-ttu-id="ac902-154">En **Permisos de inicio y activación**, haga clic en **Editar límites**.</span><span class="sxs-lookup"><span data-stu-id="ac902-154">In **Launch and Activation Permissions**, click **Edit Limits**.</span></span>  
  
8.  <span data-ttu-id="ac902-155">Si no aparece su nombre en **Permisos de inicio**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ac902-155">If you do not see your name in **Launch Permission**, click **Add**.</span></span>  
  
9. <span data-ttu-id="ac902-156">Escriba el nombre de su cuenta de usuario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ac902-156">Type the name of your user account, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="ac902-157">En \*\*permisos para \<User or Group> \*\*, en la columna **permitir** , seleccione **ejecución remota** y **activación remota**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ac902-157">In **Permissions for \<User or Group>**, in the **Allow** column, select **Remote Launch** and **Remote Activation**, and then click **OK**.</span></span>  
  
### <a name="to-set-permissions-on-the-report-server-wmi-namespace-for-non-administrators"></a><span data-ttu-id="ac902-158">Para establecer permisos para el espacio de nombres de WMI del servidor de informes para usuarios que no son administradores</span><span class="sxs-lookup"><span data-stu-id="ac902-158">To set permissions on the report server WMI namespace for non-administrators</span></span>  
  
1.  <span data-ttu-id="ac902-159">En el menú Inicio, seleccione **Herramientas administrativas** y haga clic en **Administración de equipos**.</span><span class="sxs-lookup"><span data-stu-id="ac902-159">On the Start menu, point to **Administrative Tools**, click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="ac902-160">Abra la carpeta Servicios y Aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ac902-160">Open the Services and Applications folder.</span></span>  
  
3.  <span data-ttu-id="ac902-161">Haga clic con el botón derecho en **Control WMI**y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ac902-161">Right-click **WMI Control**, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="ac902-162">Haga clic en **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="ac902-162">Click **Security**.</span></span>  
  
5.  <span data-ttu-id="ac902-163">Abra la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="ac902-163">Open the Root folder.</span></span>  
  
6.  <span data-ttu-id="ac902-164">Abra la carpeta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac902-164">Open the Microsoft folder.</span></span>  
  
7.  <span data-ttu-id="ac902-165">Abra la carpeta SQLServer.</span><span class="sxs-lookup"><span data-stu-id="ac902-165">Open the SQLServer folder.</span></span>  
  
8.  <span data-ttu-id="ac902-166">Abra la carpeta ReportServer.</span><span class="sxs-lookup"><span data-stu-id="ac902-166">Open the ReportServer folder.</span></span>  
  
9. <span data-ttu-id="ac902-167">Abra la carpeta de la instancia.</span><span class="sxs-lookup"><span data-stu-id="ac902-167">Open instance folder.</span></span> <span data-ttu-id="ac902-168">Si instaló la instancia predeterminada, la carpeta es MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="ac902-168">If you installed the default instance, the folder is MSSQLSERVER.</span></span>  
  
10. <span data-ttu-id="ac902-169">Abra la carpeta v10.</span><span class="sxs-lookup"><span data-stu-id="ac902-169">Open the v10 folder.</span></span>  
  
11. <span data-ttu-id="ac902-170">Seleccione la carpeta Admin y, a continuación, haga clic en **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="ac902-170">Select the Admin folder, and then click **Security**.</span></span>  
  
12. <span data-ttu-id="ac902-171">Haga clic en **Agregar**y, después, escriba la cuenta de usuario que se empleará para administrar el servidor.</span><span class="sxs-lookup"><span data-stu-id="ac902-171">Click **Add**, and then type the user account you will use to manage the server.</span></span>  
  
13. <span data-ttu-id="ac902-172">En la columna **Permitir** , seleccione **Habilitar cuenta**, **Llamada remota habilitada**y **Seguridad de lectura**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ac902-172">In the **Allow** column, select **Enable Account**, **Remote Enable**, and **Read Security**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac902-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac902-173">See Also</span></span>  
 [<span data-ttu-id="ac902-174">Administrador de configuración de Reporting Services &#40;modo nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="ac902-174">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
