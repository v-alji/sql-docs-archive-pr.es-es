---
title: Agregar o eliminar un indicador (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8b1aac1-53ef-47a4-afc0-8fa866c6c480
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 186ed4f5b6cf7cb239dc7c33a11089c11bccae14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747479"
---
# <a name="add-or-delete-an-indicator-report-builder-and-ssrs"></a><span data-ttu-id="7131a-102">Agregar o eliminar un indicador (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="7131a-102">Add or Delete an Indicator (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7131a-103">Los indicadores son medidores mínimos que comunican el estado del valor de un dato de un vistazo.</span><span class="sxs-lookup"><span data-stu-id="7131a-103">Indicators are minimal gauges that convey the state of a single data value at a glance.</span></span> <span data-ttu-id="7131a-104">Para obtener más información sobre ellos, vea [Indicadores &#40;Generador de informes y SSRS&#41;](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7131a-104">For more information about them, see [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="7131a-105">Los indicadores normalmente se colocan en celdas en una tabla o matriz, pero también puede utilizarlos solos, uno al lado de otro con medidores o incrustados en medidores.</span><span class="sxs-lookup"><span data-stu-id="7131a-105">Indicators are commonly placed in cells in a table or matrix, but you can also use indicators by themselves, side-by-side with gauges, or embedded in gauges.</span></span>  
  
 <span data-ttu-id="7131a-106">Al agregar por primera vez un indicador, de forma predeterminada se configura para utilizar los porcentajes como unidades de medida.</span><span class="sxs-lookup"><span data-stu-id="7131a-106">When you first add an indicator, it is by default configured to use percentages as measurement units.</span></span> <span data-ttu-id="7131a-107">Los intervalos de porcentaje se distribuyen uniformemente a través de los miembros del indicador establecido, y el ámbito de valores mostrado por el indicador es el elemento primario del indicador como una tabla o matriz.</span><span class="sxs-lookup"><span data-stu-id="7131a-107">The percentage ranges are evenly distributed across members of the indicator set, and the scope of values shown by the indicator is the parent of the indicator such as a table or matrix.</span></span>  
  
 <span data-ttu-id="7131a-108">Puede actualizar los valores y los estados de los indicadores.</span><span class="sxs-lookup"><span data-stu-id="7131a-108">You can update the values and states of indicators.</span></span> <span data-ttu-id="7131a-109">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7131a-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="7131a-110">Cambiar iconos de indicador y conjuntos de indicadores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7131a-110">Change Indicator Icons and Indicator Sets &#40;Report Builder and SSRS&#41;</span></span>](change-indicator-icons-and-indicator-sets-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="7131a-111">Establecer y configurar unidades de medida &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7131a-111">Set and Configure Measurement Units &#40;Report Builder and SSRS&#41;</span></span>](set-and-configure-measurement-units-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="7131a-112">Establecer el ámbito de sincronización &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7131a-112">Set Synchronization Scope &#40;Report Builder and SSRS&#41;</span></span>](set-synchronization-scope-report-builder-and-ssrs.md)  
  
 <span data-ttu-id="7131a-113">Dado que un indicador se coloca dentro del panel de medidor, necesita seleccionar el indicador en lugar del panel si desea configurar el indicador utilizando el cuadro de diálogo **Propiedades de los indicadores** o el panel **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="7131a-113">Because an indicator is positioned inside the gauge panel, you need to select the indicator instead of the panel when you want to configure the indicator by using the **Indicators Properties** dialog box or the **Properties** pane.</span></span> <span data-ttu-id="7131a-114">La imagen siguiente muestra un indicador seleccionado en su panel de medidor.</span><span class="sxs-lookup"><span data-stu-id="7131a-114">The following picture shows a selected indicator in its gauge panel.</span></span>  
  
 <span data-ttu-id="7131a-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span><span class="sxs-lookup"><span data-stu-id="7131a-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7131a-116">En función del ancho de columna y la longitud de los valores de los datos, el texto de la tabla o las celdas de la matriz, podría ajustar el texto y mostrarlo en varias líneas.</span><span class="sxs-lookup"><span data-stu-id="7131a-116">Depending on column width and the length of data values, the text in table or matrix cells might wrap and display text on multiple lines.</span></span> <span data-ttu-id="7131a-117">Cuando esto ocurre, el icono de indicador podría ajustarse y cambiar de forma.</span><span class="sxs-lookup"><span data-stu-id="7131a-117">When this occurs, the indicator icon might be stretched and change shape.</span></span> <span data-ttu-id="7131a-118">Esto puede hacer que el icono del indicador sea menos legible.</span><span class="sxs-lookup"><span data-stu-id="7131a-118">This can make the indicator icon less readable.</span></span> <span data-ttu-id="7131a-119">Coloque el indicador dentro de un rectángulo para asegurarse de que el icono nunca se ajusta.</span><span class="sxs-lookup"><span data-stu-id="7131a-119">Place the indicator inside a rectangle to ensure that the icon is never stretched.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="7131a-120">Agregar un indicador a una tabla o matriz</span><span class="sxs-lookup"><span data-stu-id="7131a-120">To add an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="7131a-121">Abra un informe existente o cree un informe que contenga una tabla y matriz con los datos que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="7131a-121">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="7131a-122">Para obtener más información, vea [Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) y [Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7131a-122">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="7131a-123">Inserte una columna en la tabla o matriz.</span><span class="sxs-lookup"><span data-stu-id="7131a-123">Insert a column in your table or matrix.</span></span> <span data-ttu-id="7131a-124">Para más información, vea [Insertar o eliminar una columna &#40;Generador de informes y SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7131a-124">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="7131a-125">Si lo desea, en la pestaña **Insertar** , haga clic en **Rectángulo**y, a continuación, haga clic en una celda en la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="7131a-125">Optionally, on the **Insert** tab, click **Rectangle**, and then click a cell in the new column.</span></span>  
  
4.  <span data-ttu-id="7131a-126">En la pestaña **Insertar** , haga clic en **Indicador**y, a continuación, haga clic en una celda en la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="7131a-126">On the **Insert** tab, click **Indicator**, and then click a cell in the new column.</span></span>  
  
     <span data-ttu-id="7131a-127">Si agregó un rectángulo a una celda, haga clic en ella.</span><span class="sxs-lookup"><span data-stu-id="7131a-127">If you added a rectangle to a cell, click that cell.</span></span>  
  
5.  <span data-ttu-id="7131a-128">En el cuadro de diálogo **Seleccionar estilo de indicador** , en el panel izquierdo, haga clic en el tipo de indicador que desea y, a continuación, haga clic en el indicador establecido.</span><span class="sxs-lookup"><span data-stu-id="7131a-128">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
6.  <span data-ttu-id="7131a-129">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="7131a-129">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="7131a-130">Haga clic en el indicador.</span><span class="sxs-lookup"><span data-stu-id="7131a-130">Click the indicator.</span></span> <span data-ttu-id="7131a-131">El panel **Medidor de datos** se abre.</span><span class="sxs-lookup"><span data-stu-id="7131a-131">The **Gauge Data** pane opens.</span></span>  
  
8.  <span data-ttu-id="7131a-132">En el área **Valores** , en la lista desplegable **(No especificado)** , haga clic en el campo cuyos valores quiera mostrar como un indicador.</span><span class="sxs-lookup"><span data-stu-id="7131a-132">In the **Values** area, in the **(Unspecified)** drop-down list, click the field whose values you want to display as an indicator.</span></span>  
  
     <span data-ttu-id="7131a-133">El indicador se configura para utilizar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="7131a-133">The indicator is configured to use default values.</span></span> <span data-ttu-id="7131a-134">De forma predeterminada, los indicadores son los porcentajes de uso configurados como unidades de medida, los intervalos de porcentaje se distribuyen uniformemente a través de los miembros del indicador y el valor que el indicador comunica utiliza el ámbito del grupo más cercano.</span><span class="sxs-lookup"><span data-stu-id="7131a-134">By default, indicators are configured use percentages as measurement units and the percentage ranges are evenly distributed across the members of the indicator and the value that the indicator conveys uses the scope of the nearest group.</span></span>  
  
### <a name="to-delete-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="7131a-135">Eliminar un indicador para una tabla o matriz</span><span class="sxs-lookup"><span data-stu-id="7131a-135">To delete an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="7131a-136">Haga clic con el botón derecho en el indicador y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7131a-136">Right-click the indicator to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7131a-137">Un indicador se podría colocar dentro de un panel de medidor que contenga otros indicadores o medidores.</span><span class="sxs-lookup"><span data-stu-id="7131a-137">An indicator might be positioned inside a gauge panel that contains other indicators or gauges.</span></span> <span data-ttu-id="7131a-138">Si los paneles de medidor contienen varios elementos, asegúrese de hacer clic en el indicador para eliminarlo, no el panel de medidor.</span><span class="sxs-lookup"><span data-stu-id="7131a-138">If the gauge panels contain multiple items, be sure to click the indicator to delete it, not the gauge panel.</span></span> <span data-ttu-id="7131a-139">Si hace clic y, a continuación, elimina el panel de medidor, se eliminan todos los paneles de medidor y sus elementos.</span><span class="sxs-lookup"><span data-stu-id="7131a-139">If you click and then delete the gauge panel, the gauge panels and all the items in it are deleted.</span></span>  
  
2.  <span data-ttu-id="7131a-140">Haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7131a-140">Click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7131a-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7131a-141">See Also</span></span>  
 [<span data-ttu-id="7131a-142">Indicadores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7131a-142">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
