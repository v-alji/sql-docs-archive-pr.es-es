---
title: Proyectos de calidad de datos (DQS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a43fc9c0-19b6-414a-8661-4c7c55e0c03e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 471d528144b6687ffa3aeedb82cf479817c4edc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669861"
---
# <a name="data-quality-projects-dqs"></a><span data-ttu-id="f1381-102">Proyectos de calidad de datos (DQS)</span><span class="sxs-lookup"><span data-stu-id="f1381-102">Data Quality Projects (DQS)</span></span>
  <span data-ttu-id="f1381-103">Un proyecto de calidad de datos de [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) utiliza una base de conocimiento para mejorar la calidad de los datos de origen mediante la realización de actividades de *limpieza de datos* y *búsqueda de coincidencias de datos* , y la posterior exportación de los datos resultantes a una base de datos de SQL Server o a un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="f1381-103">A data quality project in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) is a means of using a knowledge base to improve the quality of your source data by performing *data cleansing* and *data matching* activities, and then exporting the resultant data to a SQL Server database or a .csv file.</span></span> <span data-ttu-id="f1381-104">Puede crear un proyecto de calidad de datos como un proyecto de limpieza o como un proyecto de búsqueda de coincidencias para realizar las actividades respectivas.</span><span class="sxs-lookup"><span data-stu-id="f1381-104">You can create a data quality project as a cleansing project or a matching project to perform respective activities.</span></span> <span data-ttu-id="f1381-105">Los proyectos de limpieza y de búsqueda de coincidencias se pueden ejecutar usando la misma base de conocimiento, ya que el conocimiento de estos procesos se puede generar en la misma base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="f1381-105">Cleansing and matching projects can be run using the same knowledge base, because knowledge for data cleansing and matching can be built into the same knowledge base.</span></span>  
  
 <span data-ttu-id="f1381-106">Un proyecto de calidad de datos tiene las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1381-106">A data quality project has the following benefits:</span></span>  
  
-   <span data-ttu-id="f1381-107">Permite realizar la limpieza de datos en los datos de origen utilizando el conocimiento de una base de conocimiento de DQS.</span><span class="sxs-lookup"><span data-stu-id="f1381-107">Enables you to perform data cleansing on your source data by using the knowledge in a DQS knowledge base.</span></span>  
  
-   <span data-ttu-id="f1381-108">Permite realizar la búsqueda de coincidencias de datos en los datos de origen utilizando la directiva de coincidencia de una base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="f1381-108">Enables you to perform data matching on your source data by using the matching policy in a knowledge base.</span></span>  
  
-   <span data-ttu-id="f1381-109">Proporciona un asistente que le guiará durante las actividades de limpieza y búsqueda de coincidencias, y le permitirá exportar los datos al lugar de su elección: una base de datos de SQL Server o un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="f1381-109">Provides a wizard to guide you through the cleansing and matching activities, and export the data as per your selection to a SQL Server database or to a .csv file.</span></span> <span data-ttu-id="f1381-110">El administrador de datos puede utilizar el proyecto de calidad de datos para ejecutar y controlar los pasos de las actividades de limpieza (tanto la asistida por PC como la interactiva) y búsqueda de coincidencias.</span><span class="sxs-lookup"><span data-stu-id="f1381-110">The data steward can use the data quality project to run and control the computer-assisted/interactive cleansing and data matching steps.</span></span>  
  
##  <a name="data-quality-project-cleansing-activity"></a><a name="Cleansing"></a><span data-ttu-id="f1381-111">Proyecto de calidad de datos: actividad de limpieza</span><span class="sxs-lookup"><span data-stu-id="f1381-111">Data Quality Project: Cleansing Activity</span></span>  
 <span data-ttu-id="f1381-112">Un proyecto de calidad de datos de limpieza permite limpiar los datos de origen basándose en una base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="f1381-112">A cleansing data quality project enables you to cleanse your source data based on a knowledge base.</span></span> <span data-ttu-id="f1381-113">La actividad de limpieza de datos de DQS es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="f1381-113">The data cleansing activity in DQS is a two-step process:</span></span>  
  
