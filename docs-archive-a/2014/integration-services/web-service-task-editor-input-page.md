---
title: Editor de la tarea servicio Web (página entrada) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.input.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 93529c88-f540-47f2-a10a-12c87318ed6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ae876572747b9bb1088fe8b0a1c2c2fdde9f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676561"
---
# <a name="web-service-task-editor-input-page"></a><span data-ttu-id="9a583-102">Editor de la tarea Servicio web (página Entrada)</span><span class="sxs-lookup"><span data-stu-id="9a583-102">Web Service Task Editor (Input Page)</span></span>
  <span data-ttu-id="9a583-103">Use la página **Entrada** del cuadro de diálogo **Editor de la tarea Servicio web** para especificar el servicio web, el método web y los valores que se deben proporcionar como entrada para el método web.</span><span class="sxs-lookup"><span data-stu-id="9a583-103">Use the **Input** page of the **Web Service Task Editor** dialog box to specify the Web Service, the Web method, and the values to provide to the Web method as input.</span></span> <span data-ttu-id="9a583-104">Los valores se pueden proporcionar mediante la especificación directa de cadenas o la selección de variables en la columna Valor.</span><span class="sxs-lookup"><span data-stu-id="9a583-104">The values can be provided either by typing strings directly in the Value column, or by selecting variables in the Value column.</span></span>  
  
 <span data-ttu-id="9a583-105">Para obtener información sobre esta tarea, vea [Tarea Servicio web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="9a583-105">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9a583-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="9a583-106">Options</span></span>  
 <span data-ttu-id="9a583-107">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="9a583-107">**Service**</span></span>  
 <span data-ttu-id="9a583-108">Seleccione en la lista un servicio web para ejecutar el método web.</span><span class="sxs-lookup"><span data-stu-id="9a583-108">Select a Web service from the list to use to execute the Web method.</span></span>  
  
 <span data-ttu-id="9a583-109">**Método**</span><span class="sxs-lookup"><span data-stu-id="9a583-109">**Method**</span></span>  
 <span data-ttu-id="9a583-110">Seleccione en la lista un método web para la tarea que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9a583-110">Select a Web method from the list for the task to execute.</span></span>  
  
 <span data-ttu-id="9a583-111">**Documentación del método web**</span><span class="sxs-lookup"><span data-stu-id="9a583-111">**WebMethodDocumentation**</span></span>  
 <span data-ttu-id="9a583-112">Escriba una descripción del método web, o bien haga clic en el botón Examinar **(…)** y escriba una descripción en el cuadro de diálogo **Documentación del método web**.</span><span class="sxs-lookup"><span data-stu-id="9a583-112">Type a description of Web method, or the click the browse button **(...)** and then type the description in the **Web Method Documentation** dialog box.</span></span>  
  
 <span data-ttu-id="9a583-113">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9a583-113">**Name**</span></span>  
 <span data-ttu-id="9a583-114">Muestra los nombres de las entradas del método web.</span><span class="sxs-lookup"><span data-stu-id="9a583-114">Lists the names of the inputs to the Web method.</span></span>  
  
 <span data-ttu-id="9a583-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9a583-115">**Type**</span></span>  
 <span data-ttu-id="9a583-116">Muestra los tipos de datos de las entradas.</span><span class="sxs-lookup"><span data-stu-id="9a583-116">Lists the data type of the inputs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a583-117">La tarea Servicio web solo admite parámetros de los tipos de datos siguientes: tipos primitivos tales como enteros y cadenas; matrices y secuencias de tipos primitivos, y enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="9a583-117">The Web Service task supports parameters of the following data types only: primitive types such as integers and strings; arrays and sequences of primitive types; and enumerations.</span></span>  
  
 <span data-ttu-id="9a583-118">**Variable**</span><span class="sxs-lookup"><span data-stu-id="9a583-118">**Variable**</span></span>  
 <span data-ttu-id="9a583-119">Active las casillas para utilizar variables que proporcionen entradas.</span><span class="sxs-lookup"><span data-stu-id="9a583-119">Select the check boxes to use variables to provide inputs.</span></span>  
  
 <span data-ttu-id="9a583-120">**Valor**</span><span class="sxs-lookup"><span data-stu-id="9a583-120">**Value**</span></span>  
 <span data-ttu-id="9a583-121">Si las casillas de Variable están activadas, seleccione las variables de la lista para proporcionar entradas; en caso contrario, escriba los valores que se usarán en las entradas.</span><span class="sxs-lookup"><span data-stu-id="9a583-121">If the Variable check-boxes are selected, select the variables in the list to provide the inputs; otherwise, type the values to use in the inputs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a583-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a583-122">See Also</span></span>  
 <span data-ttu-id="9a583-123">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9a583-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9a583-124">[Editor de la tarea servicio Web &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="9a583-124">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="9a583-125">[Editor de la tarea servicio Web &#40;página salida&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="9a583-125">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="9a583-126">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="9a583-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
