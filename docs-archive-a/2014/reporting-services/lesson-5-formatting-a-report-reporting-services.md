---
title: 'Lección 5: Aplicar formato a un informe (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae46efa9-6e04-48ec-afb4-5a2314dcb05a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00f0d780e957fd9ff995fefb1d033275a7da428d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676874"
---
# <a name="lesson-5-formatting-a-report-reporting-services"></a><span data-ttu-id="995d9-102">Lesson 5: Formatting a Report (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="995d9-102">Lesson 5: Formatting a Report (Reporting Services)</span></span>
  <span data-ttu-id="995d9-103">Ahora que ha agregado una región de datos y algunos campos al informe Sales Orders, puede dar formato a los campos de moneda y de fecha, así como a los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="995d9-103">Now that you've added a data region and some fields to the Sales Orders report, you can format the date and currency fields and the column headers.</span></span>  
  
 <span data-ttu-id="995d9-104">En este tema:</span><span class="sxs-lookup"><span data-stu-id="995d9-104">In this topic:</span></span>  
  
-   [<span data-ttu-id="995d9-105">Dar formato a la fecha</span><span class="sxs-lookup"><span data-stu-id="995d9-105">Format the Date</span></span>](#bkmk_format_date)  
  
-   [<span data-ttu-id="995d9-106">Dar formato a la moneda</span><span class="sxs-lookup"><span data-stu-id="995d9-106">Format the Currency</span></span>](#bkmk_format_currency)  
  
-   [<span data-ttu-id="995d9-107">Cambiar el estilo de texto y los anchos de columna</span><span class="sxs-lookup"><span data-stu-id="995d9-107">Change Text Style and Column Widths</span></span>](#bkmk_change_textstyle)  
  
##  <a name="format-the-date"></a><a name="bkmk_format_date"></a><span data-ttu-id="995d9-108">Dar formato a la fecha</span><span class="sxs-lookup"><span data-stu-id="995d9-108">Format the Date</span></span>  
 <span data-ttu-id="995d9-109">En el campo Date, se muestra información de fecha y hora de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="995d9-109">The Date field displays date and time information by default.</span></span> <span data-ttu-id="995d9-110">Puede darle formato para mostrar solo la fecha.</span><span class="sxs-lookup"><span data-stu-id="995d9-110">You can format it to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field"></a><span data-ttu-id="995d9-111">Para dar formato a un campo de fecha</span><span class="sxs-lookup"><span data-stu-id="995d9-111">To format a date field</span></span>  
  
1.  <span data-ttu-id="995d9-112">Haga clic en la pestaña **Diseño** .</span><span class="sxs-lookup"><span data-stu-id="995d9-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="995d9-113">Haga clic con el botón derecho en la celda con la expresión de campo `[Date]` y, después, haga clic en **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="995d9-113">Right-click the cell with the `[Date]` field expression and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="995d9-114">Haga clic en **número**y, a continuación, en el campo **categoría** , seleccione `Date` .</span><span class="sxs-lookup"><span data-stu-id="995d9-114">Click **Number**, and then in the **Category** field, select `Date`.</span></span>  
  
4.  <span data-ttu-id="995d9-115">En el cuadro **Tipo** , seleccione **January 31, 2000**.</span><span class="sxs-lookup"><span data-stu-id="995d9-115">In the **Type** box, select **January 31, 2000**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="995d9-116">Obtenga una vista previa del informe para ver el cambio en el campo `[Date]` y, después, vuelva a cambiar a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="995d9-116">Preview the report to see the change to the `[Date]` field and then change back to design view.</span></span>  
  
##  <a name="format-the-currency"></a><a name="bkmk_format_currency"></a><span data-ttu-id="995d9-117">Dar formato a la moneda</span><span class="sxs-lookup"><span data-stu-id="995d9-117">Format the Currency</span></span>  
 <span data-ttu-id="995d9-118">El campo LineTotal muestra un número general.</span><span class="sxs-lookup"><span data-stu-id="995d9-118">The LineTotal field displays a general number.</span></span> <span data-ttu-id="995d9-119">Aplíquele el formato adecuado para mostrar el número como moneda.</span><span class="sxs-lookup"><span data-stu-id="995d9-119">Format it to display the number as currency.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="995d9-120">Para dar formato a un campo de moneda</span><span class="sxs-lookup"><span data-stu-id="995d9-120">To format a currency field</span></span>  
  
1.  <span data-ttu-id="995d9-121">Haga clic con el botón derecho en la celda con la expresión de campo `[LineTotal]` y, después, haga clic en **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="995d9-121">Right-click the cell with the `[LineTotal]` field expression and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="995d9-122">Haga clic en **Número**y, en el campo **Categoría** , seleccione **Moneda**.</span><span class="sxs-lookup"><span data-stu-id="995d9-122">Click **Number**, and in the **Category** field, select **Currency**.</span></span>  
  
3.  <span data-ttu-id="995d9-123">Si la configuración regional es Inglés (Estados Unidos), los valores predeterminados deberían ser:</span><span class="sxs-lookup"><span data-stu-id="995d9-123">If your regional setting is English (United States), the defaults should be:</span></span>  
  
    -   <span data-ttu-id="995d9-124">**Decimales: 2**</span><span class="sxs-lookup"><span data-stu-id="995d9-124">**Decimal places: 2**</span></span>  
  
    -   <span data-ttu-id="995d9-125">**Números negativos: ($12345.00)**</span><span class="sxs-lookup"><span data-stu-id="995d9-125">**Negative numbers: ($12345.00)**</span></span>  
  
    -   <span data-ttu-id="995d9-126">**Símbolo: $ Inglés (Estados Unidos)**</span><span class="sxs-lookup"><span data-stu-id="995d9-126">**Symbol: $ English (United States)**</span></span>  
  
4.  <span data-ttu-id="995d9-127">Seleccione **Usar separador de miles (.)**.</span><span class="sxs-lookup"><span data-stu-id="995d9-127">Select **Use 1000 separator (,)**.</span></span>  
  
     <span data-ttu-id="995d9-128">Si el texto de ejemplo es:**$12,345.00**, la configuración es correcta.</span><span class="sxs-lookup"><span data-stu-id="995d9-128">If the sample text is:**$12,345.00**, then your settings are correct.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="995d9-129">Obtenga una vista previa del informe para ver el cambio en el campo `[LineTotal]` y, después, vuelva a cambiar a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="995d9-129">Preview the report to see the change to the `[LineTotal]` field and then change back to design view.</span></span>  
  
##  <a name="change-text-style-and-column-widths"></a><a name="bkmk_change_textstyle"></a><span data-ttu-id="995d9-130">Cambiar el estilo de texto y los anchos de columna</span><span class="sxs-lookup"><span data-stu-id="995d9-130">Change Text Style and Column Widths</span></span>  
 <span data-ttu-id="995d9-131">También puede cambiar el formato de la fila de encabezado para diferenciarlo de las filas de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="995d9-131">You can also change the formatting of the header row to differentiate it from the rows of data in the report.</span></span> <span data-ttu-id="995d9-132">Por último, ajustará el ancho de las columnas.</span><span class="sxs-lookup"><span data-stu-id="995d9-132">Lastly, you will adjust the widths of the columns.</span></span>  
  
#### <a name="to-format-header-rows-and-table-columns"></a><span data-ttu-id="995d9-133">Para dar formato a las filas de encabezado y las columnas de tabla</span><span class="sxs-lookup"><span data-stu-id="995d9-133">To format header rows and table columns</span></span>  
  
1.  <span data-ttu-id="995d9-134">Haga clic en la tabla para que los identificadores de columna y de fila aparezcan encima y al lado de la tabla.</span><span class="sxs-lookup"><span data-stu-id="995d9-134">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="995d9-135">![Diseño, Tabla con fila de encabezado y fila de detalle](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Diseño, Tabla con fila de encabezado y fila de detalle")</span><span class="sxs-lookup"><span data-stu-id="995d9-135">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
     <span data-ttu-id="995d9-136">Las barras grises situadas en la parte superior y en el lado de la tabla son los identificadores de fila y de columna.</span><span class="sxs-lookup"><span data-stu-id="995d9-136">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
2.  <span data-ttu-id="995d9-137">Sitúe el cursor en la línea que hay entre los controladores de columna para que cambie a una flecha doble.</span><span class="sxs-lookup"><span data-stu-id="995d9-137">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="995d9-138">Arrastre las columnas hasta que tengan el tamaño deseado.</span><span class="sxs-lookup"><span data-stu-id="995d9-138">Drag the columns to the size you want.</span></span>  
  
3.  <span data-ttu-id="995d9-139">Seleccione la fila que contiene las etiquetas de los encabezados de columna y, en el menú **Formato** , seleccione **Fuente** y, a continuación, haga clic en **Negrita**.</span><span class="sxs-lookup"><span data-stu-id="995d9-139">Select the row containing column header labels and from the **Format** menu, point to **Font** and then click **Bold**.</span></span>  
  
4.  <span data-ttu-id="995d9-140">Para obtener una vista previa del informe, haga clic en la pestaña **vista previa** . Debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="995d9-140">To preview your report, click the **Preview** tab. It should look something like this:</span></span>  
  
     <span data-ttu-id="995d9-141">![Vista previa de la tabla con encabezados de columna en negrita](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Vista previa de la tabla con encabezados de columna en negrita")</span><span class="sxs-lookup"><span data-stu-id="995d9-141">![Preview of table with bold column headers](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Preview of table with bold column headers")</span></span>  
  
5.  <span data-ttu-id="995d9-142">En el menú **Archivo** , haga clic en **Guardar todo** para guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="995d9-142">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="995d9-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="995d9-143">Next Steps</span></span>  
 <span data-ttu-id="995d9-144">Ha aplicado formato correctamente a los encabezados de columna y los valores de moneda y fecha.</span><span class="sxs-lookup"><span data-stu-id="995d9-144">You have successfully formatted column headers and date and currency values.</span></span> <span data-ttu-id="995d9-145">A continuación, agregará características de agrupación y totales al informe.</span><span class="sxs-lookup"><span data-stu-id="995d9-145">Next, you will add grouping and totals to your report.</span></span> <span data-ttu-id="995d9-146">Vea [Lección 6: Agregar grupos y totales &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="995d9-146">See [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="995d9-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="995d9-147">See Also</span></span>  
 <span data-ttu-id="995d9-148">[Aplicar formato a números y fechas &#40;Generador de informes y SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="995d9-148">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="995d9-149">Comportamientos de la representación &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="995d9-149">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](report-design/rendering-behaviors-report-builder-and-ssrs.md)  
  
  
