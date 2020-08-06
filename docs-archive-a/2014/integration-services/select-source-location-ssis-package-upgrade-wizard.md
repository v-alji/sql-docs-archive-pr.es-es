---
title: Seleccionar ubicación de origen (Asistente para actualización del paquete SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectsourcelocation.f1
ms.assetid: 429f146e-edb4-4401-a225-f2c8468971c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e24eec77dc87a6215f9d686cf5af964cc244d68d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744186"
---
# <a name="select-source-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="46398-102">Seleccionar ubicación de origen (Asistente para actualización del paquete SSIS)</span><span class="sxs-lookup"><span data-stu-id="46398-102">Select Source Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="46398-103">Utilice la página **Seleccionar ubicación de origen** para especificar el origen desde el que se actualizan los paquetes.</span><span class="sxs-lookup"><span data-stu-id="46398-103">Use the **Select Source Location** page to specify the source from which to upgrade packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="46398-104">Esta página solo está disponible cuando se ejecuta el Asistente para actualizar paquetes [!INCLUDE[ssIS](../includes/ssis-md.md)] desde [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="46398-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="46398-105">**Para ejecutar el Asistente para actualización del paquete SSIS**</span><span class="sxs-lookup"><span data-stu-id="46398-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="46398-106">Actualizar paquetes de Integration Services mediante el Asistente para actualizar paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="46398-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="46398-107">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="46398-107">Static Options</span></span>  
 <span data-ttu-id="46398-108">**Origen del paquete**</span><span class="sxs-lookup"><span data-stu-id="46398-108">**Package source**</span></span>  
 <span data-ttu-id="46398-109">Seleccione la ubicación de almacenamiento que contiene los paquetes que se van a actualizar.</span><span class="sxs-lookup"><span data-stu-id="46398-109">Select the storage location that contains the packages to be upgraded.</span></span> <span data-ttu-id="46398-110">Esta opción tiene los valores que figuran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="46398-110">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="46398-111">Value</span><span class="sxs-lookup"><span data-stu-id="46398-111">Value</span></span>|<span data-ttu-id="46398-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="46398-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="46398-113">**Sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="46398-113">**File System**</span></span>|<span data-ttu-id="46398-114">Indica que los paquetes que se van a actualizar están en una carpeta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="46398-114">Indicates that the packages to be upgraded are in a folder on the local computer.</span></span><br /><br /> <span data-ttu-id="46398-115">Para hacer que el asistente realice una copia de seguridad de los paquetes originales antes de actualizarlos, estos deben estar almacenados en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="46398-115">To have the wizard back up the original packages before upgrading those packages, the original packages must be stored in the file system.</span></span> <span data-ttu-id="46398-116">Para obtener más información, vea el tema de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="46398-116">For more information, see How To Topic.</span></span>|  
|<span data-ttu-id="46398-117">**Almacén de paquetes SSIS**</span><span class="sxs-lookup"><span data-stu-id="46398-117">**SSIS Package Store**</span></span>|<span data-ttu-id="46398-118">Indica que los paquetes que se van a actualizar están en el almacén de paquetes.</span><span class="sxs-lookup"><span data-stu-id="46398-118">Indicates that the packages to be upgraded are in the package store.</span></span> <span data-ttu-id="46398-119">El almacén de paquetes consta del conjunto de carpetas del sistema de archivos que el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] administra.</span><span class="sxs-lookup"><span data-stu-id="46398-119">The package store consists of the set of file system folders that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span> <span data-ttu-id="46398-120">Para obtener más información, vea [Administración de paquetes &#40;servicio SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="46398-120">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="46398-121">Al seleccionar este valor, se muestran las opciones dinámicas de **Origen del paquete** correspondientes.</span><span class="sxs-lookup"><span data-stu-id="46398-121">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
|<span data-ttu-id="46398-122">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="46398-122">**Microsoft SQL Server**</span></span>|<span data-ttu-id="46398-123">Indica que los paquetes que se van a actualizar son de una instancia existente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46398-123">Indicates the packages to be upgraded are from an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="46398-124">Al seleccionar este valor, se muestran las opciones dinámicas de **Origen del paquete** correspondientes.</span><span class="sxs-lookup"><span data-stu-id="46398-124">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="46398-125">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="46398-125">**Folder**</span></span>  
 <span data-ttu-id="46398-126">Escriba el nombre de una carpeta que contenga los paquetes que quiere actualizar o haga clic en **Examinar** y busque la carpeta.</span><span class="sxs-lookup"><span data-stu-id="46398-126">Type the name of a folder that contains the packages you want to upgrade or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="46398-127">**Browse**</span><span class="sxs-lookup"><span data-stu-id="46398-127">**Browse**</span></span>  
 <span data-ttu-id="46398-128">Busque la carpeta que contiene los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="46398-128">Browse to locate the folder that contains the packages you want to upgrade.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="46398-129">Opciones dinámicas de Origen del paquete</span><span class="sxs-lookup"><span data-stu-id="46398-129">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="46398-130">Origen del paquete = Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="46398-130">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="46398-131">**Server**</span><span class="sxs-lookup"><span data-stu-id="46398-131">**Server**</span></span>  
 <span data-ttu-id="46398-132">Escriba el nombre del servidor que tiene los paquetes que se van a actualizar o seleccione este servidor en la lista.</span><span class="sxs-lookup"><span data-stu-id="46398-132">Type the name of the server that has the packages to be upgraded, or select this server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="46398-133">Origen del paquete = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="46398-133">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="46398-134">**Server**</span><span class="sxs-lookup"><span data-stu-id="46398-134">**Server**</span></span>  
 <span data-ttu-id="46398-135">Escriba el nombre del servidor que tiene los paquetes que se van a actualizar o seleccione este servidor en la lista.</span><span class="sxs-lookup"><span data-stu-id="46398-135">Type the name of the server that has the packages to be upgraded, or select this server from the list.</span></span>  
  
 <span data-ttu-id="46398-136">**Usar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="46398-136">**Use Windows authentication**</span></span>  
 <span data-ttu-id="46398-137">Seleccione esta opción para utilizar la autenticación de Windows para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="46398-137">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="46398-138">**Usar autenticación SQL Server**</span><span class="sxs-lookup"><span data-stu-id="46398-138">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="46398-139">Seleccione esta opción para usar la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="46398-139">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="46398-140">Si usa la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , debe proporcionar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="46398-140">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="46398-141">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="46398-141">**User name**</span></span>  
 <span data-ttu-id="46398-142">Escriba el nombre de usuario que la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usará para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="46398-142">Type the user name that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
 <span data-ttu-id="46398-143">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="46398-143">**Password**</span></span>  
 <span data-ttu-id="46398-144">Escriba la contraseña que la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usará para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="46398-144">Type the password that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46398-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46398-145">See Also</span></span>  
 [<span data-ttu-id="46398-146">Actualizar paquetes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="46398-146">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
