---
title: Crear una consulta de contenido en un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: a0ce837a-89ed-46cf-9ce1-801ccb75fa04
author: minewiskan
ms.author: owend
ms.openlocfilehash: 26af1100d6ba80185c1cc4de18548df0e387824c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743698"
---
# <a name="create-a-content-query-on-a-mining-model"></a><span data-ttu-id="8e387-102">Crear una consulta de contenido en un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="8e387-102">Create a Content Query on a Mining Model</span></span>
  <span data-ttu-id="8e387-103">Puede consultar mediante programación el contenido del modelo de minería de datos utilizando AMO o XML/A, pero crear las consultas mediante DMX resulta más fácil.</span><span class="sxs-lookup"><span data-stu-id="8e387-103">You can query the mining model content programmatically by using AMO or XML/A, but it is easier to create queries by using DMX.</span></span> <span data-ttu-id="8e387-104">También puede crear consultas con los conjuntos de filas de esquema de minería de datos estableciendo una conexión a la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y crear una consulta mediante la DMV que proporciona [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e387-104">You can also create queries against the data mining schema rowsets by establishing a connection to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and creating a query using the DMVs provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8e387-105">Los procedimientos siguientes muestran cómo crear consultas con un modelo de minería de datos utilizando DMX y cómo consultar los conjuntos de filas del esquema de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="8e387-105">The following procedures demonstrate how to create queries against a mining model by using DMX, and how to query the data mining schema rowsets.</span></span>  
  
 <span data-ttu-id="8e387-106">Para obtener un ejemplo de cómo crear una consulta similar con XML/A, vea [Crear una consulta de minería de datos utilizando XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="8e387-106">For an example of how to create a similar query by using XML/A, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="querying-data-mining-model-content-by-using-dmx"></a><span data-ttu-id="8e387-107">Consultar el contenido del modelo de minería de datos con DMX</span><span class="sxs-lookup"><span data-stu-id="8e387-107">Querying Data Mining Model Content by Using DMX</span></span>  
  
#### <a name="to-create-a-dmx-model-content-query"></a><span data-ttu-id="8e387-108">Para crear una consulta de contenido del modelo DMX</span><span class="sxs-lookup"><span data-stu-id="8e387-108">To create a DMX model content query</span></span>  
  
1.  <span data-ttu-id="8e387-109">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Ver** , haga clic en el **Explorador de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="8e387-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="8e387-110">En el panel **Explorador de plantillas** , haga clic en el icono de cubo para cambiar la lista y mostrar las plantillas de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="8e387-110">In the **Template Explorer** pane, click the cube icon to change the list and display Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="8e387-111">En la lista de categorías de plantilla, expanda **DMX**, expanda **Contenido del modelo**y haga doble clic en **Consulta de contenido**.</span><span class="sxs-lookup"><span data-stu-id="8e387-111">In the list of template categories, expand **DMX**, expand **Model Content**, and double-click **Content Query**.</span></span>  
  
4.  <span data-ttu-id="8e387-112">En el cuadro de diálogo **Conectar a Analysis Services** , seleccione la instancia que contiene el modelo de minería de datos que desea consultar y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="8e387-112">In the **Connect to Analysis Services** dialog box, select the instance that contains the mining model you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="8e387-113">La plantilla **Consulta de contenido** se abre en el editor de código adecuado.</span><span class="sxs-lookup"><span data-stu-id="8e387-113">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="8e387-114">El panel de metadatos muestra los modelos que están disponibles en la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="8e387-114">The metadata pane lists the models that are available in the current database.</span></span> <span data-ttu-id="8e387-115">Para cambiar la base de datos, seleccione una diferente en la lista **Bases de datos disponibles** .</span><span class="sxs-lookup"><span data-stu-id="8e387-115">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
5.  <span data-ttu-id="8e387-116">Escriba el nombre de un modelo de minería de datos en la línea `FROM` [ *\<mining model, name, MyModel>* ] `.CONTENT` .</span><span class="sxs-lookup"><span data-stu-id="8e387-116">Enter the name of a mining model in the line, `FROM` [*\<mining model, name, MyModel>*]`.CONTENT`.</span></span> <span data-ttu-id="8e387-117">Si el nombre del modelo de minería de datos contiene espacios, debe escribirse entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="8e387-117">If the mining model name contains spaces, you must enclose the name in brackets.</span></span>  
  
     <span data-ttu-id="8e387-118">Si no desea escribir el nombre, puede seleccionar un modelo de minería de datos en el **Explorador de objetos** y arrastrarlo a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8e387-118">If you don't want to type the name, you can select a mining model in **Object Explorer** and drag it into the template.</span></span>  
  
6.  <span data-ttu-id="8e387-119">En la línea, `SELECT` *\<select list, expr list, \*>* Escriba los nombres de las columnas del conjunto de filas de esquema de contenido del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="8e387-119">In the line, `SELECT`*\<select list, expr list, \*>*, type the names of columns in the mining model content schema rowset.</span></span>  
  
     <span data-ttu-id="8e387-120">Para obtener una lista de las columnas que puede devolver en las consultas de contenido del modelo de minería de datos, vea [Contenido del modelo de minería de datos &#40;Analysis Services - Minería de datos&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="8e387-120">To view a list of columns that you can return in mining model content queries, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
7.  <span data-ttu-id="8e387-121">Opcionalmente, escriba una condición en la cláusula WHERE de la plantilla para restringir las filas que se devuelven para nodos o valores concretos.</span><span class="sxs-lookup"><span data-stu-id="8e387-121">Optionally, type a condition in the WHERE clause of the template to restrict the rows returned to specific nodes or values.</span></span>  
  
8.  <span data-ttu-id="8e387-122">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8e387-122">Click **Execute**.</span></span>  
  
## <a name="querying-the-data-mining-schema-rowsets"></a><span data-ttu-id="8e387-123">Consultar los conjuntos de filas de esquema de minería de datos</span><span class="sxs-lookup"><span data-stu-id="8e387-123">Querying the Data Mining Schema Rowsets</span></span>  
  
#### <a name="to-create-a-query-against-the-data-mining-schema-rowset"></a><span data-ttu-id="8e387-124">Para crear una consulta con el conjunto de filas de esquema de minería de datos</span><span class="sxs-lookup"><span data-stu-id="8e387-124">To create a query against the data mining schema rowset</span></span>  
  
1.  <span data-ttu-id="8e387-125">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en la barra de herramientas **Nueva consulta** , haga clic en **Consulta DMX de Analysis Services**o **Consulta MDX de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="8e387-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **New Query** toolbar, click **Analysis Services DMX Query**, or **Analysis Services MDX query**.</span></span>  
  
2.  <span data-ttu-id="8e387-126">En el cuadro de diálogo **Conectar a Analysis Services** , seleccione la instancia que contiene los objetos que desea consultar y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="8e387-126">In the **Connect to Analysis Services** dialog box, select the instance that contains the objects you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="8e387-127">La plantilla **Consulta de contenido** se abre en el editor de código adecuado.</span><span class="sxs-lookup"><span data-stu-id="8e387-127">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="8e387-128">El panel de metadatos muestra los objetos que están disponibles en la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="8e387-128">The metadata pane lists the objects that are available in the current database.</span></span> <span data-ttu-id="8e387-129">Para cambiar la base de datos, seleccione una diferente en la lista **Bases de datos disponibles** .</span><span class="sxs-lookup"><span data-stu-id="8e387-129">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
3.  <span data-ttu-id="8e387-130">En el editor de consultas, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e387-130">In the query editor, type the following:</span></span>  
  
     `SELECT *`  
  
     `FROM $system.DMSCHEMA_MINING_MODEL_CONTENT`  
  
     `WHERE MODEL_NAME = '<model name>'`  
  
4.  <span data-ttu-id="8e387-131">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8e387-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="8e387-132">El panel Resultados muestra el contenido del modelo.</span><span class="sxs-lookup"><span data-stu-id="8e387-132">The Results pane displays the contents of the model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e387-133">Para ver una lista de todos los conjuntos de filas de esquema que puede consultar en la instancia actual, use esta consulta: `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span><span class="sxs-lookup"><span data-stu-id="8e387-133">To view a list of all the schema rowsets that you can query on the current instance, use this query: `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span></span> <span data-ttu-id="8e387-134">O bien, para obtener una lista de conjuntos de filas de esquema concretos de la minería de datos, vea [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="8e387-134">Or, for a list of schema rowsets specific to data mining, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e387-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e387-135">See Also</span></span>  
 <span data-ttu-id="8e387-136">[Contenido del modelo de minería de datos &#40;Analysis Services:&#41;de minería de datos](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="8e387-136">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="8e387-137">Data Mining Schema Rowsets</span><span class="sxs-lookup"><span data-stu-id="8e387-137">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
