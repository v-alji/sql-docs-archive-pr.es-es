---
title: Orígenes de datos en modelos multidimensionales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- metadata [Analysis Services]
- Analysis Services objects, data sources
- storing data [Analysis Services], data sources
- data sources [Analysis Services], about data sources
- security [Analysis Services], data sources
- data sources [Analysis Services]
- storage [Analysis Services], data sources
ms.assetid: a16469d9-9d53-4e35-9982-fc06327a9d33
author: minewiskan
ms.author: owend
ms.openlocfilehash: 41386c1c7abb0324aa17df24b3c427ca8cbb5615
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676222"
---
# <a name="data-sources-in-multidimensional-models"></a><span data-ttu-id="fe2c1-102">Orígenes de datos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="fe2c1-102">Data Sources in Multidimensional Models</span></span>
  <span data-ttu-id="fe2c1-103">Todos los datos que se importan o se cargan en un modelo multidimensional se originan en un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-103">All data that you import or load into a multidimensional model originates from an external data source.</span></span> <span data-ttu-id="fe2c1-104">Normalmente, los datos de origen son de un almacenamiento de datos diseñado para el informe de errores, pero pueden proceder de cualquier base de datos relacional a la que se acceda directa o indirectamente mediante un intermediario, como un paquete de [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe2c1-104">Typically, source data is from a data warehouse designed for reporting purposes, but it could come from any relational database that is accessed directly or indirectly through an intermediary, such as an [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span>  
  
 <span data-ttu-id="fe2c1-105">Un objeto de **origen de datos** en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] especifica una conexión directa a un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-105">A **data source** object in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] specifies a direct connection to an external data source.</span></span> <span data-ttu-id="fe2c1-106">Además de la ubicación física, un objeto de origen de datos especifica la cadena de conexión, el proveedor de datos, las credenciales y otras propiedades que controlan el comportamiento de la conexión.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-106">In addition to physical location, a data source object specifies the connection string, data provider, credentials, and other properties that control connection behavior.</span></span>  
  
 <span data-ttu-id="fe2c1-107">La información proporcionada por el objeto de origen de datos se utiliza durante las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe2c1-107">Information provided by the data source object is used during the following operations:</span></span>  
  
-   <span data-ttu-id="fe2c1-108">Obtener información del esquema y otros metadatos utilizados para generar vistas del origen de datos en un modelo.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-108">Get schema information and other metadata used to generate data source views into a model.</span></span>  
  
-   <span data-ttu-id="fe2c1-109">Consultar o cargar los datos en un modelo durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-109">Query or load data into a model during processing.</span></span>  
  
-   <span data-ttu-id="fe2c1-110">Ejecutar consultas con modelos de minería de datos o multidimensionales que usan el modo de almacenamiento ROLAP.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-110">Run queries against multidimensional or data mining models that use ROLAP storage mode.</span></span>  
  
-   <span data-ttu-id="fe2c1-111">Leer o escribir en particiones remotas.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-111">Read or write to remote partitions.</span></span>  
  
-   <span data-ttu-id="fe2c1-112">Conectar a objetos vinculados así como sincronizar desde el destino al origen.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-112">Connect to linked objects, as well as synchronize from target to source.</span></span>  
  
