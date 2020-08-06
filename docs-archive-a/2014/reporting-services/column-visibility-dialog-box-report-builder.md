---
title: Cuadro de diálogo visibilidad de columna (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10127"
ms.assetid: 0c030cab-6087-45a5-99f0-c7bd693f20a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4c775734a4dbba2120a2af86e35a3872f5fff718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745069"
---
# <a name="column-visibility-dialog-box-report-builder"></a><span data-ttu-id="ac787-102">Cuadro de diálogo Visibilidad de columna (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="ac787-102">Column Visibility Dialog Box (Report Builder)</span></span>
  <span data-ttu-id="ac787-103">Use el cuadro de diálogo **Visibilidad de columna** para mostrar u ocultar la columna seleccionada cuando se ejecuta el informe por primera vez o para usar otro elemento de informe para activar o desactivar la visibilidad de la columna.</span><span class="sxs-lookup"><span data-stu-id="ac787-103">Use the **Column Visibility** dialog box to show or hide the selected column when the report is first run or to use another report item to toggle the visibility of the column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac787-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="ac787-104">Options</span></span>  
 <span data-ttu-id="ac787-105">**Cuando se ejecute inicialmente el informe**</span><span class="sxs-lookup"><span data-stu-id="ac787-105">**When the report is initially run**</span></span>  
 <span data-ttu-id="ac787-106">Seleccione una opción para indicar cómo se muestra el elemento de informe inicialmente en el informe.</span><span class="sxs-lookup"><span data-stu-id="ac787-106">Select an option to indicate how the report item is initially displayed in the report.</span></span>  
  
 <span data-ttu-id="ac787-107">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="ac787-107">**Show**</span></span>  
 <span data-ttu-id="ac787-108">Elija esta opción para mostrar la columna.</span><span class="sxs-lookup"><span data-stu-id="ac787-108">Choose this option to show the column.</span></span>  
  
 <span data-ttu-id="ac787-109">**Ocultar**</span><span class="sxs-lookup"><span data-stu-id="ac787-109">**Hide**</span></span>  
 <span data-ttu-id="ac787-110">Elija esta opción para ocultar la columna.</span><span class="sxs-lookup"><span data-stu-id="ac787-110">Choose this option to hide the Column.</span></span>  
  
 <span data-ttu-id="ac787-111">**Mostrar u ocultar en función de una expresión**</span><span class="sxs-lookup"><span data-stu-id="ac787-111">**Show or hide based on an expression**</span></span>  
 <span data-ttu-id="ac787-112">Elija esta opción para modificar la visibilidad inicial por medio de una expresión.</span><span class="sxs-lookup"><span data-stu-id="ac787-112">Choose this option to vary the initial visibility using an expression.</span></span>  
  
 <span data-ttu-id="ac787-113">Escriba una expresión que se evalúe como un valor `Boolean``True` para ocultar el elemento y `False` para mostrarlo.</span><span class="sxs-lookup"><span data-stu-id="ac787-113">Type an expression that evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span> <span data-ttu-id="ac787-114">Haga clic en el botón Expresión (*fx*) para editar la expresión.</span><span class="sxs-lookup"><span data-stu-id="ac787-114">Click the Expression (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="ac787-115">**La visualización se puede activar o desactivar para este elemento de informe**</span><span class="sxs-lookup"><span data-stu-id="ac787-115">**Display can be toggled by this report item**</span></span>  
 <span data-ttu-id="ac787-116">Elija esta opción para mostrar una imagen de alternancia que permita que el usuario muestre u oculte esta columna en un visor de informes HTML.</span><span class="sxs-lookup"><span data-stu-id="ac787-116">Choose this option to display a toggle image that enables the user to show or hide this column in an HTML report viewer.</span></span>  
  
 <span data-ttu-id="ac787-117">Escriba o seleccione el nombre de un cuadro de texto del informe en el que aparezca una imagen de alternancia, por ejemplo, Textbox1.</span><span class="sxs-lookup"><span data-stu-id="ac787-117">Type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span> <span data-ttu-id="ac787-118">El cuadro de texto que elija debe estar en el ámbito actual o en el ámbito contenedor de este elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="ac787-118">The text box that you choose must be in the current or containing scope for this report item.</span></span> <span data-ttu-id="ac787-119">Por ejemplo, para alternar la visibilidad de las filas asociadas a un grupo secundario, seleccione un cuadro de texto de una fila asociada al grupo primario.</span><span class="sxs-lookup"><span data-stu-id="ac787-119">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span> <span data-ttu-id="ac787-120">Para alternar la visibilidad de un gráfico, seleccione un cuadro de texto que esté en el mismo ámbito contenedor que el gráfico; por ejemplo, un rectángulo o el cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="ac787-120">To toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac787-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac787-121">See Also</span></span>  
 <span data-ttu-id="ac787-122">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ac787-122">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ac787-123">[Agregar una acción de expandir o contraer a un elemento &#40;Generador de informes y SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ac787-123">[Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ac787-124">[Imágenes &#40;Generador de informes y SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ac787-124">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ac787-125">[Generador de informes ayuda para cuadros de diálogo, paneles y asistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="ac787-125">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="ac787-126">Cuadro de diálogo de Propiedades de la imagen, General &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ac787-126">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
