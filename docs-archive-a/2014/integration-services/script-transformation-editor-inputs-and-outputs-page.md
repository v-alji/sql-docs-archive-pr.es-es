---
title: Editor de transformación script (página entradas y salidas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.columnproperties.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: 9659d2d2-5d73-4470-9768-e07b77142fc9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16adf74a1cd8f0c778bc18eaff84437b8fc13603
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744188"
---
# <a name="script-transformation-editor-inputs-and-outputs-page"></a><span data-ttu-id="2c9f9-102">Editor de transformación Script (página Entradas y salidas)</span><span class="sxs-lookup"><span data-stu-id="2c9f9-102">Script Transformation Editor (Inputs and Outputs Page)</span></span>
  <span data-ttu-id="2c9f9-103">Use la página **Entradas y salidas** del cuadro de diálogo **Editor de transformación Script** para agregar, quitar y configurar las entradas y salidas de la transformación Script.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-103">Use the **Inputs and Outputs** page of the **Script Transformation Editor** dialog box to add, remove, and configure inputs and outputs for the Script Transformation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c9f9-104">Los componentes de origen tienen salidas y no tienen entradas, mientras que los componentes de destino tienen entradas y no tienen salidas.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-104">Source components have outputs and no inputs, while destination components have inputs but no outputs.</span></span> <span data-ttu-id="2c9f9-105">Las transformaciones tienen tanto entradas como salidas.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-105">Transformations have both inputs and outputs.</span></span>  
  
 <span data-ttu-id="2c9f9-106">Para obtener más información acerca del componente de script, vea [Script Component](data-flow/transformations/script-component.md) y [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2c9f9-106">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="2c9f9-107">Para obtener información acerca de cómo programar el componente de script, vea [Ampliar el flujo de datos con el componente de script](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="2c9f9-107">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2c9f9-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="2c9f9-108">Options</span></span>  
 <span data-ttu-id="2c9f9-109">**Inputs and outputs**</span><span class="sxs-lookup"><span data-stu-id="2c9f9-109">**Inputs and outputs**</span></span>  
 <span data-ttu-id="2c9f9-110">Seleccione una entrada o salida de la izquierda para ver sus propiedades en la tabla de la derecha.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-110">Select an input or output on the left to view its properties in the table on the right.</span></span> <span data-ttu-id="2c9f9-111">Las propiedades disponibles para edición varían según la selección.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-111">Properties available for editing vary according to the selection.</span></span> <span data-ttu-id="2c9f9-112">Muchas de las propiedades mostradas son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-112">Many of the properties displayed are read-only.</span></span> <span data-ttu-id="2c9f9-113">Para obtener más información sobre las propiedades individuales, vea los temas siguientes.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-113">For more information on the individual properties, see the following topics.</span></span>  
  
 [<span data-ttu-id="2c9f9-114">Common Properties</span><span class="sxs-lookup"><span data-stu-id="2c9f9-114">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
 [<span data-ttu-id="2c9f9-115">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="2c9f9-115">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
 <span data-ttu-id="2c9f9-116">**Agregar salida**</span><span class="sxs-lookup"><span data-stu-id="2c9f9-116">**Add Output**</span></span>  
 <span data-ttu-id="2c9f9-117">Se agrega una salida adicional a la lista.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-117">Add an additional output to the list.</span></span>  
  
 <span data-ttu-id="2c9f9-118">**Agregar columna**</span><span class="sxs-lookup"><span data-stu-id="2c9f9-118">**Add Column**</span></span>  
 <span data-ttu-id="2c9f9-119">Seleccione la carpeta en la que quiere colocar la nueva columna de salida y haga clic en **Agregar columna**para agregar la columna.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-119">Select a folder in which to place the new output column, and then add the column by clicking **Add Column**.</span></span>  
  
 <span data-ttu-id="2c9f9-120">**Quitar salida**</span><span class="sxs-lookup"><span data-stu-id="2c9f9-120">**Remove Output**</span></span>  
 <span data-ttu-id="2c9f9-121">Seleccione una salida y, después, quítela al hacer clic en **Quitar salida**.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-121">Select an output, and then remove it by clicking **Remove Output**.</span></span>  
  
 <span data-ttu-id="2c9f9-122">**Quitar columna**</span><span class="sxs-lookup"><span data-stu-id="2c9f9-122">**Remove Column**</span></span>  
 <span data-ttu-id="2c9f9-123">Seleccione una columna y, después, quítela al hacer clic en **Quitar columna**.</span><span class="sxs-lookup"><span data-stu-id="2c9f9-123">Select a column, and then remove it by clicking **Remove Column**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9f9-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c9f9-124">See Also</span></span>  
 <span data-ttu-id="2c9f9-125">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2c9f9-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2c9f9-126">[Seleccionar tipo de componente de script](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="2c9f9-126">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="2c9f9-127">[Editor de transformación script &#40;página columnas de entrada&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="2c9f9-127">[Script Transformation Editor &#40;Input Columns Page&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span></span>  
 <span data-ttu-id="2c9f9-128">[Editor de transformación script &#40;página script&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="2c9f9-128">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="2c9f9-129">[Editor de transformación script &#40;página administradores de conexión&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="2c9f9-129">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="2c9f9-130">Ejemplos de componente de script adicionales</span><span class="sxs-lookup"><span data-stu-id="2c9f9-130">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
