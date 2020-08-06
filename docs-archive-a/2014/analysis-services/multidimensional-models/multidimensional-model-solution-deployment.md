---
title: Implementación de soluciones de modelos multidimensionales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services deployments, planning
- deploying [Analysis Services]
- deploying [Analysis Services], planning
ms.assetid: 7259c201-ff54-43e8-bda5-a6d51474e0e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 638e211f261b0a8654dfbe2d8ab937aa3dee24d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675601"
---
# <a name="multidimensional-model-solution-deployment"></a><span data-ttu-id="2c60a-102">Implementación de soluciones de modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="2c60a-102">Multidimensional Model Solution Deployment</span></span>
  <span data-ttu-id="2c60a-103">Una vez completado el desarrollo de un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , puede implementar la base de datos en un servidor de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2c60a-103">After you have completed the development of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you can deploy the database to an Analysis Services server.</span></span> <span data-ttu-id="2c60a-104">Analysis Services proporciona seis métodos de implementación posibles que se pueden usar para mover la base de datos a un servidor de prueba o de producción.</span><span class="sxs-lookup"><span data-stu-id="2c60a-104">Analysis Services provides six possible deployment methods that can be used to move the database to a test or production server.</span></span> <span data-ttu-id="2c60a-105">Estos son los métodos de implementación, por orden de ventaja: automatización AMO, XMLA, Asistente para la implementación, Utilidad de implementación, Asistente para sincronizar y Copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="2c60a-105">The methods are listed here in order of advantage: AMO Automation, XMLA, Deployment Wizard, Deployment Utility, Synchronize Wizard, Backup and Restore.</span></span>  
  
 <span data-ttu-id="2c60a-106">Este tema incluye las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="2c60a-106">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="2c60a-107">Métodos de implementación</span><span class="sxs-lookup"><span data-stu-id="2c60a-107">Deployment Methods</span></span>](#bkmk_meth)  
  
 [<span data-ttu-id="2c60a-108">Consideraciones de la implementación</span><span class="sxs-lookup"><span data-stu-id="2c60a-108">Deployment considerations</span></span>](#bkmk_considerations)  
  
 [<span data-ttu-id="2c60a-109">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2c60a-109">Related Tasks</span></span>](#bkmk_rel)  
  
##  <a name="deployment-methods"></a><a name="bkmk_meth"></a><span data-ttu-id="2c60a-110">Métodos de implementación</span><span class="sxs-lookup"><span data-stu-id="2c60a-110">Deployment Methods</span></span>  
  
|<span data-ttu-id="2c60a-111">Método</span><span class="sxs-lookup"><span data-stu-id="2c60a-111">Method</span></span>|<span data-ttu-id="2c60a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c60a-112">Description</span></span>|<span data-ttu-id="2c60a-113">Vínculo</span><span class="sxs-lookup"><span data-stu-id="2c60a-113">Link</span></span>|  
|------------|-----------------|----------|  
|<span data-ttu-id="2c60a-114">**Automatización AMO (Objetos de administración de análisis)**</span><span class="sxs-lookup"><span data-stu-id="2c60a-114">**Analysis Management Objects (AMO) Automation**</span></span>|<span data-ttu-id="2c60a-115">AMO ofrece una interfaz programática para el conjunto de comandos completo establecido para [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], incluidos los comandos que se pueden usar para la implementación de soluciones.</span><span class="sxs-lookup"><span data-stu-id="2c60a-115">AMO provides a programmatic interface to the complete command set for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], including commands that can be used for solution deployment.</span></span> <span data-ttu-id="2c60a-116">Como método para la implementación de soluciones, la automatización AMO es el más flexible, pero también requiere un esfuerzo de programación.</span><span class="sxs-lookup"><span data-stu-id="2c60a-116">As an approach for solution deployment, AMO automation is the most flexible, but it also requires a programming effort.</span></span>  <span data-ttu-id="2c60a-117">Una ventaja clave de AMO es que puede usar el Agente SQL Server con la aplicación AMO para ejecutar la implementación siguiendo una programación preestablecida.</span><span class="sxs-lookup"><span data-stu-id="2c60a-117">A key advantage to using AMO is that you can use SQL Server Agent with your AMO application to run deployment on a preset schedule.</span></span>|[<span data-ttu-id="2c60a-118">Desarrollar con Objetos de administración de análisis &#40;AMO&#41;</span><span class="sxs-lookup"><span data-stu-id="2c60a-118">Developing with Analysis Management Objects &#40;AMO&#41;</span></span>](https://docs.microsoft.com/bi-reference/amo/developing-with-analysis-management-objects-amo)|  
|<span data-ttu-id="2c60a-119">**XMLA**</span><span class="sxs-lookup"><span data-stu-id="2c60a-119">**XMLA**</span></span>|<span data-ttu-id="2c60a-120">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para generar un script XMLA de los metadatos de una base de datos existente de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y, a continuación, ejecute el script en otro servidor para volver a crear la base de datos inicial.</span><span class="sxs-lookup"><span data-stu-id="2c60a-120">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to generate an XMLA script of the metadata of an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, and then run that script on another server to recreate the initial database.</span></span> <span data-ttu-id="2c60a-121">Los scripts XMLA se forman fácilmente en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] definiendo el proceso de implementación, codificándolo y guardándolo en un script XMLA.</span><span class="sxs-lookup"><span data-stu-id="2c60a-121">XMLA scripts are easily formed in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by defining the deployment process, then codifying it and saving it in an XMLA script.</span></span> <span data-ttu-id="2c60a-122">Una vez que se tiene un script XMLA en un archivo guardado, se puede ejecutar fácilmente de acuerdo con una programación, o bien se puede incrustar en una aplicación que se conecta directamente con una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c60a-122">Once you have the XMLA script in a saved file, you can easily run the script according to a schedule, or embed the script in an application that connects directly to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="2c60a-123">También se pueden ejecutar Scripts XMLA de forma preestablecida con el Agente SQL Server, pero este método no presenta la misma flexibilidad que AMO.</span><span class="sxs-lookup"><span data-stu-id="2c60a-123">You can also run XMLA Scripts on a preset basis using SQL Server Agent, but you do not have the same flexibility with XMLA Scripts as with AMO.</span></span> <span data-ttu-id="2c60a-124">AMO ofrece una mayor funcionalidad, al hospedar todo el espectro de comandos administrativos.</span><span class="sxs-lookup"><span data-stu-id="2c60a-124">AMO provides a larger breadth of functionality by hosting the complete spectrum of administrative commands.</span></span>|[<span data-ttu-id="2c60a-125">Implementar soluciones de modelo mediante XMLA</span><span class="sxs-lookup"><span data-stu-id="2c60a-125">Deploy Model Solutions Using XMLA</span></span>](deploy-model-solutions-using-xmla.md)|  
|<span data-ttu-id="2c60a-126">**Asistente para la implementación**</span><span class="sxs-lookup"><span data-stu-id="2c60a-126">**Deployment Wizard**</span></span>|<span data-ttu-id="2c60a-127">Use el Asistente para la implementación cuando desee usar los archivos de salida XMLA generados por un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para implementar los metadatos del proyecto en un servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="2c60a-127">Use the Deployment Wizard to use the XMLA output files generated by an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to deploy the project's metadata to a destination server.</span></span> <span data-ttu-id="2c60a-128">Con el Asistente para la implementación, puede implementar directamente desde el archivo de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , tal como lo creó el directorio de salida en la compilación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2c60a-128">With the Deployment Wizard, you can deploy directly from the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] file, as created by the output directory by project build.</span></span><br /><br /> <span data-ttu-id="2c60a-129">La principal ventaja de usar el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] es la comodidad.</span><span class="sxs-lookup"><span data-stu-id="2c60a-129">The primary advantage of using the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard is convenience.</span></span> <span data-ttu-id="2c60a-130">Al igual que se puede guardar un script XMLA para su uso posterior en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], se pueden guardar los scripts del Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="2c60a-130">Just as you can save an XMLA script for use later in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can save Deployment Wizard scripts.</span></span> <span data-ttu-id="2c60a-131">El Asistente para la implementación se puede ejecutar interactivamente y desde el símbolo del sistema mediante la utilidad de implementación.</span><span class="sxs-lookup"><span data-stu-id="2c60a-131">The Deployment Wizard can be run both interactively and at the command prompt via the Deployment Utility.</span></span>|[<span data-ttu-id="2c60a-132">Implementar soluciones con el Asistente para la implementación</span><span class="sxs-lookup"><span data-stu-id="2c60a-132">Deploy Model Solutions Using the Deployment Wizard</span></span>](deploy-model-solutions-using-the-deployment-wizard.md)|  
|<span data-ttu-id="2c60a-133">**Utilidad de implementación**</span><span class="sxs-lookup"><span data-stu-id="2c60a-133">**Deployment Utility**</span></span>|<span data-ttu-id="2c60a-134">La utilidad de implementación le permite iniciar el motor de implementación de Analysis Services desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="2c60a-134">The Deployment utility lets you start the Analysis Services deployment engine from a command prompt.</span></span>|[<span data-ttu-id="2c60a-135">Implementar soluciones de modelos con la utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="2c60a-135">Deploy Model Solutions with the Deployment Utility</span></span>](deploy-model-solutions-with-the-deployment-utility.md)|  
|<span data-ttu-id="2c60a-136">**Asistente para sincronizar bases de datos**</span><span class="sxs-lookup"><span data-stu-id="2c60a-136">**Synchronize Database Wizard**</span></span>|<span data-ttu-id="2c60a-137">Use el Asistente para sincronizar bases de datos cuando desee sincronizar los metadatos y los datos de dos bases de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cualquiera.</span><span class="sxs-lookup"><span data-stu-id="2c60a-137">Use the Synchronize Database Wizard to synchronize the metadata and data between any two [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases.</span></span><br /><br /> <span data-ttu-id="2c60a-138">El Asistente para sincronizar se puede usar para copiar datos y metadatos de un servidor de origen en un servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="2c60a-138">The Synchronize Wizard can be used to copy both data and metadata from a source server to a destination server.</span></span> <span data-ttu-id="2c60a-139">Si el servidor de destino no tiene una copia de la base de datos que desea implementar, se copia una nueva base de datos en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="2c60a-139">If the destination server does not have a copy of the database that you want to deploy, a new database is copied to the destination server.</span></span> <span data-ttu-id="2c60a-140">Si el servidor de destino ya tiene una copia de la misma base de datos, la base de datos del servidor de destino se actualiza para que use los metadatos y los datos de la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="2c60a-140">If the destination server already has a copy of the same database, the database on the destination server is updated to use the metadata and data of the source database.</span></span>|[<span data-ttu-id="2c60a-141">Sincronizar bases de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2c60a-141">Synchronize Analysis Services Databases</span></span>](synchronize-analysis-services-databases.md)|  
|<span data-ttu-id="2c60a-142">**Copia de seguridad y restauración**</span><span class="sxs-lookup"><span data-stu-id="2c60a-142">**Backup and Restore**</span></span>|<span data-ttu-id="2c60a-143">La copia de seguridad es la forma más simple de transferir bases de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c60a-143">Backup offers the simplest approach to transferring [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases.</span></span> <span data-ttu-id="2c60a-144">Desde el cuadro de diálogo **Copia de seguridad**, puede establecer la configuración de las opciones y, a continuación, puede ejecutar la copia de seguridad desde el mismo cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2c60a-144">From the **Backup** dialog box, you can set the options configuration, and then you can run the backup from the dialog box itself.</span></span> <span data-ttu-id="2c60a-145">O bien, puede crear un script que se puede guardar y ejecutar con la frecuencia necesaria.</span><span class="sxs-lookup"><span data-stu-id="2c60a-145">Or, you can create a script that can be saved and run as frequently as required.</span></span><br /><br /> <span data-ttu-id="2c60a-146">Las copias de seguridad y restauración no se usan con la misma frecuencia que los otros métodos de implementación, pero es una forma de completar rápidamente una implementación con requisitos mínimos de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="2c60a-146">Backup and restore is not used as frequently as the other deployment methods, but is a way to quickly complete a deployment with minimal infrastructure requirements.</span></span>|[<span data-ttu-id="2c60a-147">Realizar una copia de seguridad y restaurar las bases de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2c60a-147">Backup and Restore of Analysis Services Databases</span></span>](backup-and-restore-of-analysis-services-databases.md)|  
  
##  <a name="deployment-considerations"></a><a name="bkmk_considerations"></a><span data-ttu-id="2c60a-148">Consideraciones de implementación</span><span class="sxs-lookup"><span data-stu-id="2c60a-148">Deployment considerations</span></span>  
 <span data-ttu-id="2c60a-149">Antes de implementar un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , considere cuáles de estas preguntas se aplican a la solución y luego revise el vínculo relacionado para saber cómo solucionar el problema:</span><span class="sxs-lookup"><span data-stu-id="2c60a-149">Before you deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, consider which of these questions apply to your solution and then review the related link to learn ways of addressing the issue:</span></span>  
  
|<span data-ttu-id="2c60a-150">Consideración</span><span class="sxs-lookup"><span data-stu-id="2c60a-150">Consideration</span></span>|<span data-ttu-id="2c60a-151">Más información</span><span class="sxs-lookup"><span data-stu-id="2c60a-151">Link to more information</span></span>|  
|-------------------|------------------------------|  
|<span data-ttu-id="2c60a-152">¿Qué recursos de hardware y software se requieren para esta solución?</span><span class="sxs-lookup"><span data-stu-id="2c60a-152">What hardware and software resources are required for this solution?</span></span>|[<span data-ttu-id="2c60a-153">Requisitos y consideraciones para la implementación de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2c60a-153">Requirements and Considerations for Analysis Services Deployment</span></span>](requirements-and-considerations-for-analysis-services-deployment.md)|  
|<span data-ttu-id="2c60a-154">¿Cómo implementará los objetos relacionados que se encuentran fuera del ámbito del proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , como paquetes, informes o esquemas de las bases de datos relacionales de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ?</span><span class="sxs-lookup"><span data-stu-id="2c60a-154">How will you deploy related objects that are outside the scope of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, such as [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, reports, or relational database schemas?</span></span>||  
|<span data-ttu-id="2c60a-155">¿Cómo cargará y actualizará los datos de la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] implementada?</span><span class="sxs-lookup"><span data-stu-id="2c60a-155">How will you load and update the data in the deployed [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database?</span></span><br /><br /> <span data-ttu-id="2c60a-156">¿Cómo actualizará los metadatos (por ejemplo, cálculos) de la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] implementada?</span><span class="sxs-lookup"><span data-stu-id="2c60a-156">How will you update the metadata (such as calculations) in the deployed [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database?</span></span>|<span data-ttu-id="2c60a-157">[Métodos de implementación](#bkmk_meth) en este tema.</span><span class="sxs-lookup"><span data-stu-id="2c60a-157">[Deployment Methods](#bkmk_meth) in this topic.</span></span>|  
|<span data-ttu-id="2c60a-158">¿Desea ofrecer a los usuarios acceso a los datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a través de Internet?</span><span class="sxs-lookup"><span data-stu-id="2c60a-158">Do you want to give users access to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data through the Internet?</span></span>|[<span data-ttu-id="2c60a-159">Configurar el acceso HTTP a Analysis Services en Internet Information Services &#40;IIS&#41; 8.0</span><span class="sxs-lookup"><span data-stu-id="2c60a-159">Configure HTTP Access to Analysis Services on Internet Information Services &#40;IIS&#41; 8.0</span></span>](../instances/configure-http-access-to-analysis-services-on-iis-8-0.md)|  
|<span data-ttu-id="2c60a-160">¿Desea proporcionar acceso continuo de consulta a los datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ?</span><span class="sxs-lookup"><span data-stu-id="2c60a-160">Do you want to provide continuous query access to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data?</span></span>|[<span data-ttu-id="2c60a-161">Requisitos y consideraciones para la implementación de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2c60a-161">Requirements and Considerations for Analysis Services Deployment</span></span>](requirements-and-considerations-for-analysis-services-deployment.md)|  
|<span data-ttu-id="2c60a-162">¿Desea implementar objetos en un entorno distribuido mediante el uso de objetos vinculados o particiones remotas?</span><span class="sxs-lookup"><span data-stu-id="2c60a-162">Do you want to deploy objects in a distributed environment by using linked objects or remote partitions?</span></span>|<span data-ttu-id="2c60a-163">[Crear y administrar una partición local &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md), [Crear y administrar una partición remota &#40;Analysis Services&#41;](create-and-manage-a-remote-partition-analysis-services.md) y [Grupos de medida vinculados](linked-measure-groups.md).</span><span class="sxs-lookup"><span data-stu-id="2c60a-163">[Create and Manage a Local Partition &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md), [Create and Manage a Remote Partition &#40;Analysis Services&#41;](create-and-manage-a-remote-partition-analysis-services.md) and [Linked Measure Groups](linked-measure-groups.md).</span></span>|  
|<span data-ttu-id="2c60a-164">¿Cómo protegerá los datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ?</span><span class="sxs-lookup"><span data-stu-id="2c60a-164">How will you secure the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data?</span></span>|[<span data-ttu-id="2c60a-165">Cómo autorizar el acceso a objetos y operaciones &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2c60a-165">Authorizing access to objects and operations &#40;Analysis Services&#41;</span></span>](authorizing-access-to-objects-and-operations-analysis-services.md)|  
  
##  <a name="related-tasks"></a><a name="bkmk_rel"></a> <span data-ttu-id="2c60a-166">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2c60a-166">Related Tasks</span></span>  
 [<span data-ttu-id="2c60a-167">Requisitos y consideraciones para la implementación de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2c60a-167">Requirements and Considerations for Analysis Services Deployment</span></span>](requirements-and-considerations-for-analysis-services-deployment.md)  
  
 [<span data-ttu-id="2c60a-168">Implementar soluciones de modelo mediante XMLA</span><span class="sxs-lookup"><span data-stu-id="2c60a-168">Deploy Model Solutions Using XMLA</span></span>](deploy-model-solutions-using-xmla.md)  
  
 [<span data-ttu-id="2c60a-169">Implementar soluciones con el Asistente para la implementación</span><span class="sxs-lookup"><span data-stu-id="2c60a-169">Deploy Model Solutions Using the Deployment Wizard</span></span>](deploy-model-solutions-using-the-deployment-wizard.md)  
  
 [<span data-ttu-id="2c60a-170">Implementar soluciones de modelos con la utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="2c60a-170">Deploy Model Solutions with the Deployment Utility</span></span>](deploy-model-solutions-with-the-deployment-utility.md)  
  
  