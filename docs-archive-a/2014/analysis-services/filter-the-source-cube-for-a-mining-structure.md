---
title: Filtrar el cubo de origen para una estructura de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slice cubes [Analysis Services]
- mining structures [Analysis Services], filtering source cube
- cubes [Analysis Services], slicing
- filtering data [Analysis Services]
ms.assetid: 05dce7e1-2fe5-4500-bacf-c1a8a76e1424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61409b4803f43d3ff2634daaba65a92bc343db36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669981"
---
# <a name="filter-the-source-cube-for-a-mining-structure"></a><span data-ttu-id="d2d7c-102">Filtrar el cubo de origen para una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d2d7c-102">Filter the Source Cube for a Mining Structure</span></span>
  <span data-ttu-id="d2d7c-103">Al crear una estructura de minería de datos que se basa en los datos de un modelo multidimensional (un cubo OLAP), puede *segmentar* el cubo en el que se basa la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d2d7c-103">When you create a mining structure that is based on data in a multidimensional model (an OLAP cube), you can *slice* the cube that the mining structure is based on.</span></span> <span data-ttu-id="d2d7c-104">La segmentación permite crear subconjuntos de datos, como un tipo de filtro en los datos que se utilizan para entrenar el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d2d7c-104">Slicing lets you create subsets of data, as a kind of filter on the data that is used to train the mining model.</span></span>  
  
### <a name="to-slice-a-cube"></a><span data-ttu-id="d2d7c-105">Para segmentar un cubo</span><span class="sxs-lookup"><span data-stu-id="d2d7c-105">To slice a cube</span></span>  
  
1.  <span data-ttu-id="d2d7c-106">En el diseñador de minería de datos de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , seleccione la pestaña **estructura de minería** de datos o la pestaña **modelos de minería** de datos.</span><span class="sxs-lookup"><span data-stu-id="d2d7c-106">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], select the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="d2d7c-107">En el menú **modelo de minería de datos** , seleccione **definir segmento de cubo de estructura de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="d2d7c-107">On the **Mining Model** menu, select **Define Mining Structure Cube Slice**.</span></span>  
  
     <span data-ttu-id="d2d7c-108">Se abre el cuadro de diálogo **segmentar cubo** .</span><span class="sxs-lookup"><span data-stu-id="d2d7c-108">The **Slice Cube** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="d2d7c-109">En la columna **dimensión** del cuadro de diálogo **segmentar el cubo** , seleccione la dimensión que desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="d2d7c-109">In the **Dimension** column of the **Slice Cube** dialog box, select the dimension that you want to filter.</span></span>  
  
4.  <span data-ttu-id="d2d7c-110">Seleccione un nivel de una jerarquía mediante la lista de la columna **jerarquía** .</span><span class="sxs-lookup"><span data-stu-id="d2d7c-110">Select a level of a hierarchy, using the list in the **Hierarchy** column.</span></span>  
  
5.  <span data-ttu-id="d2d7c-111">Seleccione un operador en la lista de la columna **operador** para usarlo en la creación de la condición de filtro.</span><span class="sxs-lookup"><span data-stu-id="d2d7c-111">Select an operator from the list in the **Operator** column, to use in building the filter condition.</span></span>  
  
6.  <span data-ttu-id="d2d7c-112">Haga clic en el cuadro de la columna **filtro** .</span><span class="sxs-lookup"><span data-stu-id="d2d7c-112">Click the box in the **Filter** column.</span></span>  
  
     <span data-ttu-id="d2d7c-113">Se abre un cuadro de diálogo que contiene todos los miembros del nivel especificado de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="d2d7c-113">A dialog box opens that contains all the members at the specified level of the hierarchy.</span></span>  
  
7.  <span data-ttu-id="d2d7c-114">Seleccione el miembro o los miembros en los que desee filtrar.</span><span class="sxs-lookup"><span data-stu-id="d2d7c-114">Select the member or members on which you want to filter.</span></span>  
  
8.  <span data-ttu-id="d2d7c-115">Haga clic en **Aceptar** en el cuadro de diálogo miembro.</span><span class="sxs-lookup"><span data-stu-id="d2d7c-115">Click **OK** in the member dialog box.</span></span>  
  
9. <span data-ttu-id="d2d7c-116">Haga clic en **Aceptar** en el cuadro de diálogo **segmentar cubo** .</span><span class="sxs-lookup"><span data-stu-id="d2d7c-116">Click **OK** in the **Slice Cube** dialog box.</span></span>  
  
     <span data-ttu-id="d2d7c-117">El cubo de origen se filtrará tal y como define el segmento del cubo.</span><span class="sxs-lookup"><span data-stu-id="d2d7c-117">The source cube is now filtered as defined by the cube slice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d7c-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2d7c-118">See Also</span></span>  
 <span data-ttu-id="d2d7c-119">[Tareas y procedimientos de la estructura de minería de datos](data-mining/mining-structure-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="d2d7c-119">[Mining Structure Tasks and How-tos](data-mining/mining-structure-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="d2d7c-120">Crear una estructura de minería de datos OLAP</span><span class="sxs-lookup"><span data-stu-id="d2d7c-120">Create a New OLAP Mining Structure</span></span>](data-mining/create-a-new-olap-mining-structure.md)  
  
  
