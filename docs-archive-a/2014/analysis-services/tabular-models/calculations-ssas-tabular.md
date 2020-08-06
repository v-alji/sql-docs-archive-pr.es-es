---
title: Cálculos (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 738816e3-0e1d-44a5-8d1b-81068dce8ac0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2da86ae5c5652c8b2614cae4bbb721802700d973
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671708"
---
# <a name="calculations-ssas-tabular"></a><span data-ttu-id="2bc7e-102">Cálculos (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="2bc7e-102">Calculations (SSAS Tabular)</span></span>
  <span data-ttu-id="2bc7e-103">Después de importar datos en el modelo, puede agregar cálculos para agregar, filtrar, ampliar, combinar y proteger esos datos.</span><span class="sxs-lookup"><span data-stu-id="2bc7e-103">After you have imported data into your model, you can add calculations to aggregate, filter, extend, combine, and secure that data.</span></span> <span data-ttu-id="2bc7e-104">Los modelos tabulares utilizan Expresiones de análisis de datos (DAX), un lenguaje de fórmulas para crear cálculos personalizados.</span><span class="sxs-lookup"><span data-stu-id="2bc7e-104">Tabular models use Data Analysis Expressions (DAX), a formula language for creating custom calculations.</span></span> <span data-ttu-id="2bc7e-105">En los modelos tabulares, los cálculos que crea mediante fórmulas DAX se utilizan en *Columnas calculadas*, *Medidas*y *Filtros de fila*.</span><span class="sxs-lookup"><span data-stu-id="2bc7e-105">In tabular models, the calculations you create by using DAX formulas are used in *Calculated Columns*, *Measures*, and *Row Filters*.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2bc7e-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2bc7e-106">In This Section</span></span>  
  
|<span data-ttu-id="2bc7e-107">Tema</span><span class="sxs-lookup"><span data-stu-id="2bc7e-107">Topic</span></span>|<span data-ttu-id="2bc7e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bc7e-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2bc7e-109">Descripción de DAX en modelos tabulares &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="2bc7e-109">Understanding DAX in Tabular Models &#40;SSAS Tabular&#41;</span></span>](understanding-dax-in-tabular-models-ssas-tabular.md)|<span data-ttu-id="2bc7e-110">Describe el lenguaje de fórmulas Expresiones de análisis de datos (DAX) que se utiliza para crear cálculos para columnas calculadas, medidas y filtros de fila en modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="2bc7e-110">Describes the Data Analysis Expressions (DAX) formula language used to create calculations for calculated columns, measures, and row filters in tabular models.</span></span>|  
|[<span data-ttu-id="2bc7e-111">Compatibilidad de las fórmulas en el modo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="2bc7e-111">Formula Compatibility in DirectQuery Mode</span></span>](../dax-formula-compatibility-in-directquery-mode-ssas-2014.md)|<span data-ttu-id="2bc7e-112">Se describen las diferencias, se enumeran las funciones que no se admiten en el modo DirectQuery y se enumeran las funciones que sí se admiten pero pueden devolver resultados distintos.</span><span class="sxs-lookup"><span data-stu-id="2bc7e-112">Describes the differences, lists the functions that are not supported in DirectQuery mode, and lists the functions that are supported but could return different results.</span></span>|  
|[<span data-ttu-id="2bc7e-113">Expresiones de análisis de datos &#40;referencia de&#41; DAX</span><span class="sxs-lookup"><span data-stu-id="2bc7e-113">Data Analysis Expressions &#40;DAX&#41; Reference</span></span>](/dax/data-analysis-expressions-dax-reference)|<span data-ttu-id="2bc7e-114">En esta sección se proporcionan descripciones detalladas de sintaxis, operadores, y funciones de DAX.</span><span class="sxs-lookup"><span data-stu-id="2bc7e-114">This section provides detailed descriptions of DAX syntax, operators, and functions.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="2bc7e-115">En esta sección no se proporcionan las tareas paso a paso para crear cálculos.</span><span class="sxs-lookup"><span data-stu-id="2bc7e-115">Step-by-step tasks for creating calculations are not provided in this section.</span></span> <span data-ttu-id="2bc7e-116">Dado que los cálculos se especifican en columnas calculadas, medidas y filtros de fila (en roles), se proporcionan instrucciones sobre dónde crear fórmulas DAX en las tareas relacionadas con esas características.</span><span class="sxs-lookup"><span data-stu-id="2bc7e-116">Because calculations are specified in calculated columns, measures, and row filters (in roles), instructions on where to create DAX formulas are provided in tasks related to those features.</span></span> <span data-ttu-id="2bc7e-117">Para obtener más información, vea [Crear una columna calculada &#40;SSAS tabular&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Crear y administrar medidas &#40;SSAS tabular&#41;](measures-ssas-tabular.md) y [Crear y administrar roles &#40;SSAS tabular&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="2bc7e-117">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md), and [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bc7e-118">Si bien DAX también se puede utilizar para consultar un modelo tabular, los temas de esta sección se centran concretamente en el uso de fórmulas DAX para crear cálculos.</span><span class="sxs-lookup"><span data-stu-id="2bc7e-118">While DAX can also be used to query a tabular model, topics in this section focus specifically on using DAX formulas to create calculations.</span></span>  
  
  
