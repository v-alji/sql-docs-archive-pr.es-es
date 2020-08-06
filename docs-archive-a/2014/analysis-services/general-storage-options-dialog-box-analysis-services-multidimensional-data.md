---
title: General (cuadro de diálogo Opciones de almacenamiento) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitiondesigner.partitionstoragesettings.setstorageoptions.storage.f1
ms.assetid: ee1fac79-ae15-4c3c-9a98-33db04388817
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0963b3536dc5156d3a89fc27d3fa6221a4df18e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671260"
---
# <a name="general-storage-options-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="6005f-102">General (cuadro de diálogo Opciones de almacenamiento) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="6005f-102">General (Storage Options Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="6005f-103">Utilice la pestaña **General** del cuadro de diálogo **Opciones de almacenamiento** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para definir los parámetros de configuración del modo de almacenamiento y del almacenamiento de caché automático para una dimensión, un cubo, un grupo de medida o una partición.</span><span class="sxs-lookup"><span data-stu-id="6005f-103">Use the **General** tab of the **Storage Options** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to set the storage mode and proactive caching settings for a dimension, cube, measure group, or partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6005f-104">Antes de modificar estos parámetros de configuración, debe estar familiarizado con la funcionalidad del modo de almacenamiento y del almacenamiento en caché automático.</span><span class="sxs-lookup"><span data-stu-id="6005f-104">You should be familiar with storage mode and proactive caching functionality before modifying these settings.</span></span> <span data-ttu-id="6005f-105">Para más información, vea [Almacenamiento en caché automático &#40;Particiones&#41;](multidimensional-models-olap-logical-cube-objects/partitions-proactive-caching.md).</span><span class="sxs-lookup"><span data-stu-id="6005f-105">For more information, see [Proactive Caching &#40;Partitions&#41;](multidimensional-models-olap-logical-cube-objects/partitions-proactive-caching.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6005f-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="6005f-106">Options</span></span>  
  
