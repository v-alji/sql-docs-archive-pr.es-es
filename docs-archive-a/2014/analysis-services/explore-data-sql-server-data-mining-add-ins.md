---
title: Explorar datos (complementos de minería de datos de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- histogram [data mining]
- data visualization
ms.assetid: 714845a9-4c27-461a-9ba3-149e1e818386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2572c11e92dcf99dfa3adf661603e8f65f05116e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747237"
---
# <a name="explore-data-sql-server-data-mining-add-ins"></a><span data-ttu-id="bbbbe-102">Explorar datos (Complementos de minería de datos de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bbbbe-102">Explore Data (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="bbbbe-103">![Asistente para explorar datos](media/dmc-explore.gif "Asistente para explorar datos")</span><span class="sxs-lookup"><span data-stu-id="bbbbe-103">![Explore Data wizard](media/dmc-explore.gif "Explore Data wizard")</span></span>  
  
 <span data-ttu-id="bbbbe-104">El Asistente para **explorar datos** le ayuda a comprender el tipo y la cantidad de datos de la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-104">The **Explore Data** wizard helps you understand the type and amount of data in your data table.</span></span> <span data-ttu-id="bbbbe-105">El asistente representa de forma gráfica la distribución y los valores para las columnas seleccionadas, por columnas.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-105">The wizard graphs the distribution and values for the selected columns, one column at a time.</span></span> <span data-ttu-id="bbbbe-106">Después, puede probar a cambiar la forma en que se agrupan los datos o copiar el gráfico que muestra el contenido en un libro de Excel para revisarlo.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-106">You can then experiment with changing the way that data is grouped, or copy the chart that shows the content to an Excel workbook for review.</span></span>  
  
 <span data-ttu-id="bbbbe-107">Si los datos contienen datos numéricos continuos, puede alternar entre estas dos vistas:</span><span class="sxs-lookup"><span data-stu-id="bbbbe-107">If your data contains continuous numeric data, you can toggle between these two views:</span></span>  
  
-   <span data-ttu-id="bbbbe-108">**Gráfico de líneas.**</span><span class="sxs-lookup"><span data-stu-id="bbbbe-108">**Line graph.**</span></span> <span data-ttu-id="bbbbe-109">Este gráfico de líneas representa gráficamente los valores de datos en el eje X y el número de casos en el eje Y.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-109">This graph charts the data values on the X-axis and the number of cases on the y-axis.</span></span>  
  
-   <span data-ttu-id="bbbbe-110">**Gráfico de barras.**</span><span class="sxs-lookup"><span data-stu-id="bbbbe-110">**Bar chart.**</span></span> <span data-ttu-id="bbbbe-111">Este gráfico agrupa los valores por el número de casos correspondientes a cada valor.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-111">This graph groups values by the number of cases for each value.</span></span>  
  
 <span data-ttu-id="bbbbe-112">Cuando el asistente encuentra grupos en los datos, usa la distribución real de los valores de datos.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-112">When the wizard finds groups in the data, it uses the actual distribution of data values.</span></span> <span data-ttu-id="bbbbe-113">Por tanto, el gráfico de barras no muestra los valores numéricos según los típicos marcadores de eje numérico con números enteros como 10 o 100.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-113">Therefore, the bar chart does not show typical whole-number numeric axis markers such as 10 or 100.</span></span> <span data-ttu-id="bbbbe-114">En su lugar, los intervalos que se muestran en el gráfico de barras se asemejarían a valores como 43 521-55 603 (para la columna Income).</span><span class="sxs-lookup"><span data-stu-id="bbbbe-114">Instead, the ranges shown in the bar chart might be something like 43521-55603 (for the Income column).</span></span>  
  
 <span data-ttu-id="bbbbe-115">Si desea agrupar los datos en otros intervalos, debería hacerlo en Excel antes de analizar los datos.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-115">If you want to group your data into other ranges, you should do this in Excel before analyzing the data.</span></span> <span data-ttu-id="bbbbe-116">O bien, puede cambiar la etiqueta de los datos mediante el Asistente para cambiar [etiquetas](relabel-sql-server-data-mining-add-ins.md) .</span><span class="sxs-lookup"><span data-stu-id="bbbbe-116">Or, you can relabel the data by using the [Relabel](relabel-sql-server-data-mining-add-ins.md) wizard.</span></span>  
  
## <a name="using-the-explore-data-wizard"></a><span data-ttu-id="bbbbe-117">Usar el Asistente para explorar datos</span><span class="sxs-lookup"><span data-stu-id="bbbbe-117">Using the Explore Data Wizard</span></span>  
  
1.  <span data-ttu-id="bbbbe-118">En la cinta de opciones **minería de datos** , haga clic en **explorar datos**.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-118">In the **Data Mining** ribbon, click **Explore Data**.</span></span>  
  
2.  <span data-ttu-id="bbbbe-119">En el cuadro de diálogo **Seleccionar origen** , seleccione la tabla o el rango de celdas que contiene los datos.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-119">In the **Select Source** dialog box, select the table or range of cells that contains your data.</span></span>  
  
3.  <span data-ttu-id="bbbbe-120">En el cuadro de diálogo **Seleccionar columna** , elija la columna que se va a analizar, en los datos de ejemplo que se muestran en el panel.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-120">In the **Select Column** dialog box, choose the column to analyze, from the sample data displayed in the pane.</span></span>  
  
4.  <span data-ttu-id="bbbbe-121">En el cuadro de diálogo **explorar datos** , elija los tipos de gráficos para mostrar la distribución de los datos.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-121">In the **Explore Data** dialog box, choose the chart types for displaying the distribution of data.</span></span>  
  
5.  <span data-ttu-id="bbbbe-122">Si lo desea, puede agregar nuevas columnas a los datos, cambiar la manera en que se segmentan los datos o copiar el gráfico en Excel.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-122">Optionally, you can add new columns to the data, change the way that the data is segmented, or copy the chart to Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="bbbbe-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbbbe-123">Requirements</span></span>  
 <span data-ttu-id="bbbbe-124">Para usar el Asistente para **explorar datos** , los datos deben estar en una tabla de datos de Excel.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-124">To use the **Explore Data** wizard, your data must be in an Excel data table.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="bbbbe-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bbbbe-125">See Also</span></span>  
 [<span data-ttu-id="bbbbe-126">Lista de comprobación de la preparación para la minería de datos</span><span class="sxs-lookup"><span data-stu-id="bbbbe-126">Checklist of Preparation for Data Mining</span></span>](checklist-of-preparation-for-data-mining.md)  
  
  
