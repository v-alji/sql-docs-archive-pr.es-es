---
title: Cuadro de diálogo Restricción CHECK (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraint
ms.assetid: ad0bbf7f-b0de-406a-bd0a-cb779816b101
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7244984b869a1c68e597984a1cd03e16e53d0306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661758"
---
# <a name="check-constraint-dialog-box-visual-database-tools"></a><span data-ttu-id="20f96-102">Restricción CHECK (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="20f96-102">Check Constraint Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="20f96-103">Este cuadro de diálogo aparece cuando se hace clic con el botón derecho en una cuadrícula de definición de tabla en el Diseñador de tablas y, a continuación, se hace clic en **Restricciones CHECK**.</span><span class="sxs-lookup"><span data-stu-id="20f96-103">This dialog box appears when you right-click a table definition grid in Table Designer and click **Check Constraints**.</span></span> <span data-ttu-id="20f96-104">Este cuadro de diálogo contiene un conjunto de propiedades para las restricciones no UNIQUE anexadas a las tablas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="20f96-104">The dialog box contains a set of properties for non-unique constraints attached to the tables in your database.</span></span> <span data-ttu-id="20f96-105">Las propiedades que se aplican a las restricciones UNIQUE aparecen en el cuadro de diálogo **Índices o claves** .</span><span class="sxs-lookup"><span data-stu-id="20f96-105">Properties applying to unique constraints appear in the **Indexes/Keys** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20f96-106">Si se publica la tabla para la replicación, debe modificar el esquema mediante la instrucción Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) u Objetos de administración de SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="20f96-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="20f96-107">Si se modifica el esquema mediante el Diseñador de tablas o el Diseñador de diagramas de base de datos, se intentará eliminar la tabla y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="20f96-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="20f96-108">No se pueden eliminar objetos publicados, por lo que la modificación del esquema generará un error.</span><span class="sxs-lookup"><span data-stu-id="20f96-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="20f96-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="20f96-109">Options</span></span>  
 <span data-ttu-id="20f96-110">**Restricciones CHECK seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="20f96-110">**Selected Check Constraints**</span></span>  
 <span data-ttu-id="20f96-111">Muestra las restricciones CHECK disponibles.</span><span class="sxs-lookup"><span data-stu-id="20f96-111">Lists available check constraints.</span></span> <span data-ttu-id="20f96-112">Para ver las propiedades de una restricción, seleccione esta restricción en la lista.</span><span class="sxs-lookup"><span data-stu-id="20f96-112">To view the properties of a constraint, select it in the list.</span></span>  
  
 <span data-ttu-id="20f96-113">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="20f96-113">**Add**</span></span>  
 <span data-ttu-id="20f96-114">Crea una nueva restricción en la tabla de base de datos seleccionada y proporciona el nombre predeterminado y otros valores para la restricción.</span><span class="sxs-lookup"><span data-stu-id="20f96-114">Create a new constraint for the selected database table and provide a default name and other values for the constraint.</span></span> <span data-ttu-id="20f96-115">La restricción no será válida hasta que se especifique una expresión en la restricción.</span><span class="sxs-lookup"><span data-stu-id="20f96-115">The constraint will not become valid until an expression is entered for the constraint.</span></span>  
  
 <span data-ttu-id="20f96-116">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="20f96-116">**Delete**</span></span>  
 <span data-ttu-id="20f96-117">Elimina la restricción seleccionada de la tabla.</span><span class="sxs-lookup"><span data-stu-id="20f96-117">Remove the selected constraint from the table.</span></span> <span data-ttu-id="20f96-118">Para cancelar la adición de una restricción CHECK, utilice este botón para eliminar la restricción.</span><span class="sxs-lookup"><span data-stu-id="20f96-118">To cancel the addition of a check constraint, use this button to remove the constraint.</span></span>  
  
 <span data-ttu-id="20f96-119">**Categoría General**</span><span class="sxs-lookup"><span data-stu-id="20f96-119">**General Category**</span></span>  
 <span data-ttu-id="20f96-120">Se expande para mostrar el campo de la propiedad **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="20f96-120">Expand to show the **Expression** property field.</span></span>  
  
 <span data-ttu-id="20f96-121">**Expression**</span><span class="sxs-lookup"><span data-stu-id="20f96-121">**Expression**</span></span>  
 <span data-ttu-id="20f96-122">Muestra la expresión de la restricción CHECK seleccionada.</span><span class="sxs-lookup"><span data-stu-id="20f96-122">Displays the expression for the selected check constraint.</span></span> <span data-ttu-id="20f96-123">En las restricciones nuevas, debe especificar la expresión antes de salir del cuadro.</span><span class="sxs-lookup"><span data-stu-id="20f96-123">For new constraints, you must enter the expression before exiting this box.</span></span> <span data-ttu-id="20f96-124">También puede editar las restricciones CHECK existentes.</span><span class="sxs-lookup"><span data-stu-id="20f96-124">You can also edit existing check constraints.</span></span> <span data-ttu-id="20f96-125">Para más información, consulte [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="20f96-125">For more information, see [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="20f96-126">**Categoría Identidad**</span><span class="sxs-lookup"><span data-stu-id="20f96-126">**Identity Category**</span></span>  
 <span data-ttu-id="20f96-127">Se expande para mostrar las propiedades de **Nombre** y **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="20f96-127">Expand to show properties for **Name** and **Description**.</span></span>  
  
 <span data-ttu-id="20f96-128">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="20f96-128">**Name**</span></span>  
 <span data-ttu-id="20f96-129">Muestra el nombre de la restricción CHECK seleccionada.</span><span class="sxs-lookup"><span data-stu-id="20f96-129">Shows the name of the selected check constraint.</span></span> <span data-ttu-id="20f96-130">Para cambiar el nombre de esta restricción, escriba el texto directamente en el campo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="20f96-130">To change the name of this constraint, type the text directly in the property field.</span></span>  
  
 <span data-ttu-id="20f96-131">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="20f96-131">**Description**</span></span>  
 <span data-ttu-id="20f96-132">Descripción de esta restricción CHECK.</span><span class="sxs-lookup"><span data-stu-id="20f96-132">Describing this check constraint.</span></span> <span data-ttu-id="20f96-133">Puede editar la descripción si escribe en el campo de la propiedad o puede hacer clic en el botón de puntos suspensivos ( **...** ) que aparece a la derecha del campo de propiedad y editar la descripción en el cuadro de diálogo **Propiedad Description**.</span><span class="sxs-lookup"><span data-stu-id="20f96-133">You can edit the description by typing into the property field or you can click the ellipsis button (**...**) that appears to the right of the property field and edit the description in the **Description Property** dialog box.</span></span>  
  
 <span data-ttu-id="20f96-134">**Categoría Diseñador de tablas**</span><span class="sxs-lookup"><span data-stu-id="20f96-134">**Table Designer Category**</span></span>  
 <span data-ttu-id="20f96-135">Se expande para mostrar las propiedades de **Comprobar datos existentes al crear o al habilitar de nuevo**y **Exigir para INSERTs y UPDATEs**y **Exigir para replicación**.</span><span class="sxs-lookup"><span data-stu-id="20f96-135">Expand to show properties for **Check Existing Data on Creation or Re-enabling**, **Enforce For Inserts And Updates**, and **Enforce Replication**.</span></span>  
  
 <span data-ttu-id="20f96-136">**Check Existing Data On Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="20f96-136">**Check Existing Data On Creation or Re-Enabling**</span></span>  
 <span data-ttu-id="20f96-137">Especifica si todos los datos preexistentes (los existentes en la tabla antes de que se cree la restricción) se comprueban con la restricción.</span><span class="sxs-lookup"><span data-stu-id="20f96-137">Specify whether all pre-existing data (data existing in the table before the constraint is created) is verified against the constraint.</span></span>  
  
 <span data-ttu-id="20f96-138">**Exigir para INSERTs y UPDATEs**</span><span class="sxs-lookup"><span data-stu-id="20f96-138">**Enforce For Inserts And Updates**</span></span>  
 <span data-ttu-id="20f96-139">Especifica si se exigirá la restricción cuando se inserten o se actualicen datos en la tabla.</span><span class="sxs-lookup"><span data-stu-id="20f96-139">Specify whether the constraint is enforced when data is inserted into or updated in the table.</span></span>  
  
 <span data-ttu-id="20f96-140">**Exigir para replicación**</span><span class="sxs-lookup"><span data-stu-id="20f96-140">**Enforce For Replication**</span></span>  
 <span data-ttu-id="20f96-141">Indica si se exigirá la restricción cuando un agente de replicación realice una inserción o actualización en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="20f96-141">Indicates whether to enforce the constraint when a replication agent performs an insert or update on this table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f96-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20f96-142">See Also</span></span>  
 <span data-ttu-id="20f96-143">[Restricciones UNIQUE y restricciones check](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="20f96-143">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="20f96-144">Cuadro de diálogo índices y claves &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="20f96-144">Indexes and Keys Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
