---
title: Cuadro de diálogo Guardar resultado de consulta de minería de datos (vista predicción de modelo de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dm.savedataminingqueryresult.f1
helpviewer_keywords:
- Save Data Mining Query Result dialog box
ms.assetid: 112fb527-7466-4fd4-9cf1-75596135648f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0838c90f0797a0db9c8a66cd8c5f877aaecdad0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669918"
---
# <a name="save-data-mining-query-result-dialog-box-mining-model-prediction-view"></a><span data-ttu-id="aa877-102">Guardar resultado de consulta de minería de datos (cuadro de diálogo de la vista Predicción de modelo de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="aa877-102">Save Data Mining Query Result Dialog Box (Mining Model Prediction View)</span></span>
  <span data-ttu-id="aa877-103">Use el cuadro de diálogo **Guardar resultado de consulta de minería de datos** para guardar los resultados de una consulta de minería de datos en una tabla nueva.</span><span class="sxs-lookup"><span data-stu-id="aa877-103">Use the **Save Data Mining Query Result** dialog box to save the results of a data mining query to a new table.</span></span>  
  
 <span data-ttu-id="aa877-104">La tabla nueva se creará en la base de datos que haya definido el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="aa877-104">The new table will be created in the database defined by the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aa877-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="aa877-105">Options</span></span>  
 <span data-ttu-id="aa877-106">**Data Source** (Origen de datos)</span><span class="sxs-lookup"><span data-stu-id="aa877-106">**Data Source**</span></span>  
 <span data-ttu-id="aa877-107">Seleccione un origen de datos del proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="aa877-107">Select a data source from the current project.</span></span> <span data-ttu-id="aa877-108">Si no existe el origen de datos correcto, haga clic en **Nuevo** para crear un nuevo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="aa877-108">If the correct data source does not exist, click **New** to create a new data source.</span></span>  
  
 <span data-ttu-id="aa877-109">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="aa877-109">**New**</span></span>  
 <span data-ttu-id="aa877-110">Abre el **Asistente para orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="aa877-110">Opens the **Data Source Wizard**.</span></span>  
  
 <span data-ttu-id="aa877-111">**Nombre de tabla**</span><span class="sxs-lookup"><span data-stu-id="aa877-111">**Table Name**</span></span>  
 <span data-ttu-id="aa877-112">Escriba un nombre para la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="aa877-112">Type a name for the new table.</span></span>  
  
 <span data-ttu-id="aa877-113">**Sobrescribir si existe**</span><span class="sxs-lookup"><span data-stu-id="aa877-113">**Overwrite if exists**</span></span>  
 <span data-ttu-id="aa877-114">Seleccione esta opción si desea sobrescribir una tabla existente con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="aa877-114">Select this option if you want to overwrite an existing table with the same name.</span></span>  
  
 <span data-ttu-id="aa877-115">Es preciso sobrescribir la tabla existente si se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="aa877-115">Overwriting the existing table is required if any of the following is true:</span></span>  
  
-   <span data-ttu-id="aa877-116">Agregó columnas a la consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="aa877-116">You added columns to the prediction query.</span></span>  
  
-   <span data-ttu-id="aa877-117">Cambió los nombres o los tipos de datos de cualquier columna de la consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="aa877-117">You changed the names or data types of any columns in the prediction query.</span></span>  
  
-   <span data-ttu-id="aa877-118">Ejecutó una instrucción ALTER en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="aa877-118">You ran an ALTER statement on the destination table.</span></span>  
  
 <span data-ttu-id="aa877-119">Si varias columnas tienen el mismo nombre (por ejemplo, es posible que varias columnas derivadas tengan el nombre de columna predeterminado **Expresión**), será preciso crear un alias para cada columna con un nombre duplicado.</span><span class="sxs-lookup"><span data-stu-id="aa877-119">If multiple columns have the same name (for example, several derived columns might have the default column name **Expression**), you must create an alias for each column with a duplicate name.</span></span> <span data-ttu-id="aa877-120">Si las columnas no tienen nombres únicos, se producirá un error cuando el diseñador intente guardar los resultados en SQL Server, porque las columnas de una tabla deben tener nombres únicos.</span><span class="sxs-lookup"><span data-stu-id="aa877-120">If the columns do not have unique names, an error will be raised when the designer tries to save the results to SQL Server, because columns in a table must have unique names.</span></span>  
  
 <span data-ttu-id="aa877-121">**Agregar a vista del origen de datos**</span><span class="sxs-lookup"><span data-stu-id="aa877-121">**Add to DSV**</span></span>  
 <span data-ttu-id="aa877-122">(Opcional) Seleccione una vista del origen de datos que contenga el proyecto si desea agregar la tabla a un origen de datos existente.</span><span class="sxs-lookup"><span data-stu-id="aa877-122">(Optional) Select a data source view contained in the project if you want to add the table to an existing data source.</span></span>  
  
 <span data-ttu-id="aa877-123">Esta opción es útil si desea conservar todas las tablas relacionadas para un modelo, como los datos de entrenamiento, los datos de origen de la predicción y los resultados de la consulta, en el mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="aa877-123">This option is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa877-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa877-124">See Also</span></span>  
 <span data-ttu-id="aa877-125">[Predicción Generador de consultas &#40;de minería de datos&#41;](prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="aa877-125">[Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md) </span></span>  
 <span data-ttu-id="aa877-126">[Interfaces de consulta de minería de datos](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="aa877-126">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="aa877-127">Referencia de instrucciones de Extensiones de minería de datos &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="aa877-127">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
