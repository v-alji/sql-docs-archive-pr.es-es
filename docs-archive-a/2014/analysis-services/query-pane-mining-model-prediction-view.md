---
title: Panel de consulta (vista predicción de modelo de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.query.f1
ms.assetid: fdeec72e-d0bd-4453-9eaa-46436e4d6edc
author: minewiskan
ms.author: owend
ms.openlocfilehash: e17a27190891ea9e00be21d5013d0767d61ac148
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671241"
---
# <a name="query-pane-mining-model-prediction-view"></a><span data-ttu-id="dee8c-102">Panel de consulta (Vista Predicción de modelo de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="dee8c-102">Query Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="dee8c-103">En el panel **Consulta** se muestran las instrucciones DMX (Extensiones de minería de datos) creadas por el Generador de consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="dee8c-103">The **Query** pane displays the Data Mining Expressions (DMX) statements created by Prediction Query Builder.</span></span> <span data-ttu-id="dee8c-104">Puede modificar las instrucciones y, a continuación, hacer clic en el botón **Cambiar a vista de resultado de consulta** para devolver los resultados.</span><span class="sxs-lookup"><span data-stu-id="dee8c-104">You can modify the statements and then click the **Switch to query result view** button to return the results.</span></span> <span data-ttu-id="dee8c-105">Si cambia a la vista **Diseño** , se perderán los cambios realizados a la instrucción.</span><span class="sxs-lookup"><span data-stu-id="dee8c-105">If you switch back to the **Design** view, any changes you made to the statement will be lost.</span></span>  
  
 <span data-ttu-id="dee8c-106">**Para más información:** [Instrucciones de manipulación de datos de Extensiones de minería de datos &#40;DMX&#41;](/sql/dmx/dmx-statements-data-manipulation), [Crear una consulta DMX en SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="dee8c-106">**For More Information:** [Data Mining Extensions &#40;DMX&#41; Data Manipulation Statements](/sql/dmx/dmx-statements-data-manipulation), [Create a DMX Query in SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="dee8c-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="dee8c-107">Options</span></span>  
 <span data-ttu-id="dee8c-108">**Cambiar a vista de resultado de consulta**</span><span class="sxs-lookup"><span data-stu-id="dee8c-108">**Switch to query result view**</span></span>  
 <span data-ttu-id="dee8c-109">Haga clic para cambiar entre los paneles **Diseño**, **Consulta**y **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="dee8c-109">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="dee8c-110">Al cambiar al panel **Resultado** se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="dee8c-110">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="dee8c-111">**Guardar el resultado de la consulta**</span><span class="sxs-lookup"><span data-stu-id="dee8c-111">**Save the query result**</span></span>  
 <span data-ttu-id="dee8c-112">Abre el cuadro de diálogo **Guardar resultado de consulta de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="dee8c-112">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="dee8c-113">**Consulta singleton**</span><span class="sxs-lookup"><span data-stu-id="dee8c-113">**Singleton query**</span></span>  
 <span data-ttu-id="dee8c-114">Le permite crear una consulta singleton, en la que proporciona los datos de entrada directamente en la consulta en lugar de proporcionar una referencia a una tabla de valores de entrada.</span><span class="sxs-lookup"><span data-stu-id="dee8c-114">Lets you create a singleton query, in which you provide the input data directly in your query instead of providing a reference to a table of input values.</span></span> <span data-ttu-id="dee8c-115">La tabla **Seleccionar tabla(s) de entrada** se reemplaza por una tabla **Entrada de consulta singleton** .</span><span class="sxs-lookup"><span data-stu-id="dee8c-115">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span> <span data-ttu-id="dee8c-116">Se perderá la consulta de predicción actual si cambia a una consulta singleton.</span><span class="sxs-lookup"><span data-stu-id="dee8c-116">The current prediction query will be lost if you switch to a singleton query.</span></span>  
  
 <span data-ttu-id="dee8c-117">**Actualizar el resultado de la consulta**</span><span class="sxs-lookup"><span data-stu-id="dee8c-117">**Refresh query results**</span></span>  
 <span data-ttu-id="dee8c-118">Vuelve a procesar la consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="dee8c-118">Reprocesses the prediction query.</span></span> <span data-ttu-id="dee8c-119">Esto solo está habilitado en el panel **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="dee8c-119">This is enabled only in the **Result** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee8c-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dee8c-120">See Also</span></span>  
 <span data-ttu-id="dee8c-121">[Interfaces de consulta de minería de datos](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dee8c-121">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 <span data-ttu-id="dee8c-122">[Referencia de instrucciones de extensiones de minería de datos &#40;DMX&#41;](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="dee8c-122">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 [<span data-ttu-id="dee8c-123">Generador de consultas de predicción &#40;Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="dee8c-123">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
