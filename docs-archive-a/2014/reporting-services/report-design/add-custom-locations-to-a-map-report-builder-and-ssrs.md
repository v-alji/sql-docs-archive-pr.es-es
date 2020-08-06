---
title: Agregar ubicaciones personalizadas a un mapa (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- MICROSOFT.REPORTDESIGNER.MAPPOINT.POINTTEMPLATE
ms.assetid: 7d36faae-5bcc-446a-9eba-f42349cafacb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 167558534280f08d576205b5ff1b94d0588fcb78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748664"
---
# <a name="add-custom-locations-to-a-map-report-builder-and-ssrs"></a><span data-ttu-id="f9d4a-102">Agregar ubicaciones personalizadas a un mapa (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="f9d4a-102">Add Custom Locations to a Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f9d4a-103">Después de agregar un mapa a un informe, puede agregar sus propias ubicaciones de punto.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-103">After you add a map to a report, you can add your own point locations.</span></span>  
  
 <span data-ttu-id="f9d4a-104">Las propiedades de presentación de todos los puntos de una capa se controlan estableciendo opciones para las propiedades de punto de la capa.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-104">Display properties for all points on a layer are controlled by setting options for the point properties for the layer.</span></span> <span data-ttu-id="f9d4a-105">En un punto incrustado seleccionado, puede invalidar las propiedades de presentación.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-105">For a selected embedded point, you can override the display properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9d4a-106">Al invalidar las propiedades de presentación de capa para el punto incrustado, las modificaciones que realice no son reversibles.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-106">When you override the layer display properties for the embedded point, the changes that you make are not reversible.</span></span>  
  
 <span data-ttu-id="f9d4a-107">Para obtener más información, vea [Variar la presentación de polígonos, líneas y puntos usando reglas y datos analíticos &#40;Generador de informes y SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="f9d4a-107">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-point-layer"></a><span data-ttu-id="f9d4a-108">Para agregar una capa de punto</span><span class="sxs-lookup"><span data-stu-id="f9d4a-108">To add a point layer</span></span>  
  
1.  <span data-ttu-id="f9d4a-109">En la superficie de diseño del informe, haga clic en el mapa para seleccionarlo y muestre el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-109">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="f9d4a-110">En la barra de herramientas, haga clic en **Agregar capa**.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-110">On the toolbar, click **Add Layer**.</span></span>  
  
3.  <span data-ttu-id="f9d4a-111">En la lista desplegable, haga clic en **Agregar capa de punto**.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-111">From the drop-down list, click **Add Point Layer**.</span></span> <span data-ttu-id="f9d4a-112">Una capa de punto sin puntos se agrega al mapa.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-112">A point layer with no points is added to the map.</span></span> <span data-ttu-id="f9d4a-113">De forma predeterminada, la capa de punto está lista para los puntos incrustados.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-113">By default, the point layer is ready for embedded points.</span></span>  
  
### <a name="to-add-a-custom-point"></a><span data-ttu-id="f9d4a-114">Para agregar un punto personalizado</span><span class="sxs-lookup"><span data-stu-id="f9d4a-114">To add a custom point</span></span>  
  
1.  <span data-ttu-id="f9d4a-115">En la superficie de diseño del informe, haga clic en el mapa para seleccionarlo y muestre el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-115">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="f9d4a-116">En el panel Mapa, haga clic con el botón derecho en una capa de punto que tenga el tipo **Incrustado**y luego haga clic en **Agregar punto**.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-116">In the Map pane, right-click a point layer that has type **Embedded**, and then click **Add Point**.</span></span> <span data-ttu-id="f9d4a-117">El cursor cambia a la forma de cruz.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-117">The cursor changes to crosshairs.</span></span>  
  
3.  <span data-ttu-id="f9d4a-118">Para agregar un punto, haga clic en una ubicación del mapa.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-118">To add a point, click a location on the map.</span></span> <span data-ttu-id="f9d4a-119">Un punto incrustado se agrega a la capa seleccionada en la ubicación donde haga clic.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-119">An embedded point is added to the selected layer at the location where you click.</span></span>  
  
### <a name="to-customize-the-display-for-an-embedded-point"></a><span data-ttu-id="f9d4a-120">Para personalizar la presentación de un punto incrustado</span><span class="sxs-lookup"><span data-stu-id="f9d4a-120">To customize the display for an embedded point</span></span>  
  
1.  <span data-ttu-id="f9d4a-121">Haga clic con el botón derecho en el punto y luego haga clic en **Propiedades del punto**.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-121">Right-click the point, and then click **Point Properties**.</span></span> <span data-ttu-id="f9d4a-122">Se abre el cuadro de diálogo **Propiedades de punto incrustado de mapa** .</span><span class="sxs-lookup"><span data-stu-id="f9d4a-122">The **Map Embedded Point Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="f9d4a-123">Haga clic en **Invalidar opciones de punto para esta capa**.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-123">Click **Override point options for this layer**.</span></span> <span data-ttu-id="f9d4a-124">Varias páginas de propiedad aparecen en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-124">Multiple property pages appear in the left pane.</span></span>  
  
3.  <span data-ttu-id="f9d4a-125">Haga clic en las páginas y establezca las propiedades de presentación que desee aplicar a este punto.</span><span class="sxs-lookup"><span data-stu-id="f9d4a-125">Click the pages and set the display properties that you want to apply to this point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d4a-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9d4a-126">See Also</span></span>  
 <span data-ttu-id="f9d4a-127">[Mapas &#40;Generador de informes y SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f9d4a-127">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f9d4a-128">Variar la presentación de polígonos, líneas y puntos usando reglas y datos analíticos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f9d4a-128">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
