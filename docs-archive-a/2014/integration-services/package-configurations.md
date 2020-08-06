---
title: Configuraciones de paquetes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package configuration syntax [Integration Services]
- SQL Server Integration Services packages, configurations
- SSIS packages, configurations
- XML [Integration Services]
- Integration Services packages, configurations
- configuration syntax [Integration Services]
- indirect configurations [Integration Services]
- configurations [Integration Services]
- direct configurations [Integration Services]
- packages [Integration Services], configurations
ms.assetid: d20e0311-1fc9-4ddc-a381-6d127cf11b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d22dbfedcf4cf7084e1667586f9774926f3b2a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677771"
---
# <a name="package-configurations"></a><span data-ttu-id="211b5-102">Configuraciones de paquetes</span><span class="sxs-lookup"><span data-stu-id="211b5-102">Package Configurations</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="211b5-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] proporciona configuraciones de paquetes que se pueden usar para actualizar los valores de las propiedades en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="211b5-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides package configurations that you can use to update the values of properties at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="211b5-104">Hay configuraciones disponibles para el modelo de implementación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="211b5-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="211b5-105">Se usan parámetros en lugar de configuraciones para el modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="211b5-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="211b5-106">El modelo de implementación de proyectos le permite implementar proyectos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="211b5-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="211b5-107">Para obtener más información acerca de los modelos de implementación, vea [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="211b5-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="211b5-108">Una configuración es una par propiedad/valor que se agrega a un paquete completo.</span><span class="sxs-lookup"><span data-stu-id="211b5-108">A configuration is a property/value pair that you add to a completed package.</span></span> <span data-ttu-id="211b5-109">Normalmente, se crean las propiedades establecidas de un paquete para los objetos del paquete durante el desarrollo y, después, se agrega la configuración al paquete.</span><span class="sxs-lookup"><span data-stu-id="211b5-109">Typically, you create a package set properties on the package objects during package development, and then add the configuration to the package.</span></span> <span data-ttu-id="211b5-110">Cuando se ejecuta el paquete, éste recibe de la configuración los nuevos valores de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="211b5-110">When the package runs, it gets the new values of the property from the configuration.</span></span> <span data-ttu-id="211b5-111">Por ejemplo, al utilizar una configuración, se puede modificar la cadena de conexión de un administrador de conexiones o actualizar el valor de una variable.</span><span class="sxs-lookup"><span data-stu-id="211b5-111">For example, by using a configuration, you can change the connection string of a connection manager, or update the value of a variable.</span></span>  
  
 <span data-ttu-id="211b5-112">Las configuraciones de paquetes ofrecen las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="211b5-112">Package configurations provide the following benefits:</span></span>  
  
-   <span data-ttu-id="211b5-113">Permiten mover más fácilmente los paquetes de un entorno de desarrollo a un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="211b5-113">Configurations make it easier to move packages from a development environment to a production environment.</span></span> <span data-ttu-id="211b5-114">Por ejemplo, una configuración puede actualizar la ruta de acceso de un archivo de origen, o bien cambiar el nombre de una base de datos o servidor.</span><span class="sxs-lookup"><span data-stu-id="211b5-114">For example, a configuration can update the path of a source file, or change the name of a database or server.</span></span>  
  
-   <span data-ttu-id="211b5-115">Son útiles para implementar paquetes en varios servidores distintos.</span><span class="sxs-lookup"><span data-stu-id="211b5-115">Configurations are useful when you deploy packages to many different servers.</span></span> <span data-ttu-id="211b5-116">Por ejemplo, una variable en la configuración de cada paquete implementado puede contener un valor de espacio de disco distinto, y si el espacio de disco disponible es menor que dicho valor, el paquete no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="211b5-116">For example, a variable in the configuration for each deployed package can contain a different disk space value, and if the available disk space does not meet this value, the package does not run.</span></span>  
  
