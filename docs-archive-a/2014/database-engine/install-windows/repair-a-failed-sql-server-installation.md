---
title: Reparación de una instalación de SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 90c11b28-892b-44d6-978e-0eee48c75b7d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e382137a971b3f8b23cf1d814bff9908f04150
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746409"
---
# <a name="drop-a-sql-server-2014-installation"></a><span data-ttu-id="b6e74-102">Anular una instalación de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b6e74-102">Drop a SQL Server 2014 Installation</span></span>
  <span data-ttu-id="b6e74-103">La operación de reparación se puede utilizar en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6e74-103">Repair operation can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="b6e74-104">Para reparar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ha dañado una vez instalada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b6e74-104">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is corrupted after it was successfully installed.</span></span>  
  
-   <span data-ttu-id="b6e74-105">Para reparar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si la operación de actualización se canceló o produjo un error una vez asignado el nombre a la instancia recién actualizada.</span><span class="sxs-lookup"><span data-stu-id="b6e74-105">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if the upgrade operation is cancelled or fails after the instance name is mapped to the newly-upgraded instance.</span></span>  
  
    -   <span data-ttu-id="b6e74-106">Si ve el mensaje siguiente en el registro de resumen, puede reparar la instancia de la actualización con errores:</span><span class="sxs-lookup"><span data-stu-id="b6e74-106">If you see the following message in the summary log, you can repair the failed upgrade instance:</span></span>  
  
         <span data-ttu-id="b6e74-107">"Error en la actualización de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6e74-107">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="b6e74-108">Para continuar, investigue el motivo del error, corrija el problema, desinstale SQL Server y, después, repare la instalación."</span><span class="sxs-lookup"><span data-stu-id="b6e74-108">To continue, investigate the reason for the failure, correct the problem, and then repair your installation."</span></span>  
  
    -   <span data-ttu-id="b6e74-109">Si ve el mensaje siguiente en el registro de resumen, tiene que desinstalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]y volver a instalarlo.</span><span class="sxs-lookup"><span data-stu-id="b6e74-109">If you see the following message in the summary log, you need to uninstall and reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b6e74-110">No puede reparar la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6e74-110">You cannot repair the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="b6e74-111">"Error en la actualización de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6e74-111">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="b6e74-112">Para continuar, investigue el motivo del error y corrija el problema."</span><span class="sxs-lookup"><span data-stu-id="b6e74-112">To continue, investigate the reason for the failure, correct the problem."</span></span>  
  
 <span data-ttu-id="b6e74-113">Al reparar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b6e74-113">When you repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="b6e74-114">Se reemplazan todos los archivos que se hayan perdido o dañado.</span><span class="sxs-lookup"><span data-stu-id="b6e74-114">All missing or corrupt files are replaced.</span></span>  
  
-   <span data-ttu-id="b6e74-115">Se reemplazan todas las claves del Registro que se hayan perdido o dañado.</span><span class="sxs-lookup"><span data-stu-id="b6e74-115">All missing or corrupt registry keys are replaced.</span></span>  
  
-   <span data-ttu-id="b6e74-116">Todos los valores de configuración que se hayan perdido o que no sean válidos se establecen en los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b6e74-116">All missing or invalid configuration values are set to default values.</span></span>  
  
 <span data-ttu-id="b6e74-117">Antes de continuar, revise la siguiente información importante relacionada con los clústeres de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="b6e74-117">Before you continue, for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover clusters, review the following important information:</span></span>  
  
-   <span data-ttu-id="b6e74-118">La reparación se debe llevar a cabo en nodos de clúster individuales.</span><span class="sxs-lookup"><span data-stu-id="b6e74-118">Repair must be run on individual cluster nodes.</span></span>  
  
