---
title: Cuadro de diálogo Propiedades de ventanilla de mapa, centrar y hacer zoom | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.centerandzoom.f1
- "10506"
ms.assetid: 642a06f5-293f-48e0-97a6-1489dbefa719
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 913c00773abf71ca627b8cc2a94a873484e8ab30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670849"
---
# <a name="map-viewport-properties-dialog-box-center-and-zoom"></a><span data-ttu-id="37768-102">Cuadro de diálogo Propiedades de ventanilla de mapa, Centrar y hacer zoom</span><span class="sxs-lookup"><span data-stu-id="37768-102">Map Viewport Properties Dialog Box, Center and Zoom</span></span>
  <span data-ttu-id="37768-103">Seleccione **Centrar y hacer zoom** en el cuadro de diálogo **Propiedades de ventanilla de mapa** para establecer la vista de centro y el factor de zoom de un mapa.</span><span class="sxs-lookup"><span data-stu-id="37768-103">Select **Center and Zoom** for the **Map Viewport Properties** dialog box to set the center view and zoom factor for a map.</span></span> <span data-ttu-id="37768-104">Después de especificar un origen de datos de mapa y los límites del mapa que desee incluir en el informe, puede especificar el centro de la vista y el factor de zoom para controlar más la presentación del mapa.</span><span class="sxs-lookup"><span data-stu-id="37768-104">After you specify a map data source and the boundaries of the map that you want to include in your report, you can specify the view center and the zoom factor to further control the map display.</span></span> <span data-ttu-id="37768-105">Las opciones cambian en función de qué método se use para especificar los valores del centro y el zoom.</span><span class="sxs-lookup"><span data-stu-id="37768-105">Options change depending on which method you use to specify the center and zoom values.</span></span> <span data-ttu-id="37768-106">Haga clic en el botón **Expresión** (*fx*) para modificar una expresión que establezca el valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="37768-106">Click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
