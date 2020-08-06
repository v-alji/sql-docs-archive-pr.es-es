---
title: Especificar opciones de procesamiento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services deployments, processing options
- input files [Analysis Services]
- deploying [Analysis Services], processing options
- modifying processing options
- Analysis Services Deployment Wizard, processing options
ms.assetid: e9e50817-908e-4210-bc3d-8e2957568241
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9690aaa7e1d3b3870eb6ab01630b98027263655f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744399"
---
# <a name="specifying-processing-options"></a><span data-ttu-id="d27e7-102">Especificar opciones de procesamiento</span><span class="sxs-lookup"><span data-stu-id="d27e7-102">Specifying Processing Options</span></span>
  <span data-ttu-id="d27e7-103">El [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Asistente para la implementación de Lee las opciones de procesamiento del \<*project name*> archivo. archivo deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="d27e7-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the processing options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="d27e7-104">crea este archivo al compilar el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="d27e7-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="d27e7-105">usa las opciones de procesamiento especificadas en la página **implementación** del *\<project name>* cuadro de diálogo páginas de **propiedades** para crear el \<*project name*> archivo. archivo deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="d27e7-105">uses the processing options specified on the **Deployment** page of *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.deploymentoptions file.</span></span>  
  
## <a name="reviewing-the-processing-options-for-deployment"></a><span data-ttu-id="d27e7-106">Revisar las opciones de procesamiento para implementación</span><span class="sxs-lookup"><span data-stu-id="d27e7-106">Reviewing the Processing Options for Deployment</span></span>  
 <span data-ttu-id="d27e7-107">Los valores de configuración almacenados en el \<*project name*> archivo. archivo deploymentoptions son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d27e7-107">The configuration settings stored within the \<*project name*>.deploymentoptions file are as follows:</span></span>  
  
-   <span data-ttu-id="d27e7-108">**Método de procesamiento** Este valor controla si los objetos implementados se procesan después de la implementación y el tipo de procesamiento que se realizará.</span><span class="sxs-lookup"><span data-stu-id="d27e7-108">**Processing Method** This setting controls whether the deployed objects are processed after deployment and the type of processing that will be performed.</span></span> <span data-ttu-id="d27e7-109">Existen tres opciones de procesamiento:</span><span class="sxs-lookup"><span data-stu-id="d27e7-109">There are three processing options:</span></span>  
  
    -   <span data-ttu-id="d27e7-110">Procesamiento predeterminado (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d27e7-110">Default processing (default)</span></span>  
  
    -   <span data-ttu-id="d27e7-111">Procesamiento total</span><span class="sxs-lookup"><span data-stu-id="d27e7-111">Full processing</span></span>  
  
    -   <span data-ttu-id="d27e7-112">None</span><span class="sxs-lookup"><span data-stu-id="d27e7-112">None</span></span>  
  
-   <span data-ttu-id="d27e7-113">**Opciones de tabla de reescritura** Si la reescritura está habilitada en el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , este valor define cómo controlarla.</span><span class="sxs-lookup"><span data-stu-id="d27e7-113">**Writeback Table Options** If writeback is enabled in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, this setting defines how writeback is handled.</span></span> <span data-ttu-id="d27e7-114">Existen tres opciones de tabla de reescritura:</span><span class="sxs-lookup"><span data-stu-id="d27e7-114">There are three writeback table options:</span></span>  
  
    -   <span data-ttu-id="d27e7-115">De forma predeterminada, si existe una tabla de reescritura, se utilizará.</span><span class="sxs-lookup"><span data-stu-id="d27e7-115">By default, if a writeback table exists, it will be used.</span></span> <span data-ttu-id="d27e7-116">Si no existe ninguna tabla de reescritura, se creará una nueva.</span><span class="sxs-lookup"><span data-stu-id="d27e7-116">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="d27e7-117">Si ya existe una tabla de reescritura, la implementación producirá errores.</span><span class="sxs-lookup"><span data-stu-id="d27e7-117">If a writeback table already exists, the deployment fails.</span></span> <span data-ttu-id="d27e7-118">Si no existe ninguna tabla de reescritura, se creará una nueva.</span><span class="sxs-lookup"><span data-stu-id="d27e7-118">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="d27e7-119">Independientemente de si existe ya una tabla de reescritura o no, se crea una nueva tabla de reescritura.</span><span class="sxs-lookup"><span data-stu-id="d27e7-119">Regardless of whether a writeback table already exists, a new writeback table will be created.</span></span> <span data-ttu-id="d27e7-120">En este caso, el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] eliminará la tabla existente y la reemplazará por una tabla de reescritura nueva.</span><span class="sxs-lookup"><span data-stu-id="d27e7-120">In this case, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard will delete any existing table and replace it with a new writeback table.</span></span>  
  
-   <span data-ttu-id="d27e7-121">**Implementación transaccional** Este valor controla si la implementación de cambios de metadatos y de comandos de proceso se produce en una transacción única o en transacciones independientes.</span><span class="sxs-lookup"><span data-stu-id="d27e7-121">**Transactional Deployment** This setting controls whether the deployment of metadata changes and process commands occurs in a single transaction or in separate transactions.</span></span>  
  
    -   <span data-ttu-id="d27e7-122">Si esta opción es `True` (predeterminada), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] implementa todos los cambios de metadatos y todos los comandos de proceso en una sola transacción.</span><span class="sxs-lookup"><span data-stu-id="d27e7-122">If this option is `True` (default), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys all metadata changes and all process commands within a single transaction.</span></span>  
  
    -   <span data-ttu-id="d27e7-123">Si esta opción es `False`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] implementa los cambios de metadatos en una sola transacción e implementa cada comando de procesamiento en su propia transacción.</span><span class="sxs-lookup"><span data-stu-id="d27e7-123">If this option is `False`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys the metadata changes in a single transaction, and deploys each processing command in its own transaction.</span></span>  
  
