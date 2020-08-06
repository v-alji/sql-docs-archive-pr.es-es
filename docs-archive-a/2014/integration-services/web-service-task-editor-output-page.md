---
title: Editor de la tarea servicio Web (página salida) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.output.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 73c83969-7b0e-479d-a436-0a46b2068d01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ad034ae78a096ebe5998ac2c3d2573fe7c3bfd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676558"
---
# <a name="web-service-task-editor-output-page"></a><span data-ttu-id="5ae38-102">Editor de la tarea Servicio web (página Salida)</span><span class="sxs-lookup"><span data-stu-id="5ae38-102">Web Service Task Editor (Output Page)</span></span>
  <span data-ttu-id="5ae38-103">Use la página **Salida** del cuadro de diálogo **Editor de la tarea Servicio web** para indicar dónde desea almacenar el resultado devuelto por el método web.</span><span class="sxs-lookup"><span data-stu-id="5ae38-103">Use the **Output** page of the **Web Service Task Editor** dialog box to specify where to store the result returned by the Web method.</span></span>  
  
 <span data-ttu-id="5ae38-104">Para obtener información sobre esta tarea, vea [Tarea Servicio web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="5ae38-104">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="5ae38-105">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="5ae38-105">Static Options</span></span>  
 <span data-ttu-id="5ae38-106">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="5ae38-106">**OutputType**</span></span>  
 <span data-ttu-id="5ae38-107">Seleccione el tipo de almacenamiento que desea usar para almacenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="5ae38-107">Select the storage type to use when storing the results.</span></span> <span data-ttu-id="5ae38-108">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="5ae38-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="5ae38-109">Value</span><span class="sxs-lookup"><span data-stu-id="5ae38-109">Value</span></span>|<span data-ttu-id="5ae38-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ae38-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5ae38-111">**Conexión de archivos**</span><span class="sxs-lookup"><span data-stu-id="5ae38-111">**File Connection**</span></span>|<span data-ttu-id="5ae38-112">Almacene los resultados en un archivo.</span><span class="sxs-lookup"><span data-stu-id="5ae38-112">Store the results in a file.</span></span> <span data-ttu-id="5ae38-113">Si selecciona este valor, se mostrará la opción dinámica **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="5ae38-113">Selecting this value displays the dynamic option, **File**.</span></span>|  
|<span data-ttu-id="5ae38-114">**Variable**</span><span class="sxs-lookup"><span data-stu-id="5ae38-114">**Variable**</span></span>|<span data-ttu-id="5ae38-115">Almacene los resultados en una variable.</span><span class="sxs-lookup"><span data-stu-id="5ae38-115">Store the results in a variable.</span></span> <span data-ttu-id="5ae38-116">Si selecciona este valor, se mostrará la opción dinámica **Variable**.</span><span class="sxs-lookup"><span data-stu-id="5ae38-116">Selecting this value displays the dynamic option, **Variable**.</span></span>|  
  
## <a name="outputtype-dynamic-options"></a><span data-ttu-id="5ae38-117">Opciones dinámicas de OutputType</span><span class="sxs-lookup"><span data-stu-id="5ae38-117">OutputType Dynamic Options</span></span>  
  
### <a name="outputtype--file-connection"></a><span data-ttu-id="5ae38-118">OutputType = Conexión de archivos</span><span class="sxs-lookup"><span data-stu-id="5ae38-118">OutputType = File Connection</span></span>  
 <span data-ttu-id="5ae38-119">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="5ae38-119">**File**</span></span>  
 <span data-ttu-id="5ae38-120">Seleccione un administrador de conexiones de archivos de la lista o haga clic en \<**New Connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="5ae38-120">Select a File connection manager in the list or click \<**New Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="5ae38-121">**Temas relacionados:** [Administrador de conexiones de archivos](connection-manager/file-connection-manager.md), [Editor de administrador de conexiones de archivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="5ae38-121">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="outputtype--variable"></a><span data-ttu-id="5ae38-122">OutputType = Variable</span><span class="sxs-lookup"><span data-stu-id="5ae38-122">OutputType = Variable</span></span>  
 <span data-ttu-id="5ae38-123">**Variable**</span><span class="sxs-lookup"><span data-stu-id="5ae38-123">**Variable**</span></span>  
 <span data-ttu-id="5ae38-124">Seleccione una variable de la lista o haga clic en \<**New Variable...**> para crear una.</span><span class="sxs-lookup"><span data-stu-id="5ae38-124">Select a variable in the list or click \<**New Variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="5ae38-125">**Temas relacionados:**  [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="5ae38-125">**Related Topics:**  [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae38-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ae38-126">See Also</span></span>  
 <span data-ttu-id="5ae38-127">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5ae38-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="5ae38-128">[Editor de la tarea servicio Web &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="5ae38-128">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="5ae38-129">[Editor de la tarea servicio Web &#40;página de entrada&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="5ae38-129">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 [<span data-ttu-id="5ae38-130">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="5ae38-130">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
