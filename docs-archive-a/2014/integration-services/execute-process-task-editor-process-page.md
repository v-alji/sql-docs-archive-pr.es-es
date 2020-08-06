---
title: Editor de la tarea ejecutar proceso (página procesar) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executeprocesstask.process.f1
helpviewer_keywords:
- Execute Process Task Editor
ms.assetid: 0fc22406-e79b-47a4-a7e4-108d4ce6202f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ce8629be2c07ae4caac4586b266936a908e71499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743609"
---
# <a name="execute-process-task-editor-process-page"></a><span data-ttu-id="11933-102">Editor de la tarea Ejecutar proceso (página Procesar)</span><span class="sxs-lookup"><span data-stu-id="11933-102">Execute Process Task Editor (Process Page)</span></span>
  <span data-ttu-id="11933-103">Utilice la página **Proceso** del cuadro de diálogo **Editor de la tarea Ejecutar proceso** para configurar las opciones que permitirán ejecutar el proceso.</span><span class="sxs-lookup"><span data-stu-id="11933-103">Use the **Process** page of the **Execute Process Task Editor** dialog box to configure the options that execute the process.</span></span> <span data-ttu-id="11933-104">Estas opciones incluyen el ejecutable que se debe instalar, su ubicación, los argumentos de línea de comandos y las variables que proporcionan información de entrada y capturan información de salida.</span><span class="sxs-lookup"><span data-stu-id="11933-104">These options include the executable to run, its location, command prompt arguments, and the variables that provide input and capture output.</span></span>  
  
 <span data-ttu-id="11933-105">Para obtener información acerca de esta tarea, vea [Execute Process Task](control-flow/execute-process-task.md).</span><span class="sxs-lookup"><span data-stu-id="11933-105">To learn about this task, see [Execute Process Task](control-flow/execute-process-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="11933-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="11933-106">Options</span></span>  
 <span data-ttu-id="11933-107">**RequireFullFileName**</span><span class="sxs-lookup"><span data-stu-id="11933-107">**RequireFullFileName**</span></span>  
 <span data-ttu-id="11933-108">Indica si la tarea debe generar un error en caso de que no se encuentre el ejecutable en la ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="11933-108">Indicate whether the task should fail if the executable is not found at the specified location.</span></span>  
  
 <span data-ttu-id="11933-109">**Executable**</span><span class="sxs-lookup"><span data-stu-id="11933-109">**Executable**</span></span>  
 <span data-ttu-id="11933-110">Escriba el nombre del ejecutable que desea instalar.</span><span class="sxs-lookup"><span data-stu-id="11933-110">Type the name of the executable to run.</span></span>  
  
 <span data-ttu-id="11933-111">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="11933-111">**Arguments**</span></span>  
 <span data-ttu-id="11933-112">Proporcione los argumentos de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="11933-112">Provide command prompt arguments.</span></span>  
  
 <span data-ttu-id="11933-113">**WorkingDirectory**</span><span class="sxs-lookup"><span data-stu-id="11933-113">**WorkingDirectory**</span></span>  
 <span data-ttu-id="11933-114">Escriba la ruta de acceso de la carpeta que contiene el ejecutable, o bien haga clic en el botón Examinar **(…)** y busque la carpeta.</span><span class="sxs-lookup"><span data-stu-id="11933-114">Type the path of the folder that contains the executable, or click the browse button **(...)** and locate the folder.</span></span>  
  
 <span data-ttu-id="11933-115">**StandardInputVariable**</span><span class="sxs-lookup"><span data-stu-id="11933-115">**StandardInputVariable**</span></span>  
 <span data-ttu-id="11933-116">Seleccione una variable para proporcionar la entrada al proceso o haga clic en \<**New variable...**> para crear una:</span><span class="sxs-lookup"><span data-stu-id="11933-116">Select a variable to provide the input to the process, or click \<**New variable...**> to create a new variable:</span></span>  
  
 <span data-ttu-id="11933-117">**Temas relacionados:**  [Agregar variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="11933-117">**Related Topics:**  [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="11933-118">**StandardOutputVariable**</span><span class="sxs-lookup"><span data-stu-id="11933-118">**StandardOutputVariable**</span></span>  
 <span data-ttu-id="11933-119">Seleccione una variable para capturar la salida del proceso o haga clic en \<**New variable...**> para crear una.</span><span class="sxs-lookup"><span data-stu-id="11933-119">Select a variable to capture the output of the process, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="11933-120">**StandardErrorVariable**</span><span class="sxs-lookup"><span data-stu-id="11933-120">**StandardErrorVariable**</span></span>  
 <span data-ttu-id="11933-121">Seleccione una variable para capturar la salida del error del procesador o haga clic en \<**New variable...**> para crear una.</span><span class="sxs-lookup"><span data-stu-id="11933-121">Select a variable to capture the error output of the processor, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="11933-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span><span class="sxs-lookup"><span data-stu-id="11933-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span></span>  
 <span data-ttu-id="11933-123">Esta opción indica si la tarea genera un error porque el código de salida del proceso es diferente del valor especificado en **SuccessValue**.</span><span class="sxs-lookup"><span data-stu-id="11933-123">Indicate whether the task fails if the process exit code is different from the value specified in **SuccessValue**.</span></span>  
  
 <span data-ttu-id="11933-124">**SuccessValue**</span><span class="sxs-lookup"><span data-stu-id="11933-124">**SuccessValue**</span></span>  
 <span data-ttu-id="11933-125">Especifique el valor que devuelve el ejecutable para indicar su instalación correcta.</span><span class="sxs-lookup"><span data-stu-id="11933-125">Specify the value returned by the executable to indicate success.</span></span> <span data-ttu-id="11933-126">De forma predeterminada, este valor está establecido en **0**.</span><span class="sxs-lookup"><span data-stu-id="11933-126">By default this value is set to **0**.</span></span>  
  
 <span data-ttu-id="11933-127">**TimeOut**</span><span class="sxs-lookup"><span data-stu-id="11933-127">**TimeOut**</span></span>  
 <span data-ttu-id="11933-128">Especifique el número de segundos que el proceso puede ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="11933-128">Specify the number of seconds that the process can run.</span></span> <span data-ttu-id="11933-129">El valor **0** indica que no se usará ningún valor de tiempo de espera y que el proceso se ejecutará hasta su conclusión o hasta que se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="11933-129">A value of **0** indicates that no time-out value is used, and the process runs until it is completed or until an error occurs.</span></span>  
  
 <span data-ttu-id="11933-130">**TerminateProcessAfterTimeOut**</span><span class="sxs-lookup"><span data-stu-id="11933-130">**TerminateProcessAfterTimeOut**</span></span>  
 <span data-ttu-id="11933-131">Esta opción indica si el proceso está obligado a finalizar después del período de tiempo de espera especificado con la opción **TimeOut** .</span><span class="sxs-lookup"><span data-stu-id="11933-131">Indicate whether the process is forced to end after the time-out period specified by the **TimeOut** option.</span></span> <span data-ttu-id="11933-132">Esta opción solo está disponible si el valor de **TimeOut** es distinto de **0**.</span><span class="sxs-lookup"><span data-stu-id="11933-132">This option is available only if **TimeOut** is not **0**.</span></span>  
  
 <span data-ttu-id="11933-133">**WindowStyle**</span><span class="sxs-lookup"><span data-stu-id="11933-133">**WindowStyle**</span></span>  
 <span data-ttu-id="11933-134">Especifique el estilo de ventana en el que ejecutará el proceso.</span><span class="sxs-lookup"><span data-stu-id="11933-134">Specify the window style in which to run the process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11933-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11933-135">See Also</span></span>  
 <span data-ttu-id="11933-136">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="11933-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="11933-137">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="11933-137">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
