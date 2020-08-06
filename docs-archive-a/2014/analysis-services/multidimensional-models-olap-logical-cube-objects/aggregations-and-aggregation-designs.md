---
title: Agregaciones y diseños de agregaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- aggregations [Analysis Services], about aggregations
- storage [Analysis Services], aggregations
- Storage Design Wizard
- data summary [Analysis Services]
- data storage [Analysis Services]
- storing data [Analysis Services], aggregations
- aggregations [Analysis Services]
ms.assetid: 35bd8589-39fa-4e0b-b28f-5a07d70da0a2
author: minewiskan
ms.author: owend
ms.openlocfilehash: c56e80482ef71e8041f8518ae9901691a1809990
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746034"
---
# <a name="aggregations-and-aggregation-designs"></a><span data-ttu-id="ceb07-102">Agregaciones y diseños de agregaciones</span><span class="sxs-lookup"><span data-stu-id="ceb07-102">Aggregations and Aggregation Designs</span></span>
  <span data-ttu-id="ceb07-103">Un objeto <xref:Microsoft.AnalysisServices.AggregationDesign> define un conjunto de definiciones de agregación que se pueden compartir entre varias particiones.</span><span class="sxs-lookup"><span data-stu-id="ceb07-103">An <xref:Microsoft.AnalysisServices.AggregationDesign> object defines a set of aggregation definitions that can be shared across multiple partitions.</span></span>  
  
 <span data-ttu-id="ceb07-104">Un objeto <xref:Microsoft.AnalysisServices.Aggregation> representa el resumen de los datos de grupo de medida en una granularidad determinada de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="ceb07-104">An <xref:Microsoft.AnalysisServices.Aggregation> object represents the summarization of measure group data at certain granularity of the dimensions.</span></span>  
  
 <span data-ttu-id="ceb07-105">Un objeto <xref:Microsoft.AnalysisServices.Aggregation> simple se compone de la información básica y dimensiones.</span><span class="sxs-lookup"><span data-stu-id="ceb07-105">A simple <xref:Microsoft.AnalysisServices.Aggregation> object is composed of: basic information and dimensions.</span></span> <span data-ttu-id="ceb07-106">La información Básica incluye el nombre de la agregación, el identificador, anotaciones y una descripción.</span><span class="sxs-lookup"><span data-stu-id="ceb07-106">Basic information includes the name of the aggregation, the ID, annotations, and a description.</span></span> <span data-ttu-id="ceb07-107">Las dimensiones son una colección de objetos <xref:Microsoft.AnalysisServices.AggregationDimension> que contienen la lista de atributos de granularidad de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="ceb07-107">The dimensions are a collection of <xref:Microsoft.AnalysisServices.AggregationDimension> objects that contain the list of granularity attributes for the dimension.</span></span>  
  
 <span data-ttu-id="ceb07-108">Las agregaciones son resúmenes de datos precalculados de las celdas hoja.</span><span class="sxs-lookup"><span data-stu-id="ceb07-108">Aggregations are precalculated summaries of data from leaf cells.</span></span> <span data-ttu-id="ceb07-109">Las agregaciones mejoran el tiempo de respuesta de las consultas al preparar las respuestas antes de que se formulen las preguntas.</span><span class="sxs-lookup"><span data-stu-id="ceb07-109">Aggregations improve query response time by preparing the answers before the questions are asked.</span></span> <span data-ttu-id="ceb07-110">Por ejemplo, cuando una tabla de hechos de un almacenamiento de datos contiene cientos de miles de filas, puede tardar en responderse una consulta en la que se soliciten los totales de las ventas semanales de una determinada línea de productos si hay que recorrer y sumar todas las filas de la tabla de hechos para calcular la respuesta en el momento de la consulta.</span><span class="sxs-lookup"><span data-stu-id="ceb07-110">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the weekly sales totals for a particular product line can take a long time to answer if all the rows in the fact table have to be scanned and summed at query time to compute the answer.</span></span> <span data-ttu-id="ceb07-111">Sin embargo, la respuesta podría ser casi inmediata si se han precalculado los datos de resumen para responder a esta consulta.</span><span class="sxs-lookup"><span data-stu-id="ceb07-111">However, the response can be almost immediate if the summarization data to answer this query has been precalculated.</span></span> <span data-ttu-id="ceb07-112">El precálculo de los datos de resumen se produce durante el procesamiento y constituye la base de los tiempos de respuesta rápida de la tecnología OLAP.</span><span class="sxs-lookup"><span data-stu-id="ceb07-112">This precalculation of summary data occurs during processing and is the foundation for the rapid response times of OLAP technology.</span></span>  
  
 <span data-ttu-id="ceb07-113">Los cubos son la forma en que la tecnología OLAP organiza los datos de resumen en estructuras multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="ceb07-113">Cubes are the way that OLAP technology organizes summary data into multidimensional structures.</span></span> <span data-ttu-id="ceb07-114">Las dimensiones y sus jerarquías de atributos reflejan las consultas que se pueden hacer al cubo.</span><span class="sxs-lookup"><span data-stu-id="ceb07-114">Dimensions and their hierarchies of attributes reflect the queries that can be asked of the cube.</span></span> <span data-ttu-id="ceb07-115">Las agregaciones se almacenan en la estructura multidimensional en celdas cuyas coordenadas especifican las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="ceb07-115">Aggregations are stored in the multidimensional structure in cells at coordinates specified by the dimensions.</span></span> <span data-ttu-id="ceb07-116">Por ejemplo, la pregunta "¿Cuáles fueron las ventas del producto X en 1998 para la región Northwest?"</span><span class="sxs-lookup"><span data-stu-id="ceb07-116">For example, the question "What were the sales of product X in 1998 for the Northwest region?"</span></span> <span data-ttu-id="ceb07-117">implica tres dimensiones (producto, hora y geografía) y una medida (ventas).</span><span class="sxs-lookup"><span data-stu-id="ceb07-117">involves three dimensions (Product, Time, and Geography) and one measure (Sales).</span></span> <span data-ttu-id="ceb07-118">La respuesta es el valor de la celda del cubo que se encuentra en las coordenadas especificadas (producto X, 1998, Northwest); es decir, un valor numérico simple.</span><span class="sxs-lookup"><span data-stu-id="ceb07-118">The value of the cell in the cube at the specified coordinates (product X, 1998, Northwest) is the answer, a single numeric value.</span></span>  
  
 <span data-ttu-id="ceb07-119">Otras preguntas pueden devolver varios valores.</span><span class="sxs-lookup"><span data-stu-id="ceb07-119">Other questions may return multiple values.</span></span> <span data-ttu-id="ceb07-120">Por ejemplo: "¿Cuáles fueron las ventas de productos de hardware por trimestre y región en 1998?".</span><span class="sxs-lookup"><span data-stu-id="ceb07-120">For example, "How much were the sales of hardware products by quarter by region for 1998?"</span></span> <span data-ttu-id="ceb07-121">Estas consultas devuelven conjuntos de celdas de las coordenadas que satisfacen las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="ceb07-121">Such queries return sets of cells from the coordinates that satisfy the specified conditions.</span></span> <span data-ttu-id="ceb07-122">El número de celdas devueltas por la consulta depende del número de elementos del nivel Hardware de la dimensión Product, los cuatro trimestres de 1998 y el número de regiones de la dimensión Geography.</span><span class="sxs-lookup"><span data-stu-id="ceb07-122">The number of cells returned by the query depends on the number of items in the Hardware level of the Product dimension, the four quarters in 1998, and the number of regions in the Geography dimension.</span></span> <span data-ttu-id="ceb07-123">Si todos los datos de resumen se han precalculado en agregaciones, el tiempo de respuesta de la consulta solamente dependerá del tiempo que se necesite para extraer las celdas especificadas.</span><span class="sxs-lookup"><span data-stu-id="ceb07-123">If all summary data has been precalculated into aggregations, the response time of the query will depend only on the time that is required to extract the specified cells.</span></span> <span data-ttu-id="ceb07-124">No es necesario calcular ni leer datos de la tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="ceb07-124">No calculation or reading of data from the fact table is required.</span></span>  
  
 <span data-ttu-id="ceb07-125">Aunque el precálculo de todas las posibles agregaciones de un cubo puede acelerar al máximo el tiempo de respuesta de todas las consultas, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] puede calcular con facilidad determinados valores agregados a partir de otras agregaciones precalculadas.</span><span class="sxs-lookup"><span data-stu-id="ceb07-125">Although precalculation of all possible aggregations in a cube might provide the fastest possible response time for all queries, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] can easily calculate some aggregrated values from other precalculated aggregations.</span></span> <span data-ttu-id="ceb07-126">Además, el cálculo de todas las agregaciones posibles requiere gran cantidad de tiempo de procesamiento y espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ceb07-126">Additionally, calculating all possible aggregations requires significant processing time and storage.</span></span> <span data-ttu-id="ceb07-127">Por lo tanto, existe un equilibrio entre los requisitos de almacenamiento y el porcentaje de posibles agregaciones que se precalculan.</span><span class="sxs-lookup"><span data-stu-id="ceb07-127">Therefore, there is a tradeoff between storage requirements and the percentage of possible aggregations that are precalculated.</span></span> <span data-ttu-id="ceb07-128">Si no se precalculan agregaciones (0%), la cantidad de tiempo de procesamiento y de espacio de almacenamiento que se necesita para un cubo se reduce al mínimo, aunque el tiempo de respuesta puede ser lento, ya que es preciso recuperar de las celdas hoja los datos necesarios para responder a cada consulta y luego agregarlos en el tiempo de la consulta para responder a cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="ceb07-128">If no aggregations are precalculated (0%), the amount of required processing time and storage space for a cube is minimized, but query response time may be slow because the data required to answer each query must be retrieved from the leaf cells and then aggregated at query time to answer each query.</span></span> <span data-ttu-id="ceb07-129">Por ejemplo, para devolver un único número que responda a la pregunta planteada anteriormente ("¿Cuáles fueron las ventas del producto X en 1998 para la región noroeste?") sería necesario leer miles de filas de datos, extraer el valor de la columna utilizada para proporcionar la medida Sales de cada fila y, a continuación, calcular la suma.</span><span class="sxs-lookup"><span data-stu-id="ceb07-129">For example, returning a single number that answers the question asked earlier ("What were the sales of product X in 1998 for the Northwest region") might require reading thousands of rows of data, extracting the value of the column used to provide the Sales measure from each row, and then calculating the sum.</span></span> <span data-ttu-id="ceb07-130">Además, el período de tiempo necesario para recuperar los datos dependerá en gran parte del modo de almacenamiento elegido para los datos: MOLAP, HOLAP o ROLAP.</span><span class="sxs-lookup"><span data-stu-id="ceb07-130">Moreover, the length of time required to retrieve that data will very depending on the storage mode chosen for the data-MOLAP, HOLAP, or ROLAP.</span></span>  
  
