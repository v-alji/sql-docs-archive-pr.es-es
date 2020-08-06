---
title: Agregar, mover o eliminar un cuadro de texto (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f042cf81-d933-4ac7-9287-c074a46bde98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd85415fd2f0bac2a37b3fbda06795e10f351b19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749113"
---
# <a name="add-move-or-delete-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="5f890-102">Agregar, mover o eliminar un cuadro de texto (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="5f890-102">Add, Move, or Delete a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5f890-103">Los cuadros de texto son los elementos de informe más usados en los informes.</span><span class="sxs-lookup"><span data-stu-id="5f890-103">Text boxes are the most commonly used report item in reports.</span></span> <span data-ttu-id="5f890-104">Puede agregar un cuadro de texto al cuerpo del informe para mostrar información como títulos, opciones de parámetros, campos integrados y fechas.</span><span class="sxs-lookup"><span data-stu-id="5f890-104">You can add a text box to the report body to display information such as titles, parameter choices, built-in fields, and dates.</span></span>  
  
 <span data-ttu-id="5f890-105">Cada celda de una tabla o matriz es en realidad un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="5f890-105">Every cell in a table or matrix is really a text box.</span></span> <span data-ttu-id="5f890-106">Casi todos los datos de informe mostrados en un informe con tablas y matrices son el resultado de la evaluación por parte del procesador de informes del contenido de cada cuadro de texto del informe.</span><span class="sxs-lookup"><span data-stu-id="5f890-106">Almost all report data displayed in a report with tables and matrices is the result of the report processor evaluating the contents of each text box in the report.</span></span> <span data-ttu-id="5f890-107">Como tal, puede dar formato a las celdas de la misma manera que daría formato a otros cuadros de texto que estuvieran fuera de la región de datos.</span><span class="sxs-lookup"><span data-stu-id="5f890-107">As such, you can format cells in the same way you would format other text boxes outside the data region.</span></span>  
  
 <span data-ttu-id="5f890-108">Para agregar un cuadro de texto a una región de datos de lista, debe agregar primero el cuadro de texto y, a continuación, arrastrarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="5f890-108">To add a text box to a list data region, you must first add the text box and then drag it into the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f890-109">Al hacer clic en un cuadro de texto, puede editar inmediatamente el texto de ese cuadro.</span><span class="sxs-lookup"><span data-stu-id="5f890-109">When you click a text box, you're immediately editing the text in the text box.</span></span> <span data-ttu-id="5f890-110">Para seleccionar el propio cuadro de texto, no el texto que contiene, presione ESC.</span><span class="sxs-lookup"><span data-stu-id="5f890-110">To select the text box itself, not the text in it, press ESC.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-text-box"></a><span data-ttu-id="5f890-111">Para agregar un cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="5f890-111">To add a text box</span></span>  
  
1.  <span data-ttu-id="5f890-112">En la vista Diseño, en la pestaña **Insertar** , haga clic en **Cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="5f890-112">On the **Insert** tab in Design view, click **Text Box**.</span></span>  
  
2.  <span data-ttu-id="5f890-113">En la superficie de diseño, haga clic y, a continuación, arrastre un cuadro hasta obtener el tamaño deseado del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="5f890-113">On the design surface, click and then drag a box to the desired size of the text box.</span></span> <span data-ttu-id="5f890-114">También puede hacer clic en la superficie de diseño para crear un cuadro de texto de tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5f890-114">Alternatively, click the design surface to create a text box of default size.</span></span>  
  
### <a name="to-add-a-text-box-in-a-list"></a><span data-ttu-id="5f890-115">Para agregar un cuadro de texto a una lista</span><span class="sxs-lookup"><span data-stu-id="5f890-115">To add a text box in a list</span></span>  
  
1.  <span data-ttu-id="5f890-116">En la vista de diseño de informe, en la pestaña **Insertar** , haga clic en **Lista**.</span><span class="sxs-lookup"><span data-stu-id="5f890-116">On the **Insert** tab in report design view, click **List**.</span></span>  
  
2.  <span data-ttu-id="5f890-117">En la superficie de diseño, haga clic y, a continuación, arrastre un cuadro hasta obtener el tamaño deseado de la lista.</span><span class="sxs-lookup"><span data-stu-id="5f890-117">On the design surface, click and then drag a box to the desired size of the list.</span></span> <span data-ttu-id="5f890-118">O bien, haga clic en la superficie de diseño para crear una lista de tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5f890-118">Alternatively, click the design surface to create a list of default size.</span></span>  
  
3.  <span data-ttu-id="5f890-119">En la pestaña **Insertar** , haga clic en **Cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="5f890-119">On the **Insert** tab, click **Text Box**.</span></span>  
  
4.  <span data-ttu-id="5f890-120">En la superficie de diseño, haga clic en cuadro y, a continuación, arrástrelo hasta obtener el tamaño deseado dentro de la lista que agregó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="5f890-120">On the design surface, click and then drag a box to the desired size of the text box inside the list you added in step 1.</span></span> <span data-ttu-id="5f890-121">O bien, haga clic en la superficie de diseño dentro de la lista para crear un cuadro de texto de tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5f890-121">Alternatively, click the design surface inside the list to create a text box of default size.</span></span>  
  
5.  <span data-ttu-id="5f890-122">Para confirmar que el cuadro de texto se ha anidado correctamente dentro de la lista, selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="5f890-122">To confirm the text box is correctly nested inside the list, select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f890-123">Si hace clic en el cuadro de texto y está en modo de edición, presione ESC para seleccionar el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="5f890-123">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
6.  <span data-ttu-id="5f890-124">En el panel Propiedades, compruebe que la propiedad **Parent** es el rectángulo que se agregó automáticamente a la región de datos de lista.</span><span class="sxs-lookup"><span data-stu-id="5f890-124">In the Properties pane, verify that the **Parent** property is the rectangle that was automatically added to the list data region.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f890-125">Si el panel de propiedades no está visible, en la pestaña **Ver** seleccione **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="5f890-125">If the Properties pane is not visible, check **Properties** on the **View** tab.</span></span>  
  
### <a name="to-move-a-text-box"></a><span data-ttu-id="5f890-126">Para mover un cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="5f890-126">To move a text box</span></span>  
  
1.  <span data-ttu-id="5f890-127">En la vista de diseño de gráfico, haga clic en un espacio vacío del cuadro de texto para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="5f890-127">In report design view, click any empty space within the text box to select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f890-128">Si hace clic en el cuadro de texto y está en modo de edición, presione ESC para seleccionar el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="5f890-128">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
2.  <span data-ttu-id="5f890-129">Haga clic en el identificador del cuadro de texto y arrastre el cuadro de texto a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="5f890-129">Click the text box handle and drag the text box to the new location.</span></span> <span data-ttu-id="5f890-130">O bien, use las teclas de dirección para mover horizontal o verticalmente un cuadro de texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5f890-130">Alternatively, you can use the arrow keys to move a selected text box horizontally or vertically.</span></span> <span data-ttu-id="5f890-131">Para mover el cuadro de texto en incrementos más pequeños en la superficie de diseño, mantenga presionada la tecla CTRL mientras usa las teclas de dirección.</span><span class="sxs-lookup"><span data-stu-id="5f890-131">To move the text box in smaller increments on the design surface, hold down CTRL plus the arrow keys.</span></span>  
  
### <a name="to-delete-a-text-box"></a><span data-ttu-id="5f890-132">Para eliminar un cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="5f890-132">To delete a text box</span></span>  
  
1.  <span data-ttu-id="5f890-133">En la vista de diseño de gráfico, haga clic con el botón derecho en un espacio vacío del cuadro de texto para seleccionarlo y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5f890-133">In report design view, right-click any empty space within the text box to select it, and then click **Delete**.</span></span> <span data-ttu-id="5f890-134">O bien, haga clic en un espacio vacío del cuadro de texto y, a continuación, presione SUPRIMIR.</span><span class="sxs-lookup"><span data-stu-id="5f890-134">Alternatively, click any empty space within the text box, and then press DELETE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f890-135">Si hace clic en el cuadro de texto y está en modo de edición, presione ESC para seleccionar el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="5f890-135">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f890-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f890-136">See Also</span></span>  
 <span data-ttu-id="5f890-137">[Cuadros de texto &#40;Generador de informes y SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5f890-137">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5f890-138">[Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5f890-138">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5f890-139">Métodos abreviados de teclado &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="5f890-139">Keyboard Shortcuts &#40;Report Builder&#41;</span></span>](../report-builder/keyboard-shortcuts-report-builder.md)  
  
  
