---
title: Importar y exportar paquetes (servicio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], importing
- packages [Integration Services], exporting
- importing packages
- exporting packages
ms.assetid: ef18ec11-b536-47d9-abd1-794099f43486
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b69f9d23431ed86f6b84be6857b7104cd8ba3dcc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674948"
---
# <a name="import-and-export-packages-ssis-service"></a><span data-ttu-id="63013-102">Importar y exportar paquetes (servicio SSIS)</span><span class="sxs-lookup"><span data-stu-id="63013-102">Import and Export Packages (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="63013-103">En este tema se describe el servicio de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un servicio Windows para administrar paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63013-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="63013-104">admite el servicio para mantener la compatibilidad con versiones anteriores de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63013-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="63013-105">A partir de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], puede administrar objetos como paquetes en el servidor de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="63013-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="63013-106">Los paquetes se pueden guardar tanto en la tabla sysssispackages como en la base de datos msdb de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="63013-106">Packages can be saved either in the sysssispackages table in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database or in the file system.</span></span>  
  
 <span data-ttu-id="63013-107">El almacén de paquetes, que es el almacén lógico que el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] supervisa y administra, puede incluir tanto la base de datos msdb como las carpetas del sistema de archivos especificadas en el archivo de configuración del servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63013-107">The package store, which is the logical storage that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service monitors and manages, can include both the msdb database and the file system folders specified in the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="63013-108">Puede importar y exportar paquetes entre los siguientes tipos de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="63013-108">You can import and export packages between the following storage types:</span></span>  
  
-   <span data-ttu-id="63013-109">Carpetas del sistema de archivos en cualquier lugar del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="63013-109">File system folders anywhere in the file system.</span></span>  
  
-   <span data-ttu-id="63013-110">Carpetas del almacén de paquetes SSIS.</span><span class="sxs-lookup"><span data-stu-id="63013-110">Folders in the SSIS Package Store.</span></span> <span data-ttu-id="63013-111">Las dos carpetas predeterminadas se llaman Sistema de archivos y MSDB.</span><span class="sxs-lookup"><span data-stu-id="63013-111">The two default folders are named File System and MSDB.</span></span>  
  
