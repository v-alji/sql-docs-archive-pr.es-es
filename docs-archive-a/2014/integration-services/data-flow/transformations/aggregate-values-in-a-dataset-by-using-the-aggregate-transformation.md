---
title: Agregar valores en un conjunto de datos mediante la transformación Agregado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Aggregate transformation [Integration Services]
- aggregate values [Integration Services]
- datasets [Integration Services], aggregate values
ms.assetid: 01b81c0f-d5e0-483b-81b2-73800a6945ac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de918c6c2adf194d5808ccd1b64c77a94a52e357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744220"
---
# <a name="aggregate-values-in-a-dataset-by-using-the-aggregate-transformation"></a><span data-ttu-id="1fd75-102">Agregar valores en un conjunto de datos mediante la transformación Agregado</span><span class="sxs-lookup"><span data-stu-id="1fd75-102">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>
  <span data-ttu-id="1fd75-103">Para agregar y configurar una transformación Agregado, el paquete ya debe incluir por lo menos una tarea Flujo de datos y un origen.</span><span class="sxs-lookup"><span data-stu-id="1fd75-103">To add and configure an Aggregate transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-aggregate-values-in-a-dataset"></a><span data-ttu-id="1fd75-104">Para agregar valores en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="1fd75-104">To aggregate values in a dataset</span></span>  
  
