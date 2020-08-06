---
title: Implementar desencadenadores DDL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DDL triggers, implementing
ms.assetid: f44e5340-1d18-40e9-828e-0ffcca091ae3
author: rothja
ms.author: jroth
ms.openlocfilehash: 110e69aca31df75d4b4d7a732de5c58556bd3e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676916"
---
# <a name="implement-ddl-triggers"></a><span data-ttu-id="ef6fe-102">Implementar desencadenadores DDL</span><span class="sxs-lookup"><span data-stu-id="ef6fe-102">Implement DDL Triggers</span></span>
  <span data-ttu-id="ef6fe-103">En este tema se ofrece información acerca de la creación y modificación de desencadenadores DDL, así como para su deshabilitación o eliminación.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-103">This topic provides information to help you create DDL triggers, modify DDL triggers, and disable or drop DDL triggers.</span></span>  
  
## <a name="creating-ddl-triggers"></a><span data-ttu-id="ef6fe-104">Crear desencadenadores DDL</span><span class="sxs-lookup"><span data-stu-id="ef6fe-104">Creating DDL Triggers</span></span>  
 <span data-ttu-id="ef6fe-105">Los desencadenadores DDL se crean con la instrucción CREATE TRIGGER de [!INCLUDE[tsql](../../includes/tsql-md.md)] para desencadenadores DDL.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-105">DDL triggers are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement for DDL triggers.</span></span>  
  
 <span data-ttu-id="ef6fe-106">**Para crear un desencadenador DDL**</span><span class="sxs-lookup"><span data-stu-id="ef6fe-106">**To create a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="ef6fe-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fe-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-trigger-transact-sql)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ef6fe-108">La capacidad de devolver conjuntos de resultados desde desencadenadores se eliminará en una versión posterior de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef6fe-108">The ability to return result sets from triggers will be removed in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ef6fe-109">Los desencadenadores que devuelven conjuntos de resultados pueden provocar un comportamiento inesperado en aplicaciones que no estén diseñadas para utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-109">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span> <span data-ttu-id="ef6fe-110">Evite la devolución de conjuntos de resultados desde desencadenadores en los nuevos trabajos de desarrollo y piense en modificar las aplicaciones que la usan actualmente.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-110">Avoid returning result sets from triggers in new development work, and plan to modify applications that currently do this.</span></span> <span data-ttu-id="ef6fe-111">Para evitar que los desencadenadores devuelvan conjuntos de resultados en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], establezca la opción [disallow results from triggers](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) en 1.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-111">To prevent triggers from returning result sets in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], set the [disallow results from triggers Option](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) to 1.</span></span> <span data-ttu-id="ef6fe-112">El valor predeterminado de esta opción será 1 en una versión futura de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef6fe-112">The default setting of this option will be 1 in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="modifying-ddl-triggers"></a><span data-ttu-id="ef6fe-113">Modificar desencadenadores DDL</span><span class="sxs-lookup"><span data-stu-id="ef6fe-113">Modifying DDL Triggers</span></span>  
 <span data-ttu-id="ef6fe-114">Si necesita modificar la definición de un desencadenador DDL, puede quitarlo y volver a crearlo, o bien volver a definirlo en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-114">If you have to modify the definition of a DDL trigger, you can either drop and re-create the trigger or redefine the existing trigger in a single step.</span></span>  
  
 <span data-ttu-id="ef6fe-115">Si cambia el nombre de un objeto al que hace referencia un desencadenador DDL, debe modificar el desencadenador para que el texto refleje el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-115">If you change the name of an object that is referenced by a DDL trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="ef6fe-116">Por lo tanto, antes de cambiar el nombre de un objeto, vea primero las dependencias del mismo para determinar si algún desencadenador va a verse afectado por el cambio propuesto.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-116">Therefore, before renaming an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="ef6fe-117">También es posible modificar un desencadenador para cifrar su definición.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-117">A trigger can also be modified to encrypt its definition.</span></span>  
  
 <span data-ttu-id="ef6fe-118">**Para modificar un desencadenador**</span><span class="sxs-lookup"><span data-stu-id="ef6fe-118">**To modify a trigger**</span></span>  
  
-   [<span data-ttu-id="ef6fe-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fe-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-trigger-transact-sql)  
  
 <span data-ttu-id="ef6fe-120">**Para ver las dependencias de un desencadenador**</span><span class="sxs-lookup"><span data-stu-id="ef6fe-120">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="ef6fe-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fe-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="ef6fe-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fe-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="ef6fe-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fe-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="disabling-and-dropping-ddl-triggers"></a><span data-ttu-id="ef6fe-124">Deshabilitar y quitar desencadenadores DDL</span><span class="sxs-lookup"><span data-stu-id="ef6fe-124">Disabling and Dropping DDL Triggers</span></span>  
 <span data-ttu-id="ef6fe-125">Puede eliminar o deshabilitar un desencadenador DDL cuando ya no lo necesite.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-125">When a DDL trigger is no longer needed, you can disable it or delete it.</span></span>  
  
 <span data-ttu-id="ef6fe-126">Al deshabilitar un desencadenador DDL, éste no se quita.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-126">Disabling a DDL trigger does not drop it.</span></span> <span data-ttu-id="ef6fe-127">Sigue siendo un objeto de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-127">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="ef6fe-128">Sin embargo, el desencadenador no se activa cuando se ejecuta una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] en la que se programó.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-128">However, the trigger will not fire when any [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on which it was programmed are run.</span></span> <span data-ttu-id="ef6fe-129">Los desencadenadores DDL deshabilitados se pueden volver a habilitar.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-129">DDL triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="ef6fe-130">La habilitación de un desencadenador DDL hace que se active tal como lo hizo cuando se creó originalmente.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-130">Enabling a DDL trigger causes it to fire in the same way the trigger did when it was originally created.</span></span> <span data-ttu-id="ef6fe-131">Cuando se crean desencadenadores DDL, se habilitan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-131">When DDL triggers are created, they are enabled by default.</span></span>  
  
 <span data-ttu-id="ef6fe-132">Cuando el desencadenador DDL se elimina, se quita de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-132">When a DDL trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="ef6fe-133">Los objetos o datos incluidos en el ámbito del desencadenador DDL no se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-133">Any objects or data upon which the DDL trigger is scoped are not affected.</span></span>  
  
 <span data-ttu-id="ef6fe-134">**Para deshabilitar un desencadenador DDL**</span><span class="sxs-lookup"><span data-stu-id="ef6fe-134">**To disable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="ef6fe-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fe-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/disable-trigger-transact-sql)  
  
-   [<span data-ttu-id="ef6fe-136">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fe-136">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="ef6fe-137">**Para habilitar un desencadenador DDL**</span><span class="sxs-lookup"><span data-stu-id="ef6fe-137">**To enable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="ef6fe-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fe-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/enable-trigger-transact-sql)  
  
-   [<span data-ttu-id="ef6fe-139">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fe-139">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="ef6fe-140">**Para eliminar un desencadenador DDL**</span><span class="sxs-lookup"><span data-stu-id="ef6fe-140">**To delete a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="ef6fe-141">DROP TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fe-141">DROP TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-trigger-transact-sql)  
  
  
