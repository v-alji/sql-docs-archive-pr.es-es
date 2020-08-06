---
title: Definir parámetros en el diseñador de consultas MDX para Analysis Services (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- parameters [Reporting Services], MDX
- Multidimensional Expressions [Reporting Services]
- Data Mining Prediction [Reporting Services]
- MDX [Reporting Services], defining parameters
- DMX [Reporting Services]
ms.assetid: 4ad1e5bc-f510-4752-b4f6-589e55317a90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6b2b05fc0122eb25a7a0799f7b47b1b99486a28c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751786"
---
# <a name="define-parameters-in-the-mdx-query-designer-for-analysis-services-report-builder-and-ssrs"></a><span data-ttu-id="11877-102">Definir parámetros en el diseñador de consultas MDX para Analysis Services (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="11877-102">Define Parameters in the MDX Query Designer for Analysis Services (Report Builder and SSRS)</span></span>
  <span data-ttu-id="11877-103">Si desea incluir parámetros en una consulta MDX para un origen de datos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , debe agregar un parámetro de consulta a la consulta.</span><span class="sxs-lookup"><span data-stu-id="11877-103">To parameterize an MDX query for an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you must add a query parameter to the query.</span></span> <span data-ttu-id="11877-104">En el diseñador de consultas MDX, puede agregar un parámetro de consulta tanto en el modo de diseño como en el modo de consulta mediante la especificación de un filtro.</span><span class="sxs-lookup"><span data-stu-id="11877-104">In the MDX query designer, you can add a query parameter in both Design mode and Query mode by specifying a filter.</span></span> <span data-ttu-id="11877-105">Después de definir la consulta con un parámetro de consulta, Reporting Services crea automáticamente un parámetro de informe y un conjunto de datos para proporcionar la lista de valores válidos.</span><span class="sxs-lookup"><span data-stu-id="11877-105">After you define the query with a query parameter, Reporting Services automatically creates a report parameter and a dataset to provide the list of valid values.</span></span> <span data-ttu-id="11877-106">Esto permite al usuario especificar un valor que se pasa directamente a la consulta.</span><span class="sxs-lookup"><span data-stu-id="11877-106">This enables a user to specify a value that is passed directly to the query.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-define-a-query-parameter-in-mdx-in-design-mode"></a><span data-ttu-id="11877-107">Para definir un parámetro de consulta en MDX en el modo de diseño</span><span class="sxs-lookup"><span data-stu-id="11877-107">To define a query parameter in MDX in Design mode</span></span>

1.  <span data-ttu-id="11877-108">En el panel Datos de informe, haga clic con el botón derecho en un conjunto de datos creado a partir de un tipo de origen de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] y luego haga clic en **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="11877-108">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="11877-109">El diseñador de consultas MDX se abre en el modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="11877-109">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="11877-110">Arrastre una dimensión hacia el área de filtro y colóquela en la primera celda de la columna **Dimensión** .</span><span class="sxs-lookup"><span data-stu-id="11877-110">Drag a dimension to the filter area and drop it on the first cell in the **Dimension** column.</span></span>

3.  <span data-ttu-id="11877-111">En la columna **Jerarquía** , elija un valor en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="11877-111">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

4.  <span data-ttu-id="11877-112">En la columna **Operador** , elija a un operador en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="11877-112">In the **Operator** column, choose an operator for the drop-down list.</span></span>

5.  <span data-ttu-id="11877-113">En la columna **Expresión de filtro** , seleccione valores individuales en la lista desplegable o haga clic en el miembro **Todos** para elegir todos los valores.</span><span class="sxs-lookup"><span data-stu-id="11877-113">In the **Filter Expression** column, select individual values from the drop-down list, or click the **All** member to choose all values.</span></span>

6.  <span data-ttu-id="11877-114">En la columna **Parámetros** , active la casilla para crear un parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="11877-114">In the **Parameters** column, select the check box to create a report parameter.</span></span>

7.  <span data-ttu-id="11877-115">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="11877-115">Click **Run**.</span></span>

     <span data-ttu-id="11877-116">Después de ejecutar la consulta, haga clic en **Diseño** en la barra de herramientas para cambiar al modo de consulta y ver la consulta MDX que ha creado.</span><span class="sxs-lookup"><span data-stu-id="11877-116">After you run the query, click **Design** on the toolbar to toggle to Query mode to view the MDX query that was created.</span></span> <span data-ttu-id="11877-117">Si desea continuar usando el modo de diseño para desarrollar la consulta, no cambie el texto de la consulta en el modo de consulta.</span><span class="sxs-lookup"><span data-stu-id="11877-117">Do not change the query text in Query mode if you want to continue to use Design mode to develop the query.</span></span> <span data-ttu-id="11877-118">Haga clic en **Diseño** para volver al modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="11877-118">Click **Design** to toggle back to Design mode.</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="11877-119">En el panel Datos de informe, expanda el nodo Parámetros para mostrar el parámetro de informe que se ha creado automáticamente para el filtro.</span><span class="sxs-lookup"><span data-stu-id="11877-119">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="11877-120">Para ver el conjunto de datos que proporciona los valores disponibles para el parámetro de informe, haga clic con el botón secundario en cualquier área en blanco del panel Datos de informe y, a continuación, haga clic en **Mostrar conjuntos de datos ocultos**.</span><span class="sxs-lookup"><span data-stu-id="11877-120">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="11877-121">El panel Datos de informe muestra todos los conjuntos de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="11877-121">The Report Data pane displays all datasets in the report.</span></span>

