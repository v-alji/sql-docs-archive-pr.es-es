---
title: Instale PowerPivot desde el símbolo del sistema | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7f1f2b28-c9f5-49ad-934b-02f2fa6b9328
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 54f30142cdc2e39b3ec565d4f965fdad675405e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676820"
---
# <a name="install-powerpivot-from-the-command-prompt"></a><span data-ttu-id="de4f4-102">Instalar PowerPivot desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="de4f4-102">Install PowerPivot from the Command Prompt</span></span>
  <span data-ttu-id="de4f4-103">Puede ejecutar el programa de instalación desde la línea de comandos para instalar SQL Server PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de4f4-103">You can run Setup from the command line to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="de4f4-104">Debe incluir el parámetro `/ROLE` en el comando y excluir el parámetro `/FEATURES`.</span><span class="sxs-lookup"><span data-stu-id="de4f4-104">You must include the `/ROLE` parameter in your command and exclude the `/FEATURES` parameter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="de4f4-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="de4f4-105">Prerequisites</span></span>  
 <span data-ttu-id="de4f4-106">Debe estar instalada la versión Enterprise de SharePoint Server 2010 con Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="de4f4-106">SharePoint Server 2010 enterprise edition with Service Pack 1 (SP1) must be installed.</span></span>  
  
 <span data-ttu-id="de4f4-107">Debe utilizar las cuentas de dominio para aprovisionar a Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="de4f4-107">You must use domain accounts to provision Analysis Services.</span></span>  
  
 <span data-ttu-id="de4f4-108">El equipo debe estar unido al mismo dominio que la granja de servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de4f4-108">The computer must be joined to the same domain as the SharePoint farm.</span></span>  
  
##  <a name="role-based-installation-options"></a><a name="Commands"></a><span data-ttu-id="de4f4-109">Opciones de instalación basadas en/ROLE</span><span class="sxs-lookup"><span data-stu-id="de4f4-109">/ROLE based installation options</span></span>  
 <span data-ttu-id="de4f4-110">En las implementaciones de PowerPivot para SharePoint, se utiliza el parámetro `/ROLE` en lugar de `/FEATURES`.</span><span class="sxs-lookup"><span data-stu-id="de4f4-110">For PowerPivot for SharePoint deployments, the `/ROLE` parameter is used in place of the `/FEATURES` parameter.</span></span> <span data-ttu-id="de4f4-111">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="de4f4-111">Valid values include:</span></span>  
  
-   `SPI_AS_ExistingFarm`  
  