|<span data-ttu-id="6005f-107">Término</span><span class="sxs-lookup"><span data-stu-id="6005f-107">Term</span></span>|<span data-ttu-id="6005f-108">Definición</span><span class="sxs-lookup"><span data-stu-id="6005f-108">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="6005f-109">**Modo de almacenamiento**</span><span class="sxs-lookup"><span data-stu-id="6005f-109">**Storage mode**</span></span>|<span data-ttu-id="6005f-110">Seleccione el modo de almacenamiento que debe utilizarse para el objeto.</span><span class="sxs-lookup"><span data-stu-id="6005f-110">Selects the storage mode to use for the object.</span></span><br /><br /> <span data-ttu-id="6005f-111">**MOLAP**</span><span class="sxs-lookup"><span data-stu-id="6005f-111">**MOLAP**</span></span><br /> <span data-ttu-id="6005f-112">El objeto utiliza almacenamiento OLAP multidimensional (MOLAP).</span><span class="sxs-lookup"><span data-stu-id="6005f-112">The object uses multidimensional OLAP (MOLAP) storage.</span></span><br /><br /> <span data-ttu-id="6005f-113">**HOLAP**</span><span class="sxs-lookup"><span data-stu-id="6005f-113">**HOLAP**</span></span><br /> <span data-ttu-id="6005f-114">El objeto utiliza almacenamiento OLAP híbrido (HOLAP).</span><span class="sxs-lookup"><span data-stu-id="6005f-114">The object uses hybrid OLAP (HOLAP) storage.</span></span><br /><br /> <span data-ttu-id="6005f-115">**ROLAP**</span><span class="sxs-lookup"><span data-stu-id="6005f-115">**ROLAP**</span></span><br /> <span data-ttu-id="6005f-116">El objeto utiliza almacenamiento OLAP relacional (ROLAP).</span><span class="sxs-lookup"><span data-stu-id="6005f-116">The object uses relational OLAP (ROLAP) storage.</span></span>|  
|<span data-ttu-id="6005f-117">**Habilita el almacenamiento en caché automático**</span><span class="sxs-lookup"><span data-stu-id="6005f-117">**Enable proactive caching**</span></span>|<span data-ttu-id="6005f-118">Habilitar el almacenamiento en caché automático.</span><span class="sxs-lookup"><span data-stu-id="6005f-118">Enables proactive caching.</span></span><br /><br /> <span data-ttu-id="6005f-119">Nota: Si no se selecciona esta opción, todas las opciones, excepto **Modo de almacenamiento**, quedarán deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="6005f-119">Note: If this option is not selected, all options except **Storage mode** are disabled.</span></span>|  
|<span data-ttu-id="6005f-120">**Actualizar la caché cuando los datos cambien**</span><span class="sxs-lookup"><span data-stu-id="6005f-120">**Update the cache when data changes**</span></span>|<span data-ttu-id="6005f-121">Utiliza el método de notificación seleccionado en la pestaña **Notificaciones** para actualizar la imagen MOLAP para el objeto siempre que se recibe una notificación.</span><span class="sxs-lookup"><span data-stu-id="6005f-121">Uses the notification method selected in the **Notifications** tab to update the MOLAP image for the object whenever a notification is received.</span></span> <span data-ttu-id="6005f-122">Para más información sobre la pestaña **Notificaciones**, vea [Notificaciones &#40;cuadro de diálogo Opciones de almacenamiento&#41; &#40;Analysis Services - Datos multidimensionales&#41;](notifications-storage-options-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="6005f-122">For more information about the **Notifications** tab, see [Notifications &#40;Storage Options Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](notifications-storage-options-dialog-analysis-services-multidimensional-data.md).</span></span><br /><br /> <span data-ttu-id="6005f-123">Nota: Esta opción está deshabilitada, a menos que se seleccione **Habilitar almacenamiento en caché automático** .</span><span class="sxs-lookup"><span data-stu-id="6005f-123">Note: This option is disabled unless **Enable proactive caching** is selected.</span></span>|  
|<span data-ttu-id="6005f-124">**Intervalo de latencia**</span><span class="sxs-lookup"><span data-stu-id="6005f-124">**Silence interval**</span></span>|<span data-ttu-id="6005f-125">Establece el intervalo mínimo y las unidades de tiempo en que el objeto no tiene ninguna actividad antes de que el almacenamiento en caché automático empiece a crear la nueva imagen MOLAP para el objeto.</span><span class="sxs-lookup"><span data-stu-id="6005f-125">Sets the minimum interval and units of time in which the object has no activity before proactive caching starts to create the new MOLAP image for the object.</span></span><br /><br /> <span data-ttu-id="6005f-126">Nota: Esta opción está deshabilitada, a menos que se seleccione **Actualizar la caché cuando los datos cambien** .</span><span class="sxs-lookup"><span data-stu-id="6005f-126">Note: This option is disabled unless **Update the cache when data changes** is selected.</span></span>|  
|<span data-ttu-id="6005f-127">**Reemplazo de intervalo de latencia**</span><span class="sxs-lookup"><span data-stu-id="6005f-127">**Silence override interval**</span></span>|<span data-ttu-id="6005f-128">Establece el intervalo máximo y las unidades de tiempo en que, tras recibir una notificación para el objeto, el almacenamiento en caché automático empieza a crear una nueva imagen MOLAP para el objeto, independientemente de la actividad actual del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6005f-128">Sets the maximum interval and units of time in which, after a notification is received for the object, proactive caching starts to create a new MOLAP image for the object, regardless of the current activity of the object.</span></span> <span data-ttu-id="6005f-129">Las notificaciones que se reciben tras alcanzar este intervalo no cancelan el proceso de creación de la imagen MOLAP desencadenado por este intervalo.</span><span class="sxs-lookup"><span data-stu-id="6005f-129">Notifications received after this interval has been reached do not cancel the MOLAP image process triggered by this interval.</span></span><br /><br /> <span data-ttu-id="6005f-130">Nota: Esta opción está deshabilitada, a menos que se seleccione **Actualizar la caché cuando los datos cambien** .</span><span class="sxs-lookup"><span data-stu-id="6005f-130">Note: This option is disabled unless **Update the cache when data changes** is selected.</span></span> <span data-ttu-id="6005f-131">Tenga en cuenta también que esta opción no debe establecerse si el **modo de almacenamiento** está establecido en **HOLAP**.</span><span class="sxs-lookup"><span data-stu-id="6005f-131">Also note that this option should not be set if **Storage mode** is set to **HOLAP**.</span></span>|  
|<span data-ttu-id="6005f-132">**Quitar caché no actualizada**</span><span class="sxs-lookup"><span data-stu-id="6005f-132">**Drop outdated cache**</span></span>|<span data-ttu-id="6005f-133">Especifica el período que transcurre entre el inicio del proceso de creación de una nueva caché MOLAP y la eliminación de la caché MOLAP existente.</span><span class="sxs-lookup"><span data-stu-id="6005f-133">Specifies the period between the start of creating a new MOLAP cache and the removal of the existing MOLAP cache.</span></span><br /><br /> <span data-ttu-id="6005f-134">Nota: Esta opción está deshabilitada, a menos que se seleccione **Habilitar almacenamiento en caché automático** .</span><span class="sxs-lookup"><span data-stu-id="6005f-134">Note: This option is disabled unless **Enable proactive caching** is selected.</span></span> <span data-ttu-id="6005f-135">Tenga en cuenta también que esta opción no debe establecerse si el **modo de almacenamiento** está establecido en HOLAP.</span><span class="sxs-lookup"><span data-stu-id="6005f-135">Also note that this option should not be set if **Storage mode** is set to HOLAP.</span></span>|  
|<span data-ttu-id="6005f-136">**Latency**</span><span class="sxs-lookup"><span data-stu-id="6005f-136">**Latency**</span></span>|<span data-ttu-id="6005f-137">Selecciona el intervalo y las unidades de tiempo para el período que transcurre entre el inicio del proceso de creación de una nueva caché MOLAP y la eliminación de la caché MOLAP existente.</span><span class="sxs-lookup"><span data-stu-id="6005f-137">Selects the interval and units of time for the period between the start of creating a new MOLAP cache and the removal of the existing MOLAP cache.</span></span><br /><br /> <span data-ttu-id="6005f-138">Nota: Esta opción está deshabilitada, a menos que se seleccione **Quitar caché no actualizada** .</span><span class="sxs-lookup"><span data-stu-id="6005f-138">Note: This option is disabled unless **Drop outdated cache** is selected.</span></span> <span data-ttu-id="6005f-139">Tenga en cuenta también que esta opción no debe establecerse si el **modo de almacenamiento** está establecido en **HOLAP**.</span><span class="sxs-lookup"><span data-stu-id="6005f-139">Also note that this option should not be set if **Storage mode** is set to **HOLAP**.</span></span>|  
|<span data-ttu-id="6005f-140">**Actualizar la caché periódicamente**</span><span class="sxs-lookup"><span data-stu-id="6005f-140">**Update the cache periodically**</span></span>|<span data-ttu-id="6005f-141">Actualiza la imagen MOLAP de forma periódica, independientemente de las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="6005f-141">Updates the MOLAP image on a regular basis, regardless of notification.</span></span><br /><br /> <span data-ttu-id="6005f-142">Nota: Esta opción está deshabilitada, a menos que se seleccione **Habilitar almacenamiento en caché automático** .</span><span class="sxs-lookup"><span data-stu-id="6005f-142">Note: This option is disabled unless **Enable proactive caching** is selected.</span></span> <span data-ttu-id="6005f-143">Tenga en cuenta también que esta opción no debe establecerse si el **modo de almacenamiento** está establecido en **HOLAP**.</span><span class="sxs-lookup"><span data-stu-id="6005f-143">Also note that this option should not be set if **Storage mode** is set to **HOLAP**.</span></span>|  
|<span data-ttu-id="6005f-144">**Volver a generar intervalo**</span><span class="sxs-lookup"><span data-stu-id="6005f-144">**Rebuild interval**</span></span>|<span data-ttu-id="6005f-145">Selecciona el intervalo y las unidades de tiempo para el período que, después de crear una nueva imagen MOLAP, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] inicia de nuevo el proceso de imagen MOLAP para el objeto, independientemente de la notificación.</span><span class="sxs-lookup"><span data-stu-id="6005f-145">Selects the interval and units of time for the period that, after a new MOLAP image is created, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] starts the MOLAP image process again for the object, regardless of notification.</span></span> <span data-ttu-id="6005f-146">Las notificaciones que se reciben tras alcanzar este intervalo no cancelan el proceso de creación de la imagen MOLAP desencadenado por este intervalo.</span><span class="sxs-lookup"><span data-stu-id="6005f-146">Notifications received after this interval has been reached do not cancel the MOLAP image process triggered by this interval.</span></span><br /><br /> <span data-ttu-id="6005f-147">Nota: Esta opción está deshabilitada, a menos que se seleccione **Actualizar la caché periódicamente** .</span><span class="sxs-lookup"><span data-stu-id="6005f-147">Note: This option is disabled unless **Update the cache periodically** is selected.</span></span> <span data-ttu-id="6005f-148">Tenga en cuenta también que esta opción no debe establecerse si el **modo de almacenamiento** está establecido en **HOLAP**.</span><span class="sxs-lookup"><span data-stu-id="6005f-148">Also note that this option should not be set if **Storage mode** is set to **HOLAP**.</span></span>|  
|<span data-ttu-id="6005f-149">**Poner en línea inmediatamente**</span><span class="sxs-lookup"><span data-stu-id="6005f-149">**Bring online immediately**</span></span>|<span data-ttu-id="6005f-150">Coloca los objetos en línea de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="6005f-150">Brings objects online immediately.</span></span> <span data-ttu-id="6005f-151">Si se establece esta opción, los objetos utilizan el almacenamiento ROLAP subyacente para resolver las entradas mientras se genera de nuevo la caché MOLAP.</span><span class="sxs-lookup"><span data-stu-id="6005f-151">If this option is set, objects use the underlying ROLAP storage for resolving queries while the MOLAP cache is being rebuilt.</span></span> <span data-ttu-id="6005f-152">Si no se establece esta opción, los objetos solo pasan a estar en línea de nuevo una vez que se ha completado la caché MOLAP para el objeto.</span><span class="sxs-lookup"><span data-stu-id="6005f-152">If this option is not set, objects are brought online only after the MOLAP cache for the object is complete.</span></span>|  
|<span data-ttu-id="6005f-153">**Habilitar agregaciones ROLAP**</span><span class="sxs-lookup"><span data-stu-id="6005f-153">**Enable ROLAP aggregations**</span></span>|<span data-ttu-id="6005f-154">Utiliza vistas materializadas del origen de datos subyacente para almacenar agregaciones.</span><span class="sxs-lookup"><span data-stu-id="6005f-154">Uses materialized views on the underlying data source to store aggregations.</span></span><br /><br /> <span data-ttu-id="6005f-155">Nota: Si el origen de datos subyacente no admite vistas materializadas, se producirá un error cuando se procese el objeto.</span><span class="sxs-lookup"><span data-stu-id="6005f-155">Note: If the underlying data source does not support materialized views, an error will occur when the object is processed.</span></span>|  
|<span data-ttu-id="6005f-156">**Aplicar configuración a dimensiones**</span><span class="sxs-lookup"><span data-stu-id="6005f-156">**Apply settings to dimensions**</span></span>|<span data-ttu-id="6005f-157">Aplica los parámetros de configuración del modo de almacenamiento y del almacenamiento en caché automático a las dimensiones asociadas.</span><span class="sxs-lookup"><span data-stu-id="6005f-157">Applies storage mode and proactive caching settings to associated dimensions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6005f-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6005f-158">See Also</span></span>  
 <span data-ttu-id="6005f-159">[Cuadro de diálogo Opciones de almacenamiento &#40;Analysis Services de datos multidimensionales&#41;](storage-options-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="6005f-159">[Storage Options Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](storage-options-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="6005f-160">Notificaciones &#40;cuadro de diálogo Opciones de almacenamiento&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="6005f-160">Notifications &#40;Storage Options Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](notifications-storage-options-dialog-analysis-services-multidimensional-data.md)  
  
  