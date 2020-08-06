---
title: Cambiar el nombre de una instancia de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- instances of Analysis Services, renaming
- renaming instances of Analysis Services
- names [Analysis Services], renaming instances
- names [Analysis Services]
ms.assetid: 87494741-4a2e-4fed-8061-418fd1e111c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 763986d82dda7424f2187daf401424fd256ddd64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746583"
---
# <a name="rename-an-analysis-services-instance"></a><span data-ttu-id="26f27-102">Cambiar el nombre de una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="26f27-102">Rename an Analysis Services Instance</span></span>
  <span data-ttu-id="26f27-103">Puede cambiar el nombre de una instancia existente de mediante [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] el cuadro de diálogo **cambiar nombre de instancia** .</span><span class="sxs-lookup"><span data-stu-id="26f27-103">You can rename an existing instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using the **Rename Instance** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="26f27-104">Cuando se cambia el nombre de la instancia, la herramienta Cambiar nombre de instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se ejecuta con privilegios elevados, actualizando el nombre de servicio de Windows, las cuentas de seguridad y las entradas de Registro asociados a esa instancia.</span><span class="sxs-lookup"><span data-stu-id="26f27-104">While renaming the instance, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool runs under elevated privileges, updating the Windows service name, security accounts, and registry entries associated with that instance.</span></span> <span data-ttu-id="26f27-105">Para garantizar que estas acciones se realizan, asegúrese de ejecutar esta herramienta como administrador del sistema local.</span><span class="sxs-lookup"><span data-stu-id="26f27-105">To ensure that these actions are performed, be sure to run this tool as a local system administrator.</span></span>  
  
 <span data-ttu-id="26f27-106">La herramienta Cambiar nombre de instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no modifica la carpeta de programas creada para la instancia original.</span><span class="sxs-lookup"><span data-stu-id="26f27-106">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool does not modify the program folder that was created for the original instance.</span></span> <span data-ttu-id="26f27-107">No modifique el nombre de la carpeta de programas para que coincida con la instancia a la que está cambiando el nombre.</span><span class="sxs-lookup"><span data-stu-id="26f27-107">Do not modify the program folder name to match the instance you are renaming.</span></span> <span data-ttu-id="26f27-108">El cambio de una carpeta de programas puede evitar que el programa de instalación repare o desinstale la instalación.</span><span class="sxs-lookup"><span data-stu-id="26f27-108">Changing a program folder name can prevent Setup from repairing or uninstalling the installation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26f27-109">No se admite el uso de la herramienta para cambiar el nombre de instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en un entorno de clúster.</span><span class="sxs-lookup"><span data-stu-id="26f27-109">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool is not supported for use in a cluster environment.</span></span>  
  
### <a name="to-rename-an-instance-of-analysis-services"></a><span data-ttu-id="26f27-110">Para cambiar el nombre de una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="26f27-110">To rename an instance of Analysis Services</span></span>  
  
1.  <span data-ttu-id="26f27-111">Inicie la herramienta **cambiar nombre de instancia** , **asinstancerename.exe**, en C:\Archivos de programa\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span><span class="sxs-lookup"><span data-stu-id="26f27-111">Launch the **Instance Rename** tool, **asinstancerename.exe**, from C:\Program Files\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span></span>  
  
2.  <span data-ttu-id="26f27-112">En el cuadro de diálogo **Cambiar nombre de instancia** , seleccione en la lista **Instancia cuyo nombre se cambiará** la instancia cuyo nombre desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="26f27-112">In the **Rename Instance** dialog box, in the **Instance to rename** list, select the instance that you want to rename.</span></span>  
  
3.  <span data-ttu-id="26f27-113">En el cuadro **Nuevo nombre de instancia** , escriba el nuevo nombre de la instancia.</span><span class="sxs-lookup"><span data-stu-id="26f27-113">In the **New instance name** box, enter the new name for the instance.</span></span>  
  
4.  <span data-ttu-id="26f27-114">Compruebe que el nombre de usuario y la contraseña son correctos y, a continuación, haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="26f27-114">Verify that the user name and password are correct, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="26f27-115">La instancia de Analysis Services se detendrá y reiniciará como parte del cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="26f27-115">The Analysis Services instance will be stopped and restarted as part of the name change.</span></span>  
  
### <a name="post-rename-checklist"></a><span data-ttu-id="26f27-116">Lista de comprobación posterior al cambio de nombre</span><span class="sxs-lookup"><span data-stu-id="26f27-116">Post-rename checklist</span></span>  
  