-   <span data-ttu-id="63013-112">La base de datos msdb de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63013-112">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="63013-113">permite importar y exportar paquetes y, a través de estos procesos, cambiar el formato de almacenamiento y la ubicación de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="63013-113">gives you the ability to import and export packages, and by doing this change the storage format and location of packages.</span></span> <span data-ttu-id="63013-114">Con las características de importación y exportación, puede agregar paquetes al sistema de archivos, al almacén de paquetes o a la base de datos msdb, así como copiar paquetes de un formato de almacenamiento a otro.</span><span class="sxs-lookup"><span data-stu-id="63013-114">Using the import and export features, you can add packages to the file system, package store, or msdb database, and copy packages from one storage format to another.</span></span> <span data-ttu-id="63013-115">Por ejemplo, los paquetes guardados en msdb se pueden copiar al sistema de archivos y viceversa.</span><span class="sxs-lookup"><span data-stu-id="63013-115">For example, packages saved in msdb can be copied to the file system and vice versa.</span></span>  
  
 <span data-ttu-id="63013-116">También puede copiar un paquete a un formato distinto con la utilidad del símbolo del sistema **dtutil** (dtutil.exe).</span><span class="sxs-lookup"><span data-stu-id="63013-116">You can also copy a package to a different format using the **dtutil** command prompt utility (dtutil.exe).</span></span> <span data-ttu-id="63013-117">Para más información, consulte [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="63013-117">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
## <a name="to-import-or-export-a-package"></a><span data-ttu-id="63013-118">Para importar o exportar un paquete</span><span class="sxs-lookup"><span data-stu-id="63013-118">To import or export a package</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="63013-119">En este tema se describe el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que forma parte de [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63013-119">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that is part of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="63013-120">admite el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] por motivos de compatibilidad con [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63013-120">supports the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service for backward compatibility with [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="63013-121">Para más información sobre la administración de paquetes en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], vea [Integration Services &#40;SSIS&#41; Server](catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="63013-121">For information about managing packages in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], see [Integration Services &#40;SSIS&#41; Server](catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="63013-122">Puede importar o exportar un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] de las ubicaciones siguientes o a dichas ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="63013-122">You can import or export an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from or to the following locations:</span></span>  
  
-   <span data-ttu-id="63013-123">Puede importar un paquete que esté almacenado en una instancia de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], en el sistema de archivos o en el almacén de paquetes de [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63013-123">You can import a package that is stored in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], in the file system, or in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span> <span data-ttu-id="63013-124">El paquete importado se guarda en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o en una carpeta del almacén de paquetes de [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63013-124">The imported package is saved to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to a folder in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span>  
  
-   <span data-ttu-id="63013-125">Puede exportar un paquete que esté almacenado en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], en el sistema de archivos, o en el almacén de paquetes de [!INCLUDE[ssIS](../includes/ssis-md.md)] a una ubicación y un formato de almacenamiento diferentes.</span><span class="sxs-lookup"><span data-stu-id="63013-125">You can export a package that is stored in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], the file system, or the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store to a different storage format and location.</span></span>  
  
 <span data-ttu-id="63013-126">Sin embargo, hay algunas restricciones en la importación y exportación de un paquete entre versiones diferentes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="63013-126">However, there are some restrictions on importing and exporting a package between different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="63013-127">En una instancia de [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], puede importar paquetes de una instancia de [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], pero no puede exportar paquetes a una instancia de [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63013-127">On an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], you can import packages from an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], but you cannot export packages to an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="63013-128">En una instancia de [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], no puede importar paquetes de una instancia de [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)]o exportar paquetes a dicha instancia.</span><span class="sxs-lookup"><span data-stu-id="63013-128">On an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you cannot import packages from, or export packages to, an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="63013-129">Los procedimientos siguientes describen cómo utilizar [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para importar o exportar un paquete.</span><span class="sxs-lookup"><span data-stu-id="63013-129">The following procedures describe how to use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to import or export a package.</span></span>  
  
#### <a name="to-import-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="63013-130">Para importar un paquete con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63013-130">To import a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="63013-131">Haga clic en **Inicio**, seleccione **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="63013-131">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="63013-132">En el cuadro de diálogo **Conectar con el servidor** establezca las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="63013-132">In the **Connect to Server** dialog box set the following options:</span></span>  
  
    -   <span data-ttu-id="63013-133">En el cuadro **Tipo de servidor** , seleccione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="63013-133">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="63013-134">En el cuadro **Nombre del servidor**, escriba un nombre de servidor o haga clic en **\<Browse for more...>** y busque el servidor que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="63013-134">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="63013-135">Si el Explorador de objetos no está abierto, en el menú **Ver** , haga clic en **Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="63013-135">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="63013-136">En el Explorador de objetos, expanda la carpeta **Paquetes almacenados** .</span><span class="sxs-lookup"><span data-stu-id="63013-136">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="63013-137">Expanda las subcarpetas para encontrar la carpeta en la que desea importar un paquete.</span><span class="sxs-lookup"><span data-stu-id="63013-137">Expand the subfolders to locate the folder into which you want to import a package.</span></span>  
  
6.  <span data-ttu-id="63013-138">Haga clic con el botón derecho en la carpeta, haga clic en **Importar paquete**.</span><span class="sxs-lookup"><span data-stu-id="63013-138">Right-click the folder, click **Import Package**.</span></span> <span data-ttu-id="63013-139">y, a continuación, realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="63013-139">and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="63013-140">Para importar desde una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], seleccione la opción **SQL Server** y luego especifique el servidor y seleccione el modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="63013-140">To import from an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="63013-141">Si selecciona Autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , proporcione un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="63013-141">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="63013-142">Haga clic en el botón Examinar **(…)** , seleccione el paquete que quiera importar y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="63013-142">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
    -   <span data-ttu-id="63013-143">Para importar desde el sistema de archivos, seleccione la opción **Sistema de archivos** .</span><span class="sxs-lookup"><span data-stu-id="63013-143">To import from the file system, select the **File system** option.</span></span>  
  
         <span data-ttu-id="63013-144">Haga clic en el botón Examinar **(…)** , seleccione el paquete que quiera importar y, después, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="63013-144">Click the browse button **(...)**, select the package to import, and then click **Open.**</span></span>  
  
    -   <span data-ttu-id="63013-145">Para importar desde el almacén de paquetes [!INCLUDE[ssIS](../includes/ssis-md.md)] , seleccione la opción **Almacén de paquetes SSIS** y especifique el servidor.</span><span class="sxs-lookup"><span data-stu-id="63013-145">To import from the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, select the **SSIS Package Store** option and specify the server.</span></span>  
  
         <span data-ttu-id="63013-146">Haga clic en el botón Examinar **(…)** , seleccione el paquete que quiera importar y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="63013-146">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="63013-147">Si lo desea, actualice el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="63013-147">Optionally, update the package name.</span></span>  
  
8.  <span data-ttu-id="63013-148">Para actualizar el nivel de protección del paquete, haga clic en el botón Examinar **(…)** y seleccione otro nivel de protección con el cuadro de diálogo **Nivel de protección de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="63013-148">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="63013-149">Si se selecciona la opción **Cifrar la información confidencial con una contraseña** o la opción **Cifrar todos los datos con una contraseña** , escriba y confirme una contraseña.</span><span class="sxs-lookup"><span data-stu-id="63013-149">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
9. <span data-ttu-id="63013-150">Haga clic en **Aceptar** para completar la importación.</span><span class="sxs-lookup"><span data-stu-id="63013-150">Click **OK** to complete the import.</span></span>  
  
