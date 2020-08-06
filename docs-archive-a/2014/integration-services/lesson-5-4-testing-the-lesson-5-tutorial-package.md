---
title: 'Paso 4: Probar el paquete del tutorial de la lección 5 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5215b77d-c2ec-4b25-a3de-ca49ea197d74
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 76e4692de4daa9ddd6ed0e418bed5cda74ec7650
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670429"
---
# <a name="step-4-testing-the-lesson-5-tutorial-package"></a><span data-ttu-id="1d696-102">Paso 4: Prueba del paquete del tutorial de la lección 5</span><span class="sxs-lookup"><span data-stu-id="1d696-102">Step 4: Testing the Lesson 5 Tutorial Package</span></span>
  <span data-ttu-id="1d696-103">Durante la ejecución, el paquete obtendrá el valor de la propiedad `Directory` de una variable actualizada en tiempo de ejecución, en lugar de utilizar el nombre de directorio original especificado al crear el paquete.</span><span class="sxs-lookup"><span data-stu-id="1d696-103">At run time, your package will obtain the value for the `Directory` property from a variable updated at run time, rather than using the original directory name that you specified when you created the package.</span></span> <span data-ttu-id="1d696-104">El valor de la variable lo rellena el archivo SSISTutorial.dtsConfig.</span><span class="sxs-lookup"><span data-stu-id="1d696-104">The value of the variable is populated by the SSISTutorial.dtsConfig file.</span></span>  
  
 <span data-ttu-id="1d696-105">Para comprobar que, durante la ejecución, el paquete actualiza la propiedad Directory con el nuevo valor, simplemente debe ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="1d696-105">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="1d696-106">Puesto que en el directorio solamente se copiaron tres archivos de datos de ejemplo, el flujo de datos solamente se ejecutará tres veces, en lugar de repetirse a través de los 14 archivos de la carpeta original.</span><span class="sxs-lookup"><span data-stu-id="1d696-106">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="1d696-107">Comprobar el diseño del paquete</span><span class="sxs-lookup"><span data-stu-id="1d696-107">Checking the Package Layout</span></span>  
 <span data-ttu-id="1d696-108">Antes de probar el paquete, debe comprobar que los flujos de datos y de control de la lección 5 contienen los objetos mostrados en los diagramas siguientes.</span><span class="sxs-lookup"><span data-stu-id="1d696-108">Before you test the package you should verify that the control and data flows in the Lesson 5 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="1d696-109">El flujo de control debe ser idéntico al flujo de datos de la lección 4.</span><span class="sxs-lookup"><span data-stu-id="1d696-109">The control flow should be identical to the control flow in lesson 4.</span></span> <span data-ttu-id="1d696-110">El flujo de datos debe ser idéntico al flujo de datos de la lección 4.</span><span class="sxs-lookup"><span data-stu-id="1d696-110">The data flow should be identical to the data flow in lessons 4.</span></span>  
  
 <span data-ttu-id="1d696-111">**Flujo de control**</span><span class="sxs-lookup"><span data-stu-id="1d696-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="1d696-112">![Flujo de control del paquete](../../2014/tutorials/media/task4lesson2control.gif "Flujo de control del paquete")</span><span class="sxs-lookup"><span data-stu-id="1d696-112">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="1d696-113">**Flujo de datos**</span><span class="sxs-lookup"><span data-stu-id="1d696-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="1d696-114">![Flujo de datos del paquete](../../2014/tutorials/media/task9lesson1data.gif "Flujo de datos del paquete")</span><span class="sxs-lookup"><span data-stu-id="1d696-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-5-tutorial-package"></a><span data-ttu-id="1d696-115">Para probar el paquete de tutorial de la lección 5</span><span class="sxs-lookup"><span data-stu-id="1d696-115">To test the Lesson 5 tutorial package</span></span>  
  
1.  <span data-ttu-id="1d696-116">En el menú **Depurar**, haga clic en **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="1d696-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="1d696-117">Una vez finalizada la ejecución del paquete, en el menú **depurar** , haga clic en **detener depuración**.</span><span class="sxs-lookup"><span data-stu-id="1d696-117">After the package has completed running, on the **Debug** menu, and then click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="1d696-118">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="1d696-118">Next Lesson</span></span>  
 [<span data-ttu-id="1d696-119">Lección 6: Uso de parámetros con el modelo de implementación de proyectos</span><span class="sxs-lookup"><span data-stu-id="1d696-119">Lesson 6: Using Parameters with the Project Deployment Model</span></span>](../integration-services/lesson-6-using-parameters-with-the-project-deployment-model-in-ssis.md)  
  
  
