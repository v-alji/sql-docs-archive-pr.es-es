---
title: Ver y guardar los resultados de una consulta de predicción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- viewing prediction query results
- displaying prediction query results
- Mining Model Prediction [Analysis Services], viewing results
ms.assetid: abba4d24-3619-44c1-8279-88f27ad627d3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6da4b515c4280969f665dba2cf5bee5281df0a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671815"
---
# <a name="view-and-save-the-results-of-a-prediction-query"></a><span data-ttu-id="f3620-102">Ver y guardar los resultados de una consulta de predicción</span><span class="sxs-lookup"><span data-stu-id="f3620-102">View and Save the Results of a Prediction Query</span></span>
  <span data-ttu-id="f3620-103">Después de haber definido una consulta en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] mediante la generador de consultas de predicción, puede ejecutar la consulta y ver los resultados cambiando a la vista de resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f3620-103">After you have defined a query in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using Prediction Query Builder, you can run the query and view the results by switching to the query result view.</span></span>  
  
 <span data-ttu-id="f3620-104">Puede guardar los resultados de una consulta de predicción en una tabla de cualquier origen de datos definido en un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="f3620-104">You can save the results of a prediction query to a table in any data source that is defined in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="f3620-105">Puede crear una tabla nueva o guardar los resultados de la consulta en una tabla existente.</span><span class="sxs-lookup"><span data-stu-id="f3620-105">You can either create a new table or save the query results to an existing table.</span></span> <span data-ttu-id="f3620-106">Si guarda los resultados en una tabla existente, puede elegir sobrescribir los datos que están almacenados actualmente en la tabla. En caso contrario, los resultados se anexan a los datos existentes en la tabla.</span><span class="sxs-lookup"><span data-stu-id="f3620-106">If you save the results to an existing table, you can choose to overwrite the data that is currently stored in the table; otherwise, the query results are appended to the existing data in the table.</span></span>  
  
### <a name="run-a-query-and-view-the-results"></a><span data-ttu-id="f3620-107">Ejecutar una consulta y ver los resultados</span><span class="sxs-lookup"><span data-stu-id="f3620-107">Run a query and view the results</span></span>  
  
1.  <span data-ttu-id="f3620-108">En la barra de herramientas de la pestaña **Predicción de modelos de minería de datos** del Diseñador de minería de datos en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic en **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="f3620-108">On the toolbar of the **Mining Model Prediction** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **Result** .</span></span>  
  
     <span data-ttu-id="f3620-109">Se abre la vista de resultados de consulta y se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="f3620-109">The query results view opens and runs the query.</span></span> <span data-ttu-id="f3620-110">Los resultados se muestran en una cuadrícula del visor.</span><span class="sxs-lookup"><span data-stu-id="f3620-110">The results are displayed in a grid in the viewer.</span></span>  
  
### <a name="save-the-results-of-a-prediction-query-to-a-table"></a><span data-ttu-id="f3620-111">Guardar los resultados de una consulta de predicción en una tabla</span><span class="sxs-lookup"><span data-stu-id="f3620-111">Save the results of a prediction query to a table</span></span>  
  
1.  <span data-ttu-id="f3620-112">En la barra de herramientas de la pestaña **Predicción de modelos de minería de datos** del Diseñador de minería de datos, haga clic en **Guardar resultado de consulta**.</span><span class="sxs-lookup"><span data-stu-id="f3620-112">On the toolbar of the **Mining Model Prediction** tab in Data Mining Designer, click **Save query result**.</span></span>  
  
     <span data-ttu-id="f3620-113">Se abre el cuadro de diálogo **Guardar resultado de consulta de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="f3620-113">The **Save Data Mining Query Result** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="f3620-114">Seleccione un origen de datos en la lista **Origen de datos** o haga clic en **Nuevo** para crear un origen de datos nuevo.</span><span class="sxs-lookup"><span data-stu-id="f3620-114">Select a data source from the **Data Source** list, or click **New** to create a new data source.</span></span>  
  
3.  <span data-ttu-id="f3620-115">En el cuadro **Nombre de la tabla** , escriba el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="f3620-115">In the **Table Name** box, enter the name of the table.</span></span> <span data-ttu-id="f3620-116">Si la tabla ya existe, seleccione **Sobrescribir si existe** para sustituir el contenido de la tabla con los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f3620-116">If the table already exists, select **Overwrite if exists** to replace the contents of the table with the query results.</span></span> <span data-ttu-id="f3620-117">Si no desea sobrescribir el contenido de la tabla, no active esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f3620-117">If you do not want to overwrite the contents of the table, do not select this check box.</span></span> <span data-ttu-id="f3620-118">Los resultados de la nueva consulta se anexan a los datos existentes en la tabla.</span><span class="sxs-lookup"><span data-stu-id="f3620-118">The new query results will be appended to the existing data in the table.</span></span>  
  
4.  <span data-ttu-id="f3620-119">Seleccione una vista del origen de datos en **Agregar a vista del origen de datos** si desea agregar la tabla a una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f3620-119">Select a data source view from **Add to DSV** if you want to add the table to a data source view.</span></span>  
  
5.  <span data-ttu-id="f3620-120">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="f3620-120">Click **Save**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="f3620-121">Si el destino no admite conjuntos de filas jerárquicos, puede agregar la palabra clave FALTTENED a los resultados para guardarlos como una tabla plana.</span><span class="sxs-lookup"><span data-stu-id="f3620-121">If the destination does not support hierarchical rowsets, you can add the FALTTENED keyword to the results to save as a flat table.</span></span>  
  
  
