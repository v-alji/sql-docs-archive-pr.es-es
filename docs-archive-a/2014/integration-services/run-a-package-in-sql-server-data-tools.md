---
title: Ejecutar un paquete en SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, running
- SSIS packages, running
- packages [Integration Services], running
- SQL Server Integration Services packages, running
ms.assetid: 318e6beb-5540-4101-82a5-18c9d47f0570
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31ca2390ef6bb04b63e4de9978193aed8884da36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744738"
---
# <a name="run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="ed95b-102">Ejecutar un paquete en SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="ed95b-102">Run a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="ed95b-103">Los paquetes se ejecutan normalmente en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] durante el desarrollo, la depuración y la comprobación de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="ed95b-103">You typically run packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] during the development, debugging, and testing of packages.</span></span> <span data-ttu-id="ed95b-104">Cuando se ejecuta un paquete desde el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] , siempre se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="ed95b-104">When you run a package from [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the package always runs immediately.</span></span>  
  
 <span data-ttu-id="ed95b-105">Mientras se ejecuta un paquete, el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] muestra el progreso de la ejecución en la pestaña **Progreso** . Puede ver la hora de inicio y de fin del paquete y sus tareas y contendores, además de información acerca de las tareas o contenedores del paquete que generó un error.</span><span class="sxs-lookup"><span data-stu-id="ed95b-105">While a package is running, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer displays the progress of package execution on the **Progress** tab. You can view the start and finish time of the package and its tasks and containers, in addition to information about any tasks or containers in the package that failed.</span></span> <span data-ttu-id="ed95b-106">Una vez que el paquete ha terminado de ejecutarse, la información de tiempo de ejecución permanece disponible en la pestaña **Resultados de la ejecución** . Para obtener más información, vea la sección "Informes de progreso" en el tema [Debugging Control Flow](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="ed95b-106">After the package finishes running, the run-time information remains available on the **Execution Results** tab. For more information, see the section, "Progress Reporting," in the topic, [Debugging Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="ed95b-107">**Implementación en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="ed95b-107">**Design-time deployment**.</span></span> <span data-ttu-id="ed95b-108">Cuando se ejecuta un paquete en [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], el paquete se genera y luego se implementa en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="ed95b-108">When you run a package in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the package is built and then deployed to a folder.</span></span> <span data-ttu-id="ed95b-109">Antes de ejecutar el paquete, puede especificar la carpeta en que se implementa el paquete.</span><span class="sxs-lookup"><span data-stu-id="ed95b-109">Before you run the package, you can specify the folder to which the package is deployed.</span></span> <span data-ttu-id="ed95b-110">Si no especifica una carpeta, se usa de forma predeterminada la carpeta **bin** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ed95b-110">If you do not specify a folder, the **bin** folder is used by default.</span></span> <span data-ttu-id="ed95b-111">Este tipo de implementación se denomina implementación en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="ed95b-111">This type of deployment is called design-time deployment.</span></span>  
  
### <a name="to-run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="ed95b-112">Para ejecutar un paquete en herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed95b-112">To run a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="ed95b-113">En el Explorador de soluciones, si la solución contiene varios proyectos, haga clic con el botón derecho en el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete y, después, haga clic en **Establecer como objeto StartUp** para establecer el proyecto inicial.</span><span class="sxs-lookup"><span data-stu-id="ed95b-113">In Solution Explorer, if your solution contains multiple projects, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package, and then click **Set as StartUp Object** to set the startup project.</span></span>  
  
2.  <span data-ttu-id="ed95b-114">En el Explorador de soluciones, si el proyecto contiene varios paquetes, haga clic con el botón derecho en un paquete y, después, haga clic en **Establecer como objeto StartUp** para establecer el paquete inicial.</span><span class="sxs-lookup"><span data-stu-id="ed95b-114">In Solution Explorer, if your project contains multiple packages, right-click a package, and then click **Set as StartUp Object** to set the startup package.</span></span>  
  
3.  <span data-ttu-id="ed95b-115">Para ejecutar un paquete, use uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed95b-115">To run a package, use one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="ed95b-116">Abra el paquete que desea ejecutar y haga clic en **Iniciar depuración** en la barra de menús, o presione F5.</span><span class="sxs-lookup"><span data-stu-id="ed95b-116">Open the package that you want to run and then click **Start Debugging** on the menu bar, or press F5.</span></span> <span data-ttu-id="ed95b-117">Cuando se termine de ejecutar el paquete, presione Mayús+F5 para volver al modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="ed95b-117">After the package finishes running, press Shift+F5 to return to design mode.</span></span>  
  
    -   <span data-ttu-id="ed95b-118">En el Explorador de soluciones, haga clic con el botón derecho en el paquete y, después, haga clic en **Ejecutar paquete**.</span><span class="sxs-lookup"><span data-stu-id="ed95b-118">In Solution Explorer, right-click the package, and then click **Execute Package**.</span></span>  
  
### <a name="to-specify-a-different-folder-for-design-time-deployment"></a><span data-ttu-id="ed95b-119">Para especificar una carpeta diferente para la implementación en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ed95b-119">To specify a different folder for design-time deployment</span></span>  
  
1.  <span data-ttu-id="ed95b-120">En el Explorador de soluciones, haga clic con el botón derecho en la carpeta del proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que quiera ejecutar y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ed95b-120">In Solution Explorer, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project folder that contains the package you want to run, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ed95b-121">En el cuadro de diálogo **Página de propiedades de \<project name>** , haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="ed95b-121">In the **\<project name> Property Pages** dialog box, click **Build**.</span></span>  
  
3.  <span data-ttu-id="ed95b-122">Actualice el valor de la propiedad OutputPath para especificar la carpeta que quiere usar para la implementación en tiempo de diseño y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ed95b-122">Update the value in the OutputPath property to specify the folder you want to use for design-time deployment, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed95b-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed95b-123">See Also</span></span>  
 <span data-ttu-id="ed95b-124">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md)  (Ejecución de proyectos y paquetes)</span><span class="sxs-lookup"><span data-stu-id="ed95b-124">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="ed95b-125">Paquetes de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ed95b-125">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
