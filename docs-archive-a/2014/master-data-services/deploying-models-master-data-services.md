---
title: Implementar modelos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], about deployment packages
- deployment packages [Master Data Services]
ms.assetid: 30085c08-034f-4efe-80fe-408f9091ff5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a9cc99112ec874e89ae07faa575235d9a041a972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678226"
---
# <a name="deploying-models-master-data-services"></a><span data-ttu-id="a7705-102">Implementar modelos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a7705-102">Deploying Models (Master Data Services)</span></span>
  <span data-ttu-id="a7705-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], un paquete es un archivo XML que contiene una estructura del modelo implementable y, opcionalmente, los datos del modelo.</span><span class="sxs-lookup"><span data-stu-id="a7705-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a package is an XML file that contains a deployable model structure, and optionally, data from the model.</span></span> <span data-ttu-id="a7705-104">Use los paquetes del modelo para mover las copias de modelos desde un entorno de MDS a otro, o para crear nuevos modelos en el entorno de MDS existente.</span><span class="sxs-lookup"><span data-stu-id="a7705-104">Use model packages to move copies of models from one MDS environment to another, or to create new models in your existing MDS environment.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a7705-105">Los paquetes solamente se pueden implementar en la edición de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en la que se crearon.</span><span class="sxs-lookup"><span data-stu-id="a7705-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="a7705-106">Esto significa que los paquetes que se hayan creado en [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] no se pueden implementar en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] o posterior.</span><span class="sxs-lookup"><span data-stu-id="a7705-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="tools-for-deploying-models"></a><span data-ttu-id="a7705-107">Herramientas para implementar modelos</span><span class="sxs-lookup"><span data-stu-id="a7705-107">Tools for Deploying Models</span></span>  
 <span data-ttu-id="a7705-108">Para trabajar con paquetes de modelos, puede usar una de tres herramientas, dependiendo de sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="a7705-108">To work with model packages, you can use one of three tools, depending on your needs.</span></span>  
  
-   <span data-ttu-id="a7705-109">**Herramienta MDSModelDeploy**: para crear e implementar objetos y datos del modelo, use la herramienta MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="a7705-109">**MDSModelDeploy tool**: To create and deploy model objects and data, use the MDSModelDeploy.exe tool.</span></span> <span data-ttu-id="a7705-110">Si seleccionó la ruta de acceso predeterminada al instalar MDS, esta herramienta se encuentra en *unidad*: \Archivos de Programa\microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="a7705-110">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
-   <span data-ttu-id="a7705-111">**Asistente para implementación de modelos**: para crear e implementar paquetes de la estructura del modelo únicamente, use el asistente de la aplicación web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7705-111">**Model Deployment wizard**: To create and deploy packages of the model structure only, use the wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="a7705-112">No puede usar este asistente para la implementación de datos.</span><span class="sxs-lookup"><span data-stu-id="a7705-112">You cannot use this wizard to deploy data.</span></span>  
  
-   <span data-ttu-id="a7705-113">**Modelo editor de paquetes**: para modificar un modelo de paquetes, use ModelPackageEditor.exe que inicia el asistente de modelo editor de paquetes.</span><span class="sxs-lookup"><span data-stu-id="a7705-113">**Model Package Editor**: To edit a model package, use the ModelPackageEditor.exe that launches the Model Package Editor wizard.</span></span> <span data-ttu-id="a7705-114">Utilice este asistente para modificar un paquete que haya creado la herramienta MDSModelDeploy o el asistente para implementación de modelos.</span><span class="sxs-lookup"><span data-stu-id="a7705-114">You use this wizard to edit a package that was created by the MDSModelDeploy tool or the Model Deployment wizard.</span></span> <span data-ttu-id="a7705-115">Si seleccionó la ruta de acceso predeterminada al instalar MDS, esta herramienta se encuentra en *unidad*: \Archivos de Programa\microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="a7705-115">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a7705-116">Puede usar MDSDeployModel para crear un nuevo modelo, crear un clon de un modelo o actualizar un modelo existente y sus datos.</span><span class="sxs-lookup"><span data-stu-id="a7705-116">You can use the MDSDeployModel to create a new model, create a clone of a model, or update an existing model and its data.</span></span> <span data-ttu-id="a7705-117">Si usa la herramienta MDSModelDeploy para actualizar un modelo existente y sus datos, y el paquete no contiene una entidad, un atributo o un miembro que exista en el modelo de destino, MDSModelDeploy no eliminará dicha entidad, atributo o miembro del modelo.</span><span class="sxs-lookup"><span data-stu-id="a7705-117">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
## <a name="what-packages-contain"></a><span data-ttu-id="a7705-118">Qué contienen los paquetes</span><span class="sxs-lookup"><span data-stu-id="a7705-118">What Packages Contain</span></span>  
 <span data-ttu-id="a7705-119">Un paquete del modelo es un archivo XML que se guarda con la extensión .pkg.</span><span class="sxs-lookup"><span data-stu-id="a7705-119">A model package is an XML file that is saved with the .pkg extension.</span></span> <span data-ttu-id="a7705-120">Al crear un paquete de implementación, puede decidir si va a incluir o no datos.</span><span class="sxs-lookup"><span data-stu-id="a7705-120">When you create a deployment package, you can decide whether or not to include data.</span></span> <span data-ttu-id="a7705-121">Si decide incluir los datos, debe seleccionar una versión de los datos que se incluirán.</span><span class="sxs-lookup"><span data-stu-id="a7705-121">If you decide to include data, you must select a version of the data to include.</span></span>  
  
 <span data-ttu-id="a7705-122">Todos los objetos del modelo se incluyen en un paquete.</span><span class="sxs-lookup"><span data-stu-id="a7705-122">All model objects are included in a package.</span></span> <span data-ttu-id="a7705-123">Estos objetos son:</span><span class="sxs-lookup"><span data-stu-id="a7705-123">These objects are:</span></span>  
  
