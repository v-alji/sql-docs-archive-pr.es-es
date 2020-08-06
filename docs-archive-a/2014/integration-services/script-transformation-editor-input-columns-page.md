---
title: Editor de transformación script (página columnas de entrada) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.inputcolumn.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: d6e4ce84-3335-48e6-82d3-1c359ed87f63
author: chugugrace
ms.author: chugu
ms.openlocfilehash: daffb52b62ad59ae4fe574d7fa27d4820b9cb5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744190"
---
# <a name="script-transformation-editor-input-columns-page"></a><span data-ttu-id="a33c5-102">Editor de transformación Script (página Columnas de entrada)</span><span class="sxs-lookup"><span data-stu-id="a33c5-102">Script Transformation Editor (Input Columns Page)</span></span>
  <span data-ttu-id="a33c5-103">Utilice la página **Columnas de entrada** del cuadro de diálogo **Editor de transformación Script** para definir las propiedades de las columnas de entrada.</span><span class="sxs-lookup"><span data-stu-id="a33c5-103">Use the **Input Columns** page of the **Script Transformation Editor** dialog box to set properties on input columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a33c5-104">La página **Columnas de entrada** no se muestra para los componentes de origen, que tienen salidas, pero no entradas.</span><span class="sxs-lookup"><span data-stu-id="a33c5-104">The **Input Columns** page is not displayed for Source components, which have outputs but no inputs.</span></span>  
  
 <span data-ttu-id="a33c5-105">Para obtener más información acerca del componente de script, vea [Script Component](data-flow/transformations/script-component.md) y [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a33c5-105">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="a33c5-106">Para obtener información acerca de cómo programar el componente de script, vea [Ampliar el flujo de datos con el componente de script](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="a33c5-106">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a33c5-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="a33c5-107">Options</span></span>  
 <span data-ttu-id="a33c5-108">**Nombre de entrada**</span><span class="sxs-lookup"><span data-stu-id="a33c5-108">**Input name**</span></span>  
 <span data-ttu-id="a33c5-109">Seleccione las entradas disponibles de la lista.</span><span class="sxs-lookup"><span data-stu-id="a33c5-109">Select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="a33c5-110">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="a33c5-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="a33c5-111">Mediante las casillas, indique las columnas que utilizarán la transformación de script.</span><span class="sxs-lookup"><span data-stu-id="a33c5-111">Using the check boxes, specify the columns that the script transformation will use.</span></span>  
  
 <span data-ttu-id="a33c5-112">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="a33c5-112">**Input Column**</span></span>  
 <span data-ttu-id="a33c5-113">Seleccione de la lista de entradas disponibles las columnas para cada fila.</span><span class="sxs-lookup"><span data-stu-id="a33c5-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="a33c5-114">Las selecciones se reflejan en las casillas activadas en la tabla **Columnas de entrada disponibles**.</span><span class="sxs-lookup"><span data-stu-id="a33c5-114">Your selections are reflected in the check box selections in the **Available Input Columns**table.</span></span>  
  
 <span data-ttu-id="a33c5-115">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="a33c5-115">**Output Alias**</span></span>  
 <span data-ttu-id="a33c5-116">Escriba un alias para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="a33c5-116">Type an alias for each output column.</span></span> <span data-ttu-id="a33c5-117">El nombre predeterminado es el de la columna de entrada, pero puede elegir cualquier nombre descriptivo único.</span><span class="sxs-lookup"><span data-stu-id="a33c5-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="a33c5-118">**Tipo de uso**</span><span class="sxs-lookup"><span data-stu-id="a33c5-118">**Usage Type**</span></span>  
 <span data-ttu-id="a33c5-119">Especifique si la transformación de script tratará cada columna como `ReadOnly` o `ReadWrite`.</span><span class="sxs-lookup"><span data-stu-id="a33c5-119">Specify whether the Script Transformation will treat each column as `ReadOnly` or `ReadWrite`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33c5-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a33c5-120">See Also</span></span>  
 <span data-ttu-id="a33c5-121">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a33c5-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a33c5-122">[Seleccionar tipo de componente de script](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="a33c5-122">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="a33c5-123">[Editor de transformación script &#40;página entradas y salidas&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span><span class="sxs-lookup"><span data-stu-id="a33c5-123">[Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span></span>  
 <span data-ttu-id="a33c5-124">[Editor de transformación script &#40;página script&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="a33c5-124">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="a33c5-125">[Editor de transformación script &#40;página administradores de conexión&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="a33c5-125">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="a33c5-126">Ejemplos de componente de script adicionales</span><span class="sxs-lookup"><span data-stu-id="a33c5-126">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
