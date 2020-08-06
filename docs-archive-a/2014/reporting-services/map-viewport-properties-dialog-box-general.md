---
title: Cuadro de diálogo Propiedades de ventanilla de mapa, general | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.general.f1
- "10505"
ms.assetid: 6c9c773e-5c56-4571-95ed-8a157cfdfe52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d760d6a0572cbbd1bd948eab382c0727eb276c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662648"
---
# <a name="map-viewport-properties-dialog-box-general"></a><span data-ttu-id="c33a2-102">Cuadro de diálogo Propiedades de ventanilla de mapa, General</span><span class="sxs-lookup"><span data-stu-id="c33a2-102">Map Viewport Properties Dialog Box, General</span></span>
  <span data-ttu-id="c33a2-103">Seleccione **General** en el cuadro de diálogo **Propiedades de ventanilla de mapa** para cambiar las opciones del sistema de coordenadas, la proyección y los límites.</span><span class="sxs-lookup"><span data-stu-id="c33a2-103">Select **General** on the **Map Viewport Properties** dialog box to change the coordinate system, the projection, and the boundary options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c33a2-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="c33a2-104">Options</span></span>  
 <span data-ttu-id="c33a2-105">**Sistema de coordenadas**</span><span class="sxs-lookup"><span data-stu-id="c33a2-105">**Coordinate system**</span></span>  
 <span data-ttu-id="c33a2-106">Indique el tipo de sistema de coordenadas que el mapa de datos usa.</span><span class="sxs-lookup"><span data-stu-id="c33a2-106">Indicate the type of coordinate system that the map data uses.</span></span>  
  
-   <span data-ttu-id="c33a2-107">**Planar** : elija esta opción cuando los datos del mapa estén en coordenadas X e Y, por ejemplo para generar planes.</span><span class="sxs-lookup"><span data-stu-id="c33a2-107">**Planar** Choose this option when map data is in X and Y coordinates, for example, for building plans.</span></span>  
  
-   <span data-ttu-id="c33a2-108">**Geográfico** : elija esta opción cuando los datos del mapa estén en coordenadas de longitud y latitud, por ejemplo para las ubicaciones de ciudades.</span><span class="sxs-lookup"><span data-stu-id="c33a2-108">**Geographic** Choose this option when map data is in longitude and latitude coordinates, for example, for city locations.</span></span>  
  
 <span data-ttu-id="c33a2-109">**Proyección**</span><span class="sxs-lookup"><span data-stu-id="c33a2-109">**Projection**</span></span>  
 <span data-ttu-id="c33a2-110">Especifique el método que utilizar para proyectar las coordenadas geográficas en una superficie bidimensional.</span><span class="sxs-lookup"><span data-stu-id="c33a2-110">Specify the method to use to project geographic coordinates onto a two-dimensional surface.</span></span> <span data-ttu-id="c33a2-111">Elija una proyección que sea compatible con los datos que está visualizando.</span><span class="sxs-lookup"><span data-stu-id="c33a2-111">Choose a projection that is compatible with the data that you are visualizing.</span></span> <span data-ttu-id="c33a2-112">Las cuatro propiedades espaciales a las que afecta la proyección son el área, forma, distancia y dirección.</span><span class="sxs-lookup"><span data-stu-id="c33a2-112">The four spatial properties that are affected by projection are area, shape, distance, and direction.</span></span> <span data-ttu-id="c33a2-113">Para las vistas de la tierra, una buena opción de proyección depende de la vista del centro, los límites del mapa y el factor de zoom.</span><span class="sxs-lookup"><span data-stu-id="c33a2-113">For views of the earth, a good choice of projection depends on the center view, the map boundaries, and the zoom factor.</span></span>  
  
 <span data-ttu-id="c33a2-114">Cada una de las proyecciones siguientes conserva una o varias de estas propiedades espaciales:</span><span class="sxs-lookup"><span data-stu-id="c33a2-114">Each of the following projections preserves one or more of these spatial properties:</span></span>  
  
