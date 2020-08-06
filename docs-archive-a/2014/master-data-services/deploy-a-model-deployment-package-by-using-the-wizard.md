---
title: Implementar un paquete de implementación de modelo mediante el asistente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], deploying
- models [Master Data Services], deploying a package
ms.assetid: 4f65dc60-0ff8-46e6-9988-5bc5b9603ad0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 75af9f7c12d866c6d9707f62c898aa7601f94800
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748148"
---
# <a name="deploy-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="cfc4a-102">Implementar un paquete de implementación de modelo mediante el asistente</span><span class="sxs-lookup"><span data-stu-id="cfc4a-102">Deploy a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="cfc4a-103">Use el asistente para la implementación de modelos de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para implementar paquetes que solo contengan objetos del modelo.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to deploy packages that contain model objects only.</span></span> <span data-ttu-id="cfc4a-104">Si necesita implementar un paquete con datos, consulte [Implementar un paquete de implementación de modelo mediante MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="cfc4a-104">If you need to deploy a package with data, see [Deploy a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cfc4a-105">Los paquetes solamente se pueden implementar en la edición de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en la que se crearon.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="cfc4a-106">Esto significa que los paquetes que se hayan creado en [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] no se pueden implementar en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfc4a-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cfc4a-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cfc4a-107">Prerequisites</span></span>  
 <span data-ttu-id="cfc4a-108">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="cfc4a-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="cfc4a-109">Debe disponer de permiso de acceso al área funcional **Administración del sistema** en el entorno de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-109">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="cfc4a-110">Debe existir un paquete de implementación de modelo.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-110">A model deployment package must exist.</span></span> <span data-ttu-id="cfc4a-111">Para obtener más información, consulte [Crear un paquete de implementación de modelo mediante el asistente](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="cfc4a-111">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
-   <span data-ttu-id="cfc4a-112">Debe ser administrador en el entorno donde va a implementar el modelo.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-112">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="cfc4a-113">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cfc4a-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-deploy-a-model-deployment-package-of-model-objects-only"></a><span data-ttu-id="cfc4a-114">Para implementar solo un paquete de implementación de objetos del modelo</span><span class="sxs-lookup"><span data-stu-id="cfc4a-114">To deploy a model deployment package of model objects only</span></span>  
  
1.  <span data-ttu-id="cfc4a-115">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="cfc4a-116">En la página **Vista de modelo** , en la barra de menús, seleccione **Sistema** y haga clic en **Implementación**.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-116">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="cfc4a-117">En el **Asistente para la implementación de modelos**, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-117">On the **Model Deployment Wizard**, click **Deploy**.</span></span>  
  
4.  <span data-ttu-id="cfc4a-118">Haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-118">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="cfc4a-119">Busque el paquete de implementación (archivo .pkg) y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-119">Find your deployment package (.pkg file) and click **Open**.</span></span>  
  
6.  <span data-ttu-id="cfc4a-120">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-120">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="cfc4a-121">Una vez cargado el paquete, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-121">After the package is loaded, click **Next**.</span></span>  
  
8.  <span data-ttu-id="cfc4a-122">Si el modelo ya existe, puede seleccionar **Actualizar el modelo existente**para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-122">If the model already exists, you can update it by selecting **Update the existing model**.</span></span> <span data-ttu-id="cfc4a-123">Para crear un nuevo modelo, seleccione **Crear un nuevo modelo** y, después de hacer clic en **Siguiente** , puede escribir un nombre para el nuevo modelo.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-123">To create a new model, select **Create a new model** and after you click **Next** you can type a name for the new model.</span></span>  
  
9. <span data-ttu-id="cfc4a-124">Haga clic en **Finalizar** para salir del asistente.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-124">Click **Finish** to exit the wizard.</span></span>  
  
 <span data-ttu-id="cfc4a-125">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="cfc4a-125">**Notes:**</span></span>  
  
-   <span data-ttu-id="cfc4a-126">Si una vista de suscripciones del paquete tiene el mismo nombre que una vista de suscripciones de un modelo existente, la vista se crea como *modelname. subscriptionviewname*.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-126">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="cfc4a-127">Si este nombre ya se está usando, no se crea la vista de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-127">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="cfc4a-128">El proceso de implementación tiene cuatro pasos:</span><span class="sxs-lookup"><span data-stu-id="cfc4a-128">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="cfc4a-129">Se crean los objetos del modelo.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-129">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="cfc4a-130">Se crean vistas de suscripción.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-130">Subscription views are created.</span></span>  
  
    3.  <span data-ttu-id="cfc4a-131">Se crean las reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-131">Business rules are created.</span></span>  
  
    4.  <span data-ttu-id="cfc4a-132">Se rellenan los datos maestros.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-132">Master data is populated.</span></span>  
  
-   <span data-ttu-id="cfc4a-133">Al crear un modelo nuevo o clonado, si el proceso sufre un error en algún paso, el modelo se elimina.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-133">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="cfc4a-134">Al actualizar un modelo, si el proceso produce un error durante alguno de los tres primeros pasos, no pasa al siguiente paso; sin embargo, los cambios ya realizados no se revierten.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-134">When updating a model, if the process fails during any of the first three steps, it does not proceed beyond that step; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="cfc4a-135">Si el proceso sufre un error en el paso 4, los miembros que se pueden actualizar se actualizan.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-135">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cfc4a-136">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cfc4a-136">Next Steps</span></span>  
 <span data-ttu-id="cfc4a-137">Los metadatos definidos por el usuario, atributos de archivo y los permisos de usuario y de grupo no están incluidos en los paquetes de implementación de modelos.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-137">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="cfc4a-138">Después de implementar un modelo, debe actualizarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="cfc4a-138">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="cfc4a-139">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="cfc4a-139">For more information, see:</span></span>  
  
-   [<span data-ttu-id="cfc4a-140">Agregar metadatos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cfc4a-140">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="cfc4a-141">Asignar permisos de objeto de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cfc4a-141">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="cfc4a-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfc4a-142">See Also</span></span>  
 [<span data-ttu-id="cfc4a-143">Implementar modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cfc4a-143">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