-   <span data-ttu-id="211b5-117">Aumentan la flexibilidad de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="211b5-117">Configurations make packages more flexible.</span></span> <span data-ttu-id="211b5-118">Por ejemplo, una configuración puede actualizar el valor de una variable que se utiliza en una expresión de propiedad.</span><span class="sxs-lookup"><span data-stu-id="211b5-118">For example, a configuration can update the value of a variable that is used in a property expression.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="211b5-119">admite varios métodos distintos para almacenar configuraciones de paquetes, como archivos XML, tablas de una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y variables de entorno y de paquete.</span><span class="sxs-lookup"><span data-stu-id="211b5-119">supports several different methods of storing package configurations, such as XML files, tables in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, and environment and package variables.</span></span>  
  
 <span data-ttu-id="211b5-120">Cada configuración es una pareja propiedad/valor.</span><span class="sxs-lookup"><span data-stu-id="211b5-120">Each configuration is a property/value pair.</span></span> <span data-ttu-id="211b5-121">El archivo de configuración XML y los tipos de configuración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pueden incluir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="211b5-121">The XML configuration file and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration types can include multiple configurations.</span></span>  
  
 <span data-ttu-id="211b5-122">Las configuraciones se incluyen al crear una utilidad de implementación de paquetes para instalar paquetes.</span><span class="sxs-lookup"><span data-stu-id="211b5-122">The configurations are included when you create a package deployment utility for installing packages.</span></span> <span data-ttu-id="211b5-123">Al instalar los paquetes, las configuraciones se pueden actualizar como un paso en la instalación del paquete.</span><span class="sxs-lookup"><span data-stu-id="211b5-123">When you install the packages, the configurations can be updated as a step in the package installation.</span></span>  
  
## <a name="understanding-how-package-configurations-are-applied-at-run-time"></a><span data-ttu-id="211b5-124">Cómo se aplican las configuraciones de paquetes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="211b5-124">Understanding How Package Configurations Are Applied at Run Time</span></span>  
 <span data-ttu-id="211b5-125">Cuando usa la utilidad de símbolo del sistema **dtexec** (dtexec.exe) para ejecutar un paquete implementado, la utilidad aplica las configuraciones de paquetes dos veces.</span><span class="sxs-lookup"><span data-stu-id="211b5-125">When you use the **dtexec** command prompt utility (dtexec.exe) to run a deployed package, the utility applies package configurations twice.</span></span> <span data-ttu-id="211b5-126">antes y después de aplicar las opciones que se especificaron en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="211b5-126">The utility applies configurations both before and after it applies the options that you specified on command line.</span></span>  
  
 <span data-ttu-id="211b5-127">A medida que la utilidad carga y ejecuta el paquete, los eventos se producen en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="211b5-127">As the utility loads and runs the package, events occur in the following order:</span></span>  
  
1.  <span data-ttu-id="211b5-128">La utilidad **dtexec** carga el paquete.</span><span class="sxs-lookup"><span data-stu-id="211b5-128">The **dtexec** utility loads the package.</span></span>  
  
2.  <span data-ttu-id="211b5-129">La utilidad aplica las configuraciones que se especificaron en el paquete en tiempo de diseño, en el orden indicado en el paquete.</span><span class="sxs-lookup"><span data-stu-id="211b5-129">The utility applies the configurations that were specified in the package at design time and in the order that is specified in the package.</span></span> <span data-ttu-id="211b5-130">(Las configuraciones de las variables de paquetes primarios son la excepción.</span><span class="sxs-lookup"><span data-stu-id="211b5-130">(The one exception to this is the Parent Package Variables configurations.</span></span> <span data-ttu-id="211b5-131">La utilidad solo aplica estas configuraciones una vez y al final en el proceso).</span><span class="sxs-lookup"><span data-stu-id="211b5-131">The utility applies these configurations only once and later in the process.)</span></span>  
  
3.  <span data-ttu-id="211b5-132">A continuación, la utilidad aplica cualquier opción que especificara en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="211b5-132">The utility then applies any options that you specified on the command line.</span></span>  
  
