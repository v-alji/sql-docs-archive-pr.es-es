---
title: Mostrar números de página u otras propiedades del informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7d95245-4709-4d04-acb4-59bf71e60d97
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: efc3d5d5de11af1fcdfefc52ed12d5057ee12668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672731"
---
# <a name="display-page-numbers-or-other-report-properties-report-builder-and-ssrs"></a><span data-ttu-id="a1dce-102">Mostrar números de página u otras propiedades del informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="a1dce-102">Display Page Numbers or Other Report Properties (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a1dce-103">Es fácil agregar números de página, un título del informe, nombre de archivo y otras propiedades del informe a los encabezados o pies de página de su informe.</span><span class="sxs-lookup"><span data-stu-id="a1dce-103">It's easy to add page numbers, a report title, file name, and other report properties to the page headers or footers of your report.</span></span> <span data-ttu-id="a1dce-104">Estas propiedades se almacenan como campos en la carpeta Campos integrados del panel Datos de informe:</span><span class="sxs-lookup"><span data-stu-id="a1dce-104">These properties are stored as fields in the Built-in Fields folder in the Report Data pane:</span></span>  
  
-   <span data-ttu-id="a1dce-105">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a1dce-105">Execution time</span></span>  
  
-   <span data-ttu-id="a1dce-106">Número de página</span><span class="sxs-lookup"><span data-stu-id="a1dce-106">Page number</span></span>  
  
-   <span data-ttu-id="a1dce-107">ReportFolder</span><span class="sxs-lookup"><span data-stu-id="a1dce-107">Report folder</span></span>  
  
-   <span data-ttu-id="a1dce-108">Nombre del informe</span><span class="sxs-lookup"><span data-stu-id="a1dce-108">Report name</span></span>  
  
-   <span data-ttu-id="a1dce-109">Dirección URL del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="a1dce-109">Report server URL</span></span>  
  
-   <span data-ttu-id="a1dce-110">Páginas totales</span><span class="sxs-lookup"><span data-stu-id="a1dce-110">Total pages</span></span>  
  
-   <span data-ttu-id="a1dce-111">Id. de usuario</span><span class="sxs-lookup"><span data-stu-id="a1dce-111">User ID</span></span>  
  
-   <span data-ttu-id="a1dce-112">Idioma</span><span class="sxs-lookup"><span data-stu-id="a1dce-112">Language</span></span>  
  
 <span data-ttu-id="a1dce-113">Para un número de página, puede desear agregar la palabra "Página" antes del número.</span><span class="sxs-lookup"><span data-stu-id="a1dce-113">For a page number, you may want to add the word "Page" before the number.</span></span> <span data-ttu-id="a1dce-114">También puede desear mostrar el número total de páginas.</span><span class="sxs-lookup"><span data-stu-id="a1dce-114">You may also want to show the total number of pages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1dce-115">Agregar el número total de páginas al pie de página puede provocar un rendimiento lento cuando ejecuta el informe u obtiene de él una vista previa.</span><span class="sxs-lookup"><span data-stu-id="a1dce-115">Adding the total number of pages to the footer may slow performance when you run or preview your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-number-or-other-report-properties"></a><span data-ttu-id="a1dce-116">Para agregar un número de página u otras propiedades del informe</span><span class="sxs-lookup"><span data-stu-id="a1dce-116">To add a page number or other report properties</span></span>  
  
1.  <span data-ttu-id="a1dce-117">En el panel Datos de informe, expanda la carpeta Campos integrados.</span><span class="sxs-lookup"><span data-stu-id="a1dce-117">In the Report Data pane, expand the Built-in Fields folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a1dce-118">Si no ve el panel Datos de informe, en la pestaña Ver haga clic en **Datos de informe**.</span><span class="sxs-lookup"><span data-stu-id="a1dce-118">If you don't see the Report Data pane, on the View tab, check **Report Data**.</span></span>  
  
