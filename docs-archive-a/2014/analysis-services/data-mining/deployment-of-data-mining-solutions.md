---
title: Implementación de soluciones de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], deploying
- deploying [Analysis Services], production environments
- deploying [Analysis Services - data mining]
- solutions [Analysis Services], deploying
- models [Analysis Services], data mining
ms.assetid: d83effc7-437d-42e9-8ac3-b65f79e27043
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5764be2f7530add2fa4cb028b288be69598bb95c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676259"
---
# <a name="deployment-of-data-mining-solutions"></a><span data-ttu-id="703a6-102">Implementación de soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="703a6-102">Deployment of Data Mining Solutions</span></span>
  <span data-ttu-id="703a6-103">El último paso del proceso de minería de datos consiste en implementar los modelos en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="703a6-103">The last step in the data mining process is to deploy the models to a production environment.</span></span> <span data-ttu-id="703a6-104">La implementación es importante porque hace que los modelos estén a disposición de los usuarios para que pueda realizar cualquiera de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="703a6-104">Deployment is important because it makes the models available to users so that you can perform any of the following tasks:</span></span>  
  
-   <span data-ttu-id="703a6-105">Utilice los modelos para crear predicciones y tomar decisiones empresariales.</span><span class="sxs-lookup"><span data-stu-id="703a6-105">Use the models to create predictions and make business decisions.</span></span> <span data-ttu-id="703a6-106">Para obtener información acerca de las herramientas que puede utilizar para crear consultas, vea [interfaces de consulta de minería de datos](data-mining-query-tools.md).</span><span class="sxs-lookup"><span data-stu-id="703a6-106">For information about the tools you can use to create queries, see [Data Mining Query Interfaces](data-mining-query-tools.md).</span></span>  
  
-   <span data-ttu-id="703a6-107">Incrustar la funcionalidad de minería de datos directamente en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="703a6-107">Embed data mining functionality directly into an application.</span></span> <span data-ttu-id="703a6-108">Puede incluir Objetos de administración de análisis (AMO) o un ensamblado que contenga un conjunto de objetos que la aplicación pueda utilizar para crear, cambiar, procesar y eliminar estructuras y modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="703a6-108">You can include Analysis Management Objects (AMO) or an assembly that contains a set of objects that your application can use to create, alter, process, and delete mining structures and mining models.</span></span>  
  