### <a name="to-define-a-query-parameter-in-mdx-in-query-mode"></a><span data-ttu-id="11877-122">Para definir un parámetro de consulta en MDX en el modo de consulta</span><span class="sxs-lookup"><span data-stu-id="11877-122">To define a query parameter in MDX in Query mode</span></span>

1.  <span data-ttu-id="11877-123">En el panel Datos de informe, haga clic con el botón derecho en un conjunto de datos creado a partir de un tipo de origen de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] y luego haga clic en **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="11877-123">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="11877-124">El diseñador de consultas MDX se abre en el modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="11877-124">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="11877-125">En la barra de herramientas, haga clic en **Diseño** para cambiar al modo de consulta.</span><span class="sxs-lookup"><span data-stu-id="11877-125">On the toolbar, click **Design** to toggle to Query mode.</span></span>

3.  <span data-ttu-id="11877-126">En la barra de herramientas del diseñador de consultas MDX, haga clic en **Parámetros de consulta** (![Icono del cuadro de diálogo Parámetros de consulta](../../analysis-services/media/iconqueryparameter.gif "Icono del cuadro de diálogo Parámetros de consulta")).</span><span class="sxs-lookup"><span data-stu-id="11877-126">On the MDX query designer toolbar, click **Query Parameters** (![Icon for the Query Parameters dialog box](../../analysis-services/media/iconqueryparameter.gif "Icon for the Query Parameters dialog box")).</span></span> <span data-ttu-id="11877-127">Se abrirá el cuadro de diálogo Parámetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="11877-127">The Query Parameters dialog box opens.</span></span>

4.  <span data-ttu-id="11877-128">En la columna **parámetro** , haga clic en **\<Enter Parameter>** y escriba el nombre de un parámetro.</span><span class="sxs-lookup"><span data-stu-id="11877-128">In the **Parameter** column, click **\<Enter Parameter>**, and then type the name of a parameter.</span></span>

5.  <span data-ttu-id="11877-129">En la columna **Dimensión** , elija un valor en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="11877-129">In the **Dimension** column, choose a value from the drop-down list.</span></span>

6.  <span data-ttu-id="11877-130">En la columna **Jerarquía** , elija un valor en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="11877-130">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

7.  <span data-ttu-id="11877-131">En la columna **Valores múltiples** , active la casilla para crear un parámetro de varios valores.</span><span class="sxs-lookup"><span data-stu-id="11877-131">In the **Multiple values** column, select the check box to create a multivalue parameter.</span></span>

8.  <span data-ttu-id="11877-132">En la lista desplegable de la columna **Predeterminado** , seleccione un valor o varios valores, dependiendo de lo que haya elegido en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="11877-132">In the **Default** column, from the drop-down list, select a single value or multiple values depending on your choice in step 5.</span></span>

9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

10. <span data-ttu-id="11877-133">En la barra de herramientas del diseñador de consultas, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="11877-133">On the query designer toolbar, click **Run**.</span></span>

11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="11877-134">En el panel Datos de informe, expanda el nodo Parámetros para mostrar el parámetro de informe que se ha creado automáticamente para el filtro.</span><span class="sxs-lookup"><span data-stu-id="11877-134">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="11877-135">Para ver el conjunto de datos que proporciona los valores disponibles para el parámetro de informe, haga clic con el botón secundario en cualquier área en blanco del panel Datos de informe y, a continuación, haga clic en **Mostrar conjuntos de datos ocultos**.</span><span class="sxs-lookup"><span data-stu-id="11877-135">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="11877-136">El panel Datos de informe muestra todos los conjuntos de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="11877-136">The Report Data pane displays all datasets in the report.</span></span>

## <a name="see-also"></a><span data-ttu-id="11877-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11877-137">See Also</span></span>
 <span data-ttu-id="11877-138">[Analysis Services tipo de conexión para mdx &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services interfaz de usuario del diseñador de consultas MDX](analysis-services-mdx-query-designer-user-interface.md)</span><span class="sxs-lookup"><span data-stu-id="11877-138">[Analysis Services Connection Type for MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services MDX Query Designer User Interface](analysis-services-mdx-query-designer-user-interface.md)</span></span>


