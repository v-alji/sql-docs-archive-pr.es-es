---
title: SQL Server de complementos de minería de datos para Office | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c9021a19-2c19-4f0a-a293-5f7e0ac2524c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b64d0c8728e4752d0d5831562d43646e29f7d723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662347"
---
# <a name="sql-server-data-mining-add-ins-for-office"></a><span data-ttu-id="12801-102">Complementos de minería de datos de SQL Server para Office</span><span class="sxs-lookup"><span data-stu-id="12801-102">SQL Server Data Mining Add-Ins for Office</span></span>
  [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] <span data-ttu-id="12801-103">Complementos de minería de datos para Office es un conjunto ligero de herramientas para análisis predictivos que permite utilizar datos de Excel para generar modelos analíticos para la predicción, recomendación o exploración.</span><span class="sxs-lookup"><span data-stu-id="12801-103">Data Mining Add-ins for Office is a lightweight set of tools for predictive analytics that lets you use data in Excel to build analytical models for prediction, recommendation, or exploration.</span></span>  
  
 <span data-ttu-id="12801-104">Los asistentes y las herramientas de administración de datos de los complementos proporcionan instrucciones paso a paso para estas tareas comunes de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="12801-104">The wizards and data management tools in the add-ins provide step-by-step instruction for these common data mining tasks:</span></span>  
  
-   <span data-ttu-id="12801-105">**Organizar y limpiar los datos antes del modelado.**</span><span class="sxs-lookup"><span data-stu-id="12801-105">**Organize and clean your data prior to modeling.**</span></span> <span data-ttu-id="12801-106">Utilice los datos almacenados en Excel o en cualquier origen de datos de Excel.</span><span class="sxs-lookup"><span data-stu-id="12801-106">Use data stored in Excel or any Excel data source.</span></span> <span data-ttu-id="12801-107">Puede crear y guardar las conexiones para reutilizar los orígenes de datos y repetir experimentos o volver a entrenar los modelos.</span><span class="sxs-lookup"><span data-stu-id="12801-107">You can create and save connections to re-use data sources, repeat experiments, or re-train models.</span></span>  
  
-   <span data-ttu-id="12801-108">**Generar perfiles, obtener muestras y preparar los datos.**</span><span class="sxs-lookup"><span data-stu-id="12801-108">**Profile, sample, and prepare.**</span></span> <span data-ttu-id="12801-109">Muchos mineros de datos experimentados afirman que el 70-90 por ciento de un proyecto de minería de datos se emplea en la preparación de los datos.</span><span class="sxs-lookup"><span data-stu-id="12801-109">Many experienced data miners say that as much as 70-90 percent of a data mining project is spent on data preparation.</span></span> <span data-ttu-id="12801-110">Los complementos pueden agilizar esta tarea, proporcionando visualizaciones de Excel y asistentes que le ayudan en estas tareas comunes:</span><span class="sxs-lookup"><span data-stu-id="12801-110">The add-ins can make this task go faster, by providing visualizations in Excel and wizards that help you with these common tasks:</span></span>  
  
    -   <span data-ttu-id="12801-111">Realizar el perfil de los datos y comprender su distribución y sus características.</span><span class="sxs-lookup"><span data-stu-id="12801-111">Profile data and understand its distribution and characteristics.</span></span>  
  
    -   <span data-ttu-id="12801-112">Crear conjuntos de entrenamiento y pruebas con el muestreo aleatorio o el sobremuestreo.</span><span class="sxs-lookup"><span data-stu-id="12801-112">Create training and testing sets through random sampling or oversampling.</span></span>  
  
    -   <span data-ttu-id="12801-113">Buscar los valores atípicos y suprimirlos o reemplazarlos.</span><span class="sxs-lookup"><span data-stu-id="12801-113">Find outliers and remove or replace them.</span></span>  
  
    -   <span data-ttu-id="12801-114">Cambiar la etiqueta de los datos para mejorar la calidad del análisis.</span><span class="sxs-lookup"><span data-stu-id="12801-114">Re-label data to improve the quality of analysis.</span></span>  
  
