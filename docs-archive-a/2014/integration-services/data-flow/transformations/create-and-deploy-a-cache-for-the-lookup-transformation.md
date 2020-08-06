---
title: Crear e implementar una memoria caché para la transformación Búsqueda | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- creating cache files for Lookup transformation
- deploying cache files for Lookup transformation
- Lookup transformation cache files
ms.assetid: cedf5cad-2fac-42d0-ad91-9461e117d330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33b00b84f1f1448c2ee80882aedc3a330ba0a5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662166"
---
# <a name="create-and-deploy-a-cache-for-the-lookup-transformation"></a><span data-ttu-id="1b739-102">Crear e implementar una memoria caché para la transformación Búsqueda</span><span class="sxs-lookup"><span data-stu-id="1b739-102">Create and Deploy a Cache for the Lookup Transformation</span></span>
  <span data-ttu-id="1b739-103">Puede crear e implementar un archivo caché (.caw) para la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1b739-103">You can create and deploy a cache file (.caw) for the Lookup transformation.</span></span> <span data-ttu-id="1b739-104">El conjunto de datos de referencia está almacenado en el archivo caché.</span><span class="sxs-lookup"><span data-stu-id="1b739-104">The reference dataset is stored in the cache file.</span></span>  
  
 <span data-ttu-id="1b739-105">La transformación Búsqueda realiza búsquedas mediante la combinación de datos de las columnas de entrada procedentes de un origen de datos conectado con columnas de un conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="1b739-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference dataset.</span></span>  
  
 <span data-ttu-id="1b739-106">Se crea un archivo caché mediante un administrador de conexiones de caché y una transformación de caché.</span><span class="sxs-lookup"><span data-stu-id="1b739-106">You create a cache file by using a Cache connection manager and a Cache Transform transformation.</span></span> <span data-ttu-id="1b739-107">Para obtener más información, consulte [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) y [Cache Transform](cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="1b739-107">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Transform](cache-transform.md).</span></span>  
  
 <span data-ttu-id="1b739-108">Para obtener más información acerca de la transformación Búsqueda y de los archivos caché, vea [Lookup Transformation](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="1b739-108">To learn more about the Lookup transformation and cache files, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
### <a name="to-create-a-cache-file"></a><span data-ttu-id="1b739-109">Para crear un archivo caché</span><span class="sxs-lookup"><span data-stu-id="1b739-109">To create a cache file</span></span>  
  
1.  <span data-ttu-id="1b739-110">En [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contiene el paquete con el que desea trabajar y ábralo.</span><span class="sxs-lookup"><span data-stu-id="1b739-110">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="1b739-111">En la pestaña **Flujo de control** , agregue una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="1b739-111">On the **Control Flow** tab, add a Data Flow task.</span></span>  
  
3.  <span data-ttu-id="1b739-112">En la pestaña **Flujo de datos** , agregue una transformación de caché al flujo de datos y, a continuación, conéctela a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1b739-112">On the **Data Flow** tab, add a Cache Transform transformation to the data flow, and then connect the transformation to a data source.</span></span>  
  
     <span data-ttu-id="1b739-113">Configure el origen de datos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1b739-113">Configure the data source as needed.</span></span>  
  
4.  <span data-ttu-id="1b739-114">Haga doble clic en la transformación de caché y, después, en el **Editor de transformación Caché**, en la página **Administrador de conexiones** , haga clic en **Nuevo** para crear un administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="1b739-114">Double-click the Cache Transform, and then in the **Cache Transformation Editor**, on the **Connection Manager** page, click **New** to create a new Cache connection manager.</span></span>  
  
5.  <span data-ttu-id="1b739-115">Para guardar la caché, en el **Editor del administrador de conexiones de caché**, en la pestaña **General** , configure el administrador de conexiones de caché mediante las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1b739-115">In the **Cache Connection Manager Editor**, on the **General** tab, configure the Cache connection manager to save the cache by selecting the following options:</span></span>  
  
    1.  <span data-ttu-id="1b739-116">Seleccione **Utilizar la caché del archivo**.</span><span class="sxs-lookup"><span data-stu-id="1b739-116">Select **Use file cache**.</span></span>  
  
    2.  <span data-ttu-id="1b739-117">Para **Nombre de archivo**, escriba la ruta de acceso del archivo.</span><span class="sxs-lookup"><span data-stu-id="1b739-117">For **File name**, type the file path.</span></span>  
  
     <span data-ttu-id="1b739-118">El sistema crea el archivo al ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="1b739-118">The system creates the file when you run the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1b739-119">El nivel de protección del paquete no se aplica al archivo caché.</span><span class="sxs-lookup"><span data-stu-id="1b739-119">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="1b739-120">Si el archivo caché contiene información confidencial, utilice una lista de control de acceso (ACL) para restringir el acceso a la ubicación o carpeta en la que almacena el archivo.</span><span class="sxs-lookup"><span data-stu-id="1b739-120">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="1b739-121">Solo debería permitir el acceso a ciertas cuentas.</span><span class="sxs-lookup"><span data-stu-id="1b739-121">You should enable access only to certain accounts.</span></span> <span data-ttu-id="1b739-122">Para más información, vea [Acceso a los archivos usados por los paquetes](../../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="1b739-122">For more information, see [Access to Files Used by Packages](../../access-to-files-used-by-packages.md).</span></span>  
  
6.  <span data-ttu-id="1b739-123">Haga clic en la pestaña **Columnas** e indique qué columnas son las columnas de índice mediante la opción **Posición de índice** .</span><span class="sxs-lookup"><span data-stu-id="1b739-123">Click the **Columns** tab, and then specify which columns are the index columns by using the **Index Position** option.</span></span>  
  
     <span data-ttu-id="1b739-124">Para las columnas de no índice, la posición de índice es 0.</span><span class="sxs-lookup"><span data-stu-id="1b739-124">For non-index columns, the index position is 0.</span></span> <span data-ttu-id="1b739-125">Para las columnas de índice, la posición de índice es un número secuencial positivo.</span><span class="sxs-lookup"><span data-stu-id="1b739-125">For index columns, the index position is a sequential, positive number.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1b739-126">Cuando la transformación Búsqueda se configura para utilizar un administrador de conexiones de caché, a las columnas de entrada solo se les puede asignar las columnas de índice del conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="1b739-126">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="1b739-127">Asimismo, todas las columnas de índice deben estar asignadas.</span><span class="sxs-lookup"><span data-stu-id="1b739-127">Also all index columns must be mapped.</span></span>  
  
     <span data-ttu-id="1b739-128">Para obtener más información, vea [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="1b739-128">For more information, see [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
7.  <span data-ttu-id="1b739-129">Configure la transformación de caché según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1b739-129">Configure the Cache Transform as needed.</span></span>  
  
     <span data-ttu-id="1b739-130">Para obtener más información, vea [Editor de transformación Caché &#40;página Administrador de conexiones&#41;](../../cache-transformation-editor-connection-manager-page.md) y [Editor de transformación Caché &#40;página Asignaciones&#41;](../../cache-transformation-editor-mappings-page.md).</span><span class="sxs-lookup"><span data-stu-id="1b739-130">For more information, see [Cache Transformation Editor &#40;Connection Manager Page&#41;](../../cache-transformation-editor-connection-manager-page.md) and [Cache Transformation Editor &#40;Mappings Page&#41;](../../cache-transformation-editor-mappings-page.md).</span></span>  
  
8.  <span data-ttu-id="1b739-131">Ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="1b739-131">Run the package.</span></span>  
  
### <a name="to-deploy-a-cache-file"></a><span data-ttu-id="1b739-132">Para implementar un archivo caché</span><span class="sxs-lookup"><span data-stu-id="1b739-132">To deploy a cache file</span></span>  
  
1.  <span data-ttu-id="1b739-133">En [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contiene el paquete con el que desea trabajar y ábralo.</span><span class="sxs-lookup"><span data-stu-id="1b739-133">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="1b739-134">Opcionalmente, puede crear una configuración de paquetes.</span><span class="sxs-lookup"><span data-stu-id="1b739-134">Optionally, create a package configuration.</span></span> <span data-ttu-id="1b739-135">Para obtener más información, vea [Crear configuraciones de paquetes](../../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="1b739-135">For more information, see [Create Package Configurations](../../create-package-configurations.md).</span></span>  
  
3.  <span data-ttu-id="1b739-136">Haga lo siguiente para agregar el archivo caché al proyecto:</span><span class="sxs-lookup"><span data-stu-id="1b739-136">Add the cache file to the project by doing the following:</span></span>  
  
    1.  <span data-ttu-id="1b739-137">En el Explorador de soluciones, seleccione el proyecto que abrió en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="1b739-137">In Solution Explorer, select the project you opened in step 1.</span></span>  
  
    2.  <span data-ttu-id="1b739-138">En el menú **Proyecto** , haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="1b739-138">On the **Project** menu, click **AddExisting Item**.</span></span>  
  
    3.  <span data-ttu-id="1b739-139">Seleccione el archivo caché y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1b739-139">Select the cache file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="1b739-140">El archivo aparece en la carpeta **Varios** del Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="1b739-140">The file appears in the **Miscellaneous** folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="1b739-141">Configure el proyecto para crear una utilidad de implementación y, a continuación, genere el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1b739-141">Configure the project to create a deployment utility, and then build the project.</span></span> <span data-ttu-id="1b739-142">Para más información, consulte [Create a Deployment Utility](../../create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="1b739-142">For more information, see [Create a Deployment Utility](../../create-a-deployment-utility.md).</span></span>  
  
     <span data-ttu-id="1b739-143">Se crea un archivo de manifiesto, \<*project name*>.SSISDeploymentManifest.xml, que enumera los archivos varios del proyecto, los paquetes y las configuraciones del paquete.</span><span class="sxs-lookup"><span data-stu-id="1b739-143">A manifest file, \<*project name*>.SSISDeploymentManifest.xml, is created that lists the miscellaneous files in the project, the packages, and the package configurations.</span></span>  
  
5.  <span data-ttu-id="1b739-144">Implemente el paquete en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="1b739-144">Deploy the package to the file system.</span></span> <span data-ttu-id="1b739-145">Para más información, consulte [Deploy Packages by Using the Deployment Utility](../../deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="1b739-145">For more information, see [Deploy Packages by Using the Deployment Utility](../../deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b739-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b739-146">See Also</span></span>  
 [<span data-ttu-id="1b739-147">Crear una utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="1b739-147">Create a Deployment Utility</span></span>](../../create-a-deployment-utility.md)  
  
  
