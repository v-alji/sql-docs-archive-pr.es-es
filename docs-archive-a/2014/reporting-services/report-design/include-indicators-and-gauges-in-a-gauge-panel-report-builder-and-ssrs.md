---
title: Incluir indicadores y medidores en un panel de medidores (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4dff9b67-b483-4c51-a822-6dbe706a6840
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b1107745f54cd94abd7507a3e9b5a706ca5402de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749119"
---
# <a name="include-indicators-and-gauges-in-a-gauge-panel-report-builder-and-ssrs"></a><span data-ttu-id="841eb-102">Incluir indicadores y medidores en un panel de medidores (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="841eb-102">Include Indicators and Gauges in a Gauge Panel (Report Builder and SSRS)</span></span>
  <span data-ttu-id="841eb-103">El panel de medidores es el contenedor de nivel superior que contiene uno o más medidores e indicadores.</span><span class="sxs-lookup"><span data-stu-id="841eb-103">The gauge panel is the top-level container that holds one or more gauges and indicators.</span></span> <span data-ttu-id="841eb-104">Los indicadores se pueden incrustar en los medidores o colocar a su lado en el panel de medidores.</span><span class="sxs-lookup"><span data-stu-id="841eb-104">Indicators can be embedded in gauges or placed next to them in the gauge panel.</span></span>  
  
 <span data-ttu-id="841eb-105">Si el indicador y el medidor son adyacentes en el panel de medidores y muestran datos de campos distintos, podría desear agregar etiquetas para dejar claro qué datos comunican el medidor y el indicador.</span><span class="sxs-lookup"><span data-stu-id="841eb-105">If the indicator and gauge are adjacent in the gauge panel and show data from different fields, you might want to add labels to make it clear what data the gauge and indicator convey.</span></span>  
  
 <span data-ttu-id="841eb-106">Las opciones del medidor y el indicador se pueden establecer mediante expresiones.</span><span class="sxs-lookup"><span data-stu-id="841eb-106">Gauge and indicator options can be set by using expressions.</span></span> <span data-ttu-id="841eb-107">Para más información, vea [Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="841eb-107">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-indicator-in-a-gauge"></a><span data-ttu-id="841eb-108">Para incrustar un indicador en un medidor</span><span class="sxs-lookup"><span data-stu-id="841eb-108">To embed an indicator in a gauge</span></span>  
  
1.  <span data-ttu-id="841eb-109">Abra un informe existente o cree un informe que contenga una tabla y matriz con los datos que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="841eb-109">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="841eb-110">Para obtener más información, vea [Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) y [Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="841eb-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="841eb-111">Inserte una columna en la tabla o matriz.</span><span class="sxs-lookup"><span data-stu-id="841eb-111">Insert a column in your table or matrix.</span></span> <span data-ttu-id="841eb-112">Para más información, vea [Insertar o eliminar una columna &#40;Generador de informes y SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="841eb-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="841eb-113">En la pestaña **Insertar** , en el grupo **Regiones de datos** , haga clic en **Medidor**y, a continuación, en una de las celdas de la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="841eb-113">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then, and then click a cell in the new column.</span></span> <span data-ttu-id="841eb-114">Aparece el cuadro de diálogo **Seleccionar tipo de medidor** .</span><span class="sxs-lookup"><span data-stu-id="841eb-114">The **Select Gauge Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="841eb-115">Haga clic en **Radial**.</span><span class="sxs-lookup"><span data-stu-id="841eb-115">Click **Radial**.</span></span> <span data-ttu-id="841eb-116">Se selecciona el primer medidor radial.</span><span class="sxs-lookup"><span data-stu-id="841eb-116">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="841eb-117">Haga clic en el medidor.</span><span class="sxs-lookup"><span data-stu-id="841eb-117">Click the gauge.</span></span> <span data-ttu-id="841eb-118">El panel **Medidor de datos** se abre.</span><span class="sxs-lookup"><span data-stu-id="841eb-118">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="841eb-119">En el área **Valores** , en el cuadro de lista **(Sin especificar)** , haga clic en el campo cuyos valores quiere que se muestren en el medidor.</span><span class="sxs-lookup"><span data-stu-id="841eb-119">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="841eb-120">Si lo prefiere, puede arrastrar el campo que desea utilizar desde el conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="841eb-120">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="841eb-121">Haga clic con el botón derecho en el medidor, haga clic en **Agregar indicador**y, después, haga clic en **Secundario**.</span><span class="sxs-lookup"><span data-stu-id="841eb-121">Right-click the gauge, click **Add Indicator**, and then click **Child**.</span></span> <span data-ttu-id="841eb-122">Se abre el cuadro de diálogo **Seleccionar estilo de indicador** .</span><span class="sxs-lookup"><span data-stu-id="841eb-122">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="841eb-123">En el cuadro de diálogo **Seleccionar estilo de indicador** , en el panel izquierdo, haga clic en el tipo de indicador que desea y, a continuación, haga clic en el indicador establecido.</span><span class="sxs-lookup"><span data-stu-id="841eb-123">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="841eb-124">Haga clic en el indicador.</span><span class="sxs-lookup"><span data-stu-id="841eb-124">Click the indicator.</span></span> <span data-ttu-id="841eb-125">El panel **Medidor de datos** se abre.</span><span class="sxs-lookup"><span data-stu-id="841eb-125">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="841eb-126">En el área **Valores** , en el cuadro de lista **(Sin especificar)** , haga clic en el campo cuyos valores quiera mostrar como un indicador.</span><span class="sxs-lookup"><span data-stu-id="841eb-126">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="841eb-127">Si lo prefiere, puede arrastrar el campo que desea utilizar desde el conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="841eb-127">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="841eb-128">El campo puede ser el mismo que el utilizado en el medidor, u otro distinto.</span><span class="sxs-lookup"><span data-stu-id="841eb-128">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-show-an-indicator-and-gauge-side-by-side"></a><span data-ttu-id="841eb-129">Para mostrar un indicador y medidor en paralelo</span><span class="sxs-lookup"><span data-stu-id="841eb-129">To show an indicator and gauge side by side</span></span>  
  
1.  <span data-ttu-id="841eb-130">Abra un informe existente o cree un informe que contenga una tabla y matriz con los datos que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="841eb-130">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="841eb-131">Para obtener más información, vea [Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) y [Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="841eb-131">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="841eb-132">Inserte una columna en la tabla o matriz.</span><span class="sxs-lookup"><span data-stu-id="841eb-132">Insert a column in your table or matrix.</span></span> <span data-ttu-id="841eb-133">Para más información, vea [Insertar o eliminar una columna &#40;Generador de informes y SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="841eb-133">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="841eb-134">En la pestaña **Insertar** , en el grupo **Regiones de datos** , haga clic en **Medidor**y, a continuación, en una de las celdas de la columna que ha insertado.</span><span class="sxs-lookup"><span data-stu-id="841eb-134">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click a cell in the column you inserted.</span></span> <span data-ttu-id="841eb-135">Aparecerá el cuadro de diálogo **Seleccionar tipo de medidor** .</span><span class="sxs-lookup"><span data-stu-id="841eb-135">The **Select Gauge Type** dialog appears.</span></span>  
  
4.  <span data-ttu-id="841eb-136">Haga clic en **Radial**.</span><span class="sxs-lookup"><span data-stu-id="841eb-136">Click **Radial**.</span></span> <span data-ttu-id="841eb-137">Se selecciona el primer medidor radial.</span><span class="sxs-lookup"><span data-stu-id="841eb-137">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="841eb-138">Haga clic en el medidor.</span><span class="sxs-lookup"><span data-stu-id="841eb-138">Click the gauge.</span></span> <span data-ttu-id="841eb-139">El panel **Medidor de datos** se abre.</span><span class="sxs-lookup"><span data-stu-id="841eb-139">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="841eb-140">En el área **Valores** , en el cuadro de lista **(Sin especificar)** , haga clic en el campo cuyos valores quiere que se muestren en el medidor.</span><span class="sxs-lookup"><span data-stu-id="841eb-140">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="841eb-141">Si lo prefiere, puede arrastrar el campo que desea utilizar desde el conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="841eb-141">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="841eb-142">Haga clic con el botón derecho en el medidor, haga clic en **Agregar indicador**y, después, haga clic en **Adyacente**.</span><span class="sxs-lookup"><span data-stu-id="841eb-142">Right-click the gauge, click **Add Indicator**, and then click **Adjacent**.</span></span> <span data-ttu-id="841eb-143">Se abre el cuadro de diálogo **Seleccionar estilo de indicador** .</span><span class="sxs-lookup"><span data-stu-id="841eb-143">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="841eb-144">En el cuadro de diálogo **Seleccionar estilo de indicador** , en el panel izquierdo, haga clic en el tipo de indicador que desea y, a continuación, haga clic en el indicador establecido.</span><span class="sxs-lookup"><span data-stu-id="841eb-144">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="841eb-145">Haga clic en el indicador.</span><span class="sxs-lookup"><span data-stu-id="841eb-145">Click the indicator.</span></span> <span data-ttu-id="841eb-146">El panel **Medidor de datos** se abre.</span><span class="sxs-lookup"><span data-stu-id="841eb-146">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="841eb-147">En el área **Valores** , en el cuadro de lista **(Sin especificar)** , haga clic en el campo cuyos valores quiera mostrar como un indicador.</span><span class="sxs-lookup"><span data-stu-id="841eb-147">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="841eb-148">Si lo prefiere, puede arrastrar el campo que desea utilizar desde el conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="841eb-148">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="841eb-149">El campo puede ser el mismo que el utilizado en el medidor, u otro distinto.</span><span class="sxs-lookup"><span data-stu-id="841eb-149">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
14. <span data-ttu-id="841eb-150">Haga clic con el botón derecho en el panel de medidores y, después, haga clic en **Agregar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="841eb-150">Right-click the gauge panel and click **Add Label**.</span></span> <span data-ttu-id="841eb-151">Se agregará una etiqueta al panel de medidores.</span><span class="sxs-lookup"><span data-stu-id="841eb-151">A label is added to the gauge panel.</span></span> <span data-ttu-id="841eb-152">Realice los mismos pasos una vez más.</span><span class="sxs-lookup"><span data-stu-id="841eb-152">Repeat one more time.</span></span>  
  
     <span data-ttu-id="841eb-153">En el panel de medidores habrá dos etiquetas.</span><span class="sxs-lookup"><span data-stu-id="841eb-153">The gauge panel has two labels.</span></span>  
  
15. <span data-ttu-id="841eb-154">Arrastre cada etiqueta hasta un lugar próximo al medidor o indicador.</span><span class="sxs-lookup"><span data-stu-id="841eb-154">Drag each label to a location near the gauge or indicator.</span></span>  
  
16. <span data-ttu-id="841eb-155">Haga clic con el botón derecho en la etiqueta próxima al medidor, haga clic en **Propiedades de etiqueta**y escriba el texto que quiera en el cuadro **Texto** .</span><span class="sxs-lookup"><span data-stu-id="841eb-155">Right-click the label near the gauge, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
17. <span data-ttu-id="841eb-156">Haga clic con el botón derecho en la etiqueta próxima al indicador, haga clic en **Propiedades de etiqueta**y escriba el texto que quiera en el cuadro **Texto** .</span><span class="sxs-lookup"><span data-stu-id="841eb-156">Right-click the label near the indicator, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
18. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="841eb-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="841eb-157">See Also</span></span>  
 [<span data-ttu-id="841eb-158">Indicadores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="841eb-158">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