1.  <span data-ttu-id="26f27-117">Para reanudar el acceso a las bases de datos que se ejecutan en la instancia a la que se cambia el nombre, deberá actualizar manualmente las conexiones de datos en Excel u otras aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="26f27-117">To resume access to databases that are running on the renamed instance, you will need to manually update the data connections in Excel or other client applications.</span></span> <span data-ttu-id="26f27-118">También debe comprobar las conexiones predefinidas, como orígenes de datos compartidos de Reporting Services, archivos ODC de Exce o archivos de conexión de modelos semánticos BI, que puedan hacer referencia a la instancia cuyo nombre acaba de cambiar.</span><span class="sxs-lookup"><span data-stu-id="26f27-118">Also check any predefined connections, such as Reporting Services shared data sources, Excel ODC files, or BI Semantic Model connection files that might reference the instance you just renamed.</span></span> <span data-ttu-id="26f27-119">Para más información, vea [Conectar a Analysis Services](connect-to-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="26f27-119">For more information, see [Connect to Analysis Services](connect-to-analysis-services.md).</span></span>  
  
2.  <span data-ttu-id="26f27-120">Actualice los scripts de PowerShell o los scripts de AMO que utiliza habitualmente para la copia de seguridad, sincronización o procesamiento de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="26f27-120">Update PowerShell scripts or AMO scripts that you routinely use to backup, synchronize, or process databases.</span></span>  
  
3.  <span data-ttu-id="26f27-121">Actualice las propiedades del proyecto para los proyectos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyectos con los que trabaja en [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26f27-121">Update project properties for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects that you work with in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="26f27-122">Para las instancias de servidor en modo tabular, asegúrese de actualizar la propiedad de servidor de área de trabajo en el archivo model.bim, así como la propiedad de servidor en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="26f27-122">For tabular mode server instances, be sure to update the Workspace Server property on the model.bim file, as well as the Server property on the project.</span></span>  
  
4.  <span data-ttu-id="26f27-123">Dependiendo de cómo haya especificado la cuenta de servicio, es posible que tenga que actualizar los inicios de sesión o los permisos de archivo que conceden derechos de acceso a datos en el servicio (por ejemplo, si usa la cuenta de servicio para procesar datos o para obtener acceso a objetos vinculados en otro servidor).</span><span class="sxs-lookup"><span data-stu-id="26f27-123">Depending on how you specified the service account, you might need to update database logins or file permissions that grant data access rights to the service (for example, if you use the service account to process data or access linked objects on another server).</span></span>  
  
     <span data-ttu-id="26f27-124">Será necesario actualizar un inicio de sesión o los permisos de archivo de base de datos si ha utilizado una cuenta virtual para aprovisionar el servicio.</span><span class="sxs-lookup"><span data-stu-id="26f27-124">Updating a database login or file permissions will be necessary if you used a virtual account to provision the service.</span></span> <span data-ttu-id="26f27-125">Las cuentas virtuales se basan en el nombre de instancia, por lo que si cambia el nombre de la instancia, la cuenta virtual también se actualiza al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="26f27-125">Virtual accounts are based on the instance name, so if you rename the instance, the virtual account is also updated at the same time.</span></span> <span data-ttu-id="26f27-126">Esto significa que los inicios de sesión o permisos anteriores creados para la instancia anterior ya no son válidos.</span><span class="sxs-lookup"><span data-stu-id="26f27-126">This means that any previous logins or permissions that you created for the previous instance are no longer valid.</span></span>  
  
     <span data-ttu-id="26f27-127">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="26f27-127">The following example provides an illustration.</span></span> <span data-ttu-id="26f27-128">Supongamos que ha instalado un servidor en modo tabular como una instancia denominada "tabular" mediante la cuenta virtual predeterminada, lo que da lugar a la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="26f27-128">Suppose you installed a tabular mode server as an instance named "Tabular" using the default virtual account, resulting in the following configuration:</span></span>  
  
    1.  <span data-ttu-id="26f27-129">Nombre de instancia = \<server> \TABULAR</span><span class="sxs-lookup"><span data-stu-id="26f27-129">Instance name = \<server>\TABULAR</span></span>  
  
    2.  <span data-ttu-id="26f27-130">Nombre de servicio = MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="26f27-130">Service name = MSOLAP$TABULAR</span></span>  
  
    3.  <span data-ttu-id="26f27-131">Cuenta virtual = NT Service\ MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="26f27-131">Virtual account = NT Service\ MSOLAP$TABULAR</span></span>  
  
     <span data-ttu-id="26f27-132">Ahora Supongamos que cambia el nombre de la instancia a "TAB2".</span><span class="sxs-lookup"><span data-stu-id="26f27-132">Now suppose you rename the instance to "TAB2".</span></span> <span data-ttu-id="26f27-133">Como consecuencia del cambio de nombre, la configuración podría tener ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="26f27-133">As a result of the name change, your configuration would now look like the following:</span></span>  
  
    1.  <span data-ttu-id="26f27-134">Nombre de instancia = \<server> \TAB2</span><span class="sxs-lookup"><span data-stu-id="26f27-134">Instance name = \<server>\TAB2</span></span>  
  
    2.  <span data-ttu-id="26f27-135">Nombre de servicio = MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="26f27-135">Service name = MSOLAP$TAB2</span></span>  
  
    3.  <span data-ttu-id="26f27-136">Cuenta virtual = NT Service\ MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="26f27-136">Virtual account = NT Service\ MSOLAP$TAB2</span></span>  
  
     <span data-ttu-id="26f27-137">Como puede ver, los permisos de archivos y bases de datos que se concedieron anteriormente a "NT Service \ MSOLAP $ TABULAr" ya no son válidos.</span><span class="sxs-lookup"><span data-stu-id="26f27-137">As you can see, database and file permissions that were previously granted to "NT Service\ MSOLAP$TABULAR" are no longer valid.</span></span> <span data-ttu-id="26f27-138">Para asegurarse de que las tareas y las operaciones realizadas por el servicio se ejecuten como antes, ahora tendría que conceder nuevos permisos de base de datos y de archivo a "NT Service \ MSOLAP $ TAB2".</span><span class="sxs-lookup"><span data-stu-id="26f27-138">To ensure that tasks and operations performed by the service run as before, you would now need to grant new database and file permissions to "NT Service\ MSOLAP$TAB2".</span></span>  
  
  
