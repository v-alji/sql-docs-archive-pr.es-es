---
title: Modificación de relaciones de claves externas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65538
- vdt.ppg.relationships
helpviewer_keywords:
- foreign keys [SQL Server], modifying
- modifying foreign keys
ms.assetid: 0c9ca80d-d79b-44c4-a21e-0fce39c398ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: ba9010b0d634a174dd35391c870d5003aa78efa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663306"
---
# <a name="modify-foreign-key-relationships"></a><span data-ttu-id="a3e17-102">Modificar relaciones de claves externas.</span><span class="sxs-lookup"><span data-stu-id="a3e17-102">Modify Foreign Key Relationships</span></span>
  <span data-ttu-id="a3e17-103">Puede modificar el lado de clave externa de una relación en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3e17-103">You can modify the foreign key side of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a3e17-104">Modificar los cambios de clave externa de una tabla cuyas columnas están relacionadas con las columnas de la tabla de clave principal.</span><span class="sxs-lookup"><span data-stu-id="a3e17-104">Modifying a table's foreign key changes which columns are related to columns in the primary key table.</span></span>  
  
 <span data-ttu-id="a3e17-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a3e17-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a3e17-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a3e17-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a3e17-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a3e17-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a3e17-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a3e17-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a3e17-109">**Para modificar una clave externa con:**</span><span class="sxs-lookup"><span data-stu-id="a3e17-109">**To modify a foreign key using:**</span></span>  
  
     [<span data-ttu-id="a3e17-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a3e17-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a3e17-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a3e17-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a3e17-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a3e17-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a3e17-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a3e17-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a3e17-114">La nueva columna de clave externa debe tener el mismo tipo de datos y el mismo tamaño que la columna de clave principal con la que está relacionada, con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="a3e17-114">The new foreign key column must match the data type and size of the primary key column to which it relates, with these exceptions:</span></span>  
  
-   <span data-ttu-id="a3e17-115">Se puede asociar una columna de tipo `char` o `sysname` a una columna de tipo `varchar`.</span><span class="sxs-lookup"><span data-stu-id="a3e17-115">A `char` column or `sysname` column can relate to a `varchar` column.</span></span>  
  
-   <span data-ttu-id="a3e17-116">Se puede asociar una columna de tipo `binary` a una columna de tipo `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="a3e17-116">A `binary` column can relate to a `varbinary` column.</span></span>  
  
-   <span data-ttu-id="a3e17-117">Se puede asociar un tipo de datos de alias a su tipo básico.</span><span class="sxs-lookup"><span data-stu-id="a3e17-117">An alias data type can relate to its base type.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a3e17-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a3e17-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a3e17-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="a3e17-119">Permissions</span></span>  
 <span data-ttu-id="a3e17-120">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="a3e17-120">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a3e17-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a3e17-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-foreign-key"></a><span data-ttu-id="a3e17-122">Para modificar una clave externa</span><span class="sxs-lookup"><span data-stu-id="a3e17-122">To modify a foreign key</span></span>  
  
1.  <span data-ttu-id="a3e17-123">En el **Explorador de objetos**, expanda la tabla con la clave externa y luego expanda **Claves**.</span><span class="sxs-lookup"><span data-stu-id="a3e17-123">In **Object Explorer**, expand the table with the foreign key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="a3e17-124">Haga clic con el botón derecho en la clave externa que se va a modificar y seleccione **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="a3e17-124">Right-click the foreign key to be modified and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="a3e17-125">En el cuadro de diálogo **Relaciones de clave externa** , puede realizar las siguientes modificaciones.</span><span class="sxs-lookup"><span data-stu-id="a3e17-125">In the **Foreign Key Relationships** dialog box, you can make the following modifications.</span></span>  
  
     <span data-ttu-id="a3e17-126">**Relación seleccionada**</span><span class="sxs-lookup"><span data-stu-id="a3e17-126">**Selected Relationship**</span></span>  
     <span data-ttu-id="a3e17-127">Muestra las relaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="a3e17-127">Lists existing relationships.</span></span> <span data-ttu-id="a3e17-128">Seleccione una relación para mostrar sus propiedades en la cuadrícula situada a la derecha.</span><span class="sxs-lookup"><span data-stu-id="a3e17-128">Select a relationship to show its properties in the grid to the right.</span></span> <span data-ttu-id="a3e17-129">Si la lista está vacía, no se han definido relaciones para la tabla.</span><span class="sxs-lookup"><span data-stu-id="a3e17-129">If the list is empty, no relationships have been defined for the table.</span></span>  
  
     <span data-ttu-id="a3e17-130">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="a3e17-130">**Add**</span></span>  
     <span data-ttu-id="a3e17-131">Crea una nueva relación.</span><span class="sxs-lookup"><span data-stu-id="a3e17-131">Create a new relationship.</span></span> <span data-ttu-id="a3e17-132">Debe definir **Especificación de tablas y columnas** para que la relación sea válida.</span><span class="sxs-lookup"><span data-stu-id="a3e17-132">The **Tables and Columns Specifications** must be set before the relationship will be valid.</span></span>  
  
     <span data-ttu-id="a3e17-133">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="a3e17-133">**Delete**</span></span>  
     <span data-ttu-id="a3e17-134">Elimina la relación seleccionada en la lista **Relaciones seleccionadas** .</span><span class="sxs-lookup"><span data-stu-id="a3e17-134">Delete the relationship selected in the **Selected Relationships** list.</span></span> <span data-ttu-id="a3e17-135">Para cancelar la adición de una relación, utilice este botón para eliminar la relación.</span><span class="sxs-lookup"><span data-stu-id="a3e17-135">To cancel the addition of a relationship, use this button to remove the relationship.</span></span>  
  
     <span data-ttu-id="a3e17-136">**Categoría General**</span><span class="sxs-lookup"><span data-stu-id="a3e17-136">**General Category**</span></span>  
     <span data-ttu-id="a3e17-137">Se expande para mostrar **Comprobar datos existentes al crear o al habilitar de nuevo** y **Especificación de tablas y columnas**.</span><span class="sxs-lookup"><span data-stu-id="a3e17-137">Expand to show **Check Existing Data on Creation or RE-Enabling** and **Tables and Columns Specifications**.</span></span>  
  
     <span data-ttu-id="a3e17-138">**Check Existing Data on Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="a3e17-138">**Check Existing Data on Creation or Re-Enabling**</span></span>  
     <span data-ttu-id="a3e17-139">Comprueba con la restricción todos los datos que había en la tabla antes de crear o habilitar de nuevo la restricción.</span><span class="sxs-lookup"><span data-stu-id="a3e17-139">Verify all existing data in the table before the constraint was created or re-enabled, against the constraint.</span></span>  
  
     <span data-ttu-id="a3e17-140">**Especificación de tablas y columnas (Categoría)**</span><span class="sxs-lookup"><span data-stu-id="a3e17-140">**Tables and Columns Specifications Category**</span></span>  
     <span data-ttu-id="a3e17-141">Se expande para mostrar qué columnas actúan como clave externa y principal (o única) en la relación y a qué tablas pertenecen.</span><span class="sxs-lookup"><span data-stu-id="a3e17-141">Expand to show which columns from which tables act as the foreign key and primary (or unique) key in the relationship.</span></span> <span data-ttu-id="a3e17-142">Para editar o definir estos valores, haga clic en el botón de puntos suspensivos ( **...** ) situado a la derecha del campo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a3e17-142">To edit or define these values, click the ellipsis button (**...**) to the right of the property field.</span></span>  
  
     <span data-ttu-id="a3e17-143">**Tabla base de clave externa**</span><span class="sxs-lookup"><span data-stu-id="a3e17-143">**Foreign Key Base Table**</span></span>  
     <span data-ttu-id="a3e17-144">Muestra la tabla que contiene la columna que actúa como clave externa en la relación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a3e17-144">Shows which table contains the column acting as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="a3e17-145">**Columnas de clave externa**</span><span class="sxs-lookup"><span data-stu-id="a3e17-145">**Foreign Key Columns**</span></span>  
     <span data-ttu-id="a3e17-146">Muestra la columna que actúa como clave externa en la relación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a3e17-146">Shows which column acts as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="a3e17-147">**Tabla base de claves Primary/Unique**</span><span class="sxs-lookup"><span data-stu-id="a3e17-147">**Primary/Unique Key Base Table**</span></span>  
     <span data-ttu-id="a3e17-148">Muestra la tabla que contiene la columna que actúa como clave principal (o única) en la relación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a3e17-148">Shows which table contains the column acting as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="a3e17-149">**Columnas de clave Primary/Unique**</span><span class="sxs-lookup"><span data-stu-id="a3e17-149">**Primary/Unique Key Columns**</span></span>  
     <span data-ttu-id="a3e17-150">Muestra la columna que actúa como clave principal (o única) en la relación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a3e17-150">Shows which column acts as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="a3e17-151">**Categoría Identidad**</span><span class="sxs-lookup"><span data-stu-id="a3e17-151">**Identity Category**</span></span>  
     <span data-ttu-id="a3e17-152">Se expande para mostrar los campos de propiedades de **Nombre** y **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="a3e17-152">Expand to show the property fields for **Name** and **Description**.</span></span>  
  
     <span data-ttu-id="a3e17-153">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a3e17-153">**Name**</span></span>  
     <span data-ttu-id="a3e17-154">Muestra el nombre de relación.</span><span class="sxs-lookup"><span data-stu-id="a3e17-154">Shows the name of the relationship.</span></span> <span data-ttu-id="a3e17-155">Cuando se crea una nueva relación, se le da un nombre predeterminado que se basa en la tabla de la ventana activa del **Diseñador de tablas**.</span><span class="sxs-lookup"><span data-stu-id="a3e17-155">When a new relationship is created, it is given a default name based on the table in the active window in **Table Designer**.</span></span> <span data-ttu-id="a3e17-156">Puede cambiar el nombre en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="a3e17-156">You can change the name at any time.</span></span>  
  
     <span data-ttu-id="a3e17-157">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a3e17-157">**Description**</span></span>  
     <span data-ttu-id="a3e17-158">Describe la relación.</span><span class="sxs-lookup"><span data-stu-id="a3e17-158">Describe the relationship.</span></span> <span data-ttu-id="a3e17-159">Para escribir una descripción más detallada, haga clic en **Descripción** y luego en los puntos suspensivos **(...)** que aparecen a la derecha del campo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a3e17-159">To write a more detailed description, click **Description** and then click the ellipsis **(...)** that appears to the right of the property field.</span></span> <span data-ttu-id="a3e17-160">De este modo, obtendrá un área más grande en la que escribir el texto.</span><span class="sxs-lookup"><span data-stu-id="a3e17-160">This provides a larger area in which to write text.</span></span>  
  
     <span data-ttu-id="a3e17-161">**Categoría Diseñador de tablas**</span><span class="sxs-lookup"><span data-stu-id="a3e17-161">**Table Designer Category**</span></span>  
     <span data-ttu-id="a3e17-162">Se expande para mostrar la información de **Comprobar datos existentes al crear o al habilitar de nuevo** y **Exigir para replicación**.</span><span class="sxs-lookup"><span data-stu-id="a3e17-162">Expand to show information for **Check Existing Data on Creation or Re-Enabling** and **Enforce for Replication**.</span></span>  
  
     <span data-ttu-id="a3e17-163">**Exigir para replicación**</span><span class="sxs-lookup"><span data-stu-id="a3e17-163">**Enforce For Replication**</span></span>  
     <span data-ttu-id="a3e17-164">Indica si se exigirá la restricción cuando un agente de replicación realice una inserción, actualización o eliminación en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="a3e17-164">Indicates whether to enforce the constraint when a replication agent performs an insert, update, or delete on this table.</span></span>  
  
     <span data-ttu-id="a3e17-165">**Exigir restricción de clave externa**</span><span class="sxs-lookup"><span data-stu-id="a3e17-165">**Enforce Foreign Key Constraint**</span></span>  
     <span data-ttu-id="a3e17-166">Especifica si se pueden modificar los datos de las columnas de la relación y si estos cambios pueden invalidar la integridad de la relación de clave externa.</span><span class="sxs-lookup"><span data-stu-id="a3e17-166">Specify whether changes are allowed to the data of the columns in the relationship if those changes would invalidate the integrity of the foreign key relationship.</span></span> <span data-ttu-id="a3e17-167">Elija **Sí** si no desea permitir esos cambios y **No** si desea permitirlos.</span><span class="sxs-lookup"><span data-stu-id="a3e17-167">Choose **Yes** if you do not want to allow such changes, and choose **No** if you do want to allow them.</span></span>  
  
     <span data-ttu-id="a3e17-168">**Especificación de INSERT y UPDATE (Categoría)**</span><span class="sxs-lookup"><span data-stu-id="a3e17-168">**INSERT and UPDATE Specification Category**</span></span>  
     <span data-ttu-id="a3e17-169">Se expande para mostrar la información de **Regla de eliminación** y **Regla de actualización** de la relación.</span><span class="sxs-lookup"><span data-stu-id="a3e17-169">Expand to show information for the **Delete Rule** and the **Update Rule** for the relationship.</span></span>  
  
     <span data-ttu-id="a3e17-170">**Regla de eliminación**</span><span class="sxs-lookup"><span data-stu-id="a3e17-170">**Delete Rule**</span></span>  
     <span data-ttu-id="a3e17-171">Especifica lo que sucede si un usuario intenta eliminar una fila con datos que están implicados en una relación de clave externa:</span><span class="sxs-lookup"><span data-stu-id="a3e17-171">Specify what happens if a user tries to delete a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="a3e17-172">**Sin acción** Un mensaje de error indica al usuario que no se permite la eliminación y, a continuación, se revierte la eliminación.</span><span class="sxs-lookup"><span data-stu-id="a3e17-172">**No Action** An error message tells the user that the deletion is not allowed and the DELETE is rolled back.</span></span>  
  
    -   <span data-ttu-id="a3e17-173">**Cascada** Elimina todas las filas que contengan datos implicados en la relación de clave externa.</span><span class="sxs-lookup"><span data-stu-id="a3e17-173">**Cascade** Deletes all rows containing data involved in the foreign key relationship.</span></span> <span data-ttu-id="a3e17-174">No especifique CASCADE si la tabla se va a incluir en una publicación de combinación que utiliza registros lógicos.</span><span class="sxs-lookup"><span data-stu-id="a3e17-174">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="a3e17-175">**Establecer en Null** Establece el valor en NULL si todas las columnas de clave externa de la tabla aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="a3e17-175">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="a3e17-176">**Establecer predeterminado** Establece el valor predeterminado definido para la columna cuando todas las columnas de clave externa de la tabla tienen definidos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a3e17-176">**Set Default** Sets the value to the default value defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
     <span data-ttu-id="a3e17-177">**Regla de actualización**</span><span class="sxs-lookup"><span data-stu-id="a3e17-177">**Update Rule**</span></span>  
     <span data-ttu-id="a3e17-178">Especifica lo que sucede si un usuario intenta actualizar una fila con datos que están implicados en una relación de clave externa:</span><span class="sxs-lookup"><span data-stu-id="a3e17-178">Specify what occurs if a user tries to update a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="a3e17-179">**Ninguna acción** Un mensaje de error indica al usuario que no se permite la actualización y, a continuación, se revierte la actualización.</span><span class="sxs-lookup"><span data-stu-id="a3e17-179">**No Action** An error message tells the user that the update is not allowed and the UPDATE is rolled back.</span></span>  
  
    -   <span data-ttu-id="a3e17-180">**Cascada** Actualiza todas las filas que contengan datos implicados en la relación de clave externa.</span><span class="sxs-lookup"><span data-stu-id="a3e17-180">**Cascade** Updates all rows that contain data involved in the foreign key relationship.</span></span> <span data-ttu-id="a3e17-181">No especifique CASCADE si la tabla se va a incluir en una publicación de combinación que utiliza registros lógicos.</span><span class="sxs-lookup"><span data-stu-id="a3e17-181">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="a3e17-182">**Establecer en Null** Establece el valor en NULL si todas las columnas de clave externa de la tabla aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="a3e17-182">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="a3e17-183">**Establecer predeterminado** Establece el valor predeterminado definido para la columna si todas las columnas de clave externa de la tabla tienen valores predeterminados definidos.</span><span class="sxs-lookup"><span data-stu-id="a3e17-183">**Set Default** Sets the value to the default value that is defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
4.  <span data-ttu-id="a3e17-184">En el menú **Archivo** , haga clic en **Guardar**_table name_.</span><span class="sxs-lookup"><span data-stu-id="a3e17-184">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a3e17-185">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a3e17-185">Using Transact-SQL</span></span>  
 <span data-ttu-id="a3e17-186">**Para modificar una clave externa**</span><span class="sxs-lookup"><span data-stu-id="a3e17-186">**To modify a foreign key**</span></span>  
  
 <span data-ttu-id="a3e17-187">Para modificar una restricción FOREIGN KEY mediante Transact-SQL, primero debe eliminar la restricción FOREIGN KEY existente y, a continuación, vuelva a crearla con la nueva definición.</span><span class="sxs-lookup"><span data-stu-id="a3e17-187">To modify a FOREIGN KEY constraint by using Transact-SQL, you must first delete the existing FOREIGN KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="a3e17-188">Para obtener más información, consulte [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) y [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="a3e17-188">For more information, see [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) and [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
