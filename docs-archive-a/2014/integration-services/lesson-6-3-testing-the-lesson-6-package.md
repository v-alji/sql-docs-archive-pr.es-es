---
title: 'Paso 3: Probar el paquete de la lección 6 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c184c92d-948f-4037-a502-5fabd909c84c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3c7ab82e9b04fe0752252102374f745e311d830d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748183"
---
# <a name="step-3-testing-the-lesson-6-package"></a><span data-ttu-id="86728-102">Paso 3: Prueba del paquete de la lección 6</span><span class="sxs-lookup"><span data-stu-id="86728-102">Step 3: Testing the Lesson 6 Package</span></span>
  <span data-ttu-id="86728-103">En tiempo de ejecución, el paquete obtendrá el valor de la Propiedad de directorio desde el parámetro VarFolderName.</span><span class="sxs-lookup"><span data-stu-id="86728-103">At run time, your package will obtain the value for the Directory property from the VarFolderName parameter.</span></span>  
  
 <span data-ttu-id="86728-104">Para comprobar que, durante la ejecución, el paquete actualiza la propiedad Directory con el nuevo valor, simplemente debe ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="86728-104">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="86728-105">Puesto que en el directorio solamente se copiaron tres archivos de datos de ejemplo, el flujo de datos solamente se ejecutará tres veces, en lugar de repetirse a través de los 14 archivos de la carpeta original.</span><span class="sxs-lookup"><span data-stu-id="86728-105">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="86728-106">Comprobar el diseño del paquete</span><span class="sxs-lookup"><span data-stu-id="86728-106">Checking the Package Layout</span></span>  
 <span data-ttu-id="86728-107">Antes de probar el paquete, debe comprobar que los flujos de datos y de control de la lección 6 contienen los objetos mostrados en los diagramas siguientes.</span><span class="sxs-lookup"><span data-stu-id="86728-107">Before you test the package you should verify that the control and data flows in the Lesson 6 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="86728-108">El flujo de control debe ser idéntico al flujo de datos de la lección 5.</span><span class="sxs-lookup"><span data-stu-id="86728-108">The control flow should be identical to the control flow in lesson 5.</span></span> <span data-ttu-id="86728-109">El flujo de datos debe ser idéntico al flujo de datos de la lección 5.</span><span class="sxs-lookup"><span data-stu-id="86728-109">The data flow should be identical to the data flow in lesson 5.</span></span>  
  
 <span data-ttu-id="86728-110">**Flujo de control**</span><span class="sxs-lookup"><span data-stu-id="86728-110">**Control Flow**</span></span>  
  
 <span data-ttu-id="86728-111">![Flujo de control](../../2014/tutorials/media/task3lesson6control.jpg "Flujo de control")</span><span class="sxs-lookup"><span data-stu-id="86728-111">![Control Flow](../../2014/tutorials/media/task3lesson6control.jpg "Control Flow")</span></span>  
  
 <span data-ttu-id="86728-112">**Flujo de datos**</span><span class="sxs-lookup"><span data-stu-id="86728-112">**Data Flow**</span></span>  
  
 <span data-ttu-id="86728-113">![Flujo de datos](../../2014/tutorials/media/task3lesson6data.jpg "Data Flow")</span><span class="sxs-lookup"><span data-stu-id="86728-113">![Data Flow](../../2014/tutorials/media/task3lesson6data.jpg "Data Flow")</span></span>  
  
### <a name="to-test-the-lesson-6-tutorial-package"></a><span data-ttu-id="86728-114">Para probar el paquete del tutorial de la lección 6</span><span class="sxs-lookup"><span data-stu-id="86728-114">TO test the Lesson 6 tutorial package</span></span>  
  
1.  <span data-ttu-id="86728-115">En el menú Depurar, haga clic en Iniciar depuración.</span><span class="sxs-lookup"><span data-stu-id="86728-115">On the Debug menu, click Start Debugging.</span></span>  
  
2.  <span data-ttu-id="86728-116">Una vez que se haya completado la ejecución del paquete, en el menú Depurar, haga clic en Detener depuración.</span><span class="sxs-lookup"><span data-stu-id="86728-116">After the package has completed running, on the Debug menu, and then click Stop Debugging.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="86728-117">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="86728-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="86728-118">Paso 4: Implementación del paquete de la lección 6</span><span class="sxs-lookup"><span data-stu-id="86728-118">Step 4: Deploying the Lesson 6 Package</span></span>](../integration-services/lesson-6-4-deploying-the-lesson-6-package.md)  
  
  
