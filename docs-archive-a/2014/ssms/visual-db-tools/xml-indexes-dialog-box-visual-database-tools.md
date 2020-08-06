---
title: Cuadro de diálogo Índices XML (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.xmlindexes
ms.assetid: eef38310-4498-4ccc-bb77-5bbd1c7cc477
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1fb23a801a9129611c032fa1d659caf624088aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674482"
---
# <a name="xml-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="c6314-102">Índices XML (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c6314-102">XML Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="c6314-103">Utilice el cuadro de diálogo **Índices XML** para crear índices para las columnas de tipo de datos XML que no pueden indizarse utilizando el cuadro de diálogo **Índice y claves** .</span><span class="sxs-lookup"><span data-stu-id="c6314-103">Use the **XML Indexes** dialog box to create indexes for columns of the data type XML, which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="c6314-104">Cada columna XML puede tener más de un índice XML, pero el primero que se cree (principal) será la base de los otros (secundarios).</span><span class="sxs-lookup"><span data-stu-id="c6314-104">Each XML column can have more than one XML Index, but the first one created (primary) will be the basis of the others (secondary).</span></span> <span data-ttu-id="c6314-105">Si elimina el índice XML principal, también se eliminarán los índices secundarios.</span><span class="sxs-lookup"><span data-stu-id="c6314-105">If you delete the primary XML index, the secondary indexes will also be deleted.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c6314-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="c6314-106">Options</span></span>  
 <span data-ttu-id="c6314-107">**Índice XML seleccionado**</span><span class="sxs-lookup"><span data-stu-id="c6314-107">**Selected XML Index**</span></span>  
 <span data-ttu-id="c6314-108">Enumera los índices XML existentes.</span><span class="sxs-lookup"><span data-stu-id="c6314-108">Lists existing XML indexes.</span></span> <span data-ttu-id="c6314-109">Selecciónelo para mostrar sus propiedades en la cuadrícula que aparece a la derecha.</span><span class="sxs-lookup"><span data-stu-id="c6314-109">Select to show its properties in the grid to the right.</span></span> <span data-ttu-id="c6314-110">Si la lista está vacía, no se ha definido ninguna para la tabla.</span><span class="sxs-lookup"><span data-stu-id="c6314-110">If the list is empty, none have been defined for the table.</span></span>  
  
 <span data-ttu-id="c6314-111">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="c6314-111">**Add**</span></span>  
 <span data-ttu-id="c6314-112">Crea un nuevo índice XML.</span><span class="sxs-lookup"><span data-stu-id="c6314-112">Create a new XML index.</span></span>  
  
 <span data-ttu-id="c6314-113">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="c6314-113">**Delete**</span></span>  
 <span data-ttu-id="c6314-114">Elimina el índice XML seleccionado en la lista **Índice XML seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="c6314-114">Delete XML index selected in the **Selected XML Index** list.</span></span> <span data-ttu-id="c6314-115">Si elimina el índice XML principal, se le notificará que con ello eliminará también todos los índices secundarios y que puede elegir entre continuar o cancelar la acción.</span><span class="sxs-lookup"><span data-stu-id="c6314-115">If you delete the primary XML index, you will be notified that this will delete all secondary ones as well, and you can either continue or cancel the action.</span></span>  
  
 <span data-ttu-id="c6314-116">**Categoría General**</span><span class="sxs-lookup"><span data-stu-id="c6314-116">**General Category**</span></span>  
 <span data-ttu-id="c6314-117">Expandido, muestra los campos de propiedades de **Columnas**, **Principal**y **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="c6314-117">When expanded, shows the property fields for **Columns**, **Is Primary**, and **Type**.</span></span>  
  
 <span data-ttu-id="c6314-118">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="c6314-118">**Columns**</span></span>  
 <span data-ttu-id="c6314-119">Indica que el orden del índice es ascendente.</span><span class="sxs-lookup"><span data-stu-id="c6314-119">Shows that this index is sorted in ascending order.</span></span>  
  
 <span data-ttu-id="c6314-120">**Principal**</span><span class="sxs-lookup"><span data-stu-id="c6314-120">**Is Primary**</span></span>  
 <span data-ttu-id="c6314-121">Indica si es el índice es principal.</span><span class="sxs-lookup"><span data-stu-id="c6314-121">Indicates whether this is the primary index.</span></span> <span data-ttu-id="c6314-122">El primer índice XML creado en la columna será la base de los otros.</span><span class="sxs-lookup"><span data-stu-id="c6314-122">The first XML index created on the column will be the basis of the others.</span></span>  
  
 <span data-ttu-id="c6314-123">**Nombre de referencia principal**</span><span class="sxs-lookup"><span data-stu-id="c6314-123">**Primary reference name**</span></span>  
 <span data-ttu-id="c6314-124">Muestra el nombre del índice principal si este índice es secundario.</span><span class="sxs-lookup"><span data-stu-id="c6314-124">Shows the name of the primary index if this is a secondary index.</span></span> <span data-ttu-id="c6314-125">Solo está disponible si éste índice es secundario.</span><span class="sxs-lookup"><span data-stu-id="c6314-125">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="c6314-126">**Tipo secundario**</span><span class="sxs-lookup"><span data-stu-id="c6314-126">**Secondary type**</span></span>  
 <span data-ttu-id="c6314-127">Muestra el tipo de índice secundario.</span><span class="sxs-lookup"><span data-stu-id="c6314-127">Shows the type of secondary index.</span></span> <span data-ttu-id="c6314-128">Solo está disponible si éste índice es secundario.</span><span class="sxs-lookup"><span data-stu-id="c6314-128">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="c6314-129">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c6314-129">**Type**</span></span>  
 <span data-ttu-id="c6314-130">Indica si el índice es XML.</span><span class="sxs-lookup"><span data-stu-id="c6314-130">Shows that this is an XML index.</span></span>  
  
 <span data-ttu-id="c6314-131">**Categoría Identidad**</span><span class="sxs-lookup"><span data-stu-id="c6314-131">**Identity Category**</span></span>  
 <span data-ttu-id="c6314-132">Expandido, muestra los campos de propiedades **Nombre** y **Descripción** .</span><span class="sxs-lookup"><span data-stu-id="c6314-132">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="c6314-133">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c6314-133">**Name**</span></span>  
 <span data-ttu-id="c6314-134">Muestra el nombre del índice XML.</span><span class="sxs-lookup"><span data-stu-id="c6314-134">Shows the name of the XML index.</span></span> <span data-ttu-id="c6314-135">Cuando se crea un nuevo índice o una nueva clave, aparece un nombre predeterminado que se genera a partir de la tabla de la ventana que está activa en el Diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="c6314-135">When a new one is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="c6314-136">Puede cambiar el nombre en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="c6314-136">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="c6314-137">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c6314-137">**Description**</span></span>  
 <span data-ttu-id="c6314-138">Describe el índice.</span><span class="sxs-lookup"><span data-stu-id="c6314-138">Describe the index.</span></span> <span data-ttu-id="c6314-139">Para escribir una descripción más detallada, haga clic en **Descripción** y después en el botón de puntos suspensivos ( **...** ) situado a la derecha del campo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c6314-139">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="c6314-140">De este modo, obtendrá un área más grande en la que escribir el texto.</span><span class="sxs-lookup"><span data-stu-id="c6314-140">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="c6314-141">**Categoría Diseñador de tablas**</span><span class="sxs-lookup"><span data-stu-id="c6314-141">**Table Designer Category**</span></span>  
 <span data-ttu-id="c6314-142">Expandido, muestra información sobre las propiedades de este índice XML.</span><span class="sxs-lookup"><span data-stu-id="c6314-142">When expanded, shows information about the properties of this XML index.</span></span>  
  
 <span data-ttu-id="c6314-143">**Especificación de relleno**</span><span class="sxs-lookup"><span data-stu-id="c6314-143">**Fill Specification**</span></span>  
 <span data-ttu-id="c6314-144">Expandido, muestra información sobre **Factor de relleno** y **Rellenar índice**.</span><span class="sxs-lookup"><span data-stu-id="c6314-144">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="c6314-145">**Factor de relleno**</span><span class="sxs-lookup"><span data-stu-id="c6314-145">**Fill Factor**</span></span>  
 <span data-ttu-id="c6314-146">Especifica qué porcentaje de la página de índice puede rellenar el sistema.</span><span class="sxs-lookup"><span data-stu-id="c6314-146">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="c6314-147">Una vez completada una página, el sistema debe dividirla si se agregan nuevos datos, lo que afecta al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c6314-147">Once a page is full, the system must split the page if new data is added, which impairs performance.</span></span>  
  
-   <span data-ttu-id="c6314-148">El valor 100 significa que las páginas estarán llenas y que utilizarán el menor volumen posible de espacio de almacenamiento, pero es la opción menos eficiente.</span><span class="sxs-lookup"><span data-stu-id="c6314-148">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="c6314-149">Este valor debe utilizarse únicamente cuando no se van a efectuar cambios en los datos, como por ejemplo, en una tabla de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c6314-149">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="c6314-150">Un valor más bajo deja más espacio vacío en las páginas de datos, lo que reduce la necesidad de dividir las páginas de datos cuando los índices aumentan,</span><span class="sxs-lookup"><span data-stu-id="c6314-150">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="c6314-151">pero requiere más espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="c6314-151">However, it requires more storage space.</span></span> <span data-ttu-id="c6314-152">Este valor es más adecuado cuando se vayan a producir cambios en los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c6314-152">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="c6314-153">**Rellenar índice**</span><span class="sxs-lookup"><span data-stu-id="c6314-153">**Pad Index**</span></span>  
 <span data-ttu-id="c6314-154">Se proporciona a las páginas de este índice el mismo porcentaje de espacio vacío (relleno) especificado en **Factor de relleno**.</span><span class="sxs-lookup"><span data-stu-id="c6314-154">Provide pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="c6314-155">**Está deshabilitado**</span><span class="sxs-lookup"><span data-stu-id="c6314-155">**Is Disabled**</span></span>  
 <span data-ttu-id="c6314-156">Especifica si este índice está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="c6314-156">Specify whether this index is disabled.</span></span> <span data-ttu-id="c6314-157">Los índices deshabilitados no admiten búsquedas ni se actualizan al agregar nuevos elementos a la tabla.</span><span class="sxs-lookup"><span data-stu-id="c6314-157">Disabled indexes do not support searches, nor do they get updated when new items are added to the table.</span></span> <span data-ttu-id="c6314-158">Puede mejorar el rendimiento de las actualizaciones e inserciones masivas deshabilitando un índice.</span><span class="sxs-lookup"><span data-stu-id="c6314-158">You can improve performance for bulk inserts and updates by disabling an index.</span></span>  
  
 <span data-ttu-id="c6314-159">**Bloqueos de página permitidos**</span><span class="sxs-lookup"><span data-stu-id="c6314-159">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="c6314-160">Especifique si se permite el bloqueo de páginas en este índice.</span><span class="sxs-lookup"><span data-stu-id="c6314-160">Specify whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="c6314-161">Permitir o denegar el bloqueo de página afecta al rendimiento de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c6314-161">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="c6314-162">**Volver a calcular estadísticas**</span><span class="sxs-lookup"><span data-stu-id="c6314-162">**Re-compute Statistics**</span></span>  
 <span data-ttu-id="c6314-163">Calcula las nuevas estadísticas cuando se crea el índice.</span><span class="sxs-lookup"><span data-stu-id="c6314-163">Compute new statistics when the index is created.</span></span> <span data-ttu-id="c6314-164">Al volver a calcular las estadísticas, se ralentiza la generación de índices, pero suele mejorar el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="c6314-164">Re-computing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="c6314-165">**Bloqueos de fila permitidos**</span><span class="sxs-lookup"><span data-stu-id="c6314-165">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="c6314-166">Especifique si se permite el bloqueo de filas en este índice.</span><span class="sxs-lookup"><span data-stu-id="c6314-166">Specify whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="c6314-167">Permitir o denegar el bloqueo de fila afecta al rendimiento de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c6314-167">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6314-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6314-168">See Also</span></span>  
 [<span data-ttu-id="c6314-169">Crear índices XML</span><span class="sxs-lookup"><span data-stu-id="c6314-169">Create XML Indexes</span></span>](../../relational-databases/xml/create-xml-indexes.md)  
  
  
