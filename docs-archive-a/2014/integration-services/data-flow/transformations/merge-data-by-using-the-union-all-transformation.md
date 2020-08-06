---
title: Combinar datos mediante la transformación Unión de todo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- merging datasets [Integration Services]
- merging inputs [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 78304403-a81c-4101-b87e-ec80ddfdac98
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e782a5770ab9936e4c5cc84da706a5472ecd4d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676087"
---
# <a name="merge-data-by-using-the-union-all-transformation"></a><span data-ttu-id="9d8c0-102">Combinar datos mediante la transformación Unión de todo</span><span class="sxs-lookup"><span data-stu-id="9d8c0-102">Merge Data by Using the Union All Transformation</span></span>
  <span data-ttu-id="9d8c0-103">Para agregar y configurar una transformación Unión de todo, el paquete ya debe incluir al menos una tarea Flujo de datos y dos orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-103">To add and configure a Union All transformation, the package must already include at least one Data Flow task and two data sources.</span></span>  
  
 <span data-ttu-id="9d8c0-104">La transformación Unión de todo combina varias entradas.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-104">The Union All transformation combines multiple inputs.</span></span> <span data-ttu-id="9d8c0-105">La primera entrada que se conecta con la transformación es la entrada de referencia y las entradas conectadas posteriormente son las entradas secundarias.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-105">The first input that is connected to the transformation is the reference input, and the inputs connected subsequently are the secondary inputs.</span></span> <span data-ttu-id="9d8c0-106">La salida incluye las columnas en la entrada de referencia.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-106">The output includes the columns in the reference input.</span></span>  
  
### <a name="to-combine-inputs-in-a-data-flow"></a><span data-ttu-id="9d8c0-107">Para combinar entradas en un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="9d8c0-107">To combine inputs in a data flow</span></span>  
  
1.  <span data-ttu-id="9d8c0-108">En [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], haga doble clic en el paquete del Explorador de soluciones para abrir el paquete en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] y, después, haga clic en la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="9d8c0-108">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], double-click the package in Solution Explorer to open the package in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and then click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="9d8c0-109">Desde el **cuadro de herramientas**, arrastre la transformación Unión de todo a la superficie de diseño de la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="9d8c0-109">From the **Toolbox**, drag the Union All transformation to the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="9d8c0-110">Conecte la transformación Unión de todo al flujo de datos arrastrando un conector desde el origen de datos o una transformación anterior a la transformación Unión de todo.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-110">Connect the Union All transformation to the data flow by dragging a connector from the data source or a previous transformation to the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="9d8c0-111">Haga doble clic en la transformación Unión de todo.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-111">Double-click the Union All transformation.</span></span>  
  
5.  <span data-ttu-id="9d8c0-112">En el **Editor de transformación Unión de todo**, asigne una columna de una entrada a una columna en la lista **Nombre de la columna de salida** haciendo clic en una fila y luego seleccionando una columna en la lista de entrada.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-112">In the **Union All Transformation Editor**, map a column from an input to a column in the **Output Column Name** list by clicking a row and then selecting a column in the input list.</span></span> <span data-ttu-id="9d8c0-113">Seleccione **\<ignore>** en la lista de entrada para omitir la asignación de la columna.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-113">Select **\<ignore>** in the input list to skip mapping the column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d8c0-114">La asignación entre dos columnas requiere que los metadatos de las columnas coincidan.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-114">The mapping between two columns requires that the metadata of the columns match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d8c0-115">Las columnas en una entrada secundaria que no se asignan a las columnas de referencia se establecen con valores NULL en la salida.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-115">Columns in a secondary input that are not mapped to reference columns are set to null values in the output.</span></span>  
  
6.  <span data-ttu-id="9d8c0-116">Opcionalmente, modifique los nombres de las columnas en la columna **Nombre de la columna de salida** .</span><span class="sxs-lookup"><span data-stu-id="9d8c0-116">Optionally, modify the names of columns in the **Output Column Name** column.</span></span>  
  
7.  <span data-ttu-id="9d8c0-117">Repita los pasos 5 y 6 para cada columna en cada entrada.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-117">Repeat steps 5 and 6 for each column in each input.</span></span>  
  
8.  <span data-ttu-id="9d8c0-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="9d8c0-119">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="9d8c0-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d8c0-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d8c0-120">See Also</span></span>  
 <span data-ttu-id="9d8c0-121">[Transformación Unión de todo](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="9d8c0-121">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="9d8c0-122">[Transformaciones de Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="9d8c0-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="9d8c0-123">[Rutas de Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="9d8c0-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="9d8c0-124">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="9d8c0-124">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
