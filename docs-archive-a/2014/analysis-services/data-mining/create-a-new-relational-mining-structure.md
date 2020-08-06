---
title: Crear una nueva estructura de minería de datos relacional | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], relational
- mining structures [Analysis Services], creating
- relational mining models [Analysis Services]
ms.assetid: 55bac3bd-700e-4f91-bcc6-f3cd8c026da1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b41dd3ac2e6144011c1b3acde27c4b5829a1661
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663802"
---
# <a name="create-a-new-relational-mining-structure"></a><span data-ttu-id="927d3-102">Crear una estructura de minería de datos relacional</span><span class="sxs-lookup"><span data-stu-id="927d3-102">Create a New Relational Mining Structure</span></span>
  <span data-ttu-id="927d3-103">Utilice el Asistente para minería de datos para crear una nueva estructura de minería de datos, utilizando los datos de una base de datos relacional u otro origen, y guarde la estructura y los modelos relacionados en una base de datos [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="927d3-103">Use the Data Mining Wizard to create a new mining structure, using data from a relational database or other source, and then save the structure and any related models to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="to-create-a-relational-mining-structure"></a><span data-ttu-id="927d3-104">Para crear una estructura de minería de datos relacional</span><span class="sxs-lookup"><span data-stu-id="927d3-104">To create a relational mining structure</span></span>  
  
1.  <span data-ttu-id="927d3-105">En el Explorador de soluciones, haga clic con el botón derecho en la carpeta **Estructuras de minería de datos** en un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y, después, haga clic en **Nueva estructura de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="927d3-105">In Solution Explorer, right-click the **Mining Structures** folder in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then click **New Mining Structure**.</span></span>  
  
     <span data-ttu-id="927d3-106">Se abrirá el Asistente para minería de datos.</span><span class="sxs-lookup"><span data-stu-id="927d3-106">The Data Mining Wizard opens.</span></span>  
  
2.  <span data-ttu-id="927d3-107">En la página de inicio del **Asistente para minería de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="927d3-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="927d3-108">En la página **Seleccionar el método de definición** , seleccione **A partir de una base de datos relacional o un almacenamiento de datos**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="927d3-108">On the **Select the Definition Method** page, select **From existing relational database or data warehouse**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="927d3-109">En la página **Seleccionar la técnica de minería de datos** , seleccione el algoritmo de minería de datos que desee utilizar y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="927d3-109">On the **Select the Data Mining Technique** page, select the data mining algorithm that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="927d3-110">Para más información sobre los algoritmos de minería de datos, vea [Algoritmos de minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="927d3-110">For more information about data mining algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
5.  <span data-ttu-id="927d3-111">En la página **Seleccionar vista del origen de datos** , en **Vistas del origen de datos disponibles**, haga clic en la vista del origen de datos que desee utilizar y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="927d3-111">On the **Select Data Source View** page, under **Available data source views**, click the data source view that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="927d3-112">Para más información sobre cómo crear una vista del origen de datos, vea [Vistas del origen de datos en modelos multidimensionales](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="927d3-112">For more information about creating a data source view, see [Data Source Views in Multidimensional Models](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
6.  <span data-ttu-id="927d3-113">En la página **Especificar tipos de tablas** , en **Tablas de entrada**, seleccione una tabla de casos y una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="927d3-113">On the **Specify Table Types** page, under **Input tables**, select a case table and a nested table.</span></span>  
  
7.  <span data-ttu-id="927d3-114">En la página **Especificar los datos de entrenamiento** , en **Estructura del modelo de minería de datos**, seleccione las columnas clave, de entrada y de predicción.</span><span class="sxs-lookup"><span data-stu-id="927d3-114">On the **Specify the Training Data** page, under **Mining model structure**, select the key, input, and predictable columns.</span></span>  
  
     <span data-ttu-id="927d3-115">Después de seleccionar la columna de predicción, puede hacer clic en el botón **Sugerir** para abrir el cuadro de diálogo **Sugerir columnas relacionadas** .</span><span class="sxs-lookup"><span data-stu-id="927d3-115">After you select the predictable column, you can click the **Suggest** button to open the **Suggest Related Columns** dialog box.</span></span> <span data-ttu-id="927d3-116">Para aceptar las columnas sugeridas, haga clic en **Aceptar** en este cuadro de diálogo para incluir las columnas seleccionadas en la estructura de minería de datos, o cambie primero las selecciones de la columna **Entrada** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="927d3-116">You can accept the suggested columns by clicking **OK** in this dialog box to include the selected columns in the mining structure, or you can change the selections in the **Input** column first, and then click **OK**.</span></span> <span data-ttu-id="927d3-117">Para hacer caso omiso de las sugerencias, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="927d3-117">To ignore the suggestions, click **Cancel**.</span></span>  
  
8.  <span data-ttu-id="927d3-118">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="927d3-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="927d3-119">En la página **Especificar el contenido y el tipo de datos de las columnas** , en **Estructura del modelo de minería de datos**, puede ajustar el tipo de contenido y el tipo de datos de cada columna.</span><span class="sxs-lookup"><span data-stu-id="927d3-119">On the **Specify Columns' Content and Data Type** page, under **Mining model structure**, you can adjust the content type and data type for each column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="927d3-120">Puede hacer clic en **Detectar** para detectar automáticamente si una columna contiene datos continuos o discretos.</span><span class="sxs-lookup"><span data-stu-id="927d3-120">You can click **Detect** to automatically detect whether a column contains continuous or discrete data.</span></span> <span data-ttu-id="927d3-121">Después de hacer clic en este botón, el contenido de la columna y los tipos de datos se actualizarán en las columnas **Tipo de contenido** y **Tipo de datos** .</span><span class="sxs-lookup"><span data-stu-id="927d3-121">After you click this button, the column content and data types will be updated in the **Content Type** and **Data Type** columns.</span></span> <span data-ttu-id="927d3-122">Para más información sobre tipos de contenido y tipos de datos, vea [Tipos de contenido &#40;minería de datos&#41;](content-types-data-mining.md) y [Tipos de datos &#40;minería de datos&#41;](data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="927d3-122">For more information about content types and data types, see [Content Types &#40;Data Mining&#41;](content-types-data-mining.md) and [Data Types &#40;Data Mining&#41;](data-types-data-mining.md).</span></span>  
  
10. <span data-ttu-id="927d3-123">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="927d3-123">Click **Next**.</span></span>  
  
11. <span data-ttu-id="927d3-124">En la página **Finalización del asistente** , asigne un nombre a la estructura de minería de datos y al modelo de minería de datos inicial relacionado que se creará y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="927d3-124">On the **Completing the Wizard** page, provide a name for the mining structure and the related initial mining model that will be created, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="927d3-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="927d3-125">See Also</span></span>  
 [<span data-ttu-id="927d3-126">Tareas y procedimientos de las estructuras de minería de datos</span><span class="sxs-lookup"><span data-stu-id="927d3-126">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
