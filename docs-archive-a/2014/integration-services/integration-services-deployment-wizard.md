---
title: Asistente para la implementación de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.deploymentwizard.f1
ms.assetid: f3d93e13-2d85-47ff-a913-cda4046491c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9afdc529baa4546f126eb67456927e770cb345dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748186"
---
# <a name="integration-services-deployment-wizard"></a><span data-ttu-id="9bdae-102">Asistente para implementación de Integration Services</span><span class="sxs-lookup"><span data-stu-id="9bdae-102">Integration Services Deployment Wizard</span></span>
  <span data-ttu-id="9bdae-103">El Asistente para la implementación de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] implementa proyectos en el catálogo de SSISDB en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] mediante el modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="9bdae-103">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard deploys projects to the SSISDB catalog on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance using the project deployment model.</span></span>  
  
 <span data-ttu-id="9bdae-104">Para iniciar el [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Asistente para la implementación desde un proyecto abierto en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , seleccione **implementar** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="9bdae-104">To start the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard from an open project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], select **Deploy** from the **Project** menu.</span></span> <span data-ttu-id="9bdae-105">Para iniciar el asistente en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , expanda el nodo **catálogos de Integration Services**  >  **SSISDB** en explorador de objetos, haga clic con el botón secundario en la carpeta **proyectos** y, a continuación, haga clic en **implementar proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9bdae-105">To start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** > **SSISDB** node in Object Explorer, right-click the **Projects** folder, and then click **Deploy Project**.</span></span>  
  
 <span data-ttu-id="9bdae-106">El asistente continua con los siguientes cuatro pasos.</span><span class="sxs-lookup"><span data-stu-id="9bdae-106">The wizard proceeds through the following four steps.</span></span> <span data-ttu-id="9bdae-107">Haga clic en **siguiente** para ir al paso siguiente o **anterior** para volver al paso anterior.</span><span class="sxs-lookup"><span data-stu-id="9bdae-107">Click **Next** to move to the next step, or **Previous** to return to the previous step.</span></span>  
  
1.  <span data-ttu-id="9bdae-108">**Seleccionar origen** : seleccione el [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] proyecto que desea implementar.</span><span class="sxs-lookup"><span data-stu-id="9bdae-108">**Select Source** - Select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that you want to deploy.</span></span>  
  
2.  <span data-ttu-id="9bdae-109">**Seleccionar destino** : seleccione el destino del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9bdae-109">**Select Destination** - Select the project destination.</span></span>  
  
3.  <span data-ttu-id="9bdae-110">**Revisar** : muestra las selecciones.</span><span class="sxs-lookup"><span data-stu-id="9bdae-110">**Review** - Displays your selections.</span></span>  
  
4.  <span data-ttu-id="9bdae-111">**Deploy/Results** : implementa el proyecto y muestra los resultados.</span><span class="sxs-lookup"><span data-stu-id="9bdae-111">**Deploy/Results** - Deploys the project and displays the results.</span></span>  
  
## <a name="select-source"></a><span data-ttu-id="9bdae-112">Selección del origen</span><span class="sxs-lookup"><span data-stu-id="9bdae-112">Select Source</span></span>  
 <span data-ttu-id="9bdae-113">Para implementar un archivo de implementación de proyecto que ha creado, seleccione **archivo de implementación de proyecto** y escriba la ruta de acceso al archivo. ISPAC o haga clic en **examinar** para buscarlo en la [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9bdae-113">To deploy a project deployment file that you created, select **Project deployment file** and enter the path to the .ispac file or click **Browse** to find it in the [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project folder.</span></span> <span data-ttu-id="9bdae-114">Para implementar un proyecto que resida en el catálogo de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , seleccione **Catálogo de Integration Services**y especifique el nombre del servidor y la ruta de acceso al proyecto en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="9bdae-114">To deploy a project that resides in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, select **Integration Services catalog**, and then enter the server name and the path to the project in the catalog.</span></span>  
  
 <span data-ttu-id="9bdae-115">Si inicia el asistente en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], posteriormente, de forma predeterminada el asistente selecciona el proyecto abierto como origen y omite este paso.</span><span class="sxs-lookup"><span data-stu-id="9bdae-115">If you start the wizard in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], then by default the wizard selects the open project as the source and skips this step.</span></span> <span data-ttu-id="9bdae-116">Para volver a este paso y seleccionar un origen diferente, haga clic en **anterior** o en **Seleccionar origen** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="9bdae-116">To return to this step and select a different source, click **Previous** or click **Select Source** in the left pane.</span></span>  
  