1.  <span data-ttu-id="1fd75-105">En [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="1fd75-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="1fd75-106">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="1fd75-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="1fd75-107">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **Cuadro de herramientas**, arrastre la transformación Agregado a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="1fd75-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Aggregate transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="1fd75-108">Conecte la transformación Agregado al flujo de datos arrastrando el conector desde un origen o una transformación anterior a la transformación Agregado.</span><span class="sxs-lookup"><span data-stu-id="1fd75-108">Connect the Aggregate transformation to the data flow by dragging a connector from the source or the previous transformation to the Aggregate transformation.</span></span>  
  
5.  <span data-ttu-id="1fd75-109">Haga doble clic en la transformación.</span><span class="sxs-lookup"><span data-stu-id="1fd75-109">Double-click the transformation.</span></span>  
  
6.  <span data-ttu-id="1fd75-110">En el cuadro de diálogo **Editor de transformación Agregado** , haga clic en la pestaña **Agregaciones** .</span><span class="sxs-lookup"><span data-stu-id="1fd75-110">In the **Aggregate Transformation Editor** dialog box, click the **Aggregations** tab.</span></span>  
  
7.  <span data-ttu-id="1fd75-111">En la lista **Columnas de entrada disponibles** , active la casilla situada junto a las columnas en las que desea agregar valores.</span><span class="sxs-lookup"><span data-stu-id="1fd75-111">In the **Available Input Columns** list, select the check box by the columns on which you want to aggregate values.</span></span> <span data-ttu-id="1fd75-112">Las columnas seleccionadas aparecen en la tabla.</span><span class="sxs-lookup"><span data-stu-id="1fd75-112">The selected columns appear in the table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fd75-113">Puede seleccionar una columna muchas veces, aplicando varias transformaciones a la columna.</span><span class="sxs-lookup"><span data-stu-id="1fd75-113">You can select a column multiple times, applying multiple transformations to the column.</span></span> <span data-ttu-id="1fd75-114">Para identificar de manera exclusiva las agregaciones, se anexa un número al nombre predeterminado del alias de salida de la columna.</span><span class="sxs-lookup"><span data-stu-id="1fd75-114">To uniquely identify aggregations, a number is appended to the default name of the output alias of the column.</span></span>  
  
8.  <span data-ttu-id="1fd75-115">Opcionalmente, modifique el valor en las columnas **Alias de salida** .</span><span class="sxs-lookup"><span data-stu-id="1fd75-115">Optionally, modify the value in the **Output Alias** columns.</span></span>  
  
9. <span data-ttu-id="1fd75-116">Para cambiar la operación de agregación predeterminada, **GROUP BY**, seleccione otra operación en la lista **Operación** .</span><span class="sxs-lookup"><span data-stu-id="1fd75-116">To change the default aggregation operation, **Group by**, select a different operation in the **Operation** list.</span></span>  
  
10. <span data-ttu-id="1fd75-117">Para cambiar la comparación predeterminada, seleccione las marcas de comparación individuales enumeradas en la columna **Marcas de comparación** .</span><span class="sxs-lookup"><span data-stu-id="1fd75-117">To change the default comparison, select the individual comparison flags listed in the **Comparison Flags** column.</span></span> <span data-ttu-id="1fd75-118">De forma predeterminada, una comparación omite la distinción entre mayúsculas y minúsculas, el tipo de kana, los caracteres sin espacio y el ancho de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1fd75-118">By default, a comparison ignores case, kana type, non-spacing characters, and character width.</span></span>  
  
11. <span data-ttu-id="1fd75-119">Opcionalmente, para la agregación **Count distinct** , especifique un número exacto de valores distintos en la columna **Claves Count Distinct** , o seleccione un recuento aproximado en la columna **Escala Count Distinct** .</span><span class="sxs-lookup"><span data-stu-id="1fd75-119">Optionally, for the **Count distinct** aggregation, specify an exact number of distinct values in the **Count Distinct Keys** column, or select an approximate count in the **Count Distinct Scale** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fd75-120">Al proporcionar el número de valores distintos, sea exacto o aproximado, se optimiza el rendimiento, dado que la transformación puede asignar previamente una cantidad apropiada de memoria para realizar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="1fd75-120">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
12. <span data-ttu-id="1fd75-121">Opcionalmente, haga clic en **Avanzado** y actualice el nombre de la salida de transformación Agregado.</span><span class="sxs-lookup"><span data-stu-id="1fd75-121">Optionally, click **Advanced** and update the name of the Aggregate transformation output.</span></span> <span data-ttu-id="1fd75-122">Si las agregaciones incluyen una `Group By` operación, puede seleccionar un recuento aproximado de los valores de clave de agrupación en la columna **escala de claves** o especificar un número exacto de valores de clave de agrupación en la columna **claves** .</span><span class="sxs-lookup"><span data-stu-id="1fd75-122">If the aggregations include a `Group By` operation, you can select an approximate count of grouping key values in the **Keys Scale** column or specify an exact number of grouping key values in the **Keys** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fd75-123">Al proporcionar el número de valores distintos, sea exacto o aproximado, se optimiza el rendimiento, dado que la transformación puede asignar previamente una cantidad apropiada de memoria para realizar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="1fd75-123">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fd75-124">Las opciones **Escala de claves** y **Claves** se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="1fd75-124">The **Keys Scale** and **Keys** options are mutually exclusive.</span></span> <span data-ttu-id="1fd75-125">Si escribe valores en ambas columnas, se utiliza el valor más grande en **Escala de claves** o en **Claves** .</span><span class="sxs-lookup"><span data-stu-id="1fd75-125">If you enter values in both columns, the larger value in either **Keys Scale** or **Keys** is used.</span></span>  
  
13. <span data-ttu-id="1fd75-126">También puede hacer clic en la pestaña **Avanzado** y establecer los atributos que se aplican a la optimización de todas las operaciones que realiza la transformación Agregado.</span><span class="sxs-lookup"><span data-stu-id="1fd75-126">Optionally, click the **Advanced** tab and set the attributes that apply to optimizing all the operations that the Aggregate transformation performs.</span></span>  
  
14. <span data-ttu-id="1fd75-127">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="1fd75-127">Click **OK**.</span></span>  
  
15. <span data-ttu-id="1fd75-128">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="1fd75-128">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fd75-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1fd75-129">See Also</span></span>  
 <span data-ttu-id="1fd75-130">[Transformación Agregado](aggregate-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="1fd75-130">[Aggregate Transformation](aggregate-transformation.md) </span></span>  
 <span data-ttu-id="1fd75-131">[Transformaciones de Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="1fd75-131">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="1fd75-132">[Rutas de Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="1fd75-132">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="1fd75-133">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="1fd75-133">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
