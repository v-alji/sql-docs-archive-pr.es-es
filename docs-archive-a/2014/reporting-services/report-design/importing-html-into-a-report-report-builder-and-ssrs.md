---
title: Importar HTML en un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dd0410ea-8839-4e8c-9944-8cdfe5465591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f978e67c67556184012db6b809e4f5754f2374c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745045"
---
# <a name="importing-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="e0822-102">Importar HTML en un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="e0822-102">Importing HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e0822-103">Se puede usar un cuadro de texto para insertar en un informe texto con formato HTML recuperado de un campo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e0822-103">You can use a text box to insert HTML-formatted text that you have retrieved from a field in your dataset into a report.</span></span> <span data-ttu-id="e0822-104">El texto puede proceder de cualquier expresión simple o compleja que se evalúe como HTML con un formato correcto.</span><span class="sxs-lookup"><span data-stu-id="e0822-104">The text can come from any simple or complex expression that evaluates to correctly formatted HTML.</span></span> <span data-ttu-id="e0822-105">El texto con formato se puede representar en todos los formatos de salida compatibles, incluso PDF.</span><span class="sxs-lookup"><span data-stu-id="e0822-105">Formatted text can be rendered to all supported output formats, including PDF.</span></span>  
  
 <span data-ttu-id="e0822-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span><span class="sxs-lookup"><span data-stu-id="e0822-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span></span>  
  
 <span data-ttu-id="e0822-107">Esta ilustración se muestra texto con formato HTML en la vista de diseño de informe y el mismo texto como se representa cuando se ejecuta el informe.</span><span class="sxs-lookup"><span data-stu-id="e0822-107">This illustration shows text with HTML formatting in report design view, and the same text as it is rendered when the report is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0822-108">Cuando se importa texto que contiene marcado HTML, el cuadro de texto siempre debe analizar los datos en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="e0822-108">When you import text that contains HTML markup, the data must always be parsed by the text box first.</span></span> <span data-ttu-id="e0822-109">Dado que solo se admite un subconjunto de etiquetas HTML, el HTML que se muestra en el informe representado puede diferir del HTML original.</span><span class="sxs-lookup"><span data-stu-id="e0822-109">Because only a subset of HTML tags is supported, the HTML that is shown in the rendered report may differ from your original HTML.</span></span>  
  
 <span data-ttu-id="e0822-110">Para más información, vea [Tutorial: Dar formato a texto &#40;Generador de informes&#41;](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e0822-110">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="supported-html-tags"></a><span data-ttu-id="e0822-111">Etiquetas HTML compatibles</span><span class="sxs-lookup"><span data-stu-id="e0822-111">Supported HTML Tags</span></span>  
 <span data-ttu-id="e0822-112">La lista siguiente es una lista completa de las etiquetas que se representarán como HTML cuando se definan como texto de marcador de posición:</span><span class="sxs-lookup"><span data-stu-id="e0822-112">The following is a complete list of tags that will render as HTML when defined as placeholder text:</span></span>  
  
-   <span data-ttu-id="e0822-113">Encabezado, estilo y elementos de bloque: \<H{n}> , \<DIV> , \<SPAN> , \<P> ,\<LI></span><span class="sxs-lookup"><span data-stu-id="e0822-113">Header, style and block elements: \<H{n}>, \<DIV>, \<SPAN>,\<P>, \<LI></span></span>  
  
 <span data-ttu-id="e0822-114">Cualquier otra etiqueta de marcado HTML se omitirá durante el procesamiento del informe.</span><span class="sxs-lookup"><span data-stu-id="e0822-114">Any other HTML markup tags will be ignored during report processing.</span></span> <span data-ttu-id="e0822-115">Si el HTML representado por la expresión en el texto del marcador de posición no está bien formado, el marcador de posición se representa como texto simple.</span><span class="sxs-lookup"><span data-stu-id="e0822-115">If the HTML represented by the expression in the placeholder text is not well formed, the placeholder is rendered as plain text.</span></span> <span data-ttu-id="e0822-116">Todas las etiquetas HTML distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e0822-116">All HTML tags are case-insensitive.</span></span>  
  
 <span data-ttu-id="e0822-117">Si el texto del cuadro de texto contiene solo un bloque de texto, cualquier HTML del marcador de posición que defina elementos de bloque se representará correctamente.</span><span class="sxs-lookup"><span data-stu-id="e0822-117">If the text in your text box contains only one block of text, any HTML in the placeholder that defines block elements will render correctly.</span></span> <span data-ttu-id="e0822-118">Sin embargo, si el cuadro de texto tiene varios bloques de texto, se omitirán las etiquetas HTML y los bloques de texto definirán la estructura del texto.</span><span class="sxs-lookup"><span data-stu-id="e0822-118">However, if the text box has multiple blocks of text, the HTML tags are ignored and the structure of the text is defined by the blocks of text.</span></span>  
  
 <span data-ttu-id="e0822-119">Si se definen varias etiquetas para el texto, y [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] detecta un conflicto entre las restricciones del HTML y del informe existente, solo se considerará HTML la etiqueta HTML más interna.</span><span class="sxs-lookup"><span data-stu-id="e0822-119">If more than one tag is defined for text, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] detects a conflict between the HTML and existing report constraints, only the innermost HTML tag will be treated as HTML.</span></span>  
  
 <span data-ttu-id="e0822-120">Cuando se utilizan las etiquetas de gestión de listas, la fuente y el estilo de todos los prefijos de números y viñetas se fija en Arial negro.</span><span class="sxs-lookup"><span data-stu-id="e0822-120">When using the list handling tags, the font and style of all bullets and number prefixes will be fixed to Arial black.</span></span>  
  
 <span data-ttu-id="e0822-121">Para más información, vea [Agregar HTML a un informe &#40;Generador de informes y SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e0822-121">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="limitations-of-cascading-style-sheet-attributes"></a><span data-ttu-id="e0822-122">Limitaciones de los atributos de las hojas de estilos en cascada</span><span class="sxs-lookup"><span data-stu-id="e0822-122">Limitations of Cascading Style Sheet Attributes</span></span>  
 <span data-ttu-id="e0822-123">Cuando se usan atributos de hoja de estilos en cascada (CSS), solo se define un conjunto básico de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="e0822-123">When using cascading style sheet (CSS) attributes, only a basic set of tags are defined.</span></span> <span data-ttu-id="e0822-124">La lista siguiente es una lista de los atributos admitidos:</span><span class="sxs-lookup"><span data-stu-id="e0822-124">The following is a list of attributes that are supported:</span></span>  
  
-   <span data-ttu-id="e0822-125">text-align, text-indent</span><span class="sxs-lookup"><span data-stu-id="e0822-125">text-align, text-indent</span></span>  
  
-   <span data-ttu-id="e0822-126">font-family</span><span class="sxs-lookup"><span data-stu-id="e0822-126">font-family</span></span>  
  
-   <span data-ttu-id="e0822-127">tamaño de fuente</span><span class="sxs-lookup"><span data-stu-id="e0822-127">font-size</span></span>  
  
    -   <span data-ttu-id="e0822-128">Solo se admiten valores válidos de tamaño RDL, en unidades de longitud CSS absolutas.</span><span class="sxs-lookup"><span data-stu-id="e0822-128">Only valid RDL size values, in absolute CSS length units are supported.</span></span> <span data-ttu-id="e0822-129">Las unidades admitidas son: pda, cm, mm, pt y pc.</span><span class="sxs-lookup"><span data-stu-id="e0822-129">Supported units are: in, cm, mm, pt, pc.</span></span>  
  
    -   <span data-ttu-id="e0822-130">Las unidades de longitud de CSS relativas se pasan por algo y no se admiten.</span><span class="sxs-lookup"><span data-stu-id="e0822-130">Relative CSS length units are ignored and not supported.</span></span> <span data-ttu-id="e0822-131">Las unidades no admitidas son em, ex, px,%,rem.</span><span class="sxs-lookup"><span data-stu-id="e0822-131">Unsupported units include em, ex, px,%,rem.</span></span>  
  
-   <span data-ttu-id="e0822-132">color</span><span class="sxs-lookup"><span data-stu-id="e0822-132">color</span></span>  
  
-   <span data-ttu-id="e0822-133">padding, padding-bottom, padding-top, padding-right, padding-left</span><span class="sxs-lookup"><span data-stu-id="e0822-133">padding, padding-bottom, padding-top, padding-right, padding-left</span></span>  
  
-   <span data-ttu-id="e0822-134">font-weight</span><span class="sxs-lookup"><span data-stu-id="e0822-134">font-weight</span></span>  
  
 <span data-ttu-id="e0822-135">Estas son algunas consideraciones sobre el uso de CSS:</span><span class="sxs-lookup"><span data-stu-id="e0822-135">Here are some considerations for using CSS:</span></span>  
  
-   <span data-ttu-id="e0822-136">Los valores de CSS incorrectos se omiten de la misma manera que se omite el HTML incorrecto.</span><span class="sxs-lookup"><span data-stu-id="e0822-136">Malformed CSS values are ignored in the same way as malformed HTML.</span></span>  
  
-   <span data-ttu-id="e0822-137">Cuando en una misma etiqueta hay un atributo y atributos de estilo CSS, la propiedad de CSS tiene una prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="e0822-137">When both attribute and CSS style attributes exist in the same tag, the CSS property has a higher precedence.</span></span> <span data-ttu-id="e0822-138">Por ejemplo, si el texto es **\<p style="text-align: right" align="left">** , solo se aplicará el atributo Text-align y el texto se alineará a la derecha.</span><span class="sxs-lookup"><span data-stu-id="e0822-138">For example, if your text is **\<p style="text-align: right" align="left">**, only the text-align attribute will be applied and the text will be right-aligned.</span></span>  
  
-   <span data-ttu-id="e0822-139">Para los atributos y los estilos CSS, si una propiedad se especifica más de una vez, solo se aplica la última instancia de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e0822-139">For attributes and CSS styles, if a property is specified more than once, only the last instance of the property is applied.</span></span> <span data-ttu-id="e0822-140">Por ejemplo, si el texto es **\<p align="left" align="right">** , el texto se alinea a la derecha.</span><span class="sxs-lookup"><span data-stu-id="e0822-140">For example, if your text is **\<p align="left" align="right">**, the text will be right-aligned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0822-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0822-141">See Also</span></span>  
 [<span data-ttu-id="e0822-142">Representar en HTML &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e0822-142">Rendering to HTML &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/rendering-to-html-report-builder-and-ssrs.md)  
  
  
