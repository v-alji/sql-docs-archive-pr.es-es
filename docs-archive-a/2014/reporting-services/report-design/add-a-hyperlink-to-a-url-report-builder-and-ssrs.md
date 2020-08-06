---
title: Agregar un hipervínculo a una dirección URL (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d3392c0b-7b62-4d27-bc04-2bd0c5487d08
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d3db3fc75feca1393e73e698f44db633f09e8dc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745051"
---
# <a name="add-a-hyperlink-to-a-url-report-builder-and-ssrs"></a><span data-ttu-id="5f386-102">Agregar un hipervínculo a una dirección URL (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="5f386-102">Add a Hyperlink to a URL (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5f386-103">Puede agregar un hipervínculo a un elemento de informe si desea que los usuarios puedan hacer clic en un vínculo de un informe y abrir el explorador para la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="5f386-103">You can add a hyperlink to a report item when you want your users to be able to click a link in a report and open a browser to the URL that you specify.</span></span> <span data-ttu-id="5f386-104">Los hipervínculos pueden ser una dirección URL estática o una expresión que se evalúe como una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5f386-104">A hyperlink can be a static URL or an expression that evaluates to a URL.</span></span> <span data-ttu-id="5f386-105">Si un campo de una base de datos contiene direcciones URL, una expresión pueden contener dicho campo, lo que dará lugar a una lista dinámica de hipervínculos en el informe.</span><span class="sxs-lookup"><span data-stu-id="5f386-105">If you have a field in a database that contains URLs, the expression can contain that field, resulting in a dynamic list of hyperlinks in the report.</span></span> <span data-ttu-id="5f386-106">Puede agregar hipervínculos a cuadros de texto, imágenes, gráficos y medidores.</span><span class="sxs-lookup"><span data-stu-id="5f386-106">You can add hyperlinks to text boxes, images, charts, and gauges.</span></span> <span data-ttu-id="5f386-107">Debe asegurarse de que los usuarios tienen acceso a la dirección URL proporcionada.</span><span class="sxs-lookup"><span data-stu-id="5f386-107">You must ensure that the user has access to the URL that you provide.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="5f386-108">También puede especificar direcciones URL a los informes situados en cualquier servidor de informes para el que usted y sus usuarios tengan permiso para ver mediante solicitudes URL.</span><span class="sxs-lookup"><span data-stu-id="5f386-108">You can also specify URLs to reports on any report server that you and your users have permission to view using URL requests to the report server.</span></span> <span data-ttu-id="5f386-109">Por ejemplo, puede especificar un informe y ocultar el mapa del documento para los usuarios cuando vean el informe por primera vez.</span><span class="sxs-lookup"><span data-stu-id="5f386-109">For example, you can specify a report and hide the document map for the user when they first view the report.</span></span> <span data-ttu-id="5f386-110">Para más información, vea [Acceso URL &#40;SSRS&#41;](../url-access-ssrs.md) en la [documentación de Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f386-110">For more information, see [URL Access &#40;SSRS&#41;](../url-access-ssrs.md) in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="5f386-111">Puede agregar un hipervínculo a una dirección URL a cualquier elemento que tenga una propiedad **Acción** , como por ejemplo, un cuadro de texto, una imagen o una serie calculada en un gráfico.</span><span class="sxs-lookup"><span data-stu-id="5f386-111">You can add a hyperlink to a URL to any item that has an **Action** property, for example, a text box, an image, or a calculated series in a chart.</span></span> <span data-ttu-id="5f386-112">Cuando el usuario haga clic en el elemento de informe, tendrá lugar la acción que haya definido.</span><span class="sxs-lookup"><span data-stu-id="5f386-112">When the user clicks that report item, the action that you define takes place.</span></span> <span data-ttu-id="5f386-113">Para más información, vea [Cuadro de diálogo Propiedades de acción &#40;Generador de informes y SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) y [Especificar las rutas de acceso a los elementos externos &#40;Generador de informes y SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5f386-113">For more information, see the [Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) and [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="5f386-114">Para más información, vea [Tutorial: Dar formato a texto &#40;Generador de informes&#41;](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="5f386-114">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f386-115">Los vínculos que se enlazan a los campos de conjunto de datos pueden ser vulnerables a la alteración con fines malintencionados.</span><span class="sxs-lookup"><span data-stu-id="5f386-115">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="5f386-116">Para más información, vea [Proteger informes y recursos](../security/secure-reports-and-resources.md) en los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Libros en pantalla](https://go.microsoft.com/fwlink/?LinkId=154888) en msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5f386-116">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
### <a name="to-add-a-hyperlink"></a><span data-ttu-id="5f386-117">Para agregar un hipervínculo</span><span class="sxs-lookup"><span data-stu-id="5f386-117">To add a hyperlink</span></span>  
  
1.  <span data-ttu-id="5f386-118">En la vista de diseño de informes, haga clic con el botón derecho en el gráfico, la imagen o el cuadro de texto al que quiere agregar el vínculo y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5f386-118">In report design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="5f386-119">En el cuadro de diálogo Propiedades, haga clic en **Acción**.</span><span class="sxs-lookup"><span data-stu-id="5f386-119">In the Properties dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="5f386-120">Seleccione **Ir a dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="5f386-120">Select **Go to URL**.</span></span> <span data-ttu-id="5f386-121">Aparece una sección adicional en el cuadro de diálogo para esta opción.</span><span class="sxs-lookup"><span data-stu-id="5f386-121">An additional section appears in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="5f386-122">En **Seleccionar dirección URL**, escriba o seleccione una dirección URL o una expresión que se evalúe como una dirección URL, o haga clic en la flecha de lista desplegable y haga clic en el nombre de un campo que contenga una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5f386-122">In **Select URL**, type or select a URL or an expression that evaluates to a URL, or click the drop-down arrow and click the name of a field that contains a URL.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="5f386-123">(Opcional) El texto no recibe automáticamente el formato de vínculo.</span><span class="sxs-lookup"><span data-stu-id="5f386-123">(Optional) The text is not automatically formatted as a link.</span></span> <span data-ttu-id="5f386-124">En el caso del texto, resulta útil cambiar el color y el efecto del texto para indicar que el texto es un vínculo.</span><span class="sxs-lookup"><span data-stu-id="5f386-124">For text, it is helpful to change the color and effect of the text to indicate that the text is a link.</span></span> <span data-ttu-id="5f386-125">Por ejemplo,puede cambiar el color a azul y el efecto a subrayado en la sección **Fuente** de la pestaña Inicio de la cinta.</span><span class="sxs-lookup"><span data-stu-id="5f386-125">For example, change the color to blue and the effect to underline in the **Font** section in the Home tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="5f386-126">Para probar el vínculo, haga clic en **Ejecutar** para obtener la vista previa del informe y, a continuación, haga clic en el elemento de informe en el que ha establecido este vínculo.</span><span class="sxs-lookup"><span data-stu-id="5f386-126">To test the link, click **Run** to preview the report, and then click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f386-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f386-127">See Also</span></span>  
 <span data-ttu-id="5f386-128">[Ordenación interactiva, mapas de documento y vínculos &#40;Generador de informes y SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5f386-128">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5f386-129">Crear un mapa del documento &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5f386-129">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
  
  