-   <span data-ttu-id="703a6-109">Crear informes que permiten a los usuarios solicitar predicciones, ver tendencias o comparar modelos.</span><span class="sxs-lookup"><span data-stu-id="703a6-109">Create reports that let users request predictions, view trends, or compare models.</span></span>  
  
 <span data-ttu-id="703a6-110">En esta sección se proporciona información detallada sobre las opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="703a6-110">This section provides detailed information about deployment options.</span></span>  
  
 [<span data-ttu-id="703a6-111">Requisitos para la implementación de las soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="703a6-111">Requirements for Deployment of Data Mining Solutions</span></span>](#bkmk_Reqs)  
  
 [<span data-ttu-id="703a6-112">Implementar una solución relacional</span><span class="sxs-lookup"><span data-stu-id="703a6-112">Deploying a Relational Solution</span></span>](#bkmk_RelationalSltn)  
  
 [<span data-ttu-id="703a6-113">Implementar una solución multidimensional</span><span class="sxs-lookup"><span data-stu-id="703a6-113">Deploying a Multidimensional Solution</span></span>](#bkmk_MDSltn)  
  
 [<span data-ttu-id="703a6-114">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="703a6-114">Related Resources</span></span>](#bkmk_Resources)  
  
## <a name="in-this-section"></a><span data-ttu-id="703a6-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="703a6-115">In This Section</span></span>  
 [<span data-ttu-id="703a6-116">Implementar soluciones de minería de datos para versiones anteriores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="703a6-116">Deploy a Data Mining Solution to Previous Versions of SQL Server</span></span>](deploy-a-data-mining-solution-to-previous-versions-of-sql-server.md)  
  
 [<span data-ttu-id="703a6-117">Exportar e importar objetos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="703a6-117">Export and Import Data Mining Objects</span></span>](export-and-import-data-mining-objects.md)  
  
##  <a name="requirements-for-deployment-of-data-mining-solutions"></a><a name="bkmk_Reqs"></a><span data-ttu-id="703a6-118">Requisitos para la implementación de soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="703a6-118">Requirements for Deployment of Data Mining Solutions</span></span>  
 <span data-ttu-id="703a6-119">La instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en la que se implementa la solución debe ejecutarse en un modo que admita objetos multidimensionales y objetos de minería de datos; es decir, no puede implementar objetos de minería de datos en una instancia que hospede modelos tabulares o datos de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="703a6-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="703a6-120">Por consiguiente, al crear una solución de minería de datos en Visual Studio, asegúrese de utilizar la plantilla **Proyecto multidimensional y de minería de datos de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="703a6-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="703a6-121">Al implementar la solución, los objetos utilizados para la minería de datos se crean en la instancia especificada de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , en una base de datos con el mismo nombre que el archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="703a6-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
###  <a name="deploying-a-relational-solution"></a><a name="bkmk_RelationalSltn"></a><span data-ttu-id="703a6-122">Implementar una solución relacional</span><span class="sxs-lookup"><span data-stu-id="703a6-122">Deploying a Relational Solution</span></span>  
 <span data-ttu-id="703a6-123">Al implementar una solución relacional de minería de datos, los objetos necesarios de minería de datos se crean dentro de una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y los objetos se procesan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="703a6-123">When you deploy a relational data mining solution, the required data mining objects are created within a new [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, and the objects are processed by default.</span></span> <span data-ttu-id="703a6-124">Puede cambiar las opciones de procesamiento con la propiedad de configuración **Opción de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="703a6-124">You can change processing options by using the configuration property, **Processing Option**.</span></span> <span data-ttu-id="703a6-125">Para obtener más información, consulte [Configurar las propiedades de un proyecto de Analysis Services &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="703a6-125">For more information, see [Configure Analysis Services Project Properties &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md).</span></span>  
  
 <span data-ttu-id="703a6-126">De forma predeterminada, solo los cambios incrementales se implementan cada vez.</span><span class="sxs-lookup"><span data-stu-id="703a6-126">By default, only incremental changes are deployed each time.</span></span> <span data-ttu-id="703a6-127">En otras palabras, puede modificar un modelo de minería de datos y, cuando vuelva a implementar el proyecto, solo el modelo de minería de datos se actualizaría.</span><span class="sxs-lookup"><span data-stu-id="703a6-127">In other words, you can modify a mining model, and when you re-deploy the project, only that mining model would be updated.</span></span> <span data-ttu-id="703a6-128">Sin embargo, si tiene varios clientes que modifican la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , esto puede provocar errores.</span><span class="sxs-lookup"><span data-stu-id="703a6-128">However, if you have multiple clients editing the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, this can lead to errors.</span></span> <span data-ttu-id="703a6-129">Para cambiar el modo de implementación predeterminado para actualizar la base de datos completa al implementar la solución, cambie la propiedad **Modo de implementación**</span><span class="sxs-lookup"><span data-stu-id="703a6-129">To change the default deployment mode so that the entire database is refreshed when you deploy the solution, change the **Deployment Mode** property</span></span>  
  
 <span data-ttu-id="703a6-130">En una solución relacional de minería de datos, los únicos objetos que deben implementarse son la definición del origen de datos, cualquier vista del origen de datos que se usara, las estructuras de minería de datos y todos los modelos de minería de datos dependientes.</span><span class="sxs-lookup"><span data-stu-id="703a6-130">In a relational data mining solution, the only objects that must be deployed are the data source definition, any data source views that were used, the mining structures, and all dependent mining models.</span></span>  
  
###  <a name="deploying-a-multidimensional-solution"></a><a name="bkmk_MDSltn"></a><span data-ttu-id="703a6-131">Implementar una solución multidimensional</span><span class="sxs-lookup"><span data-stu-id="703a6-131">Deploying a Multidimensional Solution</span></span>  
 <span data-ttu-id="703a6-132">Al implementar una solución de minería de datos multidimensional, esta solución crea los objetos de minería de datos en la misma base de datos que el cubo de origen.</span><span class="sxs-lookup"><span data-stu-id="703a6-132">When you deploy a multidimensional data mining solution, this solution creates your data mining objects within the same database as the source cube.</span></span>  
  
 <span data-ttu-id="703a6-133">Cuando se procesa la estructura o el modelo de minería de datos, debe procesar también el cubo de origen.</span><span class="sxs-lookup"><span data-stu-id="703a6-133">When you process the mining structure or mining model, you must process the source cube as well.</span></span> <span data-ttu-id="703a6-134">Por esta razón, al implementar una solución que utiliza los modelos de minería de datos OLAP puede tardarse más que en las soluciones que relacionales de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="703a6-134">For this reason, deploying a solution that uses OLAP mining models can take longer than relational data mining solutions.</span></span>  
  
 <span data-ttu-id="703a6-135">Los objetos de minería de datos normalmente usan los mismos orígenes de datos y vistas del origen de datos que se utilizan para el cubo.</span><span class="sxs-lookup"><span data-stu-id="703a6-135">Typically data mining objects also use the same data sources and data source views that are used for the cube.</span></span> <span data-ttu-id="703a6-136">Sin embargo, puede agregar orígenes de datos y vistas del origen de datos que estén destinadas específicamente a la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="703a6-136">However, you can add data sources and data source views that are targeted specifically to data mining.</span></span> <span data-ttu-id="703a6-137">Por ejemplo, un cubo normalmente no contendría datos sobre los posibles clientes o datos externos que no se usen en los objetos multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="703a6-137">For example, typically a cube would not contain data about prospective clients, or external data not used in the multidimensional objects.</span></span>  
  
##  <a name="related-resources"></a><a name="bkmk_Resources"></a><span data-ttu-id="703a6-138">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="703a6-138">Related Resources</span></span>  
 [<span data-ttu-id="703a6-139">Mover objetos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="703a6-139">Moving Data Mining Objects</span></span>](moving-data-mining-objects.md)  
  
 <span data-ttu-id="703a6-140">Si el modelo se basa solo en datos relacionales, exportar e importar objetos mediante DMX es la forma más sencilla de mover los modelos.</span><span class="sxs-lookup"><span data-stu-id="703a6-140">If your model is based on relational data only, exporting and importing objects using DMX is the easiest way to move models.</span></span>  
  
 [<span data-ttu-id="703a6-141">Mover una base de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="703a6-141">Move an Analysis Services Database</span></span>](../multidimensional-models/move-an-analysis-services-database.md)  
  
 <span data-ttu-id="703a6-142">Cuando los modelos utilizan un cubo como origen de datos, consulte este tema para obtener más información sobre cómo mover los modelos y sus datos de cubo correspondientes.</span><span class="sxs-lookup"><span data-stu-id="703a6-142">When models use a cube as a data source, refer to this topic for more information about how to move models and their supporting cube data.</span></span>  
  
 [<span data-ttu-id="703a6-143">Implementar proyectos de Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="703a6-143">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](../multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
 <span data-ttu-id="703a6-144">Proporciona información general sobre la implementación de los proyectos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y describe las propiedades que puede establecer como parte de la configuración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="703a6-144">Provides general information about deployment of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects, and describes the properties that you can set as part of the project configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703a6-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="703a6-145">See Also</span></span>  
 <span data-ttu-id="703a6-146">[Procesamiento de objetos del modelo multidimensional](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="703a6-146">[Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span></span>  
 <span data-ttu-id="703a6-147">[Interfaces de consulta de minería de datos](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="703a6-147">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="703a6-148">Requisitos y consideraciones de procesamiento &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="703a6-148">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](processing-requirements-and-considerations-data-mining.md)  
  
  
