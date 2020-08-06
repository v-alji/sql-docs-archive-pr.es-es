---
title: Referencia de la interfaz de usuario del Asistente para configuración de paquetes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.configwizard.selectobjects.f1
- sql12.dts.configwizard.selecconfigtype.f1
- sql12.dts.configwizard.finishdtsconfiguration.f1
- sql12.dts.configwizard.welcome.f1
ms.assetid: adca6938-6d5a-40ec-950e-dceb79d044fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 222c5f58ca4e942dd23909b433ab346c500fceed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676579"
---
# <a name="package-configuration-wizard-ui-reference"></a><span data-ttu-id="a51bd-102">Referencia de la interfaz de usuario del Asistente para la configuración de paquetes</span><span class="sxs-lookup"><span data-stu-id="a51bd-102">Package Configuration Wizard UI Reference</span></span>
  <span data-ttu-id="a51bd-103">Use el **Asistente para la configuración de paquetes** para crear configuraciones que actualizan las propiedades de un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y sus objetos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a51bd-103">Use the **Package Configuration Wizard** to create configurations that update the properties of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and its objects at run time.</span></span> <span data-ttu-id="a51bd-104">Este asistente se ejecuta al agregar una nueva configuración o modificar una existente en el cuadro de diálogo **Organizador de configuraciones de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="a51bd-104">This wizard runs when you add a new configuration or modify an existing one in the **Package Configurations Organizer** dialog box.</span></span> <span data-ttu-id="a51bd-105">Para abrir el cuadro de diálogo **Organizador de configuraciones de paquetes** , seleccione **Configuraciones de paquetes** en el menú **SSIS** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a51bd-105">To open the **Package Configurations Organizer** dialog box, select **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="a51bd-106">Para obtener más información, vea [Crear configuraciones de paquetes](../../2014/integration-services/create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="a51bd-106">For more information, see [Create Package Configurations](../../2014/integration-services/create-package-configurations.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a51bd-107">Hay configuraciones disponibles para el modelo de implementación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="a51bd-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="a51bd-108">Se usan parámetros en lugar de configuraciones para el modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="a51bd-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="a51bd-109">El modelo de implementación de proyectos le permite implementar proyectos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a51bd-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="a51bd-110">Para obtener más información acerca de los modelos de implementación, vea [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="a51bd-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="a51bd-111">En las siguientes secciones se describen las páginas del asistente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-111">The following sections describe pages of the Wizard.</span></span>  
  
## <a name="welcome-to-the-package-configuration-wizard-page"></a><span data-ttu-id="a51bd-112">Asistente para la configuración de paquetes (página principal)</span><span class="sxs-lookup"><span data-stu-id="a51bd-112">Welcome to the Package Configuration Wizard Page</span></span>  
 <span data-ttu-id="a51bd-113">Use el **Asistente para la configuración de SSIS** para crear configuraciones que actualizan las propiedades de un paquete y sus objetos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a51bd-113">Use the **SSIS Configuration Wizard** to create configurations that update the properties of a package and its objects at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="a51bd-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="a51bd-114">Options</span></span>  
 <span data-ttu-id="a51bd-115">**No volver a mostrar esta página**</span><span class="sxs-lookup"><span data-stu-id="a51bd-115">**Don't show this page again**</span></span>  
 <span data-ttu-id="a51bd-116">Omite la página de bienvenida la próxima vez que abre el asistente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-116">Skip the welcome page the next time you open the wizard.</span></span>  
  
 <span data-ttu-id="a51bd-117">**Siguiente**</span><span class="sxs-lookup"><span data-stu-id="a51bd-117">**Next**</span></span>  
 <span data-ttu-id="a51bd-118">Avanza a la página siguiente del asistente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-118">Go the next page in the wizard.</span></span>  
  
## <a name="select-configuration-type-page"></a><span data-ttu-id="a51bd-119">Página Seleccionar tipo de configuración</span><span class="sxs-lookup"><span data-stu-id="a51bd-119">Select Configuration Type Page</span></span>  
 <span data-ttu-id="a51bd-120">Use la página **Seleccionar tipo de configuración** para especificar el tipo de configuración que se creará.</span><span class="sxs-lookup"><span data-stu-id="a51bd-120">Use the **Select Configuration Type** page to specify the type of configuration to create.</span></span>  
  
 <span data-ttu-id="a51bd-121">Si necesita obtener información adicional para determinar el tipo de configuración que debe utilizar, vea [Package Configurations](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="a51bd-121">If you need additional information to determine which type of configuration to use, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="a51bd-122">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="a51bd-122">Static Options</span></span>  
 <span data-ttu-id="a51bd-123">**Tipo de configuración**</span><span class="sxs-lookup"><span data-stu-id="a51bd-123">**Configuration type**</span></span>  
 <span data-ttu-id="a51bd-124">Seleccione el tipo de origen en el que se almacenará la configuración, utilizando las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a51bd-124">Select the type of source in which to store the configuration, using the following options:</span></span>  
  
|<span data-ttu-id="a51bd-125">Value</span><span class="sxs-lookup"><span data-stu-id="a51bd-125">Value</span></span>|<span data-ttu-id="a51bd-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="a51bd-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a51bd-127">**Archivo de configuración XML**</span><span class="sxs-lookup"><span data-stu-id="a51bd-127">**XML configuration file**</span></span>|<span data-ttu-id="a51bd-128">Almacenar la configuración como un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a51bd-128">Store the configuration as an XML file.</span></span> <span data-ttu-id="a51bd-129">Al seleccionar este valor se muestran las opciones dinámicas de la sección **Tipo de configuración**.</span><span class="sxs-lookup"><span data-stu-id="a51bd-129">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="a51bd-130">**Variable de entorno**</span><span class="sxs-lookup"><span data-stu-id="a51bd-130">**Environment variable**</span></span>|<span data-ttu-id="a51bd-131">Almacenar la configuración en una de las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="a51bd-131">Store the configuration in one of the environment variables.</span></span> <span data-ttu-id="a51bd-132">Al seleccionar este valor se muestran las opciones dinámicas de la sección **Tipo de configuración**.</span><span class="sxs-lookup"><span data-stu-id="a51bd-132">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="a51bd-133">**Entrada del Registro**</span><span class="sxs-lookup"><span data-stu-id="a51bd-133">**Registry entry**</span></span>|<span data-ttu-id="a51bd-134">Almacenar la configuración en el Registro.</span><span class="sxs-lookup"><span data-stu-id="a51bd-134">Store the configuration in the Registry.</span></span> <span data-ttu-id="a51bd-135">Al seleccionar este valor se muestran las opciones dinámicas de la sección **Tipo de configuración**.</span><span class="sxs-lookup"><span data-stu-id="a51bd-135">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="a51bd-136">**Variable de paquete primario**</span><span class="sxs-lookup"><span data-stu-id="a51bd-136">**Parent package variable**</span></span>|<span data-ttu-id="a51bd-137">Almacenar la configuración como una variable en el paquete que contiene la tarea.</span><span class="sxs-lookup"><span data-stu-id="a51bd-137">Store the configuration as a variable in the package that contains the task.</span></span>  <span data-ttu-id="a51bd-138">Al seleccionar este valor se muestran las opciones dinámicas de la sección **Tipo de configuración**.</span><span class="sxs-lookup"><span data-stu-id="a51bd-138">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="a51bd-139">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a51bd-139">**SQL Server**</span></span>|<span data-ttu-id="a51bd-140">Almacenar la configuración en una tabla en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a51bd-140">Store the configuration in a table in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a51bd-141">Al seleccionar este valor se muestran las opciones dinámicas de la sección **Tipo de configuración**.</span><span class="sxs-lookup"><span data-stu-id="a51bd-141">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
  
 <span data-ttu-id="a51bd-142">**Siguiente**</span><span class="sxs-lookup"><span data-stu-id="a51bd-142">**Next**</span></span>  
 <span data-ttu-id="a51bd-143">Muestra la siguiente página en la secuencia del asistente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-143">View the next page in the wizard sequence.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="a51bd-144">Opciones dinámicas</span><span class="sxs-lookup"><span data-stu-id="a51bd-144">Dynamic Options</span></span>  
  
#### <a name="configuration-type-option--xml-configuration-file"></a><span data-ttu-id="a51bd-145">Opción de tipo de configuración = Archivo de configuración XML</span><span class="sxs-lookup"><span data-stu-id="a51bd-145">Configuration Type Option = XML Configuration File</span></span>  
 <span data-ttu-id="a51bd-146">**Especificar valores de configuración directamente**</span><span class="sxs-lookup"><span data-stu-id="a51bd-146">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="a51bd-147">Se utiliza para especificar la configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-147">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="a51bd-148">Value</span><span class="sxs-lookup"><span data-stu-id="a51bd-148">Value</span></span>|<span data-ttu-id="a51bd-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="a51bd-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a51bd-150">**Nombre del archivo de configuración**</span><span class="sxs-lookup"><span data-stu-id="a51bd-150">**Configuration file name**</span></span>|<span data-ttu-id="a51bd-151">Escriba la ruta de acceso del archivo de configuración que genera el asistente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-151">Type the path of the configuration file that the wizard generates.</span></span>|  
|<span data-ttu-id="a51bd-152">**Browse**</span><span class="sxs-lookup"><span data-stu-id="a51bd-152">**Browse**</span></span>|<span data-ttu-id="a51bd-153">Use el cuadro de diálogo **Seleccionar ubicación del archivo de configuración** para especificar la ruta de acceso del archivo de configuración que genera el asistente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-153">Use the **Select Configuration File Location** dialog box to specify the path of the configuration file that the wizard generates.</span></span> <span data-ttu-id="a51bd-154">Si el archivo no existe, el asistente lo crea.</span><span class="sxs-lookup"><span data-stu-id="a51bd-154">If the file does not exist, it is created by the wizard.</span></span>|  
  
 <span data-ttu-id="a51bd-155">**La ubicación de configuración se almacena en una variable de entorno**</span><span class="sxs-lookup"><span data-stu-id="a51bd-155">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="a51bd-156">Se usa para especificar la variable de entorno donde se almacena la configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-156">Use to specify the environment variable in which to store the configuration.</span></span>  
  
|<span data-ttu-id="a51bd-157">Value</span><span class="sxs-lookup"><span data-stu-id="a51bd-157">Value</span></span>|<span data-ttu-id="a51bd-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="a51bd-158">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a51bd-159">**Variable de entorno**</span><span class="sxs-lookup"><span data-stu-id="a51bd-159">**Environment variable**</span></span>|<span data-ttu-id="a51bd-160">Seleccione una variable de entorno de la lista.</span><span class="sxs-lookup"><span data-stu-id="a51bd-160">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--environment-variable"></a><span data-ttu-id="a51bd-161">Opción de tipo de configuración = Variable de entorno</span><span class="sxs-lookup"><span data-stu-id="a51bd-161">Configuration Type Option = Environment Variable</span></span>  
 <span data-ttu-id="a51bd-162">**Variable de entorno**</span><span class="sxs-lookup"><span data-stu-id="a51bd-162">**Environment variable**</span></span>  
 <span data-ttu-id="a51bd-163">Seleccione la variable de entorno que contiene la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-163">Select the environment variable that contains the configuration information.</span></span>  
  
#### <a name="configuration-type-option--registry-entry"></a><span data-ttu-id="a51bd-164">Opción de tipo de configuración = Entrada del Registro</span><span class="sxs-lookup"><span data-stu-id="a51bd-164">Configuration Type Option = Registry Entry</span></span>  
 <span data-ttu-id="a51bd-165">**Especificar valores de configuración directamente**</span><span class="sxs-lookup"><span data-stu-id="a51bd-165">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="a51bd-166">Se utiliza para especificar la configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-166">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="a51bd-167">Value</span><span class="sxs-lookup"><span data-stu-id="a51bd-167">Value</span></span>|<span data-ttu-id="a51bd-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="a51bd-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a51bd-169">**Entrada del Registro**</span><span class="sxs-lookup"><span data-stu-id="a51bd-169">**Registry entry**</span></span>|<span data-ttu-id="a51bd-170">Escriba la clave del Registro que contiene la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-170">Type the Registry key that contains the configuration information.</span></span> <span data-ttu-id="a51bd-171">El formato es \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="a51bd-171">The format is \<registry key>.</span></span><br /><br /> <span data-ttu-id="a51bd-172">La clave del Registro ya debe existir en HKEY_CURRENT_USER y tener un valor con el nombre Value.</span><span class="sxs-lookup"><span data-stu-id="a51bd-172">The Registry key must already exist in HKEY_CURRENT_USER and have a value named Value.</span></span> <span data-ttu-id="a51bd-173">El valor puede ser un valor de tipo DWORD o una cadena.</span><span class="sxs-lookup"><span data-stu-id="a51bd-173">The value can be a DWORD or a string.</span></span><br /><br /> <span data-ttu-id="a51bd-174">Si quiere usar una clave del Registro que no esté en la raíz de HKEY_CURRENT_USER, use el formato \<Registry key\registry key\\...> para identificarla.</span><span class="sxs-lookup"><span data-stu-id="a51bd-174">If you want to use a Registry key is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span>|  
  
 <span data-ttu-id="a51bd-175">**La ubicación de configuración se almacena en una variable de entorno**</span><span class="sxs-lookup"><span data-stu-id="a51bd-175">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="a51bd-176">Se utiliza para especificar la variable de entorno donde debe almacenarse la configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-176">Use to specify the environment variable to store the configuration in.</span></span>  
  
|<span data-ttu-id="a51bd-177">Value</span><span class="sxs-lookup"><span data-stu-id="a51bd-177">Value</span></span>|<span data-ttu-id="a51bd-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="a51bd-178">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a51bd-179">**Variable de entorno**</span><span class="sxs-lookup"><span data-stu-id="a51bd-179">**Environment variable**</span></span>|<span data-ttu-id="a51bd-180">Seleccione una variable de entorno de la lista.</span><span class="sxs-lookup"><span data-stu-id="a51bd-180">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--parent-package-variable"></a><span data-ttu-id="a51bd-181">Opción de tipo de configuración = Variable de paquete primario</span><span class="sxs-lookup"><span data-stu-id="a51bd-181">Configuration Type Option = Parent Package Variable</span></span>  
 <span data-ttu-id="a51bd-182">**Especificar valores de configuración directamente**</span><span class="sxs-lookup"><span data-stu-id="a51bd-182">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="a51bd-183">Se utiliza para especificar la configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-183">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="a51bd-184">Value</span><span class="sxs-lookup"><span data-stu-id="a51bd-184">Value</span></span>|<span data-ttu-id="a51bd-185">Descripción</span><span class="sxs-lookup"><span data-stu-id="a51bd-185">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a51bd-186">**Variable primaria**</span><span class="sxs-lookup"><span data-stu-id="a51bd-186">**Parent variable**</span></span>|<span data-ttu-id="a51bd-187">Especifique la variable del paquete primario que contiene la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-187">Specify the variable in the parent package that contains the configuration information.</span></span>|  
  
 <span data-ttu-id="a51bd-188">**La ubicación de configuración se almacena en una variable de entorno**</span><span class="sxs-lookup"><span data-stu-id="a51bd-188">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="a51bd-189">Se usa para especificar la variable de entorno donde se almacena la configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-189">Use to specify the environment variable that stores the configuration.</span></span>  
  
|<span data-ttu-id="a51bd-190">Value</span><span class="sxs-lookup"><span data-stu-id="a51bd-190">Value</span></span>|<span data-ttu-id="a51bd-191">Descripción</span><span class="sxs-lookup"><span data-stu-id="a51bd-191">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a51bd-192">**Variable de entorno**</span><span class="sxs-lookup"><span data-stu-id="a51bd-192">**Environment variable**</span></span>|<span data-ttu-id="a51bd-193">Seleccione una variable de entorno de la lista.</span><span class="sxs-lookup"><span data-stu-id="a51bd-193">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-options--sql-server"></a><span data-ttu-id="a51bd-194">Opción de tipo de configuración = SQL Server</span><span class="sxs-lookup"><span data-stu-id="a51bd-194">Configuration Type Options = SQL Server</span></span>  
 <span data-ttu-id="a51bd-195">**Especificar valores de configuración directamente**</span><span class="sxs-lookup"><span data-stu-id="a51bd-195">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="a51bd-196">Se utiliza para especificar la configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-196">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="a51bd-197">Value</span><span class="sxs-lookup"><span data-stu-id="a51bd-197">Value</span></span>|<span data-ttu-id="a51bd-198">Descripción</span><span class="sxs-lookup"><span data-stu-id="a51bd-198">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a51bd-199">**Connection**</span><span class="sxs-lookup"><span data-stu-id="a51bd-199">**Connection**</span></span>|<span data-ttu-id="a51bd-200">Seleccione una conexión de la lista o haga clic en **Nueva** para crear una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="a51bd-200">Select a connection from the list, or click **New** to create a new connection.</span></span>|  
|<span data-ttu-id="a51bd-201">**Tabla de configuración**</span><span class="sxs-lookup"><span data-stu-id="a51bd-201">**Configuration table**</span></span>|<span data-ttu-id="a51bd-202">Seleccione una tabla existente o haga clic en **Nueva** para escribir una instrucción SQL que cree la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="a51bd-202">Select an existing table, or click **New** to write a SQL statement that creates a new table.</span></span>|  
|<span data-ttu-id="a51bd-203">**Filtro de la configuración**</span><span class="sxs-lookup"><span data-stu-id="a51bd-203">**Configuration filter**</span></span>|<span data-ttu-id="a51bd-204">Seleccione un nombre de configuración existente o escriba uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="a51bd-204">Select an existing configuration name or type a new name.</span></span><br /><br /> <span data-ttu-id="a51bd-205">Muchas de las configuraciones de SQL Server se pueden almacenar en la misma tabla, y cada configuración puede incluir varios elementos de configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-205">Many SQL Server configurations can be stored in the same table, and each configuration can include multiple configuration items.</span></span><br /><br /> <span data-ttu-id="a51bd-206">Este valor definido por el usuario se almacena en la tabla para identificar los elementos de configuración de una configuración determinada.</span><span class="sxs-lookup"><span data-stu-id="a51bd-206">This user-defined value is stored in the table to identify configuration items that belong to a particular configuration</span></span>|  
  
 <span data-ttu-id="a51bd-207">**La ubicación de configuración se almacena en una variable de entorno**</span><span class="sxs-lookup"><span data-stu-id="a51bd-207">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="a51bd-208">Se utiliza para especificar la variable de entorno donde se almacena la configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-208">Use to specify the environment variable where the configuration is stored.</span></span>  
  
|<span data-ttu-id="a51bd-209">Value</span><span class="sxs-lookup"><span data-stu-id="a51bd-209">Value</span></span>|<span data-ttu-id="a51bd-210">Descripción</span><span class="sxs-lookup"><span data-stu-id="a51bd-210">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a51bd-211">**Variable de entorno**</span><span class="sxs-lookup"><span data-stu-id="a51bd-211">**Environment variable**</span></span>|<span data-ttu-id="a51bd-212">Seleccione una variable de entorno de la lista.</span><span class="sxs-lookup"><span data-stu-id="a51bd-212">Select an environment variable from the list.</span></span>|  
  
## <a name="select-objects-to-export-page"></a><span data-ttu-id="a51bd-213">Página Seleccionar objetos para la exportación</span><span class="sxs-lookup"><span data-stu-id="a51bd-213">Select Objects to Export Page</span></span>  
 <span data-ttu-id="a51bd-214">Use la página **Seleccionar propiedad de destino o Seleccionar propiedades para la exportación** para especificar las propiedades de objetos contenidas en la configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-214">Use the **Select Target Property or Select Properties to Export** page to specify the object properties that the configuration contains.</span></span> <span data-ttu-id="a51bd-215">La posibilidad de seleccionar varias propiedades solo está disponible si se selecciona el tipo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="a51bd-215">The ability to select multiple properties is available only if you select the XML configuration type.</span></span>  
  
### <a name="options"></a><span data-ttu-id="a51bd-216">Opciones</span><span class="sxs-lookup"><span data-stu-id="a51bd-216">Options</span></span>  
 <span data-ttu-id="a51bd-217">**Objetos**</span><span class="sxs-lookup"><span data-stu-id="a51bd-217">**Objects**</span></span>  
 <span data-ttu-id="a51bd-218">Expanda la jerarquía de paquetes y seleccione las propiedades que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="a51bd-218">Expand the package hierarchy and select the properties to export.</span></span>  
  
 <span data-ttu-id="a51bd-219">**Atributos de propiedad**</span><span class="sxs-lookup"><span data-stu-id="a51bd-219">**Property attributes**</span></span>  
 <span data-ttu-id="a51bd-220">Permite ver los atributos de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="a51bd-220">View the attributes of a property.</span></span>  
  
 <span data-ttu-id="a51bd-221">**Siguiente**</span><span class="sxs-lookup"><span data-stu-id="a51bd-221">**Next**</span></span>  
 <span data-ttu-id="a51bd-222">Va a la siguiente página del asistente.</span><span class="sxs-lookup"><span data-stu-id="a51bd-222">Go to the next page in the wizard.</span></span>  
  
## <a name="completing-the-wizard-page"></a><span data-ttu-id="a51bd-223">Página Finalización del asistente</span><span class="sxs-lookup"><span data-stu-id="a51bd-223">Completing the Wizard Page</span></span>  
 <span data-ttu-id="a51bd-224">Utilice la página **Finalización del asistente** para asignar un nombre a la configuración y ver los valores utilizados por el asistente para crear la configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-224">Use the **Completing the Wizard** page to provide a name for the configuration and view settings used by the wizard to create the configuration.</span></span> <span data-ttu-id="a51bd-225">Una vez que finaliza el asistente, se muestra el **Organizador de configuraciones de paquetes** , que enumera todas las configuraciones para el paquete.</span><span class="sxs-lookup"><span data-stu-id="a51bd-225">After the wizard completes, the **Package Configurations Organizer** is displayed, which lists all configurations for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="a51bd-226">Opciones</span><span class="sxs-lookup"><span data-stu-id="a51bd-226">Options</span></span>  
 <span data-ttu-id="a51bd-227">**Nombre de la configuración**</span><span class="sxs-lookup"><span data-stu-id="a51bd-227">**Configuration name**</span></span>  
 <span data-ttu-id="a51bd-228">Escriba el nombre de la configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-228">Type the name of the configuration.</span></span>  
  
 <span data-ttu-id="a51bd-229">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="a51bd-229">**Preview**</span></span>  
 <span data-ttu-id="a51bd-230">Muestra los valores utilizados por el asistente para crear la configuración.</span><span class="sxs-lookup"><span data-stu-id="a51bd-230">View the settings used by the wizard to create the configuration.</span></span>  
  
 <span data-ttu-id="a51bd-231">**Finalizar**</span><span class="sxs-lookup"><span data-stu-id="a51bd-231">**Finish**</span></span>  
 <span data-ttu-id="a51bd-232">Crea la configuración y sale del **Asistente para configuración de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="a51bd-232">Create the configuration and exit the **Package Configuration Wizard**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51bd-233">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a51bd-233">See Also</span></span>  
 [<span data-ttu-id="a51bd-234">Crear configuraciones de paquetes</span><span class="sxs-lookup"><span data-stu-id="a51bd-234">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
