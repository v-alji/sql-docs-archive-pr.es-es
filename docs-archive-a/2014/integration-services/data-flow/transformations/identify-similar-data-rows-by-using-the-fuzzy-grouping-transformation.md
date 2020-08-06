---
title: Identificar filas de datos similares mediante la transformación Agrupación aproximada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Fuzzy Grouping transformation
- match similar data [Integration Services]
- similar data rows [Integration Services]
- fuzzy matches
ms.assetid: ffcb41a6-e23d-49ea-8c32-ac980e3dc495
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4e6d49548c211b38a35d6f5f7efc3d50fec93588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676100"
---
# <a name="identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation"></a><span data-ttu-id="36125-102">Identificar filas de datos similares mediante la transformación Agrupación aproximada</span><span class="sxs-lookup"><span data-stu-id="36125-102">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>
  <span data-ttu-id="36125-103">Para agregar y configurar una transformación Agrupación aproximada, el paquete ya debe incluir por lo menos una tarea Flujo de datos y un origen.</span><span class="sxs-lookup"><span data-stu-id="36125-103">To add and configure a Fuzzy Grouping transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-implement-fuzzy-grouping-transformation-in-a-data-flow"></a><span data-ttu-id="36125-104">Para implementar la transformación Agrupación aproximada en un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="36125-104">To implement Fuzzy Grouping transformation in a data flow</span></span>  
  