-   <span data-ttu-id="a7705-124">Entidades</span><span class="sxs-lookup"><span data-stu-id="a7705-124">Entities</span></span>  
  
-   <span data-ttu-id="a7705-125">Atributos</span><span class="sxs-lookup"><span data-stu-id="a7705-125">Attributes</span></span>  
  
-   <span data-ttu-id="a7705-126">Grupos de atributos</span><span class="sxs-lookup"><span data-stu-id="a7705-126">Attribute groups</span></span>  
  
-   <span data-ttu-id="a7705-127">Jerarquías</span><span class="sxs-lookup"><span data-stu-id="a7705-127">Hierarchies</span></span>  
  
-   <span data-ttu-id="a7705-128">Colecciones</span><span class="sxs-lookup"><span data-stu-id="a7705-128">Collections</span></span>  
  
-   <span data-ttu-id="a7705-129">Reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="a7705-129">Business rules</span></span>  
  
-   <span data-ttu-id="a7705-130">Marcas de versión</span><span class="sxs-lookup"><span data-stu-id="a7705-130">Version flags</span></span>  
  
-   <span data-ttu-id="a7705-131">Vistas de suscripciones</span><span class="sxs-lookup"><span data-stu-id="a7705-131">Subscription views</span></span>  
  
 <span data-ttu-id="a7705-132">Los metadatos definidos por el usuario, atributos de archivo y permisos de usuario y de grupo no se incluyen.</span><span class="sxs-lookup"><span data-stu-id="a7705-132">User-defined metadata, file attributes, and user and group permissions are not included.</span></span> <span data-ttu-id="a7705-133">Después de implementar un modelo, debe actualizarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="a7705-133">After you deploy a model, you must update these manually.</span></span>  
  
## <a name="sample-packages"></a><span data-ttu-id="a7705-134">Paquetes de ejemplos</span><span class="sxs-lookup"><span data-stu-id="a7705-134">Sample Packages</span></span>  
 <span data-ttu-id="a7705-135">Cuando se instala [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]se incluyen archivos de paquete de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7705-135">Sample package files are included when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="a7705-136">Estos archivos de paquete están en el directorio Master Data Services\Samples\Packages de la instalación de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7705-136">These package files are in the Master Data Services\Samples\Packages directory where you installed [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="a7705-137">Cuando se implementan estos paquetes de muestra con la herramienta MDSModelDeploy, se crean modelos de ejemplo y se rellenan con datos.</span><span class="sxs-lookup"><span data-stu-id="a7705-137">When you deploy these sample packages by using the MDSModelDeploy tool, sample models are created and populated with data.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a7705-138">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a7705-138">Related Tasks</span></span>  
  
|<span data-ttu-id="a7705-139">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="a7705-139">Task Description</span></span>|<span data-ttu-id="a7705-140">Tema</span><span class="sxs-lookup"><span data-stu-id="a7705-140">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="a7705-141">Crear un nuevo paquete de implementación de objetos o datos del modelo mediante la herramienta MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="a7705-141">Create a new deployment package of model objects and/or data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="a7705-142">Crear un paquete de implementación de modelo mediante MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="a7705-142">Create a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="a7705-143">Crear un nuevo paquete de implementación de objetos del modelo solo con el asistente.</span><span class="sxs-lookup"><span data-stu-id="a7705-143">Create a new deployment package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="a7705-144">Crear un paquete de implementación de modelo mediante el asistente</span><span class="sxs-lookup"><span data-stu-id="a7705-144">Create a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="a7705-145">Implementar un paquete de objetos y datos del modelo mediante la herramienta MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="a7705-145">Deploy a package of model objects and data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="a7705-146">Implementar un paquete de implementación de modelo mediante MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="a7705-146">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="a7705-147">Implementar un paquete de objetos del modelo solo con el asistente.</span><span class="sxs-lookup"><span data-stu-id="a7705-147">Deploy a package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="a7705-148">Implementar un paquete de implementación de modelo mediante el asistente</span><span class="sxs-lookup"><span data-stu-id="a7705-148">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="a7705-149">Modifique un paquete de implementación de modelos para implementar porciones seleccionadas de un modelo, en lugar del modelo en su totalidad.</span><span class="sxs-lookup"><span data-stu-id="a7705-149">Edit a model deployment package to deploy selected parts of a model, rather than the entire model.</span></span>|[<span data-ttu-id="a7705-150">Editar un paquete de implementación de modelos</span><span class="sxs-lookup"><span data-stu-id="a7705-150">Edit a Model Deployment Package</span></span>](../../2014/master-data-services/edit-a-model-deployment-package.md)|  
  
## <a name="related-content"></a><span data-ttu-id="a7705-151">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="a7705-151">Related Content</span></span>  
  
-   [<span data-ttu-id="a7705-152">Opciones de la implementación de modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a7705-152">Model Deployment Options &#40;Master Data Services&#41;</span></span>](model-deployment-options-master-data-services.md)  
  
  