-   `SPI_AS_NewFarm`  
  
 <span data-ttu-id="de4f4-112">Ambos roles instalan los archivos de aplicación, configuración e implementación que permiten que PowerPivot para SharePoint se ejecute en una granja de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de4f4-112">Both roles install application, configuration, and deployment files that enable a PowerPivot for SharePoint to run in a SharePoint farm.</span></span> <span data-ttu-id="de4f4-113">Si se especifica uno de los dos roles, el programa de instalación comprobará los requisitos de hardware y software necesarios para la integración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de4f4-113">Specifying either role will cause Setup to check for hardware and software requirements necessary for SharePoint integration.</span></span>  
  
 <span data-ttu-id="de4f4-114">La opción de granja existente supone que ya hay una granja de servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de4f4-114">The existing farm option assumes that a SharePoint farm is already in place.</span></span> <span data-ttu-id="de4f4-115">La nueva opción de granja supone que creará una nueva granja de servidores; admite la adición de una instancia de Motor de base de datos en la sintaxis de la línea de comandos para que pueda usar la instancia de Motor de base de datos como servidor de bases de datos de la granja.</span><span class="sxs-lookup"><span data-stu-id="de4f4-115">The new farm option assumes that you will create a new farm; it supports the addition of a Database Engine instance in the command line syntax so that you can use the Database Engine instance as the farm's database server.</span></span>  
  
 <span data-ttu-id="de4f4-116">A diferencia de las versiones anteriores, todas las tareas de configuración del servidor se realizan como tareas posteriores a la instalación.</span><span class="sxs-lookup"><span data-stu-id="de4f4-116">In contrast with the previous releases, all server configuration tasks are performed as post-installation tasks.</span></span> <span data-ttu-id="de4f4-117">Si está automatizando los pasos de instalación y configuración, puede utilizar PowerShell para configurar el servidor.</span><span class="sxs-lookup"><span data-stu-id="de4f4-117">If you are automating installation and configuration steps, you can use PowerShell to configure the server.</span></span> <span data-ttu-id="de4f4-118">Para obtener más información, vea [configuración de PowerPivot mediante Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="de4f4-118">For more information, see [PowerPivot Configuration using Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span></span>  
  
## <a name="example-commands"></a><span data-ttu-id="de4f4-119">Comandos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="de4f4-119">Example Commands</span></span>  
 <span data-ttu-id="de4f4-120">Los siguientes ejemplos ilustran el uso de cada opción.</span><span class="sxs-lookup"><span data-stu-id="de4f4-120">The following examples illustrate the usage of each option.</span></span> <span data-ttu-id="de4f4-121">En el ejemplo 1 se muestra `SPI_AS_ExistingFarm` .</span><span class="sxs-lookup"><span data-stu-id="de4f4-121">Example 1 shows `SPI_AS_ExistingFarm`.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="de4f4-122">El ejemplo 2 muestra `SPI_AS_NewFarm`.</span><span class="sxs-lookup"><span data-stu-id="de4f4-122">Example 2 shows `SPI_AS_NewFarm`.</span></span> <span data-ttu-id="de4f4-123">Observe que incluye los parámetros para aprovisionar al Motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="de4f4-123">Notice that it includes parameters for provisioning the Database Engine.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_NewFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/SQLSVCACCOUNT=<DomainName\UserName> /SQLSVCPASSWORD=<StrongPassword> /SQLSYSADMINACCOUNTS=<DomainName\UserName> /AGTSVCACCOUNT=<DomainName\UserName> /AGTSVCPASSWORD=<StrongPassword> /ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
##  <a name="modifying-the-command-syntax"></a><a name="Join"></a><span data-ttu-id="de4f4-124">Modificar la sintaxis de los comandos</span><span class="sxs-lookup"><span data-stu-id="de4f4-124">Modifying the command syntax</span></span>  
 <span data-ttu-id="de4f4-125">Utilice los siguientes pasos para modificar la sintaxis del comando del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="de4f4-125">Use the following steps to modify the example command syntax.</span></span>  
  
1.  <span data-ttu-id="de4f4-126">Copie el siguiente comando en el Bloc de notas:</span><span class="sxs-lookup"><span data-stu-id="de4f4-126">Copy the following command into Notepad:</span></span>  
  
    ```cmd
    Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
    ```  
  
     <span data-ttu-id="de4f4-127">El parámetro `/q` ejecuta el programa de instalación en modo silencio, que suprime la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="de4f4-127">The `/q` parameter runs Setup in quiet mode, which suppresses the user interface.</span></span>  
  
     <span data-ttu-id="de4f4-128">`/IAcceptSQLServerLicenseTerms` es necesario cuando se especifican los parámetros `/q` o `/qs` para instalaciones desatendidas.</span><span class="sxs-lookup"><span data-stu-id="de4f4-128">The `/IAcceptSQLServerLicenseTerms` is required when the `/q` or `/qs` parameter is specified for un-attended installations.</span></span>  
  
     <span data-ttu-id="de4f4-129">El parámetro `/action` indica al programa de instalación que realice una instalación.</span><span class="sxs-lookup"><span data-stu-id="de4f4-129">The `/action` parameter instructs Setup to perform an installation.</span></span>  
  
     <span data-ttu-id="de4f4-130">El parámetro `/role` indica al programa de instalación que instale el programa de Analysis Services y los archivos de configuración necesarios para PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de4f4-130">The `/role` parameter instructs Setup to install the Analysis Services program and configuration files required for PowerPivot for SharePoint.</span></span> <span data-ttu-id="de4f4-131">Este rol también detecta y utiliza la información de conectividad de granja existente para tener acceso a la base de datos de configuración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de4f4-131">This role also detects and uses the existing farm connectivity information to access the SharePoint configuration database.</span></span> <span data-ttu-id="de4f4-132">Este parámetro es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="de4f4-132">This parameter is required.</span></span> <span data-ttu-id="de4f4-133">Úselo en lugar del parámetro `/features` para especificar qué componentes se deben instalar.</span><span class="sxs-lookup"><span data-stu-id="de4f4-133">Use it instead of the `/features` parameter to specify the components to install.</span></span>  
  
     <span data-ttu-id="de4f4-134">El parámetro `/instancename` especifica 'PowerPivot' como una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="de4f4-134">The `/instancename` parameter specifies 'PowerPivot' as a named instance.</span></span> <span data-ttu-id="de4f4-135">Este valor está codificado de forma rígida y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="de4f4-135">This value is hard-coded and cannot be changed.</span></span> <span data-ttu-id="de4f4-136">Se especifica en el comando únicamente para que sepa cómo se instala el servicio.</span><span class="sxs-lookup"><span data-stu-id="de4f4-136">It is specified in the command for educational purposes so that you know how the service is installed.</span></span>  
  
     <span data-ttu-id="de4f4-137">El parámetro `/indicateprogress` le permite supervisar el progreso en la ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="de4f4-137">The `/indicateprogress` parameter allows you to monitor progress in the command prompt window.</span></span>  
  
2.  <span data-ttu-id="de4f4-138">El parámetro `PID` se omite del comando, que hace que se instale la edición de evaluación.</span><span class="sxs-lookup"><span data-stu-id="de4f4-138">The `PID` parameter is omitted from the command, which causes the Evaluation edition to be installed.</span></span> <span data-ttu-id="de4f4-139">Si desea instalar la edición Enterprise, agregue el PID al comando del programa de instalación y proporcione una clave del producto válida.</span><span class="sxs-lookup"><span data-stu-id="de4f4-139">If you want to install the Enterprise edition, add the PID to your Setup command and provide a valid product key.</span></span>  
  
    ```  
    /PID=<product key for an Enterprise installation>  
    ```  
  
3.  <span data-ttu-id="de4f4-140">Reemplace los marcadores de posición para \<domain\username> y \<StrongPassword> con contraseñas y cuentas de usuario válidas.</span><span class="sxs-lookup"><span data-stu-id="de4f4-140">Replace the placeholders for \<domain\username> and \<StrongPassword>with valid user accounts and passwords.</span></span>  
  
     <span data-ttu-id="de4f4-141">Los `/assvaccount` parámetros y **/assvcpassword** se usan para configurar la [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] instancia en el servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="de4f4-141">The `/assvaccount` and **/assvcpassword** parameters are used to configure the [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] instance on the application server.</span></span> <span data-ttu-id="de4f4-142">Reemplace estos marcadores de posición con información de cuenta válida.</span><span class="sxs-lookup"><span data-stu-id="de4f4-142">Replace these placeholders with valid account information.</span></span>  
  
     <span data-ttu-id="de4f4-143">El parámetro **/assysadminaccounts** debe establecerse en la identidad del usuario que ejecuta SQL Server el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="de4f4-143">The **/assysadminaccounts** parameter must be set to the identity of the user who is running SQL Server Setup.</span></span> <span data-ttu-id="de4f4-144">Debe especificar al menos un administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="de4f4-144">You must specify at least one system administrator.</span></span> <span data-ttu-id="de4f4-145">Tenga en cuenta que el programa de instalación de SQL Server no concede permisos de sysadmin automáticos a los miembros del grupo de administradores integrado.</span><span class="sxs-lookup"><span data-stu-id="de4f4-145">Note that SQL Server Setup no long grants automatic sysadmin permissions to members of the built-in Administrators group.</span></span>  
  
4.  <span data-ttu-id="de4f4-146">Quite los saltos de línea.</span><span class="sxs-lookup"><span data-stu-id="de4f4-146">Remove line breaks.</span></span>  
  
5.  <span data-ttu-id="de4f4-147">Seleccione todo el comando y, a continuación, haga clic en **copiar** en el menú edición.</span><span class="sxs-lookup"><span data-stu-id="de4f4-147">Select the entire command and then click **Copy** on the Edit menu.</span></span>  
  
6.  <span data-ttu-id="de4f4-148">Abra un símbolo del sistema de administrador.</span><span class="sxs-lookup"><span data-stu-id="de4f4-148">Open an administrator command prompt.</span></span> <span data-ttu-id="de4f4-149">Para ello, haga clic en **Inicio**, haga clic con el botón secundario en el símbolo del sistema y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="de4f4-149">To do this, click **Start**, right-click the command prompt, and select **Run as administrator**.</span></span>  
  
7.  <span data-ttu-id="de4f4-150">Navegue hasta la unidad o carpeta compartida que contiene el disco de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de4f4-150">Navigate to the drive or shared folder that contains the SQL Server installation media.</span></span>  
  
8.  <span data-ttu-id="de4f4-151">Pegue el comando revisado en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="de4f4-151">Paste the revised command into the command line.</span></span> <span data-ttu-id="de4f4-152">Para ello, haga clic en el icono de la esquina superior izquierda de la ventana del símbolo del sistema, seleccione **Editar**y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="de4f4-152">To do this, click the icon in the top left corner of the command prompt window, point to **Edit**, and then click **Paste**.</span></span>  
  
9. <span data-ttu-id="de4f4-153">Presione **entrar** para ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="de4f4-153">Press **Enter** to run the command.</span></span> <span data-ttu-id="de4f4-154">Espere a que termine la instalación.</span><span class="sxs-lookup"><span data-stu-id="de4f4-154">Wait for setup to complete.</span></span> <span data-ttu-id="de4f4-155">Puede supervisar el progreso del programa de instalación en la ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="de4f4-155">You can monitor Setup's progress in the command prompt window.</span></span>  
  
10. <span data-ttu-id="de4f4-156">Para comprobar la instalación, compruebe el archivo summary.txt en \Archivos de programa\SQL Server\120\Setup Bootstrap\Log.</span><span class="sxs-lookup"><span data-stu-id="de4f4-156">To verify installation, check the summary.txt file at \Program Files\SQL Server\120\Setup Bootstrap\Log.</span></span> <span data-ttu-id="de4f4-157">El resultado final debe decir "Passed" si el servidor se instaló sin errores.</span><span class="sxs-lookup"><span data-stu-id="de4f4-157">Final result should say "Passed" if the server installed without errors.</span></span>  
  
11. <span data-ttu-id="de4f4-158">Configure el servidor.</span><span class="sxs-lookup"><span data-stu-id="de4f4-158">Configure the server.</span></span> <span data-ttu-id="de4f4-159">Como mínimo, debe implementar soluciones, crear una aplicación de servicio y habilitar la característica para cada colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="de4f4-159">At a minimum, you must deploy solutions, create a service application, and enable the feature for each site collection.</span></span> <span data-ttu-id="de4f4-160">Para obtener más información, vea [configurar o reparar PowerPivot para SharePoint 2010 &#40;herramienta de configuración de powerpivot&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) o [Administración y configuración del servidor de PowerPivot en administración central](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span><span class="sxs-lookup"><span data-stu-id="de4f4-160">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) or [PowerPivot Server Administration and Configuration in Central Administration](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4f4-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de4f4-161">See Also</span></span>  
 <span data-ttu-id="de4f4-162">[Configurar cuentas de servicio PowerPivot](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span><span class="sxs-lookup"><span data-stu-id="de4f4-162">[Configure PowerPivot Service Accounts](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span></span>  
 [<span data-ttu-id="de4f4-163">Instalación de PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="de4f4-163">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