## <a name="designing-aggregations"></a><span data-ttu-id="ceb07-131">Diseñar agregaciones</span><span class="sxs-lookup"><span data-stu-id="ceb07-131">Designing Aggregations</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="ceb07-132">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incorpora un algoritmo sofisticado para seleccionar agregaciones para el precálculo, de modo que se puedan calcular rápidamente otras agregaciones a partir de los valores precalculados.</span><span class="sxs-lookup"><span data-stu-id="ceb07-132">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incorporates a sophisticated algorithm to select aggregations for precalculation so that other aggregations can be quickly computed from the precalculated values.</span></span> <span data-ttu-id="ceb07-133">Por ejemplo, si se han precalculado agregaciones para el nivel Month de una jerarquía Time, los cálculos de un nivel Quarter solamente necesitarán el resumen de tres números, operación que se puede realizar rápidamente a petición.</span><span class="sxs-lookup"><span data-stu-id="ceb07-133">For example, if the aggregations are precalculated for the Month level of a Time hierarchy, the calculation for a Quarter level requires only the summarization of three numbers, which can be quickly computed on demand.</span></span> <span data-ttu-id="ceb07-134">Esta técnica ahorra tiempo de procesamiento y reduce los requisitos de almacenamiento, con el mínimo efecto en el tiempo de respuesta de consultas.</span><span class="sxs-lookup"><span data-stu-id="ceb07-134">This technique saves processing time and reduces storage requirements, with minimal effect on query response time.</span></span>  
  
 <span data-ttu-id="ceb07-135">El Asistente para diseñar agregaciones permite especificar las restricciones de almacenamiento y porcentaje del algoritmo para conseguir un equilibrio satisfactorio entre el tiempo de respuesta de consultas y los requisitos de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ceb07-135">The Aggregation Design Wizard provides options for you to specify storage and percentage constraints on the algorithm to achieve a satisfactory tradeoff between query response time and storage requirements.</span></span> <span data-ttu-id="ceb07-136">Sin embargo, el algoritmo del Asistente para diseñar agregaciones asume que todas las posibles consultas son igualmente probables.</span><span class="sxs-lookup"><span data-stu-id="ceb07-136">However, the Aggregation Design Wizard's algorithm assumes that all possible queries are equally likely.</span></span> <span data-ttu-id="ceb07-137">El Asistente para optimización basada en el uso permite ajustar el diseño de la agregación de un grupo de medida mediante el análisis de las consultas enviadas por las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="ceb07-137">The Usage-Based Optimization Wizard lets you adjust the aggregation design for a measure group by analyzing the queries that have been submitted by client applications.</span></span> <span data-ttu-id="ceb07-138">Al utilizar el asistente para ajustar la agregación de un cubo, se puede mejorar el tiempo de respuesta de las consultas más frecuentes y reducir el tiempo de respuesta de aquellas consultas poco frecuentes sin afectar sustancialmente a las necesidades de almacenamiento del cubo.</span><span class="sxs-lookup"><span data-stu-id="ceb07-138">By using the wizard to tune a cube's aggregation you can increase responsiveness to frequent queries and decrease responsiveness to infrequent queries without significantly affecting the storage needed for the cube.</span></span>  
  
 <span data-ttu-id="ceb07-139">Las agregaciones se diseñan con los asistentes, pero no se calculan hasta que se procesa la partición para la que se han diseñado.</span><span class="sxs-lookup"><span data-stu-id="ceb07-139">Aggregations are designed by using the wizards but are not actually calculated until the partition for which the aggregations are designed is processed.</span></span> <span data-ttu-id="ceb07-140">Una vez creada la agregación, si cambia la estructura de un cubo o se agregan o cambian datos de las tablas de origen de un cubo, suele ser necesario revisar las agregaciones del cubo y volver a procesarlo.</span><span class="sxs-lookup"><span data-stu-id="ceb07-140">After the aggregation has been created, if the structure of a cube ever changes, or if data is added to or changed in a cube's source tables, it is usually necessary to review the cube's aggregations and process the cube again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb07-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ceb07-141">See Also</span></span>  
 [<span data-ttu-id="ceb07-142">Procesamiento y modos de almacenamiento de particiones</span><span class="sxs-lookup"><span data-stu-id="ceb07-142">Partition Storage Modes and Processing</span></span>](partitions-partition-storage-modes-and-processing.md)  
  
  