4.  <span data-ttu-id="211b5-133">La utilidad vuelve a cargar entonces las configuraciones que se especificaron en el paquete en tiempo de diseño, en el orden indicado en el paquete.</span><span class="sxs-lookup"><span data-stu-id="211b5-133">The utility then reloads the configurations that were specified in the package at design time and in the order specified in the package.</span></span> <span data-ttu-id="211b5-134">(De nuevo, la excepción a esta regla son las configuraciones de variables de paquetes primarios).</span><span class="sxs-lookup"><span data-stu-id="211b5-134">(Again, the exception to this rule is the Parent Package Variables configurations).</span></span> <span data-ttu-id="211b5-135">La utilidad utiliza las opciones de la línea de comandos que se especificaran para volver a cargar las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="211b5-135">The utility uses any command-line options that were specified to reload the configurations.</span></span> <span data-ttu-id="211b5-136">Por consiguiente, se podrían volver a cargar valores diferentes desde una ubicación diferente.</span><span class="sxs-lookup"><span data-stu-id="211b5-136">Therefore, different values might be reloaded from a different location.</span></span>  
  
5.  <span data-ttu-id="211b5-137">La utilidad aplica las configuraciones de variables de paquetes primarios.</span><span class="sxs-lookup"><span data-stu-id="211b5-137">The utility applies the Parent Package Variable configurations.</span></span>  
  
6.  <span data-ttu-id="211b5-138">La utilidad ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="211b5-138">The utility runs the package.</span></span>  
  
 <span data-ttu-id="211b5-139">La manera en la que la utilidad **dtexec** aplica las configuraciones afecta a estas opciones de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="211b5-139">The way in which the **dtexec** utility applies configurations affects the following command-line options:</span></span>  
  
-   <span data-ttu-id="211b5-140">Puede usar la opción **/Connection** o **/Set** en tiempo de ejecución para cargar configuraciones de paquete desde una ubicación distinta de la que ha especificado en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="211b5-140">You can use the **/Connection** or **/Set** option at run time to load package configurations from a location other than the location that you specified at design time.</span></span>  
  
-   <span data-ttu-id="211b5-141">Puede usar la opción **/ConfigFile** para cargar configuraciones adicionales que no ha especificado en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="211b5-141">You can use the **/ConfigFile** option to load additional configurations that you did not specify at design time.</span></span>  
  
 <span data-ttu-id="211b5-142">Sin embargo, estas opciones de la línea de comandos tienen algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="211b5-142">However, these command-line options do have some restrictions:</span></span>  
  
-   <span data-ttu-id="211b5-143">No puede usar la opción **/Set** o **/Connection** para invalidar valores únicos que también se establezcan en una configuración.</span><span class="sxs-lookup"><span data-stu-id="211b5-143">You cannot use the **/Set** or the **/Connection** option to override single values that are also set by a configuration.</span></span>  
  
