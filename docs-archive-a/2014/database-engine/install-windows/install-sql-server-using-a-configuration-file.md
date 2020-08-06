---
title: Instale SQL Server 2014 con un archivo de configuración | Microsoft Docs
ms.custom: ''
ms.date: 01/20/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: a832153a-6775-4bed-83f0-55790766d885
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a2f09ad6253762fe5b525f6c918931f4806c84c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744836"
---
# <a name="install-sql-server-2014-using-a-configuration-file"></a><span data-ttu-id="c7c8a-102">Instalar SQL Server 2014 mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="c7c8a-102">Install SQL Server 2014 Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c7c8a-103">El programa de instalación permite generar un archivo de configuración basado en las entradas de tiempo de ejecución y en la configuración predeterminada del sistema.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-103">Setup provides the ability to generate a configuration file based upon the system default and run-time inputs.</span></span> <span data-ttu-id="c7c8a-104">Puede usar el archivo de configuración para implementar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en toda la empresa con la misma configuración.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-104">You can use the configuration file to deploy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] throughout the enterprise with the same configuration.</span></span> <span data-ttu-id="c7c8a-105">También puede normalizar las instalaciones manuales en toda la empresa mediante la creación de un archivo por lotes que inicie Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-105">You can also standardize manual installations throughout the enterprise, by creating a batch file that launches Setup.exe.</span></span>  
  
 <span data-ttu-id="c7c8a-106">El programa de instalación admite el uso del archivo de configuración solamente a través del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-106">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="c7c8a-107">A continuación se indica el orden de procesamiento de los parámetros cuando se usa el archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="c7c8a-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="c7c8a-108">El archivo de configuración sobrescribe los valores predeterminados de un paquete.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="c7c8a-109">Los valores de línea de comandos sobrescriben los valores del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="c7c8a-110">El archivo de configuración se puede usar para realizar el seguimiento de los parámetros y valores de cada instalación.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-110">The configuration file can be used to track the parameters and values for each installation.</span></span> <span data-ttu-id="c7c8a-111">De este modo, el archivo de configuración es útil para comprobar y auditar las instalaciones.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-111">This makes the configuration file useful for verifying and auditing the installations.</span></span>  
  
## <a name="configuration-file-structure"></a><span data-ttu-id="c7c8a-112">Estructura de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c7c8a-112">Configuration File Structure</span></span>  
 <span data-ttu-id="c7c8a-113">El archivo ConfigurationFile.ini es un archivo de texto con parámetros (pares de nombre/valor) y comentarios descriptivos.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-113">The ConfigurationFile.ini file is a text file with parameters (name/value pair) and descriptive comments.</span></span>  
  
 <span data-ttu-id="c7c8a-114">A continuación se muestra un ejemplo de archivo ConfigurationFile.ini:</span><span class="sxs-lookup"><span data-stu-id="c7c8a-114">The following is an example of a ConfigurationFile.ini file:</span></span>  
  
```  
; Microsoft SQL Server Configuration file  
[OPTIONS]  
; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE.   
; This is a required parameter.   
ACTION="Install"  
; Specifies features to install, uninstall, or upgrade.   
; The list of top-level features include SQL, AS, RS, IS, and Tools.   
; The SQL feature will install the database engine, replication, and full-text.   
; The Tools feature will install Management Tools, Books online,   
; SQL Server Data Tools, and other shared components.   
FEATURES=SQL,Tools  
```  
  
#### <a name="how-to-generate-a-configuration-file"></a><span data-ttu-id="c7c8a-115">Cómo generar un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="c7c8a-115">How to generate a configuration file</span></span>  
  
1.  <span data-ttu-id="c7c8a-116">Inserte el medio de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7c8a-116">Insert the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span> <span data-ttu-id="c7c8a-117">Desde la carpeta raíz, haga doble clic en Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-117">From the root folder, double-click Setup.exe.</span></span> <span data-ttu-id="c7c8a-118">Para realizar la instalación desde un recurso compartido de red, localice la carpeta raíz de dicho recurso y, a continuación, haga doble clic en Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-118">To install from a network share, locate the root folder on the share, and then double-click Setup.exe.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c7c8a-119">Express Edition no crea automáticamente un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-119">Express Edition setup does not create a configuration file automatically.</span></span> <span data-ttu-id="c7c8a-120">El siguiente comando iniciará el programa de instalación y creará un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-120">The following command will start  setup and create a configuration file.</span></span>  
    >   
    >  <span data-ttu-id="c7c8a-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span><span class="sxs-lookup"><span data-stu-id="c7c8a-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span></span>  
  