-   <span data-ttu-id="12801-115">**Analizar patrones a través de aprendizaje supervisado o no supervisado.**</span><span class="sxs-lookup"><span data-stu-id="12801-115">**Analyze patterns through supervised or unsupervised learning.**</span></span> <span data-ttu-id="12801-116">Desplácese haciendo clic por sencillos asistentes para realizar algunas de las tareas de minería de datos más populares, incluidos el análisis de agrupación en clústeres, el análisis de la cesta de compras y el pronóstico.</span><span class="sxs-lookup"><span data-stu-id="12801-116">Click through friendly wizards to perform some of the most popular data mining tasks, including clustering analysis, market basket analysis, and forecasting.</span></span>  
  
     <span data-ttu-id="12801-117">Entre los algoritmos de aprendizaje automático conocidos incluidos en los complementos están Naïve Bayes, regresión logística, clústeres, serie temporal y redes neuronales.</span><span class="sxs-lookup"><span data-stu-id="12801-117">Among the well-known machine learning algorithms included in the add-ins are Naïve Bayes, logistic regression, clustering, time series, and neural networks.</span></span>  
  
     <span data-ttu-id="12801-118">Si no está familiarizado con la minería de datos, puede obtener ayuda sobre la generación de consultas de predicción en el asistente **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="12801-118">If you are new to data mining, get help building prediction queries from the **Query** wizard.</span></span>  
  
     <span data-ttu-id="12801-119">Los usuarios avanzados pueden crear consultas DMX personalizadas con el **Editor de consultas avanzadas**que permite arrastrar y colocar, o automatizar las predicciones con VBA de Excel.</span><span class="sxs-lookup"><span data-stu-id="12801-119">Advanced users can build custom DMX queries with the drag-and-drop **Advanced Query Editor**, or automate predictions using Excel VBA.</span></span>  
  
-   <span data-ttu-id="12801-120">**Documentar y administrar.**</span><span class="sxs-lookup"><span data-stu-id="12801-120">**Document and manage.**</span></span> <span data-ttu-id="12801-121">Una vez que haya creado un conjunto de datos y creado algunos modelos, documente su trabajo y sus perspectivas generando un resumen estadístico de los datos y de los parámetros del modelo.</span><span class="sxs-lookup"><span data-stu-id="12801-121">After you've created a data set and built some models, document your work and your insights by generating a statistical summary of the data and model parameters.</span></span>  
  
-   <span data-ttu-id="12801-122">**Explorar y visualizar.**</span><span class="sxs-lookup"><span data-stu-id="12801-122">**Explore and visualize.**</span></span> <span data-ttu-id="12801-123">La minería de datos no es una actividad que se puede automatizar completamente: debe explorar y comprender los resultados para realizar acciones significativas.</span><span class="sxs-lookup"><span data-stu-id="12801-123">Data mining is not an activity that can be fully automated - you need to explore and understand your results to take meaningful action.</span></span> <span data-ttu-id="12801-124">Los complementos le ayudan con la exploración al proporcionar visores interactivos de Excel, plantillas de Visio que le permiten personalizar los diagramas de modelos y la capacidad de exportar los gráficos y las tablas de Excel para filtrarlas o modificarlas más.</span><span class="sxs-lookup"><span data-stu-id="12801-124">The add-ins help you with exploration by providing interactive viewers in Excel, Visio templates that let you customize model diagrams, and the ability to export charts and tables to Excel for additional filtering or modification.</span></span>  
  
-   <span data-ttu-id="12801-125">**Implementar e integrar.**</span><span class="sxs-lookup"><span data-stu-id="12801-125">**Deploy and integrate.**</span></span> <span data-ttu-id="12801-126">Cuando haya creado un modelo útil, coloque el modelo en producción, usando las herramientas de administración para exportar el modelo del servidor experimental a otra instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="12801-126">When you've created a useful model, put your model into production, by using the management tools to export the model from your experimental server to another instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="12801-127">También puede dejar el modelo en el servidor donde lo creó, pero actualizar los datos de aprendizaje y ejecutar predicciones con Integration Services o scripts DMX.</span><span class="sxs-lookup"><span data-stu-id="12801-127">You can also leave the model on the server where you created it, but refresh the training data and run predictions using Integration Services or DMX scripts.</span></span>  
  
     <span data-ttu-id="12801-128">Los usuarios avanzados apreciarán la funcionalidad **Seguimiento** , que permite ver las instrucciones DMX y XMLA enviadas al servidor.</span><span class="sxs-lookup"><span data-stu-id="12801-128">Power users will appreciate the **Trace** functionality, that lets you see the XMLA and DMX statements sent to the server.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="12801-129">Introducción</span><span class="sxs-lookup"><span data-stu-id="12801-129">Getting Started</span></span>  
 <span data-ttu-id="12801-130">Consulte estos temas para obtener información sobre las herramientas y cómo configurarlas:</span><span class="sxs-lookup"><span data-stu-id="12801-130">See these topics to learn about the tools and to get set up:</span></span>  
  
