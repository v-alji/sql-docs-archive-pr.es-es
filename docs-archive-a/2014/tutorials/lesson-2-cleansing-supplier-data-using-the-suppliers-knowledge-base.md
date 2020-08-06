---
title: 'Lección 2: limpiar datos de proveedor mediante la base de conocimiento proveedores | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 215c14de-fc3f-46de-a022-bf69b9ea2a96
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ebc0231cd0f28fcad23656cf22abd8d68eca7dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662428"
---
# <a name="lesson-2-cleansing-supplier-data-using-the-suppliers-knowledge-base"></a><span data-ttu-id="837e3-102">Lección 2: Limpieza de datos de proveedor con la base de conocimiento Proveedores</span><span class="sxs-lookup"><span data-stu-id="837e3-102">Lesson 2: Cleansing Supplier Data using the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="837e3-103">En esta lección, limpiará los datos de proveedor en un archivo de Excel con la base de conocimiento **proveedores** que creó en la primera lección.</span><span class="sxs-lookup"><span data-stu-id="837e3-103">In this lesson, you cleanse the supplier data in an Excel file by using the **Suppliers** knowledge base you have created in the first lesson.</span></span> <span data-ttu-id="837e3-104">La limpieza de datos en DQS incluye un **proceso asistido por PC** que analiza cómo se ajustan los datos a la información de una base de conocimiento y un **proceso interactivo** que permite revisar y modificar los resultados del proceso asistido por PC.</span><span class="sxs-lookup"><span data-stu-id="837e3-104">Data cleansing in DQS includes a **computer-assisted process** that analyzes how data conforms to the knowledge in a knowledge base, and an **interactive process** that enables you to review and modify results from the computer-assisted process.</span></span> <span data-ttu-id="837e3-105">La característica de limpieza de datos identifica los datos incorrectos en el origen de datos y después corrige o sugiere correcciones a los datos incorrectos.</span><span class="sxs-lookup"><span data-stu-id="837e3-105">The data cleansing feature identifies incorrect data in your data source and then corrects or suggests corrections for the incorrect data.</span></span> <span data-ttu-id="837e3-106">También normaliza y enriquece los datos de cliente usando valores de dominio, valores iniciales de sinónimos, reglas de dominio, relaciones basadas en términos y datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="837e3-106">It also standardizes and enriches customer data by using domain values, leading values for synonyms, domain rules, term-based relations, and reference data.</span></span> <span data-ttu-id="837e3-107">Puede aprobar o rechazar interactivamente los cambios propuestos por el proceso asistido por PC.</span><span class="sxs-lookup"><span data-stu-id="837e3-107">You can interactively approve or reject changes proposed by the computer-assisted process.</span></span> <span data-ttu-id="837e3-108">Vea [limpieza de datos](https://msdn.microsoft.com/library/gg524800.aspx) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="837e3-108">See [Data Cleansing](https://msdn.microsoft.com/library/gg524800.aspx) for more details.</span></span>  
  
 <span data-ttu-id="837e3-109">El proceso asistido por PC emplea los valores de umbral siguientes que puede configurar mediante la opción Configuración de la página principal del Cliente DQS.</span><span class="sxs-lookup"><span data-stu-id="837e3-109">The computer-assisted process uses the following threshold values that you can configure using the Configuration option on the DQS Client main page.</span></span>  
  
-   <span data-ttu-id="837e3-110">**Puntuación mínima para sugerencias:** Puntuación mínima o nivel de confianza que utiliza DQS para sugerir el reemplazo de un valor.</span><span class="sxs-lookup"><span data-stu-id="837e3-110">**Min score for suggestions:** The minimum score or confidence level that is used by DQS for suggesting replacement for a value.</span></span>  
  
