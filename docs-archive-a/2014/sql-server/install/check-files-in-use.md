---
title: Comprobar archivos en uso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccd65867-d4c0-43b2-8361-7fd41c6f79ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 51505b0dece146b7f6fcdf982e6f88a5715357e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672507"
---
# <a name="check-files-in-use"></a><span data-ttu-id="59f4e-102">Comprobar archivos en uso</span><span class="sxs-lookup"><span data-stu-id="59f4e-102">Check Files In Use</span></span>
  <span data-ttu-id="59f4e-103">Para no tener que reiniciar Windows después de instalar las actualizaciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , use la página Comprobar archivos en uso con el fin de identificar los procesos que están bloqueando los archivos requeridos por el programa de instalación de la actualización de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59f4e-103">To avoid restarting Windows after you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates, use the Check Files in Use page to identify processes that are locking files required by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] update Setup program.</span></span>  
  
 <span data-ttu-id="59f4e-104">Detenga todas las aplicaciones y servicios que establecen conexiones con las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se están actualizando.</span><span class="sxs-lookup"><span data-stu-id="59f4e-104">Stop all applications and services that make connections to the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are being updated.</span></span> <span data-ttu-id="59f4e-105">Se incluye la detención de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59f4e-105">This includes stopping [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="59f4e-106">Si el programa de instalación determina que hay archivos bloqueados durante el proceso de instalación, puede que sea necesario reiniciar el equipo una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="59f4e-106">If Setup determines that files are locked during installation, you might have to restart your computer after installation is completed.</span></span> <span data-ttu-id="59f4e-107">Si es necesario, el programa de instalación le indica que reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="59f4e-107">If necessary, Setup prompts you to restart your computer.</span></span> <span data-ttu-id="59f4e-108">Si el programa de instalación debe detener un servicio durante el proceso de instalación, lo reiniciará una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="59f4e-108">If the Setup program must stop a service during installation, it will restart the service after installation is completed.</span></span>  
  
 <span data-ttu-id="59f4e-109">Para eliminar el requisito de reinicio del equipo tras la instalación, el programa de instalación muestra una lista de los procesos que están bloqueando los archivos.</span><span class="sxs-lookup"><span data-stu-id="59f4e-109">To eliminate the requirement to restart your computer after installation, Setup displays a list of processes that are locking files.</span></span> <span data-ttu-id="59f4e-110">Detenga o finalice los procesos y las aplicaciones de la lista.</span><span class="sxs-lookup"><span data-stu-id="59f4e-110">Stop or end the processes and applications in the list.</span></span> <span data-ttu-id="59f4e-111">A continuación, haga clic en **Actualizar comprobación** para volver a ejecutar la comprobación.</span><span class="sxs-lookup"><span data-stu-id="59f4e-111">Then click **Refresh check** to rerun the check.</span></span> <span data-ttu-id="59f4e-112">Haga clic en **Detener comprobación** para finalizar una comprobación que se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="59f4e-112">Click **Stop check** to end a check that is running.</span></span> <span data-ttu-id="59f4e-113">Si no se encuentra ningún archivo bloqueado, la tabla está vacía.</span><span class="sxs-lookup"><span data-stu-id="59f4e-113">If locked files are not found, the table is empty.</span></span> <span data-ttu-id="59f4e-114">Cuando todos los procesos bloqueados se hayan cerrado o detenido, haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="59f4e-114">When all locked processes have been closed or stopped, click **Next** to continue.</span></span>  
  
 <span data-ttu-id="59f4e-115">El programa de instalación registra la información en los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="59f4e-115">Setup logs the information in the log files.</span></span> <span data-ttu-id="59f4e-116">Para obtener más información sobre cómo ver los archivos de registro, vea [Ver y leer los archivos de registro de instalación de SQL Server](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) y [Cómo leer un archivo de registro de instalación de SQL Server](https://go.microsoft.com/fwlink/?LinkID=134490).</span><span class="sxs-lookup"><span data-stu-id="59f4e-116">For more information about how to view the log files, see [View and Read SQL Server Setup Log Files](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) and [How to: Read a SQL Server Setup Log File](https://go.microsoft.com/fwlink/?LinkID=134490).</span></span>  
  
 <span data-ttu-id="59f4e-117">En el archivo de registro se incluye la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="59f4e-117">The following information is included in the log file:</span></span>  
  
-   <span data-ttu-id="59f4e-118">Nombre del proceso</span><span class="sxs-lookup"><span data-stu-id="59f4e-118">Name of the process</span></span>  
  
-   <span data-ttu-id="59f4e-119">Nombre de la característica de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59f4e-119">Name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature</span></span>  
  
-   <span data-ttu-id="59f4e-120">Tipo de proceso</span><span class="sxs-lookup"><span data-stu-id="59f4e-120">Process type</span></span>  
  
-   <span data-ttu-id="59f4e-121">Cuenta en la que se está ejecutando el proceso</span><span class="sxs-lookup"><span data-stu-id="59f4e-121">Account under which the process is running</span></span>  
  
-   <span data-ttu-id="59f4e-122">Identificador del proceso</span><span class="sxs-lookup"><span data-stu-id="59f4e-122">Process ID</span></span>  
  
-   <span data-ttu-id="59f4e-123">Nombre del archivo que está bloqueado</span><span class="sxs-lookup"><span data-stu-id="59f4e-123">Name of the file that is locked</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="59f4e-124">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="59f4e-124">UI element list</span></span>  
  
|<span data-ttu-id="59f4e-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="59f4e-125">Name</span></span>|<span data-ttu-id="59f4e-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="59f4e-126">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="59f4e-127">Proceso</span><span class="sxs-lookup"><span data-stu-id="59f4e-127">Process</span></span>|<span data-ttu-id="59f4e-128">Muestra el nombre completo del proceso que está utilizando los archivos que se van a actualizar.</span><span class="sxs-lookup"><span data-stu-id="59f4e-128">Displays the full name of the process that is using the files to be updated.</span></span>|  
|<span data-ttu-id="59f4e-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="59f4e-129">Type</span></span>|<span data-ttu-id="59f4e-130">Muestra el tipo de proceso.</span><span class="sxs-lookup"><span data-stu-id="59f4e-130">Displays the type of process.</span></span>|  
|<span data-ttu-id="59f4e-131">Cuenta</span><span class="sxs-lookup"><span data-stu-id="59f4e-131">Account</span></span>|<span data-ttu-id="59f4e-132">Muestra la cuenta en la que se está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="59f4e-132">Displays the account under which the process is running.</span></span>|  
|<span data-ttu-id="59f4e-133">Identificador del proceso</span><span class="sxs-lookup"><span data-stu-id="59f4e-133">Process ID</span></span>|<span data-ttu-id="59f4e-134">Muestra el identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="59f4e-134">Displays the process ID.</span></span>|  
  
  
