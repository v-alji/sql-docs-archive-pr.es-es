---
title: Crear una dimensión de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], dimensions
ms.assetid: 9f0c39e5-3516-43ab-b203-f3f6dbcff89a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 265cf671bbc825258f0b2bd6627690e8c52f252b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743695"
---
# <a name="create-a-data-mining-dimension"></a><span data-ttu-id="524d4-102">Crear una dimensión de minería de datos</span><span class="sxs-lookup"><span data-stu-id="524d4-102">Create a Data Mining Dimension</span></span>
  <span data-ttu-id="524d4-103">Si su estructura de minería de datos está basada en un cubo OLAP, puede crear una dimensión que incluya el contenido del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="524d4-103">If your mining structure is based on an OLAP cube, you can create a dimension that contains the content of the mining model.</span></span> <span data-ttu-id="524d4-104">A continuación, puede volver a incorporar la dimensión en el cubo de origen.</span><span class="sxs-lookup"><span data-stu-id="524d4-104">You can then incorporate the dimension back into the source cube.</span></span>  
  
 <span data-ttu-id="524d4-105">También puede examinar la dimensión, utilizarla para explorar los resultados del modelo o consultar la dimensión mediante MDX.</span><span class="sxs-lookup"><span data-stu-id="524d4-105">You can also browse the dimension, use it to explore the model results, or query the dimension using MDX.</span></span>  
  
### <a name="to-create-a-data-mining-dimension"></a><span data-ttu-id="524d4-106">Para crear una dimensión de minería de datos</span><span class="sxs-lookup"><span data-stu-id="524d4-106">To create a data mining dimension</span></span>  
  
1.  <span data-ttu-id="524d4-107">En el Diseñador de minería de datos de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], seleccione la pestaña **Estructura de minería de datos** o la pestaña **Modelos de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="524d4-107">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], select either the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="524d4-108">En el menú **Modelo de minería de datos** , seleccione **Crear una dimensión de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="524d4-108">From the **Mining Model** menu, select **Create a Data Mining Dimension**.</span></span>  
  
     <span data-ttu-id="524d4-109">Aparece el cuadro de diálogo **Crear una dimensión de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="524d4-109">The **Create Data Mining Dimension** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="524d4-110">En la lista **Nombre del modelo** del cuadro de diálogo **Crear una dimensión de minería de datos** , seleccione el modelo de minería de datos OLAP.</span><span class="sxs-lookup"><span data-stu-id="524d4-110">In the **Model name** list of the **Create Data Mining Dimension** dialog box, select an OLAP mining model.</span></span>  
  
4.  <span data-ttu-id="524d4-111">En el cuadro **Nombre de dimensión** , escriba el nombre de la nueva dimensión de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="524d4-111">In the **Dimension name** box, enter a name for the new data mining dimension.</span></span>  
  
5.  <span data-ttu-id="524d4-112">Si desea crear un cubo que incluya la nueva dimensión de minería de datos, seleccione **Crear cubo**.</span><span class="sxs-lookup"><span data-stu-id="524d4-112">If you want to create a cube that includes the new data mining dimension, select **Create cube**.</span></span> <span data-ttu-id="524d4-113">Después de seleccionar **Crear cubo**, puede escribir un nuevo nombre para el cubo.</span><span class="sxs-lookup"><span data-stu-id="524d4-113">After you select **Create cube**, you can enter a new name for the cube.</span></span>  
  
6.  <span data-ttu-id="524d4-114">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="524d4-114">Click **OK**.</span></span>  
  
     <span data-ttu-id="524d4-115">La dimensión de minería de datos se crea y se agrega a la carpeta **Dimensiones** del Explorador de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="524d4-115">The data mining dimension is created and is added to the **Dimensions** folder in Solution Explorer.</span></span> <span data-ttu-id="524d4-116">Si ha seleccionado **Crear cubo**, también se crea un cubo nuevo que se agrega a la carpeta **Cubos** .</span><span class="sxs-lookup"><span data-stu-id="524d4-116">If you selected **Create cube**, a new cube is also created and is added to the **Cubes** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524d4-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="524d4-117">See Also</span></span>  
 [<span data-ttu-id="524d4-118">Tareas y procedimientos de las estructuras de minería de datos</span><span class="sxs-lookup"><span data-stu-id="524d4-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