## <a name="modifying-the-processing-options-for-deployment"></a><span data-ttu-id="d27e7-124">Modificar las opciones de procesamiento para implementación</span><span class="sxs-lookup"><span data-stu-id="d27e7-124">Modifying the Processing Options for Deployment</span></span>  
 <span data-ttu-id="d27e7-125">Sin embargo, puede que tenga que implementar el [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto con distintas opciones de procesamiento que las almacenadas en el \<*project name*> archivo. archivo deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="d27e7-125">However, you may need to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different processing options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="d27e7-126">Por ejemplo, puede que desee tener todos los objetos totalmente procesados, o procesados con la opción de procesamiento predeterminada, o que no se produzca ningún procesamiento.</span><span class="sxs-lookup"><span data-stu-id="d27e7-126">For example, you may want to have all objects fully processed, or processed using the default processing option, or have no processing occur.</span></span> <span data-ttu-id="d27e7-127">Si los cubos o las dimensiones están habilitadas para escritura, puede especificar si se utilizará una tabla de reescritura nueva o ya existente.</span><span class="sxs-lookup"><span data-stu-id="d27e7-127">If the cubes or dimensions are write-enabled, you can specify whether a new or existing writeback table be used.</span></span>  
  
 <span data-ttu-id="d27e7-128">Para modificar las opciones de procesamiento utilizadas durante la implementación, puede editar y volver a generar el proyecto, o cambiar las opciones de procesamiento del archivo de entrada mediante uno de los métodos descritos en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d27e7-128">To modify the processing options used during deployment, you can either edit and rebuild the project, or change the processing options in the input file by using one of the methods as described in the following procedure.</span></span>  
  
#### <a name="to-change-processing-options-after-the-input-files-have-been-generated"></a><span data-ttu-id="d27e7-129">Para cambiar las opciones de procesamiento después de haber generado los archivos de entrada</span><span class="sxs-lookup"><span data-stu-id="d27e7-129">To change processing options after the input files have been generated</span></span>  
  
-   <span data-ttu-id="d27e7-130">Ejecute el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="d27e7-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="d27e7-131">En la página **Opciones de procesamiento** , especifique las opciones de procesamiento del proyecto que se está implementando.</span><span class="sxs-lookup"><span data-stu-id="d27e7-131">On the **Processing Options** page, specify the processing options for the project being deployed.</span></span>  
  
     <span data-ttu-id="d27e7-132">O bien</span><span class="sxs-lookup"><span data-stu-id="d27e7-132">-or-</span></span>  
  
-   <span data-ttu-id="d27e7-133">Ejecute el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en el símbolo del sistema y ajuste el asistente de manera que se ejecute en modo de archivo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d27e7-133">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="d27e7-134">Para obtener más información acerca del modo de archivo de respuesta, vea [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d27e7-134">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="d27e7-135">O bien</span><span class="sxs-lookup"><span data-stu-id="d27e7-135">-or-</span></span>  
  
-   <span data-ttu-id="d27e7-136">Modifique el \<*project name*> archivo. archivo deploymentoptions con cualquier editor de texto.</span><span class="sxs-lookup"><span data-stu-id="d27e7-136">Modify the \<*project name*>.deploymentoptions file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27e7-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d27e7-137">See Also</span></span>  
 <span data-ttu-id="d27e7-138">[Especificar el destino de instalación](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="d27e7-138">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="d27e7-139">[Especificar las opciones de implementación de roles y particiones](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="d27e7-139">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 [<span data-ttu-id="d27e7-140">Especificar la configuración para la implementación de soluciones</span><span class="sxs-lookup"><span data-stu-id="d27e7-140">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
  