1.  <span data-ttu-id="36125-105">En [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="36125-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="36125-106">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="36125-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="36125-107">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre la transformación Agrupación aproximada a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="36125-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Fuzzy Grouping transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="36125-108">Conecte la transformación Agrupación aproximada al flujo de datos arrastrando el conector desde el origen de datos o una transformación anterior a la transformación Agrupación aproximada.</span><span class="sxs-lookup"><span data-stu-id="36125-108">Connect the Fuzzy Grouping transformation to the data flow by dragging the connector from the data source or a previous transformation to the Fuzzy Grouping transformation.</span></span>  
  
5.  <span data-ttu-id="36125-109">Haga doble clic en la transformación Agrupación aproximada.</span><span class="sxs-lookup"><span data-stu-id="36125-109">Double-click the Fuzzy Grouping transformation.</span></span>  
  
6.  <span data-ttu-id="36125-110">En el cuadro de diálogo **Editor de transformación Agrupación aproximada** , en la pestaña **Administrador de conexiones** , seleccione un administrador de conexiones OLE DB que se conecte con una base de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36125-110">In the **Fuzzy Grouping Transformation Editor** dialog box, on the **Connection Manager** tab, select an OLE DB connection manager that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="36125-111">La transformación requiere una conexión a una base de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para crear tablas e índices temporales.</span><span class="sxs-lookup"><span data-stu-id="36125-111">The transformation requires a connection to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database to create temporary tables and indexes.</span></span>  
  
7.  <span data-ttu-id="36125-112">Haga clic en la pestaña **Columnas** y en la lista **Columnas de entrada disponibles** , active la casilla de las columnas de entrada que se deben usar para identificar filas similares en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="36125-112">Click the **Columns** tab and, in the **Available Input Columns** list, select the check box of the input columns to use to identify similar rows in the dataset.</span></span>  
  
8.  <span data-ttu-id="36125-113">Active la casilla de la columna **Paso a través** para identificar las columnas de entrada que pasan a través de la salida de transformación.</span><span class="sxs-lookup"><span data-stu-id="36125-113">Select the check box in the **Pass Through** column to identify the input columns to pass through to the transformation output.</span></span> <span data-ttu-id="36125-114">Las columnas de paso a través no se incluyen en el proceso de identificación de filas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="36125-114">Pass-through columns are not included in the process of identification of duplicate rows.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="36125-115">Las columnas de entrada que se usan para agrupar se seleccionan automáticamente como columnas de paso a través, y no se puede eliminar su selección mientras se usan para la agrupación.</span><span class="sxs-lookup"><span data-stu-id="36125-115">Input columns that are used for grouping are automatically selected as pass-through columns, and they cannot be unselected while used for grouping.</span></span>  
  
9. <span data-ttu-id="36125-116">Opcionalmente, actualice los nombres de las columnas de salida en la columna **Alias de salida** .</span><span class="sxs-lookup"><span data-stu-id="36125-116">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="36125-117">También puede actualizar los nombres de las columnas limpias en la columna **Alias de salida de grupo** .</span><span class="sxs-lookup"><span data-stu-id="36125-117">Optionally, update the names of cleaned columns in the **Group OutputAlias** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="36125-118">Los nombres predeterminados de las columnas son los nombres de las columnas de entrada con el sufijo "_clean".</span><span class="sxs-lookup"><span data-stu-id="36125-118">The default names of columns are the names of the input columns with a "_clean" suffix.</span></span>  
  
11. <span data-ttu-id="36125-119">Opcionalmente, actualice el tipo de coincidencia que se debe usar en la columna **Tipo de coincidencia** .</span><span class="sxs-lookup"><span data-stu-id="36125-119">Optionally, update the type of match to use in the **Match Type** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="36125-120">Al menos una columna debe usar coincidencia aproximada.</span><span class="sxs-lookup"><span data-stu-id="36125-120">At least one column must use fuzzy matching.</span></span>  
  
12. <span data-ttu-id="36125-121">Especifique las columnas de nivel de similitud mínima en la columna **Similitud mínima** .</span><span class="sxs-lookup"><span data-stu-id="36125-121">Specify the minimum similarity level columns in the **Minimum Similarity** column.</span></span> <span data-ttu-id="36125-122">El valor debe estar entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="36125-122">The value must be between 0 and 1.</span></span> <span data-ttu-id="36125-123">Cuanto más cercano sea el valor a 1, más similares deberán ser los valores en las columnas de entrada para formar un grupo.</span><span class="sxs-lookup"><span data-stu-id="36125-123">The closer the value is to 1, the more similar the values in the input columns must be to form a group.</span></span> <span data-ttu-id="36125-124">Una similitud mínima de 1 indica una coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="36125-124">A minimum similarity of 1 indicates an exact match.</span></span>  
  
13. <span data-ttu-id="36125-125">Opcionalmente, actualice los nombres de las columnas de similitud en la columna **Alias de salida de similitud** .</span><span class="sxs-lookup"><span data-stu-id="36125-125">Optionally, update the names of similarity columns in the **Similarity Output Alias** column.</span></span>  
  
14. <span data-ttu-id="36125-126">Para especificar el manejo de números en valores de datos, actualice los valores en la columna **Números** .</span><span class="sxs-lookup"><span data-stu-id="36125-126">To specify the handling of numbers in data values, update the values in the **Numerals** column.</span></span>  
  
15. <span data-ttu-id="36125-127">Para especificar la manera en que la transformación compara los datos de cadenas en una columna, modifique la selección predeterminada de las opciones de comparación en la columna **Marcas de comparación** .</span><span class="sxs-lookup"><span data-stu-id="36125-127">To specify how the transformation compares the string data in a column, modify the default selection of comparison options in the **Comparison Flags** column.</span></span>  
  
16. <span data-ttu-id="36125-128">Haga clic en la pestaña **Avanzadas** para modificar los nombres de las columnas que la transformación agrega a la salida para el identificador de filas únicas (_key_in), el identificador de filas duplicadas (_key_out) y el valor de similitud (_score).</span><span class="sxs-lookup"><span data-stu-id="36125-128">Click the **Advanced** tab to modify the names of the columns that the transformation adds to the output for the unique row identifier (_key_in), the duplicate row identifier (_key_out), and the similarity value (_score).</span></span>  
  
17. <span data-ttu-id="36125-129">Opcionalmente, ajuste el umbral de similitud moviendo la barra del control deslizante.</span><span class="sxs-lookup"><span data-stu-id="36125-129">Optionally, adjust the similarity threshold by moving the slider bar.</span></span>  
  
18. <span data-ttu-id="36125-130">También puede desactivar las casillas de delimitadores de token para omitir los delimitadores en los datos.</span><span class="sxs-lookup"><span data-stu-id="36125-130">Optionally, clear the token delimiter check boxes to ignore delimiters in the data.</span></span>  
  
19. <span data-ttu-id="36125-131">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="36125-131">Click **OK**.</span></span>  
  
20. <span data-ttu-id="36125-132">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="36125-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36125-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36125-133">See Also</span></span>  
 <span data-ttu-id="36125-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="36125-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span></span>  
 <span data-ttu-id="36125-135">[Transformaciones de Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="36125-135">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="36125-136">[Rutas de Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="36125-136">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="36125-137">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="36125-137">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
