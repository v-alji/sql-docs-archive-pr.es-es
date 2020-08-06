---
title: Implementar un paquete de implementación de modelo mediante MDSModelDeploy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: fb2a4df4-5e0d-4b34-818f-383dbde1b15c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c23dcc592c2de34fa87703c8ba58d949dfec455c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674876"
---
# <a name="deploy-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="8e118-102">Implementar un paquete de implementación de modelo mediante MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="8e118-102">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="8e118-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], utilice la herramienta MDSModelDeploy para implementar un paquete que contiene:</span><span class="sxs-lookup"><span data-stu-id="8e118-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to deploy a package that contains either:</span></span>  
  
-   <span data-ttu-id="8e118-104">Solo objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="8e118-104">Model objects only.</span></span>  
  
-   <span data-ttu-id="8e118-105">Objetos de modelo y datos.</span><span class="sxs-lookup"><span data-stu-id="8e118-105">Model objects and data.</span></span>  
  
 <span data-ttu-id="8e118-106">Si desea implementar un paquete que solo contiene objetos de modelo, puede usar en su lugar el Asistente para la implementación de modelos en la aplicación web de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e118-106">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="8e118-107">Para obtener más información, consulte [Crear un paquete de implementación de modelo mediante el asistente](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8e118-107">For more information, see [Deploy a Model Deployment Package by Using the Wizard](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e118-108">Los paquetes solamente se pueden implementar en la edición de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en la que se crearon.</span><span class="sxs-lookup"><span data-stu-id="8e118-108">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="8e118-109">Esto significa que los paquetes que se hayan creado en [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] no se pueden implementar en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] o posterior.</span><span class="sxs-lookup"><span data-stu-id="8e118-109">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8e118-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8e118-110">Prerequisites</span></span>  
 <span data-ttu-id="8e118-111">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="8e118-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8e118-112">Debe disponer de permiso de acceso al área funcional **Administración del sistema** en el entorno de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="8e118-112">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="8e118-113">Debe existir un paquete de implementación de modelo.</span><span class="sxs-lookup"><span data-stu-id="8e118-113">A model deployment package must exist.</span></span> <span data-ttu-id="8e118-114">Para obtener más información, consulte [Crear un paquete de implementación de modelo mediante el asistente](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="8e118-114">For more information, see  [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
-   <span data-ttu-id="8e118-115">Debe ser administrador en el entorno donde va a implementar el modelo.</span><span class="sxs-lookup"><span data-stu-id="8e118-115">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="8e118-116">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8e118-116">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="8e118-117">Si va a actualizar un modelo con datos, la versión que se va a implementar no puede tener los valores **Bloqueado** o **Confirmado**.</span><span class="sxs-lookup"><span data-stu-id="8e118-117">If you are updating a model with data, the version you're deploying to cannot be **Locked** or **Committed**.</span></span>  
  
### <a name="to-deploy-a-model-deployment-package"></a><span data-ttu-id="8e118-118">Para implementar un paquete de implementación de modelos</span><span class="sxs-lookup"><span data-stu-id="8e118-118">To deploy a model deployment package</span></span>  
  
1.  <span data-ttu-id="8e118-119">Determine si está implementando un nuevo modelo, un clon de un modelo o actualizando un modelo clonado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8e118-119">Determine whether you are deploying a new model, a clone of a model, or updating a previously-cloned model.</span></span> <span data-ttu-id="8e118-120">Para obtener más información, consulte [Opciones de la implementación de modelos &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8e118-120">For more information, see [Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="8e118-121">Abra un símbolo del sistema y navegue a MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="8e118-121">Open a command prompt and navigate to MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="8e118-122">Si MDS está instalado en la ubicación predeterminada, la herramienta está disponible en *unidad*: \Archivos de Programa\microsoft SQL Server\120\Master Data Services\Configuration\MDSModelDeploy.exe</span><span class="sxs-lookup"><span data-stu-id="8e118-122">If MDS is installed at the default location, the tool is available at *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration\MDSModelDeploy.exe</span></span>  
  
    -   <span data-ttu-id="8e118-123">Si MDS no se ha instalado en la ubicación predeterminada, busque en el equipo local MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="8e118-123">If MDS is not installed at the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="8e118-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8e118-124">Optional.</span></span> <span data-ttu-id="8e118-125">Vea las opciones y la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="8e118-125">View options and help.</span></span>  
  
    -   <span data-ttu-id="8e118-126">Para mostrar todas las opciones disponibles, escriba `MDSModelDeploy` y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="8e118-126">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="8e118-127">Para mostrar la ayuda de una opción, escriba lo siguiente, donde *OptionName* es el nombre de la opción: `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="8e118-127">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="8e118-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8e118-128">Optional.</span></span> <span data-ttu-id="8e118-129">Si tiene varias aplicaciones web, determine el nombre del servicio en el que vaya a hacer las implementaciones; para ello, escriba este comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="8e118-129">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="8e118-130">Se devuelve una lista de valores, por ejemplo `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="8e118-130">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="8e118-131">El primer valor de esta lista (en este caso, `MDS1`) es necesario para implementar el modelo.</span><span class="sxs-lookup"><span data-stu-id="8e118-131">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="8e118-132">Dependiendo de si se crea un modelo, se clona un modelo o se actualiza un modelo, en el símbolo del sistema, escriba lo siguiente y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="8e118-132">Depending on whether you are creating a model, cloning a model, or updating a model, at the command prompt, type the following and press Enter.</span></span>  
  
    -   <span data-ttu-id="8e118-133">Para crear un modelo:</span><span class="sxs-lookup"><span data-stu-id="8e118-133">To create a new model:</span></span>  
  
        ```  
        MDSModelDeploy deploynew -package PackageName -model ModelName -service ServiceName  
        ```  
  
    -   <span data-ttu-id="8e118-134">Para crear un clon de un modelo:</span><span class="sxs-lookup"><span data-stu-id="8e118-134">To create a clone of a model:</span></span>  
  
        ```  
        MDSModelDeploy deployclone -package PackageName  
        ```  
  
    -   <span data-ttu-id="8e118-135">Para actualizar un modelo existente y sus datos:</span><span class="sxs-lookup"><span data-stu-id="8e118-135">To update an existing model and its data:</span></span>  
  
        ```  
        MDSModelDeploy deployupdate -package PackageName -version VersionName  
        ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8e118-136">Si usa la herramienta MDSModelDeploy para actualizar un modelo existente y sus datos, y el paquete no contiene una entidad, un atributo o un miembro que exista en el modelo de destino, MDSModelDeploy no eliminará dicha entidad, atributo o miembro del modelo.</span><span class="sxs-lookup"><span data-stu-id="8e118-136">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
     <span data-ttu-id="8e118-137">Donde *PackageName* es el nombre del archivo de paquete (.pkg), *ModelName* es el nombre del nuevo modelo, *VersionName* es el nombre de la versión y *ServiceName* es el nombre del servicio devuelto en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="8e118-137">Where *PackageName* is the name of the package (.pkg) file, *ModelName* is the name of the new model, *VersionName* is the name of the version, and *ServiceName* is the name of the service that you returned in the previous step.</span></span> <span data-ttu-id="8e118-138">Asegúrese de que los nombres del modelo y de la versión se correspondan exactamente con los nombres con distinción de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8e118-138">Ensure that the model and version names match the exact case-sensitive names.</span></span>  
  
6.  <span data-ttu-id="8e118-139">Cuando el paquete se implementa correctamente, se muestra un mensaje que indica que "la operación de MDSModelDeploy se completó correctamente".</span><span class="sxs-lookup"><span data-stu-id="8e118-139">When the package is successfully deployed, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
 <span data-ttu-id="8e118-140">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="8e118-140">**Notes:**</span></span>  
  
-   <span data-ttu-id="8e118-141">Si una vista de suscripciones del paquete tiene el mismo nombre que una vista de suscripciones de un modelo existente, la vista se crea como *modelname. subscriptionviewname*.</span><span class="sxs-lookup"><span data-stu-id="8e118-141">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="8e118-142">Si este nombre ya se está usando, no se crea la vista de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="8e118-142">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="8e118-143">El proceso de implementación tiene cuatro pasos:</span><span class="sxs-lookup"><span data-stu-id="8e118-143">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="8e118-144">Se crean los objetos del modelo.</span><span class="sxs-lookup"><span data-stu-id="8e118-144">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="8e118-145">Se crean las reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="8e118-145">Business rules are created.</span></span>  
  
    3.  <span data-ttu-id="8e118-146">Se crean vistas de suscripción.</span><span class="sxs-lookup"><span data-stu-id="8e118-146">Subscription views are created.</span></span>  
  
    4.  <span data-ttu-id="8e118-147">Se rellenan los datos maestros.</span><span class="sxs-lookup"><span data-stu-id="8e118-147">Master data is populated.</span></span>  
  
-   <span data-ttu-id="8e118-148">Al crear un modelo nuevo o clonado, si el proceso sufre un error en algún paso, el modelo se elimina.</span><span class="sxs-lookup"><span data-stu-id="8e118-148">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="8e118-149">Al actualizar un modelo, si el proceso sufre un error durante los tres primeros pasos, no continúa; sin embargo, los cambios ya realizados no se revierten.</span><span class="sxs-lookup"><span data-stu-id="8e118-149">When updating a model, if the process fails during the first three steps, it does not proceed; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="8e118-150">Si el proceso sufre un error en el paso 4, los miembros que se pueden actualizar se actualizan.</span><span class="sxs-lookup"><span data-stu-id="8e118-150">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8e118-151">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8e118-151">Next Steps</span></span>  
 <span data-ttu-id="8e118-152">Los metadatos definidos por el usuario, atributos de archivo y los permisos de usuario y de grupo no están incluidos en los paquetes de implementación de modelos.</span><span class="sxs-lookup"><span data-stu-id="8e118-152">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="8e118-153">Después de implementar un modelo, debe actualizarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="8e118-153">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="8e118-154">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="8e118-154">For more information, see:</span></span>  
  
-   [<span data-ttu-id="8e118-155">Agregar metadatos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8e118-155">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="8e118-156">Asignar permisos de objeto de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8e118-156">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="8e118-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e118-157">See Also</span></span>  
 [<span data-ttu-id="8e118-158">Implementar modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8e118-158">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
