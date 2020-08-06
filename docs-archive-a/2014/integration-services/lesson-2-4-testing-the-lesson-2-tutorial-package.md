---
title: 'Paso 4: Probar el paquete del tutorial de la lección 2 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0e8c0a25-8f79-41df-8ed2-f82a74b129cd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c055f80cbe9e6748b82569204e3a2d82e2f437e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663575"
---
# <a name="step-4-testing-the-lesson-2-tutorial-package"></a><span data-ttu-id="0073a-102">Paso 4: Prueba del paquete del tutorial de la lección 2</span><span class="sxs-lookup"><span data-stu-id="0073a-102">Step 4: Testing the Lesson 2 Tutorial Package</span></span>
  <span data-ttu-id="0073a-103">Con el contenedor de bucles Foreach y el administrador de conexiones de archivo plano que ha configurado, el paquete de la lección 2 puede iterarse a través de la colección de 14 archivos planos de la carpeta Datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0073a-103">With the Foreach Loop container and the Flat File connection manager now configured, the Lesson 2 package can iterate through the collection of 14 flat files in the Sample Data folder.</span></span> <span data-ttu-id="0073a-104">Cada vez que se encuentra un archivo que coincide con los criterios de nombre de archivo especificados, el contenedor de bucles Foreach rellena la variable definida por el usuario con el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="0073a-104">Each time a file name is found that matches the specified file name criteria, the Foreach Loop container populates the user-defined variable with the file name.</span></span> <span data-ttu-id="0073a-105">Esta variable, a su vez, actualiza la propiedad ConnectionString del administrador de conexiones de archivos planos, y se establece una conexión con el archivo plano nuevo.</span><span class="sxs-lookup"><span data-stu-id="0073a-105">This variable, in turn, updates the ConnectionString property of the Flat File connection manager, and a connection to the new flat file is made.</span></span> <span data-ttu-id="0073a-106">A continuación, el contenedor de bucles Foreach ejecuta la tarea de flujo de datos sin modificar en los datos del nuevo archivo plano antes de establecer conexión con el siguiente archivo de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="0073a-106">The Foreach Loop container then runs the unmodified data flow task against the data in the new flat file before connecting to the next file in the folder.</span></span>  
  
 <span data-ttu-id="0073a-107">Utilice el procedimiento siguiente para probar la nueva función del bucle que ha agregado al paquete.</span><span class="sxs-lookup"><span data-stu-id="0073a-107">Use the following procedure to test the new looping functionality that you have added to your package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0073a-108">Si ejecutó el paquete desde la lección 1, necesitará eliminar los registros de dbo.FactCurrency en AdventureWorksDW2012 antes de ejecutar el paquete desde esta lección; de lo contrario, el paquete producirá errores que indican la infracción de una restricción de clave principal.</span><span class="sxs-lookup"><span data-stu-id="0073a-108">If you ran the package from Lesson 1, you will need to delete the records from dbo.FactCurrency in AdventureWorksDW2012 before you run the package from this lesson or the package will fail with errors indicating a Violation of Primary Key constraint.</span></span> <span data-ttu-id="0073a-109">Recibirá los mismos errores si ejecuta el paquete seleccionando Depurar/Iniciar la depuración (o presiona F5) porque se ejecutarán las lecciones 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="0073a-109">You will receive the same errors if you run the package by selecting Debug/Start Debugging (or press F5) because both Lesson 1 and Lesson 2 will run.</span></span> <span data-ttu-id="0073a-110">La lección 2 intentará insertar registros que ya se insertaron en la lección 1.</span><span class="sxs-lookup"><span data-stu-id="0073a-110">Lesson 2 will attempt to insert records already inserted in Lesson 1.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="0073a-111">Comprobar el diseño del paquete</span><span class="sxs-lookup"><span data-stu-id="0073a-111">Checking the Package Layout</span></span>  
 <span data-ttu-id="0073a-112">Antes de probar el paquete, debe comprobar que los flujos de datos y de control de la lección 2 contienen los objetos mostrados en los diagramas siguientes.</span><span class="sxs-lookup"><span data-stu-id="0073a-112">Before you test the package you should verify that the control and data flows in the Lesson 2 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="0073a-113">El flujo de datos debe ser idéntico al flujo de datos de la lección 1.</span><span class="sxs-lookup"><span data-stu-id="0073a-113">The data flow should be identical to the data flow in lesson 1.</span></span>  
  
 <span data-ttu-id="0073a-114">**Flujo de control**</span><span class="sxs-lookup"><span data-stu-id="0073a-114">**Control Flow**</span></span>  
  
 <span data-ttu-id="0073a-115">![Flujo de control del paquete](../../2014/tutorials/media/task4lesson2control.gif "Flujo de control del paquete")</span><span class="sxs-lookup"><span data-stu-id="0073a-115">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="0073a-116">**Flujo de datos**</span><span class="sxs-lookup"><span data-stu-id="0073a-116">**Data Flow**</span></span>  
  
 <span data-ttu-id="0073a-117">![Flujo de datos del paquete](../../2014/tutorials/media/task9lesson1data.gif "Flujo de datos del paquete")</span><span class="sxs-lookup"><span data-stu-id="0073a-117">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-2-tutorial-package"></a><span data-ttu-id="0073a-118">Para probar el paquete del tutorial de la lección 2</span><span class="sxs-lookup"><span data-stu-id="0073a-118">To test the Lesson 2 tutorial package</span></span>  
  
1.  <span data-ttu-id="0073a-119">En el **Explorador de soluciones**, haga clic con el botón derecho en **Lesson 2.dtsx** y, después, haga clic en **Ejecutar paquete**.</span><span class="sxs-lookup"><span data-stu-id="0073a-119">In **Solution Explorer**, right-click **Lesson 2.dtsx** and click **Execute Package**.</span></span>  
  
     <span data-ttu-id="0073a-120">El paquete se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="0073a-120">The package will run.</span></span> <span data-ttu-id="0073a-121">Puede comprobar el estado de cada bucle en la ventana de salida o haciendo clic en la pestaña **progreso** . Por ejemplo, puede ver que se han agregado 1097 líneas a la tabla de destino desde el archivo Currency_VEB.txt.</span><span class="sxs-lookup"><span data-stu-id="0073a-121">You can verify the status of each loop in the Output window, or by clicking on the **Progress** tab. For example, you can see that 1097 lines were added to the destination table from the file Currency_VEB.txt.</span></span>  
  
2.  <span data-ttu-id="0073a-122">Una vez que se haya completado la ejecución del paquete, en el menú **Depurar** , haga clic en **Detener depuración**.</span><span class="sxs-lookup"><span data-stu-id="0073a-122">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="0073a-123">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="0073a-123">Next Lesson</span></span>  
 [<span data-ttu-id="0073a-124">Lección 5: Adición de configuraciones de paquete para el modelo de implementación de paquetes</span><span class="sxs-lookup"><span data-stu-id="0073a-124">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>](../integration-services/lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="0073a-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0073a-125">See Also</span></span>  
 <span data-ttu-id="0073a-126">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) (Ejecución de proyectos y paquetes)</span><span class="sxs-lookup"><span data-stu-id="0073a-126">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md)</span></span>  
  
  
