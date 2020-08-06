---
title: Detectar categorías (herramientas de análisis de tabla para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- clustering [data mining]
- mining model, decision tree
- category detection
ms.assetid: 3c7e9ebb-d0c9-498e-a9ba-cc13eaa43520
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4874c85d7e4ab65716741e8ae9433406dfb08b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748390"
---
# <a name="detect-categories-table-analysis-tools-for-excel"></a><span data-ttu-id="b0c34-102">Detectar categorías (Herramientas de análisis de tabla para Excel)</span><span class="sxs-lookup"><span data-stu-id="b0c34-102">Detect Categories (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="b0c34-103">![Botón Detectar categorías en cinta de opciones](media/tat-detectcat.gif "Botón Detectar categorías en cinta de opciones")</span><span class="sxs-lookup"><span data-stu-id="b0c34-103">![Detect Categories button in ribbon](media/tat-detectcat.gif "Detect Categories button in ribbon")</span></span>

 <span data-ttu-id="b0c34-104">La herramienta **detectar categorías** busca automáticamente las filas de una tabla que tienen características similares.</span><span class="sxs-lookup"><span data-stu-id="b0c34-104">The **Detect Categories** tool automatically finds rows in a table that have similar characteristics.</span></span>

 <span data-ttu-id="b0c34-105">Cuando la herramienta finaliza, genera un informe que muestra las categorías encontradas junto con sus características distintivas.</span><span class="sxs-lookup"><span data-stu-id="b0c34-105">When the tool finishes, it creates a report that lists the categories it found, together with their distinguishing characteristics.</span></span> <span data-ttu-id="b0c34-106">De forma predeterminada, agrega una nueva columna a la tabla de datos que contiene la categoría propuesta para cada fila de datos.</span><span class="sxs-lookup"><span data-stu-id="b0c34-106">By default, it adds a new column to the data table that contains the proposed category for each row of your data.</span></span> <span data-ttu-id="b0c34-107">Después, podrá revisar las categorías y cambiar su nombre.</span><span class="sxs-lookup"><span data-stu-id="b0c34-107">You can then review the categories and rename them.</span></span>

## <a name="using-the-detect-categories-tool"></a><span data-ttu-id="b0c34-108">Usar la herramienta Detectar categorías</span><span class="sxs-lookup"><span data-stu-id="b0c34-108">Using the Detect Categories Tool</span></span>

1.  <span data-ttu-id="b0c34-109">Abra una tabla de Excel.</span><span class="sxs-lookup"><span data-stu-id="b0c34-109">Open an Excel table.</span></span>

2.  <span data-ttu-id="b0c34-110">Haga clic en **detectar categorías**.</span><span class="sxs-lookup"><span data-stu-id="b0c34-110">Click **Detect Categories**.</span></span>

3.  <span data-ttu-id="b0c34-111">Especifique las columnas que desea usar en el análisis.</span><span class="sxs-lookup"><span data-stu-id="b0c34-111">Specify the columns to use in analysis.</span></span> <span data-ttu-id="b0c34-112">Puede anular la selección de las columnas que tengan valores distintivos, como nombres de persona o identificadores de registro, ya que estas columnas podrían no ser útiles para el análisis.</span><span class="sxs-lookup"><span data-stu-id="b0c34-112">You can deselect columns that have distinct values, such as personal names or record IDs, because these columns might not be useful for analysis.</span></span>

4.  <span data-ttu-id="b0c34-113">Opcionalmente, especifique el número máximo de categorías que desea crear.</span><span class="sxs-lookup"><span data-stu-id="b0c34-113">Optionally, specify the maximum number of categories to create.</span></span> <span data-ttu-id="b0c34-114">De forma predeterminada, la herramienta crea automáticamente tantas categorías como encuentra.</span><span class="sxs-lookup"><span data-stu-id="b0c34-114">By default, the tool automatically creates as many categories as it finds.</span></span>

5.  <span data-ttu-id="b0c34-115">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b0c34-115">Click **Run**.</span></span>

6.  <span data-ttu-id="b0c34-116">La herramienta crea una nueva hoja de cálculo, denominada Informe de categorías, que contiene la lista de categorías y sus características.</span><span class="sxs-lookup"><span data-stu-id="b0c34-116">The tool creates a new worksheet, named Categories Report, which contains the list of categories and their characteristics.</span></span>

 <span data-ttu-id="b0c34-117">Para obtener más información sobre cómo especificar las opciones de la herramienta, vea [detectar categorías (cuadro de diálogo, herramientas de análisis de tabla para Excel)](detect-categories-table-analysis-tools-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="b0c34-117">For more information about how to specify options for the tool, see [Detect Categories Dialog Box (Table Analysis Tools for Excel)](detect-categories-table-analysis-tools-for-excel.md).</span></span>

## <a name="understanding-the-categories-report"></a><span data-ttu-id="b0c34-118">Descripción del Informe de categorías</span><span class="sxs-lookup"><span data-stu-id="b0c34-118">Understanding the Categories Report</span></span>
 <span data-ttu-id="b0c34-119">El **Informe de categorías** contiene dos tablas, una **lista de categorías** y características de **categoría**, y un gráfico de **perfiles de categoría** .</span><span class="sxs-lookup"><span data-stu-id="b0c34-119">The **Categories Report** contains two tables, **Category List** and **Category Characteristics**, and a **Category Profiles** chart.</span></span>

### <a name="category-list"></a><span data-ttu-id="b0c34-120">Lista de categorías</span><span class="sxs-lookup"><span data-stu-id="b0c34-120">Category List</span></span>
 <span data-ttu-id="b0c34-121">La primera tabla enumera las categorías que se encontraron.</span><span class="sxs-lookup"><span data-stu-id="b0c34-121">The first table lists the categories that were found.</span></span> <span data-ttu-id="b0c34-122">La columna **recuento de filas** indica el número de filas de datos que se asignaron a cada categoría.</span><span class="sxs-lookup"><span data-stu-id="b0c34-122">The **Row Count** column indicates how many rows of data were assigned to each category.</span></span>

 <span data-ttu-id="b0c34-123">El modelo crea nombres temporales para cada categoría, pero puede cambiar el nombre de las categorías como desee.</span><span class="sxs-lookup"><span data-stu-id="b0c34-123">The model creates temporary names for each category, but you can rename the categories as you like.</span></span> <span data-ttu-id="b0c34-124">Por ejemplo, en el ejemplo siguiente, se ha cambiado el nombre de la primera categoría a **Income**, porque ese era el atributo superior del clúster.</span><span class="sxs-lookup"><span data-stu-id="b0c34-124">For example, in the following example, the first category has been renamed **Low Income**, because that was the top attribute of the cluster.</span></span>

 <span data-ttu-id="b0c34-125">![informe creado por la herramienta Detectar categorías](media/dm13-tat-detectcat-report1.gif "informe creado por la herramienta Detectar categorías")</span><span class="sxs-lookup"><span data-stu-id="b0c34-125">![report created by Detect Categories tool](media/dm13-tat-detectcat-report1.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="b0c34-126">En cuanto escribe la nueva etiqueta, el cambio se propaga al resto de gráficos así como a la lista de categorías agregada en la hoja de cálculo de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="b0c34-126">As soon as you type the new label, the change is propagated to all the other charts as well as to the category list added in the source data worksheet.</span></span>

### <a name="category-characteristics"></a><span data-ttu-id="b0c34-127">Características de categoría</span><span class="sxs-lookup"><span data-stu-id="b0c34-127">Category Characteristics</span></span>
 <span data-ttu-id="b0c34-128">La segunda tabla, **características**de la categoría, muestra detalles sobre la composición de cada categoría.</span><span class="sxs-lookup"><span data-stu-id="b0c34-128">The second table, **Category Characteristics**, shows details about the makeup of each category.</span></span> <span data-ttu-id="b0c34-129">Haga clic en el botón **filtrar** situado en la parte superior de la columna **categoría** para ver el foco en una o solo algunas categorías.</span><span class="sxs-lookup"><span data-stu-id="b0c34-129">Click the **Filter** button at the top of the **Category** column to see focus on one or just a few categories.</span></span>

 <span data-ttu-id="b0c34-130">![informe creado por la herramienta Detectar categorías](media/dm13-tat-detectcat-report2.gif "informe creado por la herramienta Detectar categorías")</span><span class="sxs-lookup"><span data-stu-id="b0c34-130">![report created by Detect Categories tool](media/dm13-tat-detectcat-report2.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="b0c34-131">El sombreado de la columna **importancia relativa**indica la importancia de la combinación de atributo y valor como factor diferenciador.</span><span class="sxs-lookup"><span data-stu-id="b0c34-131">The shading in the column, **Relative Importance**, indicates how important that combination of attribute and value is as a distinguishing factor.</span></span> <span data-ttu-id="b0c34-132">Cuanto más larga sea la barra, más posibilidades existen de que el atributo sea muy representativo de esta categoría.</span><span class="sxs-lookup"><span data-stu-id="b0c34-132">The longer the bar, the more likely it is that this attribute is strongly representative of this category.</span></span>

### <a name="categories-profile-chart"></a><span data-ttu-id="b0c34-133">Gráfico de perfil de categorías</span><span class="sxs-lookup"><span data-stu-id="b0c34-133">Categories Profile Chart</span></span>
 <span data-ttu-id="b0c34-134">El gráfico final de la hoja de cálculo **Informe de categorías** , **perfiles de categoría**, es un **gráfico dinámico** interactivo que puede utilizar para reorganizar y ocultar campos, filtrar valores y personalizar la apariencia del gráfico.</span><span class="sxs-lookup"><span data-stu-id="b0c34-134">The final chart in the **Categories Report** worksheet, **Category Profiles**, is an interactive **Pivot Chart** that you can use to rearrange and hide fields, filter on values, and customize the chart's appearance.</span></span>

 <span data-ttu-id="b0c34-135">Excel 2013 ahora proporciona los **estilos de gráfico** y los controles de elementos de **gráfico** directamente en la superficie de diseño que facilitan la mejora del diseño del gráfico.</span><span class="sxs-lookup"><span data-stu-id="b0c34-135">Excel 2013 now provides **Chart Styles** and **Chart Elements** controls right in the design surface that make it easy to improve the chart design.</span></span>

 <span data-ttu-id="b0c34-136">![informe creado por la herramienta Detectar categorías](media/dm13-tat-detectcat-report3.gif "informe creado por la herramienta Detectar categorías")</span><span class="sxs-lookup"><span data-stu-id="b0c34-136">![report created by Detect Categories tool](media/dm13-tat-detectcat-report3.gif "report created by Detect Categories tool")</span></span>

## <a name="requirements"></a><span data-ttu-id="b0c34-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0c34-137">Requirements</span></span>
 <span data-ttu-id="b0c34-138">La herramienta **detectar categorías** no tiene ningún requisito para la cantidad o el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="b0c34-138">The **Detect Categories** tool has no requirements for the amount or type of data.</span></span>

> [!NOTE]
>  <span data-ttu-id="b0c34-139">Cuando se usa la herramienta **detectar categorías** , se crea una nueva columna, categoría, en la tabla de datos original.</span><span class="sxs-lookup"><span data-stu-id="b0c34-139">When you use the **Detect Categories** tool, it creates a new column, Category, in the original data table.</span></span> <span data-ttu-id="b0c34-140">Si deja esta columna en la tabla de datos y después realiza operaciones de minería de datos posteriores, la presencia de esta columna podría influir en los resultados.</span><span class="sxs-lookup"><span data-stu-id="b0c34-140">If you leave this column in the data table and then perform subsequent data mining operations, the presence of this column could influence your results.</span></span> <span data-ttu-id="b0c34-141">Para asegurarse de que otras operaciones no se verán afectadas, debería hacer una copia de la tabla de datos sin la columna Categoría antes de usar otras herramientas de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b0c34-141">To ensure that this does not affect other operations, you should make a copy of the data table without the Category column before using other data mining tools.</span></span>

## <a name="related-tools"></a><span data-ttu-id="b0c34-142">Herramientas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b0c34-142">Related Tools</span></span>
 <span data-ttu-id="b0c34-143">Cuando la herramienta **detectar categorías** analiza los datos, crea una estructura de minería de datos y un modelo de minería de datos mediante el [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo de clústeres.</span><span class="sxs-lookup"><span data-stu-id="b0c34-143">When the **Detect Categories** tool analyzes your data, it creates a data mining structure and data mining model by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span>

 <span data-ttu-id="b0c34-144">Después de crear un modelo de minería de datos con la herramienta **analizar influenciadores clave** , puede usar el cliente de minería de datos para Excel para examinar el modelo y explorar las relaciones con más detalle.</span><span class="sxs-lookup"><span data-stu-id="b0c34-144">After you have created a data mining model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client for Excel to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="b0c34-145">El Cliente de minería de datos para Excel es un complemento independiente que proporciona funciones de minería de datos más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="b0c34-145">The Data Mining Client for Excel is a separate add-in that provides more advanced data mining functionality.</span></span> <span data-ttu-id="b0c34-146">Para obtener más información, vea [examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="b0c34-146">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>

 <span data-ttu-id="b0c34-147">Para obtener más información acerca del uso de las funcionalidades de modelado de datos en el cliente de minería de datos para Excel, vea [crear un modelo de minería de datos](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="b0c34-147">For more information about using the data modeling capabilities in the Data Mining Client for Excel, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="b0c34-148">Para obtener más información acerca del algoritmo usado por la herramienta **detectar categorías** , vea el tema "algoritmo de clústeres de Microsoft" en los [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] libros en pantalla de.</span><span class="sxs-lookup"><span data-stu-id="b0c34-148">For more information about the algorithm used by the **Detect Categories** tool, see the topic "Microsoft Clustering Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0c34-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0c34-149">See Also</span></span>
 [<span data-ttu-id="b0c34-150">Herramientas de análisis de tabla para Excel</span><span class="sxs-lookup"><span data-stu-id="b0c34-150">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


