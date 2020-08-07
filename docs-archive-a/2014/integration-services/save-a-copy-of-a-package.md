---
title: Guardar una copia de un paquete | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, saving
- packages [Integration Services], saving
- saving packages
- SSIS packages, saving
- SQL Server Integration Services packages, saving
ms.assetid: 21482a20-e420-4452-b7eb-8f9fa1929f31
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 02ee2374fddb7dbb6b17adc2a4a10707179c882d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745374"
---
# <a name="save-a-copy-of-a-package"></a><span data-ttu-id="dc2ae-102">Guardar una copia de un paquete</span><span class="sxs-lookup"><span data-stu-id="dc2ae-102">Save a Copy of a Package</span></span>
  <span data-ttu-id="dc2ae-103">Este procedimiento describe cómo guardar una copia de un paquete en el sistema de archivos, en el almacén de paquetes o en la base de datos **msdb** en [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc2ae-103">This procedure describes how to save a copy of a package to the file system, to the package store, or to the **msdb** database in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dc2ae-104">Al especificar una ubicación para guardar la copia del paquete, puede actualizar también el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-104">When you specify a location to save the package copy, you can also update the name of the package.</span></span>  
  
 <span data-ttu-id="dc2ae-105">El almacén de paquetes puede incluir la base de datos **msdb** y las carpetas del sistema de archivos, solamente la base de datos **msdb**o solamente las carpetas del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-105">The package store can include both the **msdb** database and the folders in the file system, only **msdb**, or only folders in the file system.</span></span> <span data-ttu-id="dc2ae-106">En **msdb**, los paquetes se guardan en la tabla **sysssispackages** .</span><span class="sxs-lookup"><span data-stu-id="dc2ae-106">In **msdb**, packages are saved to the **sysssispackages** table.</span></span> <span data-ttu-id="dc2ae-107">Esta tabla incluye una columna **folderid** que identifica la carpeta lógica a la que pertenece el paquete.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-107">This table includes a **folderid** column that identifies the logical folder to which the package belongs.</span></span> <span data-ttu-id="dc2ae-108">Las carpetas lógicas proporcionan una forma útil de agrupar paquetes guardados en **msdb** del mismo modo que las carpetas del sistema de archivos proporcionan una forma de agrupar paquetes guardados en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-108">The logical folders provide a useful way to group packages saved to **msdb** in the same way that folders in the file system provide a way to group packages saved to the file system.</span></span> <span data-ttu-id="dc2ae-109">Las filas en la tabla **sysssispackagefolders** en **msdb** definen las carpetas.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-109">Rows in the **sysssispackagefolders** table in **msdb** define the folders.</span></span>  
  
 <span data-ttu-id="dc2ae-110">Si **msdb** no está definida como parte del almacén de paquetes, puede continuar asociando paquetes con carpetas lógicas existentes cuando seleccione SQL Server en la opción **Ruta de acceso del paquete** .</span><span class="sxs-lookup"><span data-stu-id="dc2ae-110">If **msdb** is not defined as part of the package store, you can continue to associate packages with existing logical folders when you select SQL Server in the **Package Path** option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc2ae-111">El paquete se debe abrir en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] para poder guardar una copia del paquete.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-111">The package must be opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer before you can save a copy of the package.</span></span>  
  
### <a name="to-save-a-copy-of-a-package"></a><span data-ttu-id="dc2ae-112">Para guardar una copia de un paquete</span><span class="sxs-lookup"><span data-stu-id="dc2ae-112">To save a copy of a package</span></span>  
  
1.  <span data-ttu-id="dc2ae-113">En el Explorador de soluciones, haga doble clic en el paquete cuya copia desea guardar.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-113">In Solution Explorer, double-click the package of which you want to save a copy.</span></span>  
  
2.  <span data-ttu-id="dc2ae-114">En el menú **Archivo**, haga clic en **Guardar copia de \<package file> como**.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-114">On the **File** menu, click **Save Copy of \<package file> As**.</span></span>  
  
3.  <span data-ttu-id="dc2ae-115">En el cuadro de diálogo **Guardar copia del paquete** , seleccione una ubicación de paquete en la lista **Ubicación del paquete** .</span><span class="sxs-lookup"><span data-stu-id="dc2ae-115">In the **Save Copy of Package** dialog box, select a package location in the **Package location** list.</span></span>  
  
4.  <span data-ttu-id="dc2ae-116">Si la ubicación es **SQL Server** o **Almacén de paquetes SSIS**, proporcione un nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-116">If the location is **SQL Server** or **SSIS Package Store**, provide a server name.</span></span>  
  
5.  <span data-ttu-id="dc2ae-117">Si se guarda en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], especifique el tipo de autenticación y, si se usa la Autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , proporcione un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-117">If saving to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], specify the authentication type and, if using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and password.</span></span>  
  
