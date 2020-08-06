---
title: Crear configuraciones de paquetes | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, configurations
- Package Configurations Organizer dialog box
- SSIS packages, configurations
- Integration Services packages, configurations
- configurations [Integration Services]
- packages [Integration Services], configurations
- deploying packages [Integration Services], configurations
ms.assetid: 91ac0347-f908-44f5-bd3d-115790223af4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58c93242c9ef51a5e00076bd367e46b43187098e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671604"
---
# <a name="create-package-configurations"></a><span data-ttu-id="07f84-102">Crear configuraciones de paquetes</span><span class="sxs-lookup"><span data-stu-id="07f84-102">Create Package Configurations</span></span>
  <span data-ttu-id="07f84-103">Puede crear configuraciones de paquetes con el cuadro de diálogo **Organizador de configuraciones de paquetes** y el Asistente para la configuración de paquetes.</span><span class="sxs-lookup"><span data-stu-id="07f84-103">You create package configurations by using the **Package Configuration Organizer** dialog box and the Package Configuration Wizard.</span></span> <span data-ttu-id="07f84-104">Para tener acceso a estas herramientas, haga clic en **Configuraciones de paquetes** en el menú **SSI** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07f84-104">To access these tools, click **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07f84-105">También puede tener acceso al **organizador de configuraciones de paquetes**haciendo clic en el botón de puntos suspensivos junto a la propiedad de **configuración** .</span><span class="sxs-lookup"><span data-stu-id="07f84-105">You can also access the **Package Configuration Organizer**, by clicking the ellipsis button next to the **Configuration** property.</span></span> <span data-ttu-id="07f84-106">La propiedad Configuración aparece en la ventana de propiedades del paquete.</span><span class="sxs-lookup"><span data-stu-id="07f84-106">The Configuration property appears in the properties window for the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07f84-107">Hay configuraciones disponibles para el modelo de implementación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="07f84-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="07f84-108">Se usan parámetros en lugar de configuraciones para el modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="07f84-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="07f84-109">El modelo de implementación de proyectos le permite implementar proyectos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07f84-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="07f84-110">Para obtener más información acerca de los modelos de implementación, vea [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="07f84-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="07f84-111">En el cuadro de diálogo **Organizador de configuraciones de paquetes** , puede habilitar paquetes para usar configuraciones, agregar y eliminar configuraciones, y establecer el orden preferido en que se deben cargar las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="07f84-111">In the **Package Configuration Organizer** dialog box, you can enable packages to use configurations, add and delete configurations, and set the preferred order in which configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07f84-112">Cuando las configuraciones de paquetes se cargan en el orden preferido, se cargan de arriba a abajo, según la lista que se muestra en el cuadro de diálogo **Organizador de configuraciones de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="07f84-112">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="07f84-113">Sin embargo, en tiempo de ejecución, las configuraciones de paquetes podrían no cargarse en el orden preferido.</span><span class="sxs-lookup"><span data-stu-id="07f84-113">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="07f84-114">Concretamente, las configuraciones de paquetes principales se cargan después de las configuraciones de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="07f84-114">In particular, parent package configurations load after configurations of other types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07f84-115">Si varias configuraciones establecen la misma propiedad de objeto, el último valor cargado se utiliza en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="07f84-115">If multiple configurations set the same object property, the value loaded last is used at run time.</span></span>  
  
 <span data-ttu-id="07f84-116">En el cuadro de diálogo **Organizador de configuraciones de paquetes** , puede ejecutar el Asistente para la configuración de paquetes, que guía al usuario para crear una configuración.</span><span class="sxs-lookup"><span data-stu-id="07f84-116">From the **Package Configuration Organizer** dialog box, you run the Package Configuration Wizard, which guides you through the steps to create a configuration.</span></span> <span data-ttu-id="07f84-117">Para ejecutar el Asistente para la configuración de paquetes, agregue una nueva configuración en el cuadro de diálogo **Organizador de configuraciones de paquetes** o modifique una existente.</span><span class="sxs-lookup"><span data-stu-id="07f84-117">To run the Package Configuration Wizard, add a new configuration in the **Package Configurations Organizer** dialog box or edit an existing one.</span></span> <span data-ttu-id="07f84-118">En las páginas del asistente, puede elegir el tipo de configuración, seleccionar si desea tener acceso directo a la configuración o utilizar variables de entorno, así como seleccionar las propiedades que desee guardar en la configuración.</span><span class="sxs-lookup"><span data-stu-id="07f84-118">On the wizard pages, you choose the configuration type, select whether you want to access the configuration directly or use environment variables, and select the properties to save in the configuration.</span></span>  
  
 <span data-ttu-id="07f84-119">En el ejemplo siguiente se muestran las propiedades de destino de una variable y un paquete tal como aparecen en la página de finalización del Asistente para la configuración de paquetes:</span><span class="sxs-lookup"><span data-stu-id="07f84-119">The following example shows the target properties of a variable and a package as they appear on the Completing the Wizard page of the Package Configuration Wizard.:</span></span>  
  
 <span data-ttu-id="07f84-120">\Package.Variables[User::TodaysDate].Properties[RaiseChangedEvent]</span><span class="sxs-lookup"><span data-stu-id="07f84-120">\Package.Variables[User::TodaysDate].Properties[RaiseChangedEvent]</span></span>  
  
 <span data-ttu-id="07f84-121">\Package.Properties[MaximumErrorCount]</span><span class="sxs-lookup"><span data-stu-id="07f84-121">\Package.Properties[MaximumErrorCount]</span></span>  
  
 <span data-ttu-id="07f84-122">\Package.Properties[LoggingMode]</span><span class="sxs-lookup"><span data-stu-id="07f84-122">\Package.Properties[LoggingMode]</span></span>  
  
 <span data-ttu-id="07f84-123">\Package.Properties[LocaleID]</span><span class="sxs-lookup"><span data-stu-id="07f84-123">\Package.Properties[LocaleID]</span></span>  
  
 <span data-ttu-id="07f84-124">\Package\My SQL Task.Variables[User::varTableName].Properties[Value]</span><span class="sxs-lookup"><span data-stu-id="07f84-124">\Package\My SQL Task.Variables[User::varTableName].Properties[Value]</span></span>  
  
 <span data-ttu-id="07f84-125">En este ejemplo, la configuración actualiza estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="07f84-125">In this example, the configuration updates these properties:</span></span>  
  
