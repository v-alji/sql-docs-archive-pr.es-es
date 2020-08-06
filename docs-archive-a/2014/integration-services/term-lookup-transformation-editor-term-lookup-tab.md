---
title: Editor de transformación búsqueda de términos (pestaña búsqueda de términos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termlookup.termlookup.f1
helpviewer_keywords:
- Term Lookup Transformation Editor
ms.assetid: 245d3466-d51f-4073-978a-694a8d9dfaec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bb8c0bd0477d9883640cc3e4d3cb25c2a3a8b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677203"
---
# <a name="term-lookup-transformation-editor-term-lookup-tab"></a><span data-ttu-id="8e16e-102">Editor de transformación Búsqueda de términos (pestaña Búsqueda de términos)</span><span class="sxs-lookup"><span data-stu-id="8e16e-102">Term Lookup Transformation Editor (Term Lookup Tab)</span></span>
  <span data-ttu-id="8e16e-103">Use la pestaña **Búsqueda de términos** del cuadro de diálogo **Editor de transformación Búsqueda de términos** para asignar una columna de entrada a una columna de búsqueda en una tabla de referencia y para proporcionar un alias a cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="8e16e-103">Use the **Term Lookup** tab of the **Term Lookup Transformation Editor** dialog box to map an input column to a lookup column in a reference table and to provide an alias for each output column.</span></span>  
  
 <span data-ttu-id="8e16e-104">Para obtener más información acerca de la transformación Búsqueda de términos, vea [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8e16e-104">To learn more about the Term Lookup transformation, see [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8e16e-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="8e16e-105">Options</span></span>  
 <span data-ttu-id="8e16e-106">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="8e16e-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="8e16e-107">Con las casillas, seleccione las columnas de entrada que se van a pasar directamente a la salida sin cambios.</span><span class="sxs-lookup"><span data-stu-id="8e16e-107">Using the check boxes, select input columns to pass through to the output unchanged.</span></span> <span data-ttu-id="8e16e-108">Arrastre una columna de entrada a la lista **Columnas de referencia disponibles** para asignarla a una columna de búsqueda en la tabla de referencia.</span><span class="sxs-lookup"><span data-stu-id="8e16e-108">Drag an input column to the **Available Reference Columns** list to map it to a lookup column in the reference table.</span></span> <span data-ttu-id="8e16e-109">Las columnas de entrada y búsqueda deben coincidir en los tipos de datos admitidos, DT_NTEXT o DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="8e16e-109">The input and lookup columns must have matching, supported data types, either DT_NTEXT or DT_WSTR.</span></span> <span data-ttu-id="8e16e-110">Seleccione una línea de asignación y haga clic con el botón derecho para editar las asignaciones en el cuadro de diálogo [Crear relaciones](data-flow/transformations/create-relationships.md) .</span><span class="sxs-lookup"><span data-stu-id="8e16e-110">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="8e16e-111">**Columnas de referencia disponibles**</span><span class="sxs-lookup"><span data-stu-id="8e16e-111">**Available Reference Columns**</span></span>  
 <span data-ttu-id="8e16e-112">Vea las columnas disponibles en la tabla de referencia.</span><span class="sxs-lookup"><span data-stu-id="8e16e-112">View the available columns in the reference table.</span></span> <span data-ttu-id="8e16e-113">Elija la columna que contiene la lista de términos que coincidirán.</span><span class="sxs-lookup"><span data-stu-id="8e16e-113">Choose the column that contains the list of terms to match.</span></span>  
  
 <span data-ttu-id="8e16e-114">**Columna de paso a través**</span><span class="sxs-lookup"><span data-stu-id="8e16e-114">**Pass-Through Column**</span></span>  
 <span data-ttu-id="8e16e-115">Seleccione las columnas de entrada disponibles de la lista.</span><span class="sxs-lookup"><span data-stu-id="8e16e-115">Select from the list of available input columns.</span></span> <span data-ttu-id="8e16e-116">Las selecciones se reflejan en las casillas activadas en la tabla **Columnas de entrada disponibles** .</span><span class="sxs-lookup"><span data-stu-id="8e16e-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="8e16e-117">**Alias de columna de salida**</span><span class="sxs-lookup"><span data-stu-id="8e16e-117">**Output Column Alias**</span></span>  
 <span data-ttu-id="8e16e-118">Escriba un alias para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="8e16e-118">Type an alias for each output column.</span></span> <span data-ttu-id="8e16e-119">El valor predeterminado es el nombre de la columna; no obstante, puede elegir un nombre descriptivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="8e16e-119">The default is the name of the column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="8e16e-120">**Configurar la salida de errores**</span><span class="sxs-lookup"><span data-stu-id="8e16e-120">**Configure Error Output**</span></span>  
 <span data-ttu-id="8e16e-121">Use el cuadro de diálogo [Configurar la salida de errores](../../2014/integration-services/configure-error-output.md) para especificar las opciones de control de errores de las filas que provocan errores.</span><span class="sxs-lookup"><span data-stu-id="8e16e-121">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e16e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e16e-122">See Also</span></span>  
 <span data-ttu-id="8e16e-123">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8e16e-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8e16e-124">[Editor de transformación búsqueda de términos &#40;pestaña tabla de referencia&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="8e16e-124">[Term Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 <span data-ttu-id="8e16e-125">[Editor de transformación búsqueda de términos &#40;pestaña avanzadas&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="8e16e-125">[Term Lookup Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="8e16e-126">Transformación Extracción de términos</span><span class="sxs-lookup"><span data-stu-id="8e16e-126">Term Extraction Transformation</span></span>](data-flow/transformations/term-extraction-transformation.md)  
  
  