## <a name="options"></a><span data-ttu-id="37768-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="37768-107">Options</span></span>  
 <span data-ttu-id="37768-108">**Establecer un nivel para centrar y hacer zoom de la vista**</span><span class="sxs-lookup"><span data-stu-id="37768-108">**Set a view center and zoom level**</span></span>  
 <span data-ttu-id="37768-109">Elija esta opción para especificar los valores personalizados para el centro de la vista y el nivel de zoom.</span><span class="sxs-lookup"><span data-stu-id="37768-109">Choose this option to specify custom values for the view center and the zoom level.</span></span>  
  
 <span data-ttu-id="37768-110">**Centrar mapa para mostrar una capa de mapa**</span><span class="sxs-lookup"><span data-stu-id="37768-110">**Center map to show a map layer**</span></span>  
 <span data-ttu-id="37768-111">Elija esta opción para especificar una capa y centrar automáticamente la vista en los datos del mapa.</span><span class="sxs-lookup"><span data-stu-id="37768-111">Choose this option to specify a layer and automatically center the view on its map data.</span></span> <span data-ttu-id="37768-112">Por ejemplo, centre la vista en LineLayer1.</span><span class="sxs-lookup"><span data-stu-id="37768-112">For example, center the view on LineLayer1.</span></span>  
  
 <span data-ttu-id="37768-113">**Centrar mapa para mostrar un elemento de mapa incrustado**</span><span class="sxs-lookup"><span data-stu-id="37768-113">**Center map to show an embedded map element**</span></span>  
 <span data-ttu-id="37768-114">Elija esta opción para centrar la vista en un elemento de mapa enlazado a datos concreto.</span><span class="sxs-lookup"><span data-stu-id="37768-114">Choose this option to center the view on a specific data-bound map element.</span></span> <span data-ttu-id="37768-115">Los datos espaciales deben tener una relación con los datos analíticos para especificar esta opción.</span><span class="sxs-lookup"><span data-stu-id="37768-115">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="37768-116">Por ejemplo, centre la vista en el elemento de mapa en el que el nombre del campo coincidente sea [City] y el valor de coincidencia "Seattle".</span><span class="sxs-lookup"><span data-stu-id="37768-116">For example, center the view on the map element where the name of the match field is [City] and the match value is "Seattle".</span></span>  
  
 <span data-ttu-id="37768-117">**Centrar el mapa para mostrar todos los elementos del mapa de enlaces de datos**</span><span class="sxs-lookup"><span data-stu-id="37768-117">**Center map to show all data-bound map elements**</span></span>  
 <span data-ttu-id="37768-118">Elija esta opción para centrar la vista en todos los elementos de mapa de la capa.</span><span class="sxs-lookup"><span data-stu-id="37768-118">Choose this option to center the view on all map elements in the layer.</span></span> <span data-ttu-id="37768-119">Los datos espaciales deben tener una relación con los datos analíticos para especificar esta opción.</span><span class="sxs-lookup"><span data-stu-id="37768-119">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="37768-120">Por ejemplo, centre la vista en la capa de burbuja de polígono que muestra las ciudades y el tamaño de burbuja se relaciona con la población.</span><span class="sxs-lookup"><span data-stu-id="37768-120">For example, center the view on the polygon bubble layer that shows cities and the bubble size is related to population.</span></span> <span data-ttu-id="37768-121">Solo las ciudades con un valor de población coincidente se incluyen al calcular el centro de la ventanilla.</span><span class="sxs-lookup"><span data-stu-id="37768-121">Only those cities with a matching population value are included when calculating the center for the viewport.</span></span>  
  
 <span data-ttu-id="37768-122">**Opciones de centrar y hacer zoom**</span><span class="sxs-lookup"><span data-stu-id="37768-122">**Center and zoom options**</span></span>  
 <span data-ttu-id="37768-123">Seleccione una opción para especificar el centro de la vista y el nivel de zoom.</span><span class="sxs-lookup"><span data-stu-id="37768-123">Select an option to specify the view center and zoom level.</span></span>  
  
 <span data-ttu-id="37768-124">**Centro de vista (X) %**</span><span class="sxs-lookup"><span data-stu-id="37768-124">**View center (X) %**</span></span>  
 <span data-ttu-id="37768-125">Coordenada horizontal.</span><span class="sxs-lookup"><span data-stu-id="37768-125">The horizontal coordinate.</span></span> <span data-ttu-id="37768-126">El valor predeterminado, 50%,</span><span class="sxs-lookup"><span data-stu-id="37768-126">The default value, 50%.</span></span> <span data-ttu-id="37768-127">centra la vista en el punto medio entre los valores horizontales mínimo y máximo.</span><span class="sxs-lookup"><span data-stu-id="37768-127">centers the view at the midpoint between the minimum and maximum horizontal values.</span></span>  
  
 <span data-ttu-id="37768-128">**Centro de vista (Y) %**</span><span class="sxs-lookup"><span data-stu-id="37768-128">**View center (Y) %**</span></span>  
 <span data-ttu-id="37768-129">Coordenada vertical.</span><span class="sxs-lookup"><span data-stu-id="37768-129">The vertical coordinate.</span></span> <span data-ttu-id="37768-130">El valor predeterminado, 50%, centra la vista en el punto medio entre los valores verticales mínimo y máximo.</span><span class="sxs-lookup"><span data-stu-id="37768-130">The default value, 50%, centers the view at the midpoint between the minimum and maximum vertical values.</span></span>  
  
 <span data-ttu-id="37768-131">**Nivel de zoom (%)**</span><span class="sxs-lookup"><span data-stu-id="37768-131">**Zoom level (%)**</span></span>  
 <span data-ttu-id="37768-132">Factor del zoom.</span><span class="sxs-lookup"><span data-stu-id="37768-132">The zoom factor.</span></span> <span data-ttu-id="37768-133">El valor predeterminado, 100%, indica que no se produce aumento.</span><span class="sxs-lookup"><span data-stu-id="37768-133">The default value, 100%, indicates no magnification.</span></span>  
  
 <span data-ttu-id="37768-134">**Centrar vista en esta capa**</span><span class="sxs-lookup"><span data-stu-id="37768-134">**Center view on this layer**</span></span>  
 <span data-ttu-id="37768-135">Especifica el nombre de la capa.</span><span class="sxs-lookup"><span data-stu-id="37768-135">Specify the name of the layer.</span></span>  
  
 <span data-ttu-id="37768-136">**Centrar vista en elemento del mapa que coincida con esta condición**</span><span class="sxs-lookup"><span data-stu-id="37768-136">**Center view on the map element that matches this condition**</span></span>  
 <span data-ttu-id="37768-137">El campo de solo lectura que se muestra se utiliza para hacer coincidir los datos del mapa con los datos analíticos.</span><span class="sxs-lookup"><span data-stu-id="37768-137">The read-only field that is displayed is used to match map data and analytical data.</span></span> <span data-ttu-id="37768-138">Especifique el valor con el que desea buscar la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="37768-138">Specify the value that you want to match on.</span></span> <span data-ttu-id="37768-139">La vista se centra automáticamente en este elemento del mapa.</span><span class="sxs-lookup"><span data-stu-id="37768-139">The view automatically centers on this map element.</span></span> <span data-ttu-id="37768-140">Por ejemplo, NAME = TEXAS.</span><span class="sxs-lookup"><span data-stu-id="37768-140">For example, NAME = TEXAS.</span></span> <span data-ttu-id="37768-141">De forma predeterminada, el tipo de datos de la condición es String y la coincidencia distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="37768-141">By default, the data type for the condition is String and the match is case-sensitive.</span></span>  
  
 <span data-ttu-id="37768-142">Para establecer la coincidencia en un campo que tiene un tipo de datos diferente, debe escribir una expresión que se evalúe como ese tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="37768-142">To match on a field that has a different data type, you must write an expression that evaluates to that data type.</span></span> <span data-ttu-id="37768-143">Por ejemplo, si el campo coincidente es un código postal de cinco dígitos que se almacena como un entero, para especificar el código postal 98053, debe utilizar la expresión =98053.</span><span class="sxs-lookup"><span data-stu-id="37768-143">For example, if the match field is a 5 digit postal code that is stored as an integer, then to specify the postal code 98053, you must use the expression =98053.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37768-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37768-144">See Also</span></span>  
 [<span data-ttu-id="37768-145">Mapas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="37768-145">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
