---
title: 'Paso 9: Probar el paquete del tutorial de la lección 1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9aee7acf-797b-46f2-830d-80ab64a9f0b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dff1132489c1683430b1003e88f5037664b11983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673114"
---
# <a name="step-9-testing-the-lesson-1-tutorial-package"></a><span data-ttu-id="5460d-102">Paso 9: Prueba del paquete del tutorial de la lección 1</span><span class="sxs-lookup"><span data-stu-id="5460d-102">Step 9: Testing the Lesson 1 Tutorial Package</span></span>
  <span data-ttu-id="5460d-103">En esta lección, ha llevado a cabo las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5460d-103">In this lesson, you have done the following tasks:</span></span>  
  
-   <span data-ttu-id="5460d-104">Ha creado un proyecto de [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5460d-104">Created a new [!INCLUDE[ssIS](../includes/ssis-md.md)] project.</span></span>  
  
-   <span data-ttu-id="5460d-105">Ha configurado los administradores de conexión que el paquete necesita para conectarse a los datos de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="5460d-105">Configured the connection managers that the package needs to connect to the source and destination data.</span></span>  
  
-   <span data-ttu-id="5460d-106">Ha agregado un flujo de datos que toma los datos de un origen de archivo plano, realiza las transformaciones de búsqueda necesarias en los datos y configura los datos para el destino.</span><span class="sxs-lookup"><span data-stu-id="5460d-106">Added a data flow that takes the data from a flat file source, performs the necessary Lookup transformations on the data, and configures the data for the destination.</span></span>  
  
 <span data-ttu-id="5460d-107">El paquete ya se ha completado.</span><span class="sxs-lookup"><span data-stu-id="5460d-107">Your package is now complete!</span></span> <span data-ttu-id="5460d-108">Ha llegado el momento de probarlo.</span><span class="sxs-lookup"><span data-stu-id="5460d-108">It is time to test your package.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="5460d-109">Comprobar el diseño del paquete</span><span class="sxs-lookup"><span data-stu-id="5460d-109">Checking the Package Layout</span></span>  
 <span data-ttu-id="5460d-110">Antes de probar el paquete, debe comprobar que los flujos de datos y de control de la lección 1 contienen los objetos mostrados en los diagramas siguientes.</span><span class="sxs-lookup"><span data-stu-id="5460d-110">Before you test the package you should verify that the control and data flows in the Lesson 1 package contain the objects shown in the following diagrams.</span></span>  
  
 <span data-ttu-id="5460d-111">**Flujo de control**</span><span class="sxs-lookup"><span data-stu-id="5460d-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="5460d-112">![Flujo de control del paquete](../../2014/tutorials/media/task9lesson1control.gif "Flujo de control del paquete")</span><span class="sxs-lookup"><span data-stu-id="5460d-112">![Control flow in package](../../2014/tutorials/media/task9lesson1control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="5460d-113">**Flujo de datos**</span><span class="sxs-lookup"><span data-stu-id="5460d-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="5460d-114">![Flujo de datos del paquete](../../2014/tutorials/media/task9lesson1data.gif "Flujo de datos del paquete")</span><span class="sxs-lookup"><span data-stu-id="5460d-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-1-tutorial-package"></a><span data-ttu-id="5460d-115">Para ejecutar el paquete del tutorial de la lección 1</span><span class="sxs-lookup"><span data-stu-id="5460d-115">To run the Lesson 1 tutorial package</span></span>  
  
1.  <span data-ttu-id="5460d-116">En el menú **Depurar**, haga clic en **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="5460d-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="5460d-117">El paquete se ejecutará, dando lugar a la correcta inclusión de 1097 filas en la tabla de hechos **FactCurrency** de **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="5460d-117">The package will run, resulting in 1097 rows successfully added into the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span>  
  
2.  <span data-ttu-id="5460d-118">Una vez que se haya completado la ejecución del paquete, en el menú **Depurar** , haga clic en **Detener depuración**.</span><span class="sxs-lookup"><span data-stu-id="5460d-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="5460d-119">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="5460d-119">Next Lesson</span></span>  
 [<span data-ttu-id="5460d-120">Lección 2: Adición de bucles</span><span class="sxs-lookup"><span data-stu-id="5460d-120">Lesson 2: Adding Looping</span></span>](../integration-services/lesson-2-adding-looping-with-ssis.md)  
  
## <a name="see-also"></a><span data-ttu-id="5460d-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5460d-121">See Also</span></span>  
 <span data-ttu-id="5460d-122">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) (Ejecución de proyectos y paquetes)</span><span class="sxs-lookup"><span data-stu-id="5460d-122">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md)</span></span>  
  
  