-   <span data-ttu-id="c33a2-115">**Equirectangular** : elija esta opción para utilizar la longitud y la latitud como coordenadas rectangulares.</span><span class="sxs-lookup"><span data-stu-id="c33a2-115">**Equirectangular** Choose this option to use longitude and latitude as rectangular coordinates.</span></span>  
  
-   <span data-ttu-id="c33a2-116">**Mercator** : elija esta proyección popular para las áreas más pequeñas, con menos distorsión alrededor del ecuador o cuando desee agregar una capa de mapa con una capa de mosaico existente que use la proyección Mercator.</span><span class="sxs-lookup"><span data-stu-id="c33a2-116">**Mercator** Choose this popular projection for smaller areas, for less distortion around the equator, or when you want to add a map layer with an existing tile layer that uses the Mercator projection.</span></span>  
  
-   <span data-ttu-id="c33a2-117">**Robinson** : elija esta opción para tener menos distorsión de áreas grandes que abarcan desde el ecuador a los polos.</span><span class="sxs-lookup"><span data-stu-id="c33a2-117">**Robinson** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="c33a2-118">Fue desarrollado por Arthur H. Robinson en 1963.</span><span class="sxs-lookup"><span data-stu-id="c33a2-118">Developed by Arthur H. Robinson in 1963.</span></span>  
  
-   <span data-ttu-id="c33a2-119">**Fahey** : elija esta opción para tener menos distorsión de las áreas grandes que abarcan desde el ecuador a los polos.</span><span class="sxs-lookup"><span data-stu-id="c33a2-119">**Fahey** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="c33a2-120">Fue desarrollado por Lawrence Fahey en 1975.</span><span class="sxs-lookup"><span data-stu-id="c33a2-120">Developed by Lawrence Fahey in 1975.</span></span>  
  
-   <span data-ttu-id="c33a2-121">**Eckert1** : elija esta opción para utilizar paralelos igualmente espaciados en latitud y con líneas rectas para los meridianos en la longitud.</span><span class="sxs-lookup"><span data-stu-id="c33a2-121">**Eckert1** Choose this option to use equally spaced parallels in latitude and straight lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="c33a2-122">**Eckert3** : elija esta opción para utilizar paralelos igualmente espaciados en latitud y con líneas curvas para los meridianos en la longitud.</span><span class="sxs-lookup"><span data-stu-id="c33a2-122">**Eckert3** Choose this option to use equally spaced parallels in latitude and curved lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="c33a2-123">**HammerAitoff** : elija esta opción para los mapas polares o los mapas mundiales.</span><span class="sxs-lookup"><span data-stu-id="c33a2-123">**HammerAitoff** Choose this option for polar maps or world maps.</span></span>  
  
-   <span data-ttu-id="c33a2-124">**Wagner3** : elija esta opción para los mapas mundiales.</span><span class="sxs-lookup"><span data-stu-id="c33a2-124">**Wagner3** Choose this option for world maps.</span></span>  
  
