---
title: Implementar paquetes mediante la utilidad de implementación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], installing
- installing packages
- dependencies [Integration Services]
- deploying packages [Integration Services], installing
ms.assetid: eaf4b56e-2023-4d17-971c-703031da758c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a09ad307dc0215fca679cfb1ef5a37031f951caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747153"
---
# <a name="deploy-packages-by-using-the-deployment-utility"></a><span data-ttu-id="c6a46-102">Implementar los paquetes mediante la utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="c6a46-102">Deploy Packages by Using the Deployment Utility</span></span>
  <span data-ttu-id="c6a46-103">Después de generar una utilidad de implementación para instalar paquetes de un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en un equipo distinto del que se utilizó para generar la utilidad, debe copiar la carpeta de implementación en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c6a46-103">When you have built a deployment utility to install packages from an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project on a different computer than the one on which the deployment utility was built, you must first copy the deployment folder to the destination computer.</span></span>  
  
 <span data-ttu-id="c6a46-104">La ruta de acceso a la carpeta de implementación se especifica en la propiedad DeploymentOutputPath del proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para el que ha creado la utilidad de implementación.</span><span class="sxs-lookup"><span data-stu-id="c6a46-104">The path of the deployment folder is specified in the DeploymentOutputPath property of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you created the deployment utility.</span></span> <span data-ttu-id="c6a46-105">La ruta predeterminada es bin\Deployment, relativa al proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6a46-105">The default path is bin\Deployment, relative to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="c6a46-106">Para más información, consulte [Create a Deployment Utility](../../2014/integration-services/create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="c6a46-106">For more information, see [Create a Deployment Utility](../../2014/integration-services/create-a-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="c6a46-107">Para instalar los paquetes, puede utilizar el Asistente para la instalación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="c6a46-107">You use the Package Installation Wizard to install the packages.</span></span> <span data-ttu-id="c6a46-108">Para iniciar el asistente, haga doble clic en el archivo de la utilidad de implementación una vez copiada la carpeta de implementación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c6a46-108">To launch the wizard, double-click the deployment utility file after you have copied the deployment folder to the server.</span></span> <span data-ttu-id="c6a46-109">El archivo recibe el nombre \<project name>.SSISDeploymentManifest, y se puede buscar en la carpeta de implementación del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c6a46-109">This file is named \<project name>.SSISDeploymentManifest, and can be found in the deployment folder on the destination computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6a46-110">Dependiendo de la versión del paquete que esté implementando, puede encontrar un error si tiene varias versiones diferentes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instaladas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="c6a46-110">Depending on the version of the package that you are deploying, you might encounter an error if you have different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installed side-by-side.</span></span> <span data-ttu-id="c6a46-111">Este error puede producirse porque la extensión de nombre de archivo .SSISDeploymentManifest es la misma para todas las versiones de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6a46-111">This error can occur because the .SSISDeploymentManifest file name extension is the same for all versions of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="c6a46-112">Al hacer doble clic en el archivo, se llama al instalador (dtsinstall.exe) para la versión instalada más recientemente de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], que podría no ser la misma versión que la del archivo de la utilidad de implementación.</span><span class="sxs-lookup"><span data-stu-id="c6a46-112">Double-clicking the file calls the installer (dtsinstall.exe) for the most recently installed version of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], which might not be the same version as the deployment utility file.</span></span> <span data-ttu-id="c6a46-113">Para evitar este problema, ejecute la versión correcta de dtsinstall.exe desde la línea de comandos y proporcione la ruta de acceso al archivo de la utilidad de implementación.</span><span class="sxs-lookup"><span data-stu-id="c6a46-113">To work around this problem, run the correct version of dtsinstall.exe from the command line, and provide the path of the deployment utility file.</span></span>  
  
 <span data-ttu-id="c6a46-114">El Asistente para la instalación de paquetes le guía paso a paso durante la instalación de paquetes en el sistema de archivos o en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6a46-114">The Package Installation Wizard guides you through the steps to install packages to the file system or to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c6a46-115">Puede configurar la instalación de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6a46-115">You can configure the installation in the following ways:</span></span>  
  
-   <span data-ttu-id="c6a46-116">Eligiendo el tipo de ubicación y la ubicación para instalar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="c6a46-116">Choosing the location type and location to install the packages.</span></span>  
  
-   <span data-ttu-id="c6a46-117">Eligiendo la ubicación para instalar las dependencias de paquete.</span><span class="sxs-lookup"><span data-stu-id="c6a46-117">Choosing location to install package dependencies.</span></span>  
  
