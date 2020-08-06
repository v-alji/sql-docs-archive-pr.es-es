---
title: Seleccionar opciones de Administración de paquetes (Asistente para actualización del paquete SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectpackagemgtoptions.f1
ms.assetid: 810fc020-51cd-43ed-9f35-af99b4f35947
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5113ad5a1f6758a75742ca58aef04ce92168649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677764"
---
# <a name="select-package-management-options-ssis-package-upgrade-wizard"></a><span data-ttu-id="82f21-102">Seleccionar opciones de administración de paquetes (Asistente para actualización del paquete SSIS)</span><span class="sxs-lookup"><span data-stu-id="82f21-102">Select Package Management Options (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="82f21-103">Utilice la página **Seleccionar opciones de administración de paquetes** con el fin de especificar las opciones para actualizar paquetes.</span><span class="sxs-lookup"><span data-stu-id="82f21-103">Use the **Select Package Management Options** page to specify options for upgrading packages.</span></span>  
  
 <span data-ttu-id="82f21-104">**Para ejecutar el Asistente para actualización del paquete SSIS**</span><span class="sxs-lookup"><span data-stu-id="82f21-104">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="82f21-105">Actualizar paquetes de Integration Services mediante el Asistente para actualizar paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="82f21-105">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="82f21-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="82f21-106">Options</span></span>  
 <span data-ttu-id="82f21-107">**Actualizar las cadenas de conexión para reflejar los nuevos nombres de proveedor**</span><span class="sxs-lookup"><span data-stu-id="82f21-107">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="82f21-108">Se actualizan las cadenas de conexión para que usen los nombres de los proveedores siguientes para la versión actual de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="82f21-108">Update the connection strings to use the names for the following providers for the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="82f21-109">Proveedor OLE DB para [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82f21-109">OLE DB Provider for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="82f21-110">Native Client</span><span class="sxs-lookup"><span data-stu-id="82f21-110">Native Client</span></span>  
  
 <span data-ttu-id="82f21-111">El Asistente para actualizar paquetes de [!INCLUDE[ssIS](../includes/ssis-md.md)] solo actualiza las cadenas de conexión que se almacenan en administradores de conexiones.</span><span class="sxs-lookup"><span data-stu-id="82f21-111">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="82f21-112">No actualiza las cadenas de conexión que se construyen dinámicamente utilizando el lenguaje de expresiones de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o código en una tarea Script.</span><span class="sxs-lookup"><span data-stu-id="82f21-112">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="82f21-113">**Validar los paquetes de actualización**</span><span class="sxs-lookup"><span data-stu-id="82f21-113">**Validate upgrade packages**</span></span>  
 <span data-ttu-id="82f21-114">Se validan los paquetes de actualización y se guardan solo aquéllos que superan la validación.</span><span class="sxs-lookup"><span data-stu-id="82f21-114">Validate the upgrade packages and save only those upgrade packages that pass validation.</span></span>  
  
 <span data-ttu-id="82f21-115">Si no selecciona esta opción, el asistente no validará los paquetes de actualización.</span><span class="sxs-lookup"><span data-stu-id="82f21-115">If you do not select this option, the wizard will not validate upgrade packages.</span></span> <span data-ttu-id="82f21-116">Por consiguiente, el asistente guardará todos los paquetes de actualización, sin tener en cuenta si son válidos o no.</span><span class="sxs-lookup"><span data-stu-id="82f21-116">Therefore, the wizard will save all upgrade packages, regardless of whether the packages are valid or not.</span></span> <span data-ttu-id="82f21-117">El asistente guarda los paquetes de actualización en el destino que se especifica en la página **Seleccionar ubicación de destino** del asistente.</span><span class="sxs-lookup"><span data-stu-id="82f21-117">The wizard saves upgrade packages to the destination that is specified on the **SelectDestination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="82f21-118">La validación agrega tiempo al proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="82f21-118">Validation adds time to the upgrade process.</span></span> <span data-ttu-id="82f21-119">Se recomienda no seleccionar esta opción con paquetes grandes que probablemente se actualizarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="82f21-119">We recommend that you do not select this option for large packages that are likely to be upgraded successfully.</span></span>  
  
 <span data-ttu-id="82f21-120">**Crear nuevo id. de paquete**</span><span class="sxs-lookup"><span data-stu-id="82f21-120">**Create new package IDs**</span></span>  
 <span data-ttu-id="82f21-121">Se crean nuevos identificadores de paquete para los paquetes de actualización.</span><span class="sxs-lookup"><span data-stu-id="82f21-121">Create new package IDs for the upgrade packages.</span></span>  
  
 <span data-ttu-id="82f21-122">**Continuar el proceso de actualización cuando la actualización de un paquete genera un error**</span><span class="sxs-lookup"><span data-stu-id="82f21-122">**Continue upgrade process when a package upgrade fails**</span></span>  
 <span data-ttu-id="82f21-123">Se especifica que cuando un paquete no se pueda actualizar, el Asistente para actualizar paquetes [!INCLUDE[ssIS](../includes/ssis-md.md)] continúe actualizando el resto de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="82f21-123">Specify that when a package cannot be upgraded, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard continues to upgrade the remaining packages.</span></span>  
  
 <span data-ttu-id="82f21-124">**Conflictos con nombres de paquete**</span><span class="sxs-lookup"><span data-stu-id="82f21-124">**Package name conflicts**</span></span>  
 <span data-ttu-id="82f21-125">Se especifica cómo debe administrar el asistente los paquetes que tienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="82f21-125">Specify how the wizard should handle packages that have the same name.</span></span> <span data-ttu-id="82f21-126">Esta opción tiene los valores que figuran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="82f21-126">This option has the values listed in the following table.</span></span>  
  
 <span data-ttu-id="82f21-127">**Sobrescribir archivos de paquete existentes**</span><span class="sxs-lookup"><span data-stu-id="82f21-127">**Overwrite existing package files**</span></span>  
 <span data-ttu-id="82f21-128">Se reemplaza el paquete existente por el paquete de actualización del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="82f21-128">Replaces the existing package with the upgrade package of the same name.</span></span>  
  
 <span data-ttu-id="82f21-129">**Agregar sufijos numéricos para actualizar nombres de paquete**</span><span class="sxs-lookup"><span data-stu-id="82f21-129">**Add numeric suffixes to upgrade package names**</span></span>  
 <span data-ttu-id="82f21-130">Se agrega un sufijo numérico al nombre del paquete de actualización.</span><span class="sxs-lookup"><span data-stu-id="82f21-130">Adds a numeric suffix to the name of the upgrade package.</span></span>  
  
 <span data-ttu-id="82f21-131">**No actualizar paquetes**</span><span class="sxs-lookup"><span data-stu-id="82f21-131">**Do not upgrade packages**</span></span>  
 <span data-ttu-id="82f21-132">Se detiene la actualización de los paquetes y se muestra un error cuando se completa el asistente.</span><span class="sxs-lookup"><span data-stu-id="82f21-132">Stops the packages from being upgraded and displays an error when you complete the wizard.</span></span>  
  
 <span data-ttu-id="82f21-133">Estas opciones no están disponibles cuando se selecciona la opción **Guardar en ubicación de origen** en la página **Seleccionar ubicación de destino** del asistente.</span><span class="sxs-lookup"><span data-stu-id="82f21-133">These options are not available when you select the **Save to source location** option on the **Select Destination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="82f21-134">**Omitir configuraciones**</span><span class="sxs-lookup"><span data-stu-id="82f21-134">**Ignore Configurations**</span></span>  
 <span data-ttu-id="82f21-135">No carga configuraciones de paquetes durante la actualización del paquete.</span><span class="sxs-lookup"><span data-stu-id="82f21-135">Does not load package configurations during the package upgrade.</span></span> <span data-ttu-id="82f21-136">Si se selecciona esta opción se reduce el tiempo necesario para actualizar el paquete.</span><span class="sxs-lookup"><span data-stu-id="82f21-136">Selecting this option reduces the time required to upgrade the package.</span></span>  
  
 <span data-ttu-id="82f21-137">**Realizar copia de seguridad de paquetes originales**</span><span class="sxs-lookup"><span data-stu-id="82f21-137">**Backup original packages**</span></span>  
 <span data-ttu-id="82f21-138">El asistente hace una copia de seguridad de los paquetes originales en una carpeta **SSISBackupFolder** .</span><span class="sxs-lookup"><span data-stu-id="82f21-138">Have the wizard back up the original packages to an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="82f21-139">El asistente crea la carpeta **SSISBackupFolder** como una subcarpeta de la carpeta que contiene los paquetes originales y los paquetes actualizados.</span><span class="sxs-lookup"><span data-stu-id="82f21-139">The wizard creates the **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82f21-140">Esta opción solo está disponible cuando se especifica que los paquetes originales y los paquetes actualizados se almacenen en el sistema de archivos y en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="82f21-140">This option is available only when you specify that the original packages and the upgraded packages are stored in the file system and in the same folder.</span></span>  
  
 <span data-ttu-id="82f21-141">Para más información, vea [Actualizar paquetes de Integration Services mediante el Asistente para actualizar paquetes SSIS](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="82f21-141">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f21-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82f21-142">See Also</span></span>  
 [<span data-ttu-id="82f21-143">Actualizar paquetes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="82f21-143">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
