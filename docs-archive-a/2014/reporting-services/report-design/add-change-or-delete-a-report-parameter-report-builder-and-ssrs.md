---
title: Agregar, cambiar o eliminar parámetros de informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d44a8e0a-10cf-4502-9391-09743ffc9bad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 231cd51d7ed0a481f004b39a2e8819df3fc33748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672762"
---
# <a name="add-change-or-delete-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="3814c-102">Agregar, cambiar o eliminar parámetros de informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="3814c-102">Add, Change, or Delete a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3814c-103">Los parámetros de informe permiten elegir datos de informe, conectar informes relacionados y cambiar la presentación de los informes.</span><span class="sxs-lookup"><span data-stu-id="3814c-103">A report parameter provides a way to choose report data, connect related reports together, and vary the report presentation.</span></span> <span data-ttu-id="3814c-104">Puede proporcionar un valor predeterminado y una lista de valores disponibles, y el usuario puede cambiar la selección.</span><span class="sxs-lookup"><span data-stu-id="3814c-104">You can provide a default value and a list of available values, and the user can change the selection.</span></span>  
  
 <span data-ttu-id="3814c-105">Una vez publicado el informe, puede cambiar los valores predeterminados, los valores disponibles y otras propiedades del parámetro en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="3814c-105">After you publish a report, you can change the default values, the available values, and other properties for a report parameter on the report server.</span></span> <span data-ttu-id="3814c-106">Puede proporcionar varios conjuntos de valores de parámetros predeterminados creando informes vinculados.</span><span class="sxs-lookup"><span data-stu-id="3814c-106">You can provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="3814c-107">Para obtener más información, vea "Establecer las propiedades de los parámetros de un informe publicado" en la documentación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en los [Libros en pantalla de SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="3814c-107">For more information, see "Setting Parameter Properties for a Published Report" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-or-edit-a-report-parameter"></a><span data-ttu-id="3814c-108">Para agregar o modificar un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="3814c-108">To add or edit a report parameter</span></span>  
  
1.  <span data-ttu-id="3814c-109">En el panel **Datos de informe** , haga clic con el botón secundario en el nodo **Parámetros** y haga clic en **Agregar parámetro**.</span><span class="sxs-lookup"><span data-stu-id="3814c-109">In the **Report Data** pane, right-click the **Parameters** node and click **Add Parameter**.</span></span> <span data-ttu-id="3814c-110">Se abrirá el cuadro de diálogo **Propiedades de parámetro de informe** .</span><span class="sxs-lookup"><span data-stu-id="3814c-110">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="3814c-111">En **Nombre**, escriba el nombre del parámetro o acepte el nombre predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3814c-111">In **Name**, type the name of the parameter or accept the default name.</span></span>  
  
3.  <span data-ttu-id="3814c-112">En **Pedir datos**, escriba el texto que se mostrará junto al cuadro de texto del parámetro cuando el usuario ejecute el informe.</span><span class="sxs-lookup"><span data-stu-id="3814c-112">In **Prompt**, type the text that appears next to the parameter text box when the user runs the report.</span></span>  
  
4.  <span data-ttu-id="3814c-113">En **Tipo de datos**, seleccione el tipo de datos del valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="3814c-113">In **Data type**, select the data type for the parameter value.</span></span>  
  
5.  <span data-ttu-id="3814c-114">Si el parámetro puede contener un valor en blanco, seleccione **Permitir valor en blanco**.</span><span class="sxs-lookup"><span data-stu-id="3814c-114">If the parameter can contain a blank value, select **Allow blank value**.</span></span>  
  
6.  <span data-ttu-id="3814c-115">Si el parámetro puede contener un valor NULL, seleccione **Permitir valor NULL**.</span><span class="sxs-lookup"><span data-stu-id="3814c-115">If the parameter can contain a null value, select **Allow null value**.</span></span>  
  
7.  <span data-ttu-id="3814c-116">Para permitir a los usuarios seleccionar más de un valor para el parámetro, seleccione **Permitir varios valores**.</span><span class="sxs-lookup"><span data-stu-id="3814c-116">To allow a user to select more than one value for the parameter, select **Allow multiple values**.</span></span>  
  
8.  <span data-ttu-id="3814c-117">Establezca la opción de visibilidad.</span><span class="sxs-lookup"><span data-stu-id="3814c-117">Set the visibility option.</span></span>  
  
    -   <span data-ttu-id="3814c-118">Para mostrar el parámetro en la barra de herramientas de la parte superior del informe, seleccione **Visible**.</span><span class="sxs-lookup"><span data-stu-id="3814c-118">To show the parameter on the toolbar at the top of the report, select **Visible**.</span></span>  
  
    -   <span data-ttu-id="3814c-119">Para ocultar el parámetro con objeto de que no se muestre en la barra de herramientas, seleccione **Oculto**.</span><span class="sxs-lookup"><span data-stu-id="3814c-119">To hide the parameter so that it does not display on the toolbar, select **Hidden**.</span></span>  
  
    -   <span data-ttu-id="3814c-120">Para ocultar el parámetro y evitar que pueda modificarse en el servidor de informes una vez publicado el informe, seleccione **Interno**.</span><span class="sxs-lookup"><span data-stu-id="3814c-120">To hide the parameter and protect it from being modified on the report server after the report is published, select **Internal**.</span></span> <span data-ttu-id="3814c-121">De esta forma, el parámetro de informe solamente podrá verse en la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="3814c-121">The report parameter can then only be viewed in the report definition.</span></span> <span data-ttu-id="3814c-122">Si elige esta opción, debe establecer un valor predeterminado o permitir que el parámetro acepte un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="3814c-122">For this option, you must set a default value or allow the parameter to accept a null value.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-report-parameter"></a><span data-ttu-id="3814c-123">Para eliminar un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="3814c-123">To delete a report parameter</span></span>  
  
1.  <span data-ttu-id="3814c-124">En el panel **Datos de informe** , expanda el nodo **Parámetros** .</span><span class="sxs-lookup"><span data-stu-id="3814c-124">In the **Report Data** pane, expand the **Parameters** node.</span></span>  
  
2.  <span data-ttu-id="3814c-125">Haga clic con el botón derecho en el parámetro de informe y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3814c-125">Right-click the report parameter and click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3814c-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3814c-126">See Also</span></span>  
 <span data-ttu-id="3814c-127">[Agregar, cambiar o eliminar los valores disponibles para un parámetro de informe &#40;Generador de informes y SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="3814c-127">[Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="3814c-128">[Agregar, cambiar o eliminar valores predeterminados para un parámetro de informe &#40;Generador de informes y SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="3814c-128">[Add, Change, or Delete Default Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="3814c-129">[Cambiar el orden de un parámetro de informe &#40;Generador de informes y SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3814c-129">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3814c-130">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="3814c-130">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="3814c-131">[Generador de informes ayuda para cuadros de diálogo, paneles y asistentes](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="3814c-131">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="3814c-132">[Agregar parámetros en cascada a un informe &#40;Generador de informes y SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3814c-132">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3814c-133">[Tutorial: agregar un parámetro a un informe &#40;Generador de informes&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="3814c-133">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="3814c-134">[Tutoriales &#40;Generador de informes&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="3814c-134">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="3814c-135">[Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="3814c-135">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="3814c-136">[Referencias a la colección Parameters &#40;Generador de informes y SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="3814c-136">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 [<span data-ttu-id="3814c-137">Agregar un parámetro de varios valores a un informe</span><span class="sxs-lookup"><span data-stu-id="3814c-137">Add a multi-value parameter to a Report</span></span>](add-a-multi-value-parameter-to-a-report.md)  
  
  
