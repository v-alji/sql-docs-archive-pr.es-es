---
title: Implementación de paquetes secundarios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- child packages
ms.assetid: ab0c09d7-ce2e-487d-a1ed-a4b5adb6cc01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4fa4fa7c523c55c595341c7aee6a530c5918a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745379"
---
# <a name="implementation-of-child-packages"></a><span data-ttu-id="fe88e-102">Implementación de paquetes secundarios</span><span class="sxs-lookup"><span data-stu-id="fe88e-102">Implementation of Child Packages</span></span>
  <span data-ttu-id="fe88e-103">Cuando implementa el equilibrio de carga mediante [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], los paquetes secundarios se instalan en otros servidores para aprovechar el tiempo de servidor o CPU disponible.</span><span class="sxs-lookup"><span data-stu-id="fe88e-103">When you implement load balancing using [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], child packages are installed on other servers to take advantage of the available CPU or server time.</span></span> <span data-ttu-id="fe88e-104">Para crear y ejecutar los paquetes secundarios, es necesario realizar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe88e-104">To create and run the child packages requires the following steps:</span></span>  
  
-   <span data-ttu-id="fe88e-105">Diseñar los paquetes secundarios.</span><span class="sxs-lookup"><span data-stu-id="fe88e-105">Designing the child packages.</span></span>  
  
-   <span data-ttu-id="fe88e-106">Mover los paquetes al servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="fe88e-106">Moving the packages to the remote server.</span></span>  
  
-   <span data-ttu-id="fe88e-107">Crear un trabajo del Agente SQL Server en el servidor remoto que contenga un paso que ejecute el paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="fe88e-107">Creating a SQL Server Agent Job on the remote server that contains a step that runs the child package.</span></span>  
  
-   <span data-ttu-id="fe88e-108">Probar y depurar el trabajo del Agente SQL Server y los paquetes secundarios.</span><span class="sxs-lookup"><span data-stu-id="fe88e-108">Testing and debugging the SQL Server Agent Job and child packages.</span></span>  
  
 <span data-ttu-id="fe88e-109">Cuando diseñe los paquetes secundarios, puesto que no hay ningún límite establecido para el diseño, podrá incluir la funcionalidad que desee.</span><span class="sxs-lookup"><span data-stu-id="fe88e-109">When you design the child packages, the packages have no limitations in their design, and you can put in any functionality you desire.</span></span> <span data-ttu-id="fe88e-110">Sin embargo, si el paquete tiene acceso a datos, debe asegurarse de que el servidor que ejecuta el paquete tenga acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="fe88e-110">However, if the package accesses data, you must ensure that the server that runs the package has access to the data.</span></span>  
  
 <span data-ttu-id="fe88e-111">Para identificar el paquete primario que ejecuta paquetes secundarios, en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] haga clic con el botón derecho en el paquete en el Explorador de soluciones y, después, haga clic en **Paquete de punto de entrada**.</span><span class="sxs-lookup"><span data-stu-id="fe88e-111">To identify the parent package that executes child packages, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] right click the package in Solution Explorer and then click **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="fe88e-112">Una vez diseñados los paquetes secundarios, el próximo paso es implementarlos en los servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="fe88e-112">After the child packages have been designed, the next step is to deploy them on the remote servers.</span></span>  
  
## <a name="moving-the-child-package-to-the-remote-instance"></a><span data-ttu-id="fe88e-113">Mover el paquete secundario a la instancia remota</span><span class="sxs-lookup"><span data-stu-id="fe88e-113">Moving the Child Package to the Remote Instance</span></span>  
 <span data-ttu-id="fe88e-114">Existen varias formas de mover paquetes a otros servidores.</span><span class="sxs-lookup"><span data-stu-id="fe88e-114">There are multiple ways to move packages to other servers.</span></span> <span data-ttu-id="fe88e-115">Los dos métodos sugeridos son:</span><span class="sxs-lookup"><span data-stu-id="fe88e-115">The two suggested methods are:</span></span>  
  