1.  <span data-ttu-id="f1381-114">Un proceso de limpieza de datos *asistido por PC* que analiza los datos de origen comparándolos con el conocimiento de la base de conocimiento y propone cambios.</span><span class="sxs-lookup"><span data-stu-id="f1381-114">A *computer-assisted* data cleansing process that analyzes source data against the knowledge in the knowledge base, and proposes changes.</span></span> <span data-ttu-id="f1381-115">DQS organiza los datos procesados por categorías (sugerido, nuevo, no válido, corregido y correcto) y los muestra al usuario para su procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="f1381-115">The processed data is categorized (suggested, new, invalid, corrected, and correct) by DQS, and displayed to the user for further processing.</span></span>  
  
2.  <span data-ttu-id="f1381-116">Un proceso de limpieza *interactivo* que permite al administrador de datos aprobar, rechazar o modificar los datos propuestos por el proceso de limpieza de datos asistido por PC.</span><span class="sxs-lookup"><span data-stu-id="f1381-116">An *interactive* cleansing process that enables the data steward to approve, reject, or modify the data proposed by the computer-assisted data cleansing process.</span></span>  
  
 <span data-ttu-id="f1381-117">Para obtener información detallada acerca de la actividad de limpieza en un proyecto de calidad de datos, vea [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="f1381-117">For detailed information about the cleansing activity in a data quality project, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
##  <a name="data-quality-project-matching-activity"></a><a name="Matching"></a><span data-ttu-id="f1381-118">Proyecto de calidad de datos: actividad de coincidencia</span><span class="sxs-lookup"><span data-stu-id="f1381-118">Data Quality Project: Matching Activity</span></span>  
 <span data-ttu-id="f1381-119">Un proyecto de calidad de datos de búsqueda de coincidencias permite realizar la actividad de búsqueda de coincidencias basándose en la directiva de coincidencia de una base de conocimiento para evitar la duplicación de datos; para ello, se identifican las coincidencias exactas o aproximadas, lo que permite quitar los datos duplicados.</span><span class="sxs-lookup"><span data-stu-id="f1381-119">A matching data quality project enables you to perform matching activity based on matching policy in a knowledge base to prevent data duplication by identifying exact and approximate matches, and thereby enabling you to remove duplicate data.</span></span> <span data-ttu-id="f1381-120">Se recomienda limpiar los datos antes de ejecutar en ellos la actividad de búsqueda de coincidencias.</span><span class="sxs-lookup"><span data-stu-id="f1381-120">It is recommended that you cleanse your data before running matching on it.</span></span> <span data-ttu-id="f1381-121">Para ello:</span><span class="sxs-lookup"><span data-stu-id="f1381-121">To do so:</span></span>  
  
1.  <span data-ttu-id="f1381-122">Cree un proyecto de calidad de los datos, seleccione la actividad **Limpieza** , complete la actividad de limpieza de datos con los datos de origen y, a continuación expórtelos a una tabla de una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1381-122">Create a data quality project, select the **Cleansing** activity, complete the data cleansing activity on your source data, and then export it to a table in a SQL Server database.</span></span>  
  
2.  <span data-ttu-id="f1381-123">Cree otro proyecto de calidad de datos utilizando una base de conocimiento que contenga una directiva de coincidencia, seleccione la actividad **Coincidencia** y, a continuación, en la página **Asignación** , seleccione la base de datos y la tabla donde exportó los datos que limpió en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f1381-123">Create another data quality project by using a knowledge base that contains a matching policy, select the **Matching** activity, and then in the **Map** page, select the database and the table where you exported the cleansed data in step 1.</span></span>  
  
3.  <span data-ttu-id="f1381-124">Complete la actividad de búsqueda de coincidencias con los datos limpios.</span><span class="sxs-lookup"><span data-stu-id="f1381-124">Complete the matching activity on the cleansed data.</span></span>  
  
 <span data-ttu-id="f1381-125">Para obtener información detallada acerca de la actividad de búsqueda de coincidencias en un proyecto de calidad de datos, vea [Data Matching](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="f1381-125">For detailed information about the matching activity in a data quality project, see [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
##  <a name="data-profiling-and-notifications"></a><a name="ProfilingNotification"></a><span data-ttu-id="f1381-126">Generación de perfiles de datos y notificaciones</span><span class="sxs-lookup"><span data-stu-id="f1381-126">Data Profiling and Notifications</span></span>  
 <span data-ttu-id="f1381-127">Mientras ejecuta las actividades de búsqueda de coincidencias y limpieza en un proyecto de calidad de datos, puede ver estadísticas e información en tiempo real de los datos que DQS está procesando.</span><span class="sxs-lookup"><span data-stu-id="f1381-127">While running the cleansing and matching activities in a data quality project, you can see real-time statistics and information about the data that is being processed by DQS.</span></span> <span data-ttu-id="f1381-128">El proceso de generación de perfiles de datos le ayuda a evaluar la eficacia de los procesos de limpieza y búsqueda de coincidencias, y le permite determinar en qué medida le han ayudado estos procesos a mejorar la calidad de los datos.</span><span class="sxs-lookup"><span data-stu-id="f1381-128">Data profiling helps you assess the effectiveness of the cleansing and matching processes, and you can potentially determine the extent to which data cleansing or matching helped improve the data quality.</span></span> <span data-ttu-id="f1381-129">El proceso de generación de perfiles de DQS proporciona dos dimensiones de calidad de datos: *integridad* (la medida en que los datos están presentes) y *precisión* (la medida en que los datos se pueden utilizar para su uso previsto).</span><span class="sxs-lookup"><span data-stu-id="f1381-129">DQS profiling provides two data-quality dimensions: *completeness* (the extent to which data is present) and *accuracy* (the extent to which data can be used for its intended use).</span></span> <span data-ttu-id="f1381-130">Además, en función de la información de los perfiles de datos, el usuario verá notificaciones sobre las medidas que puede tomar para mejorar las operaciones de limpieza de datos y búsqueda de coincidencias de datos.</span><span class="sxs-lookup"><span data-stu-id="f1381-130">Further, based on the data profiling information, notifications are displayed to the user on the actions that can be taken to enhance the data cleansing and data matching operations.</span></span> <span data-ttu-id="f1381-131">Para obtener información detallada acerca de las notificaciones y la generación de perfiles de datos, vea [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="f1381-131">For detailed information about data profiling and notifications, see [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f1381-132">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f1381-132">Related Tasks</span></span>  
  
|<span data-ttu-id="f1381-133">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="f1381-133">Task Description</span></span>|<span data-ttu-id="f1381-134">Tema</span><span class="sxs-lookup"><span data-stu-id="f1381-134">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="f1381-135">Describe cómo crear un proyecto de calidad de datos.</span><span class="sxs-lookup"><span data-stu-id="f1381-135">Describes how to create a data quality project.</span></span>|[<span data-ttu-id="f1381-136">Crear un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="f1381-136">Create a Data Quality Project</span></span>](../../2014/data-quality-services/create-a-data-quality-project.md)|  
|<span data-ttu-id="f1381-137">Describe cómo administrar (abrir, desbloquear, cambiar el nombre y eliminar) un proyecto de calidad de datos.</span><span class="sxs-lookup"><span data-stu-id="f1381-137">Describes how to manage (open, unlock, rename, and delete) a data quality project.</span></span>|[<span data-ttu-id="f1381-138">Administrar &#40;abrir, desbloquear, cambiar el nombre y eliminar&#41; un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="f1381-138">Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project</span></span>](../../2014/data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md)|  
|<span data-ttu-id="f1381-139">Describe cómo abrir un proyecto de Integration Services en [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1381-139">Describes how to open an Integration Services project in [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>|[<span data-ttu-id="f1381-140">Abrir proyectos de Integration Services en Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="f1381-140">Open Integration Services Projects in Data Quality Client</span></span>](../../2014/data-quality-services/open-integration-services-projects-in-data-quality-client.md)|  
  
## <a name="see-also"></a><span data-ttu-id="f1381-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1381-141">See Also</span></span>  
 [<span data-ttu-id="f1381-142">Bases de conocimiento y dominios de DQS</span><span class="sxs-lookup"><span data-stu-id="f1381-142">DQS Knowledge Bases and Domains</span></span>](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md)  
  
  