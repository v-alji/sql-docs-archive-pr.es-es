---
title: Ejemplos de tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], examples
- examples [Integration Services]
- SSIS Script task, examples
ms.assetid: b0dd77ee-ee11-4cd9-87aa-61dd67f2fe1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 920d2ee5cc2e64db1048d10522d9be644794e55b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746325"
---
# <a name="script-task-examples"></a><span data-ttu-id="64390-102">Ejemplos de tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-102">Script Task Examples</span></span>
  <span data-ttu-id="64390-103">La tarea Script es una herramienta con varias funciones que puede utilizar en un paquete para satisfacer casi cualquier requisito que no cumplan las tareas incluidas con [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64390-103">The Script task is a multi-purpose tool that you can use in a package to fill almost any requirement that is not met by the tasks included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="64390-104">En este tema se enumeran los ejemplos de código de la tarea Script que muestran alguna de las funciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="64390-104">This topic lists Script task code samples that demonstrate some of the available functionality.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64390-105">Si desea crear tareas que pueda reutilizar más fácilmente en varios paquetes, considere la posibilidad de utilizar el código de estos ejemplos de tarea Script como punto inicial de las tareas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="64390-105">If you want to create tasks that you can more easily reuse across multiple packages, consider using the code in these Script task samples as the starting point for custom tasks.</span></span> <span data-ttu-id="64390-106">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="64390-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="64390-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="64390-107">In This Section</span></span>  
  
### <a name="example-topics"></a><span data-ttu-id="64390-108">Temas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="64390-108">Example Topics</span></span>  
 <span data-ttu-id="64390-109">Esta sección contiene ejemplos de código que muestran varios usos de las clases de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que puede incorporar en una tarea Script de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64390-109">This section contains code examples that demonstrate various uses of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that you can incorporate into an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task:</span></span>  
  
 [<span data-ttu-id="64390-110">Detectar un archivo plano vacío con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-110">Detecting an Empty Flat File with the Script Task</span></span>](../extending-packages-scripting-task-examples/detecting-an-empty-flat-file-with-the-script-task.md)  
 <span data-ttu-id="64390-111">Comprueba un archivo plano para determinar si contiene filas de datos, y guarda el resultado en una variable para su uso en una bifurcación del flujo de control.</span><span class="sxs-lookup"><span data-stu-id="64390-111">Checks a flat file to determine whether it contains rows of data, and saves the result to a variable for use in control flow branching.</span></span>  
  
 [<span data-ttu-id="64390-112">Recopilar una lista para el bucle ForEach con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-112">Gathering a List for the ForEach Loop with the Script Task</span></span>](../extending-packages-scripting-task-examples/gathering-a-list-for-the-foreach-loop-with-the-script-task.md)  
 <span data-ttu-id="64390-113">Recopila una lista de archivos que cumplen los criterios especificados por el usuario y rellena una variable para su uso posterior por parte del enumerador de variable para Foreach.</span><span class="sxs-lookup"><span data-stu-id="64390-113">Gathers a list of files that meet user-specified criteria, and populates a variable for later use by the Foreach from Variable Enumerator.</span></span>  
  
 [<span data-ttu-id="64390-114">Consultar Active Directory con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-114">Querying the Active Directory with the Script Task</span></span>](../extending-packages-scripting-task-examples/querying-the-active-directory-with-the-script-task.md)  
 <span data-ttu-id="64390-115">Recupera información sobre el usuario de Active Directory basándose en el valor de una variable [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], mediante las clases del espacio de nombres System.DirectoryServices.</span><span class="sxs-lookup"><span data-stu-id="64390-115">Retrieves user information from Active Directory based on the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, by using classes in the System.DirectoryServices namespace.</span></span>  
  
 [<span data-ttu-id="64390-116">Supervisar los contadores de rendimiento con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-116">Monitoring Performance Counters with the Script Task</span></span>](../extending-packages-scripting-task-examples/monitoring-performance-counters-with-the-script-task.md)  
 <span data-ttu-id="64390-117">Crea un contador de rendimiento personalizado que se puede utilizar para realizar el seguimiento del progreso de ejecución de un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], mediante las clases del espacio de nombres System.Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="64390-117">Creates a custom performance counter that can be used to track the execution progress of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package, by using classes in the System.Diagnostics namespace.</span></span>  
  
 [<span data-ttu-id="64390-118">Trabajar con imágenes con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-118">Working with Images with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md)  
 <span data-ttu-id="64390-119">Comprime las imágenes en el formato JPEG y crea las imágenes en miniatura a partir de ellas, mediante las clases del espacio de nombres System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="64390-119">Compresses images into the JPEG format and creates thumbnail images from them, by using classes in the System.Drawing namespace.</span></span>  
  
 [<span data-ttu-id="64390-120">Buscar impresoras instaladas con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-120">Finding Installed Printers with the Script Task</span></span>](../extending-packages-scripting-task-examples/finding-installed-printers-with-the-script-task.md)  
 <span data-ttu-id="64390-121">Busca las impresoras instaladas que admiten un tamaño de papel concreto, mediante las clases del espacio de nombres System.Drawing.Printing.</span><span class="sxs-lookup"><span data-stu-id="64390-121">Locates installed printers that support a specific paper size, by using classes in the System.Drawing.Printing namespace.</span></span>  
  
 [<span data-ttu-id="64390-122">Enviar un mensaje de correo electrónico HTML con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-122">Sending an HTML Mail Message with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-an-html-mail-message-with-the-script-task.md)  
 <span data-ttu-id="64390-123">Envía un mensaje de correo en formato HTML en lugar de texto simple.</span><span class="sxs-lookup"><span data-stu-id="64390-123">Sends a mail message in HTML format instead of plain text format.</span></span>  
  
 [<span data-ttu-id="64390-124">Trabajar con archivos de Excel con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-124">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
 <span data-ttu-id="64390-125">Enumera las hojas de cálculo de un archivo de Excel y comprueba la existencia de una hoja de cálculo concreta.</span><span class="sxs-lookup"><span data-stu-id="64390-125">Lists the worksheets in an Excel file and checks for the existence of a specific worksheet.</span></span>  
  
 [<span data-ttu-id="64390-126">Enviar a una cola de mensajes privada remota con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-126">Sending to a Remote Private Message Queue with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-to-a-remote-private-message-queue-with-the-script-task.md)  
 <span data-ttu-id="64390-127">Envía un mensaje a una cola de mensajes privada remota.</span><span class="sxs-lookup"><span data-stu-id="64390-127">Sends a message to a remote private message queue.</span></span>  
  
### <a name="other-examples"></a><span data-ttu-id="64390-128">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="64390-128">Other Examples</span></span>  
 <span data-ttu-id="64390-129">Los siguientes temas también contienen ejemplos de código para su uso con la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="64390-129">The following topics also contain code examples for use with the Script task:</span></span>  
  
 [<span data-ttu-id="64390-130">Usar variables en la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-130">Using Variables in the Script Task</span></span>](../extending-packages-scripting/task/using-variables-in-the-script-task.md)  
 <span data-ttu-id="64390-131">Solicita al usuario confirmación de si el paquete debe continuar ejecutándose, basándose en el valor de una variable de paquete que puede superar el límite especificado en otra variable.</span><span class="sxs-lookup"><span data-stu-id="64390-131">Asks the user for confirmation of whether the package should continue to run, based on the value of a package variable that may exceed the limit specified in another variable.</span></span>  
  
 [<span data-ttu-id="64390-132">Conectarse a orígenes de datos de la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-132">Connecting to Data Sources in the Script Task</span></span>](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md)  
 <span data-ttu-id="64390-133">Recupera una conexión o información de conexión de los administradores de conexión definidos en el paquete.</span><span class="sxs-lookup"><span data-stu-id="64390-133">Retrieves a connection or connection information from connection managers defined in the package.</span></span>  
  
 [<span data-ttu-id="64390-134">Provocar eventos en la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-134">Raising Events in the Script Task</span></span>](../extending-packages-scripting/task/raising-events-in-the-script-task.md)  
 <span data-ttu-id="64390-135">Produce un error, una advertencia o un mensaje informativo basándose en el estado de conexión a Internet en el servidor.</span><span class="sxs-lookup"><span data-stu-id="64390-135">Raises an error, a warning, or an informational message based on the status of the Internet connection on the server.</span></span>  
  
 [<span data-ttu-id="64390-136">Registrar en la tarea Script</span><span class="sxs-lookup"><span data-stu-id="64390-136">Logging in the Script Task</span></span>](../extending-packages-scripting/task/logging-in-the-script-task.md)  
 <span data-ttu-id="64390-137">Registra el número de elementos procesados por la tarea para los proveedores de registro habilitados.</span><span class="sxs-lookup"><span data-stu-id="64390-137">Logs the number of items processed by the task to enabled log providers.</span></span>  
  
<span data-ttu-id="64390-138">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="64390-138">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="64390-139">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="64390-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="64390-140">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="64390-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="64390-141">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="64390-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
