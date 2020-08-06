---
title: Crear un mapa del documento (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c200a97b-67f2-499f-8374-3ed1ebe3f33c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a9dad0f8e6ee1d9b9ada44fda0eec5908f27cfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671435"
---
# <a name="create-a-document-map-report-builder-and-ssrs"></a><span data-ttu-id="c8ad7-102">Crear un mapa del documento (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="c8ad7-102">Create a Document Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c8ad7-103">Un mapa del documento proporciona un conjunto de vínculos de navegación a los elementos de informe de un informe representado.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-103">A document map provides a set of navigational links to report items in a rendered report.</span></span> <span data-ttu-id="c8ad7-104">Cuando se ve un informe que incluya un mapa del documento, aparece un panel lateral separado junto al informe.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-104">When you view a report that includes a document map, a separate side pane appears next to the report.</span></span> <span data-ttu-id="c8ad7-105">Un usuario puede hacer clic en los vínculos del mapa del documento para saltar a la página del informe que muestra el elemento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-105">A user can click links in the document map to jump to the report page that displays that item.</span></span> <span data-ttu-id="c8ad7-106">Las secciones y los grupos del informe se organizan en una jerarquía de vínculos.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-106">Report sections and groups are arranged in a hierarchy of links.</span></span> <span data-ttu-id="c8ad7-107">Cada vez que se hace clic en un elemento del mapa del documento, se actualiza el informe y se muestra el área del mismo correspondiente a dicho elemento en el mapa del documento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-107">Clicking items in the document map refreshes the report and displays the area of the report that corresponds to the item in the document map.</span></span>  
  
 <span data-ttu-id="c8ad7-108">Para agregar vínculos al mapa del documento, se establece la propiedad `DocumentMapLabel` del elemento de informe en un texto o en una expresión que se evalúa como el texto que se desea mostrar en el mapa del documento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-108">To add links to the document map, you set the `DocumentMapLabel` property of the report item to text that you create or to an expression that evaluates to the text that you want display in the document map.</span></span> <span data-ttu-id="c8ad7-109">También puede agregar los valores únicos para un grupo de tablas o de matrices al mapa del documento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-109">You can also add the unique values for a table or matrix group to the document map.</span></span> <span data-ttu-id="c8ad7-110">Por ejemplo, para un grupo basado en colores, cada color único es un vínculo a la página del informe que muestra la instancia de grupo para ese color.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-110">For example, for a group based on color, each unique color is a link to the report page that displays the group instance for that color.</span></span>  
  
 <span data-ttu-id="c8ad7-111">También puede crear una dirección URL a un informe que invalide la presentación del mapa del documento, lo que le permite ejecutar el informe sin mostrar el mapa del documento y, después, hacer clic en el botón **Mostrar u ocultar mapa del documento** de la barra de herramientas del visor de informes para alternar la presentación.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-111">You can also create a URL to a report that overrides the display of the document map, so that you can run the report without displaying the document map, and then click the **Show/Hide Document Map** button on the report viewer toolbar to toggle the display.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="document-maps-and-rendering-extensions"></a><a name="DocMapRenderExtensions"></a> <span data-ttu-id="c8ad7-112">Mapas de documento y extensiones de representación</span><span class="sxs-lookup"><span data-stu-id="c8ad7-112">Document Maps and Rendering Extensions</span></span>  
 <span data-ttu-id="c8ad7-113">El mapa del documento está pensado para usarlo en la extensión de representación de HTML, por ejemplo, en la vista previa y el visor de informes.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-113">The document map is intended for use in the HTML rendering extension-for example, in Preview and the Report Viewer.</span></span> <span data-ttu-id="c8ad7-114">Otras extensiones de representación tienen diferentes formas de articular un mapa del documento:</span><span class="sxs-lookup"><span data-stu-id="c8ad7-114">Other rendering extensions have different ways of articulating a document map:</span></span>  
  
-   <span data-ttu-id="c8ad7-115">PDF representa un mapa del documento como el panel Marcadores.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-115">PDF renders a document map as the Bookmarks pane.</span></span>  
  
-   <span data-ttu-id="c8ad7-116">Excel representa un mapa del documento como una hoja con nombre que incluye una jerarquía de vínculos.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-116">Excel renders a document map as a named worksheet that includes a hierarchy of links.</span></span> <span data-ttu-id="c8ad7-117">Las secciones del informe se representan en hojas separadas que se incluyen con el mapa del documento en el mismo libro.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-117">Report sections are rendered in separate worksheets that are included with the document map in the same workbook.</span></span>  
  
-   <span data-ttu-id="c8ad7-118">Word representa el mapa del documento como la tabla de contenido.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-118">Word includes a document map as the table of contents.</span></span>  
  
-   <span data-ttu-id="c8ad7-119">Atom, TIFF, XML y CSV omiten los mapas de documento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-119">Atom, TIFF, XML, and CSV ignore document maps.</span></span>  
  
 <span data-ttu-id="c8ad7-120">Para más información, vea [Funcionalidad interactiva para diferentes extensiones de representación de informes &#40;Generador de informes y SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="c8ad7-120">For more information, see [Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span></span>  
  
##  <a name="AddRptItemToMap"></a>   
#### <a name="to-add-a-report-item-to-a-document-map"></a><span data-ttu-id="c8ad7-121">Para agregar un elemento de informe a un mapa del documento</span><span class="sxs-lookup"><span data-stu-id="c8ad7-121">To add a report item to a document map</span></span>  
  
1.  <span data-ttu-id="c8ad7-122">En la vista de diseño, seleccione el elemento de informe (tabla, matriz o medidor, por ejemplo) que desea agregar al mapa del documento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-122">In Design view, select the report item such as a table, matrix, or gauge that you want to add to the document map.</span></span> <span data-ttu-id="c8ad7-123">Las propiedades del elemento de informe aparecen en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-123">The report item properties appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c8ad7-124">Para seleccionar una región de datos Tablix, haga clic en cualquier celda para mostrar los identificadores de fila y de columna y, a continuación, haga clic en el controlador de tabla.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-124">To select a tablix data region, click in any cell to display the row and column handles, and then click the corner handle.</span></span>  
  
2.  <span data-ttu-id="c8ad7-125">En el panel Propiedades, escriba el texto que desea que aparezca en el mapa del documento en la `DocumentMapLabel` propiedad o escriba una expresión que se evalúe como una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-125">In the Properties pane, type the text that you want to appear in the document map in the `DocumentMapLabel` property, or enter an expression that evaluates to a label.</span></span> <span data-ttu-id="c8ad7-126">Por ejemplo, escriba **Gráfico de ventas**.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-126">For example, type **Sales Chart**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c8ad7-127">Si no ve el panel de propiedades, en la pestaña **Vista** , en el grupo **Mostrar u ocultar** , seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-127">If you do not see the Properties pane, on the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="c8ad7-128">Repita los pasos 1 y 2 para cada elemento de informe que desee que aparezca en el mapa del documento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-128">Repeat steps 1 and 2 for every report item that you want to appear in the document map.</span></span>  
  
4.  <span data-ttu-id="c8ad7-129">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-129">Click **Run**.</span></span> <span data-ttu-id="c8ad7-130">El informe se ejecuta y el mapa del documento muestra las etiquetas que ha creado.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-130">The report runs and the document map displays the labels you created.</span></span> <span data-ttu-id="c8ad7-131">Haga clic en cualquier vínculo para saltar a la página del informe que contiene ese elemento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-131">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="AddUniqueValuesToMap"></a>   
#### <a name="to-add-unique-group-values-to-a-document-map"></a><span data-ttu-id="c8ad7-132">Para agregar valores de grupo únicos a un mapa del documento</span><span class="sxs-lookup"><span data-stu-id="c8ad7-132">To add unique group values to a document map</span></span>  
  
1.  <span data-ttu-id="c8ad7-133">En la vista Diseño, seleccione la tabla, la matriz o la lista que contiene el grupo que desea mostrar en el mapa del documento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-133">In Design view, select the table, matrix, or list that contains the group that you want to display in the document map.</span></span> <span data-ttu-id="c8ad7-134">El Panel de agrupación muestra los grupos de filas y de columnas.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-134">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="c8ad7-135">En el panel Grupos de filas, haga clic con el botón derecho en el grupo y, después, haga clic en **Editar grupo**.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-135">In the Row Groups pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="c8ad7-136">Se abre la página **General** del cuadro de diálogo **Propiedades de grupo de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="c8ad7-136">The **General** page of the **Tablix Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c8ad7-137">Haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-137">Click **Advanced**.</span></span>  
  
4.  <span data-ttu-id="c8ad7-138">En el cuadro de lista **Mapa del documento** , escriba o seleccione una expresión que coincida con la expresión de grupo.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-138">In the **Document map** list box, type or select an expression that matches the group expression.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c8ad7-139">Repita los pasos 1 a 4 para cada grupo que desee que aparezca en el mapa del documento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-139">Repeat steps 1-4 for every group that you want to appear in the document map.</span></span>  
  
7.  <span data-ttu-id="c8ad7-140">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-140">Click **Run**.</span></span> <span data-ttu-id="c8ad7-141">El informe se ejecuta y el mapa del documento muestra los valores de grupo.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-141">The report runs and the document map displays the group values.</span></span> <span data-ttu-id="c8ad7-142">Haga clic en cualquier vínculo para saltar a la página del informe que contiene ese elemento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-142">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="HideMapWhenViewRpt"></a>   
#### <a name="to-hide-the-document-map-when-you-view-a-report"></a><span data-ttu-id="c8ad7-143">Para ocultar el mapa del documento al ver un informe</span><span class="sxs-lookup"><span data-stu-id="c8ad7-143">To hide the document map when you view a report</span></span>  
  
1.  <span data-ttu-id="c8ad7-144">En el Administrador de informes, busque el informe que contiene el mapa del documento.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-144">In Report Manager, browse to the report that has the document map.</span></span>  
  
     <span data-ttu-id="c8ad7-145">Por ejemplo, para los informes de ejemplo de [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] , la dirección URL siguiente especifica el informe denominado Product Catalog.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-145">For example, for the [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] sample reports, the following URL specifies the report named Product Catalog.</span></span>  
  
    ```  
    http://localhost/Reports/Pages/Report.aspx?ItemPath=%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    ```  
  
2.  <span data-ttu-id="c8ad7-146">Copie la ruta de acceso del informe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-146">Copy the report path on the server.</span></span> <span data-ttu-id="c8ad7-147">En el ejemplo, la ruta de acceso del informe es `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-147">In the example, the report path is `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span></span>  
  
3.  <span data-ttu-id="c8ad7-148">Cree una nueva dirección URL con los tres componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="c8ad7-148">Create a new URL with the following three components:</span></span>  
  
    -   <span data-ttu-id="c8ad7-149">El visor de informes en el servidor de informes: `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span><span class="sxs-lookup"><span data-stu-id="c8ad7-149">The report viewer on the report server: `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span></span>  
  
    -   <span data-ttu-id="c8ad7-150">El nombre del informe que copió en el paso 1, por ejemplo: `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span><span class="sxs-lookup"><span data-stu-id="c8ad7-150">The name of the report you copied in step 1, for example: `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span></span>  
  
    -   <span data-ttu-id="c8ad7-151">Los parámetros de información de dispositivo que especifican que se oculte el mapa del documento: `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span><span class="sxs-lookup"><span data-stu-id="c8ad7-151">The device information parameters that specify hiding the document map: `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span></span>  
  
     <span data-ttu-id="c8ad7-152">La dirección URL siguiente consta de estos tres componentes anexados en el orden de la lista.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-152">The following URL consists of these three components appended in the order they are listed.</span></span>  
  
    ```  
    http://localhost/ReportServer/Pages/ReportViewer.aspx?  
    %2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    &rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False  
    ```  
  
     <span data-ttu-id="c8ad7-153">Para usar esta dirección URL, cópiela y quite todos los saltos de línea.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-153">To use this URL, copy it and remove all line breaks.</span></span>  
  
4.  <span data-ttu-id="c8ad7-154">Pegue la dirección URL en el Administrador de informes y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-154">Paste the URL in Report Manager, and then press ENTER.</span></span> <span data-ttu-id="c8ad7-155">El informe se ejecuta con el mapa del documento oculto.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-155">The report runs, and the document map is hidden.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8ad7-156"> Para obtener más información sobre cómo descargar los informes de ejemplo, consulte [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Informes de ejemplo del Generador de informes y el Diseñador de informes](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="c8ad7-156">For more information about downloading sample reports, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
>   
>  <span data-ttu-id="c8ad7-157">Para obtener más información, vea el tema acerca del acceso URL en la [documentación de Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c8ad7-157">For more information, see "URL Access" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="c8ad7-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8ad7-158">See Also</span></span>  
 [<span data-ttu-id="c8ad7-159">Buscar y ver informes en el Administrador de informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c8ad7-159">Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md)  
  
  
