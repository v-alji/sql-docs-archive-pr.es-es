---
title: Ocultar un elemento (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.visibility.f1
- "10503"
ms.assetid: 9d78f8de-959b-456f-8947-687fa6e2ba91
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56e834204698369687528c622cf6167a492766f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670831"
---
# <a name="hide-an-item-report-builder-and-ssrs"></a><span data-ttu-id="37b20-102">Ocultar un elemento (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="37b20-102">Hide an Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="37b20-103">Establezca la visibilidad de un elemento de informe cuando desee ocultar condicionalmente un elemento basándose en un parámetro de informe o en alguna otra expresión que especifique.</span><span class="sxs-lookup"><span data-stu-id="37b20-103">Set the visibility of a report item when you want to conditionally hide an item based on a report parameter or some other expression that you specify.</span></span>

 <span data-ttu-id="37b20-104">También puede diseñar un informe que permita al usuario cambiar la visibilidad de los elementos de informe haciendo clic en los cuadros de texto del informe, por ejemplo, para un informe detallado.</span><span class="sxs-lookup"><span data-stu-id="37b20-104">You can also design a report to allow the user to toggle the visibility of report items based on clicking text boxes in the report, for example, for a drilldown report.</span></span> <span data-ttu-id="37b20-105">Para obtener más información, vea [Agregar una acción de expandir y contraer a un elemento &#40;Generador de informes y SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="37b20-105">For more information, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="37b20-106">Los procedimientos siguientes describen cómo mostrar u ocultar un elemento de informe en un informe representado en una constante o en una expresión.</span><span class="sxs-lookup"><span data-stu-id="37b20-106">The following procedures describe how to show or hide a report item in a rendered report based on a constant or an expression.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-hide-a-report-item"></a><span data-ttu-id="37b20-107">Ocultar un elemento de informe</span><span class="sxs-lookup"><span data-stu-id="37b20-107">To hide a report item</span></span>

1.  <span data-ttu-id="37b20-108">En la vista de diseño de informe, haga clic con el botón derecho en el elemento de informe y, después, abra la página **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="37b20-108">In report design view, right-click the report item and open its **Properties** page.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="37b20-109">Para seleccionar una tabla entera o una región de datos de la matriz, haga clic en la región de datos para seleccionarla, haga clic con el botón derecho en un identificador de fila, de columna o de tabla y, después, haga clic en **Propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="37b20-109">To select an entire table or matrix data region, click in the data region to select it, right-click a row, column, or corner handle, and then click **Tablix Properties**.</span></span>

2.  <span data-ttu-id="37b20-110">Haga clic en **visibilidad.**</span><span class="sxs-lookup"><span data-stu-id="37b20-110">Click **Visibility.**</span></span>

3.  <span data-ttu-id="37b20-111">En **Cuando se ejecute inicialmente el informe**, especifique si desea ocultar el elemento la primera vez que se ve el informe:</span><span class="sxs-lookup"><span data-stu-id="37b20-111">In **When the report is initially run**, specify whether to hide the item when you first view the report:</span></span>

    -   <span data-ttu-id="37b20-112">Para mostrar el elemento, haga clic en **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="37b20-112">To display the item, click **Show**.</span></span>

    -   <span data-ttu-id="37b20-113">Para ocultar el elemento, haga clic en **Ocultar**.</span><span class="sxs-lookup"><span data-stu-id="37b20-113">To hide the item, click **Hide**.</span></span>

    -   <span data-ttu-id="37b20-114">Para especificar una expresión que se evalúa en tiempo de ejecución, haga clic en **Mostrar u ocultar en función de una expresión**.</span><span class="sxs-lookup"><span data-stu-id="37b20-114">To specify an expression that is evaluated at run-time, click **Show or hide based on an expression**.</span></span> <span data-ttu-id="37b20-115">Escriba la expresión o haga clic en el botón de expresión (**fx**) para crearla en el cuadro de diálogo **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="37b20-115">Type the expression or click the expression (**fx**) button to create the expression in the **Expression** dialog box.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="37b20-116">Al especificar una expresión para la visibilidad, está estableciendo la propiedad Hidden del elemento de informe, tal como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="37b20-116">When you specify an expression for visibility, you are setting the Hidden property of the report item, as shown in the following image.</span></span> <span data-ttu-id="37b20-117">La expresión evaluada muestra el elemento de informe cuando el valor es False, y lo oculta cuando el valor es True.</span><span class="sxs-lookup"><span data-stu-id="37b20-117">The evaluated expression shows the report item when the value is False, and hides the report item when the value is True.</span></span> 
        > <span data-ttu-id="37b20-118">![Cuadro de diálogo Properties_Visibility y propiedad Hidden](../media/hiddenproperty-propertiesvisibility.png "Cuadro de diálogo Properties_Visibility y propiedad Hidden")</span><span class="sxs-lookup"><span data-stu-id="37b20-118">![Properties_Visibility dialog and Hidden property](../media/hiddenproperty-propertiesvisibility.png "Properties_Visibility dialog and Hidden property")</span></span>

4.  <span data-ttu-id="37b20-119">Haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="37b20-119">Click **OK** twice.</span></span>

### <a name="to-hide-static-rows-in-a-table-matrix-or-list"></a><span data-ttu-id="37b20-120">Ocultar las filas estáticas de una tabla, matriz o lista</span><span class="sxs-lookup"><span data-stu-id="37b20-120">To hide static rows in a table, matrix, or list</span></span>

1.  <span data-ttu-id="37b20-121">En la vista de diseño de informe, haga clic en la tabla, matriz o lista para mostrar los controladores de fila y de columna.</span><span class="sxs-lookup"><span data-stu-id="37b20-121">In report design view, click the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="37b20-122">Haga clic con el botón derecho en el identificador de fila y, después, haga clic en **Visibilidad de fila**.</span><span class="sxs-lookup"><span data-stu-id="37b20-122">Right-click the row handle, and then click **Row Visibility**.</span></span> <span data-ttu-id="37b20-123">Se abrirá el cuadro de diálogo **Visibilidad de fila** .</span><span class="sxs-lookup"><span data-stu-id="37b20-123">The **Row Visibility** dialog box opens.</span></span>

3.  <span data-ttu-id="37b20-124">Para establecer la visibilidad, siga los pasos 3 y 4 del primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="37b20-124">To set the visibility, follow steps 3 and 4 in the first procedure.</span></span>

### <a name="to-hide-static-columns-in-a-table-matrix-or-list"></a><span data-ttu-id="37b20-125">Para ocultar las columnas estáticas de una tabla, matriz o lista</span><span class="sxs-lookup"><span data-stu-id="37b20-125">To hide static columns in a table, matrix, or list</span></span>

1.  <span data-ttu-id="37b20-126">En la vista Diseño, seleccione la tabla, matriz o lista para mostrar los identificadores de fila y de columna.</span><span class="sxs-lookup"><span data-stu-id="37b20-126">In Design view, select the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="37b20-127">Haga clic con el botón derecho en el identificador de columna y, después, haga clic en **Visibilidad de columna**.</span><span class="sxs-lookup"><span data-stu-id="37b20-127">Right-click the column handle, and then click **Column Visibility**.</span></span>

3.  <span data-ttu-id="37b20-128">En el cuadro de diálogo **Visibilidad de columna** , siga los pasos 3 y 4 del primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="37b20-128">In the **Column Visibility** dialog box, follow steps 3 and 4 in the first procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="37b20-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37b20-129">See Also</span></span>
 <span data-ttu-id="37b20-130">[Acción de obtención de detalles &#40;generador de informes y ssrs&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Agregar una acción de expandir o contraer a un elemento &#40;Generador de informes y SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) [ejemplos de expresiones &#40;generador de informes y SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="37b20-130">[Drilldown Action &#40;Report Builder and SSRS&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) [Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md)</span></span>


