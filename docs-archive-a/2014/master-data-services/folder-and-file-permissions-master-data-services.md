---
title: Permisos de carpetas y archivos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- security [Master Data Services], file and folder
- folders [Master Data Services]
- files [Master Data Services]
ms.assetid: 6402d81d-7349-47b1-95ca-99b0c0f4f373
author: lrtoyou1223
ms.author: lle
robots: noindex,nofollow
ms.openlocfilehash: 6dc356e074574a4c520b1f4de2f41db0e983c4df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745873"
---
# <a name="folder-and-file-permissions-master-data-services"></a><span data-ttu-id="73fc0-102">Permisos de carpetas y archivos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="73fc0-102">Folder and File Permissions (Master Data Services)</span></span>
  <span data-ttu-id="73fc0-103">Al instalar [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], las carpetas y archivos se instalan en el sistema de archivos en la ruta de instalación que especifica para las características compartidas de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73fc0-103">When you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], folders and files are installed in the file system at the installation path you specify for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features.</span></span> <span data-ttu-id="73fc0-104">Si usa la ruta de instalación predeterminada para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] las características compartidas, la ruta de instalación de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] es *unidad*: \Archivos de programa\Microsoft SQL Server\120\Master Data Services.</span><span class="sxs-lookup"><span data-stu-id="73fc0-104">If you use the default installation path for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features, the installation path for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services.</span></span> <span data-ttu-id="73fc0-105">Aunque puede cambiar la ruta de instalación de las características compartidas, sea consciente de los permisos que se heredan de la carpeta primaria y de los que se establecen explícitamente para [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73fc0-105">Although you can change the shared features installation path, be aware of permissions that are inherited from the parent folder and permissions that are explicitly set for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span>  
  
## <a name="inherited-permissions"></a><span data-ttu-id="73fc0-106">Permisos heredados</span><span class="sxs-lookup"><span data-stu-id="73fc0-106">Inherited Permissions</span></span>  
 <span data-ttu-id="73fc0-107">La carpeta **Microsoft SQL Server** , la carpeta **Master Data Services** y la mayoría de las subcarpetas y archivos heredan los permisos de la carpeta primaria especificada en el programa de instalación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73fc0-107">The **Microsoft SQL Server** folder, the **Master Data Services** folder, and most subfolders and files inherit permissions from the parent folder specified in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="73fc0-108">Si elige la ubicación de instalación predeterminada, la carpeta principal de la que se heredan los permisos es *unidad*:\Archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="73fc0-108">If you choose the default installation location, the parent folder that permissions are inherited from is *drive*:\Program Files.</span></span> <span data-ttu-id="73fc0-109">En la siguiente tabla se describen los permisos predeterminado para **Archivos de programa**.</span><span class="sxs-lookup"><span data-stu-id="73fc0-109">The following table describes the default permissions for **Program Files**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73fc0-110">Si modifica los permisos predeterminados para **Archivos de programa**o elige una ubicación de instalación diferente, los permisos de las carpetas y archivos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] heredados de la carpeta principal y los permisos generales pueden diferir de los descritos en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="73fc0-110">If you modify default permissions for **Program Files**, or you choose a different installation location, the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] folders and files inherit permissions from their parent folder accordingly, and the permissions might differ from those described in the following table.</span></span>  
  
###### <a name="program-files-default-permissions"></a><span data-ttu-id="73fc0-111">Permisos predeterminados de Archivos de programas</span><span class="sxs-lookup"><span data-stu-id="73fc0-111">Program Files Default Permissions</span></span>  
  
|<span data-ttu-id="73fc0-112">Nombre de grupo o cuenta</span><span class="sxs-lookup"><span data-stu-id="73fc0-112">Group or account name</span></span>|<span data-ttu-id="73fc0-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="73fc0-113">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="73fc0-114">CREATOR OWNER</span><span class="sxs-lookup"><span data-stu-id="73fc0-114">CREATOR OWNER</span></span>|<span data-ttu-id="73fc0-115">Permisos especiales</span><span class="sxs-lookup"><span data-stu-id="73fc0-115">Special permissions</span></span>|  
|<span data-ttu-id="73fc0-116">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="73fc0-116">SYSTEM</span></span>|<span data-ttu-id="73fc0-117">Permisos especiales</span><span class="sxs-lookup"><span data-stu-id="73fc0-117">Special permissions</span></span>|  
|<span data-ttu-id="73fc0-118">Administradores</span><span class="sxs-lookup"><span data-stu-id="73fc0-118">Administrators</span></span>|<span data-ttu-id="73fc0-119">Permisos especiales</span><span class="sxs-lookup"><span data-stu-id="73fc0-119">Special permissions</span></span>|  
|<span data-ttu-id="73fc0-120">Usuarios</span><span class="sxs-lookup"><span data-stu-id="73fc0-120">Users</span></span>|<span data-ttu-id="73fc0-121">Lectura y ejecución, mostrar contenido de carpetas, lectura</span><span class="sxs-lookup"><span data-stu-id="73fc0-121">Read & execute, List folder contents, Read</span></span>|  
|<span data-ttu-id="73fc0-122">TrustedInstaller</span><span class="sxs-lookup"><span data-stu-id="73fc0-122">TrustedInstaller</span></span>|<span data-ttu-id="73fc0-123">Mostrar contenido de carpetas, permisos especiales</span><span class="sxs-lookup"><span data-stu-id="73fc0-123">List folder contents, Special permissions</span></span>|  
  
