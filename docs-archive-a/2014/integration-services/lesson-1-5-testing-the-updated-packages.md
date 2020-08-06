---
title: 'Paso 5: Probar los paquetes actualizados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 683e52e5-1c7e-49ab-9ffe-6a450a1c5776
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a075af2e030c8257d01abf5eba7d330b1cc8efe7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673122"
---
# <a name="step-5-testing-the-updated-packages"></a><span data-ttu-id="66e56-102">Paso 5: Prueba de los paquetes actualizados</span><span class="sxs-lookup"><span data-stu-id="66e56-102">Step 5: Testing the Updated Packages</span></span>
  <span data-ttu-id="66e56-103">Antes de ir a la siguiente lección, en la que creará el paquete de implementación que se utilizará para instalar los paquetes del tutorial en el equipo de destino, debe probar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="66e56-103">Before you go on to the next lesson, in which you will create the deployment bundle to use to install the tutorial packages on the destination computer, you should test the packages.</span></span> <span data-ttu-id="66e56-104">En esta tarea, ejecutará los paquetes, DataTransfer.dtsx y LoadXMLData, que ha agregado al proyecto Deployment Tutorial y ha ampliado con configuraciones.</span><span class="sxs-lookup"><span data-stu-id="66e56-104">In this task, you will run the packages, DataTransfer.dtsx and LoadXMLData, that you added to the Deployment Tutorial project and then extended with configurations.</span></span>  
  
 <span data-ttu-id="66e56-105">Al ejecutar los paquetes, cada ejecutable del paquete se convierte en color verde en cuanto finaliza correctamente.</span><span class="sxs-lookup"><span data-stu-id="66e56-105">When the packages run, each executable in the package becomes a green color as it completes successfully.</span></span> <span data-ttu-id="66e56-106">Cuando todos los ejecutables están en verde, el paquete se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="66e56-106">When all executables are green, the package has completed successfully.</span></span> <span data-ttu-id="66e56-107">También puede ver el progreso en la ejecución del paquete en la pestaña **Progreso** .</span><span class="sxs-lookup"><span data-stu-id="66e56-107">You can also view the package execution progress on the **Progress** tab.</span></span>  
  
 <span data-ttu-id="66e56-108">Si los paquetes no se ejecutan correctamente, debe solucionarlos antes de ir a la siguiente lección.</span><span class="sxs-lookup"><span data-stu-id="66e56-108">If the packages do not run successfully, you must fix them before you go on to the next lesson.</span></span>  
  
### <a name="to-run-the-datatransfer-package"></a><span data-ttu-id="66e56-109">Para ejecutar el paquete DataTransfer</span><span class="sxs-lookup"><span data-stu-id="66e56-109">To run the DataTransfer package</span></span>  
  
1.  <span data-ttu-id="66e56-110">En el Explorador de soluciones, haga clic en DataTransfer.dtsx.</span><span class="sxs-lookup"><span data-stu-id="66e56-110">In Solution Explorer, click DataTransfer.dtsx.</span></span>  
  
2.  <span data-ttu-id="66e56-111">En el menú **Depurar** , haga clic en **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="66e56-111">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="66e56-112">Una vez que se haya completado la ejecución del paquete, en el menú **Depurar** , haga clic en **Detener depuración**.</span><span class="sxs-lookup"><span data-stu-id="66e56-112">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-run-the-loadxmldata-package"></a><span data-ttu-id="66e56-113">Para ejecutar el paquete LoadXMLData</span><span class="sxs-lookup"><span data-stu-id="66e56-113">To run the LoadXMLData package</span></span>  
  
1.  <span data-ttu-id="66e56-114">En el Explorador de soluciones, haga clic en LoadXMLData.dtsx.</span><span class="sxs-lookup"><span data-stu-id="66e56-114">In Solution Explorer, click LoadXMLData.dtsx.</span></span>  
  
2.  <span data-ttu-id="66e56-115">En el menú **Depurar** , haga clic en **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="66e56-115">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="66e56-116">Una vez que se haya completado la ejecución del paquete, en el menú **Depurar** , haga clic en **Detener depuración**.</span><span class="sxs-lookup"><span data-stu-id="66e56-116">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="66e56-117">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="66e56-117">Next Lesson</span></span>  
 [<span data-ttu-id="66e56-118">Lección 2: Creación del paquete de implementación</span><span class="sxs-lookup"><span data-stu-id="66e56-118">Lesson 2: Creating the Deployment Bundle</span></span>](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md)  
  
<span data-ttu-id="66e56-119">![Integration Services icono (pequeño)](media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="66e56-119">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="66e56-120">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="66e56-120">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="66e56-121">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="66e56-121">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="66e56-122">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="66e56-122">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
