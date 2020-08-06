---
title: 'Paso 1: Generar la utilidad de implementación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1ff4dcff-89b3-4b99-a725-5f7963e98abf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3d32dcbf4bfcf9758dfe58803b75094d1807aa90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673107"
---
# <a name="step-1-building-the-deployment-utility"></a><span data-ttu-id="26bef-102">Paso 1: Compilación de la utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="26bef-102">Step 1: Building the Deployment Utility</span></span>
  <span data-ttu-id="26bef-103">En esta tarea, configurará y generará una utilidad de implementación para el proyecto Deployment Tutorial.</span><span class="sxs-lookup"><span data-stu-id="26bef-103">In this task, you will configure and build a deployment utility for the Deployment Tutorial project.</span></span>  
  
 <span data-ttu-id="26bef-104">Antes de generar la utilidad de implementación, debe modificar las propiedades del proyecto Deployment Tutorial.</span><span class="sxs-lookup"><span data-stu-id="26bef-104">Before you can build the deployment utility, you must modify the properties of the Deployment Tutorial project.</span></span> <span data-ttu-id="26bef-105">Usará el cuadro de diálogo **Deployment Tutorial Property Pages** (Páginas de propiedades de Deployment Tutorial) para configurar estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="26bef-105">You will use the **Deployment Tutorial Property Pages** dialog box to configure these properties.</span></span> <span data-ttu-id="26bef-106">En este cuadro de diálogo, debe habilitar la capacidad de actualizar configuraciones durante la implementación y especificar que el proceso de creación crea una utilidad de implementación.</span><span class="sxs-lookup"><span data-stu-id="26bef-106">In this dialog box, you must enable the ability to update configurations during deployment and specify that the build process generates a deployment utility.</span></span> <span data-ttu-id="26bef-107">Después de establecer las propiedades, generará el proyecto.</span><span class="sxs-lookup"><span data-stu-id="26bef-107">After you set the properties, you will build the project.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="26bef-108">proporciona un conjunto de ventanas que puede usar para depurar paquetes.</span><span class="sxs-lookup"><span data-stu-id="26bef-108">provides a set of windows that you can use to debug packages.</span></span> <span data-ttu-id="26bef-109">Puede ver mensajes de errores, advertencias e información, realizar el seguimiento del estado de paquetes en tiempo de ejecución o ver el progreso y los resultados de los procesos de generación.</span><span class="sxs-lookup"><span data-stu-id="26bef-109">You can view error, warning, and information messages, track about the status of packages at run time, or view the progress and results of build processes.</span></span> <span data-ttu-id="26bef-110">En esta lección, usará la ventana de resultados para ver el progreso y el resultado de la generación de la utilidad de implementación.</span><span class="sxs-lookup"><span data-stu-id="26bef-110">For this lesson, you will use the Output window to view the progress and results of building the deployment utility.</span></span>  
  
### <a name="to-set-the-deployment-utility-properties"></a><span data-ttu-id="26bef-111">Para establecer las propiedades de la utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="26bef-111">To set the deployment utility properties</span></span>  
  