## <a name="explicit-permissions"></a><span data-ttu-id="73fc0-124">Permisos explícitos</span><span class="sxs-lookup"><span data-stu-id="73fc0-124">Explicit Permissions</span></span>  
 <span data-ttu-id="73fc0-125">La carpeta **MDSTempDir** y el archivo Web.config de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (en la carpeta **WebApplication** ) no heredan permisos.</span><span class="sxs-lookup"><span data-stu-id="73fc0-125">The **MDSTempDir** folder and the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file (in the **WebApplication** folder) do not inherit permissions.</span></span> <span data-ttu-id="73fc0-126">Tienen permisos que se establecen explícitamente al instalar [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], sin tener en cuenta la ruta de instalación que elija.</span><span class="sxs-lookup"><span data-stu-id="73fc0-126">They have permissions that are set explicitly when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], regardless of the installation path you choose.</span></span> <span data-ttu-id="73fc0-127">No modifique estos permisos.</span><span class="sxs-lookup"><span data-stu-id="73fc0-127">Do not modify these permissions.</span></span>  
  
###### <a name="mdstempdir-permissions"></a><span data-ttu-id="73fc0-128">Permisos de MDSTempDir</span><span class="sxs-lookup"><span data-stu-id="73fc0-128">MDSTempDir Permissions</span></span>  
  
|<span data-ttu-id="73fc0-129">Nombre de grupo o cuenta</span><span class="sxs-lookup"><span data-stu-id="73fc0-129">Group or account name</span></span>|<span data-ttu-id="73fc0-130">Permisos</span><span class="sxs-lookup"><span data-stu-id="73fc0-130">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="73fc0-131">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="73fc0-131">SYSTEM</span></span>|<span data-ttu-id="73fc0-132">Modificar, lectura y ejecución, mostrar contenido de carpetas, lectura, escritura</span><span class="sxs-lookup"><span data-stu-id="73fc0-132">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="73fc0-133">Administradores</span><span class="sxs-lookup"><span data-stu-id="73fc0-133">Administrators</span></span>|<span data-ttu-id="73fc0-134">Modificar, lectura y ejecución, mostrar contenido de carpetas, lectura, escritura</span><span class="sxs-lookup"><span data-stu-id="73fc0-134">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="73fc0-135">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="73fc0-135">MDS_ServiceAccounts</span></span>|<span data-ttu-id="73fc0-136">Modificar, lectura y ejecución, mostrar contenido de carpetas, lectura, escritura</span><span class="sxs-lookup"><span data-stu-id="73fc0-136">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
  
###### <a name="webconfig-permissions"></a><span data-ttu-id="73fc0-137">Permisos de Web.config</span><span class="sxs-lookup"><span data-stu-id="73fc0-137">Web.config Permissions</span></span>  
  
|<span data-ttu-id="73fc0-138">Nombre de grupo o cuenta</span><span class="sxs-lookup"><span data-stu-id="73fc0-138">Group or account name</span></span>|<span data-ttu-id="73fc0-139">Permisos</span><span class="sxs-lookup"><span data-stu-id="73fc0-139">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="73fc0-140">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="73fc0-140">SYSTEM</span></span>|<span data-ttu-id="73fc0-141">Control total, modificar, lectura y ejecución, lectura, escritura</span><span class="sxs-lookup"><span data-stu-id="73fc0-141">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="73fc0-142">Administradores</span><span class="sxs-lookup"><span data-stu-id="73fc0-142">Administrators</span></span>|<span data-ttu-id="73fc0-143">Control total, modificar, lectura y ejecución, lectura, escritura</span><span class="sxs-lookup"><span data-stu-id="73fc0-143">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="73fc0-144">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="73fc0-144">MDS_ServiceAccounts</span></span>|<span data-ttu-id="73fc0-145">Lectura y ejecutar, lectura</span><span class="sxs-lookup"><span data-stu-id="73fc0-145">Read & execute, Read</span></span>|  
  
 <span data-ttu-id="73fc0-146">Para obtener más información sobre el contenido del archivo Web.config de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], consulte [Referencia de la configuración web &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="73fc0-146">For more information about the contents of the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file, see [Web Configuration Reference &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73fc0-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73fc0-147">See Also</span></span>  
 [<span data-ttu-id="73fc0-148">Instalar Master Data Services</span><span class="sxs-lookup"><span data-stu-id="73fc0-148">Install Master Data Services</span></span>](install-windows/install-master-data-services.md)  
  
  