-   [<span data-ttu-id="12801-131">Cliente de minería de datos para Excel &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="12801-131">Data Mining Client for Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](../data-mining-client-for-excel-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="12801-132">Herramientas de análisis de tabla para Excel</span><span class="sxs-lookup"><span data-stu-id="12801-132">Table Analysis Tools for Excel</span></span>](../table-analysis-tools-for-excel.md)  
  
-   [<span data-ttu-id="12801-133">Formas de minería de datos para Visio</span><span class="sxs-lookup"><span data-stu-id="12801-133">Data Mining Shapes for Visio</span></span>](../data-mining-shapes-for-visio.md)  
  
-   [<span data-ttu-id="12801-134">Conectar con un servidor de minería de datos</span><span class="sxs-lookup"><span data-stu-id="12801-134">Connect to a Data Mining Server</span></span>](../connect-to-a-data-mining-server.md)  
  
## <a name="support-and-requirements"></a><span data-ttu-id="12801-135">Compatibilidad y requisitos</span><span class="sxs-lookup"><span data-stu-id="12801-135">Support and Requirements</span></span>  
 <span data-ttu-id="12801-136">Los Complementos de minería de datos de SQL Server para Office se descargan gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="12801-136">The SQL Server Data Mining Add-Ins for Office is a free download.</span></span> <span data-ttu-id="12801-137">Para usar estas herramientas, debe tener instalada una de las siguientes versiones de Office:</span><span class="sxs-lookup"><span data-stu-id="12801-137">You must have one of the following versions of Office already installed to use these tools:</span></span>  
  
-   <span data-ttu-id="12801-138">Office 2010, versiones de 32 bits o de 64 bits</span><span class="sxs-lookup"><span data-stu-id="12801-138">Office 2010, 32-bit or 64-bit version</span></span>  
  
-   <span data-ttu-id="12801-139">Office 2013, versiones de 32 bits o de 64 bits</span><span class="sxs-lookup"><span data-stu-id="12801-139">Office 2013, 32-bit or 64-bit version</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="12801-140">Asegúrese de descargar la versión de los complementos que corresponda a la versión de Excel.</span><span class="sxs-lookup"><span data-stu-id="12801-140">Be sure to download the version of the add-ins that matches your version of Excel.</span></span>  
  
 <span data-ttu-id="12801-141">Los Complementos de minería de datos necesitan una conexión con una de las siguientes ediciones de SQL Server Analysis Services:</span><span class="sxs-lookup"><span data-stu-id="12801-141">The Data Mining Add-ins requires a connection to one of the following editions of SQL Server Analysis Services:</span></span>  
  
-   <span data-ttu-id="12801-142">Empresa</span><span class="sxs-lookup"><span data-stu-id="12801-142">Enterprise</span></span>  
  
-   <span data-ttu-id="12801-143">Inteligencia empresarial</span><span class="sxs-lookup"><span data-stu-id="12801-143">Business Intelligence</span></span>  
  
-   <span data-ttu-id="12801-144">Estándar</span><span class="sxs-lookup"><span data-stu-id="12801-144">Standard</span></span>  
  
 <span data-ttu-id="12801-145">Dependiendo de la edición de SQL Server Analysis Services a la que se conecte, es posible que algunos algoritmos avanzados no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="12801-145">Depending on the edition of SQL Server Analysis Services that you connect to, some of the advanced algorithms might not be available.</span></span> <span data-ttu-id="12801-146">Para obtener información, vea [Características compatibles con las ediciones de SQL Server 2014](https://msdn.microsoft.com/library/cc645993.aspx).</span><span class="sxs-lookup"><span data-stu-id="12801-146">For information, see [Features Supported by the Editions of SQL Server 2014](https://msdn.microsoft.com/library/cc645993.aspx).</span></span>  
  
 <span data-ttu-id="12801-147">Para obtener ayuda adicional con la instalación, vea esta página en el centro de descarga:[https://www.microsoft.com/download/details.aspx?id=29061](https://www.microsoft.com/download/details.aspx?id=29061)</span><span class="sxs-lookup"><span data-stu-id="12801-147">For additional help with installation, see this page on the Download Center: [https://www.microsoft.com/download/details.aspx?id=29061](https://www.microsoft.com/download/details.aspx?id=29061)</span></span>  
  
  