1.  <span data-ttu-id="26bef-112">Si [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] no está abierto todavía, haga clic en **Inicio**, seleccione **Todos los programas**, **Microsoft SQL Server**y, después, haga clic en **Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="26bef-112">If [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="26bef-113">En el menú **Archivo** , haga clic en **Abrir**y, en **Proyecto o solución**, haga clic en la carpeta **Deployment Tutorial** a continuación, haga clic en **Abrir**y, después, haga doble clic en **Deployment Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="26bef-113">On the **File** menu, click **Open**, click **Project/Solution**, click the **Deployment Tutorial** folder and click **Open**, and then double-click **Deployment Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="26bef-114">En el Explorador de soluciones, haga clic con el botón derecho en Deployment Tutorial y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="26bef-114">In Solution Explorer, right-click Deployment Tutorial and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="26bef-115">En el cuadro de diálogo **Deployment Tutorial Property Pages** (Páginas de propiedades de Deployment Tutorial), expanda Propiedades de configuración y haga clic en Utilidad de implementación.</span><span class="sxs-lookup"><span data-stu-id="26bef-115">In the **Deployment Tutorial Property Pages** dialog box, expand Configuration Properties, and click Deployment Utility.</span></span>  
  
5.  <span data-ttu-id="26bef-116">En el panel derecho del cuadro de diálogo **páginas de propiedades del tutorial de implementación** , compruebe que `AllowConfigurationChanges` está establecido en `true` , establecido `CreateDeploymentUtility` en y `true` , opcionalmente, actualice el valor predeterminado de `DeploymentOutputPath` .</span><span class="sxs-lookup"><span data-stu-id="26bef-116">In the right pane of the **Deployment Tutorial Property Pages** dialog box, verify that `AllowConfigurationChanges` is set to `true`, set `CreateDeploymentUtility` to `true`, and optionally update the default value of `DeploymentOutputPath`.</span></span>  
  
6.  <span data-ttu-id="26bef-117">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="26bef-117">Click **OK**.</span></span>  
  
### <a name="to-build-the-deployment-utility"></a><span data-ttu-id="26bef-118">Para generar las propiedades de la utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="26bef-118">To build the deployment utility</span></span>  
  
1.  <span data-ttu-id="26bef-119">En el Explorador de soluciones, haga clic en **Deployment Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="26bef-119">In Solution Explorer, click **Deployment Tutorial**.</span></span>  
  
2.  <span data-ttu-id="26bef-120">En el menú **Ver** , haga clic en **Salida**.</span><span class="sxs-lookup"><span data-stu-id="26bef-120">On the **View** menu, click **Output**.</span></span> <span data-ttu-id="26bef-121">De forma predeterminada, la ventana de resultados se encuentra en la esquina inferior izquierda de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26bef-121">By default, the Output window is located in the bottom left corner of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="26bef-122">En el menú **Generar** , haga clic en **Build Deployment Tutorial**(Generar Deployment Tutorial).</span><span class="sxs-lookup"><span data-stu-id="26bef-122">On the **Build** menu, click **Build Deployment Tutorial**.</span></span>  
  
4.  <span data-ttu-id="26bef-123">En la ventana de resultados, compruebe la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="26bef-123">In the Output window, verify the following information:</span></span>  
  
     <span data-ttu-id="26bef-124">Generación iniciada: proyecto de SQL Integration Services: Incremental...</span><span class="sxs-lookup"><span data-stu-id="26bef-124">Build started: SQL Integration Services project: Incremental ...</span></span>  
  
     <span data-ttu-id="26bef-125">Creando la utilidad de implementación...</span><span class="sxs-lookup"><span data-stu-id="26bef-125">Creating deployment utility...</span></span>  
  
     <span data-ttu-id="26bef-126">Utilidad de implementación creada.</span><span class="sxs-lookup"><span data-stu-id="26bef-126">Deployment Utility created.</span></span>  
  
     <span data-ttu-id="26bef-127">Generación completa -- 0 errores, 0 advertencias</span><span class="sxs-lookup"><span data-stu-id="26bef-127">Build complete -- 0 errors, 0 warnings</span></span>  
  
     <span data-ttu-id="26bef-128">========== Compilación: 0 correcto, 0 errores, 1 actualizados, 0 omitidos ==========</span><span class="sxs-lookup"><span data-stu-id="26bef-128">========== Build: 0 succeeded, 0 failed, 1 up-to-date, 0 skipped ==========</span></span>  
  
5.  <span data-ttu-id="26bef-129">En el menú **Archivo** , haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="26bef-129">On the **File** menu, click **Exit**.</span></span> <span data-ttu-id="26bef-130">Si se le pregunta si quiere guardar los cambios en los elementos de Deployment Tutorial, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="26bef-130">If prompted to save changes to Deployment Tutorial items, click **Yes**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="26bef-131">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="26bef-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="26bef-132">Paso 2: Comprobar el paquete de implementación</span><span class="sxs-lookup"><span data-stu-id="26bef-132">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
<span data-ttu-id="26bef-133">![Integration Services icono (pequeño)](media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="26bef-133">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="26bef-134">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="26bef-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="26bef-135">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="26bef-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="26bef-136">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="26bef-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26bef-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26bef-137">See Also</span></span>  
 [<span data-ttu-id="26bef-138">Crear una utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="26bef-138">Create a Deployment Utility</span></span>](../../2014/integration-services/create-a-deployment-utility.md)  
  
  
