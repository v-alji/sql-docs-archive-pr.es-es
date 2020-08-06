---
title: Referencia de la interfaz de usuario de Utilidad de ejecución de paquetes (DtExecUI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtexecui.general.f1
- sql12.dts.dtexecui.executionoptions.f1
- sql12.dts.dtexecui.configuration.f1
- sql12.dts.dtexecui.setvalues.f1
- sql12.dts.dtexecui.commandline.f1
- sql12.dts.dtexecui.commandfiles.f1
- sql12.dts.dtexecui.verification.f1
- sql12.dts.dtexecui.datasources.f1
- sql12.dts.dtexecui.reporting.f1
- sql12.dts.dtexecui.logging.f1
helpviewer_keywords:
- DTExecUI utility
ms.assetid: 3d71df39-126b-4c8e-bd77-128bbd5b0887
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 13601983a4ab841a2b64ff8e4fc722fcf5ae496c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674193"
---
# <a name="execute-package-utility-dtexecui-ui-reference"></a><span data-ttu-id="bcbbb-102">Referencia de la interfaz de usuario de la Utilidad de ejecución de paquetes (DtExecUI)</span><span class="sxs-lookup"><span data-stu-id="bcbbb-102">Execute Package Utility (DtExecUI) UI Reference</span></span>
  <span data-ttu-id="bcbbb-103">Use la **Utilidad de ejecución de paquetes** para ejecutar paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-103">Use the **Execute Package Utility** to run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="bcbbb-104">La utilidad ejecuta los paquetes almacenados en una de estas tres ubicaciones: la base de datos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el almacén de paquetes de [!INCLUDE[ssIS](../../includes/ssis-md.md)] y el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-104">The utility runs packages that are stored in one of three locations: [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store, and the file system.</span></span> <span data-ttu-id="bcbbb-105">Esta interfaz de usuario, que se puede abrir desde [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o escribiendo `dtexecui` en un símbolo del sistema, es una alternativa a la ejecución de paquetes mediante la herramienta del símbolo del sistema **DTExec** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-105">This user interface, which can be opened from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by typing `dtexecui` at a command prompt, is an alternative to running packages by using the **DTExec** command prompt tool.</span></span>  
  
 <span data-ttu-id="bcbbb-106">Los paquetes se ejecutan en el mismo proceso que la utilidad **dtexecui.exe** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-106">Packages execute in the same process as the **dtexecui.exe** utility.</span></span> <span data-ttu-id="bcbbb-107">Como esta utilidad es una herramienta de 32 bits, los paquetes que se ejecutan con **dtexecui.exe** en un entorno de 64 bits se ejecutan en Windows en Win32 (WOW).</span><span class="sxs-lookup"><span data-stu-id="bcbbb-107">Because this utility is a 32-bit tool, packages run by using **dtexecui.exe** in a 64-bit environment run in Windows on Win32 (WOW).</span></span> <span data-ttu-id="bcbbb-108">Al desarrollar y probar comandos mediante la utilidad dtexecui.exe en un equipo de 64 bits, debe probar los comandos en modo de 64 bits mediante la versión de 64 bits de **dtexecui.exe** antes de implementar o programar los comandos en un servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-108">When developing and testing commands by using the dtexecui.exe utility on a 64-bit computer, you should test the commands in 64-bit mode by using the 64-bit version of **dtexec.exe** before deploying or scheduling the commands on a production server.</span></span>  
  
 <span data-ttu-id="bcbbb-109">La **Utilidad de ejecución de paquetes** es una interfaz gráfica de usuario para la herramienta del símbolo del sistema **DTExec** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-109">The **Execute Package Utility** is a graphical user interface for the **DTExec** command prompt tool.</span></span> <span data-ttu-id="bcbbb-110">La interfaz de usuario permite configurar opciones de forma sencilla y reúne automáticamente la línea de comandos que se pasa a la herramienta del símbolo del sistema **DTExec** al ejecutar el paquete desde las opciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-110">The user interface makes it easy to configure options and it automatically assembles the command line that is passed to the **DTExec** command prompt tool when you run the package from the specified options.</span></span>  
  
 <span data-ttu-id="bcbbb-111">La **Utilidad de ejecución de paquetes** también se puede usar para reunir líneas de comandos que se usan al ejecutar **DTExec** directamente.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-111">The **Execute Package Utility** can also be used to assemble command lines that you use when running **DTExec** directly.</span></span>  
  
### <a name="to-open-execute-package-utility-in-sql-server-management-studio"></a><span data-ttu-id="bcbbb-112">Para abrir la Utilidad de ejecución de paquetes en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bcbbb-112">To open Execute Package Utility in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="bcbbb-113">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Ver** , haga clic en **Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="bcbbb-114">En el Explorador de objetos, haga clic en **Conectar**y, después, haga clic en **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-114">In Object Explorer, click **Connect**, and then click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="bcbbb-115">En el cuadro de diálogo **Conectar al servidor** , escriba el nombre de servidor en la lista **Nombre del servidor** y, después, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-115">In the **Connect to Server** dialog box, enter the server name in the **Server name** list, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="bcbbb-116">Expanda la carpeta **Paquetes almacenados**y sus subcarpetas, haga clic con el botón derecho en el paquete que quiera ejecutar y, después, haga clic en **Ejecutar paquete**.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-116">Expand the **Stored Package**s folder and subfolders, right-click the package you want to run, and then click **Run Package**.</span></span>  
  
### <a name="to-open-the-execute-package-utility-at-the-command-prompt"></a><span data-ttu-id="bcbbb-117">Para abrir la Utilidad de ejecución de paquetes en el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="bcbbb-117">To open the Execute Package Utility at the Command Prompt</span></span>  
  
-   <span data-ttu-id="bcbbb-118">En una ventana del símbolo del sistema, ejecute `dtexecui`.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-118">In a command prompt window, run `dtexecui`.</span></span>  
  
 <span data-ttu-id="bcbbb-119">En las siguientes secciones se describen las páginas del cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-119">The following sections describe pages of the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="general-page"></a><span data-ttu-id="bcbbb-120">Página General</span><span class="sxs-lookup"><span data-stu-id="bcbbb-120">General Page</span></span>  
 <span data-ttu-id="bcbbb-121">Use la página **General** del cuadro de diálogo **Utilidad de ejecución de paquetes** para especificar un nombre y una ubicación del paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-121">Use the **General** page of the **Execute Package Utility** dialog box to specify a package name and location.</span></span>  
  
 <span data-ttu-id="bcbbb-122">La Utilidad de ejecución de paquetes (dtexecui.exe) siempre ejecuta un paquete en el equipo local, aunque el paquete se guarde en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-122">The Execute Package utility (dtexecui.exe) always runs a package on the local computer, even if the package is saved on a remote server.</span></span> <span data-ttu-id="bcbbb-123">Si el paquete remoto usa archivos de configuración que también se guardan en el servidor remoto, es probable que la Utilidad de ejecución de paquetes no encuentre las configuraciones y que el paquete genere un error.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-123">If the remote package uses configuration files that also are saved on the remote server, then the Execute Package utility may not locate the configurations and the package fails.</span></span> <span data-ttu-id="bcbbb-124">Para impedir que esto suceda, se deben crear referencias a las configuraciones mediante el uso de un nombre compartido de la convención de nomenclatura universal (UNC) como \\\miservidor\miarchivo.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-124">To avoid this problem, the configurations must be referenced by using a Universal Naming Convention (UNC) share name like \\\myserver\myfile.</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="bcbbb-125">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="bcbbb-125">Static Options</span></span>  
 <span data-ttu-id="bcbbb-126">**Origen del paquete**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-126">**Package source**</span></span>  
 <span data-ttu-id="bcbbb-127">Especifique la ubicación del paquete que desea ejecutar, mediante las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="bcbbb-127">Specify the location of the package to run, using the following options:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bcbbb-128">Value</span><span class="sxs-lookup"><span data-stu-id="bcbbb-128">Value</span></span>|<span data-ttu-id="bcbbb-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcbbb-129">Description</span></span>|  
|<span data-ttu-id="bcbbb-130">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-130">**SQL Server**</span></span>|<span data-ttu-id="bcbbb-131">Seleccione esta opción si el paquete reside en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcbbb-131">Select this option when the package resides in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bcbbb-132">Especifique una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y proporcione un nombre de usuario y una contraseña para llevar a cabo la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-132">Specify an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and provide a user name and password for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="bcbbb-133">Cada nombre de usuario y contraseña agrega las opciones **/USER** _username_ y **/PASSWORD** _password_ al símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-133">Each user name and password adds the **/USER** _username_ and **/PASSWORD** _password_ options to the command prompt.</span></span>|  
|<span data-ttu-id="bcbbb-134">**Sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-134">**File system**</span></span>|<span data-ttu-id="bcbbb-135">Seleccione esta opción si el paquete reside en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-135">Select this option when the package resides in the file system.</span></span>|  
|<span data-ttu-id="bcbbb-136">**Almacén de paquetes SSIS**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-136">**SSIS Package Store**</span></span>|<span data-ttu-id="bcbbb-137">Seleccione esta opción si el paquete reside en el Almacén de paquetes [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-137">Select this option when the package resides in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span>|  
  
 <span data-ttu-id="bcbbb-138">Cada una de estas selecciones tiene el siguiente conjunto de opciones.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-138">Each of these selections has the following set of options.</span></span>  
  
 <span data-ttu-id="bcbbb-139">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-139">**Execute**</span></span>  
 <span data-ttu-id="bcbbb-140">Haga clic para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-140">Click to run the package.</span></span>  
  
 <span data-ttu-id="bcbbb-141">**Close**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-141">**Close**</span></span>  
 <span data-ttu-id="bcbbb-142">Haga clic en esta opción para cerrar el cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-142">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="bcbbb-143">Opciones dinámicas</span><span class="sxs-lookup"><span data-stu-id="bcbbb-143">Dynamic Options</span></span>  
  
#### <a name="package-source--sql-server"></a><span data-ttu-id="bcbbb-144">Origen del paquete = SQL Server</span><span class="sxs-lookup"><span data-stu-id="bcbbb-144">Package Source = SQL Server</span></span>  
 <span data-ttu-id="bcbbb-145">**Server**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-145">**Server**</span></span>  
 <span data-ttu-id="bcbbb-146">Escriba el nombre del servidor en el que reside el paquete o seleccione un servidor de la lista.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-146">Type the name of the server where the package resides, or select a server from the list.</span></span>  
  
 <span data-ttu-id="bcbbb-147">**Iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-147">**Log on to the server**</span></span>  
 <span data-ttu-id="bcbbb-148">Especifique si el paquete debe usar autenticación de Windows o autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcbbb-148">Specify whether the package should use Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bcbbb-149">Para obtener una mayor seguridad, es recomendable utilizar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-149">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="bcbbb-150">Si se utiliza la autenticación de Windows, no será necesario especificar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-150">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="bcbbb-151">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-151">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="bcbbb-152">Seleccione esta opción para usar la autenticación de Windows e iniciar sesión con una cuenta de usuario de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-152">Select this option to use Windows Authentication and log on using a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="bcbbb-153">**Utilizar autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-153">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="bcbbb-154">Elija esta opción para usar la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-154">Select this option to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="bcbbb-155">Cuando un usuario se conecta con un nombre y una contraseña de inicio de sesión determinados desde una conexión no de confianza, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] realiza la autenticación y comprueba si se ha configurado una cuenta de inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y si la contraseña especificada coincide con la almacenada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-155">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="bcbbb-156">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no encuentra la cuenta de inicio de sesión, la autenticación no se realizará correctamente y el usuario recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-156">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bcbbb-157">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-157">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="bcbbb-158">**Package**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-158">**Package**</span></span>  
 <span data-ttu-id="bcbbb-159">Escriba el nombre del paquete, o bien haga clic en el botón de puntos suspensivos **(…)** para buscar un paquete mediante el cuadro de diálogo **Seleccionar un paquete SSIS**.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-159">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
#### <a name="package-source--file-system"></a><span data-ttu-id="bcbbb-160">Origen del paquete = Sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="bcbbb-160">Package Source = File System</span></span>  
 <span data-ttu-id="bcbbb-161">**Package**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-161">**Package**</span></span>  
 <span data-ttu-id="bcbbb-162">Escriba el nombre del paquete, o bien haga clic en el botón de puntos suspensivos **(…)** para buscar un paquete mediante el cuadro de diálogo Abrir.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-162">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the Open dialog box.</span></span> <span data-ttu-id="bcbbb-163">De forma predeterminada, el cuadro de diálogo solamente muestra archivos con la extensión .dtsx.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-163">By default, the dialog box lists only files that have the .dtsx extension.</span></span>  
  
#### <a name="package-source--ssis-package-store"></a><span data-ttu-id="bcbbb-164">Origen del paquete = Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="bcbbb-164">Package Source = SSIS Package Store</span></span>  
 <span data-ttu-id="bcbbb-165">**Server**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-165">**Server**</span></span>  
 <span data-ttu-id="bcbbb-166">Escriba el nombre del equipo en el que reside el paquete o seleccione un equipo de la lista.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-166">Type the name of the computer where the package resides, or select a computer from the list.</span></span>  
  
 <span data-ttu-id="bcbbb-167">**Iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-167">**Log on to the server**</span></span>  
 <span data-ttu-id="bcbbb-168">Especifique si el paquete debe utilizar la autenticación de Microsoft Windows para conectarse al origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-168">Specify whether the package should use Microsoft Windows Authentication to connect to the package source.</span></span> <span data-ttu-id="bcbbb-169">Para obtener una mayor seguridad, es recomendable utilizar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-169">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="bcbbb-170">Si se utiliza la autenticación de Windows, no será necesario especificar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-170">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="bcbbb-171">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-171">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="bcbbb-172">Seleccione esta opción para utilizar la autenticación de Windows e iniciar sesión con una cuenta de usuario de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-172">Select this option to use Windows Authentication and log on using a Microsoft Windows user account.</span></span>  
  
 <span data-ttu-id="bcbbb-173">**Utilizar autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-173">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="bcbbb-174">Esta opción no está disponible si ejecuta un paquete almacenado en el **Almacén de paquetes SSIS**.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-174">This option is not available when you run a package stored in the **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="bcbbb-175">**Package**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-175">**Package**</span></span>  
 <span data-ttu-id="bcbbb-176">Escriba el nombre del paquete, o bien haga clic en el botón de puntos suspensivos **(…)** para buscar un paquete mediante el cuadro de diálogo **Seleccionar un paquete SSIS**.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-176">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
## <a name="configurations-page"></a><span data-ttu-id="bcbbb-177">Página Configuraciones</span><span class="sxs-lookup"><span data-stu-id="bcbbb-177">Configurations Page</span></span>  
 <span data-ttu-id="bcbbb-178">Use la página **Configuraciones** del cuadro de diálogo **Utilidad de ejecución de paquetes** para seleccionar los archivos de configuración que se van a cargar en tiempo de ejecución y especificar el orden de carga.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-178">Use the **Configurations** page of the **Execute Package Utility** dialog box to select the configuration files to load at run time, and to specify the order in which they load.</span></span>  
  
### <a name="options"></a><span data-ttu-id="bcbbb-179">Opciones</span><span class="sxs-lookup"><span data-stu-id="bcbbb-179">Options</span></span>  
 <span data-ttu-id="bcbbb-180">**Archivos de configuración**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-180">**Configuration files**</span></span>  
 <span data-ttu-id="bcbbb-181">Muestra una lista de las configuraciones que utiliza el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-181">Lists the configurations that the package uses.</span></span> <span data-ttu-id="bcbbb-182">Cada uno de los archivos de configuración agrega una opción **/CONFIGFILE nombreDeArchivo** al símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-182">Each configuration file adds a **/CONFIGFILE filename** option to the command prompt.</span></span>  
  
 <span data-ttu-id="bcbbb-183">**Teclas de dirección**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-183">**Arrow keys**</span></span>  
 <span data-ttu-id="bcbbb-184">Seleccione un archivo de configuración de la lista y utilice las flechas de dirección situadas a la derecha para cambiar el orden de carga.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-184">Select a configuration file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="bcbbb-185">Las configuraciones se cargan en orden comenzando desde la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-185">Configurations load in order starting from the top of the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bcbbb-186">Si varias configuraciones modifican la misma propiedad, se utiliza la configuración que se carga en último lugar.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-186">If multiple configurations modify the same property, the configuration that loads last is used.</span></span>  
  
 <span data-ttu-id="bcbbb-187">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-187">**Add**</span></span>  
 <span data-ttu-id="bcbbb-188">Haga clic para agregar configuraciones mediante el cuadro de diálogo **Abrir** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-188">Click to add configurations using the **Open** dialog box.</span></span> <span data-ttu-id="bcbbb-189">De manera predeterminada, el cuadro de diálogo muestra una lista de los archivos que tienen la extensión .dtsconfig.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-189">By default, the dialog box lists only files that have the .dtsconfig extension.</span></span>  
  
 <span data-ttu-id="bcbbb-190">**Remove**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-190">**Remove**</span></span>  
 <span data-ttu-id="bcbbb-191">Seleccione un archivo de configuración de la lista y, después, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-191">Select a configuration file in the list and then click **Remove**.</span></span>  
  
 <span data-ttu-id="bcbbb-192">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-192">**Execute**</span></span>  
 <span data-ttu-id="bcbbb-193">Haga clic para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-193">Click to run the package.</span></span>  
  
 <span data-ttu-id="bcbbb-194">**Close**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-194">**Close**</span></span>  
 <span data-ttu-id="bcbbb-195">Haga clic en esta opción para cerrar el cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-195">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-files-page"></a><span data-ttu-id="bcbbb-196">Página Archivos de comandos</span><span class="sxs-lookup"><span data-stu-id="bcbbb-196">Command Files Page</span></span>  
 <span data-ttu-id="bcbbb-197">Use la página **Archivos de comandos** del cuadro de diálogo **Utilidad de ejecución de paquetes** para seleccionar los archivos de comandos que quiere cargar en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-197">Use the **Command Files** page of the **Execute Package Utility** dialog box to select the command files to load at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="bcbbb-198">Opciones</span><span class="sxs-lookup"><span data-stu-id="bcbbb-198">Options</span></span>  
 <span data-ttu-id="bcbbb-199">**Archivos de comandos**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-199">**Command files**</span></span>  
 <span data-ttu-id="bcbbb-200">Muestra los archivos de comandos que utiliza el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-200">Lists the command files that the package uses.</span></span> <span data-ttu-id="bcbbb-201">Un paquete puede utilizar varios archivos para establecer las opciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-201">A package can use multiple files to set command-line options.</span></span>  
  
 <span data-ttu-id="bcbbb-202">**Teclas de dirección**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-202">**Arrow keys**</span></span>  
 <span data-ttu-id="bcbbb-203">Seleccione un archivo de comandos de la lista y utilice las teclas de dirección de la derecha para cambiar el orden de carga.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-203">Select a command file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="bcbbb-204">Los archivos de comandos se cargarán en orden, comenzando por la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-204">Command files load in order, starting from the top of the list.</span></span>  
  
 <span data-ttu-id="bcbbb-205">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-205">**Add**</span></span>  
 <span data-ttu-id="bcbbb-206">Haga clic para agregar un archivo de comandos mediante el cuadro de diálogo **Abrir** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-206">Click to add a command file, using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="bcbbb-207">**Remove**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-207">**Remove**</span></span>  
 <span data-ttu-id="bcbbb-208">Para quitar un archivo de comandos, selecciónelo en el cuadro de texto y haga clic en el botón **Quitar** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-208">Select a command file in the text box, and then remove it using the **Remove** button.</span></span>  
  
 <span data-ttu-id="bcbbb-209">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-209">**Execute**</span></span>  
 <span data-ttu-id="bcbbb-210">Haga clic para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-210">Click to run the package.</span></span>  
  
 <span data-ttu-id="bcbbb-211">**Close**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-211">**Close**</span></span>  
 <span data-ttu-id="bcbbb-212">Haga clic en esta opción para cerrar el cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-212">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="connection-managers-page"></a><span data-ttu-id="bcbbb-213">Página Administradores de conexión</span><span class="sxs-lookup"><span data-stu-id="bcbbb-213">Connection Managers Page</span></span>  
 <span data-ttu-id="bcbbb-214">Use la página **Administradores de conexiones** del cuadro de diálogo **Utilidad de ejecución de paquetes** para editar las cadenas de conexión de los administradores de conexión que el paquete usa.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-214">Use the **Connection Managers** page of the **Execute Package Utility** dialog box to edit the connection strings of the connection managers that the package uses.</span></span>  
  
### <a name="options"></a><span data-ttu-id="bcbbb-215">Opciones</span><span class="sxs-lookup"><span data-stu-id="bcbbb-215">Options</span></span>  
 <span data-ttu-id="bcbbb-216">**Connection Manager**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-216">**Connection Manager**</span></span>  
 <span data-ttu-id="bcbbb-217">Active esta casilla para que la columna **Cadena de conexión** se pueda editar.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-217">Select its check box to make the **Connection String** column editable.</span></span>  
  
 <span data-ttu-id="bcbbb-218">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-218">**Description**</span></span>  
 <span data-ttu-id="bcbbb-219">Vea una descripción de cada administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-219">View a description for each connection manager.</span></span> <span data-ttu-id="bcbbb-220">Las descripciones no se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-220">Descriptions cannot be edited.</span></span>  
  
 <span data-ttu-id="bcbbb-221">**Cadena de conexión**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-221">**Connection String**</span></span>  
 <span data-ttu-id="bcbbb-222">Edite la cadena de conexión para un administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-222">Edit the connection string for a connection manager.</span></span> <span data-ttu-id="bcbbb-223">Este campo solamente se puede editar si la casilla **Administrador de conexiones** está activada.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-223">This field is editable only when the **Connection Manager** check box is selected.</span></span>  
  
 <span data-ttu-id="bcbbb-224">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-224">**Execute**</span></span>  
 <span data-ttu-id="bcbbb-225">Haga clic para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-225">Click to run the package.</span></span>  
  
 <span data-ttu-id="bcbbb-226">**Close**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-226">**Close**</span></span>  
 <span data-ttu-id="bcbbb-227">Haga clic en esta opción para cerrar el cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-227">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="execution-options-page"></a><span data-ttu-id="bcbbb-228">Página Opciones de ejecución</span><span class="sxs-lookup"><span data-stu-id="bcbbb-228">Execution Options Page</span></span>  
 <span data-ttu-id="bcbbb-229">Use la página **Opciones de ejecución** del cuadro de diálogo **Utilidad de ejecución de paquetes** para especificar opciones de tiempo de ejecución para el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-229">Use the **Execution Options** page of the **Execute Package Utility** dialog box to specify run-time options for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="bcbbb-230">Opciones</span><span class="sxs-lookup"><span data-stu-id="bcbbb-230">Options</span></span>  
 <span data-ttu-id="bcbbb-231">**Rechazar el paquete cuando haya advertencias de validación**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-231">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="bcbbb-232">Indique si debe rechazarse el paquete cuando se produce una advertencia de validación.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-232">Indicate whether the package fails if a validation warning occurs.</span></span>  
  
 <span data-ttu-id="bcbbb-233">**Validar el paquete sin ejecutarlo**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-233">**Validate package without executing**</span></span>  
 <span data-ttu-id="bcbbb-234">Indique si el paquete solo debe validarse.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-234">Indicate whether the package is validated only.</span></span>  
  
 <span data-ttu-id="bcbbb-235">**Número máximo de ejecutables simultáneos**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-235">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="bcbbb-236">Indica si desea especificar el número máximo de ejecutables que pueden ejecutarse en el paquete al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-236">Indicate whether you want to specify the maximum number of executables that can run in the package at the same time.</span></span> <span data-ttu-id="bcbbb-237">Después de activar esta casilla, utilice el cuadro de número para especificar el número máximo de ejecutables.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-237">After you select this check box, use the spin box to specify the maximum number of executables.</span></span>  
  
 <span data-ttu-id="bcbbb-238">**Habilitar puntos de comprobación de paquetes**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-238">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="bcbbb-239">Indique si deben habilitarse los puntos de comprobación de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-239">Indicate whether to enable package checkpoints.</span></span>  
  
 <span data-ttu-id="bcbbb-240">**Archivo de punto de comprobación**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-240">**Checkpoint file**</span></span>  
 <span data-ttu-id="bcbbb-241">Indique el archivo de punto de comprobación que utiliza el paquete si se han habilitado los puntos de comprobación de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-241">List the checkpoint file the package uses, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="bcbbb-242">**Browse**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-242">**Browse**</span></span>  
 <span data-ttu-id="bcbbb-243">Haga clic en el botón Examinar **(…)** para buscar el archivo de punto de control mediante el cuadro de diálogo **Abrir** si ha habilitado los puntos de control de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-243">Click the browse button **(...)** to locate the checkpoint file using the **Open** dialog box, if you enable package checkpoints.</span></span> <span data-ttu-id="bcbbb-244">Si ya se ha especificado un punto de comprobación, se sustituye por el archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-244">If a checkpoint file is already specified, it is replaced by the selected file.</span></span>  
  
 <span data-ttu-id="bcbbb-245">**Omitir opciones de reinicio**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-245">**Override restart options**</span></span>  
 <span data-ttu-id="bcbbb-246">Indique si deben reemplazarse las opciones de reinicio si se habilitan los puntos de comprobación de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-246">Indicate whether to override restart options, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="bcbbb-247">**Opción de reinicio**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-247">**Restart option**</span></span>  
 <span data-ttu-id="bcbbb-248">Seleccione cómo deben utilizarse los puntos de comprobación si se reemplazan las opciones de reinicio.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-248">Select how to use checkpoints, if you override restart options.</span></span>  
  
 <span data-ttu-id="bcbbb-249">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-249">**Execute**</span></span>  
 <span data-ttu-id="bcbbb-250">Haga clic para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-250">Click to run the package.</span></span>  
  
 <span data-ttu-id="bcbbb-251">**Close**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-251">**Close**</span></span>  
 <span data-ttu-id="bcbbb-252">Haga clic en esta opción para cerrar el cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-252">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="reporting-page"></a><span data-ttu-id="bcbbb-253">Página de informe</span><span class="sxs-lookup"><span data-stu-id="bcbbb-253">Reporting Page</span></span>  
 <span data-ttu-id="bcbbb-254">Use la página **Informes** del cuadro de diálogo **Utilidad de ejecución de paquetes** para especificar los eventos y la información sobre el paquete que se registrará en la consola cuando se ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-254">Use the **Reporting** page of the **Execute Package Utility** dialog box to specify the events and information about the package to log to the console when the package runs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="bcbbb-255">Opciones</span><span class="sxs-lookup"><span data-stu-id="bcbbb-255">Options</span></span>  
 <span data-ttu-id="bcbbb-256">**Eventos de consola**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-256">**Console events**</span></span>  
 <span data-ttu-id="bcbbb-257">Indica los eventos y los tipos de mensajes que se notificarán.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-257">Indicate the events and types of messages to report.</span></span>  
  
 <span data-ttu-id="bcbbb-258">**None**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-258">**None**</span></span>  
 <span data-ttu-id="bcbbb-259">Seleccione esta opción para no obtener elaborar ningún informe.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-259">Select for no reporting.</span></span>  
  
 <span data-ttu-id="bcbbb-260">**Errores**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-260">**Errors**</span></span>  
 <span data-ttu-id="bcbbb-261">Seleccione esta opción para notificar mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-261">Select to report error messages.</span></span>  
  
 <span data-ttu-id="bcbbb-262">**Advertencias**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-262">**Warnings**</span></span>  
 <span data-ttu-id="bcbbb-263">Seleccione esta opción para notificar mensajes de advertencia.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-263">Select to report warning messages.</span></span>  
  
 <span data-ttu-id="bcbbb-264">**Eventos personalizados**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-264">**Custom Events**</span></span>  
 <span data-ttu-id="bcbbb-265">Seleccione esta opción para notificar mensajes de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-265">Select to report custom event messages.</span></span>  
  
 <span data-ttu-id="bcbbb-266">**Eventos de canalización**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-266">**Pipeline Events**</span></span>  
 <span data-ttu-id="bcbbb-267">Seleccione esta opción notificar mensajes de eventos de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-267">Select to report data flow events messages.</span></span>  
  
 <span data-ttu-id="bcbbb-268">**Información**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-268">**Information**</span></span>  
 <span data-ttu-id="bcbbb-269">Seleccione esta opción para notificar mensajes informativos.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-269">Select to report information messages.</span></span>  
  
 <span data-ttu-id="bcbbb-270">**Detallado**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-270">**Verbose**</span></span>  
 <span data-ttu-id="bcbbb-271">Seleccione esta opción para utilizar informes detallados.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-271">Select to use verbose reporting.</span></span>  
  
 <span data-ttu-id="bcbbb-272">**Registro de consolas**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-272">**Console logging**</span></span>  
 <span data-ttu-id="bcbbb-273">Especifique la información que desea escribir en el registro cuando se produzca el evento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-273">Specify the information that you want written to the log when the selected event occurs.</span></span>  
  
 <span data-ttu-id="bcbbb-274">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-274">**Name**</span></span>  
 <span data-ttu-id="bcbbb-275">Seleccione esta opción para notificar el nombre de la persona que creó el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-275">Select to report the name of the person who created the package.</span></span>  
  
 <span data-ttu-id="bcbbb-276">**Equipo**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-276">**Computer**</span></span>  
 <span data-ttu-id="bcbbb-277">Seleccione esta opción para notificar el nombre del equipo donde se está ejecutando el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-277">Select to report the name of the computer the package is running on.</span></span>  
  
 <span data-ttu-id="bcbbb-278">**Operador**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-278">**Operator**</span></span>  
 <span data-ttu-id="bcbbb-279">Seleccione esta opción para notificar el nombre de la persona que inició el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-279">Select to report the name of the person who started the package.</span></span>  
  
 <span data-ttu-id="bcbbb-280">**Nombre de origen**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-280">**Source name**</span></span>  
 <span data-ttu-id="bcbbb-281">Seleccione esta opción para notificar el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-281">Select to report the package name.</span></span>  
  
 <span data-ttu-id="bcbbb-282">**GUID de origen**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-282">**Source GUID**</span></span>  
 <span data-ttu-id="bcbbb-283">Seleccione esta opción para notificar el GUID del paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-283">Select to report the package GUID.</span></span>  
  
 <span data-ttu-id="bcbbb-284">**GUID de ejecución**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-284">**Execution GUID**</span></span>  
 <span data-ttu-id="bcbbb-285">Seleccione esta opción para notificar el GUID de la instancia de ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-285">Select to report the GUID of the package execution instance.</span></span>  
  
 <span data-ttu-id="bcbbb-286">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-286">**Message**</span></span>  
 <span data-ttu-id="bcbbb-287">Seleccione esta opción para notificar mensajes.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-287">Select to report messages.</span></span>  
  
 <span data-ttu-id="bcbbb-288">**Hora de inicio y finalización**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-288">**Start time and end time**</span></span>  
 <span data-ttu-id="bcbbb-289">Seleccione esta opción para notificar cuándo el paquete comienza y termina.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-289">Select to report when the package began and finished.</span></span>  
  
 <span data-ttu-id="bcbbb-290">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-290">**Execute**</span></span>  
 <span data-ttu-id="bcbbb-291">Haga clic para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-291">Click to run the package.</span></span>  
  
 <span data-ttu-id="bcbbb-292">**Close**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-292">**Close**</span></span>  
 <span data-ttu-id="bcbbb-293">Haga clic en esta opción para cerrar el cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-293">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="logging-page"></a><span data-ttu-id="bcbbb-294">Página Registro</span><span class="sxs-lookup"><span data-stu-id="bcbbb-294">Logging Page</span></span>  
 <span data-ttu-id="bcbbb-295">Use la página **Registro** del cuadro de diálogo **Utilidad de ejecución de paquetes** para que los proveedores de registro estén disponibles para el paquete en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-295">Use the **Logging** page of the **Execute Package Utility** dialog box to make log providers available to the package at run time.</span></span> <span data-ttu-id="bcbbb-296">Seleccione el tipo de proveedor de registro del paquete y la cadena de conexión para la conexión al registro.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-296">Provide the package log provider type and the connection string for connecting to the log.</span></span> <span data-ttu-id="bcbbb-297">Cada entrada de los proveedores de registro agrega una opción **/LOGGER**_classid_ al símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-297">Each log provider entry adds a **/LOGGER**_classid_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="bcbbb-298">Opciones</span><span class="sxs-lookup"><span data-stu-id="bcbbb-298">Options</span></span>  
 <span data-ttu-id="bcbbb-299">**Proveedor de registro**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-299">**Log Provider**</span></span>  
 <span data-ttu-id="bcbbb-300">Seleccione un proveedor de registro de la lista.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-300">Select a log provider from the list.</span></span>  
  
 <span data-ttu-id="bcbbb-301">**Cadena de configuración**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-301">**Configuration String**</span></span>  
 <span data-ttu-id="bcbbb-302">Seleccione el nombre del administrador de conexiones del paquete que señala la ubicación del registro o escriba la cadena de conexión para la conexión al proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-302">Select the name of the connection manager from the package that points to the log location, or type the connection string for connecting to the log provider.</span></span>  
  
 <span data-ttu-id="bcbbb-303">**Remove**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-303">**Remove**</span></span>  
 <span data-ttu-id="bcbbb-304">Seleccione un proveedor de registro y haga clic para quitarlo.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-304">Select a log provider and click to remove it.</span></span>  
  
 <span data-ttu-id="bcbbb-305">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-305">**Execute**</span></span>  
 <span data-ttu-id="bcbbb-306">Haga clic para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-306">Click to run the package.</span></span>  
  
 <span data-ttu-id="bcbbb-307">**Close**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-307">**Close**</span></span>  
 <span data-ttu-id="bcbbb-308">Haga clic en esta opción para cerrar el cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-308">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="set-values-page"></a><span data-ttu-id="bcbbb-309">Página Valores establecidos</span><span class="sxs-lookup"><span data-stu-id="bcbbb-309">Set Values Page</span></span>  
 <span data-ttu-id="bcbbb-310">Use la página **Valores establecidos** del cuadro de diálogo **Utilidad de ejecución de paquetes** para establecer los valores de las propiedades de paquetes, ejecutables, conexiones, variables y proveedores de registro escribiendo las rutas de acceso de las propiedades y los valores de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-310">Use the **Set Values** page of the **Execute Package Utility** dialog box to set the property values of packages, executables, connections, variables, and log providers by typing the paths of properties and the property values.</span></span> <span data-ttu-id="bcbbb-311">Cada entrada de ruta agrega una opción **/SET**_propertypath;value_ al símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-311">Each path entry adds a **/SET**_propertypath;value_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="bcbbb-312">Opciones</span><span class="sxs-lookup"><span data-stu-id="bcbbb-312">Options</span></span>  
 <span data-ttu-id="bcbbb-313">**Ruta de acceso de la propiedad**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-313">**Property Path**</span></span>  
 <span data-ttu-id="bcbbb-314">Escriba la ruta de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-314">Type the path of the property.</span></span> <span data-ttu-id="bcbbb-315">En la sintaxis de la ruta se usa una barra diagonal inversa (\\) para indicar que el elemento siguiente es un contenedor, un punto (.) para indicar que el elemento siguiente es una propiedad y corchetes para indicar que es un miembro de una colección.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-315">The path syntax uses a backslash (\\) to indicate that the following item is a container, the period (.) to indicate the following item is a property, and brackets to indicate a collection member.</span></span> <span data-ttu-id="bcbbb-316">Es posible identificar al miembro por su índice o nombre.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-316">The member can be identified by its index or its name.</span></span> <span data-ttu-id="bcbbb-317">Por ejemplo, la ruta de acceso de la propiedad de una variable de un paquete es \Package.Variables[MyVariable].Value.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-317">For example, the property path of a package variable is \Package.Variables[MyVariable].Value.</span></span>  
  
 <span data-ttu-id="bcbbb-318">**Valor**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-318">**Value**</span></span>  
 <span data-ttu-id="bcbbb-319">Escriba el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-319">Type the value of the property.</span></span>  
  
 <span data-ttu-id="bcbbb-320">**Remove**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-320">**Remove**</span></span>  
 <span data-ttu-id="bcbbb-321">Seleccione una ruta de acceso a una propiedad y haga clic para quitarla.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-321">Select a property path and click to remove it.</span></span>  
  
 <span data-ttu-id="bcbbb-322">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-322">**Execute**</span></span>  
 <span data-ttu-id="bcbbb-323">Haga clic para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-323">Click to run the package.</span></span>  
  
 <span data-ttu-id="bcbbb-324">**Close**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-324">**Close**</span></span>  
 <span data-ttu-id="bcbbb-325">Haga clic en esta opción para cerrar el cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-325">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="verification-page"></a><span data-ttu-id="bcbbb-326">Página Comprobación</span><span class="sxs-lookup"><span data-stu-id="bcbbb-326">Verification Page</span></span>  
 <span data-ttu-id="bcbbb-327">Use la página **Comprobación** del cuadro de diálogo **Ejecutar paquete** para establecer los criterios para comprobar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-327">Use the **Verification** page of the **Execute Package** dialog box to set criteria for verifying the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="bcbbb-328">Opciones</span><span class="sxs-lookup"><span data-stu-id="bcbbb-328">Options</span></span>  
 <span data-ttu-id="bcbbb-329">**Ejecutar solo los paquetes firmados**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-329">**Execute only signed packages**</span></span>  
 <span data-ttu-id="bcbbb-330">Seleccione esta opción para ejecutar solamente los paquetes que se han firmado.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-330">Select to execute only packages that have been signed.</span></span>  
  
 <span data-ttu-id="bcbbb-331">**Comprobar la generación del paquete**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-331">**Verify package build**</span></span>  
 <span data-ttu-id="bcbbb-332">Seleccione esta opción para comprobar la generación del paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-332">Select to verify the package build.</span></span>  
  
 <span data-ttu-id="bcbbb-333">Build</span><span class="sxs-lookup"><span data-stu-id="bcbbb-333">Build</span></span>  
 <span data-ttu-id="bcbbb-334">Especifique el número secuencial de versión asociado a la compilación.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-334">Specify the sequential Build number associated with the build.</span></span>  
  
 <span data-ttu-id="bcbbb-335">**Comprobar el Id. del paquete**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-335">**Verify package ID**</span></span>  
 <span data-ttu-id="bcbbb-336">Seleccione esta opción para comprobar el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-336">Select to verify the package ID.</span></span>  
  
 <span data-ttu-id="bcbbb-337">Id. de paquete</span><span class="sxs-lookup"><span data-stu-id="bcbbb-337">Package ID</span></span>  
 <span data-ttu-id="bcbbb-338">Especifique el número de identificación del paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-338">Specify the package identification number.</span></span>  
  
 <span data-ttu-id="bcbbb-339">**Comprobar el Id. de versión**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-339">**Verify version ID**</span></span>  
 <span data-ttu-id="bcbbb-340">Seleccione esta opción para comprobar el identificador de la versión.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-340">Select to verify the version ID.</span></span>  
  
 <span data-ttu-id="bcbbb-341">Id. de la versión</span><span class="sxs-lookup"><span data-stu-id="bcbbb-341">Version ID</span></span>  
 <span data-ttu-id="bcbbb-342">Especifique el número de identificación de la versión.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-342">Specify the version identification number.</span></span>  
  
 <span data-ttu-id="bcbbb-343">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-343">**Execute**</span></span>  
 <span data-ttu-id="bcbbb-344">Haga clic para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-344">Click to run the package.</span></span>  
  
 <span data-ttu-id="bcbbb-345">**Close**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-345">**Close**</span></span>  
 <span data-ttu-id="bcbbb-346">Haga clic en esta opción para cerrar el cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-346">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-line-page"></a><span data-ttu-id="bcbbb-347">Página Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="bcbbb-347">Command Line Page</span></span>  
 <span data-ttu-id="bcbbb-348">Use el nodo **Línea de comandos** del cuadro de diálogo **Utilidad de ejecución de paquetes** para editar la línea de comandos generada con las opciones creadas en los diversos cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-348">Use the **Command Line** node of the **Execute Package Utility** dialog box to edit the command line that has been generated by the options created by the various dialogs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="bcbbb-349">Opciones</span><span class="sxs-lookup"><span data-stu-id="bcbbb-349">Options</span></span>  
 <span data-ttu-id="bcbbb-350">**Restaurar las opciones originales**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-350">**Restore the original options**</span></span>  
 <span data-ttu-id="bcbbb-351">Haga clic para restaurar el estado original de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-351">Click to restore the command line to its original state.</span></span> <span data-ttu-id="bcbbb-352">Use esta opción si ha realizado modificaciones con la opción **Editar la línea de comandos manualmente** y quiere restaurar las opciones originales de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-352">Use this option if you have made modifications using the **Edit the command line manually** option and want to restore the original command-line options.</span></span>  
  
 <span data-ttu-id="bcbbb-353">**Editar la línea de comandos manualmente**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-353">**Edit the command line manually**</span></span>  
 <span data-ttu-id="bcbbb-354">Haga clic para editar la línea de comandos en el cuadro de texto **Línea de comandos** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-354">Click to edit the command line in the **Command line** text box.</span></span>  
  
 <span data-ttu-id="bcbbb-355">**Línea de comandos**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-355">**Command line**</span></span>  
 <span data-ttu-id="bcbbb-356">Muestra la línea de comandos actual.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-356">Displays the current command line.</span></span> <span data-ttu-id="bcbbb-357">Podrá editarla si ha seleccionado la opción para editar la línea de comandos manualmente.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-357">Editable if you selected the option to edit the command line manually.</span></span>  
  
 <span data-ttu-id="bcbbb-358">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-358">**Execute**</span></span>  
 <span data-ttu-id="bcbbb-359">Haga clic para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bcbbb-359">Click to run the package.</span></span>  
  
 <span data-ttu-id="bcbbb-360">**Close**</span><span class="sxs-lookup"><span data-stu-id="bcbbb-360">**Close**</span></span>  
 <span data-ttu-id="bcbbb-361">Haga clic en esta opción para cerrar el cuadro de diálogo **Utilidad de ejecución de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="bcbbb-361">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbbb-362">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bcbbb-362">See Also</span></span>  
 [<span data-ttu-id="bcbbb-363">dtexec (utilidad)</span><span class="sxs-lookup"><span data-stu-id="bcbbb-363">dtexec Utility</span></span>](dtexec-utility.md)  
  
  