-   <span data-ttu-id="fe88e-116">Exportar paquetes mediante [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe88e-116">Exporting packages by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="fe88e-117">Implementar paquetes generando una utilidad de implementación para el proyecto que contiene los paquetes que desea implementar y, a continuación, ejecutar el Asistente para la instalación de paquetes para instalar los paquetes en el sistema de archivos o en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe88e-117">Deploying packages by building a deployment utility for the project that contains the packages you want to deploy, and then running the Package Installation Wizard to install the packages to the file system or to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fe88e-118">Para obtener más información, vea [implementación de paquetes &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="fe88e-118">For more information, see [Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md).</span></span>  
  
 <span data-ttu-id="fe88e-119">Debe repetir la implementación con cada servidor remoto que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="fe88e-119">You must repeat the deployment to each remote server you want to use.</span></span>  
  
## <a name="creating-the-sql-server-agent-jobs"></a><span data-ttu-id="fe88e-120">Crear trabajos del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="fe88e-120">Creating the SQL Server Agent Jobs</span></span>  
 <span data-ttu-id="fe88e-121">Una vez que se hayan implementado los paquetes secundarios en los distintos servidores, cree un trabajo del Agente SQL Server en cada servidor que contenga un paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="fe88e-121">After the child packages have been deployed to the various servers, create a SQL Server Agent job on each server that contains a child package.</span></span> <span data-ttu-id="fe88e-122">El trabajo del Agente SQL Server incluye un paso que ejecuta el paquete secundario cuando se llama al agente del trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe88e-122">The SQL Server Agent job contains a step that runs the child package when the job agent is called.</span></span> <span data-ttu-id="fe88e-123">Los trabajos del Agente SQL Server no son trabajos programados, sino que ejecutan paquetes secundarios únicamente cuando los llama un paquete primario.</span><span class="sxs-lookup"><span data-stu-id="fe88e-123">The SQL Server Agent jobs are not scheduled jobs; they run the child packages only when they are called by the parent package.</span></span> <span data-ttu-id="fe88e-124">La notificación del éxito o fracaso del trabajo que se devuelve al paquete primario refleja el éxito o fracaso del trabajo del Agente SQL Server y si la llamada fue satisfactoria, no el éxito o fracaso del paquete secundario o si éste se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="fe88e-124">Notification of success or failure of the job back to the parent package reflects the success or failure of the SQL Server Agent job and whether it was called successfully, not the success or failure of the child package or whether it was executed.</span></span>  
  
## <a name="debugging-the-sql-server-agent-jobs-and-child-packages"></a><span data-ttu-id="fe88e-125">Depurar los trabajos del Agente SQL Server y los paquetes secundarios</span><span class="sxs-lookup"><span data-stu-id="fe88e-125">Debugging the SQL Server Agent Jobs and Child Packages</span></span>  
 <span data-ttu-id="fe88e-126">Puede probar los trabajos del Agente SQL Server y sus paquetes secundarios a través de uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe88e-126">You can test the SQL Server Agent jobs and their child packages by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="fe88e-127">Ejecutar cada paquete secundario en el diseñador SSIS haciendo clic en **depurar**  /  **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="fe88e-127">Running each child package in SSIS Designer, by clicking **Debug** / **Start Without Debugging**.</span></span>  
  
-   <span data-ttu-id="fe88e-128">Ejecutar el trabajo individual del Agente SQL Server en el equipo remoto a través de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], para asegurarse de que el paquete se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="fe88e-128">Running the individual SQL Server Agent job on the remote computer by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to make sure that the package runs.</span></span>  
  
 <span data-ttu-id="fe88e-129">Para obtener información sobre cómo solucionar problemas de los paquetes que se ejecutan desde trabajos del Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vea el artículo acerca de [un paquete de SSIS no se ejecuta al llamarlo desde un paso de trabajo del Agente SQL Server](https://support.microsoft.com/kb/918760) en Support Knowledge Base de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe88e-129">For information about how to troubleshoot packages that you run from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs, see [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760) in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Support Knowledge Base.</span></span>  
  
 <span data-ttu-id="fe88e-130">El Agente SQL Server comprueba el acceso al subsistema de un proxy y da acceso al proxy cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe88e-130">The SQL Server Agent checks subsystem access for a proxy and gives access to the proxy every time the job step runs.</span></span>  
  
 <span data-ttu-id="fe88e-131">Puede crear un proxy en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe88e-131">You can create a proxy in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="fe88e-132">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="fe88e-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fe88e-133">Ejecutar un paquete en el servidor SSIS con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe88e-133">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="fe88e-134">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="fe88e-134">Related Content</span></span>  
  
-   <span data-ttu-id="fe88e-135">Entrada de blog, [SSIS: acceso a variables en un paquete primario](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), en andyleonard. blog.</span><span class="sxs-lookup"><span data-stu-id="fe88e-135">Blog entry, [SSIS: Accessing variables in a parent package](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), on andyleonard.blog.</span></span>  
  
-   <span data-ttu-id="fe88e-136">Artículo, [tarea ejecutar paquete](../integration-services/control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="fe88e-136">Article, [Execute Package Task](../integration-services/control-flow/execute-package-task.md).</span></span>  
  
  