-   <span data-ttu-id="07f84-126">La propiedad RaiseChangedEvent de una variable definida por el usuario, `TodaysDate`.</span><span class="sxs-lookup"><span data-stu-id="07f84-126">The RaiseChangedEvent property of user-defined variable, `TodaysDate`.</span></span>  
  
-   <span data-ttu-id="07f84-127">Las propiedades MaximumErrorCount, LoggingMode y LocaleID del paquete.</span><span class="sxs-lookup"><span data-stu-id="07f84-127">The MaximumErrorCount, LoggingMode, and LocaleID properties of the package.</span></span>  
  
-   <span data-ttu-id="07f84-128">La propiedad Value de una variable definida por el usuario, `varTableName`, en el ámbito de la tarea, My SQL Task.</span><span class="sxs-lookup"><span data-stu-id="07f84-128">The Value property of user-defined variable, `varTableName`, within scope of the task, My SQL Task.</span></span>  
  
 <span data-ttu-id="07f84-129">"\Package" representa la raíz y los puntos (.) separan los objetos que definen la ruta de acceso a la propiedad que actualiza la configuración</span><span class="sxs-lookup"><span data-stu-id="07f84-129">The "\Package" represents the root, and periods (.) separate the objects that define the path to the property that the configuration updates.</span></span> <span data-ttu-id="07f84-130">Los nombres de variables y propiedades se ponen entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="07f84-130">The names of variables and properties are enclosed in brackets.</span></span> <span data-ttu-id="07f84-131">El término Package se usa siempre en configuración, independientemente del nombre del paquete; sin embargo, los demás objetos de la ruta utilizan sus nombres definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="07f84-131">The term Package is always used in configuration, regardless of the package name; however, all other objects in the path use their user-defined names.</span></span>  
  
 <span data-ttu-id="07f84-132">Cuando finaliza el asistente, la nueva configuración se agrega a la lista de configuraciones del cuadro de diálogo **Organizador de configuraciones de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="07f84-132">After the wizard finishes, the new configuration is added to the configuration list in the **Package Configuration Organizer** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07f84-133">La última página del Asistente para la configuración de paquetes, la página Finalización del asistente, enumera las propiedades de destino de la configuración.</span><span class="sxs-lookup"><span data-stu-id="07f84-133">The last page in the Package Configuration Wizard, Completing the Wizard, lists the target properties in the configuration.</span></span> <span data-ttu-id="07f84-134">Si quiere actualizar propiedades cuando ejecuta paquetes mediante la utilidad del símbolo del sistema **dtexec** , puede generar las cadenas que representan las rutas de acceso a las propiedades con el Asistente para configuración de paquetes, y, después, copiarlas y pegarlas en la ventana del símbolo del sistema para usarlas con la opción establecida de **dtexec**.</span><span class="sxs-lookup"><span data-stu-id="07f84-134">If you want to update properties when you run packages by using the **dtexec** command prompt utility, you can generate the strings that represent the property paths by running the Package Configuration Wizard and then copy and paste them into the command prompt window for use with the set option of **dtexec.**</span></span>  
  
 <span data-ttu-id="07f84-135">En la tabla siguiente se describen las columnas de la lista de configuraciones del cuadro de diálogo **Organizador de configuraciones de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="07f84-135">The following table describes the columns in the configuration list in the **Package Configuration Organizer** dialog box.</span></span>  
  