-   <span data-ttu-id="c6a46-118">Validando los paquetes una vez instalados en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="c6a46-118">Validating the packages after they are installed on the target server.</span></span>  
  
 <span data-ttu-id="c6a46-119">Las dependencias basadas en archivos de los paquetes se instalan siempre en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="c6a46-119">The file-based dependencies for packages are always installed to the file system.</span></span> <span data-ttu-id="c6a46-120">Si instala un paquete en el sistema de archivos, las dependencias se instalarán en la misma carpeta que especificó para el paquete.</span><span class="sxs-lookup"><span data-stu-id="c6a46-120">If you install a package to the file system, the dependencies are installed in the same folder as the one that you specify for the package.</span></span> <span data-ttu-id="c6a46-121">Si instala un paquete en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], puede especificar la carpeta en la que desee almacenar las dependencias basadas en archivo.</span><span class="sxs-lookup"><span data-stu-id="c6a46-121">If you install a package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify the folder in which to store the file-based dependencies.</span></span>  
  
 <span data-ttu-id="c6a46-122">Si el paquete incluye configuraciones que desea modificar para utilizarlas en el equipo de destino, puede utilizar el asistente para actualizar los valores de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="c6a46-122">If the package includes configurations that you want to modify for use on the destination computer, you can update the values of the properties by using the wizard.</span></span>  
  
 <span data-ttu-id="c6a46-123">Además de instalar paquetes con el Asistente para instalar paquetes, puede copiar y mover paquetes con la utilidad **dtutil** del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c6a46-123">In addition to installing packages by using the Package Installation Wizard, you can copy and move packages by using the **dtutil** command prompt utility.</span></span> <span data-ttu-id="c6a46-124">Para más información, consulte [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="c6a46-124">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-deploy-packages-to-an-instance-of-sql-server"></a><span data-ttu-id="c6a46-125">Para implementar paquetes en una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6a46-125">To deploy packages to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="c6a46-126">Abra la carpeta de implementación en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c6a46-126">Open the deployment folder on the target computer.</span></span>  
  
2.  <span data-ttu-id="c6a46-127">Haga doble clic en el archivo de manifiesto \<project name>.SSISDeploymentManifest para iniciar el Asistente para la instalación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="c6a46-127">Double-click the manifest file, \<project name>.SSISDeploymentManifest, to start the Package Installation Wizard.</span></span>  
  
3.  <span data-ttu-id="c6a46-128">En la página **Implementar paquetes SSIS** , seleccione la opción **Implementación en SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="c6a46-128">On the **Deploy SSIS Packages** page, select the **SQL Server deployment** option.</span></span>  
  
4.  <span data-ttu-id="c6a46-129">Opcionalmente, puede seleccionar **Validar los paquetes después de la instalación** para validar los paquetes una vez instalados en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="c6a46-129">Optionally, select **Validate packages after installation** to validate packages after they are installed on the target server.</span></span>  
  
5.  <span data-ttu-id="c6a46-130">En la página **Especificar el servidor SQL Server de destino** , especifique la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en la que desee instalar los paquetes y seleccione un modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="c6a46-130">On the **Specify Target SQL Server** page, specify the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to install the packages to and select an authentication mode.</span></span> <span data-ttu-id="c6a46-131">Si selecciona la Autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , deberá proporcionar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="c6a46-131">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and a password.</span></span>  
  
6.  <span data-ttu-id="c6a46-132">En la página **Seleccionar la carpeta de instalación** , especifique la carpeta del sistema de archivos para las dependencias de paquete que se instalarán.</span><span class="sxs-lookup"><span data-stu-id="c6a46-132">On the **Select Installation Folder** page, specify the folder in the file system for the package dependencies that will be installed.</span></span>  
  
7.  <span data-ttu-id="c6a46-133">Si el paquete incluye configuraciones, puede modificarlas actualizando los valores de la lista **Valor** de la página Configurar paquetes.</span><span class="sxs-lookup"><span data-stu-id="c6a46-133">If the package includes configurations, you can edit configurations by updating values in the **Value** list on the Configure Packages page.</span></span>  
  
8.  <span data-ttu-id="c6a46-134">Si elige validar los paquetes después de la instalación, vea los resultados de la validación de los paquetes implementados.</span><span class="sxs-lookup"><span data-stu-id="c6a46-134">If you elected to validate packages after installation, view the validation results of the deployed packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a46-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6a46-135">See Also</span></span>  
 [<span data-ttu-id="c6a46-136">Implementación de paquetes &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c6a46-136">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
