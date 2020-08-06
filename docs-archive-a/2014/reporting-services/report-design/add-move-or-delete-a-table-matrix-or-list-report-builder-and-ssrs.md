---
title: Agregar, mover o eliminar una tabla, una matriz o una lista (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b97c470-cde0-4bb1-a46e-5f5f5553feaa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 43941639a41c897a49cd34662b74de26a27e3f07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749114"
---
# <a name="add-move-or-delete-a-table-matrix-or-list-report-builder-and-ssrs"></a><span data-ttu-id="73290-102">Agregar, mover o eliminar una tabla, una matriz o una lista (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="73290-102">Add, Move, or Delete a Table, Matrix, or List (Report Builder and SSRS)</span></span>
  <span data-ttu-id="73290-103">Una región de datos muestra los datos de un conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="73290-103">A data region displays data from a report dataset.</span></span> <span data-ttu-id="73290-104">Entre las regiones de datos se incluyen las siguientes: tabla, matriz, lista, gráfico y medidor.</span><span class="sxs-lookup"><span data-stu-id="73290-104">Data regions include table, matrix, list, chart, and gauge.</span></span> <span data-ttu-id="73290-105">Para anidar una región de datos dentro de otra, agregue por separado cada región de datos y, a continuación, arrastre la región de datos secundaria a la región de datos primaria.</span><span class="sxs-lookup"><span data-stu-id="73290-105">To nest one data region inside another, add each data region separately, and then drag the child data region onto the parent data region.</span></span>  
  
 <span data-ttu-id="73290-106">La manera más simple de agregar una región de datos de tabla o de matriz a su informe es ejecutar el Asistente para nueva tabla o el Asistente para nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="73290-106">The simplest way to add a table or matrix data region to your report is to run the New Table or New Matrix Wizard.</span></span> <span data-ttu-id="73290-107">Estos asistentes le guiarán en el proceso de elegir una conexión a un origen de datos, de organizar los campos y de elegir el diseño y el estilo.</span><span class="sxs-lookup"><span data-stu-id="73290-107">These wizards will guide you through the process of choosing a connection to a data source, arranging fields, and choosing the layout and style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73290-108">El asistente solamente está disponible en el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="73290-108">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-table-or-matrix-to-a-report-by-using-the-new-table-or-new-matrix-wizard"></a><span data-ttu-id="73290-109">Para agregar una tabla o una matriz a un informe utilizando el Asistente para nueva tabla o el Asistente para nueva matriz</span><span class="sxs-lookup"><span data-stu-id="73290-109">To add a table or matrix to a report by using the New Table or New Matrix Wizard</span></span>  
  
1.  <span data-ttu-id="73290-110">En la pestaña **Insertar** , haga clic en **Tabla** o en **Matriz**y, a continuación, haga clic en **Asistente para tablas** o en **Asistente para matrices**.</span><span class="sxs-lookup"><span data-stu-id="73290-110">On the **Insert** tab, click **Table** or **Matrix**, and then click **Table Wizard** or **Matrix Wizard**.</span></span>  
  
2.  <span data-ttu-id="73290-111">Siga los pasos del Asistente para **NewTable** o **nueva matriz** .</span><span class="sxs-lookup"><span data-stu-id="73290-111">Follow the steps in the **NewTable** or **New Matrix** wizard.</span></span>  
  
3.  <span data-ttu-id="73290-112">En la pestaña **Inicio** , haga clic en **Ejecutar** para ver el informe representado.</span><span class="sxs-lookup"><span data-stu-id="73290-112">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="73290-113">En la pestaña **Ejecutar** , haga clic en **Diseño** para seguir trabajando en el informe.</span><span class="sxs-lookup"><span data-stu-id="73290-113">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-data-region"></a><span data-ttu-id="73290-114">Para agregar una región de datos</span><span class="sxs-lookup"><span data-stu-id="73290-114">To add a data region</span></span>  
  
1.  <span data-ttu-id="73290-115">En la **Cinta de opciones**, en el grupo **Regiones de datos** , haga clic en la región de datos que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="73290-115">On the **Ribbon**, in the **Data Regions** group, click the data region to add.</span></span>  
  
2.  <span data-ttu-id="73290-116">Haga clic en la superficie de diseño y, a continuación, arrastre para crear un cuadro que tenga el tamaño deseado para la región de datos.</span><span class="sxs-lookup"><span data-stu-id="73290-116">Click the design surface, and then drag to create a box that is the desired size of the data region.</span></span>  
  
3.  <span data-ttu-id="73290-117">Arrastre un campo del conjunto de datos de informe desde el panel Datos de informe hasta una celda de la región de datos.</span><span class="sxs-lookup"><span data-stu-id="73290-117">Drag a report dataset field from the Report Data pane onto a data region cell.</span></span> <span data-ttu-id="73290-118">La región de datos queda enlazada con los datos del conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="73290-118">The data region is now bound to data from the report dataset.</span></span>  
  
### <a name="to-select-a-data-region"></a><span data-ttu-id="73290-119">Para seleccionar una región de datos</span><span class="sxs-lookup"><span data-stu-id="73290-119">To select a data region</span></span>  
  
-   <span data-ttu-id="73290-120">En el caso de una región de datos Tablix, haga clic con el botón secundario en el controlador de tabla.</span><span class="sxs-lookup"><span data-stu-id="73290-120">For a tablix data region, right-click the corner handle.</span></span> <span data-ttu-id="73290-121">En el caso de un gráfico o una región de datos de medidor, haga clic en la región de datos.</span><span class="sxs-lookup"><span data-stu-id="73290-121">For a chart or gauge data region, click in the data region.</span></span>  
  
     <span data-ttu-id="73290-122">Aparecerá un controlador de selección y ocho controladores de tamaño.</span><span class="sxs-lookup"><span data-stu-id="73290-122">A selection handle and eight resizing handles appear.</span></span>  
  
     <span data-ttu-id="73290-123">En el caso de regiones de datos anidadas, haga clic con el botón derecho en la región de datos anidada, haga clic en **Seleccionar**y, después, seleccione el elemento de informe que quiera.</span><span class="sxs-lookup"><span data-stu-id="73290-123">For nested data regions, right-click in the nested data region, click **Select**, and then select the report item you want.</span></span> <span data-ttu-id="73290-124">Para comprobar qué elemento de informe está seleccionado, use el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="73290-124">To verify which report item is selected, use the Properties pane.</span></span> <span data-ttu-id="73290-125">El nombre del elemento seleccionado en la superficie de diseño aparece en la barra de herramientas del panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="73290-125">The name of the selected item on the design surface appears in the toolbar of the Properties pane.</span></span>  
  
### <a name="to-move-a-data-region"></a><span data-ttu-id="73290-126">Para mover una región de datos</span><span class="sxs-lookup"><span data-stu-id="73290-126">To move a data region</span></span>  
  
-   <span data-ttu-id="73290-127">Para mover una región de datos, haga clic en el controlador de selección de ésta y arrástrelo.</span><span class="sxs-lookup"><span data-stu-id="73290-127">To move a data region, click the selection handle of the data region and drag it.</span></span> <span data-ttu-id="73290-128">Use las líneas de ajuste para alinearla con los elementos de informe existentes.</span><span class="sxs-lookup"><span data-stu-id="73290-128">Use snaplines to align it to existing report items.</span></span>  
  
     <span data-ttu-id="73290-129">Si la regla no está visible, hace clic la pestaña Ver y selecciona la opción **Regla** .</span><span class="sxs-lookup"><span data-stu-id="73290-129">If the ruler is not visible, click the View tab and select the **Ruler** option.</span></span>  
  
     <span data-ttu-id="73290-130">Como alternativa, use las teclas de dirección para mover la región de datos seleccionada por la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="73290-130">Alternatively, use the arrow keys to move the selected data region on the design surface.</span></span>  
  
### <a name="to-delete-a-data-region"></a><span data-ttu-id="73290-131">Para eliminar una región de datos</span><span class="sxs-lookup"><span data-stu-id="73290-131">To delete a data region</span></span>  
  
-   <span data-ttu-id="73290-132">Seleccione la región de datos, haga clic con el botón derecho en ella y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="73290-132">Select the data region, right-click in the data region, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73290-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73290-133">See Also</span></span>  
 <span data-ttu-id="73290-134">[Región de datos Tablix &#40;Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="73290-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="73290-135">[Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="73290-135">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="73290-136">[Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="73290-136">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="73290-137">[Enumera &#40;Generador de informes y SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="73290-137">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="73290-138">Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="73290-138">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
