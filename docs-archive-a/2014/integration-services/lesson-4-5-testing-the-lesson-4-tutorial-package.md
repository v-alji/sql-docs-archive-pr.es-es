---
title: 'Paso 5: Probar el paquete del tutorial de la lección 4 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5f18df92-0248-4858-836b-c8b02f0e0439
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a897f99bf68805e4e66c3b6bbe818b312077fb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747690"
---
# <a name="step-5-testing-the-lesson-4-tutorial-package"></a><span data-ttu-id="5d4ba-102">Paso 5: Prueba del paquete del tutorial de la lección 4</span><span class="sxs-lookup"><span data-stu-id="5d4ba-102">Step 5: Testing the Lesson 4 Tutorial Package</span></span>
  <span data-ttu-id="5d4ba-103">En tiempo de ejecución, el archivo dañado, Currency_BAD.txt, no podrá generar una coincidencia en la transformación Lookup Currency Key.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-103">At run time, the corrupted file, Currency_BAD.txt, will fail to generate a match within the Currency Key Lookup transformation.</span></span> <span data-ttu-id="5d4ba-104">Puesto que la salida de errores de Lookup Currency Key se ha configurado para redirigir las filas con errores al nuevo destino de filas con errores, el componente no genera ningún error y el paquete se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-104">Because the error output of Currency Key Lookup has now been configured to redirect failed rows to the new Failed Rows destination, the component does not fail, and the package runs successfully.</span></span> <span data-ttu-id="5d4ba-105">Todas las filas que generan un error se escriben en el archivo ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-105">All failed error rows are written to ErrorOutput.txt.</span></span>  
  
 <span data-ttu-id="5d4ba-106">En esta tarea, probará la configuración de la salida de error revisada ejecutando el paquete.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-106">In this task, you will test the revised error output configuration by running the package.</span></span> <span data-ttu-id="5d4ba-107">Tras ejecutar correctamente el paquete, verá el contenido del archivo ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-107">Upon successful package execution, you will then view the contents of the ErrorOutput.txt file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d4ba-108">Si no desea acumular filas con errores en el archivo ErrorOutput.txt, debe eliminar manualmente el contenido del archivo entre ejecuciones de paquetes.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-108">If you do not want to accumulate error rows in the ErrorOutput.txt file, you should manually delete the file content between package runs.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="5d4ba-109">Comprobar el diseño del paquete</span><span class="sxs-lookup"><span data-stu-id="5d4ba-109">Checking the Package layout</span></span>  
 <span data-ttu-id="5d4ba-110">Antes de probar el paquete, debe comprobar que los flujos de datos y de control del paquete de la lección 4 contienen los objetos mostrados en los diagramas siguientes.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-110">Before you test the package you should verify that the control flow and the data flow in the Lesson 4 package contain the objects shown in the following diagrams.</span></span> <span data-ttu-id="5d4ba-111">El flujo de control debe ser idéntico al flujo de datos de las lecciones 2 a 4.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-111">The control flow should be identical to the control flow in lessons 2 - 4.</span></span>  
  
 <span data-ttu-id="5d4ba-112">**Flujo de control**</span><span class="sxs-lookup"><span data-stu-id="5d4ba-112">**Control Flow**</span></span>  
  
 <span data-ttu-id="5d4ba-113">![Flujo de control del paquete](../../2014/tutorials/media/task4lesson2control.gif "Flujo de control del paquete")</span><span class="sxs-lookup"><span data-stu-id="5d4ba-113">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="5d4ba-114">**Flujo de datos**</span><span class="sxs-lookup"><span data-stu-id="5d4ba-114">**Data Flow**</span></span>  
  
 <span data-ttu-id="5d4ba-115">![Flujo de datos del paquete](../../2014/tutorials/media/task5lesson5data.gif "Flujo de datos del paquete")</span><span class="sxs-lookup"><span data-stu-id="5d4ba-115">![Data flow in package](../../2014/tutorials/media/task5lesson5data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-4-tutorial-package"></a><span data-ttu-id="5d4ba-116">Para ejecutar el paquete de tutorial de la lección 4</span><span class="sxs-lookup"><span data-stu-id="5d4ba-116">To run the Lesson 4 tutorial package</span></span>  
  
1.  <span data-ttu-id="5d4ba-117">En el menú **Depurar**, haga clic en **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-117">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="5d4ba-118">Una vez que se haya completado la ejecución del paquete, en el menú **Depurar** , haga clic en **Detener depuración**.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-verify-the-contents-of-the-erroroutputtxt-file"></a><span data-ttu-id="5d4ba-119">Para comprobar el contenido del archivo ErrorOutput.txt</span><span class="sxs-lookup"><span data-stu-id="5d4ba-119">To verify the contents of the ErrorOutput.txt file</span></span>  
  
-   <span data-ttu-id="5d4ba-120">En el Bloc de notas o en cualquier otro editor de texto, abra el archivo ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-120">In Notepad or any other text editor, open the ErrorOutput.txt file.</span></span> <span data-ttu-id="5d4ba-121">El orden predeterminado de las columnas es: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-121">The default column order is: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span></span>  
  
     <span data-ttu-id="5d4ba-122">Observe que todas las filas del archivo contienen el valor BAD de CurrencyID sin coincidencia, el valor -1071607778 de ErrorCode, el valor 0 de ErrorColumn y el valor "La fila no produjo ninguna coincidencia durante la búsqueda" de ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-122">Notice that all the rows in the file contain the unmatched CurrencyID value of BAD, the ErrorCode value of -1071607778, the ErrorColumn value of 0, and the ErrorDescription value "Row yielded no match during lookup".</span></span> <span data-ttu-id="5d4ba-123">El valor de ErrorColumn se establece en 0 porque el error no es específico de columna.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-123">The value of the ErrorColumn is set to 0 because the error is not column specific.</span></span> <span data-ttu-id="5d4ba-124">Es la operación de búsqueda la que ha generado el error.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-124">It is the lookup operation that failed.</span></span> <span data-ttu-id="5d4ba-125">.</span><span class="sxs-lookup"><span data-stu-id="5d4ba-125">.</span></span>  
  
  