|<span data-ttu-id="07f84-136">Columna</span><span class="sxs-lookup"><span data-stu-id="07f84-136">Column</span></span>|<span data-ttu-id="07f84-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="07f84-137">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="07f84-138">**Nombre de la configuración**</span><span class="sxs-lookup"><span data-stu-id="07f84-138">**Configuration Name**</span></span>|<span data-ttu-id="07f84-139">Nombre de la configuración.</span><span class="sxs-lookup"><span data-stu-id="07f84-139">The name of the configuration.</span></span>|  
|<span data-ttu-id="07f84-140">**Tipo de configuración**</span><span class="sxs-lookup"><span data-stu-id="07f84-140">**Configuration Type**</span></span>|<span data-ttu-id="07f84-141">Tipo de configuración.</span><span class="sxs-lookup"><span data-stu-id="07f84-141">The configuration type.</span></span>|  
|<span data-ttu-id="07f84-142">**Cadena de configuración**</span><span class="sxs-lookup"><span data-stu-id="07f84-142">**Configuration String**</span></span>|<span data-ttu-id="07f84-143">Ubicación de la configuración.</span><span class="sxs-lookup"><span data-stu-id="07f84-143">The location of the configuration.</span></span> <span data-ttu-id="07f84-144">La ubicación puede ser una ruta de acceso, una variable de entorno, una clave del Registro, un nombre de variable de paquete primario o una tabla de una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07f84-144">The location can be a path, an environment variable, a Registry key, a parent package variable name, or a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="07f84-145">**Objeto de destino**</span><span class="sxs-lookup"><span data-stu-id="07f84-145">**Target Object**</span></span>|<span data-ttu-id="07f84-146">Nombre del objeto que tiene una propiedad con una configuración.</span><span class="sxs-lookup"><span data-stu-id="07f84-146">The name of the object with a property that has a configuration.</span></span> <span data-ttu-id="07f84-147">Si la configuración es un archivo de configuración XML, la columna aparece en blanco, ya que la configuración puede actualizar varios objetos.</span><span class="sxs-lookup"><span data-stu-id="07f84-147">If the configuration is an XML configuration file, the column is blank, because the configuration can update multiple objects.</span></span>|  
|<span data-ttu-id="07f84-148">**Propiedad de destino**</span><span class="sxs-lookup"><span data-stu-id="07f84-148">**Target Property**</span></span>|<span data-ttu-id="07f84-149">El nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="07f84-149">The name of the property.</span></span> <span data-ttu-id="07f84-150">Si la configuración escribe en un archivo de configuración XML o una tabla de SQL Server, la columna aparece en blanco, ya que la configuración puede actualizar varios objetos.</span><span class="sxs-lookup"><span data-stu-id="07f84-150">If the configuration writes to an XML configuration file or a SQL Server table, the column is blank, because the configuration can update multiple objects.</span></span>|  
  
