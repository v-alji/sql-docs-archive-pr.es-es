---
title: Configuración del servicio de Integration Services (servicio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- configuration files [Integration Services]
- service [Integration Services], configuring
- default configuration files
ms.assetid: 36d78393-a54c-44b0-8709-7f003f44c27f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70c41377a2c302e1a021c6ade2a9d487579fa64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748873"
---
# <a name="configuring-the-integration-services-service-ssis-service"></a><span data-ttu-id="843b9-102">Configurar el servicio Integration Services (servicio SSIS)</span><span class="sxs-lookup"><span data-stu-id="843b9-102">Configuring the Integration Services Service (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="843b9-103">En este tema se describe el servicio de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un servicio Windows para administrar paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="843b9-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] <span data-ttu-id="843b9-104">admite el servicio para mantener la compatibilidad con versiones anteriores de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="843b9-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="843b9-105">A partir de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], puede administrar objetos como paquetes en el servidor de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="843b9-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="843b9-106">El servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] se basa en un archivo de configuración para sus valores.</span><span class="sxs-lookup"><span data-stu-id="843b9-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service relies on a configuration file for its settings.</span></span> <span data-ttu-id="843b9-107">De forma predeterminada, el nombre de este archivo de configuración es MsDtsSrvr.ini.xml y el archivo se encuentra en la carpeta% archivos de programa%\Microsoft SQL Server\120\dts\binn</span><span class="sxs-lookup"><span data-stu-id="843b9-107">By default, the name for this configuration file is MsDtsSrvr.ini.xml, and the file is located in the folder, %ProgramFiles%\Microsoft SQL Server\120\DTS\Binn.</span></span>  
  
 <span data-ttu-id="843b9-108">Normalmente, no tiene que realizar ningún cambio en este archivo de configuración, ni es necesario cambiar su ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="843b9-108">Typically, you do not have to make any changes to this configuration file, nor do you have to change the file's default location.</span></span> <span data-ttu-id="843b9-109">Sin embargo, tendrá que modificar el archivo de configuración si sus paquetes están almacenados en una instancia con nombre o una instancia remota del [!INCLUDE[ssDE](../includes/ssde-md.md)], o en varias instancias de [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="843b9-109">However, you will have to modify the configuration file if your packages are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)], or in multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="843b9-110">Además, si mueve el archivo de configuración a una ubicación distinta de la predeterminada, tendrá que modificar la clave del Registro que especifica la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="843b9-110">Also, if you move the configuration file to a location other than the default location, you will have to modify the Registry key that specifies the file location.</span></span>  
  
## <a name="configuration-file-contents"></a><span data-ttu-id="843b9-111">Contenido del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="843b9-111">Configuration File Contents</span></span>  
 <span data-ttu-id="843b9-112">Cuando se instala [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], el proceso de instalación crea e instala el archivo de configuración para el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="843b9-112">When you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the setup process creates and installs the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="843b9-113">Este archivo de configuración contiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="843b9-113">This configuration file contains the following settings:</span></span>  
  
-   <span data-ttu-id="843b9-114">Si se envía a los paquetes un comando de detención cuando se detenga el servicio.</span><span class="sxs-lookup"><span data-stu-id="843b9-114">Packages are sent a stop command when the service stops.</span></span>  
  
-   <span data-ttu-id="843b9-115">Las carpetas raíz que deben mostrarse para [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en el Explorador de objetos de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] son MSDB y File System.</span><span class="sxs-lookup"><span data-stu-id="843b9-115">The root folders to display for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in Object Explorer of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] are the MSDB and File System folders.</span></span>  
  
-   <span data-ttu-id="843b9-116">Los paquetes del sistema de archivos que [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] administra el servicio se encuentran en%ProgramFiles%\MICROSOFT SQL Server\120\DTS\Packages.</span><span class="sxs-lookup"><span data-stu-id="843b9-116">The packages in the file system that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages are located in %ProgramFiles%\Microsoft SQL Server\120\DTS\Packages.</span></span>  
  
 <span data-ttu-id="843b9-117">Este archivo de configuración también especifica qué base de datos msdb contiene los paquetes que el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] administrará.</span><span class="sxs-lookup"><span data-stu-id="843b9-117">This configuration file also specifies which msdb database contains the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service will manage.</span></span> <span data-ttu-id="843b9-118">De forma predeterminada, el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] se configura para administrar los paquetes de la base de datos msdb de la instancia del [!INCLUDE[ssDE](../includes/ssde-md.md)] que se instala al mismo tiempo que [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="843b9-118">By default, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed at the same time as [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="843b9-119">Si no se instala al mismo tiempo una instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)] , el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] se configura para administrar paquetes de la base de datos msdb de la instancia local predeterminada del [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="843b9-119">If an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] is not installed at the same time, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the local, default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
