---
title: Editor de transformación búsqueda (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.columns.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: 690ffef5-fd59-4e95-a27d-4fcf0d6b1c0b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b768076d8acbcaef8cbff21783a7697020e027eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673099"
---
# <a name="lookup-transformation-editor-columns-page"></a><span data-ttu-id="9c5e3-102">Editor de transformación Búsqueda (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="9c5e3-102">Lookup Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="9c5e3-103">Use la página **Columnas** del cuadro de diálogo **Editor de transformación Búsqueda** para especificar la combinación entre la tabla de origen y la tabla de referencia, y para seleccionar columnas de búsqueda de la tabla de referencia.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-103">Use the **Columns** page of the **Lookup Transformation Editor** dialog box to specify the join between the source table and the reference table, and to select lookup columns from the reference table.</span></span>  
  
 <span data-ttu-id="9c5e3-104">Para obtener más información acerca de la transformación Búsqueda, vea [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="9c5e3-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9c5e3-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="9c5e3-105">Options</span></span>  
 <span data-ttu-id="9c5e3-106">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="9c5e3-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="9c5e3-107">Muestra la lista de columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-107">View the list of available input columns.</span></span> <span data-ttu-id="9c5e3-108">Las columnas de entrada son las columnas del flujo de datos de un origen conectado.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-108">The input columns are the columns in the data flow from a connected source.</span></span> <span data-ttu-id="9c5e3-109">Las columnas de entrada y la columna de búsqueda deben tener tipos de datos coincidentes.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-109">The input columns and lookup column must have matching data types.</span></span>  
  
 <span data-ttu-id="9c5e3-110">Utilice una operación de arrastrar y colocar para asignar columnas de entrada disponibles a columnas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-110">Use a drag-and-drop operation to map available input columns to lookup columns.</span></span>  
  
 <span data-ttu-id="9c5e3-111">También puede asignar columnas de entrada a columnas de búsqueda utilizando el teclado, resaltando una columna en la tabla **Columnas de entrada disponibles** , presionando la tecla de aplicación y haciendo clic en **Editar asignaciones**a continuación.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-111">You can also map input columns to lookup columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="9c5e3-112">**Columnas de búsqueda disponibles**</span><span class="sxs-lookup"><span data-stu-id="9c5e3-112">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="9c5e3-113">Muestra la lista de columnas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-113">View the list of lookup columns.</span></span> <span data-ttu-id="9c5e3-114">Las columnas de búsqueda son columnas de la tabla de referencia en las que desea buscar valores que coinciden con las columnas de entrada.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-114">The lookup columns are columns in the reference table in which you want to look up values that match the input columns.</span></span>  
  
 <span data-ttu-id="9c5e3-115">Utilice una operación de arrastrar y colocar para asignar columnas de búsqueda disponibles a columnas de entrada.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-115">Use a drag-and-drop operation to map available lookup columns to input columns.</span></span>  
  
 <span data-ttu-id="9c5e3-116">Use las casillas para seleccionar las columnas de búsqueda de la tabla de referencia en las que se realizarán operaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-116">Use the check boxes to select lookup columns in the reference table on which to perform lookup operations.</span></span>  
  
 <span data-ttu-id="9c5e3-117">También puede asignar columnas de búsqueda a columnas de entrada utilizando el teclado, resaltando una columna en la tabla **Columnas de búsqueda disponibles** , presionando la tecla de aplicación y haciendo clic en **Editar asignaciones**a continuación.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-117">You can also map lookup columns to input columns using the keyboard, by highlighting a column in the **Available Lookup Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="9c5e3-118">**columna de búsqueda**</span><span class="sxs-lookup"><span data-stu-id="9c5e3-118">**Lookup Column**</span></span>  
 <span data-ttu-id="9c5e3-119">Muestra las columnas de búsqueda seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-119">View the selected lookup columns.</span></span> <span data-ttu-id="9c5e3-120">Las selecciones se reflejan en las casillas activadas en la tabla **Columnas de búsqueda disponibles** .</span><span class="sxs-lookup"><span data-stu-id="9c5e3-120">The selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span>  
  
 <span data-ttu-id="9c5e3-121">**Operación de búsqueda**</span><span class="sxs-lookup"><span data-stu-id="9c5e3-121">**Lookup Operation**</span></span>  
 <span data-ttu-id="9c5e3-122">Seleccione una operación de búsqueda de la lista para llevar a cabo en la columna de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-122">Select a lookup operation from the list to perform on the lookup column.</span></span>  
  
 <span data-ttu-id="9c5e3-123">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="9c5e3-123">**Output Alias**</span></span>  
 <span data-ttu-id="9c5e3-124">Escriba un alias para la salida de cada columna de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-124">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="9c5e3-125">El valor predeterminado es el nombre de la columna de búsqueda; no obstante, puede elegir un nombre descriptivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="9c5e3-125">The default is the name of the lookup column; however, you can select any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c5e3-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c5e3-126">See Also</span></span>  
 <span data-ttu-id="9c5e3-127">[Editor de transformación búsqueda &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="9c5e3-127">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="9c5e3-128">[Editor de transformación búsqueda &#40;página de conexión&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="9c5e3-128">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="9c5e3-129">[Editor de transformación búsqueda &#40;página avanzadas&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="9c5e3-129">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="9c5e3-130">[Editor de transformación búsqueda &#40;página salida de error&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="9c5e3-130">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="9c5e3-131">Búsqueda aproximada, transformación</span><span class="sxs-lookup"><span data-stu-id="9c5e3-131">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