#### <a name="to-export-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="63013-151">Para exportar un paquete con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63013-151">To export a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="63013-152">Haga clic en **Inicio**, seleccione **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="63013-152">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="63013-153">En el cuadro de diálogo **Conectar al servidor** , establezca las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="63013-153">In the **Connect to Server** dialog box, set the following options:</span></span>  
  
    -   <span data-ttu-id="63013-154">En el cuadro **Tipo de servidor** , seleccione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="63013-154">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="63013-155">En el cuadro **Nombre del servidor**, escriba un nombre de servidor o haga clic en **\<Browse for more...>** y busque el servidor que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="63013-155">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="63013-156">Si el Explorador de objetos no está abierto, en el menú **Ver** , haga clic en **Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="63013-156">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="63013-157">En el Explorador de objetos, expanda la carpeta **Paquetes almacenados** .</span><span class="sxs-lookup"><span data-stu-id="63013-157">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="63013-158">Expanda las subcarpetas para buscar el paquete que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="63013-158">Expand the subfolders to locate the package you want to export.</span></span>  
  
6.  <span data-ttu-id="63013-159">Opcionalmente, haga clic en **Exportar**y, después, realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="63013-159">Right-click the package, click **Export**, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="63013-160">Para exportar a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], seleccione la opción **SQL Server** y luego especifique el servidor y seleccione el modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="63013-160">To export to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="63013-161">Si selecciona Autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , proporcione un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="63013-161">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="63013-162">Haga clic en el botón Examinar **(…)** y expanda la carpeta **Paquetes SSIS** para buscar la carpeta donde quiera guardar el paquete.</span><span class="sxs-lookup"><span data-stu-id="63013-162">Click the browse button **(...)**, and expand the **SSIS Packages** folder to locate the folder to which you want to save the package.</span></span> <span data-ttu-id="63013-163">Opcionalmente, actualice el nombre predeterminado del paquete y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="63013-163">Optionally, update the default name of the package, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="63013-164">Para exportar al sistema de archivos, seleccione la opción **Sistema de archivos** .</span><span class="sxs-lookup"><span data-stu-id="63013-164">To export to the file system, select the **File System** option.</span></span>  
  
         <span data-ttu-id="63013-165">Haga clic en el botón Examinar **(…)** para buscar la carpeta donde quiera exportar el paquete, escriba el nombre del archivo de paquete y, después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="63013-165">Click the browse button **(...)** to locate the folder to which you want to export the package, type the name of the package file, and then click **Save.**</span></span>  
  
    -   <span data-ttu-id="63013-166">Para exportar al almacén de paquetes [!INCLUDE[ssIS](../includes/ssis-md.md)] , seleccione la opción **Almacén de paquetes SSIS** y especifique el servidor.</span><span class="sxs-lookup"><span data-stu-id="63013-166">To export to the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store, select the **SSIS Package Store** option, and specify the server.</span></span>  
  
         <span data-ttu-id="63013-167">Haga clic en el botón Examinar **(…)** , expanda la carpeta **Paquetes SSIS** y seleccione la carpeta donde quiera guardar el paquete.</span><span class="sxs-lookup"><span data-stu-id="63013-167">Click the browse button **(...)**, expand the **SSIS Packages** folder, and select the folder to which you want to save the package.</span></span> <span data-ttu-id="63013-168">Opcionalmente, escriba un nuevo nombre para el paquete en el cuadro de texto **Nombre del paquete** .</span><span class="sxs-lookup"><span data-stu-id="63013-168">Optionally, enter a new name for the package in the **Package Name** text box.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="63013-169">Para actualizar el nivel de protección del paquete, haga clic en el botón Examinar **(…)** y seleccione otro nivel de protección con el cuadro de diálogo **Nivel de protección de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="63013-169">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="63013-170">Si se selecciona la opción **Cifrar la información confidencial con una contraseña** o la opción **Cifrar todos los datos con una contraseña** , escriba y confirme una contraseña.</span><span class="sxs-lookup"><span data-stu-id="63013-170">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
8.  <span data-ttu-id="63013-171">Haga clic en **Aceptar** para completar la exportación.</span><span class="sxs-lookup"><span data-stu-id="63013-171">Click **OK** to complete the export.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63013-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63013-172">See Also</span></span>  
 [<span data-ttu-id="63013-173">Administración de paquetes &#40;servicio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="63013-173">Package Management &#40;SSIS Service&#41;</span></span>](service/package-management-ssis-service.md)  
  
  