### <a name="default-configuration-file-example"></a><span data-ttu-id="843b9-120">Ejemplo de archivo de configuración predeterminado</span><span class="sxs-lookup"><span data-stu-id="843b9-120">Default Configuration File Example</span></span>  
 <span data-ttu-id="843b9-121">En el ejemplo siguiente se muestra un archivo de configuración predeterminado que especifica los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="843b9-121">The following example shows a default configuration file that specifies the following settings:</span></span>  
  
-   <span data-ttu-id="843b9-122">Los paquetes dejan de ejecutarse cuando se detiene el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="843b9-122">Packages stop running when the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service stops.</span></span>  
  
-   <span data-ttu-id="843b9-123">Las carpetas raíz donde se almacenan los paquetes en [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] son MSDB y Sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="843b9-123">The root folders for package storage in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are MSDB and File System.</span></span>  
  
-   <span data-ttu-id="843b9-124">El servicio administra paquetes que están almacenados en la base de datos msdb de la instancia local y predeterminada de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="843b9-124">The service manages packages that are stored in the msdb database of the local, default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="843b9-125">El servicio administra los paquetes que están almacenados en el sistema de archivos en la carpeta Paquetes.</span><span class="sxs-lookup"><span data-stu-id="843b9-125">The service manages packages that are stored in the file system in the Packages folder.</span></span>  
  
 <span data-ttu-id="843b9-126">**Ejemplo de archivo de configuración predeterminado**</span><span class="sxs-lookup"><span data-stu-id="843b9-126">**Example of a Default Configuration File**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>.</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file"></a><span data-ttu-id="843b9-127">Modificación del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="843b9-127">Modification of the Configuration File</span></span>  
 <span data-ttu-id="843b9-128">Puede modificar el archivo de configuración para permitir que los paquetes se sigan ejecutando si se detiene el servicio, para mostrar carpetas raíz adicionales en el Explorador de objetos, o para especificar una carpeta distinta o carpetas adicionales del sistema de archivos que deban ser administradas por el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="843b9-128">You can modify the configuration file to allow packages to continue running if the service stops, to display additional root folders in Object Explorer, or to specify a different folder or additional folders in the file system to be managed by [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="843b9-129">Por ejemplo, puede crear carpetas raíz adicionales de tipo, `SqlServerFolder`, para administrar paquetes en las bases de datos msdb de instancias adicionales de [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="843b9-129">For example, you can create additional root folders of type, `SqlServerFolder`, to manage packages in the msdb databases of additional instances of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="843b9-130">Algunos caracteres no son válidos en los nombres de carpeta.</span><span class="sxs-lookup"><span data-stu-id="843b9-130">Some characters are not valid in folder names.</span></span> <span data-ttu-id="843b9-131">Los caracteres válidos para los nombres de carpeta se determinan mediante la clase [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] System.IO.Path **de** y el campo **GetInvalidFilenameChars** .</span><span class="sxs-lookup"><span data-stu-id="843b9-131">Valid characters for folder names are determined by the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] class **System.IO.Path** and the **GetInvalidFilenameChars** field.</span></span> <span data-ttu-id="843b9-132">El campo **GetInvalidFilenameChars** proporciona una matriz específica de la plataforma de caracteres que no se pueden especificar en los argumentos de la cadena de ruta pasada a los miembros de la clase **Path** .</span><span class="sxs-lookup"><span data-stu-id="843b9-132">The **GetInvalidFilenameChars** field provides a platform-specific array of characters that cannot be specified in path string arguments passed to members of the **Path** class.</span></span> <span data-ttu-id="843b9-133">El juego de caracteres no válidos puede variar en función del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="843b9-133">The set of invalid characters can vary by file system.</span></span> <span data-ttu-id="843b9-134">Normalmente, los caracteres no válidos son las comillas ("), el carácter mayor que (<) y la barra vertical (|).</span><span class="sxs-lookup"><span data-stu-id="843b9-134">Typically, invalid characters are the quotation mark ("), less than (<) character, and pipe (|) character.</span></span>  
  
 <span data-ttu-id="843b9-135">Sin embargo, tendrá que modificar el archivo de configuración para administrar paquetes que estén almacenados en una instancia con nombre o una instancia remota de [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="843b9-135">However, you will have to modify the configuration file to manage packages that are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="843b9-136">Si no actualiza el archivo de configuración, no puede usar el **Explorador de objetos** de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para ver los paquetes que estén almacenados en la base de datos msdb en la instancia con nombre o en la instancia remota.</span><span class="sxs-lookup"><span data-stu-id="843b9-136">If you do not update the configuration file, you cannot use **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to view packages that are stored in the msdb database on the named instance or the remote instance.</span></span> <span data-ttu-id="843b9-137">Si intenta utilizar el **Explorador de objetos** para ver estos paquetes, aparece el mensaje de error siguiente:</span><span class="sxs-lookup"><span data-stu-id="843b9-137">If you try to use **Object Explorer** to view these packages, you receive the following error message:</span></span>  
  
 `Failed to retrieve data for this request. (Microsoft.SqlServer.SmoEnum)`  
  
 `The SQL Server specified in Integration Services service configuration is not present or is not available. This might occur when there is no default instance of SQL Server on the computer. For more information, see the topic "Configuring the Integration Services Service" in SQL Server 2008 Books Online.`  
  
 `Login Timeout Expired`  
  
 `An error has occurred while establishing a connection to the server. When connecting to SQL Server 2008, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.`  
  
 `Named Pipes Provider: Could not open a connection to SQL Server [2]. (MsDtsSvr).`  
  
 <span data-ttu-id="843b9-138">Para modificar el archivo de configuración para el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , se ha de utilizar un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="843b9-138">To modify the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, you use a text editor.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="843b9-139">Después de modificar el archivo de configuración del servicio, deberá reiniciar el servicio para usar la configuración del servicio actualizada.</span><span class="sxs-lookup"><span data-stu-id="843b9-139">After you modify the service configuration file, you must restart the service to use the updated service configuration.</span></span>  
  
### <a name="modified-configuration-file-example"></a><span data-ttu-id="843b9-140">Ejemplo de archivo de configuración modificado</span><span class="sxs-lookup"><span data-stu-id="843b9-140">Modified Configuration File Example</span></span>  
 <span data-ttu-id="843b9-141">El ejemplo siguiente muestra un archivo de configuración modificado para [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="843b9-141">The following example shows a modified configuration file for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="843b9-142">Este archivo es para una instancia con nombre de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] denominada `InstanceName` en un servidor denominado `ServerName`.</span><span class="sxs-lookup"><span data-stu-id="843b9-142">This file is for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] called `InstanceName` on a server named `ServerName`.</span></span>  
  
 <span data-ttu-id="843b9-143">**Ejemplo de un archivo de configuración modificado para una instancia con nombre de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="843b9-143">**Example of a Modified Configuration File for a Named Instance of SQL Server**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>ServerName\InstanceName</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file-location"></a><span data-ttu-id="843b9-144">Modificación de la ubicación del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="843b9-144">Modification of the Configuration File Location</span></span>  
<span data-ttu-id="843b9-145">La clave del registro **HKEY_LOCAL_MACHINE \SOFTWARE\MICROSOFT\MICROSOFT SQL Server\120\SSIS\ServiceConfigFile** especifica la ubicación y el nombre del archivo de configuración que [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] usa el servicio.</span><span class="sxs-lookup"><span data-stu-id="843b9-145">The Registry key **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\120\SSIS\ServiceConfigFile** specifies the location and name for the configuration file that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service uses.</span></span> <span data-ttu-id="843b9-146">El valor predeterminado de la clave del registro es **c:\Archivos de programa\Microsoft SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span><span class="sxs-lookup"><span data-stu-id="843b9-146">The default value of the Registry key is **C:\Program Files\Microsoft SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span></span> <span data-ttu-id="843b9-147">Puede actualizar el valor de la clave del Registro para utilizar un nombre y una ubicación diferentes para el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="843b9-147">You can update the value of the Registry key to use a different name and location for the configuration file.</span></span> <span data-ttu-id="843b9-148">Tenga en cuenta que el número de versión en la ruta de acceso (120 para SQL Server [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] ) variará en función de la versión SQL Server.</span><span class="sxs-lookup"><span data-stu-id="843b9-148">Note that the version number in the path (120 for SQL Server  [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)]) will vary depending on the SQL Server version.</span></span> 
  
  
> [!CAUTION]  
>  <span data-ttu-id="843b9-149">Editar el Registro de forma incorrecta puede originar problemas graves que requieran volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="843b9-149">Incorrectly editing the Registry can cause serious problems that may require you to reinstall your operating system.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="843b9-150">no puede garantizar la resolución de dichos problemas.</span><span class="sxs-lookup"><span data-stu-id="843b9-150">cannot guarantee that problems resulting from editing the Registry incorrectly can be resolved.</span></span> <span data-ttu-id="843b9-151">Haga una copia de seguridad de los datos importantes antes de modificar el Registro.</span><span class="sxs-lookup"><span data-stu-id="843b9-151">Before editing the Registry, back up any valuable data.</span></span> <span data-ttu-id="843b9-152">Para obtener información sobre cómo hacer una copia de seguridad, restaurar y modificar el Registro, vea el artículo de [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base, [Definición del Registro de Microsoft Windows](https://support.microsoft.com/kb/256986).</span><span class="sxs-lookup"><span data-stu-id="843b9-152">For information about how to back up, restore, and edit the Registry, see the [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base article, [Description of the Microsoft Windows registry](https://support.microsoft.com/kb/256986).</span></span>  
  
 <span data-ttu-id="843b9-153">El servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] carga el archivo de configuración cuando se inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="843b9-153">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service loads the configuration file when the service is started.</span></span> <span data-ttu-id="843b9-154">Si se cambia la entrada del Registro, es preciso reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="843b9-154">Any changes to the Registry entry require that the service be restarted.</span></span>  
  
  