-   <span data-ttu-id="837e3-111">**Puntuación mínima para las correcciones automáticas:** Puntuación mínima o nivel de confianza que utiliza DQS para corregir automáticamente un valor.</span><span class="sxs-lookup"><span data-stu-id="837e3-111">**Min score for auto corrections:** The minimum score or confidence level that is used by DQS for automatically correcting a value.</span></span>  
  
 <span data-ttu-id="837e3-112">Vea [configurar los valores de umbral para la limpieza y la búsqueda de coincidencias](https://msdn.microsoft.com/library/hh510415.aspx) para obtener más información sobre cómo configurar estas opciones.</span><span class="sxs-lookup"><span data-stu-id="837e3-112">See [Configure Threshold Values for Cleansing and Matching](https://msdn.microsoft.com/library/hh510415.aspx) for details on how to configure these settings.</span></span>  
  
 <span data-ttu-id="837e3-113">En esta lección, realizará las tareas siguientes para limpiar los datos de entrada mediante la base de conocimiento Proveedores.</span><span class="sxs-lookup"><span data-stu-id="837e3-113">In this lesson, you perform the following tasks to cleanse the input data by using the Suppliers knowledge base.</span></span>  
  
1.  <span data-ttu-id="837e3-114">Crear un proyecto de calidad de datos para la limpieza, seleccionar la base de conocimiento Proveedores como base de conocimiento que se usará para analizar y limpiar los datos de origen en un archivo de Excel, y seleccionar la actividad Limpieza.</span><span class="sxs-lookup"><span data-stu-id="837e3-114">Create a Data Quality Project for Cleansing, select the Suppliers knowledge base as the knowledge base to use to analyze and cleanse the source data in an Excel file, and select the Cleansing activity.</span></span>  
  
2.  <span data-ttu-id="837e3-115">Asignar las columnas de Excel que desea limpiar a los dominios de DQS o dominios compuestos adecuados de la base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="837e3-115">Map the Excel columns that you want to cleanse to appropriate DQS domains/composite domains in the knowledge base.</span></span>  
  
3.  <span data-ttu-id="837e3-116">Ejecutar la actividad de limpieza asistida por PC.</span><span class="sxs-lookup"><span data-stu-id="837e3-116">Run the computer-assisted cleansing activity.</span></span> <span data-ttu-id="837e3-117">El proceso asistido por PC muestra información sobre la calidad de los datos en el Cliente de calidad de los datos que puede usar para limpiar los datos de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="837e3-117">The computer-assisted process displays data quality information in the Data Quality Client that you can use to cleanse the data interactively.</span></span>  
  
4.  <span data-ttu-id="837e3-118">Ver y administrar los resultados de la actividad Limpieza.</span><span class="sxs-lookup"><span data-stu-id="837e3-118">View and manage the results of the cleansing activity.</span></span> <span data-ttu-id="837e3-119">Puede examinar los valores que el proceso asistido por PC dice que son correctos, incorrectos pero corregidos, incorrectos con un cambio sugerido o no válidos.</span><span class="sxs-lookup"><span data-stu-id="837e3-119">You can review the values that the computer-assisted process finds to be correct, incorrect but corrected, incorrect with a suggested change, or invalid.</span></span> <span data-ttu-id="837e3-120">Puede aprobar o rechazar interactivamente los cambios, corrigiendo o invalidando la sugerencia del proceso asistido por PC mediante el campo Corregir a.</span><span class="sxs-lookup"><span data-stu-id="837e3-120">You can interactively approve or reject changes, correcting or overriding the suggestion from the computer-assisted process by using the Correct To field.</span></span>  
  
5.  <span data-ttu-id="837e3-121">Exportar los resultados del proceso de limpieza a un archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="837e3-121">Export the results from the cleansing process to an Excel file.</span></span>  
  
6.  <span data-ttu-id="837e3-122">Importe los valores del proyecto de limpieza a los dominios para aumentar el conocimiento de la base de conocimiento con nuevas reglas, valores, correcciones, etc.</span><span class="sxs-lookup"><span data-stu-id="837e3-122">Import the values from the cleansing project into domains to augment the knowledge in the knowledge base with new rules, values, corrections etc...</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="837e3-123">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="837e3-123">Next Step</span></span>  
 [<span data-ttu-id="837e3-124">Tarea 1: Creación de un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="837e3-124">Task 1: Creating a Data Quality Project</span></span>](../../2014/tutorials/task-1-creating-a-data-quality-project.md)  
  
  
