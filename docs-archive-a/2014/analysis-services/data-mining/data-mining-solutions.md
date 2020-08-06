---
title: Soluciones de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
- data mining [Analysis Services], development
ms.assetid: 84f6548d-ebb0-4e10-9b29-66253fa0a04a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0ab4b5ddcc9958fa36d6c8ecae0e7fd79585b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671838"
---
# <a name="data-mining-solutions"></a><span data-ttu-id="f8bff-102">Soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8bff-102">Data Mining Solutions</span></span>
  <span data-ttu-id="f8bff-103">Una solución de minería de datos es una solución de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contiene uno o más proyectos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="f8bff-103">A data mining solution is an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] solution that contains one or more data mining projects.</span></span>  
  
 <span data-ttu-id="f8bff-104">En los temas de esta sección se proporciona información sobre cómo diseñar e implementar una solución de minería de datos integrada mediante [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8bff-104">The topics in this section provide information about how to design and implement an integrated data mining solution by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f8bff-105">Para obtener información general acerca del proceso de diseño de minería de datos y de las herramientas relacionadas, vea [Data Mining Concepts](data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="f8bff-105">For an overview of the data mining design process and related tools, see [Data Mining Concepts](data-mining-concepts.md).</span></span>  
  
 <span data-ttu-id="f8bff-106">Para más información sobre los tipos adicionales de proyecto que son útiles para la minería de datos, vea [Proyectos relacionados en las soluciones de minería de datos](data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="f8bff-106">For more information about additional projects types that are useful for data mining, see [Related Projects for Data Mining Solutions](data-mining-solutions.md).</span></span>  
  
 [<span data-ttu-id="f8bff-107">Soluciones relacionales y multidimensionales</span><span class="sxs-lookup"><span data-stu-id="f8bff-107">Relational vs. Multidimensional Solutions</span></span>](#bkmk_RelMD)  
  
 [<span data-ttu-id="f8bff-108">Implementar soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8bff-108">Deploying Data Mining Solutions</span></span>](#bkmk_Deploy)  
  
 [<span data-ttu-id="f8bff-109">Tutoriales de la solución</span><span class="sxs-lookup"><span data-stu-id="f8bff-109">Solution Walkthroughs</span></span>](#bkmk_Walkthru)  
  
##  <a name="relational-vs-multidimensional-solutions"></a><a name="bkmk_RelMD"></a> <span data-ttu-id="f8bff-110">Soluciones relacionales y multidimensionales</span><span class="sxs-lookup"><span data-stu-id="f8bff-110">Relational vs. Multidimensional Solutions</span></span>  
 <span data-ttu-id="f8bff-111">Una solución de minería de datos se puede basar en datos multidimensionales, es decir, en un cubo existente o en datos puramente relacionales, como las tablas y las vistas de un almacenamiento de datos, o en archivos de texto, libros de Excel u otros orígenes de datos externos.</span><span class="sxs-lookup"><span data-stu-id="f8bff-111">A data mining solution can be based either on multidimensional data-that is, an existing cube-or on purely relational data, such as the tables and views in a data warehouse, or on text files, Excel workbooks, or other external data sources.</span></span>  
  
-   <span data-ttu-id="f8bff-112">Puede crear objetos de minería de datos en una solución de base de datos multidimensional existente.</span><span class="sxs-lookup"><span data-stu-id="f8bff-112">You can create data mining objects within an existing multidimensional database solution.</span></span>  
  
     <span data-ttu-id="f8bff-113">Normalmente, se crearía una solución como esta si ya ha creado un cubo y desearía realizar la minería de datos utilizando el cubo como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f8bff-113">Typically you would create a solution like this if you have already created a cube and want to perform data mining by using the cube as a data source.</span></span> <span data-ttu-id="f8bff-114">Al mover y crear copias de seguridad de modelos basados en un cubo, el cubo también debe moverse o copiarse.</span><span class="sxs-lookup"><span data-stu-id="f8bff-114">When you move and backup models based on a cube, the cube must also be moved or copied.</span></span>  
  
-   <span data-ttu-id="f8bff-115">Puede crear una solución de minería de datos que solo contenga objetos de minería de datos, incluidos los orígenes de datos y vistas del origen de datos que admiten, y que use un origen de datos relacional solamente.</span><span class="sxs-lookup"><span data-stu-id="f8bff-115">You can create a data mining solution that contains only data mining objects, including the supporting data sources and data source views, and that uses relational data source only.</span></span>  
  
     <span data-ttu-id="f8bff-116">Este es el método preferido para crear modelos de minería de datos, dado que el procesamiento y la consulta normalmente es más rápido en orígenes de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="f8bff-116">This is the preferred method for creating data mining models, as processing and querying is generally fastest against relational data sources.</span></span> <span data-ttu-id="f8bff-117">También puede mover y hacer copia de seguridad fácilmente de los modelos entre servidores copiando los comandos EXPORT e IMPORT.</span><span class="sxs-lookup"><span data-stu-id="f8bff-117">You can also easily move and backup models between servers by using the EXPORT and IMPORT commands.</span></span>  
  
##  <a name="deploying-data-mining-solutions"></a><a name="bkmk_Deploy"></a><span data-ttu-id="f8bff-118">Implementar soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8bff-118">Deploying Data Mining Solutions</span></span>  
 <span data-ttu-id="f8bff-119">La instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en la que se implementa la solución debe ejecutarse en un modo que admita objetos multidimensionales y objetos de minería de datos; es decir, no puede implementar objetos de minería de datos en una instancia que hospede modelos tabulares o datos de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="f8bff-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="f8bff-120">Por consiguiente, al crear una solución de minería de datos en Visual Studio, asegúrese de utilizar la plantilla **Proyecto multidimensional y de minería de datos de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="f8bff-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="f8bff-121">Al implementar la solución, los objetos utilizados para la minería de datos se crean en la instancia especificada de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , en una base de datos con el mismo nombre que el archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="f8bff-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
 <span data-ttu-id="f8bff-122">Para más información sobre cómo implementar tanto soluciones multidimensionales como relacionales, vea [Implementación de soluciones de minería de datos](deployment-of-data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="f8bff-122">For more information about how to deploy both relational and multidimensional solutions, see [Deployment of Data Mining Solutions](deployment-of-data-mining-solutions.md).</span></span>  
  
##  <a name="solution-walkthrough"></a><a name="bkmk_Walkthru"></a> <span data-ttu-id="f8bff-123">Tutorial de la solución</span><span class="sxs-lookup"><span data-stu-id="f8bff-123">Solution Walkthrough</span></span>  
 <span data-ttu-id="f8bff-124">Proporciona información general sobre cómo crear soluciones de minería de datos mediante el Asistente para minería de datos.</span><span class="sxs-lookup"><span data-stu-id="f8bff-124">Provides an overview of how to create data mining solutions by using the Data Mining Wizard.</span></span>  
  
 [<span data-ttu-id="f8bff-125">Crear una estructura de minería de datos relacional</span><span class="sxs-lookup"><span data-stu-id="f8bff-125">Create a Relational Mining Structure</span></span>](create-a-relational-mining-structure.md)  
 <span data-ttu-id="f8bff-126">Crear una estructura de minería de datos relacionales, archivos de texto y otros orígenes que se pueden combinar en una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f8bff-126">Create a mining structure from relational data, text files, and other sources that can be combined in a data source view.</span></span>  
  
 [<span data-ttu-id="f8bff-127">Crear una estructura de minería de datos OLAP</span><span class="sxs-lookup"><span data-stu-id="f8bff-127">Create an OLAP Mining Structure</span></span>](create-an-olap-mining-structure.md)  
 <span data-ttu-id="f8bff-128">Crear una estructura de minería de datos basada en los datos de un cubo OLAP.</span><span class="sxs-lookup"><span data-stu-id="f8bff-128">Create a mining structure based on data in an OLAP cube.</span></span> <span data-ttu-id="f8bff-129">Los modelos que se crean a partir de datos OLAP se pueden guardar como una dimensión de minería de datos, o puede guardar el conjunto de datos y sus modelos como un cubo nuevo.</span><span class="sxs-lookup"><span data-stu-id="f8bff-129">Models that you create from OLAP data can be saved as a data mining dimension, or you can save the set of data and your models as a new cube.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8bff-130">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f8bff-130">In This Section</span></span>  
 [<span data-ttu-id="f8bff-131">Proyectos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8bff-131">Data Mining Projects</span></span>](data-mining-projects.md)  
  
 [<span data-ttu-id="f8bff-132">Procesar objetos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8bff-132">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)  
  
 [<span data-ttu-id="f8bff-133">Proyectos relacionados en las soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8bff-133">Related Projects for Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
 [<span data-ttu-id="f8bff-134">Implementación de soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8bff-134">Deployment of Data Mining Solutions</span></span>](deployment-of-data-mining-solutions.md)  
  
## <a name="related-tasks-and-topics"></a><span data-ttu-id="f8bff-135">Temas y tareas relacionados</span><span class="sxs-lookup"><span data-stu-id="f8bff-135">Related Tasks and Topics</span></span>  
 <span data-ttu-id="f8bff-136">Después de crear una solución básica de minería de datos, incluidos los orígenes de datos y su estructura de minería de datos, puede generar la solución agregando nuevos modelos,probando y comparando modelos, creando predicciones, y experimentando con subconjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="f8bff-136">After you have created a basic data mining solution, including data sources and a mining structure, you can build on the solution by adding new models, testing and comparing models, creating predictions, and experimenting with subsets of data.</span></span>  
  
 <span data-ttu-id="f8bff-137">Para obtener más información, vea los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="f8bff-137">For more information, see the following links:</span></span>  
  
|<span data-ttu-id="f8bff-138">Tareas</span><span class="sxs-lookup"><span data-stu-id="f8bff-138">Tasks</span></span>|<span data-ttu-id="f8bff-139">Temas</span><span class="sxs-lookup"><span data-stu-id="f8bff-139">Topics</span></span>|  
|-----------|------------|  
|<span data-ttu-id="f8bff-140">Pruebe los modelos que cree, valide la calidad de los datos de entrenamiento y cree gráficos que representen la precisión de los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="f8bff-140">Test the models you create, validate the quality of your training data, and create charts that represent the accuracy of data mining models.</span></span>|[<span data-ttu-id="f8bff-141">Prueba y validación &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="f8bff-141">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)|  
|<span data-ttu-id="f8bff-142">Entrene el modelo rellenando la estructura y los modelos relacionados con datos.</span><span class="sxs-lookup"><span data-stu-id="f8bff-142">Train the model by populating the structure and related models with data.</span></span> <span data-ttu-id="f8bff-143">Actualice y amplía los modelos con nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="f8bff-143">Update and extend models with new data.</span></span>|[<span data-ttu-id="f8bff-144">Procesar objetos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8bff-144">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)|  
|<span data-ttu-id="f8bff-145">Personalice un modelo de minería de datos aplicando filtros a los datos de entrenamiento, eligiendo un algoritmo diferente o estableciendo parámetros avanzados para el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="f8bff-145">Customize a mining model by applying filters to the training data, choosing a different algorithm, or setting advanced algorithm parameters.</span></span>|[<span data-ttu-id="f8bff-146">Personalizar la estructura y los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8bff-146">Customize Mining Models and Structure</span></span>](customize-mining-models-and-structure.md)|  
|<span data-ttu-id="f8bff-147">Personalice un modelo de minería de datos aplicando filtros a los datos usados en el entrenamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="f8bff-147">Customize a mining model by applying filters to the data used in training the mode.</span></span>|[<span data-ttu-id="f8bff-148">Agregar modelos de minería de datos a una estructura &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="f8bff-148">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](add-mining-models-to-a-structure-analysis-services-data-mining.md)|  
|<span data-ttu-id="f8bff-149">Actualice y administre las soluciones de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="f8bff-149">Update and manage data mining solutions.</span></span>|<span data-ttu-id="f8bff-150">Vínculo TBD</span><span class="sxs-lookup"><span data-stu-id="f8bff-150">Link TBD</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8bff-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8bff-151">See Also</span></span>  
 [<span data-ttu-id="f8bff-152">Tutoriales de minería de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f8bff-152">Data Mining Tutorials &#40;Analysis Services&#41;</span></span>](../data-mining-tutorials-analysis-services.md)  
  
  
