---
title: Cuadro de diálogo Índices espaciales (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.spatialindexes
ms.assetid: 4d84239a-68c7-4aa2-8602-2b51dd07260f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e401b7f93a8376b1c6dc0c75ca29cbdc8a39863d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672349"
---
# <a name="spatial-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="e726b-102">Cuadro de diálogo Índices espaciales (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="e726b-102">Spatial Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="e726b-103">Use el cuadro de diálogo **Índices espaciales** para crear índices para las columnas del tipo de datos **geometry** o **geography** (*columnas espaciales*) que no pueden indizarse mediante el cuadro de diálogo **Índice y claves** .</span><span class="sxs-lookup"><span data-stu-id="e726b-103">Use the **Spatial Indexes** dialog box to create indexes for columns of the **geometry** or **geography** data type (*spatial columns*), which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="e726b-104">Cada columna espacial puede tener más de un índice espacial, pero se deben crear de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="e726b-104">Each spatial column can have more than one spatial index, but they must be created one at a time.</span></span>  
  
 <span data-ttu-id="e726b-105">Para más información sobre las restricciones de la creación de índices espaciales, consulte [Información general sobre los índices espaciales](../../relational-databases/spatial/spatial-indexes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e726b-105">For information about restrictions on spatial index creation, see [Spatial Indexes Overview](../../relational-databases/spatial/spatial-indexes-overview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e726b-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="e726b-106">Options</span></span>  
 <span data-ttu-id="e726b-107">**Índice espacial seleccionado**</span><span class="sxs-lookup"><span data-stu-id="e726b-107">**Selected Spatial Index**</span></span>  
 <span data-ttu-id="e726b-108">Enumera los índices espaciales existentes.</span><span class="sxs-lookup"><span data-stu-id="e726b-108">Lists existing spatial indexes.</span></span> <span data-ttu-id="e726b-109">Seleccione un índice para mostrar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="e726b-109">Select an index to show its properties.</span></span> <span data-ttu-id="e726b-110">Si la lista está vacía, no se han definido índices espaciales para la tabla.</span><span class="sxs-lookup"><span data-stu-id="e726b-110">If the list is empty, no spatial indexes have been defined for the table.</span></span>  
  
 <span data-ttu-id="e726b-111">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="e726b-111">**Add**</span></span>  
 <span data-ttu-id="e726b-112">Crea un nuevo índice espacial.</span><span class="sxs-lookup"><span data-stu-id="e726b-112">Creates a new spatial index.</span></span>  
  
 <span data-ttu-id="e726b-113">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="e726b-113">**Delete**</span></span>  
 <span data-ttu-id="e726b-114">Elimina el índice espacial seleccionado en la lista **Índice espacial seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="e726b-114">Deletes the spatial index selected in the **Selected Spatial Index** list.</span></span>  
  
 <span data-ttu-id="e726b-115">**Celdas por objeto**</span><span class="sxs-lookup"><span data-stu-id="e726b-115">**Cells Per Object**</span></span>  
 <span data-ttu-id="e726b-116">Indica el número de celdas por objeto de teselación que se pueden usar para un único objeto espacial en el índice.</span><span class="sxs-lookup"><span data-stu-id="e726b-116">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="e726b-117">Este número puede ser un entero comprendido entre 1 y 8192, ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="e726b-117">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="e726b-118">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="e726b-118">The default is 16.</span></span>  
  
 <span data-ttu-id="e726b-119">Si un objeto abarca más celdas de las especificadas mediante *n*, la indización usa tantas celdas como sean necesarias para proporcionar una teselación de nivel superior completa.</span><span class="sxs-lookup"><span data-stu-id="e726b-119">If an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="e726b-120">En tales casos, un objeto podría recibir más celdas de las especificadas.</span><span class="sxs-lookup"><span data-stu-id="e726b-120">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="e726b-121">En este caso, el número máximo es la cantidad de celdas generadas por la cuadrícula de nivel superior, que depende de la densidad de **Nivel 1** .</span><span class="sxs-lookup"><span data-stu-id="e726b-121">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
 <span data-ttu-id="e726b-122">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="e726b-122">**Columns**</span></span>  
 <span data-ttu-id="e726b-123">Indica el nombre de la columna y el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="e726b-123">Indicates the column name and sort order.</span></span>  
  
 <span data-ttu-id="e726b-124">**IsSpatialIndex**</span><span class="sxs-lookup"><span data-stu-id="e726b-124">**IsSpatialIndex**</span></span>  
 <span data-ttu-id="e726b-125">Indica que se ha seleccionado un índice espacial.</span><span class="sxs-lookup"><span data-stu-id="e726b-125">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="e726b-126">**Nivel 1**</span><span class="sxs-lookup"><span data-stu-id="e726b-126">**Level 1**</span></span>  
 <span data-ttu-id="e726b-127">Indica la densidad de la cuadrícula del primer nivel (superior).</span><span class="sxs-lookup"><span data-stu-id="e726b-127">Indicates the density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="e726b-128">**Nivel 2**</span><span class="sxs-lookup"><span data-stu-id="e726b-128">**Level 2**</span></span>  
 <span data-ttu-id="e726b-129">Indica la densidad de la cuadrícula del segundo nivel.</span><span class="sxs-lookup"><span data-stu-id="e726b-129">Indicates the density of the second-level grid.</span></span>  
  
 <span data-ttu-id="e726b-130">**Nivel 3**</span><span class="sxs-lookup"><span data-stu-id="e726b-130">**Level 3**</span></span>  
 <span data-ttu-id="e726b-131">Indica la densidad de la cuadrícula del tercer nivel.</span><span class="sxs-lookup"><span data-stu-id="e726b-131">Indicates the density of the third-level grid.</span></span>  
  
 <span data-ttu-id="e726b-132">**Nivel 4**</span><span class="sxs-lookup"><span data-stu-id="e726b-132">**Level 4**</span></span>  
 <span data-ttu-id="e726b-133">Indica la densidad de la cuadrícula del cuarto nivel.</span><span class="sxs-lookup"><span data-stu-id="e726b-133">Indicates the density of the fourth-level grid.</span></span>  
  
 <span data-ttu-id="e726b-134">**Esquema de teselación**</span><span class="sxs-lookup"><span data-stu-id="e726b-134">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="e726b-135">Indica el esquema de teselación:</span><span class="sxs-lookup"><span data-stu-id="e726b-135">Indicates the tessellation scheme:</span></span>  
  
 <span data-ttu-id="e726b-136">Opciones de la columna**Geometría** :</span><span class="sxs-lookup"><span data-stu-id="e726b-136">**Geometry** column options:</span></span>  
  
-   <span data-ttu-id="e726b-137">**Cuadrícula de geometría** para una columna de geometría</span><span class="sxs-lookup"><span data-stu-id="e726b-137">**Geometry grid** for a geometry column</span></span>  
  
-   <span data-ttu-id="e726b-138">**Cuadrícula de geografía** para una columna de geografía</span><span class="sxs-lookup"><span data-stu-id="e726b-138">**Geography grid** for a geography column</span></span>  
  
 <span data-ttu-id="e726b-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e726b-139">**Type**</span></span>  
 <span data-ttu-id="e726b-140">Indica que se ha seleccionado un índice espacial.</span><span class="sxs-lookup"><span data-stu-id="e726b-140">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="e726b-141">**X máxima**</span><span class="sxs-lookup"><span data-stu-id="e726b-141">**X-max**</span></span>  
 <span data-ttu-id="e726b-142">Especifica la coordenada X de la esquina superior derecha del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="e726b-142">Specifies the x-coordinate of the upper-right corner of the bounding box.</span></span> <span data-ttu-id="e726b-143">Esta propiedad está atenuada si el **Esquema de teselación** es **Cuadrícula de geografía**.</span><span class="sxs-lookup"><span data-stu-id="e726b-143">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="e726b-144">**X mínima**</span><span class="sxs-lookup"><span data-stu-id="e726b-144">**X-min**</span></span>  
 <span data-ttu-id="e726b-145">Especifica la coordenada X de la esquina inferior izquierda del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="e726b-145">Specifies the x-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="e726b-146">Esta propiedad está atenuada si el **Esquema de teselación** es **Cuadrícula de geografía**.</span><span class="sxs-lookup"><span data-stu-id="e726b-146">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="e726b-147">**Y máxima**</span><span class="sxs-lookup"><span data-stu-id="e726b-147">**Y-max**</span></span>  
 <span data-ttu-id="e726b-148">Especifica la coordenada y de la esquina superior derecha del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="e726b-148">Specifies the y-coordinate of upper-right corner of the bounding box.</span></span> <span data-ttu-id="e726b-149">Esta propiedad está atenuada si el **Esquema de teselación** es **Cuadrícula de geografía**.</span><span class="sxs-lookup"><span data-stu-id="e726b-149">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="e726b-150">**Y mínima**</span><span class="sxs-lookup"><span data-stu-id="e726b-150">**Y-min**</span></span>  
 <span data-ttu-id="e726b-151">Especifica la coordenada Y de la esquina inferior izquierda del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="e726b-151">Specifies the y-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="e726b-152">Esta propiedad está atenuada si el **Esquema de teselación** es **Cuadrícula de geografía**.</span><span class="sxs-lookup"><span data-stu-id="e726b-152">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="e726b-153">**Identidad**</span><span class="sxs-lookup"><span data-stu-id="e726b-153">**Identity**</span></span>  
 <span data-ttu-id="e726b-154">Expandido, muestra los campos de propiedades **Nombre** y **Descripción** .</span><span class="sxs-lookup"><span data-stu-id="e726b-154">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="e726b-155">**(Nombre)**</span><span class="sxs-lookup"><span data-stu-id="e726b-155">**(Name)**</span></span>  
 <span data-ttu-id="e726b-156">Muestra el nombre del índice espacial.</span><span class="sxs-lookup"><span data-stu-id="e726b-156">Shows the name of the spatial index.</span></span> <span data-ttu-id="e726b-157">Cuando se crea un nuevo índice, aparece un nombre predeterminado que se genera a partir de la tabla de la ventana que está activa en el Diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="e726b-157">When a new index is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="e726b-158">Puede cambiar el nombre en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="e726b-158">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="e726b-159">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e726b-159">**Description**</span></span>  
 <span data-ttu-id="e726b-160">Describe el índice.</span><span class="sxs-lookup"><span data-stu-id="e726b-160">Describes the index.</span></span> <span data-ttu-id="e726b-161">Para escribir una descripción más detallada, haga clic en **Descripción** y después en el botón de puntos suspensivos ( **...** ) situado a la derecha del campo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="e726b-161">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="e726b-162">De este modo, obtendrá un área más grande en la que escribir el texto.</span><span class="sxs-lookup"><span data-stu-id="e726b-162">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="e726b-163">**Categoría Diseñador de tablas**</span><span class="sxs-lookup"><span data-stu-id="e726b-163">**Table Designer Category**</span></span>  
 <span data-ttu-id="e726b-164">Expandido, muestra información sobre las propiedades de este índice espacial.</span><span class="sxs-lookup"><span data-stu-id="e726b-164">When expanded, shows information about the properties of this spatial index.</span></span>  
  
 <span data-ttu-id="e726b-165">**Especificación de relleno**</span><span class="sxs-lookup"><span data-stu-id="e726b-165">**Fill Specification**</span></span>  
 <span data-ttu-id="e726b-166">Expandido, muestra información sobre **Factor de relleno** y **Rellenar índice**.</span><span class="sxs-lookup"><span data-stu-id="e726b-166">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="e726b-167">**Factor de relleno**</span><span class="sxs-lookup"><span data-stu-id="e726b-167">**Fill Factor**</span></span>  
 <span data-ttu-id="e726b-168">Especifica qué porcentaje de la página de índice puede rellenar el sistema.</span><span class="sxs-lookup"><span data-stu-id="e726b-168">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="e726b-169">Cuando una página está llena, si se agregan datos nuevos, el sistema debe dividirla, lo que perjudica al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e726b-169">When a page is full, if new data is added, the system must split the page, which impairs performance.</span></span>  
  
-   <span data-ttu-id="e726b-170">El valor 100 significa que las páginas estarán llenas y que utilizarán el menor volumen posible de espacio de almacenamiento, pero es la opción menos eficiente.</span><span class="sxs-lookup"><span data-stu-id="e726b-170">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="e726b-171">Este valor debe utilizarse únicamente cuando no se van a efectuar cambios en los datos, como por ejemplo, en una tabla de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="e726b-171">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="e726b-172">Un valor más bajo deja más espacio vacío en las páginas de datos, lo que reduce la necesidad de dividir las páginas de datos cuando los índices aumentan,</span><span class="sxs-lookup"><span data-stu-id="e726b-172">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="e726b-173">pero requiere más espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e726b-173">However, it requires more storage space.</span></span> <span data-ttu-id="e726b-174">Este valor es más adecuado cuando se vayan a producir cambios en los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e726b-174">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="e726b-175">**Rellenar índice**</span><span class="sxs-lookup"><span data-stu-id="e726b-175">**Pad Index**</span></span>  
 <span data-ttu-id="e726b-176">Proporciona a las páginas de este índice el mismo porcentaje de espacio vacío (relleno) especificado en **Factor de relleno**.</span><span class="sxs-lookup"><span data-stu-id="e726b-176">Provides pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="e726b-177">**Bloqueos de página permitidos**</span><span class="sxs-lookup"><span data-stu-id="e726b-177">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="e726b-178">Especifica si se permite el bloqueo de páginas en este índice.</span><span class="sxs-lookup"><span data-stu-id="e726b-178">Specifies whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="e726b-179">Permitir o denegar el bloqueo de página afecta al rendimiento de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e726b-179">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="e726b-180">**Volver a calcular estadísticas**</span><span class="sxs-lookup"><span data-stu-id="e726b-180">**Re-compute  Statistics**</span></span>  
 <span data-ttu-id="e726b-181">Especifica si se deben calcular estadísticas nuevas cuando se crea el índice.</span><span class="sxs-lookup"><span data-stu-id="e726b-181">Specifies whether to compute new statistics when the index is created.</span></span> <span data-ttu-id="e726b-182">Al volver a calcular las estadísticas, se ralentiza la generación de índices, pero suele mejorar el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="e726b-182">Recomputing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="e726b-183">**Bloqueos de fila permitidos**</span><span class="sxs-lookup"><span data-stu-id="e726b-183">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="e726b-184">Especifica si se permite el bloqueo de filas en este índice.</span><span class="sxs-lookup"><span data-stu-id="e726b-184">Specifies whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="e726b-185">Permitir o denegar el bloqueo de fila afecta al rendimiento de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e726b-185">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e726b-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e726b-186">See Also</span></span>  
 [<span data-ttu-id="e726b-187">Información general sobre los índices espaciales</span><span class="sxs-lookup"><span data-stu-id="e726b-187">Spatial Indexes Overview</span></span>](../../relational-databases/spatial/spatial-indexes-overview.md)  
  
  