-   <span data-ttu-id="211b5-144">No puede usar la opción **/ConfigFile** para cargar configuraciones que reemplacen las configuraciones que ha especificado en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="211b5-144">You cannot use the **/ConfigFile** option to load configurations that replace the configurations that you specified at design time.</span></span>  
  
 <span data-ttu-id="211b5-145">Para obtener más información acerca de estas opciones y cómo difiere el comportamiento de estas opciones entre [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] y versiones anteriores, vea [cambios de comportamiento en Integration Services características en SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="211b5-145">For more information about these options, and how the behavior of these options differs between [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] and earlier versions, see [Behavior Changes to Integration Services Features in SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span></span>  
  
## <a name="package-configuration-types"></a><span data-ttu-id="211b5-146">Tipos de configuraciones de paquetes</span><span class="sxs-lookup"><span data-stu-id="211b5-146">Package Configuration Types</span></span>  
 <span data-ttu-id="211b5-147">En la tabla siguiente se describen los tipos de configuraciones de paquetes.</span><span class="sxs-lookup"><span data-stu-id="211b5-147">The following table describes the package configuration types.</span></span>  
  
|<span data-ttu-id="211b5-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="211b5-148">Type</span></span>|<span data-ttu-id="211b5-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="211b5-149">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="211b5-150">Archivo de configuración XML</span><span class="sxs-lookup"><span data-stu-id="211b5-150">XML configuration file</span></span>|<span data-ttu-id="211b5-151">Un archivo XML contiene las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="211b5-151">An XML file contains the configurations.</span></span> <span data-ttu-id="211b5-152">El archivo XML puede incluir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="211b5-152">The XML file can include multiple configurations.</span></span>|  
|<span data-ttu-id="211b5-153">Variable de entorno</span><span class="sxs-lookup"><span data-stu-id="211b5-153">Environment variable</span></span>|<span data-ttu-id="211b5-154">Una variable de entorno contiene la configuración.</span><span class="sxs-lookup"><span data-stu-id="211b5-154">An environment variable contains the configuration.</span></span>|  
|<span data-ttu-id="211b5-155">Entrada del Registro</span><span class="sxs-lookup"><span data-stu-id="211b5-155">Registry entry</span></span>|<span data-ttu-id="211b5-156">Una entrada del Registro contiene la configuración.</span><span class="sxs-lookup"><span data-stu-id="211b5-156">A Registry entry contains the configuration.</span></span>|  
|<span data-ttu-id="211b5-157">Variable de paquete primario</span><span class="sxs-lookup"><span data-stu-id="211b5-157">Parent package variable</span></span>|<span data-ttu-id="211b5-158">Una variable del paquete contiene la configuración.</span><span class="sxs-lookup"><span data-stu-id="211b5-158">A variable in the package contains the configuration.</span></span> <span data-ttu-id="211b5-159">Este tipo de configuración se utiliza habitualmente para actualizar las propiedades de los paquetes secundarios.</span><span class="sxs-lookup"><span data-stu-id="211b5-159">This configuration type is typically used to update properties in child packages.</span></span>|  
|<span data-ttu-id="211b5-160">Tabla [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="211b5-160">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table</span></span>|<span data-ttu-id="211b5-161">Una tabla de una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] contiene la configuración.</span><span class="sxs-lookup"><span data-stu-id="211b5-161">A table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database contains the configuration.</span></span> <span data-ttu-id="211b5-162">La tabla puede incluir varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="211b5-162">The table can include multiple configurations.</span></span>|  
  
### <a name="xml-configuration-files"></a><span data-ttu-id="211b5-163">Archivos de configuración XML</span><span class="sxs-lookup"><span data-stu-id="211b5-163">XML Configuration Files</span></span>  
 <span data-ttu-id="211b5-164">Si selecciona el tipo de configuración **Archivo de configuración XML** , puede crear un archivo de configuración, reutilizar un archivo existente y agregarle configuraciones nuevas, o bien reutilizar un archivo existente sobrescribiendo el contenido actual.</span><span class="sxs-lookup"><span data-stu-id="211b5-164">If you select the **XML configuration file** configuration type, you can create a new configuration file, reuse an existing file and add new configurations, or reuse an existing file but overwrite existing file content.</span></span>  
  
 <span data-ttu-id="211b5-165">Un archivo de configuración XML tiene dos secciones:</span><span class="sxs-lookup"><span data-stu-id="211b5-165">An XML configuration file includes two sections:</span></span>  
  
-   <span data-ttu-id="211b5-166">Un encabezado que contiene información acerca del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="211b5-166">A heading that contains information about the configuration file.</span></span> <span data-ttu-id="211b5-167">Este elemento incluye atributos como por ejemplo, cuándo se creó el archivo y el nombre de la persona que lo generó.</span><span class="sxs-lookup"><span data-stu-id="211b5-167">This element includes attributes such as when the file was created and the name of the person who generated the file.</span></span>  
  
-   <span data-ttu-id="211b5-168">Elementos de configuración que contienen información acerca de cada configuración.</span><span class="sxs-lookup"><span data-stu-id="211b5-168">Configuration elements that contain information about each configuration.</span></span> <span data-ttu-id="211b5-169">Este elemento incluye atributos como la ruta de acceso de la propiedad y el valor configurado de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="211b5-169">This element includes attributes such as the property path and the configured value of a property.</span></span>  
  
 <span data-ttu-id="211b5-170">El siguiente código XML muestra la sintaxis de un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="211b5-170">The following XML code demonstrates the syntax of an XML configuration file.</span></span> <span data-ttu-id="211b5-171">En este ejemplo se muestra una configuración para la propiedad Value de una variable entera llamada `MyVar`.</span><span class="sxs-lookup"><span data-stu-id="211b5-171">This example shows a configuration for the Value property of an integer variable named `MyVar`.</span></span>  
  
```  
<?xml version="1.0"?>  
<DTSConfiguration>  
   <DTSConfigurationHeading>  
      <DTSConfigurationFileInfo  
          GeneratedBy="DomainName\UserName"  
          GeneratedFromPackageName="Package"  
          GeneratedFromPackageID="{2AF06766-817A-4E28-9878-0DE37A150648}"  
          GeneratedDate="2/01/2005 5:58:09 PM"/>  
   </DTSConfigurationHeading>  
   <Configuration ConfiguredType="Property" Path="\Package.Variables[User::MyVar].Value" ValueType="Int32">  
      <ConfiguredValue>0</ConfiguredValue>  
   </Configuration>  
</DTSConfiguration>  
  
```  
  
### <a name="registry-entry"></a><span data-ttu-id="211b5-172">Entrada del Registro</span><span class="sxs-lookup"><span data-stu-id="211b5-172">Registry Entry</span></span>  
 <span data-ttu-id="211b5-173">Si desea usar una entrada del Registro para guardar la configuración, puede usar una clave existente o crear otra en HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="211b5-173">If you want to use a Registry entry to store the configuration, you can either use an existing key or create a new key in HKEY_CURRENT_USER.</span></span> <span data-ttu-id="211b5-174">La clave del Registro que utilice debe tener un valor denominado `Value`.</span><span class="sxs-lookup"><span data-stu-id="211b5-174">The Registry key that you use must have a value named `Value`.</span></span> <span data-ttu-id="211b5-175">El valor puede ser un valor de tipo DWORD o una cadena.</span><span class="sxs-lookup"><span data-stu-id="211b5-175">The value can be a DWORD or a string.</span></span>  
  
 <span data-ttu-id="211b5-176">Si selecciona el tipo de configuración **Entrada del Registro** , debe escribir el nombre de la clave del Registro en el cuadro de texto del Registro.</span><span class="sxs-lookup"><span data-stu-id="211b5-176">If you select the **Registry entry** configuration type, you type the name of the Registry key in the Registry entry box.</span></span> <span data-ttu-id="211b5-177">El formato es \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="211b5-177">The format is \<registry key>.</span></span> <span data-ttu-id="211b5-178">Si quiere usar una clave del Registro que no esté en la raíz de HKEY_CURRENT_USER, use el formato \<Registry key\registry key\\...> para identificarla.</span><span class="sxs-lookup"><span data-stu-id="211b5-178">If you want to use a Registry key that is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span> <span data-ttu-id="211b5-179">Por ejemplo, para usar la clave MyPackage de SSISPackages, escriba `SSISPackages\MyPackage`.</span><span class="sxs-lookup"><span data-stu-id="211b5-179">For example, to use the MyPackage key located in SSISPackages, type `SSISPackages\MyPackage`.</span></span>  
  
### <a name="sql-server"></a><span data-ttu-id="211b5-180">SQL Server</span><span class="sxs-lookup"><span data-stu-id="211b5-180">SQL Server</span></span>  
 <span data-ttu-id="211b5-181">Si selecciona el tipo de configuración **SQL Server** , debe especificar la conexión a la base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en la que desee almacenar las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="211b5-181">If you select the **SQL Server** configuration type, you specify the connection to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database in which you want to store the configurations.</span></span> <span data-ttu-id="211b5-182">Puede guardar las configuraciones en una tabla existente o crear una tabla nueva en la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="211b5-182">You can save the configurations to an existing table or create a new table in the specified database.</span></span>  
  
 <span data-ttu-id="211b5-183">La siguiente instrucción SQL muestra la instrucción CREATE TABLE predeterminada que proporciona el Asistente para la configuración de paquetes.</span><span class="sxs-lookup"><span data-stu-id="211b5-183">The following SQL statement shows the default CREATE TABLE statement that the Package Configuration Wizard provides.</span></span>  
  
```  
CREATE TABLE [dbo].[SSIS Configurations]  
(  
ConfigurationFilter NVARCHAR(255) NOT NULL,  
ConfiguredValue NVARCHAR(255) NULL,  
PackagePath NVARCHAR(255) NOT NULL,  
ConfiguredValueType NVARCHAR(20) NOT NULL  
)  
  
```  
  
 <span data-ttu-id="211b5-184">El nombre que asigna a la configuración es el valor que se almacena en la columna **ConfigurationFilter** .</span><span class="sxs-lookup"><span data-stu-id="211b5-184">The name that you provide for the configuration is the value stored in the **ConfigurationFilter** column.</span></span>  
  
## <a name="direct-and-indirect-configurations"></a><span data-ttu-id="211b5-185">Configuraciones directas e indirectas</span><span class="sxs-lookup"><span data-stu-id="211b5-185">Direct and Indirect Configurations</span></span>  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="211b5-186">proporciona configuraciones directas e indirectas.</span><span class="sxs-lookup"><span data-stu-id="211b5-186">provides direct and indirect configurations.</span></span> <span data-ttu-id="211b5-187">Si especifica las configuraciones directamente, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] crea un vínculo directo entre el elemento de configuración y la propiedad del objeto de paquete.</span><span class="sxs-lookup"><span data-stu-id="211b5-187">If you specify configurations directly, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] creates a direct link between the configuration item and the package object property.</span></span> <span data-ttu-id="211b5-188">Las configuraciones directas son una opción mejor cuando la ubicación del origen no cambia.</span><span class="sxs-lookup"><span data-stu-id="211b5-188">Direct configurations are a better choice when the location of the source does not change.</span></span> <span data-ttu-id="211b5-189">Por ejemplo, si está seguro de que todas las implementaciones del paquete utilizarán la misma ruta de acceso al archivo, puede especificar un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="211b5-189">For example, if you are sure that all deployments in the package use the same file path, you can specify an XML configuration file.</span></span>  
  
 <span data-ttu-id="211b5-190">Las configuraciones indirectas utilizan variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="211b5-190">Indirect configurations use environment variables.</span></span> <span data-ttu-id="211b5-191">En lugar de especificar el entorno de configuración directamente, la configuración apunta a una variable de entorno, que a su vez contiene el valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="211b5-191">Instead of specifying the configuration setting directly, the configuration points to an environment variable, which in turn contains the configuration value.</span></span> <span data-ttu-id="211b5-192">Las configuraciones indirectas son una opción mejor cuando la ubicación de la configuración puede cambiar en cada implementación de un paquete.</span><span class="sxs-lookup"><span data-stu-id="211b5-192">Using indirect configurations is a better choice when the location of the configuration can change for each deployment of a package.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="211b5-193">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="211b5-193">Related Tasks</span></span>  
 [<span data-ttu-id="211b5-194">Crear configuraciones de paquetes</span><span class="sxs-lookup"><span data-stu-id="211b5-194">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
## <a name="related-content"></a><span data-ttu-id="211b5-195">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="211b5-195">Related Content</span></span>  
  
-   <span data-ttu-id="211b5-196">Artículo técnico con una [introducción a las configuraciones de paquetes de Integration Services](https://go.microsoft.com/fwlink/?LinkId=165643), en msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="211b5-196">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="211b5-197">Entrada de blog, [crear paquetes en configuraciones de paquetes de código](https://go.microsoft.com/fwlink/?LinkId=217663), en www.sqlis.com.</span><span class="sxs-lookup"><span data-stu-id="211b5-197">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="211b5-198">Entrada de blog, [ejemplo de API: agregar mediante programación un archivo de configuración a un paquete](https://go.microsoft.com/fwlink/?LinkId=217664), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="211b5-198">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
  