-   <span data-ttu-id="fe2c1-113">Realizar operaciones de reescritura que actualizan los datos de la tabla de hechos almacenados en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-113">Perform write back operations that update fact table data stored in a relational database.</span></span>  
  
 <span data-ttu-id="fe2c1-114">Al generar un modelo multidimensional de abajo arriba, empiece por crear el objeto de origen de datos y luego uśelo para generar el objeto a continuación, una **vista del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-114">When building a multidimensional model from the bottom up, you start by creating the data source object, and then use it to generate the next object, a **data source view**.</span></span> <span data-ttu-id="fe2c1-115">Una vista del origen de datos es la capa de abstracción de datos del modelo.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-115">A data source view is the data abstraction layer in the model.</span></span> <span data-ttu-id="fe2c1-116">Se suele crear tras el objeto de origen de datos, usando el esquema de la base de datos de origen como base.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-116">It is typically created after the data source object, using the schema of the source database as the basis.</span></span> <span data-ttu-id="fe2c1-117">No obstante, puede elegir otras maneras de crear un modelo, por ejemplo, comenzar con cubos y dimensiones y generar el esquema que mejor admite el diseño.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-117">However, you can choose other ways to build a model, including starting with cubes and dimensions, and generating the schema that best supports your design.</span></span>  
  
 <span data-ttu-id="fe2c1-118">Independientemente de cómo se generan, cada modelo requiere al menos un objeto de origen de datos que especifique una conexión al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-118">Regardless of how you build it, each model requires at least one data source object that specifies a connection to source data.</span></span> <span data-ttu-id="fe2c1-119">Puede crear objetos de origen de datos en un único modelo para usar los datos de orígenes diferentes o variar las propiedades de conexión de objetos específicos.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-119">You can create multiple data source objects in a single model to use data from different sources or vary connection properties for specific objects.</span></span>  
  
 <span data-ttu-id="fe2c1-120">Los objetos de origen de datos se pueden administrar independientemente de otros objetos del modelo.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-120">Data source objects can be managed independently of other objects in your model.</span></span> <span data-ttu-id="fe2c1-121">Después de crear un origen de datos, puede cambiar sus propiedades más tarde y después procesar previamente el modelo para asegurarse de que los datos se recuperan de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-121">After you create a data source, you can change its properties later, and then preprocess the model to ensure the data is retrieved correctly.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="fe2c1-122">Temas y tareas relacionados</span><span class="sxs-lookup"><span data-stu-id="fe2c1-122">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="fe2c1-123">Tema</span><span class="sxs-lookup"><span data-stu-id="fe2c1-123">Topic</span></span>|<span data-ttu-id="fe2c1-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe2c1-124">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fe2c1-125">Orígenes de datos admitidos &#40;&#41;de SSAS multidimensionales</span><span class="sxs-lookup"><span data-stu-id="fe2c1-125">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)|<span data-ttu-id="fe2c1-126">Describe los tipos de orígenes de datos que puede usar en un modelo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-126">Describes the types of data sources that can be used in a multidimensional model.</span></span>|  
|[<span data-ttu-id="fe2c1-127">Crear un origen de datos &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="fe2c1-127">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](create-a-data-source-ssas-multidimensional.md)|<span data-ttu-id="fe2c1-128">Explica cómo agregar un objeto de origen de datos a un modelo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-128">Explains how to add a data source object to a multidimensional model.</span></span>|  
|[<span data-ttu-id="fe2c1-129">Eliminar un origen de datos en el Explorador de soluciones &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="fe2c1-129">Delete a Data Source in Solution Explorer &#40;SSAS Multidimensional&#41;</span></span>](delete-a-data-source-in-solution-explorer-ssas-multidimensional.md)|<span data-ttu-id="fe2c1-130">Use este procedimiento para eliminar un objeto de origen de datos de un modelo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-130">Use this procedure to delete a data source object from a multidimensional model.</span></span>|  
|[<span data-ttu-id="fe2c1-131">Establecer propiedades de origen de datos &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="fe2c1-131">Set Data Source Properties &#40;SSAS Multidimensional&#41;</span></span>](set-data-source-properties-ssas-multidimensional.md)|<span data-ttu-id="fe2c1-132">Describe cada propiedad y explica cómo configurar cada una.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-132">Describes each property and explains how to set each one.</span></span>|  
|[<span data-ttu-id="fe2c1-133">Establezca las opciones de suplantación &#40;SSAS - multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="fe2c1-133">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](set-impersonation-options-ssas-multidimensional.md)|<span data-ttu-id="fe2c1-134">Explica cómo configurar opciones en el cuadro de diálogo información de suplantación.</span><span class="sxs-lookup"><span data-stu-id="fe2c1-134">Explains how to configure options in the Impersonation Information dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe2c1-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe2c1-135">See Also</span></span>  
 <span data-ttu-id="fe2c1-136">[Objetos de base de datos &#40;Analysis Services de datos multidimensionales&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="fe2c1-136">[Database Objects &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="fe2c1-137">[Arquitectura lógica &#40;Analysis Services de datos multidimensionales&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="fe2c1-137">[Logical Architecture &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span></span>  
 <span data-ttu-id="fe2c1-138">[Vistas del origen de datos en modelos multidimensionales](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="fe2c1-138">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="fe2c1-139">Orígenes de datos y enlaces &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="fe2c1-139">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](data-sources-and-bindings-ssas-multidimensional.md)  
  
  