-   <span data-ttu-id="b6e74-119">Para reparar un nodo de clúster de conmutación por error después una operación de preparación con errores, use **Eliminar nodo de un clúster de conmutación por error de SQL Server** y, a continuación, vuelva a realizar el paso de preparación.</span><span class="sxs-lookup"><span data-stu-id="b6e74-119">To repair a failover cluster node after a failed Prepare operation, use **Remove node** and then perform the Prepare step again.</span></span> <span data-ttu-id="b6e74-120">Para obtener más información, vea [Agregar o quitar nodos en un clúster de conmutación por error de SQL Server &#40;programa de instalación&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="b6e74-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-from-the-installation-center"></a><span data-ttu-id="b6e74-121">Para reparar una instalación con errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde el Centro de instalación</span><span class="sxs-lookup"><span data-stu-id="b6e74-121">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the Installation Center</span></span>  
  
1.  <span data-ttu-id="b6e74-122">Inicie el programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (setup.exe) desde el disco de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6e74-122">Launch the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program (setup.exe) from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span>  
  
2.  <span data-ttu-id="b6e74-123">Después de comprobar los requisitos previos y el sistema, el programa de instalación mostrará la página Centro de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6e74-123">After prerequisites and system verification, the Setup program will display the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Center page.</span></span>  
  
3.  <span data-ttu-id="b6e74-124">Haga clic en **Mantenimiento** en el área de navegación de la izquierda y, después, haga clic en **Reparar** para iniciar la operación de reparación.</span><span class="sxs-lookup"><span data-stu-id="b6e74-124">Click **Maintenance** in the left-hand navigation area, and then click **Repair** to start the repair operation.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="b6e74-125">Si el Centro de instalación se ha iniciado con el menú de inicio, tendrá que proporcionar la ubicación del medio de instalación en este momento.</span><span class="sxs-lookup"><span data-stu-id="b6e74-125">If the Installation Center was launched using the start menu, you will need to provide the location of the installation media at this time.</span></span>  
  
4.  <span data-ttu-id="b6e74-126">Configure las reglas auxiliares del programa de instalación y las rutinas de archivo para asegurarse de que el sistema tiene instalados los requisitos previos y de que el equipo pasa las reglas de validación del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="b6e74-126">Setup support rule and file routines will run to ensure that your system has prerequisites installed and that the computer passes Setup validation rules.</span></span> <span data-ttu-id="b6e74-127">Haga clic en **Aceptar** o en **Instalar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="b6e74-127">Click **OK** or **Install** to continue.</span></span>  
  
5.  <span data-ttu-id="b6e74-128">En la página Seleccionar instancia, seleccione la instancia que desea reparar y, a continuación, haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="b6e74-128">On the Select Instance page, select the instance to repair, and then click **Next** to continue.</span></span>  
  
6.  <span data-ttu-id="b6e74-129">Las reglas de reparación se ejecutarán para validar la operación.</span><span class="sxs-lookup"><span data-stu-id="b6e74-129">The repair rules will run to validate the operation.</span></span> <span data-ttu-id="b6e74-130">Para continuar, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b6e74-130">To continue, click **Next**.</span></span>  
  
7.  <span data-ttu-id="b6e74-131">La página Listo para reparar indica que la operación está lista para continuar.</span><span class="sxs-lookup"><span data-stu-id="b6e74-131">The Ready to Repair page indicates that the operation is ready to proceed.</span></span> <span data-ttu-id="b6e74-132">Para continuar, haga clic en **Reparar**.</span><span class="sxs-lookup"><span data-stu-id="b6e74-132">To continue, click **Repair**.</span></span>  
  
8.  <span data-ttu-id="b6e74-133">La página Progreso de la reparación muestra el estado de la operación de reparación.</span><span class="sxs-lookup"><span data-stu-id="b6e74-133">The Repair Progress page shows the status of the repair operation.</span></span> <span data-ttu-id="b6e74-134">La página Operación completada indica que la operación ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="b6e74-134">The Complete page indicates that the operation is finished.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-using-command-prompt"></a><span data-ttu-id="b6e74-135">Para reparar una instalación con errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="b6e74-135">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Command Prompt</span></span>  
  
1.  <span data-ttu-id="b6e74-136">Ejecute el comando siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b6e74-136">Run the following command at a command prompt:</span></span>  
  
    ```  
    Setup.exe /q /ACTION=Repair /INSTANCENAME=instancename  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b6e74-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6e74-137">See Also</span></span>  
 <span data-ttu-id="b6e74-138">[Ver y leer los archivos de registro de instalación de SQL Server](view-and-read-sql-server-setup-log-files.md) </span><span class="sxs-lookup"><span data-stu-id="b6e74-138">[View and Read SQL Server Setup Log Files](view-and-read-sql-server-setup-log-files.md) </span></span>  
 [<span data-ttu-id="b6e74-139">Temas de procedimientos de instalación</span><span class="sxs-lookup"><span data-stu-id="b6e74-139">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
  
  
