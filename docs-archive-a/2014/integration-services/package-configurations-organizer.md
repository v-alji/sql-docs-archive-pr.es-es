---
title: Organizador de configuraciones de paquetes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.packageconfigurationorganizer.f1
helpviewer_keywords:
- Package Configurations Organizer dialog box
ms.assetid: f20ae6cb-9e6a-4d24-88ff-d7a903a4e8d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fdc9ca0faeff57c18fdb6e4d10acca3e9963f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748171"
---
# <a name="package-configurations-organizer"></a><span data-ttu-id="49dcf-102">Organizador de configuraciones de paquetes</span><span class="sxs-lookup"><span data-stu-id="49dcf-102">Package Configurations Organizer</span></span>
  <span data-ttu-id="49dcf-103">Utilice el cuadro de diálogo **Organizador de configuraciones de paquetes** para habilitar las configuraciones de paquetes, ver una lista de configuraciones para el paquete actual y especificar el orden de preferencia en el que se deben cargar las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="49dcf-103">Use the **Package Configurations Organizer** dialog box to enable package configurations, view a list of configurations for the current package, and specify the preferred order in which the configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49dcf-104">Hay configuraciones disponibles para el modelo de implementación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="49dcf-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="49dcf-105">Se usan parámetros en lugar de configuraciones para el modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="49dcf-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="49dcf-106">El modelo de implementación de proyectos le permite implementar proyectos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49dcf-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="49dcf-107">Para obtener más información acerca de los modelos de implementación, vea [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="49dcf-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="49dcf-108">Si varias configuraciones actualizan la misma propiedad, los valores de las configuraciones que aparezcan más abajo en la lista reemplazarán los valores de aquéllas que ocupen un lugar superior en la lista.</span><span class="sxs-lookup"><span data-stu-id="49dcf-108">If multiple configurations update the same property, values from configurations listed lower in the configuration list will replace values from configurations higher in the list.</span></span> <span data-ttu-id="49dcf-109">El último valor cargado en la propiedad es el valor que se usa cuando se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="49dcf-109">The last value loaded into the property is the value that is used when the package runs.</span></span> <span data-ttu-id="49dcf-110">Asimismo, si el paquete utiliza una combinación de configuración directa, como un archivo de configuración XML, y configuración indirecta, como una variable de entorno, la configuración indirecta que señala a la ubicación de la configuración directa debe ocupar un lugar superior en la lista.</span><span class="sxs-lookup"><span data-stu-id="49dcf-110">Also, if the package uses a combination of direct configuration such as an XML configuration file and an indirect configuration such as an environment variable, the indirect configuration that points to the location of the direct configuration must be higher in the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49dcf-111">Cuando las configuraciones de paquetes se cargan en el orden preferido, se cargan de arriba a abajo, según la lista que se muestra en el cuadro de diálogo **Organizador de configuraciones de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="49dcf-111">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="49dcf-112">Sin embargo, en tiempo de ejecución, las configuraciones de paquetes podrían no cargarse en el orden preferido.</span><span class="sxs-lookup"><span data-stu-id="49dcf-112">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="49dcf-113">Concretamente, las configuraciones de paquetes principales se cargan después de las configuraciones de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="49dcf-113">In particular, Parent Package Configurations load after configurations of other types.</span></span>  
  
 <span data-ttu-id="49dcf-114">Las configuraciones de paquetes actualizan los valores de las propiedades de los objetos de paquete en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="49dcf-114">Package configurations update the values of properties of package objects at run time.</span></span> <span data-ttu-id="49dcf-115">Cuando se carga un paquete, los valores de las configuraciones reemplazan los valores establecidos cuando se desarrolló el paquete.</span><span class="sxs-lookup"><span data-stu-id="49dcf-115">When a package is loaded, the values from the configurations replace the values that were set when the package was developed.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="49dcf-116">admite distintos tipos de configuración.</span><span class="sxs-lookup"><span data-stu-id="49dcf-116">supports different configuration types.</span></span> <span data-ttu-id="49dcf-117">Por ejemplo, se puede utilizar un archivo XML que contenga múltiples configuraciones o una variable de entorno que contenga una única configuración.</span><span class="sxs-lookup"><span data-stu-id="49dcf-117">For example, you can use an XML file that can contain multiple configurations, or an environment variable that contains a single configuration.</span></span> <span data-ttu-id="49dcf-118">Para más información, consulte [Package Configurations](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="49dcf-118">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="49dcf-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="49dcf-119">Options</span></span>  
 <span data-ttu-id="49dcf-120">**Habilitar configuraciones de paquetes**</span><span class="sxs-lookup"><span data-stu-id="49dcf-120">**Enable package configurations**</span></span>  
 <span data-ttu-id="49dcf-121">Seleccione esta opción para utilizar las configuraciones incluidas con el paquete.</span><span class="sxs-lookup"><span data-stu-id="49dcf-121">Select to use configurations with the package.</span></span>  
  
 <span data-ttu-id="49dcf-122">**Nombre de la configuración**</span><span class="sxs-lookup"><span data-stu-id="49dcf-122">**Configuration Name**</span></span>  
 <span data-ttu-id="49dcf-123">Presenta el nombre de la configuración.</span><span class="sxs-lookup"><span data-stu-id="49dcf-123">View the name of the configuration.</span></span>  
  
 <span data-ttu-id="49dcf-124">**Tipo de configuración**</span><span class="sxs-lookup"><span data-stu-id="49dcf-124">**Configuration Type**</span></span>  
 <span data-ttu-id="49dcf-125">Presenta el tipo de la ubicación donde se almacenan las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="49dcf-125">View the type of the location where configurations are stored.</span></span>  
  
 <span data-ttu-id="49dcf-126">**Cadena de configuración**</span><span class="sxs-lookup"><span data-stu-id="49dcf-126">**Configuration String**</span></span>  
 <span data-ttu-id="49dcf-127">Presenta la ubicación donde se almacenan los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="49dcf-127">View the location where the configuration values are stored.</span></span> <span data-ttu-id="49dcf-128">La ubicación puede ser la ruta de acceso a un archivo, el nombre de una variable de entorno, el nombre de una variable de paquete principal, una clave del Registro o el nombre de una tabla de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49dcf-128">The location can be the path of a file, the name of an environment variable, the name of a parent package variable, a Registry key, or the name of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="49dcf-129">**Objeto de destino**</span><span class="sxs-lookup"><span data-stu-id="49dcf-129">**Target Object**</span></span>  
 <span data-ttu-id="49dcf-130">Muestra el nombre del objeto que la configuración actualiza.</span><span class="sxs-lookup"><span data-stu-id="49dcf-130">View the name of the object that the configuration updates.</span></span> <span data-ttu-id="49dcf-131">Si la configuración se encuentra en un archivo de configuración XML o una tabla de SQL Server, la columna aparece en blanco, ya que la configuración puede incluir varios objetos.</span><span class="sxs-lookup"><span data-stu-id="49dcf-131">If the configuration is an XML configuration file or a SQL Server table, the column is blank because the configuration can include multiple objects.</span></span>  
  
 <span data-ttu-id="49dcf-132">**Propiedad de destino**</span><span class="sxs-lookup"><span data-stu-id="49dcf-132">**Target Property**</span></span>  
 <span data-ttu-id="49dcf-133">Presenta el nombre de la propiedad modificada por la configuración.</span><span class="sxs-lookup"><span data-stu-id="49dcf-133">View the name of the property modified by the configuration.</span></span> <span data-ttu-id="49dcf-134">La columna está en blanco si el tipo de configuración admite varias configuraciones.</span><span class="sxs-lookup"><span data-stu-id="49dcf-134">This column is blank if the configuration type supports multiple configurations.</span></span>  
  
 <span data-ttu-id="49dcf-135">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="49dcf-135">**Add**</span></span>  
 <span data-ttu-id="49dcf-136">Agrega una configuración empleando el Asistente para la configuración de paquetes.</span><span class="sxs-lookup"><span data-stu-id="49dcf-136">Add a configuration by using the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="49dcf-137">**Edición**</span><span class="sxs-lookup"><span data-stu-id="49dcf-137">**Edit**</span></span>  
 <span data-ttu-id="49dcf-138">Edita una configuración existente volviendo a ejecutar el Asistente para la configuración de paquetes.</span><span class="sxs-lookup"><span data-stu-id="49dcf-138">Edit an existing configuration by rerunning the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="49dcf-139">**Remove**</span><span class="sxs-lookup"><span data-stu-id="49dcf-139">**Remove**</span></span>  
 <span data-ttu-id="49dcf-140">Seleccione una configuración y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="49dcf-140">Select a configuration, and then click **Remove**.</span></span>  
  
 <span data-ttu-id="49dcf-141">**Flechas**</span><span class="sxs-lookup"><span data-stu-id="49dcf-141">**Arrows**</span></span>  
 <span data-ttu-id="49dcf-142">Seleccione una configuración y utilice las flechas arriba y abajo para subirla o bajarla de la lista.</span><span class="sxs-lookup"><span data-stu-id="49dcf-142">Select a configuration and use the up and down arrows to move it up or down in the list.</span></span> <span data-ttu-id="49dcf-143">Las configuraciones se cargan en la secuencia en la que aparecen en la lista.</span><span class="sxs-lookup"><span data-stu-id="49dcf-143">Configurations are loaded in the sequence in which they appear in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49dcf-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49dcf-144">See Also</span></span>  
 [<span data-ttu-id="49dcf-145">Crear configuraciones de paquetes</span><span class="sxs-lookup"><span data-stu-id="49dcf-145">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