### <a name="to-create-a-package-configuration"></a><span data-ttu-id="07f84-151">Para crear una configuración de paquetes</span><span class="sxs-lookup"><span data-stu-id="07f84-151">To create a package configuration</span></span>  
  
1.  <span data-ttu-id="07f84-152">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="07f84-152">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="07f84-153">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="07f84-153">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="07f84-154">En el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , haga clic en las pestañas **Flujo de control**, **Flujo de datos**, **Controlador de eventos**o **Explorador de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="07f84-154">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, **Event Handler**, or **Package Explorer** tab.</span></span>  
  
4.  <span data-ttu-id="07f84-155">En el menú **SSIS** , haga clic en **Configuraciones de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="07f84-155">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="07f84-156">En el cuadro de diálogo **Organizador de configuraciones de paquetes** , seleccione **Habilitar configuraciones de paquetes**y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="07f84-156">In the **Package Configuration Organizer** dialog box, select **Enable package configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="07f84-157">En la página de bienvenida del Asistente para la configuración de paquetes, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="07f84-157">On the welcome page of the Package Configuration Wizard page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="07f84-158">En la página Seleccionar tipo de configuración, especifique el tipo de configuración y establezca las propiedades relevantes para el tipo de configuración.</span><span class="sxs-lookup"><span data-stu-id="07f84-158">On the Select Configuration Type page, specify the configuration type, and then set the properties that are relevant to the configuration type.</span></span> <span data-ttu-id="07f84-159">Para más información, vea [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="07f84-159">For more information, see [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span></span>  
  
8.  <span data-ttu-id="07f84-160">En la página Seleccionar propiedades para la exportación, seleccione las propiedades de los objetos de paquete que desee incluir en la configuración.</span><span class="sxs-lookup"><span data-stu-id="07f84-160">On the Select Properties to Export page, select the properties of package objects to include in the configuration.</span></span> <span data-ttu-id="07f84-161">Si el tipo de configuración admite solamente una propiedad, el título de esta página del asistente es Seleccionar propiedad de destino.</span><span class="sxs-lookup"><span data-stu-id="07f84-161">If the configuration type supports only one property, the title of this wizard page is Select Target Property.</span></span> <span data-ttu-id="07f84-162">Para más información, vea [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="07f84-162">For more information, see [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="07f84-163">Los tipos de configuración **Archivo de configuración XML** y **SQL Server** son los únicos que admiten varias propiedades en una configuración.</span><span class="sxs-lookup"><span data-stu-id="07f84-163">Only the **XML Configuration File** and **SQL Server** configuration types support including multiple properties in a configuration.</span></span>  
  
9. <span data-ttu-id="07f84-164">En la página Finalización del asistente, escriba el nombre de la configuración y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="07f84-164">On the Completing the Wizard page, type the name of the configuration, and then click **Finish**.</span></span>  
  
10. <span data-ttu-id="07f84-165">Vea la configuración en el cuadro de diálogo **Organizador de configuraciones de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="07f84-165">View the configuration in the **Package Configuration Organizer** dialog box.</span></span>  
  
11. <span data-ttu-id="07f84-166">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="07f84-166">Click **Close**.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="07f84-167">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="07f84-167">External Resources</span></span>  
  
-   <span data-ttu-id="07f84-168">Artículo técnico con una [introducción a las configuraciones de paquetes de Integration Services](https://go.microsoft.com/fwlink/?LinkId=165643), en msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="07f84-168">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="07f84-169">Entrada de blog, [crear paquetes en configuraciones de paquetes de código](https://go.microsoft.com/fwlink/?LinkId=217663), en www.sqlis.com.</span><span class="sxs-lookup"><span data-stu-id="07f84-169">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="07f84-170">Entrada de blog, [ejemplo de API: agregar mediante programación un archivo de configuración a un paquete](https://go.microsoft.com/fwlink/?LinkId=217664), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="07f84-170">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f84-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07f84-171">See Also</span></span>  
 <span data-ttu-id="07f84-172">[Configuraciones de paquetes](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="07f84-172">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="07f84-173">[Implementación de paquetes &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="07f84-173">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="07f84-174">Trabajar con variables mediante programación</span><span class="sxs-lookup"><span data-stu-id="07f84-174">Working with Variables Programmatically</span></span>](building-packages-programmatically/working-with-variables-programmatically.md)  
  
  
