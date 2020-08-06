---
title: Visor y tarea de generación de perfiles de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], about data profiling
- data profiling
- profiling data
ms.assetid: 756840e3-aa09-45cd-9951-1a17af4b5925
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ae15d1cc75f8db04c36a830e44d07800c5aecf75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671625"
---
# <a name="data-profiling-task-and-viewer"></a><span data-ttu-id="feec1-102">Visor y tarea de generación de perfiles de datos</span><span class="sxs-lookup"><span data-stu-id="feec1-102">Data Profiling Task and Viewer</span></span>
  <span data-ttu-id="feec1-103">La tarea de generación de perfiles de datos proporciona la funcionalidad para generar perfiles de datos dentro del proceso de extracción, transformación y carga de datos.</span><span class="sxs-lookup"><span data-stu-id="feec1-103">The Data Profiling task provides data profiling functionality inside the process of extracting, transforming, and loading data.</span></span> <span data-ttu-id="feec1-104">El uso de esta tarea le permitirá:</span><span class="sxs-lookup"><span data-stu-id="feec1-104">By using the Data Profiling task, you can achieve the following benefits:</span></span>  
  
-   <span data-ttu-id="feec1-105">Analizar los datos de origen de forma más eficaz.</span><span class="sxs-lookup"><span data-stu-id="feec1-105">Analyze the source data more effectively</span></span>  
  
-   <span data-ttu-id="feec1-106">Comprender mejor la estructura de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="feec1-106">Understand the source data better</span></span>  
  
-   <span data-ttu-id="feec1-107">Evitar problemas de calidad en los datos antes de incluirlos en el almacenamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="feec1-107">Prevent data quality problems before they are introduced into the data warehouse.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="feec1-108">La tarea de generación de perfiles de datos solo funciona con datos que estén almacenados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="feec1-108">The Data Profiling task works only with data that is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="feec1-109">No funciona con orígenes de datos de otros fabricantes o basados en archivos.</span><span class="sxs-lookup"><span data-stu-id="feec1-109">It does not work with third-party or file-based data sources.</span></span>  
  
## <a name="data-profiling-overview"></a><span data-ttu-id="feec1-110">Información general de generación de perfiles de datos</span><span class="sxs-lookup"><span data-stu-id="feec1-110">Data Profiling Overview</span></span>  
 <span data-ttu-id="feec1-111">La calidad de los datos es importante en todos los negocios.</span><span class="sxs-lookup"><span data-stu-id="feec1-111">Data quality is important to every business.</span></span> <span data-ttu-id="feec1-112">A medida que las empresas desarrollan sistemas analíticos y de inteligencia empresarial sobre sus sistemas transaccionales, la fiabilidad de los indicadores clave de rendimiento y de las predicciones de la minería de datos dependerán por completo de la validez de los datos en los que se basan.</span><span class="sxs-lookup"><span data-stu-id="feec1-112">As enterprises build analytical and business intelligence systems on top of their transactional systems, the reliability of key performance indicators and of data mining predictions depends completely on the validity of the data on which they are based.</span></span> <span data-ttu-id="feec1-113">Pero aunque la importancia de disponer de datos válidos para la toma de decisiones empresariales está aumentando, también lo hace en la misma medida el desafío de garantizar la validez de los mismos.</span><span class="sxs-lookup"><span data-stu-id="feec1-113">But although the importance of valid data for business decision-making is increasing, the challenge of making sure of this data's validity is also increasing.</span></span> <span data-ttu-id="feec1-114">La información fluye de forma ininterrumpida en la empresa procedente de diversos sistemas y orígenes, y de un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="feec1-114">Data is streaming into the enterprise constantly from diverse systems and sources, and a large numbers of users.</span></span>  
  
 <span data-ttu-id="feec1-115">Las métricas para determinar la calidad de los datos pueden ser difíciles de definir porque son específicas del dominio o de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="feec1-115">Metrics for data quality can be difficult to define because they are specific to the domain or the application.</span></span> <span data-ttu-id="feec1-116">Un método común para definir la calidad de los datos es la generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="feec1-116">One common approach to defining data quality is data profiling.</span></span>  
  
 <span data-ttu-id="feec1-117">Un perfil de datos es una colección de estadísticas acumuladas sobre los datos que puede incluir la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="feec1-117">A data profile is a collection of aggregate statistics about data that might include the following:</span></span>  
  
-   <span data-ttu-id="feec1-118">El número de filas de la tabla de clientes.</span><span class="sxs-lookup"><span data-stu-id="feec1-118">The number of rows in the Customer table.</span></span>  
  
-   <span data-ttu-id="feec1-119">El número de valores distintos en la columna Estado.</span><span class="sxs-lookup"><span data-stu-id="feec1-119">The number of distinct values in the State column.</span></span>  
  
-   <span data-ttu-id="feec1-120">El número de valores nulos o ausentes en la columna Código postal.</span><span class="sxs-lookup"><span data-stu-id="feec1-120">The number of null or missing values in the Zip column.</span></span>  
  
-   <span data-ttu-id="feec1-121">La distribución de los valores en la columna Ciudad.</span><span class="sxs-lookup"><span data-stu-id="feec1-121">The distribution of values in the City column.</span></span>  
  
-   <span data-ttu-id="feec1-122">La intensidad de la dependencia funcional entre la columna Estado y la columna Código postal; es decir, el estado siempre tendría que ser el mismo para un valor de código postal determinado.</span><span class="sxs-lookup"><span data-stu-id="feec1-122">The strength of the functional dependency of the State column on the Zip column-that is, the state should always be the same for a given zip value.</span></span>  
  
 <span data-ttu-id="feec1-123">Las estadísticas proporcionadas por un perfil de datos le ofrecen la información que necesita para minimizar de forma eficaz los problemas de calidad derivados del uso de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="feec1-123">The statistics that a data profile provides gives you the information that you need in order to effectively minimize the quality issues that might occur from using the source data.</span></span>  
  
