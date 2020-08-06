---
title: Descripción de los archivos de entrada utilizados para crear el script de implementación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- Analysis Services Deployment Wizard, scripts
- deploying [Analysis Services], input files
- Analysis Services Deployment Wizard, input files
- scripts [Analysis Services], deployment
- Analysis Services deployments, input files
- modifying input files
ms.assetid: 20e080cd-6a0e-4591-b022-ea4cd3638e36
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34695993d4f153c6c0b97fef744d92c682517c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673373"
---
# <a name="understanding-the-input-files-used-to-create-the-deployment-script"></a><span data-ttu-id="c850b-102">Comprender los archivos de entrada utilizados para crear el script de implementación</span><span class="sxs-lookup"><span data-stu-id="c850b-102">Understanding the Input Files Used to Create the Deployment Script</span></span>
  <span data-ttu-id="c850b-103">Al compilar un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] de, genera archivos XML para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c850b-103">When you build a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] generates XML files for the project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="c850b-104">coloca estos archivos XML en la carpeta de salida del proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c850b-104">puts these XML files in the Output folder of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="c850b-105">De manera predeterminada la carpeta de salida está fuera en la carpeta \Bin.</span><span class="sxs-lookup"><span data-stu-id="c850b-105">By default output is out in the \Bin folder.</span></span> <span data-ttu-id="c850b-106">En la siguiente tabla se describen los archivos XML que crea [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c850b-106">The following table lists the XML files that [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates.</span></span>  
  
|<span data-ttu-id="c850b-107">Archivo XMLA</span><span class="sxs-lookup"><span data-stu-id="c850b-107">XMLA file</span></span>|<span data-ttu-id="c850b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c850b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c850b-109">\<*project name*>. asdatabase</span><span class="sxs-lookup"><span data-stu-id="c850b-109">\<*project name*>.asdatabase</span></span>|<span data-ttu-id="c850b-110">Contiene las definiciones declarativas para todos los objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que se encuentran en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c850b-110">Contains the declarative definitions for all the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in the project.</span></span>|  
|<span data-ttu-id="c850b-111">\<*project name*>. deploymenttargets</span><span class="sxs-lookup"><span data-stu-id="c850b-111">\<*project name*>.deploymenttargets</span></span>|<span data-ttu-id="c850b-112">Contiene el nombre de la base de datos y la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en la que se crearán los objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c850b-112">Contains the name of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database in which the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects will be created.</span></span>|  
|<span data-ttu-id="c850b-113">\<*project name*>. configsettings</span><span class="sxs-lookup"><span data-stu-id="c850b-113">\<*project name*>.configsettings</span></span>|<span data-ttu-id="c850b-114">Contiene configuración específica del entorno, como información sobre la conexión del origen de datos y ubicaciones de almacenamiento de objetos.</span><span class="sxs-lookup"><span data-stu-id="c850b-114">Contains environment specific settings, such as data source connection information and object storage locations.</span></span> <span data-ttu-id="c850b-115">La configuración de este archivo invalida la configuración del \<*project name*> archivo. asdatabase.</span><span class="sxs-lookup"><span data-stu-id="c850b-115">Settings in this file override settings in the \<*project name*>.asdatabase file.</span></span>|  
|<span data-ttu-id="c850b-116">\<*project name*>. archivo deploymentoptions</span><span class="sxs-lookup"><span data-stu-id="c850b-116">\<*project name*>.deploymentoptions</span></span>|<span data-ttu-id="c850b-117">Contiene opciones de implementación como, por ejemplo, si la implementación es transaccional y si los objetos implementados deben procesarse después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="c850b-117">Contains deployment options, such as whether deployment is transactional and whether deployed objects should be processed after deployment.</span></span>|  
  
> [!NOTE]  
>  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="c850b-118">nunca almacena las contraseñas en sus archivos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c850b-118">never stores passwords in its project files.</span></span>  
  
## <a name="modifying-the-input-files"></a><span data-ttu-id="c850b-119">Modificar los archivos de entrada</span><span class="sxs-lookup"><span data-stu-id="c850b-119">Modifying the Input Files</span></span>  
 <span data-ttu-id="c850b-120">La modificación de los valores de los archivos de entrada, o de los valores recuperados de los archivos de entrada, permite cambiar el destino de la implementación, los valores de configuración y las opciones de implementación sin editar el \<*project name*> archivo. asdatabase completo (o un archivo de script XMLA completo si se genera un script a partir de una [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de datos existente).</span><span class="sxs-lookup"><span data-stu-id="c850b-120">Modifying the values in the input files, or the values retrieved from the input files, makes it possible to change the deployment destination, the configuration settings, and deployment options without editing the whole \<*project name*>.asdatabase file (or a whole XMLA script file if you generate a script from an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database).</span></span> <span data-ttu-id="c850b-121">La posibilidad de modificar archivos individuales le permite crear fácilmente diferentes scripts de implementación para distintos fines.</span><span class="sxs-lookup"><span data-stu-id="c850b-121">Being able to modify individual files lets you easily create different deployment scripts for different purposes.</span></span>  
  
 <span data-ttu-id="c850b-122">En los siguientes temas se explica cómo modificar los valores de los diversos archivos de entrada:</span><span class="sxs-lookup"><span data-stu-id="c850b-122">The following topics explain how to modify values in the various input files:</span></span>  
  
-   [<span data-ttu-id="c850b-123">Especificar el destino de instalación</span><span class="sxs-lookup"><span data-stu-id="c850b-123">Specifying the Installation Target</span></span>](deployment-script-files-specifying-the-installation-target.md)  
  
-   [<span data-ttu-id="c850b-124">Especificar opciones de implementación de roles y particiones</span><span class="sxs-lookup"><span data-stu-id="c850b-124">Specifying Partition and Role Deployment Options</span></span>](deployment-script-files-partition-and-role-deployment-options.md)  
  
-   [<span data-ttu-id="c850b-125">Especificar la configuración para la implementación de soluciones</span><span class="sxs-lookup"><span data-stu-id="c850b-125">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
-   [<span data-ttu-id="c850b-126">Especificar opciones de procesamiento</span><span class="sxs-lookup"><span data-stu-id="c850b-126">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="c850b-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c850b-127">See Also</span></span>  
 <span data-ttu-id="c850b-128">[Ejecutar el Asistente para la implementación de Analysis Services](running-the-analysis-services-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="c850b-128">[Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="c850b-129">Descripción del script de implementación de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c850b-129">Understanding the Analysis Services Deployment Script</span></span>](understanding-the-analysis-services-deployment-script.md)  
  
  
