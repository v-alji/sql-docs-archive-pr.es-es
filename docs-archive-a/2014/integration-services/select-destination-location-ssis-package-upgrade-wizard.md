---
title: Seleccionar ubicación de destino (Asistente para actualización del paquete SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectdestinationlocation.f1
ms.assetid: 89274a71-0ffe-4889-84df-f5a7d78459ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9411157434c3dbb9fb033f7b63b5e6041fd8f75d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677766"
---
# <a name="select-destination-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="3e79d-102">Seleccionar ubicación de destino (Asistente para actualización del paquete SSIS)</span><span class="sxs-lookup"><span data-stu-id="3e79d-102">Select Destination Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="3e79d-103">Utilice la página **Seleccionar ubicación de destino** para especificar el destino en el que desee guardar los paquetes actualizados.</span><span class="sxs-lookup"><span data-stu-id="3e79d-103">Use the **Select Destination Location** page to specify the destination to which to save the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e79d-104">Esta página solo está disponible cuando se ejecuta el Asistente para actualizar paquetes [!INCLUDE[ssIS](../includes/ssis-md.md)] desde [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3e79d-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="3e79d-105">**Para ejecutar el Asistente para actualización del paquete SSIS**</span><span class="sxs-lookup"><span data-stu-id="3e79d-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="3e79d-106">Actualizar paquetes de Integration Services mediante el Asistente para actualizar paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="3e79d-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="3e79d-107">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="3e79d-107">Static Options</span></span>  
 <span data-ttu-id="3e79d-108">**Guardar en ubicación de origen**</span><span class="sxs-lookup"><span data-stu-id="3e79d-108">**Save to source location**</span></span>  
 <span data-ttu-id="3e79d-109">Guarde los paquetes actualizados en la misma ubicación que la especificada en la página **Seleccionar ubicación de origen** del asistente.</span><span class="sxs-lookup"><span data-stu-id="3e79d-109">Save the upgraded packages to the same location as specified on the **Select Source Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="3e79d-110">Si los paquetes originales se almacenan en el sistema de archivos y desea que el asistente realice la copia de seguridad de esos paquetes, seleccione la opción **Guardar en ubicación de origen** .</span><span class="sxs-lookup"><span data-stu-id="3e79d-110">If the original packages are stored in the file system and you want the wizard to back up those packages, select the **Save to source location** option.</span></span> <span data-ttu-id="3e79d-111">Para más información, vea [Actualizar paquetes de Integration Services mediante el Asistente para actualizar paquetes SSIS](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="3e79d-111">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
 <span data-ttu-id="3e79d-112">**Seleccionar nueva ubicación de destino**</span><span class="sxs-lookup"><span data-stu-id="3e79d-112">**Select new destination location**</span></span>  
 <span data-ttu-id="3e79d-113">Guarde los paquetes actualizados en la ubicación de destino que se especifica en esta página.</span><span class="sxs-lookup"><span data-stu-id="3e79d-113">Save the upgraded packages to the destination location that is specified on this page.</span></span>  
  
 <span data-ttu-id="3e79d-114">**Origen del paquete**</span><span class="sxs-lookup"><span data-stu-id="3e79d-114">**Package source**</span></span>  
 <span data-ttu-id="3e79d-115">Especifique dónde se van a almacenar los paquetes de actualización.</span><span class="sxs-lookup"><span data-stu-id="3e79d-115">Specify where the upgrade packages are to be stored.</span></span> <span data-ttu-id="3e79d-116">Esta opción tiene los valores que figuran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="3e79d-116">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="3e79d-117">Value</span><span class="sxs-lookup"><span data-stu-id="3e79d-117">Value</span></span>|<span data-ttu-id="3e79d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e79d-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e79d-119">**Sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="3e79d-119">**File System**</span></span>|<span data-ttu-id="3e79d-120">Indica que los paquetes actualizados se van a guardar en una carpeta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="3e79d-120">Indicates that the upgraded packages are to be saved to a folder on the local computer.</span></span>|  
|<span data-ttu-id="3e79d-121">**Almacén de paquetes SSIS**</span><span class="sxs-lookup"><span data-stu-id="3e79d-121">**SSIS Package Store**</span></span>|<span data-ttu-id="3e79d-122">Indica que los paquetes actualizados se van a guardar en el almacén de paquetes de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="3e79d-122">Indicates that the upgraded packages are to be saved to the Integration Services package store.</span></span> <span data-ttu-id="3e79d-123">El almacén de paquetes consta del conjunto de carpetas del sistema de archivos que el servicio Integration Services administra.</span><span class="sxs-lookup"><span data-stu-id="3e79d-123">The package store consists of the set of file system folders that the Integration Services service manages.</span></span> <span data-ttu-id="3e79d-124">Para obtener más información, vea [Administración de paquetes &#40;servicio SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="3e79d-124">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="3e79d-125">Al seleccionar este valor, se muestran las opciones dinámicas correspondientes de **Origen del paquete** .</span><span class="sxs-lookup"><span data-stu-id="3e79d-125">Selecting this value displays the corresponding **Package source** dynamics options.</span></span>|  
|<span data-ttu-id="3e79d-126">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3e79d-126">**Microsoft SQL Server**</span></span>|<span data-ttu-id="3e79d-127">Indica que los paquetes actualizados se guardarán en una instancia existente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e79d-127">Indicates that the upgraded packages are to be saved to an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="3e79d-128">Al seleccionar este valor, se muestran las opciones dinámicas correspondientes de **Origen del paquete** .</span><span class="sxs-lookup"><span data-stu-id="3e79d-128">Selecting this value displays the corresponding dynamic **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="3e79d-129">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="3e79d-129">**Folder**</span></span>  
 <span data-ttu-id="3e79d-130">Escriba el nombre de una carpeta en la que se guardarán los paquetes actualizados, o bien haga clic en **Examinar** y busque la carpeta.</span><span class="sxs-lookup"><span data-stu-id="3e79d-130">Type the name of a folder to which the upgraded packages will be saved, or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="3e79d-131">**Browse**</span><span class="sxs-lookup"><span data-stu-id="3e79d-131">**Browse**</span></span>  
 <span data-ttu-id="3e79d-132">Busque la carpeta en la que se guardarán los paquetes actualizados.</span><span class="sxs-lookup"><span data-stu-id="3e79d-132">Browse to locate the folder to which the upgraded packages will be saved.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="3e79d-133">Opciones dinámicas de Origen del paquete</span><span class="sxs-lookup"><span data-stu-id="3e79d-133">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="3e79d-134">Origen del paquete = Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="3e79d-134">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="3e79d-135">**Server**</span><span class="sxs-lookup"><span data-stu-id="3e79d-135">**Server**</span></span>  
 <span data-ttu-id="3e79d-136">Escriba el nombre del servidor en el que se guardarán los paquetes de la actualización, o seleccione un servidor en la lista.</span><span class="sxs-lookup"><span data-stu-id="3e79d-136">Type the name of the server to which the upgrade packages will be saved, or select a server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="3e79d-137">Origen del paquete = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="3e79d-137">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="3e79d-138">**Server**</span><span class="sxs-lookup"><span data-stu-id="3e79d-138">**Server**</span></span>  
 <span data-ttu-id="3e79d-139">Escriba el nombre del servidor en el que se guardarán los paquetes de la actualización, o seleccione este servidor en la lista.</span><span class="sxs-lookup"><span data-stu-id="3e79d-139">Type the name of the server to which the upgrade packages will be saved, or select this server in the list.</span></span>  
  
 <span data-ttu-id="3e79d-140">**Usar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="3e79d-140">**Use Windows authentication**</span></span>  
 <span data-ttu-id="3e79d-141">Seleccione esta opción para utilizar la autenticación de Windows para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="3e79d-141">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="3e79d-142">**Usar autenticación SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3e79d-142">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="3e79d-143">Seleccione esta opción para usar la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="3e79d-143">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="3e79d-144">Si usa la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , debe proporcionar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="3e79d-144">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="3e79d-145">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="3e79d-145">**User name**</span></span>  
 <span data-ttu-id="3e79d-146">Escriba el nombre de usuario que se usará con la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="3e79d-146">Type the user name to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="3e79d-147">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="3e79d-147">**Password**</span></span>  
 <span data-ttu-id="3e79d-148">Escriba la contraseña que se usará con la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="3e79d-148">Type the password to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e79d-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e79d-149">See Also</span></span>  
 [<span data-ttu-id="3e79d-150">Actualizar paquetes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="3e79d-150">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
