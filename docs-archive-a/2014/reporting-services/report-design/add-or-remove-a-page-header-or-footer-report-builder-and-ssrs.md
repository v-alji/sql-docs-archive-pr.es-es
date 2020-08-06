---
title: Agregar o quitar un encabezado o un pie de página (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 72988623-fee8-4a05-9f72-8fcb8e668576
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b29db3f72323c460360c872a0f60d13a808e3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747476"
---
# <a name="add-or-remove-a-page-header-or-footer-report-builder-and-ssrs"></a><span data-ttu-id="faf58-102">Agregar o quitar un encabezado o un pie de página (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="faf58-102">Add or Remove a Page Header or Footer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="faf58-103">Puede agregar texto estático, imágenes, líneas, rectángulos y bordes a encabezados y pies de página.</span><span class="sxs-lookup"><span data-stu-id="faf58-103">You can add static text, images, lines, rectangles, and borders to page headers or footers.</span></span> <span data-ttu-id="faf58-104">Puede colocar expresiones e imágenes enlazadas a datos en un cuadro de texto si desea incluir datos variables o calculados en un encabezado o pie de página.</span><span class="sxs-lookup"><span data-stu-id="faf58-104">You can place expressions and data-bound images in a textbox if you want variable or computed data in a header or footer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="faf58-105">Cada extensión de representación procesa los encabezados y pies de página de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="faf58-105">Each rendering extension processes page headers and footers differently.</span></span> <span data-ttu-id="faf58-106">Para más información, vea [Encabezados y pies de página &#40;Generador de informes y SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) y [Paginación en Reporting Services &#40;Generador de informes y SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="faf58-106">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) and [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-header-or-footer"></a><span data-ttu-id="faf58-107">Para agregar un encabezado o pie de página</span><span class="sxs-lookup"><span data-stu-id="faf58-107">To add a page header or footer</span></span>  
  
1.  <span data-ttu-id="faf58-108">Abra un informe.</span><span class="sxs-lookup"><span data-stu-id="faf58-108">Open a report.</span></span>  
  
2.  <span data-ttu-id="faf58-109">En la superficie de diseño, haga clic con el botón derecho en el informe, seleccione **Insertar**y, después, haga clic en **Encabezado** o **Pie de página**.</span><span class="sxs-lookup"><span data-stu-id="faf58-109">On the design surface, right-click the report, point to **Insert**, and then click **Header** or **Footer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="faf58-110">Las opciones **Encabezado** y **Pie de página** solo aparecen si todavía no hay un encabezado o un pie de página en el informe.</span><span class="sxs-lookup"><span data-stu-id="faf58-110">The **Header** and **Footer** options appear only when a header or footer is not already part of the report.</span></span>  
  
### <a name="to-configure-a-page-header-or-footer"></a><span data-ttu-id="faf58-111">Para configurar un encabezado o un pie de página</span><span class="sxs-lookup"><span data-stu-id="faf58-111">To configure a page header or footer</span></span>  
  
1.  <span data-ttu-id="faf58-112">En la superficie de diseño, haga clic con el botón secundario en el encabezado o el pie de página.</span><span class="sxs-lookup"><span data-stu-id="faf58-112">On the design surface, right-click the page header or footer.</span></span>  
  
2.  <span data-ttu-id="faf58-113">Seleccione **Insertar**y, a continuación, haga clic en uno de los elementos siguientes para agregarlo al área de encabezado o de pie de página:</span><span class="sxs-lookup"><span data-stu-id="faf58-113">Point to **Insert**, and then click one of the following items to add it to the header or footer area:</span></span>  
  
    -   <span data-ttu-id="faf58-114">**Cuadro de texto**</span><span class="sxs-lookup"><span data-stu-id="faf58-114">**Textbox**</span></span>  
  
    -   <span data-ttu-id="faf58-115">**Línea**</span><span class="sxs-lookup"><span data-stu-id="faf58-115">**Line**</span></span>  
  
    -   <span data-ttu-id="faf58-116">**Rectángulo**</span><span class="sxs-lookup"><span data-stu-id="faf58-116">**Rectangle**</span></span>  
  
    -   <span data-ttu-id="faf58-117">**Imagen**</span><span class="sxs-lookup"><span data-stu-id="faf58-117">**Image**</span></span>  
  
3.  <span data-ttu-id="faf58-118">Haga clic con el botón derecho en el encabezado de página y, después, haga clic en **Propiedades de encabezado** para agregar bordes, imágenes de fondo o colores, o para ajustar el ancho del encabezado.</span><span class="sxs-lookup"><span data-stu-id="faf58-118">Right-click the page header, and then click **Header Properties** to add borders, background images, or colors, or to adjust the width of the header.</span></span> <span data-ttu-id="faf58-119">A continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="faf58-119">Then click **OK**.</span></span>  
  
4.  <span data-ttu-id="faf58-120">Haga clic con el botón derecho en el pie de página y, después, haga clic en **Propiedades de pie de página** para agregar bordes, imágenes de fondo o colores, o para ajustar el ancho del pie de página.</span><span class="sxs-lookup"><span data-stu-id="faf58-120">Right-click the page footer, and then click **Footer Properties** to add borders, background images, or colors, or to adjust the width of the footer.</span></span> <span data-ttu-id="faf58-121">A continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="faf58-121">Then click **OK**.</span></span>  
  
### <a name="to-remove-a-page-header-or-footer"></a><span data-ttu-id="faf58-122">Para quitar un encabezado o pie de página</span><span class="sxs-lookup"><span data-stu-id="faf58-122">To remove a page header or footer</span></span>  
  
1.  <span data-ttu-id="faf58-123">Abra un informe.</span><span class="sxs-lookup"><span data-stu-id="faf58-123">Open a report.</span></span>  
  
2.  <span data-ttu-id="faf58-124">En la superficie de diseño, haga clic con el botón derecho en el encabezado o el pie de página y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="faf58-124">On the design surface, right-click the page header or footer, and then click **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="faf58-125">Cuando se quita un encabezado o pie de página, se elimina del informe.</span><span class="sxs-lookup"><span data-stu-id="faf58-125">When you remove a page header or footer, you delete it from the report.</span></span> <span data-ttu-id="faf58-126">Los elementos que agregó previamente al encabezado o el pie de página no aparecerán de nuevo si vuelve a agregar uno u otro.</span><span class="sxs-lookup"><span data-stu-id="faf58-126">Any items that you previously added to the page header or footer will not reappear if you subsequently add the header or footer again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf58-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="faf58-127">See Also</span></span>  
 [<span data-ttu-id="faf58-128">Encabezados y pies de página &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="faf58-128">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
