---
title: Crear un paquete de implementación de modelo mediante MDSModelDeploy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: c2687e39-dc20-494f-a707-2aa29f4c329e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c546d6398234dd43103d0e6c75822377e11de61a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677746"
---
# <a name="create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="004c7-102">Crear un paquete de implementación de modelo mediante MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="004c7-102">Create a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="004c7-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], utilice la herramienta MDSModelDeploy para crear un paquete.</span><span class="sxs-lookup"><span data-stu-id="004c7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to create a package.</span></span> <span data-ttu-id="004c7-104">Dependiendo de los comandos que especifique, el paquete puede contener:</span><span class="sxs-lookup"><span data-stu-id="004c7-104">Depending on the commands you specify, the package can contain either:</span></span>  
  
-   <span data-ttu-id="004c7-105">Solo objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="004c7-105">Model objects only.</span></span>  
  
-   <span data-ttu-id="004c7-106">Objetos de modelo y datos.</span><span class="sxs-lookup"><span data-stu-id="004c7-106">Model objects and data.</span></span>  
  
 <span data-ttu-id="004c7-107">Si desea implementar un paquete que solo contiene objetos de modelo, puede usar en su lugar el Asistente para la implementación de modelos en la aplicación web de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="004c7-107">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="004c7-108">Para obtener más información, consulte [Crear un paquete de implementación de modelo mediante el asistente](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="004c7-108">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
> [!NOTE]  
> <span data-ttu-id="004c7-109">Esta versión de la herramienta MDSModelDeploy no puede usar más de gigabytes (GB) de memoria.</span><span class="sxs-lookup"><span data-stu-id="004c7-109">This version of the MDSModelDeploy tool cannot use more than gigabytes (GB) of memory.</span></span> <span data-ttu-id="004c7-110">Al crear o implementar modelos grandes con la opción de **datos y objetos del modelo** , puede experimentar errores de "memoria insuficiente" o "flujo demasiado largo".</span><span class="sxs-lookup"><span data-stu-id="004c7-110">When you create or deploy large models by using **Model objects and data** option, you may experience "Out of Memory" or "Stream was too long" errors.</span></span> <span data-ttu-id="004c7-111">Para resolver este problema, use el almacenamiento provisional de MDS para implementar los datos. o actualice a MDS 2016 o una versión posterior, que incluye la versión actualizada de la herramienta MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="004c7-111">To resolve this issue, use MDS staging to deploy the data; or upgrade to MDS 2016 or a later version, which includes the updated version of the MDSModelDeploy tool.</span></span>
## <a name="prerequisites"></a><span data-ttu-id="004c7-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="004c7-112">Prerequisites</span></span>  
 <span data-ttu-id="004c7-113">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="004c7-113">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="004c7-114">Los permisos básicos necesarios para ejecutar la herramienta de MDSModelDeploy son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="004c7-114">The basic permissions required to run the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="004c7-115">El mismo permiso de Windows que para el administrador de configuración de MDS (administrador de Windows)</span><span class="sxs-lookup"><span data-stu-id="004c7-115">The same Windows permission as the MDS Configuration Manager (administrator of Windows)</span></span>  
  
    -   <span data-ttu-id="004c7-116">Permiso DBA en la base de datos de MDS.</span><span class="sxs-lookup"><span data-stu-id="004c7-116">DBA permission on the MDS database.</span></span>  
  
2.  <span data-ttu-id="004c7-117">Los permisos necesarios para crear el paquete mediante la herramienta MDSModelDeploy son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="004c7-117">The permissions required to create the package using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="004c7-118">Permiso de administrador de modelo MDS en el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="004c7-118">MDS model administrator permission on the data model.</span></span>  
  
    -   <span data-ttu-id="004c7-119">Permiso de la función de administración de integraciones de MDS.</span><span class="sxs-lookup"><span data-stu-id="004c7-119">MDS Integration Management function permission.</span></span>  
  
3.  <span data-ttu-id="004c7-120">Los permisos necesarios para implementar un modelo mediante la herramienta MDSModelDeploy son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="004c7-120">The permissions required to deploy a model using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="004c7-121">Permiso de la función de explorador de MDS</span><span class="sxs-lookup"><span data-stu-id="004c7-121">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="004c7-122">Permiso de la función de administración de integraciones de MDS</span><span class="sxs-lookup"><span data-stu-id="004c7-122">MDS Integration Management function permission</span></span>  
  
    -   <span data-ttu-id="004c7-123">Permiso de la función de administración del sistema de MDS.</span><span class="sxs-lookup"><span data-stu-id="004c7-123">MDS System Administration function permission.</span></span>  
  
4.  <span data-ttu-id="004c7-124">Los permisos necesarios para mostrar modelos mediante la herramienta MDSModelDeploy son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="004c7-124">The permissions required to list models using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="004c7-125">Permiso de la función de explorador de MDS</span><span class="sxs-lookup"><span data-stu-id="004c7-125">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="004c7-126">Permiso de administrador de modelos de MDS en el modelo de datos en orden para ver el modelo en la lista.</span><span class="sxs-lookup"><span data-stu-id="004c7-126">MDS model administrator permission on the data model on order to see the model in the list.</span></span>  
  
 <span data-ttu-id="004c7-127">Debe existir un modelo para que se pueda crear un paquete del mismo.</span><span class="sxs-lookup"><span data-stu-id="004c7-127">A model must exist for you to create a package of.</span></span> <span data-ttu-id="004c7-128">Para obtener más información, consulte [Crear un modelo &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="004c7-128">For more information, see [Create a Model &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span></span>  
  
 <span data-ttu-id="004c7-129">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="004c7-129">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="004c7-130">Para crear un paquete de implementación de modelo mediante MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="004c7-130">To create a model deployment package by using MDSModelDeploy</span></span>  
  
1.  <span data-ttu-id="004c7-131">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="004c7-131">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="004c7-132">Navegue a la ubicación de MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="004c7-132">Navigate to the location of MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="004c7-133">Si MDS se instaló en la ubicación predeterminada, el archivo se encuentra en *unidad*: \Archivos de Programa\microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="004c7-133">If MDS was installed in the default location, the file is in *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
    -   <span data-ttu-id="004c7-134">Si MDS no se instaló en la ubicación predeterminada, busque en el equipo local MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="004c7-134">If MDS was not installed in the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="004c7-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="004c7-135">Optional.</span></span> <span data-ttu-id="004c7-136">Vea las opciones y la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="004c7-136">View options and help.</span></span>  
  
    -   <span data-ttu-id="004c7-137">Para mostrar todas las opciones disponibles, escriba `MDSModelDeploy` y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="004c7-137">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="004c7-138">Para mostrar la ayuda de una opción, escriba lo siguiente, donde *OptionName* es el nombre de la opción: `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="004c7-138">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="004c7-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="004c7-139">Optional.</span></span> <span data-ttu-id="004c7-140">Si tiene varias aplicaciones web, determine el nombre del servicio en el que vaya a hacer las implementaciones; para ello, escriba este comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="004c7-140">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="004c7-141">Se devuelve una lista de valores, por ejemplo `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="004c7-141">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="004c7-142">El primer valor de esta lista (en este caso, `MDS1`) es necesario para implementar el modelo.</span><span class="sxs-lookup"><span data-stu-id="004c7-142">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="004c7-143">Para crear un paquete que contenga objetos de modelo y datos, escriba lo siguiente, donde *ModelName*, *VersionName*, *ServiceName*y *PackageName* son los nombres del modelo, la versión, el servicio y el archivo de salida .pkg, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="004c7-143">To create a package that contains model objects and data, type the following, where *ModelName*, *VersionName*, *ServiceName*,  and *PackageName* are the names of the model, version, service, and of the .pkg output file respectively:</span></span>  
  
    ```  
    MDSModelDeploy createpackage -model ModelName -version VersionName -service ServiceName -package PackageName -includedata  
    ```  
  
     <span data-ttu-id="004c7-144">Si no desea incluir datos, no utilice los modificadores `-version` y `-includedata` .</span><span class="sxs-lookup"><span data-stu-id="004c7-144">If you do not want to include data, do not use the `-version` and `-includedata` switches.</span></span>  
  
6.  <span data-ttu-id="004c7-145">Presiona Entrar.</span><span class="sxs-lookup"><span data-stu-id="004c7-145">Press Enter.</span></span> <span data-ttu-id="004c7-146">Cuando el paquete se crea correctamente, se muestra un mensaje que indica que "la operación de MDSModelDeploy se ha completado correctamente".</span><span class="sxs-lookup"><span data-stu-id="004c7-146">When the package is successfully created, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="004c7-147">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="004c7-147">Next Steps</span></span>  
  
-   [<span data-ttu-id="004c7-148">Implementar un paquete de implementación de modelo mediante MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="004c7-148">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
## <a name="see-also"></a><span data-ttu-id="004c7-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="004c7-149">See Also</span></span>  
 <span data-ttu-id="004c7-150">[Opciones de implementación de modelos &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="004c7-150">[Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span></span>  
 [<span data-ttu-id="004c7-151">Implementar modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="004c7-151">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
