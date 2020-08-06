---
title: Editor de la tarea servicio Web (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.general.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 4d7df283-430d-4f0f-9dd4-5909554cd5eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dbacf2a2a867ab01039678ff4f43eebac839c11a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676563"
---
# <a name="web-service-task-editor-general-page"></a><span data-ttu-id="c7ba7-102">Editor de la tarea Servicio web (página General)</span><span class="sxs-lookup"><span data-stu-id="c7ba7-102">Web Service Task Editor (General Page)</span></span>
  <span data-ttu-id="c7ba7-103">Use la página **General** del cuadro de diálogo **Editor de la tarea Servicio web** para especificar un administrador de conexiones de HTTP, especificar la ubicación del archivo de Lenguaje de descripción de servicios web (WSDL) que usa la tarea Servicio web, describir la tarea Servicios web y descargar el archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-103">Use the **General** page of the **Web Services Task Editor** dialog box to specify an HTTP connection manager, specify the location of the Web Services Description Language (WSDL) file the Web Service task uses, describe the Web Services task, and download the WSDL file.</span></span>  
  
 <span data-ttu-id="c7ba7-104">Para obtener más información sobre esta tarea, vea [Tarea Servicio web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="c7ba7-104">For more information about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c7ba7-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="c7ba7-105">Options</span></span>  
 <span data-ttu-id="c7ba7-106">**HTTPConnection**</span><span class="sxs-lookup"><span data-stu-id="c7ba7-106">**HTTPConnection**</span></span>  
 <span data-ttu-id="c7ba7-107">Seleccione un administrador de conexiones de la lista o haga clic en \<**New connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-107">Select a connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c7ba7-108">El administrador de conexiones HTTP solo es compatible con la autenticación anónima y la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-108">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="c7ba7-109">No es compatible con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-109">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="c7ba7-110">**Temas relacionados:**  [Administrador de conexiones HTTP](connection-manager/http-connection-manager.md), [Editor del administrador de conexiones HTTP &#40;página Servidor&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span><span class="sxs-lookup"><span data-stu-id="c7ba7-110">**Related Topics:**  [HTTP Connection Manager](connection-manager/http-connection-manager.md), [HTTP Connection Manager Editor &#40;Server Page&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span></span>  
  
 <span data-ttu-id="c7ba7-111">**WSDLFile**</span><span class="sxs-lookup"><span data-stu-id="c7ba7-111">**WSDLFile**</span></span>  
 <span data-ttu-id="c7ba7-112">Escriba la ruta de acceso completa de un archivo WSDL local del equipo, o bien haga clic en el botón Examinar **(…)** y busque el archivo.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-112">Type the fully qualified path of a WSDL file that is local to the computer, or click the browse button **(...)** and locate this file.</span></span>  
  
 <span data-ttu-id="c7ba7-113">Si ya ha descargado manualmente el archivo WSDL en el equipo, seleccione este archivo.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-113">If you have already manually downloaded the WSDL file to the computer, select this file.</span></span> <span data-ttu-id="c7ba7-114">Sin embargo, si el archivo WSDL todavía no se ha descargado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c7ba7-114">However, if the WSDL file has not yet been downloaded, follow these steps:</span></span>  
  
-   <span data-ttu-id="c7ba7-115">Cree un archivo vacío que tenga la extensión ".wsdl".</span><span class="sxs-lookup"><span data-stu-id="c7ba7-115">Create an empty file that has the ".wsdl" file name extension.</span></span>  
  
-   <span data-ttu-id="c7ba7-116">Seleccione este archivo vacío para la opción **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="c7ba7-116">Select this empty file for the **WSDLFile** option.</span></span>  
  
-   <span data-ttu-id="c7ba7-117">Establezca el valor de **OverwriteWSDLFile** en `True` para permitir que el archivo vacío se sobrescriba con el archivo WSDL real.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-117">Set the value of **OverwriteWSDLFile** to `True` to enable the empty file to be overwritten with the actual WSDL file.</span></span>  
  
-   <span data-ttu-id="c7ba7-118">Haga clic en **Descargar WSDL** para descargar el archivo WSDL real y sobrescribir el archivo vacío.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-118">Click **Download WSDL** to download the actual WSDL file and overwrite the empty file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c7ba7-119">La opción **Descargar WSDL** no se habilita hasta que se proporciona el nombre de un archivo local existente en el cuadro **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="c7ba7-119">The **Download WSDL** option is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
 <span data-ttu-id="c7ba7-120">**OverwriteWSDLFile**</span><span class="sxs-lookup"><span data-stu-id="c7ba7-120">**OverwriteWSDLFile**</span></span>  
 <span data-ttu-id="c7ba7-121">Indica si el archivo WSDL de la tarea Servicio web se puede sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-121">Indicate whether the WSDL file for the Web Service task can be overwritten.</span></span>  
  
 <span data-ttu-id="c7ba7-122">Si tiene previsto descargar el archivo WSDL mediante el botón **Descargar WSDL** , establezca este valor en `True` .</span><span class="sxs-lookup"><span data-stu-id="c7ba7-122">If you intend to download the WSDL file by using the **Download WSDL** button, set this value to `True`.</span></span>  
  
 <span data-ttu-id="c7ba7-123">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c7ba7-123">**Name**</span></span>  
 <span data-ttu-id="c7ba7-124">Proporcione un nombre único para la tarea Servicio web.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-124">Provide a unique name for the Web Service task.</span></span> <span data-ttu-id="c7ba7-125">Este nombre se utiliza como etiqueta en el icono de tarea.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-125">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7ba7-126">Los nombres de tarea deben ser únicos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-126">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="c7ba7-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c7ba7-127">**Description**</span></span>  
 <span data-ttu-id="c7ba7-128">Escriba una descripción de la tarea Servicio web.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-128">Type a description of the Web Service task.</span></span>  
  
 <span data-ttu-id="c7ba7-129">**Descargar WSDL**</span><span class="sxs-lookup"><span data-stu-id="c7ba7-129">**Download WSDL**</span></span>  
 <span data-ttu-id="c7ba7-130">Descarga el archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="c7ba7-130">Download the WSDL file.</span></span>  
  
 <span data-ttu-id="c7ba7-131">Este botón no se habilita hasta que se proporciona el nombre de un archivo local existente en el cuadro **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="c7ba7-131">This button is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ba7-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7ba7-132">See Also</span></span>  
 <span data-ttu-id="c7ba7-133">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c7ba7-133">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c7ba7-134">[Editor de la tarea servicio Web &#40;página de entrada&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="c7ba7-134">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 <span data-ttu-id="c7ba7-135">[Editor de la tarea servicio Web &#40;página salida&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c7ba7-135">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="c7ba7-136">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="c7ba7-136">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
