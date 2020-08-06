---
title: Dar formato al texto en un cuadro de texto (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df0794b5-96b0-4034-bd17-1be7f31e29db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 522bc420f77b2e5e9d2163c28d3d688b7c47883c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671380"
---
# <a name="format-text-in-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="edea2-102">Dar formato al texto en un cuadro de texto (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="edea2-102">Format Text in a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="edea2-103">Puede dar formato por separado a cualquier parte del texto de un cuadro de texto, y usar texto de marcador de posición y texto estático en un mismo cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="edea2-103">You can format any part of the text within a text box independently, and mix placeholder text and static text in one text box.</span></span> <span data-ttu-id="edea2-104">Esta capacidad de mezclar formatos y agregar texto de marcador de posición permite crear combinaciones de correspondencia o plantillas para el texto del informe.</span><span class="sxs-lookup"><span data-stu-id="edea2-104">This ability to mix formats and add placeholder text enables you to create mail merges or templates for text in your report.</span></span> <span data-ttu-id="edea2-105">Podrá definir y dar formato a cualquier expresión de forma independiente mediante un marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="edea2-105">Any expression can be defined and formatted separately using a placeholder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-combine-multiple-formats-in-a-text-box"></a><span data-ttu-id="edea2-106">Para combinar varios formatos en un cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="edea2-106">To combine multiple formats in a text box</span></span>  
  
1.  <span data-ttu-id="edea2-107">En la pestaña **Insertar** , haga clic en **Cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="edea2-107">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="edea2-108">Haga clic en la superficie de diseño y, a continuación, arrastre para crear un cuadro que tenga el tamaño que desee.</span><span class="sxs-lookup"><span data-stu-id="edea2-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
2.  <span data-ttu-id="edea2-109">Dentro del cuadro de texto, seleccione el texto al que desea dar formato.</span><span class="sxs-lookup"><span data-stu-id="edea2-109">Inside the text box, select the text you want to format.</span></span>  
  
3.  <span data-ttu-id="edea2-110">Haga clic con el botón derecho en el texto y, después, haga clic en **Propiedades de texto**.</span><span class="sxs-lookup"><span data-stu-id="edea2-110">Right-click the selected text, and click **Text Properties**.</span></span>  
  
4.  <span data-ttu-id="edea2-111">Establezca las opciones de formato.</span><span class="sxs-lookup"><span data-stu-id="edea2-111">Set formatting options.</span></span> <span data-ttu-id="edea2-112">Por ejemplo, en la pestaña **General** :</span><span class="sxs-lookup"><span data-stu-id="edea2-112">For example, on the **General** tab:</span></span>  
  
    -   <span data-ttu-id="edea2-113">**Información sobre herramientas** Escriba un texto o una expresión que se evalúe como una información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="edea2-113">**Tooltip** Type text or an expression that evaluates to a ToolTip.</span></span> <span data-ttu-id="edea2-114">La información sobre herramientas aparece cuando el usuario pausa el puntero sobre el elemento en un informe.</span><span class="sxs-lookup"><span data-stu-id="edea2-114">The ToolTip appears when the user pauses the pointer over the item in a report</span></span>  
  
    -   <span data-ttu-id="edea2-115">**Tipo de marcado** Seleccione una opción para indicar cómo se representará el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="edea2-115">**Markup type** Select an option to indicate how the selected text will be rendered:</span></span>  
  
         <span data-ttu-id="edea2-116">**Texto sin formato** : muestra el texto seleccionado como texto simple.</span><span class="sxs-lookup"><span data-stu-id="edea2-116">**Plain Text** Display the selected text as simple text.</span></span> <span data-ttu-id="edea2-117">El código HTML se tratará como texto literal.</span><span class="sxs-lookup"><span data-stu-id="edea2-117">HTML will be treated as literal text.</span></span>  
  
         <span data-ttu-id="edea2-118">**HTML**  : muestra el texto seleccionado como HTML.</span><span class="sxs-lookup"><span data-stu-id="edea2-118">**HTML**  Display the selected text as HTML.</span></span> <span data-ttu-id="edea2-119">Si el valor de expresión del marcador de posición contiene etiquetas HTML válidas, estas etiquetas se representarán como HTML.</span><span class="sxs-lookup"><span data-stu-id="edea2-119">If the expression value of the placeholder contains valid HTML tags, these tags will be rendered as HTML.</span></span> <span data-ttu-id="edea2-120">Para más información, vea [Importar HTML en un informe &#40;Generador de informes y SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="edea2-120">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="edea2-121">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="edea2-121">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="edea2-122">Repita los pasos del 2 al 5 para el texto restante al que desea dar formato.</span><span class="sxs-lookup"><span data-stu-id="edea2-122">Repeat steps 2 through 5 for the remaining text you want to format.</span></span>  
  
### <a name="to-format-text-and-placeholders-differently-in-the-same-text-box"></a><span data-ttu-id="edea2-123">Para dar formato de manera diferente al texto y a los marcadores de posición en el mismo cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="edea2-123">To format text and placeholders differently in the same text box</span></span>  
  
1.  <span data-ttu-id="edea2-124">En la pestaña **Insertar** , haga clic en **Lista**.</span><span class="sxs-lookup"><span data-stu-id="edea2-124">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="edea2-125">Haga clic en la superficie de diseño y, a continuación, arrastre para crear un cuadro que tenga el tamaño que desee.</span><span class="sxs-lookup"><span data-stu-id="edea2-125">Click the design surface, and then drag to create a box that is the size you want.</span></span> <span data-ttu-id="edea2-126">Se abre el cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="edea2-126">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="edea2-127">En el informe, podrá utilizar un conjunto de datos compartido o un conjunto de datos incrustado.</span><span class="sxs-lookup"><span data-stu-id="edea2-127">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="edea2-128">Para más información, haga clic en [Propiedades del conjunto de datos (cuadro de diálogo), Consulta &#40;Generador de informes&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) o [Propiedades del conjunto de datos (cuadro de diálogo), Consulta](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="edea2-128">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="edea2-129">En la pestaña **Insertar** , haga clic en **Cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="edea2-129">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="edea2-130">Haga clic en la lista y, a continuación, arrastre para crear un cuadro que tenga el tamaño que desee.</span><span class="sxs-lookup"><span data-stu-id="edea2-130">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="edea2-131">Escriba una etiqueta en el cuadro de texto, por ejemplo, **Mi campo**:.</span><span class="sxs-lookup"><span data-stu-id="edea2-131">Type a label in the text box - for example, **My Field**:.</span></span>  
  
4.  <span data-ttu-id="edea2-132">Arrastre un campo desde el conjunto de datos hasta el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="edea2-132">Drag a field from your dataset into the text box.</span></span> <span data-ttu-id="edea2-133">Se crea un marcador de posición para el campo.</span><span class="sxs-lookup"><span data-stu-id="edea2-133">A placeholder is created for your field.</span></span>  
  
5.  <span data-ttu-id="edea2-134">Para el formato básico, seleccione el texto del marcador de posición y, a continuación, haga clic en una de las opciones de formato del grupo **Fuente** de la pestaña **Inicio** . Por ejemplo, haga clic en el botón **Negrita**.</span><span class="sxs-lookup"><span data-stu-id="edea2-134">For basic formatting, select the placeholder text and then click one of the formatting options in the **Font** group on the **Home** tab. For example, click the **Bold** button.</span></span>  
  
     <span data-ttu-id="edea2-135">Para obtener más opciones de formato, haga clic con el botón derecho en el texto del marcador de posición y, después, haga clic en **Propiedades del marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="edea2-135">For more formatting options, right-click the placeholder text, and then click **Placeholder Properties**.</span></span>  
  
6.  <span data-ttu-id="edea2-136">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="edea2-136">Click **OK**.</span></span> <span data-ttu-id="edea2-137">En la vista de diseño de informe, el cuadro de texto debe contener "**Mi campo**: [*FieldName*]", donde *FieldName* es el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="edea2-137">In report design view, the text box should contain "**My Field**: [*FieldName*]", where *FieldName* is the name of your field.</span></span>  
  
7.  <span data-ttu-id="edea2-138">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="edea2-138">Click **Run**.</span></span>  
  
 <span data-ttu-id="edea2-139">La lista se repite una vez por cada valor del campo y el marcador de posición *FieldName* se reemplaza cada vez por el valor de ese campo en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="edea2-139">The list repeats one time for every value in the field, and the *FieldName* placeholder is replaced each time by the value of that field in the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edea2-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edea2-140">See Also</span></span>  
 <span data-ttu-id="edea2-141">[Cuadros de texto &#40;Generador de informes y SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="edea2-141">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="edea2-142">[Aplicar formato a texto y a marcadores de posición &#40;Generador de informes y SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="edea2-142">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="edea2-143">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="edea2-143">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="edea2-144">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="edea2-144">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="edea2-145">[Agregar HTML a un informe &#40;Generador de informes y SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="edea2-145">[Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="edea2-146">[Enumera &#40;Generador de informes y SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="edea2-146">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="edea2-147">[Aplicar formato a números y fechas &#40;Generador de informes y SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="edea2-147">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="edea2-148">Cuadro de diálogo Propiedades del marcador de posición, General &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="edea2-148">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
