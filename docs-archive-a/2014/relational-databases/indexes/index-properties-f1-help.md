---
title: Propiedades del índice (Ayuda F1) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.storage.f1
- sql12.swb.indexproperties.columns.f1
- sql12.swb.indexproperties.partitions.f1
- sql12.swb.indexproperties.general.f1
- sql12.swb.indexproperties.filter.f1
- sql12.swb.indexproperties.options.f1
- sql12.swb.indexproperties.spatial.f1
ms.assetid: 45efd81a-3796-4b04-b0cc-f3deec94c733
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 390a63d21dc72e052017f2d30b061d71de863bc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750941"
---
# <a name="index-properties-f1-help"></a><span data-ttu-id="ac381-102">Propiedades del índice (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="ac381-102">Index Properties F1 Help</span></span>
  <span data-ttu-id="ac381-103">Las secciones de este tema hacen referencia a las distintas propiedades de índice disponibles mediante cuadros de diálogo de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac381-103">The sections in this topic refer to various index properties that are available by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialogs.</span></span>  
  
 <span data-ttu-id="ac381-104">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="ac381-104">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="ac381-105">Propiedades del índice (página General)</span><span class="sxs-lookup"><span data-stu-id="ac381-105">Index Properties General Page</span></span>](#General)  
  
 [<span data-ttu-id="ac381-106">Cuadro de diálogo Seleccionar columnas de (índice)</span><span class="sxs-lookup"><span data-stu-id="ac381-106">Select (Index) Columns Dialog Box</span></span>](#Columns)  
  
 [<span data-ttu-id="ac381-107">Propiedades del índice (página Almacenamiento)</span><span class="sxs-lookup"><span data-stu-id="ac381-107">Index Properties Storage Page</span></span>](#Storage)  
  
 [<span data-ttu-id="ac381-108">Propiedades del índice (página Espacial)</span><span class="sxs-lookup"><span data-stu-id="ac381-108">Index Properties Spatial Page</span></span>](#Spatial)  
  
 [<span data-ttu-id="ac381-109">Propiedades del índice (página Filtro)</span><span class="sxs-lookup"><span data-stu-id="ac381-109">Index Properties Filter Page</span></span>](#Filter)  
  
##  <a name="index-properties-general-page"></a><a name="General"></a> <span data-ttu-id="ac381-110">Propiedades del índice (página General)</span><span class="sxs-lookup"><span data-stu-id="ac381-110">Index Properties General Page</span></span>  
 <span data-ttu-id="ac381-111">Use la página General para ver o modificar las propiedades del índice para la tabla o vista seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ac381-111">Use the General page to view or modify index properties for the selected table or view.</span></span> <span data-ttu-id="ac381-112">Las opciones para cada página pueden cambiar según el tipo de índice seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ac381-112">The options for each page may change based on the type of index selected.</span></span>  
  
 <span data-ttu-id="ac381-113">**Nombre de la tabla**</span><span class="sxs-lookup"><span data-stu-id="ac381-113">**Table name**</span></span>  
 <span data-ttu-id="ac381-114">Muestra el nombre de la tabla o vista en la que se ha creado el índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-114">Displays the name of the table or view that the index was created on.</span></span> <span data-ttu-id="ac381-115">Este campo es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="ac381-115">This field is read-only.</span></span> <span data-ttu-id="ac381-116">Para seleccionar una tabla diferente, cierre la página Propiedades del índice, seleccione la tabla correcta y vuelva a abrir la página Propiedades del índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-116">To select a different table, close the Index Properties page, select the correct table, and then open the Index Properties page again.</span></span>  
  
 <span data-ttu-id="ac381-117">Los índices espaciales no se pueden especificar en vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="ac381-117">Spatial indexes cannot be specified on indexed views.</span></span> <span data-ttu-id="ac381-118">Los índices espaciales solo se pueden definir para una tabla que tenga una clave principal.</span><span class="sxs-lookup"><span data-stu-id="ac381-118">Spatial indexes can be defined only for a table that has a primary key.</span></span> <span data-ttu-id="ac381-119">El número máximo de columnas de clave principal en la tabla es de 15.</span><span class="sxs-lookup"><span data-stu-id="ac381-119">The maximum number of primary key columns on the table is 15.</span></span> <span data-ttu-id="ac381-120">El tamaño por fila combinado de las columnas de clave principal está limitado a un valor máximo de 895 bytes.</span><span class="sxs-lookup"><span data-stu-id="ac381-120">The combined per-row size of the primary-key columns is limited to a maximum of 895 bytes.</span></span>  
  
 <span data-ttu-id="ac381-121">**Nombre del índice**</span><span class="sxs-lookup"><span data-stu-id="ac381-121">**Index name**</span></span>  
 <span data-ttu-id="ac381-122">Muestra el nombre del índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-122">Displays the name of the index.</span></span> <span data-ttu-id="ac381-123">Este campo es de solo lectura para un índice existente.</span><span class="sxs-lookup"><span data-stu-id="ac381-123">This field is read-only for an existing index.</span></span> <span data-ttu-id="ac381-124">Si está creando un nuevo índice, escriba el nombre del índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-124">When creating a new index, type the name of the index.</span></span>  
  
 <span data-ttu-id="ac381-125">**Tipo de índice**</span><span class="sxs-lookup"><span data-stu-id="ac381-125">**Index type**</span></span>  
 <span data-ttu-id="ac381-126">Indica el tipo de índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-126">Indicates the type of index.</span></span> <span data-ttu-id="ac381-127">Para los índices nuevos, indica el tipo de índice seleccionado al abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ac381-127">For new indexes, indicates the type of index selected when opening the dialog box.</span></span> <span data-ttu-id="ac381-128">Los índices pueden ser: **En clúster**, **No clúster**, **XML primario**, **XML secundario**, **Espacial**, **Almacén de columnas en clúster** o **Almacén de columnas no clúster**.</span><span class="sxs-lookup"><span data-stu-id="ac381-128">Indexes can be: **Clustered**, **Nonclustered**, **Primary XML**, **Secondary XML**, **Spatial**, **Clustered columnstore**, or **Nonclustered Columnstore**.</span></span>  
  
 <span data-ttu-id="ac381-129">**Nota** : solo se permite un índice clúster por tabla.</span><span class="sxs-lookup"><span data-stu-id="ac381-129">**Note** Only one clustered index is allowed for each table.</span></span> <span data-ttu-id="ac381-130">Solo se permite un índice de almacén de columnas optimizado de memoria one xVelocity por tabla.</span><span class="sxs-lookup"><span data-stu-id="ac381-130">Only one xVelocity memory optimized columnstore index is allowed for each table.</span></span>  
  
 <span data-ttu-id="ac381-131">**Único**</span><span class="sxs-lookup"><span data-stu-id="ac381-131">**Unique**</span></span>  
 <span data-ttu-id="ac381-132">Si selecciona esta casilla, el índice será único.</span><span class="sxs-lookup"><span data-stu-id="ac381-132">Selecting this check box makes the index unique.</span></span> <span data-ttu-id="ac381-133">No está permitido que dos filas tengan el mismo valor de índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-133">No two rows are permitted to have the same index value.</span></span> <span data-ttu-id="ac381-134">De forma predeterminada, esta casilla no está activada.</span><span class="sxs-lookup"><span data-stu-id="ac381-134">By default, this check box is cleared.</span></span> <span data-ttu-id="ac381-135">Cuando se modifica un índice existente, la creación de índice generará un error si dos filas tienen el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="ac381-135">When modifying an existing index, index creation will fail if two rows have the same value.</span></span> <span data-ttu-id="ac381-136">En las columnas donde se permite NULL, un índice único admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="ac381-136">For columns where NULL is permitted, a unique index permits one NULL value.</span></span>  
  
 <span data-ttu-id="ac381-137">Si selecciona **Espacial** en el campo **Tipo de índice** , la casilla **Único** aparece atenuada.</span><span class="sxs-lookup"><span data-stu-id="ac381-137">If you select **Spatial** in the **Index type** field, the **Unique** check box is dimmed.</span></span>  
  
 <span data-ttu-id="ac381-138">**Columnas de clave de índice**</span><span class="sxs-lookup"><span data-stu-id="ac381-138">**Index key columns**</span></span>  
 <span data-ttu-id="ac381-139">Agregue las columnas deseadas a la cuadrícula **Columnas de clave de índice** .</span><span class="sxs-lookup"><span data-stu-id="ac381-139">Add the desired columns to the **Index key columns** grid.</span></span> <span data-ttu-id="ac381-140">Cuando se agrega más de una columna, las columnas deben aparecer en una lista con el orden deseado.</span><span class="sxs-lookup"><span data-stu-id="ac381-140">When more than one column is added, the columns must be listed in the order desired.</span></span> <span data-ttu-id="ac381-141">El orden de las columnas en un índice puede tener un gran impacto en el rendimiento del índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-141">The column order in an index can have a great impact on the index performance.</span></span>  
  
 <span data-ttu-id="ac381-142">No pueden participar más de 16 columnas en un solo índice compuesto.</span><span class="sxs-lookup"><span data-stu-id="ac381-142">No more than 16 columns can participate in a single composite index.</span></span> <span data-ttu-id="ac381-143">Para más de 16 columnas, vea Columnas incluidas al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ac381-143">For greater than 16 columns, see included columns at the end of this topic.</span></span>  
  
 <span data-ttu-id="ac381-144">Un índice espacial solo se puede definir en una única columna que contenga un tipo de datos espaciales (una *columna espacial*).</span><span class="sxs-lookup"><span data-stu-id="ac381-144">A spatial index can be defined only on a single column that contains a spatial data type (a *spatial column*).</span></span>  
  
 <span data-ttu-id="ac381-145">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ac381-145">**Name**</span></span>  
 <span data-ttu-id="ac381-146">Muestra el nombre de la columna que participa en la clave de índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-146">Displays the name of the column that participates in the index key.</span></span>  
  
 <span data-ttu-id="ac381-147">**Criterio de ordenación**</span><span class="sxs-lookup"><span data-stu-id="ac381-147">**Sort Order**</span></span>  
 <span data-ttu-id="ac381-148">Especifica la ordenación de la columna de índice seleccionada, es decir, **Ascendente** o **Descendente**.</span><span class="sxs-lookup"><span data-stu-id="ac381-148">Specifies the sort direction of the selected index column, either **Ascending** or **Descending**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac381-149">Si el tipo de índice es **XML principal** o **Espacial**, esta columna no aparece en la tabla.</span><span class="sxs-lookup"><span data-stu-id="ac381-149">If the index type is **Primary XML** or **Spatial**, this column does not appear in the table.</span></span>  
  
 <span data-ttu-id="ac381-150">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ac381-150">**Data Type**</span></span>  
 <span data-ttu-id="ac381-151">Muestra la información sobre el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ac381-151">Displays the data type information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac381-152">Si la columna de tabla es una columna calculada, **Tipo de datos** mostrará "columna calculada".</span><span class="sxs-lookup"><span data-stu-id="ac381-152">If the table column is a computed column, **Data type** displays "computed column."</span></span>  
  
 <span data-ttu-id="ac381-153">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="ac381-153">**Size**</span></span>  
 <span data-ttu-id="ac381-154">Muestra el número máximo de bytes necesarios para almacenar el tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="ac381-154">Displays the maximum number of bytes required to store the column data type.</span></span> <span data-ttu-id="ac381-155">Muestra cero (0) para las columnas espaciales o XML.</span><span class="sxs-lookup"><span data-stu-id="ac381-155">Displays zero (0) for a spatial or XML column.</span></span>  
  
 <span data-ttu-id="ac381-156">**Identidad**</span><span class="sxs-lookup"><span data-stu-id="ac381-156">**Identity**</span></span>  
 <span data-ttu-id="ac381-157">Muestra si la columna que participa en la clave de índice es una columna de identidad.</span><span class="sxs-lookup"><span data-stu-id="ac381-157">Displays whether the column participating in the index key is an identity column.</span></span>  
  
 <span data-ttu-id="ac381-158">**Permitir valores NULL**</span><span class="sxs-lookup"><span data-stu-id="ac381-158">**Allow NULLs**</span></span>  
 <span data-ttu-id="ac381-159">Muestra si la columna que participa en la clave de índice permite almacenar valores NULL en la columna de vista o tabla.</span><span class="sxs-lookup"><span data-stu-id="ac381-159">Displays whether the column participating in the index key allows NULL values to be stored in the table or view column.</span></span>  
  
 <span data-ttu-id="ac381-160">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="ac381-160">**Add**</span></span>  
 <span data-ttu-id="ac381-161">Agrega una columna a la clave de índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-161">Adds a column to the index key.</span></span> <span data-ttu-id="ac381-162">Seleccione columnas de tabla del cuadro de diálogo **Seleccionar columnas de** *\<table name>* que aparece al hacer clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ac381-162">Select table columns from the **Select Columns from** *\<table name>* dialog box that appears when you click **Add**.</span></span> <span data-ttu-id="ac381-163">Para un índice espacial, después de seleccionar una columna, este botón aparece atenuado.</span><span class="sxs-lookup"><span data-stu-id="ac381-163">For a spatial index, after you select one column, this button is dimmed.</span></span>  
  
 <span data-ttu-id="ac381-164">**Remove**</span><span class="sxs-lookup"><span data-stu-id="ac381-164">**Remove**</span></span>  
 <span data-ttu-id="ac381-165">Quita la columna seleccionada de la clave de índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-165">Removes the selected column from participation in the index key.</span></span>  
  
 <span data-ttu-id="ac381-166">**Subir**</span><span class="sxs-lookup"><span data-stu-id="ac381-166">**Move Up**</span></span>  
 <span data-ttu-id="ac381-167">Sube la columna seleccionada en la cuadrícula de la clave de índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-167">Moves the selected column up in the index key grid.</span></span>  
  
 <span data-ttu-id="ac381-168">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="ac381-168">**Move Down**</span></span>  
 <span data-ttu-id="ac381-169">Baja la columna seleccionada en la cuadrícula de la clave de índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-169">Moves the selected column down in the index key grid.</span></span>  
  
 <span data-ttu-id="ac381-170">**Columnas de almacén de columnas**</span><span class="sxs-lookup"><span data-stu-id="ac381-170">**Columnstore columns**</span></span>  
 <span data-ttu-id="ac381-171">Haga clic en **Agregar** para seleccionar columnas para el índice de almacén de columnas.</span><span class="sxs-lookup"><span data-stu-id="ac381-171">Click **Add** to select columns for the columnstore index.</span></span> <span data-ttu-id="ac381-172">Para conocer las limitaciones de un índice de almacén de columnas, vea [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac381-172">For limitations on a columnstore index, see [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span></span>  
  
 <span data-ttu-id="ac381-173">**Columnas incluidas**</span><span class="sxs-lookup"><span data-stu-id="ac381-173">**Included columns**</span></span>  
 <span data-ttu-id="ac381-174">Incluye columnas sin clave en el índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="ac381-174">Include nonkey columns in the nonclustered index.</span></span> <span data-ttu-id="ac381-175">Esta opción le permite superar los límites actuales del índice relativos al tamaño total de una clave de índice y el número máximo de columnas que participan en una clave de índice agregando columnas como columnas sin clave en el nivel hoja del índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="ac381-175">This option allows you to bypass the current index limits on the total size of an index key and the maximum number of columns participating in an index key by adding columns as nonkey columns in the leaf level of the nonclustered index.</span></span> <span data-ttu-id="ac381-176">Para obtener más información, vea [Crear índices con columnas incluidas](create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="ac381-176">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md)</span></span>  
  
##  <a name="select-index-columns-dialog-box"></a><a name="Columns"></a> <span data-ttu-id="ac381-177">Cuadro de diálogo Seleccionar columnas de (índice)</span><span class="sxs-lookup"><span data-stu-id="ac381-177">Select (Index) Columns Dialog Box</span></span>  
 <span data-ttu-id="ac381-178">Use esta página para agregar columnas a la página General de **Propiedades del índice** cuando cree o modifique un índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-178">Use this page to add columns to the **Index Properties General** page when creating or modifying an index.</span></span>  
  
 <span data-ttu-id="ac381-179">**casilla**</span><span class="sxs-lookup"><span data-stu-id="ac381-179">**Check box**</span></span>  
 <span data-ttu-id="ac381-180">Seleccione esta opción para agregar columnas.</span><span class="sxs-lookup"><span data-stu-id="ac381-180">Select to add columns.</span></span>  
  
 <span data-ttu-id="ac381-181">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ac381-181">**Name**</span></span>  
 <span data-ttu-id="ac381-182">Nombre de la columna.</span><span class="sxs-lookup"><span data-stu-id="ac381-182">Name of the column.</span></span>  
  
 <span data-ttu-id="ac381-183">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ac381-183">**Data Type**</span></span>  
 <span data-ttu-id="ac381-184">Tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="ac381-184">The data type of the column.</span></span>  
  
 <span data-ttu-id="ac381-185">**Bytes**</span><span class="sxs-lookup"><span data-stu-id="ac381-185">**Bytes**</span></span>  
 <span data-ttu-id="ac381-186">Tamaño de la columna, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ac381-186">The size of the column in bytes.</span></span>  
  
 <span data-ttu-id="ac381-187">**Identidad**</span><span class="sxs-lookup"><span data-stu-id="ac381-187">**Identity**</span></span>  
 <span data-ttu-id="ac381-188">Muestra **Sí** para columnas de identidad y **No** cuando la columna no es una columna de identidad.</span><span class="sxs-lookup"><span data-stu-id="ac381-188">Displays **Yes** for identity columns, and **No** when the column is not an identity column.</span></span>  
  
 <span data-ttu-id="ac381-189">**Permitir valores NULL**</span><span class="sxs-lookup"><span data-stu-id="ac381-189">**Allow Nulls**</span></span>  
 <span data-ttu-id="ac381-190">Muestra **Sí** cuando la definición de la tabla permite valores NULL para la columna.</span><span class="sxs-lookup"><span data-stu-id="ac381-190">Displays **Yes** when the table definition allows null values for the column.</span></span> <span data-ttu-id="ac381-191">Muestra **No** cuando la definición de la tabla no permite valores NULL para la columna.</span><span class="sxs-lookup"><span data-stu-id="ac381-191">Displays **No** when the table definition does not allow nulls for the column.</span></span>  
  
##  <a name="storage-page-options"></a><a name="Storage"></a> <span data-ttu-id="ac381-192">Opciones de la página Almacenamiento</span><span class="sxs-lookup"><span data-stu-id="ac381-192">Storage Page Options</span></span>  
 <span data-ttu-id="ac381-193">Utilice esta página para ver o modificar las propiedades del grupo de archivos o del esquema de partición para el índice seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ac381-193">Use this page to view or modify filegroup or partition scheme properties for the selected index.</span></span> <span data-ttu-id="ac381-194">Solo muestra las opciones relacionadas con el tipo de índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-194">Only shows options related to the type of index.</span></span>  
  
 <span data-ttu-id="ac381-195">**Grupo de archivos**</span><span class="sxs-lookup"><span data-stu-id="ac381-195">**Filegroup**</span></span>  
 <span data-ttu-id="ac381-196">Almacena el índice en el grupo de archivos especificado.</span><span class="sxs-lookup"><span data-stu-id="ac381-196">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="ac381-197">En la lista solo se muestran los grupos de archivos (fila) estándar.</span><span class="sxs-lookup"><span data-stu-id="ac381-197">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="ac381-198">La selección de lista predeterminada es el grupo de archivos PRIMARY de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac381-198">The default list selection is the PRIMARY filegroup of the database.</span></span> <span data-ttu-id="ac381-199">Para más información, consulte [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="ac381-199">For more information, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
 <span data-ttu-id="ac381-200">**Grupo de archivos de flujo de archivos**</span><span class="sxs-lookup"><span data-stu-id="ac381-200">**Filestream filegroup**</span></span>  
 <span data-ttu-id="ac381-201">Especifica el grupo de archivos para los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ac381-201">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="ac381-202">En esta lista solo se muestran los grupos de archivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ac381-202">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="ac381-203">La selección de lista predeterminada es el grupo de archivos PRIMARY FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ac381-203">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span> <span data-ttu-id="ac381-204">Para obtener más información, vea [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ac381-204">For more information, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="ac381-205">**Esquema de partición**</span><span class="sxs-lookup"><span data-stu-id="ac381-205">**Partition scheme**</span></span>  
 <span data-ttu-id="ac381-206">Almacena el índice en un esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="ac381-206">Stores the index in a partition scheme.</span></span> <span data-ttu-id="ac381-207">Al hacer clic en **Esquema de partición** , se habilita la cuadrícula que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="ac381-207">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="ac381-208">La selección de lista predeterminada es el esquema de partición utilizado para almacenar los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ac381-208">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="ac381-209">Si se selecciona un esquema de partición distinto de la lista, se actualizará la información en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="ac381-209">When you select a different partition scheme in the list, the information in the grid is updated.</span></span> <span data-ttu-id="ac381-210">Para obtener más información, vea [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="ac381-210">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="ac381-211">La opción de esquema de partición no estará disponible si no hay ningún esquema de partición en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac381-211">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="ac381-212">**Esquema de partición Filestream**</span><span class="sxs-lookup"><span data-stu-id="ac381-212">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="ac381-213">Especifica el esquema de partición de los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ac381-213">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="ac381-214">El esquema de partición debe ser simétrico al esquema especificado en la opción **Esquema de partición** .</span><span class="sxs-lookup"><span data-stu-id="ac381-214">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="ac381-215">Si no tiene particiones, el campo está en blanco.</span><span class="sxs-lookup"><span data-stu-id="ac381-215">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="ac381-216">**Parámetro del esquema de partición**</span><span class="sxs-lookup"><span data-stu-id="ac381-216">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="ac381-217">Muestra el nombre de la columna que participa en el esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="ac381-217">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="ac381-218">**Columna de la tabla**</span><span class="sxs-lookup"><span data-stu-id="ac381-218">**Table Column**</span></span>  
 <span data-ttu-id="ac381-219">Seleccione la tabla o vista que se asignará al esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="ac381-219">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="ac381-220">**Tipo de datos de la columna**</span><span class="sxs-lookup"><span data-stu-id="ac381-220">**Column Data Type**</span></span>  
 <span data-ttu-id="ac381-221">Muestra información de tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="ac381-221">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac381-222">Si la columna de tabla es una columna calculada, **Tipo de datos de la columna** mostrará "columna calculada".</span><span class="sxs-lookup"><span data-stu-id="ac381-222">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="ac381-223">**Permitir procesamiento en línea de instrucciones DML al mover el índice**</span><span class="sxs-lookup"><span data-stu-id="ac381-223">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="ac381-224">Permite a los usuarios obtener acceso a los datos de la tabla subyacente o del índice clúster, así como a todos los índices no clúster asociados durante las operaciones de índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-224">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span> <span data-ttu-id="ac381-225">Para más información, consulte [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="ac381-225">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac381-226">Esta opción no estará disponible para los índices XML ni cuando el índice sea un índice clúster deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ac381-226">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="ac381-227">**Establecer grado máximo de paralelismo**</span><span class="sxs-lookup"><span data-stu-id="ac381-227">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="ac381-228">Limita el número de procesadores que se van a utilizar durante la ejecución de planes paralelos.</span><span class="sxs-lookup"><span data-stu-id="ac381-228">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="ac381-229">El valor predeterminado es 0, que utiliza el número real de CPU disponibles.</span><span class="sxs-lookup"><span data-stu-id="ac381-229">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="ac381-230">Si el valor se establece en 1, se suprime la generación de planes paralelos; si el valor se establece en un número mayor que 1, se restringe el número máximo de procesadores que se utilizan en la ejecución de una única consulta.</span><span class="sxs-lookup"><span data-stu-id="ac381-230">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="ac381-231">Esta opción solo está disponible si el cuadro de diálogo está en los estados **Volver a generar** o **Volver a crear** .</span><span class="sxs-lookup"><span data-stu-id="ac381-231">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span> <span data-ttu-id="ac381-232">Para más información, consulte [Establecer la opción Grado máximo de paralelismo para lograr un rendimiento óptimo](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span><span class="sxs-lookup"><span data-stu-id="ac381-232">For more information, see [Set the Max Degree of Parallelism Option for Optimal Performance](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac381-233">Si especifica un valor superior al número de CPU disponibles, se utilizará el número real de CPU disponibles.</span><span class="sxs-lookup"><span data-stu-id="ac381-233">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="spatial-page-index-options"></a><a name="Spatial"></a> <span data-ttu-id="ac381-234">Opciones de índice de la página Espacial</span><span class="sxs-lookup"><span data-stu-id="ac381-234">Spatial Page Index Options</span></span>  
 <span data-ttu-id="ac381-235">Use la página **Espacial** para ver o especificar los valores de las propiedades espaciales.</span><span class="sxs-lookup"><span data-stu-id="ac381-235">Use the **Spatial** page to view or specify the values of the spatial properties.</span></span> <span data-ttu-id="ac381-236">Para obtener más información, vea [Datos espaciales &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ac381-236">For more information, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
### <a name="bounding-box"></a><span data-ttu-id="ac381-237">Cuadro de límite</span><span class="sxs-lookup"><span data-stu-id="ac381-237">Bounding Box</span></span>  
 <span data-ttu-id="ac381-238">El *cuadro de límite* es el perímetro de la cuadrícula de nivel superior de un plano geométrico.</span><span class="sxs-lookup"><span data-stu-id="ac381-238">The *bounding box* is the perimeter of the top-level grid of a geometric plane.</span></span> <span data-ttu-id="ac381-239">Los parámetros de cuadro de límite solo existen en la teselación de cuadrícula de geometría.</span><span class="sxs-lookup"><span data-stu-id="ac381-239">The bounding-box parameters exist only in the geometry grid tessellation.</span></span> <span data-ttu-id="ac381-240">Estos parámetros no están disponibles si **Esquema de teselación** es **Cuadrícula de geografía**.</span><span class="sxs-lookup"><span data-stu-id="ac381-240">These parameters are unavailable if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="ac381-241">El panel muestra las coordenadas **( *`X-min`* , *`Y-min`* )** y **( *`X-max`* , *`Y-max`* )** del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="ac381-241">The panel displays the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="ac381-242">No hay valores predeterminados para las coordenadas.</span><span class="sxs-lookup"><span data-stu-id="ac381-242">There are no default coordinate values.</span></span> <span data-ttu-id="ac381-243">Por consiguiente, cuando cree un nuevo índice espacial en una columna de tipo `geometry`, deberá especificar los valores de las coordenadas.</span><span class="sxs-lookup"><span data-stu-id="ac381-243">Therefore, when you are creating a new spatial index on a `geometry` type column, you must specify the coordinate values.</span></span>  
  
 `X-min`  
 <span data-ttu-id="ac381-244">La coordenada x de la esquina inferior izquierda del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="ac381-244">The X-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `Y-min`  
 <span data-ttu-id="ac381-245">La coordenada y de la esquina inferior izquierda del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="ac381-245">The Y-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `X-max`  
 <span data-ttu-id="ac381-246">La coordenada x de la esquina superior derecha del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="ac381-246">The X-coordinate of the upper-right corner of the bounding box.</span></span>  
  
 `Y-max`  
 <span data-ttu-id="ac381-247">La coordenada y de la esquina superior derecha del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="ac381-247">The Y-coordinate of upper-right corner of the bounding box.</span></span>  
  
### <a name="general"></a><span data-ttu-id="ac381-248">General</span><span class="sxs-lookup"><span data-stu-id="ac381-248">General</span></span>  
 <span data-ttu-id="ac381-249">**Esquema de teselación**</span><span class="sxs-lookup"><span data-stu-id="ac381-249">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="ac381-250">Indica el esquema de teselación del índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-250">Indicates the tessellation scheme of the index.</span></span> <span data-ttu-id="ac381-251">Los esquemas de teselación admitidos son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="ac381-251">The supported tessellation schemes are as follows.</span></span>  
  
 <span data-ttu-id="ac381-252">**Cuadrícula de geometría**</span><span class="sxs-lookup"><span data-stu-id="ac381-252">**Geometry grid**</span></span>  
 <span data-ttu-id="ac381-253">Especifica el esquema de teselación de cuadrícula de geometría, que se aplica a una columna del tipo de datos `geometry`.</span><span class="sxs-lookup"><span data-stu-id="ac381-253">Specifies the geometry grid tessellation scheme, which applies to a column of the `geometry` data type.</span></span>  
  
 <span data-ttu-id="ac381-254">**Cuadrícula automática de geometría**</span><span class="sxs-lookup"><span data-stu-id="ac381-254">**Geometry Auto grid**</span></span>  
 <span data-ttu-id="ac381-255">Esta opción está habilitada para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cuando el nivel de compatibilidad de base de datos se ha establecido en 110 o superior.</span><span class="sxs-lookup"><span data-stu-id="ac381-255">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="ac381-256">**Cuadrícula de geografía**</span><span class="sxs-lookup"><span data-stu-id="ac381-256">**Geography grid**</span></span>  
 <span data-ttu-id="ac381-257">Especifica el esquema de teselación de cuadrícula de geografía, que se aplica a una columna del tipo de datos **geography** .</span><span class="sxs-lookup"><span data-stu-id="ac381-257">Specifies the geography grid tessellation scheme, which applies to a column of the **geography** data type.</span></span>  
  
 <span data-ttu-id="ac381-258">**Cuadrícula automática de geografía**</span><span class="sxs-lookup"><span data-stu-id="ac381-258">**Geography Auto grid**</span></span>  
 <span data-ttu-id="ac381-259">Esta opción está habilitada para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cuando el nivel de compatibilidad de base de datos se ha establecido en 110 o superior.</span><span class="sxs-lookup"><span data-stu-id="ac381-259">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="ac381-260">Para obtener información sobre el modo en que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implementa la teselación, vea [Datos espaciales &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ac381-260">For information about how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implements tessellation, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="ac381-261">**Celdas por objeto**</span><span class="sxs-lookup"><span data-stu-id="ac381-261">**Cells Per Object**</span></span>  
 <span data-ttu-id="ac381-262">Indica el número de celdas por objeto de teselación que se pueden usar para un único objeto espacial en el índice.</span><span class="sxs-lookup"><span data-stu-id="ac381-262">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="ac381-263">Este número puede ser un entero comprendido entre 1 y 8192, ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="ac381-263">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="ac381-264">El valor predeterminado es 16, y 8 para versiones anteriores de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cuando el nivel de compatibilidad de base de datos se ha establecido en 110 o superior.</span><span class="sxs-lookup"><span data-stu-id="ac381-264">The default is 16, and 8 for earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="ac381-265">En el nivel superior, si un objeto abarca más celdas de las especificadas mediante *n*, la indexación usa tantas celdas como sean necesarias para proporcionar una teselación de nivel superior completa.</span><span class="sxs-lookup"><span data-stu-id="ac381-265">At the top level, if an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="ac381-266">En tales casos, un objeto podría recibir más celdas de las especificadas.</span><span class="sxs-lookup"><span data-stu-id="ac381-266">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="ac381-267">En este caso, el número máximo es la cantidad de celdas generadas por la cuadrícula de nivel superior, que depende de la densidad de **Nivel 1** .</span><span class="sxs-lookup"><span data-stu-id="ac381-267">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
### <a name="grids"></a><span data-ttu-id="ac381-268">Cuadrículas</span><span class="sxs-lookup"><span data-stu-id="ac381-268">Grids</span></span>  
 <span data-ttu-id="ac381-269">Este panel muestra la densidad de la cuadrícula en cada nivel del esquema de la teselación.</span><span class="sxs-lookup"><span data-stu-id="ac381-269">This panel shows the density of the grid at each level of the tessellation scheme.</span></span> <span data-ttu-id="ac381-270">La densidad se especifica como **Baja**, **Media**o **Alta**.</span><span class="sxs-lookup"><span data-stu-id="ac381-270">Density is specified as **Low**, **Medium**, or **High**.</span></span> <span data-ttu-id="ac381-271">El valor predeterminado es **Media**.</span><span class="sxs-lookup"><span data-stu-id="ac381-271">The default is **Medium**.</span></span> <span data-ttu-id="ac381-272">**Baja** representa una cuadrícula de 4 x 4 (16 celdas), **Media** representa una cuadrícula de 8 x 8 (64 celdas) y **Alta** representa una cuadrícula de 16 x 16 (256 celdas).</span><span class="sxs-lookup"><span data-stu-id="ac381-272">**Low** represents a 4x4 grid (16 cells), **Medium** represents an 8x8 grid (64 cells), and **High** represents a 16x16 grid (256 cells).</span></span> <span data-ttu-id="ac381-273">Estas opciones no están disponibles cuando se eligen las opciones de teselación **Cuadrícula automática de geometría** o **Cuadrícula automática de geografía** .</span><span class="sxs-lookup"><span data-stu-id="ac381-273">These options are not available when the **Geometry Auto grid** or **Geography Auto grid** tessellation options are chosen.</span></span>  
  
 <span data-ttu-id="ac381-274">**Nivel 1**</span><span class="sxs-lookup"><span data-stu-id="ac381-274">**Level 1**</span></span>  
 <span data-ttu-id="ac381-275">La densidad de la cuadrícula del primer nivel (superior).</span><span class="sxs-lookup"><span data-stu-id="ac381-275">The density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="ac381-276">**Nivel 2**</span><span class="sxs-lookup"><span data-stu-id="ac381-276">**Level 2**</span></span>  
 <span data-ttu-id="ac381-277">La densidad de la cuadrícula del segundo nivel.</span><span class="sxs-lookup"><span data-stu-id="ac381-277">The density of the second-level grid.</span></span>  
  
 <span data-ttu-id="ac381-278">**Nivel 3**</span><span class="sxs-lookup"><span data-stu-id="ac381-278">**Level 3**</span></span>  
 <span data-ttu-id="ac381-279">La densidad de la cuadrícula del tercer nivel.</span><span class="sxs-lookup"><span data-stu-id="ac381-279">The density of the third-level grid.</span></span>  
  
 <span data-ttu-id="ac381-280">**Nivel 4**</span><span class="sxs-lookup"><span data-stu-id="ac381-280">**Level 4**</span></span>  
 <span data-ttu-id="ac381-281">La densidad de la cuadrícula del cuarto nivel.</span><span class="sxs-lookup"><span data-stu-id="ac381-281">The density of the fourth-level grid.</span></span>  
  
##  <a name="filter-page"></a><a name="Filter"></a> <span data-ttu-id="ac381-282">Página Filtro</span><span class="sxs-lookup"><span data-stu-id="ac381-282">Filter Page</span></span>  
 <span data-ttu-id="ac381-283">Use esta página para especificar el predicado de filtro para un índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="ac381-283">Use this page to enter the filter predicate for a filtered index.</span></span> <span data-ttu-id="ac381-284">Para obtener más información, consulte [Create Filtered Indexes](create-filtered-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="ac381-284">For more information, see [Create Filtered Indexes](create-filtered-indexes.md).</span></span>  
  
 <span data-ttu-id="ac381-285">**Expresión de filtro**</span><span class="sxs-lookup"><span data-stu-id="ac381-285">**Filter Expression**</span></span>  
 <span data-ttu-id="ac381-286">Define qué filas de datos para incluir en el índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="ac381-286">Defines which data rows to include in the filtered index.</span></span> <span data-ttu-id="ac381-287">Por ejemplo: `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span><span class="sxs-lookup"><span data-stu-id="ac381-287">For example, `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac381-288">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac381-288">See Also</span></span>  
 <span data-ttu-id="ac381-289">[Establecer opciones de índice](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="ac381-289">[Set Index Options](set-index-options.md) </span></span>  
 <span data-ttu-id="ac381-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ac381-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 [<span data-ttu-id="ac381-291">sys.indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ac381-291">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