## <a name="integration-services-and-data-profiling"></a><span data-ttu-id="feec1-124">Integration Services y generación de perfiles de datos</span><span class="sxs-lookup"><span data-stu-id="feec1-124">Integration Services and Data Profiling</span></span>  
 <span data-ttu-id="feec1-125">En [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], el proceso de generación de perfiles de datos consta de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="feec1-125">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the data profiling process consist of the following steps:</span></span>  
  
 <span data-ttu-id="feec1-126">**Paso 1: Preparación de la tarea de generación de perfiles de datos**</span><span class="sxs-lookup"><span data-stu-id="feec1-126">**Step 1: Setting up the Data Profiling Task**</span></span>  
 <span data-ttu-id="feec1-127">La tarea de generación de perfiles de datos es una tarea que se utiliza para configurar los perfiles que se desean calcular.</span><span class="sxs-lookup"><span data-stu-id="feec1-127">The Data Profiling task is a task that you use to configure the profiles that you want to compute.</span></span> <span data-ttu-id="feec1-128">A continuación, se ejecuta el paquete que contiene la tarea de generación de perfiles de datos para calcular los perfiles.</span><span class="sxs-lookup"><span data-stu-id="feec1-128">You then run the package that contains the Data Profiling task to compute the profiles.</span></span> <span data-ttu-id="feec1-129">La tarea guarda el perfil generado en formato XML en un archivo o en una variable de paquete.</span><span class="sxs-lookup"><span data-stu-id="feec1-129">The task saves the profile output in XML format to a file or a package variable.</span></span>  
  
 <span data-ttu-id="feec1-130">**Para obtener más información:** [Configuración de la tarea de generación de perfiles de datos](data-profiling-task.md)</span><span class="sxs-lookup"><span data-stu-id="feec1-130">**For more information:** [Setup of the Data Profiling Task](data-profiling-task.md)</span></span>  
  
 <span data-ttu-id="feec1-131">**Paso 2: Revisión de los perfiles calculados por la tarea de generación de perfiles de datos**</span><span class="sxs-lookup"><span data-stu-id="feec1-131">**Step 2: Reviewing the Profiles that the Data Profiling Task Computes**</span></span>  
 <span data-ttu-id="feec1-132">Para ver los perfiles de datos calculados por la tarea de generación de perfiles de datos, se envía la salida a un archivo y, a continuación, se utiliza el Visor de perfil de datos.</span><span class="sxs-lookup"><span data-stu-id="feec1-132">To view the data profiles that the Data Profiling task computes, you send the output to a file, and then you use the Data Profile Viewer.</span></span> <span data-ttu-id="feec1-133">Este visor es una utilidad independiente que muestra el perfil generado tanto en formato resumen como en formato detallado, y que también permite la obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="feec1-133">This viewer is a stand-alone utility that displays the profile output in both summary and detail format with optional drilldown capability.</span></span>  
  
 <span data-ttu-id="feec1-134">**Para obtener más información:** [Visor de perfil de datos](data-profile-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="feec1-134">**For more information:** [Data Profile Viewer](data-profile-viewer.md)</span></span>  
  
### <a name="addition-of-conditional-logic-to-the-data-profiling-workflow"></a><span data-ttu-id="feec1-135">Inclusión de la lógica condicional al flujo de trabajo que genera perfiles de datos</span><span class="sxs-lookup"><span data-stu-id="feec1-135">Addition of Conditional Logic to the Data Profiling Workflow</span></span>  
 <span data-ttu-id="feec1-136">La tarea de generación de perfiles de datos no tiene características integradas que le permitan utilizar lógica condicional para conectar esta tarea a las tareas de nivel inferior según el perfil generado.</span><span class="sxs-lookup"><span data-stu-id="feec1-136">The Data Profiling task does not have built-in features that allow you to use conditional logic to connect this task to downstream tasks based on the profile output.</span></span> <span data-ttu-id="feec1-137">Sin embargo, puede agregar fácilmente esta lógica, con una pequeña cantidad de programación, en una tarea Script.</span><span class="sxs-lookup"><span data-stu-id="feec1-137">However, you can easily add this logic, with a small amount of programming, in a Script task.</span></span> <span data-ttu-id="feec1-138">Por ejemplo, la tarea Script puede realizar una consulta XPath en el archivo de salida de la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="feec1-138">For example, the Script task could perform an XPath query against the output file of the Data Profiling task.</span></span> <span data-ttu-id="feec1-139">La consulta podría determinar si el porcentaje de valores nulos en una columna determinada supera un cierto umbral.</span><span class="sxs-lookup"><span data-stu-id="feec1-139">The query could determine whether the percentage of null values in a particular column exceeds a certain threshold.</span></span> <span data-ttu-id="feec1-140">Si el porcentaje supera el umbral, puede interrumpir el paquete y resolver el problema en los datos de origen antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="feec1-140">If the percentage exceeds the threshold, you could interrupt the package and resolve the problem in the source data before continuing.</span></span> <span data-ttu-id="feec1-141">Para obtener más información, vea [Incorporar una tarea de generación de perfiles de datos en un flujo de trabajo de paquetes](incorporate-a-data-profiling-task-in-package-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="feec1-141">For more information, see [Incorporate a Data Profiling Task in Package Workflow](incorporate-a-data-profiling-task-in-package-workflow.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="feec1-142">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="feec1-142">Related Content</span></span>  
 [<span data-ttu-id="feec1-143">Esquema del generador de perfiles de datos</span><span class="sxs-lookup"><span data-stu-id="feec1-143">Data Profiler Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=251524)  
  
  
