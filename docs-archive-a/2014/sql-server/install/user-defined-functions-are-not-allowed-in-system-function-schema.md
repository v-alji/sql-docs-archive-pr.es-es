---
title: No se permiten funciones definidas por el usuario en system_function_schema | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system functions [SQL Server]
- user-defined functions [SQL Server], system
ms.assetid: 3cb54053-ef65-4558-ae96-8686b6b22f4f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7242f9fda74288a2b7354ac0550ff4966e05c555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751658"
---
# <a name="user-defined-functions-are-not-allowed-in-system_function_schema"></a><span data-ttu-id="9bff1-102">Las funciones definidas por el usuario no se permiten en system_function_schema</span><span class="sxs-lookup"><span data-stu-id="9bff1-102">User-defined functions are not allowed in system_function_schema</span></span>
  <span data-ttu-id="9bff1-103">El asesor de actualizaciones detectó funciones definidas por el usuario que son propiedad del usuario no documentado **system_function_schema**.</span><span class="sxs-lookup"><span data-stu-id="9bff1-103">The Upgrade Advisor detected user-defined functions that are owned by the undocumented user **system_function_schema**.</span></span> <span data-ttu-id="9bff1-104">No puede crear una función del sistema definida por el usuario especificando este usuario.</span><span class="sxs-lookup"><span data-stu-id="9bff1-104">You cannot create a user-defined system function by specifying this user.</span></span> <span data-ttu-id="9bff1-105">El nombre de usuario **system_function_schema** no existe y el ID. de usuario asociado a este nombre (UID = 4) está reservado para el esquema **Sys** y está restringido exclusivamente al uso interno.</span><span class="sxs-lookup"><span data-stu-id="9bff1-105">The **system_function_schema** user name does not exist, and the user ID that is associated with this name (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
## <a name="component"></a><span data-ttu-id="9bff1-106">Componente</span><span class="sxs-lookup"><span data-stu-id="9bff1-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="9bff1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bff1-107">Description</span></span>  
 <span data-ttu-id="9bff1-108">El almacenamiento de objetos del sistema y el acceso han cambiado de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="9bff1-108">System object storage and access has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="9bff1-109">Los objetos del sistema se almacenan en la base de datos de **recursos** de solo lectura y no se permiten las actualizaciones directas de objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="9bff1-109">System objects are stored in the read-only **Resource** database, and direct system object updates are not permitted.</span></span>  
  
     <span data-ttu-id="9bff1-110">Los objetos del sistema aparecen lógicamente en el esquema **Sys** de todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="9bff1-110">System objects logically appear in the **sys** schema of every database.</span></span> <span data-ttu-id="9bff1-111">Esto mantiene la capacidad de invocar funciones del sistema desde cualquier base de datos especificando un nombre de función con una sola parte.</span><span class="sxs-lookup"><span data-stu-id="9bff1-111">This maintains the ability to invoke system functions from any database by specifying a one-part function name.</span></span> <span data-ttu-id="9bff1-112">Por ejemplo, la instrucción `SELECT * FROM fn_helpcollations()` se puede ejecutar desde cualquier base de datos.</span><span class="sxs-lookup"><span data-stu-id="9bff1-112">For example, the statement `SELECT * FROM fn_helpcollations()` can be run from any database.</span></span>  
  
-   <span data-ttu-id="9bff1-113">Se ha quitado el **system_function_schema** de usuario no documentado.</span><span class="sxs-lookup"><span data-stu-id="9bff1-113">The undocumented user **system_function_schema** has been removed.</span></span>  
  
-   <span data-ttu-id="9bff1-114">El ID. de usuario asociado a **system_function_schema** (UID = 4) se reserva para el esquema **Sys** y está restringido exclusivamente al uso interno.</span><span class="sxs-lookup"><span data-stu-id="9bff1-114">The user ID associated with **system_function_schema** (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
 <span data-ttu-id="9bff1-115">Estos cambios tienen el efecto siguiente sobre las funciones del sistema definidas por el usuario:</span><span class="sxs-lookup"><span data-stu-id="9bff1-115">These changes have the following effect on user-defined system functions:</span></span>  
  
-   <span data-ttu-id="9bff1-116">Se producirá un error en las instrucciones del lenguaje de definición de datos (DDL) que hacen referencia a **system_function_schema** .</span><span class="sxs-lookup"><span data-stu-id="9bff1-116">Data Definition Language (DDL) statements that reference **system_function_schema** will fail.</span></span> <span data-ttu-id="9bff1-117">Por ejemplo, la instrucción `CREATE FUNCTION system` _ `function` \_ `schema.fn` \_ `MySystemFunction` ... no se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="9bff1-117">For example, the statement `CREATE FUNCTION system`_`function`\_`schema.fn`\_`MySystemFunction` ... will not succeed.</span></span>  
  
-   <span data-ttu-id="9bff1-118">Después de actualizar a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , los objetos existentes que son propiedad de **system_function_schema** solo se incluyen en el esquema **Sys** de la base de datos **maestra** .</span><span class="sxs-lookup"><span data-stu-id="9bff1-118">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], existing objects that are owned by **system_function_schema** are contained only in the **sys** schema of the **master** database.</span></span> <span data-ttu-id="9bff1-119">Dado que no se pueden modificar los objetos del sistema, estas funciones nunca se pueden cambiar o quitar de la base de datos **maestra** .</span><span class="sxs-lookup"><span data-stu-id="9bff1-119">Because system objects cannot be modified, these functions can never be changed or dropped from the **master** database.</span></span> <span data-ttu-id="9bff1-120">Además, estas funciones no se pueden invocar desde otras bases de datos especificando solo un nombre de función con una parte.</span><span class="sxs-lookup"><span data-stu-id="9bff1-120">Additionally, these functions cannot be invoked from other databases by specifying only a one-part function name.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9bff1-121">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="9bff1-121">Corrective Action</span></span>  
 <span data-ttu-id="9bff1-122">Antes de actualizar, lleve a cabo las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="9bff1-122">Before you upgrade , complete the following tasks:</span></span>  
  
1.  <span data-ttu-id="9bff1-123">Cambiar la propiedad de las funciones definidas por el usuario existentes a **DBO** mediante el **sp_changeobjectowner** procedimiento almacenado del sistema.</span><span class="sxs-lookup"><span data-stu-id="9bff1-123">Change the ownership of existing user-defined functions to **dbo** by using the **sp_changeobjectowner** system stored procedure.</span></span>  
  
2.  <span data-ttu-id="9bff1-124">Considere cambiar el nombre de la función para que no utilice el prefijo 'fn_'.</span><span class="sxs-lookup"><span data-stu-id="9bff1-124">Consider renaming the function so that is does not use the prefix 'fn_'.</span></span> <span data-ttu-id="9bff1-125">Esto evitará conflictos potenciales del nombre con otras funciones del sistema existentes o futuras.</span><span class="sxs-lookup"><span data-stu-id="9bff1-125">This will avoid potential name conflicts with current or future system functions.</span></span>  
  
3.  <span data-ttu-id="9bff1-126">Agregue una copia de las funciones modificadas en cada base de datos que las utilice.</span><span class="sxs-lookup"><span data-stu-id="9bff1-126">Add a copy of the modified functions in every database that uses them.</span></span>  
  
4.  <span data-ttu-id="9bff1-127">Reemplace las referencias a **system_function_schema** con **DBO** en todos los scripts que CONtengan instrucciones DDL de funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9bff1-127">Replace references to **system_function_schema** with **dbo** in all scripts that contain user-defined function DDL statements.</span></span>  
  
5.  <span data-ttu-id="9bff1-128">Modifique los scripts que invocan estas funciones para usar el nombre DBO de dos partes **.** _function_name_o el nombre de tres partes _database_name_**.** DBO. *function_name*.</span><span class="sxs-lookup"><span data-stu-id="9bff1-128">Modify scripts that invoke these functions to use either the two-part name dbo **.**_function_name_, or the three-part name _database_name_**.** dbo.*function_name*.</span></span>  
  
 <span data-ttu-id="9bff1-129">Para obtener más información, vea los temas siguientes en los Libros en pantalla de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="9bff1-129">For more information, see the following topics in SQL Server Books Online:</span></span>  
  
-   <span data-ttu-id="9bff1-130">"sp_changeobjectowner"</span><span class="sxs-lookup"><span data-stu-id="9bff1-130">"sp_changeobjectowner"</span></span>  
  
-   <span data-ttu-id="9bff1-131">"Separación de esquemas de usuario"</span><span class="sxs-lookup"><span data-stu-id="9bff1-131">"User-schema Separation"</span></span>  
  
-   <span data-ttu-id="9bff1-132">"Base de datos Resource"</span><span class="sxs-lookup"><span data-stu-id="9bff1-132">"Resource Database"</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bff1-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9bff1-133">See Also</span></span>  
 <span data-ttu-id="9bff1-134">[SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="9bff1-134">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="9bff1-135">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="9bff1-135">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 <span data-ttu-id="9bff1-136">[Quitar instrucciones que modifican objetos del sistema](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span><span class="sxs-lookup"><span data-stu-id="9bff1-136">[Remove statements that modify system objects](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span></span>  
 [<span data-ttu-id="9bff1-137">Quitar instrucciones que quiten objetos del sistema</span><span class="sxs-lookup"><span data-stu-id="9bff1-137">Remove statements that drop system objects</span></span>](../../../2014/sql-server/install/remove-statements-that-drop-system-objects.md)  
  
  
