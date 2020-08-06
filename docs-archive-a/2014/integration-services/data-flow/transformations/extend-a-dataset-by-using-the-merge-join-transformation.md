---
title: Ampliar un conjunto de datos con la transformación Combinación de mezcla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Merge Join transformation
- datasets [Integration Services], joining
- datasets [Integration Services], extending
- joining datasets [Integration Services]
ms.assetid: 9e512c3c-f89b-45f3-8281-cdb8f35a2b1f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a387c4ad840eb739d36023be9323c063dcb9a68e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669774"
---
# <a name="extend-a-dataset-by-using-the-merge-join-transformation"></a><span data-ttu-id="66874-102">Ampliar un conjunto de datos con la transformación Combinación de mezcla</span><span class="sxs-lookup"><span data-stu-id="66874-102">Extend a Dataset by Using the Merge Join Transformation</span></span>
  <span data-ttu-id="66874-103">Para agregar y configurar una transformación Combinación de mezcla, el paquete ya debe incluir por lo menos una tarea Flujo de datos y dos componentes de flujo de datos que proporcionen entradas a la transformación Combinación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="66874-103">To add and configure a Merge Join transformation, the package must already include at least one Data Flow task and two data flow components that provide inputs to the Merge Join transformation.</span></span>  
  
 <span data-ttu-id="66874-104">La transformación Combinación de mezcla requiere dos entradas ordenadas.</span><span class="sxs-lookup"><span data-stu-id="66874-104">The Merge Join transformation requires two sorted inputs.</span></span> <span data-ttu-id="66874-105">Para obtener más información, vea [Ordenar datos para las transformaciones Mezclar y Combinación de mezcla](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="66874-105">For more information, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
### <a name="to-extend-a-dataset"></a><span data-ttu-id="66874-106">Para ampliar un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="66874-106">To extend a dataset</span></span>  
  
1.  <span data-ttu-id="66874-107">En [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="66874-107">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="66874-108">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="66874-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="66874-109">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre la transformación Combinación de mezcla a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="66874-109">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Merge Join transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="66874-110">Conecte la transformación Combinación de mezcla con el flujo de datos arrastrando el conector desde un origen de datos o una transformación anterior a la transformación Combinación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="66874-110">Connect the Merge Join transformation to the data flow by dragging the connector from a data source or a previous transformation to the Merge Join transformation.</span></span>  
  
5.  <span data-ttu-id="66874-111">Haga doble clic en la transformación Combinación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="66874-111">Double-click the Merge Join transformation.</span></span>  
  
6.  <span data-ttu-id="66874-112">En el cuadro de diálogo **Editor de transformación Combinación de mezcla** , seleccione el tipo de combinación que se debe usar en la lista **Tipo de combinación** .</span><span class="sxs-lookup"><span data-stu-id="66874-112">In the **Merge Join Transformation Editor** dialog box, select the type of join to use in the **Join type** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="66874-113">Si selecciona el tipo **Combinación externa izquierda** , puede hacer clic en **Intercambiar entradas** para intercambiar las entradas y convertir la combinación externa izquierda en una combinación externa derecha.</span><span class="sxs-lookup"><span data-stu-id="66874-113">If you select the **Left outer join** type, you can click **Swap Inputs** to switch the inputs and convert the left outer join to a right outer join.</span></span>  
  
7.  <span data-ttu-id="66874-114">Arrastre las columnas de la entrada izquierda a las columnas de la entrada derecha para especificar las columnas de combinación.</span><span class="sxs-lookup"><span data-stu-id="66874-114">Drag columns in the left input to columns in the right input to specify the join columns.</span></span> <span data-ttu-id="66874-115">Si las columnas tienen el mismo nombre, puede activar la casilla **Clave de combinación** y la transformación Combinación de mezcla automáticamente crea la combinación.</span><span class="sxs-lookup"><span data-stu-id="66874-115">If the columns have the same name, you can select the **Join Key** check box and the Merge Join transformation automatically creates the join.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="66874-116">Se pueden crear combinaciones solo entre columnas que tengan la misma posición de ordenación y las combinaciones se deben crear en el orden especificado por la posición de ordenación.</span><span class="sxs-lookup"><span data-stu-id="66874-116">You can create joins only between columns that have the same sort position, and the joins must be created in the order specified by the sort position.</span></span> <span data-ttu-id="66874-117">Si intenta crear las combinaciones no ordenadas, el **Editor de transformación Combinación de mezcla** le indica que debe crear combinaciones adicionales para las posiciones de ordenación omitidas.</span><span class="sxs-lookup"><span data-stu-id="66874-117">If you attempt to create the joins out of order, the **Merge Join Transformation Editor** prompts you to create additional joins for the skipped sort order positions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="66874-118">Como opción predeterminada, la salida se ordena en las columnas de combinación.</span><span class="sxs-lookup"><span data-stu-id="66874-118">By default, the output is sorted on the join columns.</span></span>  
  
8.  <span data-ttu-id="66874-119">En las entradas derecha e izquierda, active las casillas de columnas adicionales que se deben incluir en la salida.</span><span class="sxs-lookup"><span data-stu-id="66874-119">In the left and right inputs, select the check boxes of additional columns to include in the output.</span></span> <span data-ttu-id="66874-120">Las columnas de combinación se incluyen como opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="66874-120">Join columns are included by default.</span></span>  
  
9. <span data-ttu-id="66874-121">Opcionalmente, actualice los nombres de las columnas de salida en la columna **Alias de salida** .</span><span class="sxs-lookup"><span data-stu-id="66874-121">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="66874-122">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="66874-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="66874-123">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="66874-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66874-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66874-124">See Also</span></span>  
 <span data-ttu-id="66874-125">[Transformación Combinación de mezcla](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="66874-125">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="66874-126">[Transformaciones de Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="66874-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="66874-127">[Rutas de Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="66874-127">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="66874-128">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="66874-128">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