## <a name="select-destination"></a><span data-ttu-id="9bdae-117">Seleccionar destino</span><span class="sxs-lookup"><span data-stu-id="9bdae-117">Select Destination</span></span>  
 <span data-ttu-id="9bdae-118">Para seleccionar la carpeta de destino para el proyecto en el catálogo [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , escriba la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o haga clic en **Examinar** para seleccionarla en una lista de servidores.</span><span class="sxs-lookup"><span data-stu-id="9bdae-118">To select the destination folder for the project in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, enter the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance or click **Browse** to select from a list of servers.</span></span> <span data-ttu-id="9bdae-119">Escriba la ruta de acceso del proyecto en SSISDB o haga clic en **Examinar** para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="9bdae-119">Enter the project path in SSISDB or click **Browse** to select it.</span></span>  
  
 <span data-ttu-id="9bdae-120">Si inicia el asistente en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], de forma predeterminada, el asistente selecciona la instancia de servidor conectado y especifica la ruta de acceso para el proyecto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9bdae-120">If you start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], then by default the wizard selects the connected server instance and enters the path to the selected project.</span></span> <span data-ttu-id="9bdae-121">Puede cambiar estos valores para implementar el proyecto en una ubicación diferente.</span><span class="sxs-lookup"><span data-stu-id="9bdae-121">You can change these values to deploy the project to a different location.</span></span>  
  
## <a name="review"></a><span data-ttu-id="9bdae-122">Revisar</span><span class="sxs-lookup"><span data-stu-id="9bdae-122">Review</span></span>  
 <span data-ttu-id="9bdae-123">El asistente le permite revisar los valores de configuración que ha seleccionado antes de implementar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9bdae-123">The wizard allows you to review the settings you have selected before deploying the project.</span></span> <span data-ttu-id="9bdae-124">Puede cambiar las selecciones si hace clic en **Anterior**o si hace clic en cualquiera de los pasos del panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="9bdae-124">You can change your selections by clicking **Previous**, or by clicking any of the steps in the left pane.</span></span>  
  
## <a name="deployresults"></a><span data-ttu-id="9bdae-125">Implementar/Resultados</span><span class="sxs-lookup"><span data-stu-id="9bdae-125">Deploy/Results</span></span>  
 <span data-ttu-id="9bdae-126">Al hacer clic en **implementar** en la página **revisar** , el proyecto se implementa y la página **resultados** muestra si cada acción se ha realizado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="9bdae-126">When you click **Deploy** from the **Review** page, the project is deployed and the **Results** page displays the success or failure of each action.</span></span> <span data-ttu-id="9bdae-127">Si la acción no se realiza correctamente, haga clic en **Error** en la columna **Resultado** para que aparezca una explicación del error.</span><span class="sxs-lookup"><span data-stu-id="9bdae-127">If the action fails, click the **Failed** in the **Result** column to display an explanation of the error.</span></span> <span data-ttu-id="9bdae-128">Haga clic en **Guardar Informe** para guardar los resultados en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="9bdae-128">Click **Save Report...** to save the results to an XML file.</span></span>  
  
 <span data-ttu-id="9bdae-129">Haga clic en **Cerrar** para salir del asistente.</span><span class="sxs-lookup"><span data-stu-id="9bdae-129">Click **Close** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bdae-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9bdae-130">See Also</span></span>  
 <span data-ttu-id="9bdae-131">[Implementación de proyectos en Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="9bdae-131">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 [<span data-ttu-id="9bdae-132">Implementación de proyectos y paquetes</span><span class="sxs-lookup"><span data-stu-id="9bdae-132">Deployment of Projects and Packages</span></span>](packages/deploy-integration-services-ssis-projects-and-packages.md)  
  
  