-   <span data-ttu-id="c33a2-125">**Bonne** : elija esta opción para ver el mundo tal como él aparece en un atlas.</span><span class="sxs-lookup"><span data-stu-id="c33a2-125">**Bonne** Choose this option to view the world as it appears in an atlas.</span></span>  
  
 <span data-ttu-id="c33a2-126">**Opciones de salto de página**</span><span class="sxs-lookup"><span data-stu-id="c33a2-126">**Page break options**</span></span>  
 <span data-ttu-id="c33a2-127">Seleccione opciones para indicar la manera en que se ajusta el contenido a una página del informe.</span><span class="sxs-lookup"><span data-stu-id="c33a2-127">Select options to indicate how content is fitted to a report page.</span></span>  
  
 <span data-ttu-id="c33a2-128">**Opciones de límite**</span><span class="sxs-lookup"><span data-stu-id="c33a2-128">**Boundary options**</span></span>  
 <span data-ttu-id="c33a2-129">Especifique los límites inferior y superior de las coordenadas para controlar qué parte del mapa aparece en el informe.</span><span class="sxs-lookup"><span data-stu-id="c33a2-129">Specify the lower and upper boundaries for coordinates to control which part of the map appears in the report.</span></span>  
  
 <span data-ttu-id="c33a2-130">**X mínimo**</span><span class="sxs-lookup"><span data-stu-id="c33a2-130">**Minimum X**</span></span>  
 <span data-ttu-id="c33a2-131">El valor de X inferior.</span><span class="sxs-lookup"><span data-stu-id="c33a2-131">Lowest X value.</span></span> <span data-ttu-id="c33a2-132">Solo está disponible para **Planar** .</span><span class="sxs-lookup"><span data-stu-id="c33a2-132">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="c33a2-133">**X máximo**</span><span class="sxs-lookup"><span data-stu-id="c33a2-133">**Maximum X**</span></span>  
 <span data-ttu-id="c33a2-134">El valor de X superior.</span><span class="sxs-lookup"><span data-stu-id="c33a2-134">Highest X value.</span></span> <span data-ttu-id="c33a2-135">Solo está disponible para **Planar** .</span><span class="sxs-lookup"><span data-stu-id="c33a2-135">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="c33a2-136">**Y mínimo**</span><span class="sxs-lookup"><span data-stu-id="c33a2-136">**Minimum Y**</span></span>  
 <span data-ttu-id="c33a2-137">El valor de Y inferior.</span><span class="sxs-lookup"><span data-stu-id="c33a2-137">Lowest Y value.</span></span> <span data-ttu-id="c33a2-138">Solo está disponible para **Planar** .</span><span class="sxs-lookup"><span data-stu-id="c33a2-138">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="c33a2-139">**Y máximo**</span><span class="sxs-lookup"><span data-stu-id="c33a2-139">**Maximum Y**</span></span>  
 <span data-ttu-id="c33a2-140">El valor de Y superior.</span><span class="sxs-lookup"><span data-stu-id="c33a2-140">Highest Y value.</span></span> <span data-ttu-id="c33a2-141">Solo está disponible para **Planar** .</span><span class="sxs-lookup"><span data-stu-id="c33a2-141">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="c33a2-142">**Longitud mínima**</span><span class="sxs-lookup"><span data-stu-id="c33a2-142">**Minimum Longitude**</span></span>  
 <span data-ttu-id="c33a2-143">El valor de longitud inferior.</span><span class="sxs-lookup"><span data-stu-id="c33a2-143">Lowest longitude value.</span></span> <span data-ttu-id="c33a2-144">Solo está disponible para **Geographic** .</span><span class="sxs-lookup"><span data-stu-id="c33a2-144">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="c33a2-145">**Longitud máxima**</span><span class="sxs-lookup"><span data-stu-id="c33a2-145">**Maximum Longitude**</span></span>  
 <span data-ttu-id="c33a2-146">El valor de longitud superior.</span><span class="sxs-lookup"><span data-stu-id="c33a2-146">Highest longitude value.</span></span> <span data-ttu-id="c33a2-147">Solo está disponible para **Geographic** .</span><span class="sxs-lookup"><span data-stu-id="c33a2-147">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="c33a2-148">**Latitud mínima**</span><span class="sxs-lookup"><span data-stu-id="c33a2-148">**Minimum Latitude**</span></span>  
 <span data-ttu-id="c33a2-149">El valor de latitud inferior.</span><span class="sxs-lookup"><span data-stu-id="c33a2-149">Lowest latitude value.</span></span> <span data-ttu-id="c33a2-150">Solo está disponible para **Geographic** .</span><span class="sxs-lookup"><span data-stu-id="c33a2-150">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="c33a2-151">**Latitud máxima**</span><span class="sxs-lookup"><span data-stu-id="c33a2-151">**Maximum Latitude**</span></span>  
 <span data-ttu-id="c33a2-152">El valor de latitud superior.</span><span class="sxs-lookup"><span data-stu-id="c33a2-152">Highest latitude value.</span></span> <span data-ttu-id="c33a2-153">Solo está disponible para **Geographic** .</span><span class="sxs-lookup"><span data-stu-id="c33a2-153">Available for **Geographic** only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c33a2-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c33a2-154">See Also</span></span>  
 [<span data-ttu-id="c33a2-155">Mapas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c33a2-155">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
