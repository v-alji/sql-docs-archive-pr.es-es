---
title: Editor de transformación búsqueda aproximada (pestaña columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.columns.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: aaf45327-79e9-4760-9b4d-546ace91b5b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9294022b52536940916a381d7b811437eaa5814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744771"
---
# <a name="fuzzy-lookup-transformation-editor-columns-tab"></a><span data-ttu-id="bbff1-102">Editor de transformación Búsqueda aproximada (pestaña Columnas)</span><span class="sxs-lookup"><span data-stu-id="bbff1-102">Fuzzy Lookup Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="bbff1-103">Use la pestaña **Columnas** del cuadro de diálogo **Editor de transformación Búsqueda aproximada** para especificar las propiedades de las columnas de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="bbff1-103">Use the **Columns** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set properties for input and output columns.</span></span>  
  
 <span data-ttu-id="bbff1-104">Para obtener más información acerca de la transformación Búsqueda aproximada, vea [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="bbff1-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bbff1-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="bbff1-105">Options</span></span>  
 <span data-ttu-id="bbff1-106">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="bbff1-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="bbff1-107">Arrastre las columnas de entrada para conectarlas a las columnas de búsqueda disponibles.</span><span class="sxs-lookup"><span data-stu-id="bbff1-107">Drag input columns to connect them to available lookup columns.</span></span> <span data-ttu-id="bbff1-108">Las columnas deben poseer tipos de datos coincidentes y compatibles.</span><span class="sxs-lookup"><span data-stu-id="bbff1-108">These columns must have matching, supported data types.</span></span> <span data-ttu-id="bbff1-109">Seleccione una línea de asignación y haga clic con el botón derecho para editar las asignaciones en el cuadro de diálogo [Crear relaciones](data-flow/transformations/create-relationships.md) .</span><span class="sxs-lookup"><span data-stu-id="bbff1-109">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="bbff1-110">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="bbff1-110">**Name**</span></span>  
 <span data-ttu-id="bbff1-111">Muestra los nombres de las columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="bbff1-111">View the names of the available input columns.</span></span>  
  
 <span data-ttu-id="bbff1-112">**Paso a través**</span><span class="sxs-lookup"><span data-stu-id="bbff1-112">**Pass Through**</span></span>  
 <span data-ttu-id="bbff1-113">Especifique si desea incluir las columnas de entrada en la salida de transformación.</span><span class="sxs-lookup"><span data-stu-id="bbff1-113">Specify whether to include the input columns in the output of the transformation.</span></span>  
  
 <span data-ttu-id="bbff1-114">**Columnas de búsqueda disponibles**</span><span class="sxs-lookup"><span data-stu-id="bbff1-114">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="bbff1-115">Use las casillas para seleccionar las columnas en las que se realizarán operaciones de búsqueda aproximada.</span><span class="sxs-lookup"><span data-stu-id="bbff1-115">Use the check boxes to select columns on which to perform fuzzy lookup operations.</span></span>  
  
 <span data-ttu-id="bbff1-116">**columna de búsqueda**</span><span class="sxs-lookup"><span data-stu-id="bbff1-116">**Lookup Column**</span></span>  
 <span data-ttu-id="bbff1-117">Seleccione las columnas de búsqueda en la lista de columnas de tabla de referencia disponibles.</span><span class="sxs-lookup"><span data-stu-id="bbff1-117">Select lookup columns from the list of available reference table columns.</span></span> <span data-ttu-id="bbff1-118">Sus selecciones se reflejan en las casillas en la tabla **Columnas de búsqueda disponibles** .</span><span class="sxs-lookup"><span data-stu-id="bbff1-118">Your selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span> <span data-ttu-id="bbff1-119">Seleccione una columna en la tabla **Columnas de búsqueda disponibles** para crear una columna de salida que contenga el valor de la columna de la tabla de referencia para cada fila coincidente devuelta.</span><span class="sxs-lookup"><span data-stu-id="bbff1-119">Selecting a column in the **Available Lookup Columns** table creates an output column that contains the reference table column value for each matching row returned.</span></span>  
  
 <span data-ttu-id="bbff1-120">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="bbff1-120">**Output Alias**</span></span>  
 <span data-ttu-id="bbff1-121">Escriba un alias para la salida de cada columna de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bbff1-121">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="bbff1-122">El nombre predeterminado es el de la columna de búsqueda con un valor de índice numérico anexado, pero puede elegir cualquier nombre descriptivo único.</span><span class="sxs-lookup"><span data-stu-id="bbff1-122">The default is the name of the lookup column with a numeric index value appended; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbff1-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bbff1-123">See Also</span></span>  
 <span data-ttu-id="bbff1-124">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bbff1-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="bbff1-125">[Editor de transformación búsqueda aproximada &#40;pestaña tabla de referencia&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="bbff1-125">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="bbff1-126">Editor de transformación Búsqueda aproximada &#40;pestaña Avanzadas&#41;</span><span class="sxs-lookup"><span data-stu-id="bbff1-126">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
