---
title: Agregar un marcador a un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f130562e-5673-40e3-8e01-de7227a21d41
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fae543dd1b071ff38853637a3da57ffd2410c3a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749122"
---
# <a name="add-a-bookmark-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="bb991-102">Agregar un marcador a un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="bb991-102">Add a Bookmark to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bb991-103">Agregue marcadores y vínculos de marcador a un informe si desea incluir una tabla de contenido personalizada o vínculos de navegación interna personalizados en el informe.</span><span class="sxs-lookup"><span data-stu-id="bb991-103">Add bookmarks and bookmark links to a report when you want to provide a customized table of contents or to provide customized internal navigation links in the report.</span></span> <span data-ttu-id="bb991-104">Normalmente, se agregan marcadores a las ubicaciones del informe a las que se desea dirigir a los usuarios, como las tablas, los gráficos o los valores de grupo únicos mostrados en una tabla o matriz.</span><span class="sxs-lookup"><span data-stu-id="bb991-104">Typically, you add bookmarks to locations in the report to which you want to direct users, such as to each table or chart or to the unique group values displayed in a table or matrix.</span></span> <span data-ttu-id="bb991-105">Puede crear sus propias cadenas para usarlas como marcadores o, para los grupos, puede establecer el marcador en la expresión de grupo.</span><span class="sxs-lookup"><span data-stu-id="bb991-105">You can create your own strings to use as bookmarks, or, for groups, you can set the bookmark to the group expression.</span></span>  
  
 <span data-ttu-id="bb991-106">Una vez creados los marcadores, puede agregar elementos de informe en los que el usuario puede hacer clic para desplazarse a cada marcador.</span><span class="sxs-lookup"><span data-stu-id="bb991-106">After you create bookmarks, you can add report items that the user can click to go to each bookmark.</span></span> <span data-ttu-id="bb991-107">Normalmente, estos elementos son cuadros de texto o imágenes.</span><span class="sxs-lookup"><span data-stu-id="bb991-107">These items are typically text boxes or images.</span></span>  
  
 <span data-ttu-id="bb991-108">Por ejemplo, si el informe muestra una tabla agrupada por color, podría agregar un marcador basado en la expresión de grupo al encabezado de grupo.</span><span class="sxs-lookup"><span data-stu-id="bb991-108">For example, if your report displays a table grouped by color, you would add a bookmark based on the group expression to the group header.</span></span> <span data-ttu-id="bb991-109">A continuación, agregaría una tabla con un único cuadro de texto al principio del informe que mostrase los valores de color y establecería el vínculo de marcador en dicho cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bb991-109">Then you would add a table with a single text box at the beginning of the report that displayed the color values, and set the bookmark link on that text box.</span></span> <span data-ttu-id="bb991-110">Al hacer clic en el color, el informe saltará a la página que muestra la fila del encabezado de grupo para ese color.</span><span class="sxs-lookup"><span data-stu-id="bb991-110">When you click the color, the report jumps to the page that displays the group header row for that color.</span></span>  
  
 <span data-ttu-id="bb991-111">Puede agregar un marcador a cualquier elemento de informe y un vínculo de marcador a cualquier elemento que tenga una propiedad **Action** , como por ejemplo, un cuadro de texto, una imagen o una serie calculada en un gráfico.</span><span class="sxs-lookup"><span data-stu-id="bb991-111">You can add a bookmark to any report item and add a bookmark link to any item that has an **Action** property, for example, a text box, an image, or a calculated series in a chart.</span></span> <span data-ttu-id="bb991-112">Para más información vea [Cuadro de diálogo Propiedades de acción &#40;Generador de informes y SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bb991-112">For more information, see the [Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-bookmark"></a><span data-ttu-id="bb991-113">Para agregar un marcador</span><span class="sxs-lookup"><span data-stu-id="bb991-113">To add a bookmark</span></span>  
  
1.  <span data-ttu-id="bb991-114">En la vista de diseño de informe, seleccione el cuadro de texto, la imagen, el gráfico o el elemento de informe al que desea agregar un marcador.</span><span class="sxs-lookup"><span data-stu-id="bb991-114">In report design view, select the text box, image, chart, or other report item to which you want to add a bookmark.</span></span> <span data-ttu-id="bb991-115">Las propiedades del elemento seleccionado aparecen en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="bb991-115">The properties for the selected item appear in the Properties pane.</span></span>  
  
2.  <span data-ttu-id="bb991-116">En el cuadro de texto situado junto a **Marcador**, escriba una cadena que será la etiqueta de este marcador.</span><span class="sxs-lookup"><span data-stu-id="bb991-116">In the text box next to **Bookmark**, type a string that is the label for this bookmark.</span></span> <span data-ttu-id="bb991-117">Por ejemplo, podría escribir **BikePhoto** como marcador para una imagen en el informe.</span><span class="sxs-lookup"><span data-stu-id="bb991-117">For example, you could type **BikePhoto** as the bookmark for an image in your report.</span></span> <span data-ttu-id="bb991-118">También puede hacer clic en el botón Expresión (**fx**) para abrir el cuadro de diálogo **Expresión** y especificar una expresión que dé como resultado una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bb991-118">Alternatively, click the Expression (**fx**) button to open the **Expression** dialog box to specify an expression that evaluates to a label.</span></span> <span data-ttu-id="bb991-119">En el caso de un grupo, la expresión usada debería ser la expresión de grupo.</span><span class="sxs-lookup"><span data-stu-id="bb991-119">For a group, the expression you type should be the group expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb991-120">El marcador puede ser cualquier cadena, pero debe ser única en el informe.</span><span class="sxs-lookup"><span data-stu-id="bb991-120">The bookmark can be any string, but it must be unique in the report.</span></span> <span data-ttu-id="bb991-121">Si el marcador no es único, el vínculo a ese marcador encontrará el primer marcador que coincida.</span><span class="sxs-lookup"><span data-stu-id="bb991-121">If the bookmark is not unique, a link to the bookmark finds the first matching bookmark.</span></span>  
  
### <a name="to-add-a-bookmark-link"></a><span data-ttu-id="bb991-122">Para agregar un vínculo de marcador</span><span class="sxs-lookup"><span data-stu-id="bb991-122">To add a bookmark link</span></span>  
  
1.  <span data-ttu-id="bb991-123">En la vista Diseño, haga clic con el botón derecho en el gráfico, la imagen o el cuadro de texto donde quiere agregar el vínculo y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bb991-123">In Design view, right-click the text box, image, chart, to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="bb991-124">En el cuadro de diálogo **Propiedades** que aparece para ese elemento de informe, haga clic en **Action**.</span><span class="sxs-lookup"><span data-stu-id="bb991-124">In The **Properties** dialog box for that report item, click **Action**.</span></span>  
  
3.  <span data-ttu-id="bb991-125">Seleccione **Ir a marcador**.</span><span class="sxs-lookup"><span data-stu-id="bb991-125">Select **Go to bookmark**.</span></span> <span data-ttu-id="bb991-126">Aparece una sección adicional en el cuadro de diálogo para esta opción.</span><span class="sxs-lookup"><span data-stu-id="bb991-126">An additional section appears in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="bb991-127">En el cuadro **Seleccionar marcador** , escriba o seleccione un marcador o una expresión que se evalúe como un marcador.</span><span class="sxs-lookup"><span data-stu-id="bb991-127">In the **Select bookmark** box, type or select a bookmark or an expression that evaluates to a bookmark.</span></span> <span data-ttu-id="bb991-128">Con el ejemplo anterior, escriba **BikePhoto** para crear un vínculo a la imagen en el informe.</span><span class="sxs-lookup"><span data-stu-id="bb991-128">Using the previous example, type **BikePhoto** to create a link to the image in your report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="bb991-129">(Opcional) El texto no recibe automáticamente el formato de vínculo.</span><span class="sxs-lookup"><span data-stu-id="bb991-129">(Optional) The text is not automatically formatted like a link.</span></span> <span data-ttu-id="bb991-130">En el caso del texto, resulta útil cambiar el color y el efecto del texto para indicar que el texto es un vínculo.</span><span class="sxs-lookup"><span data-stu-id="bb991-130">For text, it is helpful to change the color and effect of the text to indicate that the text is a link.</span></span> <span data-ttu-id="bb991-131">Por ejemplo,puede cambiar el color a azul y el efecto a subrayado en la sección **Fuente** de la pestaña Inicio de la cinta.</span><span class="sxs-lookup"><span data-stu-id="bb991-131">For example, change the color to blue and the effect to underline in the **Font** section in the Home tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="bb991-132">Para probar el vínculo, haga clic en **Ejecutar** para obtener la vista previa del informe y, a continuación, haga clic en el elemento de informe en el que ha establecido este vínculo.</span><span class="sxs-lookup"><span data-stu-id="bb991-132">To test the link, click **Run** to preview the report, and then click the report item that you set this link on..</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb991-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb991-133">See Also</span></span>  
 <span data-ttu-id="bb991-134">[Ordenación interactiva, mapas de documento y vínculos &#40;Generador de informes y SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb991-134">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bb991-135">[Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb991-135">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bb991-136">Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bb991-136">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