6.  <span data-ttu-id="dc2ae-118">Para especificar la ruta de acceso del paquete, escríbala o haga clic en el botón Examinar **(…)** para especificar la ubicación del paquete.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-118">To specify the package path, either type the path or click the browse button **(...)** to specify the location of the package.</span></span> <span data-ttu-id="dc2ae-119">El nombre predeterminado del paquete es Paquete.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-119">The default name of the package is Package.</span></span> <span data-ttu-id="dc2ae-120">Opcionalmente, cambie el nombre del paquete a uno que satisfaga sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-120">Optionally, update the package name to one that suits your needs.</span></span>  
  
     <span data-ttu-id="dc2ae-121">Si selecciona **SQL Server** como opción de **Ruta de acceso del paquete** , la ruta de acceso del paquete consta de carpetas lógicas de **msdb** y el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-121">If you select **SQL Server** as the **Package Path** option, the package path consists of logical folders in **msdb** and the package name.</span></span> <span data-ttu-id="dc2ae-122">Por ejemplo, si el paquete DownloadMonthlyData está asociado con la carpeta Finance dentro de la carpeta MSDB (nombre predeterminado de la carpeta lógica raíz de **msdb**), la ruta del paquete DownloadMonthlyData es MSDB/Finance/DownloadMonthlyData.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-122">For example, if the package DownloadMonthlyData is associated with the Finance folder within the MSDB folder (the default name of the root logical folder in **msdb**), the package path for the package named DownloadMonthlyData is MSDB/Finance/DownloadMonthlyData</span></span>  
  
     <span data-ttu-id="dc2ae-123">Si selecciona **Almacén de paquetes SSIS** como opción de **Ruta de acceso del paquete** , la ruta del paquete consta de la carpeta que administra el servicio Integration Services.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-123">If you select **SSIS Package Store** as the **Package Path** option, the package path consists of the folder that the Integration Services service manages.</span></span> <span data-ttu-id="dc2ae-124">Por ejemplo, si el paquete UpdateDeductions se encuentra en la carpeta HumanResources dentro de la carpeta del sistema de archivos que administra el servicio, la ruta del paquete es /File System/HumanResources/UpdateDeductions; de igual modo, si el paquete PostResumes está asociado con la carpeta HumanResources dentro de la carpeta MSDB, la ruta de acceso del paquete es MSDB/HumanResources/PostResumes.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-124">For example, if the package UpdateDeductions is located in the HumanResources folder within the file system folder that the service manages, the package path is /File System/HumanResources/UpdateDeductions; likewise, if the package PostResumes is associated with the HumanResources folder within the MSDB folder, the package path is MSDB/HumanResources/PostResumes.</span></span>  
  
     <span data-ttu-id="dc2ae-125">Si selecciona **Sistema de archivos** como opción de **Ruta de acceso del paquete** , la ruta del paquete es la ubicación en el sistema de archivos y el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-125">If you select **File System** as the **Package Path** option, the package path is the location in the file system and the file name.</span></span> <span data-ttu-id="dc2ae-126">Por ejemplo, si el nombre del paquete es UpdateDemographics, la ruta del paquete es C:\HumanResources\Quarterly\UpdateDemographics.dtsx.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-126">For example, if the package name is UpdateDemographics the package path is C:\HumanResources\Quarterly\UpdateDemographics.dtsx.</span></span>  
  
7.  <span data-ttu-id="dc2ae-127">Revise el nivel de protección del paquete.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-127">Review the package protection level.</span></span>  
  
8.  <span data-ttu-id="dc2ae-128">También puede hacer clic en el botón Examinar **(…)** junto al cuadro **Nivel de protección** para cambiar el nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-128">Optionally, click the browse button **(...)** by the **Protection level** box to change the protection level.</span></span>  
  
    -   <span data-ttu-id="dc2ae-129">En el cuadro de diálogo **Nivel de protección de paquetes** , seleccione un nivel de protección diferente.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-129">In the **Package Protection Level** dialog box, select a different protection level.</span></span>  
  
    -   <span data-ttu-id="dc2ae-130">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-130">Click **OK**.</span></span>  
  
9. <span data-ttu-id="dc2ae-131">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc2ae-131">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc2ae-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc2ae-132">See Also</span></span>  
 <span data-ttu-id="dc2ae-133">[Integration Services &#40;paquetes&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="dc2ae-133">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="dc2ae-134">Configurar el servicio Integration Services &#40;servicio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc2ae-134">Configuring the Integration Services Service &#40;SSIS Service&#41;</span></span>](service/integration-services-service-ssis-service.md)  
  
  
