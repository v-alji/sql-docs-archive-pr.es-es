---
title: Explorar datos en una vista del origen de datos (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exploring data [Analysis Services]
- data source views [Analysis Services], exploring data
- viewing source data
ms.assetid: 2c922c35-fbcb-45b2-96b1-c7a846d8b419
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adf9edecd807158ba1d0de3287cccd6fa8dd787
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677902"
---
# <a name="explore-data-in-a-data-source-view-analysis-services"></a><span data-ttu-id="71d45-102">Explorar datos en una vista del origen de datos (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="71d45-102">Explore Data in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="71d45-103">Puede usar el cuadro de diálogo **Explorar datos** del Diseñador de vistas del origen de datos de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para explorar los datos de una tabla, vista o consulta con nombre en una vista del origen de datos (DSV).</span><span class="sxs-lookup"><span data-stu-id="71d45-103">You can use the **Explore Data** dialog box in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to browse data for a table, view, or named query in a data source view (DSV).</span></span> <span data-ttu-id="71d45-104">Al explorar los datos en el Diseñador de vistas del origen de datos, puede ver el contenido de cada columna de datos de una tabla, vista o consulta con nombre seleccionada.</span><span class="sxs-lookup"><span data-stu-id="71d45-104">When you explore the data in Data Source View Designer, you can view the contents of each column of data in a selected table, view, or named query.</span></span> <span data-ttu-id="71d45-105">Observar el contenido real le puede ayudar a determinar si todas las columnas son necesarias, si se necesitan cálculos con nombre para mejorar la facilidad de uso, y si los cálculos o consultas con nombre devuelven los valores previstos.</span><span class="sxs-lookup"><span data-stu-id="71d45-105">Viewing the actual contents assists you in determining whether all columns are needed, if named calculations are required to increase user friendliness and usability, and whether existing named calculations or named queries return the anticipated values.</span></span>  
  
 <span data-ttu-id="71d45-106">Para ver datos, debe tener una conexión activa con el origen u orígenes de datos del objeto seleccionado en la DSV.</span><span class="sxs-lookup"><span data-stu-id="71d45-106">To view data, you must have an active connection to the data source or sources for the selected object in the DSV.</span></span> <span data-ttu-id="71d45-107">En la consulta también se envían todos los cálculos con nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="71d45-107">Any named calculations in a table are also sent in the query.</span></span>  
  
 <span data-ttu-id="71d45-108">Los datos se devuelven en formato tabular, y pueden ordenarse y copiarse.</span><span class="sxs-lookup"><span data-stu-id="71d45-108">The data returned in a tabular format that you can sort and copy.</span></span> <span data-ttu-id="71d45-109">Haga clic en los encabezados de columna para reordenar las filas por esa columna.</span><span class="sxs-lookup"><span data-stu-id="71d45-109">Click on the column headers to re-sort the rows by that column.</span></span> <span data-ttu-id="71d45-110">También puede resaltar datos en la cuadrícula y presionar Ctrl+C para copiar la selección en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="71d45-110">You can also highlight data in the grid and press Ctrl-C to copy the selection to the clipboard.</span></span>  
  
 <span data-ttu-id="71d45-111">Asimismo, puede controlar el método de muestreo y el número de muestras.</span><span class="sxs-lookup"><span data-stu-id="71d45-111">You can also control the sample method and the sample count.</span></span> <span data-ttu-id="71d45-112">De forma predeterminada, se devuelven las 5000 principales filas.</span><span class="sxs-lookup"><span data-stu-id="71d45-112">By default, the top 5000 rows are returned.</span></span>  
  
## <a name="to-browse-data-or-change-sampling-options"></a><span data-ttu-id="71d45-113">Para examinar los datos o cambiar las opciones de muestreo</span><span class="sxs-lookup"><span data-stu-id="71d45-113">To browse data or change sampling options</span></span>  
  
1.  <span data-ttu-id="71d45-114">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto o conéctese a la base de datos que contiene la vista del origen de datos en que desea examinar los datos.</span><span class="sxs-lookup"><span data-stu-id="71d45-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to browse data.</span></span>  
  
2.  <span data-ttu-id="71d45-115">En el Explorador de soluciones, expanda la carpeta **Vistas del origen de datos** y, después, haga doble clic en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="71d45-115">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="71d45-116">Haga clic con el botón derecho en la tabla, vista o consulta con nombre que contiene los datos que quiere ver y, después, haga clic en **Explorar datos**.</span><span class="sxs-lookup"><span data-stu-id="71d45-116">Right-click the table, view, or named query that contains the data you want to view, and then click **Explore Data**.</span></span>  
  
     <span data-ttu-id="71d45-117">El origen de datos subyacente de la tabla, vista o consulta con nombre de la vista del origen de datos es consultas y los resultados aparecen en la pestaña **explorar \<object name> tabla** .</span><span class="sxs-lookup"><span data-stu-id="71d45-117">The data source underlying the table, view, or named query in the data source view are queries, and the results appear in the **Explore \<object name> Table** tab.</span></span>  
  
4.  <span data-ttu-id="71d45-118">En la barra de herramientas **explorar \<object name> tabla** , haga clic en el icono **Opciones de muestreo** .</span><span class="sxs-lookup"><span data-stu-id="71d45-118">On the **Explore \<object name> Table** toolbar, click the **Sampling options** icon.</span></span>  
  
     <span data-ttu-id="71d45-119">Se abrirá el cuadro de diálogo **Opciones de exploración de datos** .</span><span class="sxs-lookup"><span data-stu-id="71d45-119">The **Data Exploration Options** dialog box opens.</span></span> <span data-ttu-id="71d45-120">En este cuadro de diálogo puede especificar el método de muestreo (más o menos registros que el tamaño de muestreo predeterminado de 5000 filas) o el número de muestras.</span><span class="sxs-lookup"><span data-stu-id="71d45-120">In this dialog box you can specify the sampling method (fewer or more records than the default sampling size of 5000 rows), or sample count.</span></span>  
  
5.  <span data-ttu-id="71d45-121">Haga clic en **Aceptar** o en **Cancelar** , según corresponda.</span><span class="sxs-lookup"><span data-stu-id="71d45-121">Click **OK** or **Cancel** as appropriate.</span></span>  
  
6.  <span data-ttu-id="71d45-122">Para volver a muestrear los datos, haga clic en volver a **muestrear datos** en la barra de herramientas **explorar \<object name> tabla** .</span><span class="sxs-lookup"><span data-stu-id="71d45-122">To resample the data, click **Resample Data** on the **Explore \<object name> Table** toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d45-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71d45-123">See Also</span></span>  
 [<span data-ttu-id="71d45-124">Vistas del origen de datos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="71d45-124">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
