---
title: Propiedades de tabla (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.tabledesigner
- vdt.designers.properties.Table
ms.assetid: cc392987-1aab-45f5-b5af-a26be53409bf
author: stevestein
ms.author: sstein
ms.openlocfilehash: df4a0332ebc622b069c468e51c461b7cba20aa36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747846"
---
# <a name="table-properties-visual-database-tools"></a><span data-ttu-id="9b322-102">Propiedades de la tabla (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9b322-102">Table Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="9b322-103">Estas propiedades aparecen en la ventana Propiedades cuando se hace clic con el botón secundario en el Diseñador de tablas y se selecciona Propiedades.</span><span class="sxs-lookup"><span data-stu-id="9b322-103">These properties appear in the Properties window when you right click in Table Designer and select Properties.</span></span> <span data-ttu-id="9b322-104">A menos que se especifique lo contrario, podrá modificar estas propiedades en la ventana Propiedades cuando la tabla esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9b322-104">Unless otherwise noted, you can edit these properties in the Properties window when the table is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b322-105">Si se publica la tabla para la replicación, debe modificar el esquema mediante la instrucción Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) u Objetos de administración de SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="9b322-105">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="9b322-106">Si se modifica el esquema mediante el Diseñador de tablas o el Diseñador de diagramas de base de datos, se intentará eliminar la tabla y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="9b322-106">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="9b322-107">No se pueden eliminar objetos publicados, por lo que la modificación del esquema generará un error.</span><span class="sxs-lookup"><span data-stu-id="9b322-107">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="show-table-properties-in-table-designer"></a><span data-ttu-id="9b322-108">Mostrar las propiedades de tabla en el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="9b322-108">Show Table Properties in Table Designer</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b322-109">Las propiedades de este tema se ordenan por categoría en lugar de alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="9b322-109">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
 <span data-ttu-id="9b322-110">**Categoría Identidad**</span><span class="sxs-lookup"><span data-stu-id="9b322-110">**Identity Category**</span></span>  
 <span data-ttu-id="9b322-111">Se expande para mostrar las propiedades **Nombre**, **Descripción**y **Esquema**.</span><span class="sxs-lookup"><span data-stu-id="9b322-111">Expands to show properties for **Name**, **Description**, and **Schema**.</span></span>  
  
 <span data-ttu-id="9b322-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9b322-112">**Name**</span></span>  
 <span data-ttu-id="9b322-113">Muestra el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9b322-113">Displays the name of the table.</span></span> <span data-ttu-id="9b322-114">Para editar el nombre, escriba en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="9b322-114">To edit the name, type in the text box.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9b322-115">Si las consultas, vistas, funciones definidas por el usuario, procedimientos almacenados o programas existentes hacen referencia a la tabla, la modificación del nombre hará que estos objetos dejen de ser válidos.</span><span class="sxs-lookup"><span data-stu-id="9b322-115">If existing queries, views, user-defined functions, stored procedures, or programs refer to the table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="9b322-116">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="9b322-116">**Database Name**</span></span>  
 <span data-ttu-id="9b322-117">Muestra el nombre del origen de datos de la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9b322-117">Shows the name of the data source of the selected table.</span></span>  
  
 <span data-ttu-id="9b322-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9b322-118">**Description**</span></span>  
 <span data-ttu-id="9b322-119">Muestra una descripción de la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9b322-119">Shows a description of the selected table.</span></span> <span data-ttu-id="9b322-120">Para ver o editar la descripción completa, haga clic en la descripción y después en el botón de puntos suspensivos **(...)** situado a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9b322-120">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span>  
  
 <span data-ttu-id="9b322-121">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="9b322-121">**Schema**</span></span>  
 <span data-ttu-id="9b322-122">Muestra el nombre del esquema al que pertenece esta tabla</span><span class="sxs-lookup"><span data-stu-id="9b322-122">Shows the name of the schema to which this table belongs.</span></span> <span data-ttu-id="9b322-123">(solo se aplica a Microsoft SQL Server).</span><span class="sxs-lookup"><span data-stu-id="9b322-123">(Applies only to Microsoft SQL Server.)</span></span>  
  
 <span data-ttu-id="9b322-124">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="9b322-124">**Server Name**</span></span>  
 <span data-ttu-id="9b322-125">Muestra el nombre del servidor del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9b322-125">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="9b322-126">**Categoría Diseñador de tablas**</span><span class="sxs-lookup"><span data-stu-id="9b322-126">**Table Designer Category**</span></span>  
 <span data-ttu-id="9b322-127">Se expande para mostrar las propiedades de **Columna de identidad**, **Indizable**y **Replicado**.</span><span class="sxs-lookup"><span data-stu-id="9b322-127">Expands to show properties for **Identity Column**, **Is Indexable**, and **Is Replicated**.</span></span>  
  
 <span data-ttu-id="9b322-128">**Columna de identidad**</span><span class="sxs-lookup"><span data-stu-id="9b322-128">**Identity Column**</span></span>  
 <span data-ttu-id="9b322-129">Muestra la columna utilizada como columna de identidad de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9b322-129">Shows the column used as the table's identity column.</span></span> <span data-ttu-id="9b322-130">Para cambiar la columna de identidad, elija una en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9b322-130">To change the identity column, choose from the drop-down list.</span></span> <span data-ttu-id="9b322-131">Solo se mostrarán en la lista columnas de tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="9b322-131">Only columns of a numeric data type will show in the list.</span></span>  
  
 <span data-ttu-id="9b322-132">**Indizable**</span><span class="sxs-lookup"><span data-stu-id="9b322-132">**Is Indexable**</span></span>  
 <span data-ttu-id="9b322-133">Muestra si la tabla puede indizarse.</span><span class="sxs-lookup"><span data-stu-id="9b322-133">Shows whether the table can be indexed.</span></span> <span data-ttu-id="9b322-134">Si la tabla no puede indizarse, puede deberse a que no es el propietario de la tabla o a que la tabla contiene columnas con tipos de datos text, ntext o image.</span><span class="sxs-lookup"><span data-stu-id="9b322-134">If the table is not indexable it may be because you are not the table owner or because the table contains columns with data types of text, ntext, or image.</span></span>  
  
 <span data-ttu-id="9b322-135">**Replicado**</span><span class="sxs-lookup"><span data-stu-id="9b322-135">**Is Replicated**</span></span>  
 <span data-ttu-id="9b322-136">Muestra si la columna se replica en otra ubicación</span><span class="sxs-lookup"><span data-stu-id="9b322-136">Shows whether the table is replicated in another location.</span></span>  
  
 <span data-ttu-id="9b322-137">**Categoría Especificación de espacio de datos normal**</span><span class="sxs-lookup"><span data-stu-id="9b322-137">**Regular Data Space Specification Category**</span></span>  
 <span data-ttu-id="9b322-138">Se expande para mostrar las propiedades de **(Tipo de espacio de datos)** , **Nombre de esquema de partición o grupo de archivos**y **Lista de columnas de particiones**.</span><span class="sxs-lookup"><span data-stu-id="9b322-138">Expands to show properties for **(Data Space Type)**, **Filegroup or Partition Scheme Name**, and **Partition Column List**.</span></span>  
  
 <span data-ttu-id="9b322-139">**(Tipo de espacio de datos)**</span><span class="sxs-lookup"><span data-stu-id="9b322-139">**(Data Space Type)**</span></span>  
 <span data-ttu-id="9b322-140">Indica si la tabla se almacena utilizando un grupo de archivos o un esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="9b322-140">Shows whether this table is stored using a filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="9b322-141">**Nombre de esquema de partición o grupo de archivo**</span><span class="sxs-lookup"><span data-stu-id="9b322-141">**Filegroup or Partition Scheme Name**</span></span>  
 <span data-ttu-id="9b322-142">Muestra el nombre del grupo de archivos o esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="9b322-142">Shows the name of the filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="9b322-143">**Lista de columnas de particiones**</span><span class="sxs-lookup"><span data-stu-id="9b322-143">**Partition Column List**</span></span>  
 <span data-ttu-id="9b322-144">Proporciona acceso al cuadro de diálogo **Lista de columnas de particiones** .</span><span class="sxs-lookup"><span data-stu-id="9b322-144">Provides access to the **Partition Column List** dialog box.</span></span>  
  
 <span data-ttu-id="9b322-145">**Columna de GUID de filas**</span><span class="sxs-lookup"><span data-stu-id="9b322-145">**Row GUID Column**</span></span>  
 <span data-ttu-id="9b322-146">Muestra la columna utilizada por Microsoft SQL Server como columna ROWGUID de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9b322-146">Shows the column used by Microsoft SQL Server as the table's ROWGUID column.</span></span> <span data-ttu-id="9b322-147">Para cambiar la columna ROWGUID, elija una en la lista desplegable</span><span class="sxs-lookup"><span data-stu-id="9b322-147">To change the ROWGUID column, choose from the drop-down list.</span></span> <span data-ttu-id="9b322-148">(solo se aplica a SQL Server 7.0 o posterior).</span><span class="sxs-lookup"><span data-stu-id="9b322-148">(Applies only to SQL Server 7.0 or higher.)</span></span>  
  
 <span data-ttu-id="9b322-149">**Grupo de archivos Text/Image**</span><span class="sxs-lookup"><span data-stu-id="9b322-149">**Text/Image Filegroup**</span></span>  
 <span data-ttu-id="9b322-150">Proporciona una lista desplegable en la que se puede elegir el grupo de archivos para columnas que tienen tipos de datos text o image.</span><span class="sxs-lookup"><span data-stu-id="9b322-150">Provides a drop-down list from which you can choose the filegroup for columns that have text or image data types.</span></span> <span data-ttu-id="9b322-151">Si la tabla se almacena utilizando un esquema de partición, deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="9b322-151">If the table is stored using a partition scheme, leave this field blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b322-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b322-152">See Also</span></span>  
 [<span data-ttu-id="9b322-153">Diseñar tablas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9b322-153">Design Tables &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