2.  <span data-ttu-id="c7c8a-122">Siga los pasos del asistente hasta llegar a la página **Listo para instalar** .</span><span class="sxs-lookup"><span data-stu-id="c7c8a-122">Follow the wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="c7c8a-123">La ruta de acceso al archivo de configuración se especifica en la sección que así lo indica en la página **Listo para instalar** .</span><span class="sxs-lookup"><span data-stu-id="c7c8a-123">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span> <span data-ttu-id="c7c8a-124">Para obtener más información acerca de cómo instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte Instalación [de SQL Server 2014 desde el Asistente para la instalación &#40;&#41;de instalación ](install-sql-server-from-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="c7c8a-124">For more information about how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
3.  <span data-ttu-id="c7c8a-125">Cancele la instalación sin completarla realmente para generar el archivo INI.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-125">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c7c8a-126">La infraestructura de instalación escribe todos los parámetros correspondientes a las acciones que se ejecutaron, con la excepción de la información confidencial, como las contraseñas.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-126">The setup infrastructure writes out all the appropriate parameters for the actions that were run, with the exception of sensitive information such as passwords.</span></span> <span data-ttu-id="c7c8a-127">El parámetro /IAcceptSQLServerLicenseTerms tampoco se escribe en el archivo de configuración, y para incluirlo es necesario modificar dicho archivo o proporcionar un valor en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-127">The /IAcceptSQLServerLicenseTerms parameter is also not written out to the configuration file and requires either a modification of the configuration file or a value to be supplied at the command prompt.</span></span> <span data-ttu-id="c7c8a-128">Para obtener más información, vea [Instalar SQL Server 2014 desde el símbolo del sistema](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="c7c8a-128">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span> <span data-ttu-id="c7c8a-129">Además se incluye un valor para los parámetros booleanos, ya que normalmente no se proporciona a través del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-129">In addition, a value is included for Boolean parameters where a value is usually not supplied through the command prompt.</span></span>  
  
## <a name="using-the-configuration-file-to-install-ssnoversion"></a><span data-ttu-id="c7c8a-130">Usar el archivo de configuración para instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7c8a-130">Using the Configuration File to Install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="c7c8a-131">El archivo de configuración solamente se usa en instalaciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-131">You can only use the configuration file on command-line installations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7c8a-132">Si necesita realizar cambios en el archivo de configuración, se recomienda hacer una copia y trabajar con ella.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-132">If you need to make changes to the configuration file, we recommend that you make a copy and work with the copy.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-install-a-stand-alone-ssnoversion-instance"></a><span data-ttu-id="c7c8a-133">Cómo usar un archivo de configuración para instalar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] independiente</span><span class="sxs-lookup"><span data-stu-id="c7c8a-133">How to use a configuration file to install a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance</span></span>  
  
-   <span data-ttu-id="c7c8a-134">Realice la instalación a través del símbolo del sistema y proporcione el archivo ConfigurationFile.ini mediante el parámetro *ConfigurationFile* .</span><span class="sxs-lookup"><span data-stu-id="c7c8a-134">Run the installation through the command prompt and supply the ConfigurationFile.ini using the *ConfigurationFile* parameter.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-prepare-and-complete-an-image-of-a-stand-alone-ssnoversion-instance-sysprep"></a><span data-ttu-id="c7c8a-135">Utilizar un archivo de configuración para preparar y completar una imagen de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] independiente (SysPrep)</span><span class="sxs-lookup"><span data-stu-id="c7c8a-135">How to use a configuration file to prepare and complete an image of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (SysPrep)</span></span>  
  
1.  <span data-ttu-id="c7c8a-136">Para preparar una o más instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y configurarlas en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-136">To prepare one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and configure them on the same machine.</span></span>  
  
    -   <span data-ttu-id="c7c8a-137">Ejecute **Preparar imagen de una instancia independiente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** en la página **Avanzadas** del Centro de instalación y capture el archivo de configuración de preparación de imagen.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-137">Run **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="c7c8a-138">Utilice el mismo archivo de configuración de preparación de imagen como plantilla para preparar más instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7c8a-138">Use the same prepare image configuration file as a template to prepare more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="c7c8a-139">Ejecute **Completar imagen de una instancia independiente preparada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** en la página **Avanzadas** del Centro de instalación para configurar una instancia preparada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-139">Run **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center to configure a prepared instances on the machine.</span></span>  
  
2.  <span data-ttu-id="c7c8a-140">Para preparar una imagen del sistema operativo que incluya una instancia preparada no configurada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mediante la herramienta Windows SysPrep.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-140">To prepare an image of the operating system including an unconfigured prepared instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], using Windows SysPrep tool.</span></span>  
  
    -   <span data-ttu-id="c7c8a-141">Ejecute **Preparar imagen de una instancia independiente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** en la página Avanzadas del Centro de instalación y capture el archivo de configuración de preparación de imagen.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-141">Run the **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the Advanced page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="c7c8a-142">Ejecute **Completar imagen de una instancia independiente preparada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** en la página **Avanzadas** del Centro de instalación, pero cancele el proceso en la página **Listo para completar la imagen** después de capturar el archivo de configuración completo.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-142">Run the **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center, but cancel it on the **Ready to Complete** page after capturing the complete configuration file.</span></span>  
  
    -   <span data-ttu-id="c7c8a-143">El archivo de configuración de imagen completo se puede almacenar con la imagen de Windows para automatizar la configuración de las instancias preparadas.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-143">The complete image configuration file can be stored with the Windows image for automating the configuration of the prepared instances.</span></span>  
  
#### <a name="how-to-install-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="c7c8a-144">Cómo instalar un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante el archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="c7c8a-144">How to install a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="c7c8a-145">Opción de instalación integrada (crear un clúster de conmutación por error de nodo único en un nodo y ejecutar AddNode en los demás nodos):</span><span class="sxs-lookup"><span data-stu-id="c7c8a-145">Integrated Install option (create a single node failover cluster on a node and for additional nodes, run AddNode on them):</span></span>  
  
    -   <span data-ttu-id="c7c8a-146">Ejecute la opción de instalación de clúster de conmutación por error y capture el archivo de configuración que enumera todos los valores de configuración de la instalación.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-146">Run the "Install a Failover Cluster" option and capture the configuration file that lists all the installation settings.</span></span>  
  
    -   <span data-ttu-id="c7c8a-147">Ejecute la instalación del clúster de conmutación por error de línea de comandos proporcionando el parámetro *ConfigurationFile* .</span><span class="sxs-lookup"><span data-stu-id="c7c8a-147">Run the command-line failover cluster install by supplying the *ConfigurationFile* parameter.</span></span>  
  
    -   <span data-ttu-id="c7c8a-148">En un nodo adicional que vaya a agregarse, ejecute AddNode para capturar el archivo ConfigurationFile.ini aplicable al clúster de conmutación por error existente.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-148">On an additional node to be added, run AddNode to capture the ConfigurationFile.ini file applicable to the existing failover cluster.</span></span>  
  
    -   <span data-ttu-id="c7c8a-149">Ejecute AddNode en la línea de comandos en todos los demás nodos que se unirán al clúster de conmutación por error; proporcione el mismo archivo de configuración mediante el parámetro ConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-149">Run the command-line AddNode on all the additional nodes that will join the failover cluster, by supplying the same configuration file using the ConfigurationFile parameter.</span></span>  
  
2.  <span data-ttu-id="c7c8a-150">Opción de instalación avanzada (preparar el clúster de conmutación por error en todos los nodos de clúster de conmutación por error y, a continuación, después de preparar todos los nodos, ejecutar "complete" en el nodo donde se encuentra el disco compartido):</span><span class="sxs-lookup"><span data-stu-id="c7c8a-150">Advanced install option (prepare failover cluster on all failover cluster nodes, then, after preparing all the nodes, run complete on the node that owns the shared disk):</span></span>  
  
    -   <span data-ttu-id="c7c8a-151">Ejecute **Prepare** en uno de los nodos y capture el archivo ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-151">Run **Prepare** on one of the nodes, and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="c7c8a-152">Proporcione al programa de instalación el mismo archivo ConfigurationFile.ini en todos los nodos que se prepararán para el clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-152">Supply the same ConfigurationFile.ini file to Setup on all the nodes that will be prepared for the failover cluster.</span></span>  
  
    -   <span data-ttu-id="c7c8a-153">Una vez preparados todos los nodos, ejecute una operación para completar el clúster de conmutación por error en el nodo que posee el disco compartido y capture el archivo ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-153">After all the nodes have been prepared, run a complete failover cluster operation on the node that owns the shared disk and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="c7c8a-154">A continuación, puede proporcionar este archivo ConfigurationFile.ini para completar el clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-154">You can then supply this ConfigurationFile.ini file to complete the failover cluster.</span></span>  
  
#### <a name="how-to-add-or-remove-a-node-to-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="c7c8a-155">Cómo agregar o quitar un nodo en un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante el archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="c7c8a-155">How to add or remove a node to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
-   <span data-ttu-id="c7c8a-156">Si tiene un archivo de configuración que ya se usó previamente para agregar o quitar un nodo en un clúster de conmutación por error, puede volver a usar ese mismo archivo para agregar o quitar nodos adicionales.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-156">If you have a configuration file that was previously used to add a node to or remove a node from a failover cluster, you can reuse that same file to add or remove additional nodes.</span></span>  
  
#### <a name="how-to-upgrade-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="c7c8a-157">Cómo actualizar un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante el archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="c7c8a-157">How to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="c7c8a-158">Ejecute la actualización en el nodo pasivo y capture el archivo ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-158">Run upgrade on the passive node and capture the ConfigurationFile.ini file.</span></span> <span data-ttu-id="c7c8a-159">Para ello, puede realizar la actualización real o salir al final sin llegar a realizarla.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-159">You can do this either by performing the actual upgrade, or exiting at the end without doing the actual upgrade.</span></span>  
  
2.  <span data-ttu-id="c7c8a-160">En todos los nodos adicionales que se van a actualizar, proporcione el archivo ConfigurationFile.ini para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="c7c8a-160">On all the additional nodes to be upgraded, supply the ConfigurationFile.ini file to complete the process.</span></span>  
  
## <a name="sample-syntax"></a><span data-ttu-id="c7c8a-161">Sintaxis de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7c8a-161">Sample Syntax</span></span>  
 <span data-ttu-id="c7c8a-162">A continuación se ofrecen algunos ejemplos de uso del archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="c7c8a-162">Following are some examples on how to use the configuration file:</span></span>  
  
-   <span data-ttu-id="c7c8a-163">Para especificar el archivo de configuración en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="c7c8a-163">To specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /ConfigurationFile=MyConfigurationFile.INI  
```  
  
-   <span data-ttu-id="c7c8a-164">Para especificar las contraseñas en el símbolo del sistema en lugar de hacerlo en el archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="c7c8a-164">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
```  
Setup.exe /SQLSVCPASSWORD="************" /AGTSVCPASSWORD="************" /ASSVCPASSWORD="************" /ISSVCPASSWORD="************" /RSSVCPASSWORD="************" /ConfigurationFile=MyConfigurationFile.INI  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7c8a-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7c8a-165">See Also</span></span>  
 <span data-ttu-id="c7c8a-166">[Instalación de SQL Server 2014 desde el símbolo del sistema](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="c7c8a-166">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="c7c8a-167">[Instalación de clúster de conmutación por error de SQL Server](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span><span class="sxs-lookup"><span data-stu-id="c7c8a-167">[SQL Server Failover Cluster Installation](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span></span>  
 [<span data-ttu-id="c7c8a-168">Actualizar un clúster de conmutación por error de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c7c8a-168">Upgrade a SQL Server Failover Cluster</span></span>](../../sql-server/failover-clusters/windows/upgrade-a-sql-server-failover-cluster-instance.md)  
  
  
