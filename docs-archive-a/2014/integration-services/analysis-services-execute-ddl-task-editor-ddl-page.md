---
title: Analysis Services el editor de la tarea ejecutar DDL (página DDL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.ddl.f1
helpviewer_keywords:
- Analysis Services Execute DDL Task Editor
ms.assetid: f21bf8d0-ec5f-4c18-9de0-8875addb927b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d207afe666e582c44f1014a6c80f4f4984fd5410
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670517"
---
# <a name="analysis-services-execute-ddl-task-editor-ddl-page"></a><span data-ttu-id="6633a-102">Editor de la tarea Ejecutar DDL de Analysis Services (página DDL)</span><span class="sxs-lookup"><span data-stu-id="6633a-102">Analysis Services Execute DDL Task Editor (DDL Page)</span></span>
  <span data-ttu-id="6633a-103">Use la página **DDL** del cuadro de diálogo **Editor de la tarea Ejecutar DDL de Analysis Services** para especificar una conexión a un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y proporcionar información sobre el origen de las instrucciones del lenguaje de definición de datos (DDL).</span><span class="sxs-lookup"><span data-stu-id="6633a-103">Use the **DDL** page of the **Analysis Services Execute DDL Task Editor** dialog box to specify a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database and to provide information about the source of data definition language (DDL) statements.</span></span>  
  
 <span data-ttu-id="6633a-104">Para obtener información acerca de esta tarea, vea [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).</span><span class="sxs-lookup"><span data-stu-id="6633a-104">To learn about this task, see [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="6633a-105">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="6633a-105">Static Options</span></span>  
 <span data-ttu-id="6633a-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="6633a-106">**Connection**</span></span>  
 <span data-ttu-id="6633a-107">Seleccione un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o un administrador de conexiones de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en la lista, o bien haga clic en \<**New connection...**> y use el cuadro de diálogo **Agregar administrador de conexiones de Analysis Services** para crear una conexión.</span><span class="sxs-lookup"><span data-stu-id="6633a-107">Select an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager in the list, or click \<**New connection...**> and use the **Add Analysis Services Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="6633a-108">**Temas relacionados:** [Referencia de la interfaz de usuario del cuadro de diálogo Agregar administrador de conexiones con Analysis Services](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Administrador de conexiones de Analysis Services](connection-manager/analysis-services-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="6633a-108">**Related Topics:** [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md)</span></span>  
  
 <span data-ttu-id="6633a-109">**Tipo de origen**</span><span class="sxs-lookup"><span data-stu-id="6633a-109">**SourceType**</span></span>  
 <span data-ttu-id="6633a-110">Especifique el tipo de origen de las instrucciones de DDL.</span><span class="sxs-lookup"><span data-stu-id="6633a-110">Specify the source type of the DDL statements.</span></span> <span data-ttu-id="6633a-111">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="6633a-111">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="6633a-112">Value</span><span class="sxs-lookup"><span data-stu-id="6633a-112">Value</span></span>|<span data-ttu-id="6633a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6633a-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6633a-114">**Entrada directa**</span><span class="sxs-lookup"><span data-stu-id="6633a-114">**Direct Input**</span></span>|<span data-ttu-id="6633a-115">Establezca en el cuadro de texto **SourceDirect** el origen de la instrucción DDL almacenada.</span><span class="sxs-lookup"><span data-stu-id="6633a-115">Set the source to the DDL statement stored in the **SourceDirect** text box.</span></span> <span data-ttu-id="6633a-116">Al seleccionar este valor se muestran las opciones dinámicas de la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="6633a-116">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="6633a-117">**Conexión de archivos**</span><span class="sxs-lookup"><span data-stu-id="6633a-117">**File Connection**</span></span>|<span data-ttu-id="6633a-118">Establezca el origen de un archivo que contenga la instrucción DDL.</span><span class="sxs-lookup"><span data-stu-id="6633a-118">Set the source to a file that contains the DDL statement.</span></span> <span data-ttu-id="6633a-119">Al seleccionar este valor se muestran las opciones dinámicas de la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="6633a-119">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="6633a-120">**Variable**</span><span class="sxs-lookup"><span data-stu-id="6633a-120">**Variable**</span></span>|<span data-ttu-id="6633a-121">Establezca el origen en una variable.</span><span class="sxs-lookup"><span data-stu-id="6633a-121">Set the source to a variable.</span></span> <span data-ttu-id="6633a-122">Al seleccionar este valor se muestran las opciones dinámicas de la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="6633a-122">Selecting this value displays the dynamic options in the following section.</span></span>|  
  
## <a name="dynamic-options"></a><span data-ttu-id="6633a-123">Opciones dinámicas</span><span class="sxs-lookup"><span data-stu-id="6633a-123">Dynamic Options</span></span>  
  
### <a name="sourcetype--direct-input"></a><span data-ttu-id="6633a-124">SourceType = Entrada directa</span><span class="sxs-lookup"><span data-stu-id="6633a-124">SourceType = Direct Input</span></span>  
 <span data-ttu-id="6633a-125">**Origen**</span><span class="sxs-lookup"><span data-stu-id="6633a-125">**Source**</span></span>  
 <span data-ttu-id="6633a-126">Escriba las instrucciones de DDL, o bien haga clic en el botón de puntos suspensivos **(…)** y, después, escriba las instrucciones en el cuadro de diálogo **Instrucciones DDL**.</span><span class="sxs-lookup"><span data-stu-id="6633a-126">Type the DDL statements or click the ellipsis **(...)** and then type the statements in the **DDL Statements** dialog box.</span></span>  
  
### <a name="sourcetype--file-connection"></a><span data-ttu-id="6633a-127">SourceType = Conexión de archivos</span><span class="sxs-lookup"><span data-stu-id="6633a-127">SourceType = File Connection</span></span>  
 <span data-ttu-id="6633a-128">**Origen**</span><span class="sxs-lookup"><span data-stu-id="6633a-128">**Source**</span></span>  
 <span data-ttu-id="6633a-129">Seleccione una conexión de archivos de la lista, o bien haga clic en \<**New connection...**> y use el cuadro de diálogo **Administrador de conexiones de archivos** para crear una conexión.</span><span class="sxs-lookup"><span data-stu-id="6633a-129">Select a File connection in the list, or click \<**New connection...**> and use the **File Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="6633a-130">**Temas relacionados:** [Administrador de conexiones de archivos](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="6633a-130">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
### <a name="sourcetype--variable"></a><span data-ttu-id="6633a-131">SourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="6633a-131">SourceType = Variable</span></span>  
 <span data-ttu-id="6633a-132">**Origen**</span><span class="sxs-lookup"><span data-stu-id="6633a-132">**Source**</span></span>  
 <span data-ttu-id="6633a-133">Seleccione una variable de la lista, o bien haga clic en \<**New variable...**> y use el cuadro de diálogo **Agregar variable** para crear una variable.</span><span class="sxs-lookup"><span data-stu-id="6633a-133">Select a variable in the list, or click \<**New variable...**> and use the **Add Variable** dialog box to create a new variable.</span></span>  
  
 <span data-ttu-id="6633a-134">**Temas relacionados:** [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="6633a-134">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6633a-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6633a-135">See Also</span></span>  
 <span data-ttu-id="6633a-136">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6633a-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6633a-137">[Analysis Services &#40;página general del editor de la tarea ejecutar DDL&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="6633a-137">[Analysis Services Execute DDL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="6633a-138">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="6633a-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="6633a-139">[Flujo de control](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="6633a-139">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="6633a-140">[Referencia de ASSL&#41; &#40;de lenguaje de scripting Analysis Services](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span><span class="sxs-lookup"><span data-stu-id="6633a-140">[Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span></span>  
 [<span data-ttu-id="6633a-141">Referencia XML for Analysis &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="6633a-141">XML for Analysis  &#40;XMLA&#41; Reference</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference)  
  
  