2.  <span data-ttu-id="a1dce-119">Arrastre el campo **Número de página** desde el panel Datos de informe al encabezado o el pie del informe.</span><span class="sxs-lookup"><span data-stu-id="a1dce-119">Drag the **Page Number** field from the Report Data pane to the report header or footer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a1dce-120">El pie de página se agrega automáticamente al informe.</span><span class="sxs-lookup"><span data-stu-id="a1dce-120">The page footer is added to the report automatically.</span></span> <span data-ttu-id="a1dce-121">Para agregar un encabezado de página, en la pestaña **Insertar** haga clic en **Encabezado**y, a continuación, en **Agregar encabezado**.</span><span class="sxs-lookup"><span data-stu-id="a1dce-121">To add a page header, on the **Insert** tab, click **Header**, and then click **Add Header**.</span></span>  
    >   
    >  <span data-ttu-id="a1dce-122">Se agrega un cuadro de texto contiene la expresión simple [&PageNumber].</span><span class="sxs-lookup"><span data-stu-id="a1dce-122">A text box that contains the simple expression [&PageNumber] is added.</span></span>  
  
### <a name="to-add-the-word-page-before-the-page-number"></a><span data-ttu-id="a1dce-123">Para agregar la palabra "Página" antes del número de página</span><span class="sxs-lookup"><span data-stu-id="a1dce-123">To add the word "Page" before the page number</span></span>  
  
1.  <span data-ttu-id="a1dce-124">Haga clic con el botón derecho en el cuadro de texto que contiene [&PageNumber] y haga clic en **Expresiones**.</span><span class="sxs-lookup"><span data-stu-id="a1dce-124">Right-click the text box that contains [&PageNumber] and click **Expressions**.</span></span>  
  
     <span data-ttu-id="a1dce-125">El cuadro de texto **Establecer expresión para: Valor** contiene la expresión =Globals!PageNumber.</span><span class="sxs-lookup"><span data-stu-id="a1dce-125">The **Set Expression for: Value** text box contains the expression =Globals!PageNumber.</span></span>  
  
2.  <span data-ttu-id="a1dce-126">Coloque el cursor después del signo = y escriba `"Page " &`.</span><span class="sxs-lookup"><span data-stu-id="a1dce-126">Place the cursor after the = sign and type `"Page " &`.</span></span>  
  
     <span data-ttu-id="a1dce-127">La expresión ahora es ="Página "&Globals!PageNumber</span><span class="sxs-lookup"><span data-stu-id="a1dce-127">The expression is now  ="Page "&Globals!PageNumber</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-total-number-of-pages-after-the-page-number"></a><span data-ttu-id="a1dce-128">Para agregar el número total de páginas después del número de página</span><span class="sxs-lookup"><span data-stu-id="a1dce-128">To add total number of pages after the page number</span></span>  
  
1.  <span data-ttu-id="a1dce-129">Haga clic con el botón secundario en el cuadro de texto con la expresión y haga clic en **Expresiones**.</span><span class="sxs-lookup"><span data-stu-id="a1dce-129">Right click the text box with the expression and click **Expressions**.</span></span>  
  
2.  <span data-ttu-id="a1dce-130">Escriba **&" de "&** al final de la expresión.</span><span class="sxs-lookup"><span data-stu-id="a1dce-130">Type **&" of "&** at the end of the expression.</span></span>  
  
3.  <span data-ttu-id="a1dce-131">En el panel Categoría, expanda **Campos integrados** y haga doble clic en **TotalPages**.</span><span class="sxs-lookup"><span data-stu-id="a1dce-131">In the Category pane, expand **Built-in Fields** and double-click **TotalPages**.</span></span>  
  
     <span data-ttu-id="a1dce-132">La expresión es ahora ="Página "&Globals!PageNumber &" de "&Globals!TotalPages</span><span class="sxs-lookup"><span data-stu-id="a1dce-132">The expression is now ="Page "&Globals!PageNumber &" of "&Globals!TotalPages</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a1dce-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1dce-133">See Also</span></span>  
 <span data-ttu-id="a1dce-134">[Encabezados y pies de página &#40;Generador de informes y SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a1dce-134">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a1dce-135">Dar formato al texto en un cuadro de texto &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a1dce-135">Format Text in a Text Box &#40;Report Builder and SSRS&#41;</span></span>](format-text-in-a-text-box-report-builder-and-ssrs.md)  
  
  
