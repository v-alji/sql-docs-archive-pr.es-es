---
title: Usar sinónimos (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synonyms [SQL Server], about synonyms
ms.assetid: 6210e1d5-075f-47e4-ac8d-f84bcf26fbc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3494f4f5b13c422efb8e2a39597e131c10d81ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672872"
---
# <a name="synonyms-database-engine"></a><span data-ttu-id="05e2f-102">Usar sinónimos (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="05e2f-102">Synonyms (Database Engine)</span></span>
  <span data-ttu-id="05e2f-103">Un sinónimo es un objeto de base de datos que sirve para los siguientes objetivos:</span><span class="sxs-lookup"><span data-stu-id="05e2f-103">A synonym is a database object that serves the following purposes:</span></span>  
  
-   <span data-ttu-id="05e2f-104">Proporciona un nombre alternativo para otro objeto de base de datos, denominado objeto base, que puede existir en un servidor local o remoto.</span><span class="sxs-lookup"><span data-stu-id="05e2f-104">Provides an alternative name for another database object, referred to as the base object, that can exist on a local or remote server.</span></span>  
  
-   <span data-ttu-id="05e2f-105">Proporciona una capa de abstracción que protege una aplicación cliente de cambios realizados en el nombre o la ubicación del objeto base.</span><span class="sxs-lookup"><span data-stu-id="05e2f-105">Provides a layer of abstraction that protects a client application from changes made to the name or location of the base object.</span></span>  
  
 <span data-ttu-id="05e2f-106">Por ejemplo, suponga la tabla **Employee** de [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], situada en un servidor denominado **Server1**.</span><span class="sxs-lookup"><span data-stu-id="05e2f-106">For example, consider the **Employee** table of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], located on a server named **Server1**.</span></span> <span data-ttu-id="05e2f-107">Para hacer referencia a esta tabla desde otro servidor, **Server2**, una aplicación cliente tendría que usar el nombre de cuatro partes **Server1.AdventureWorks.Person.Employee**.</span><span class="sxs-lookup"><span data-stu-id="05e2f-107">To reference this table from another server, **Server2**, a client application would have to use the four-part name **Server1.AdventureWorks.Person.Employee**.</span></span> <span data-ttu-id="05e2f-108">Además, si la ubicación de la tabla cambiara, por ejemplo a otro servidor, la aplicación cliente debería modificarse para reflejar ese cambio.</span><span class="sxs-lookup"><span data-stu-id="05e2f-108">Also, if the location of the table were to change, for example, to another server, the client application would have to be modified to reflect that change.</span></span>  
  
 <span data-ttu-id="05e2f-109">Para solucionar ambas cosas, puede crear un sinónimo, **EmpTable**, en **Server2** para la tabla **Employee** en **Server1**.</span><span class="sxs-lookup"><span data-stu-id="05e2f-109">To address both these issues, you can create a synonym, **EmpTable**, on **Server2** for the **Employee** table on **Server1**.</span></span> <span data-ttu-id="05e2f-110">Ahora la aplicación cliente solo tiene que usar el nombre de una parte, **EmpTable**, para hacer referencia a la tabla **Employee** .</span><span class="sxs-lookup"><span data-stu-id="05e2f-110">Now, the client application only has to use the single-part name, **EmpTable**, to reference the **Employee** table.</span></span> <span data-ttu-id="05e2f-111">Además, si la ubicación de la tabla **Employee** cambia, tendrá que modificar el sinónimo, **EmpTable**, para que apunte a la nueva ubicación de la tabla **Employee** .</span><span class="sxs-lookup"><span data-stu-id="05e2f-111">Also, if the location of the **Employee** table changes, you will have to modify the synonym, **EmpTable**, to point to the new location of the **Employee** table.</span></span> <span data-ttu-id="05e2f-112">Puesto que no hay ninguna instrucción ALTER SYNONYM, primero tiene que quitar el sinónimo, **EmpTable**y, luego, volver a crearlo con el mismo nombre, pero apuntando a la nueva ubicación de **Employee**.</span><span class="sxs-lookup"><span data-stu-id="05e2f-112">Because there is no ALTER SYNONYM statement, you first have to drop the synonym, **EmpTable**, and then re-create the synonym with the same name, but point the synonym to the new location of **Employee**.</span></span>  
  
 <span data-ttu-id="05e2f-113">Un sinónimo pertenece a un esquema y, al igual que otros objetos de un esquema, el nombre de un sinónimo debe ser único.</span><span class="sxs-lookup"><span data-stu-id="05e2f-113">A synonym belongs to a schema, and like other objects in a schema, the name of a synonym must be unique.</span></span> <span data-ttu-id="05e2f-114">Puede crear sinónimos para los siguientes objetos de base de datos:</span><span class="sxs-lookup"><span data-stu-id="05e2f-114">You can create synonyms for the following database objects:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05e2f-115">Procedimiento almacenado del ensamblado (CLR)</span><span class="sxs-lookup"><span data-stu-id="05e2f-115">Assembly (CLR) stored procedure</span></span>|<span data-ttu-id="05e2f-116">Función con valores de tabla del ensamblado (CLR)</span><span class="sxs-lookup"><span data-stu-id="05e2f-116">Assembly (CLR) table-valued function</span></span>|  
|<span data-ttu-id="05e2f-117">Función escalar del ensamblado (CLR)</span><span class="sxs-lookup"><span data-stu-id="05e2f-117">Assembly (CLR) scalar function</span></span>|<span data-ttu-id="05e2f-118">Función de agregado del ensamblado (CLR)</span><span class="sxs-lookup"><span data-stu-id="05e2f-118">Assembly (CLR) aggregate functions</span></span>|  
|<span data-ttu-id="05e2f-119">Procedimiento de filtro de replicación</span><span class="sxs-lookup"><span data-stu-id="05e2f-119">Replication-filter-procedure</span></span>|<span data-ttu-id="05e2f-120">Procedimiento almacenado extendido</span><span class="sxs-lookup"><span data-stu-id="05e2f-120">Extended stored procedure</span></span>|  
|<span data-ttu-id="05e2f-121">Función escalar de SQL</span><span class="sxs-lookup"><span data-stu-id="05e2f-121">SQL scalar function</span></span>|<span data-ttu-id="05e2f-122">Función con valores de tabla de SQL</span><span class="sxs-lookup"><span data-stu-id="05e2f-122">SQL table-valued function</span></span>|  
|<span data-ttu-id="05e2f-123">Función SQL insertada con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="05e2f-123">SQL inline-tabled-valued function</span></span>|<span data-ttu-id="05e2f-124">Procedimiento almacenado de SQL</span><span class="sxs-lookup"><span data-stu-id="05e2f-124">SQL stored procedure</span></span>|  
|<span data-ttu-id="05e2f-125">Ver</span><span class="sxs-lookup"><span data-stu-id="05e2f-125">View</span></span>|<span data-ttu-id="05e2f-126">Tabla<sup>1</sup> (definida por el usuario)</span><span class="sxs-lookup"><span data-stu-id="05e2f-126">Table<sup>1</sup> (User-defined)</span></span>|  
  
 <span data-ttu-id="05e2f-127"><sup>1</sup> incluye tablas temporales locales y globales</span><span class="sxs-lookup"><span data-stu-id="05e2f-127"><sup>1</sup> Includes local and global temporary tables</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05e2f-128">No pueden usarse nombres de cuatro partes para objetos base de función.</span><span class="sxs-lookup"><span data-stu-id="05e2f-128">Four-part names for function base objects are not supported.</span></span>  
  
 <span data-ttu-id="05e2f-129">Un sinónimo no puede ser el objeto base de otro sinónimo y un sinónimo no puede hacer referencia a una función de agregado definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="05e2f-129">A synonym cannot be the base object for another synonym, and a synonym cannot reference a user-defined aggregate function.</span></span>  
  
 <span data-ttu-id="05e2f-130">El enlace entre un sinónimo y su objeto base solo es mediante el nombre.</span><span class="sxs-lookup"><span data-stu-id="05e2f-130">The binding between a synonym and its base object is by name only.</span></span> <span data-ttu-id="05e2f-131">Todas las comprobaciones de existencia, tipo y permisos en el objeto base se posponen hasta la ejecución.</span><span class="sxs-lookup"><span data-stu-id="05e2f-131">All existence, type, and permissions checking on the base object is deferred until run time.</span></span> <span data-ttu-id="05e2f-132">Por tanto, el objeto base puede modificarse, quitarse o quitarse y reemplazarse por otro objeto con el mismo nombre que el objeto base original.</span><span class="sxs-lookup"><span data-stu-id="05e2f-132">Therefore, the base object can be modified, dropped, or dropped and replaced by another object that has the same name as the original base object.</span></span> <span data-ttu-id="05e2f-133">Por ejemplo, suponga un sinónimo, **MyContacts**, que hace referencia a la tabla **Person.Contact** de [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05e2f-133">For example, consider a synonym, **MyContacts**, that references the **Person.Contact** table in [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span></span> <span data-ttu-id="05e2f-134">Si la tabla **Contact** se quita y reemplaza por una vista llamada **Person.Contact**, **MyContacts** ahora hace referencia a la vista **Person.Contact** .</span><span class="sxs-lookup"><span data-stu-id="05e2f-134">If the **Contact** table is dropped and replaced by a view named **Person.Contact**, **MyContacts** now references the **Person.Contact** view.</span></span>  
  
 <span data-ttu-id="05e2f-135">Las referencias a sinónimos no están enlazadas a esquema.</span><span class="sxs-lookup"><span data-stu-id="05e2f-135">References to synonyms are not schema-bound.</span></span> <span data-ttu-id="05e2f-136">Por tanto, un sinónimo puede quitarse en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="05e2f-136">Therefore, a synonym can be dropped at any time.</span></span> <span data-ttu-id="05e2f-137">Sin embargo, al quitar un sinónimo se corre el riesgo de dejar referencias pendientes al sinónimo quitado.</span><span class="sxs-lookup"><span data-stu-id="05e2f-137">However, by dropping a synonym, you run the risk of leaving dangling references to the synonym that was dropped.</span></span> <span data-ttu-id="05e2f-138">Estas referencias solo se encontrarán en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="05e2f-138">These references will only be found at run time.</span></span>  
  
## <a name="synonyms-and-schemas"></a><span data-ttu-id="05e2f-139">Sinónimos y esquemas</span><span class="sxs-lookup"><span data-stu-id="05e2f-139">Synonyms and Schemas</span></span>  
 <span data-ttu-id="05e2f-140">Si tiene un esquema predeterminado que no posee y desea crear un sinónimo, debe calificar el nombre del sinónimo con el nombre de un esquema que posea.</span><span class="sxs-lookup"><span data-stu-id="05e2f-140">If you have a default schema that you do not own and want to create a synonym, you must qualify the synonym name with the name of a schema that you do own.</span></span> <span data-ttu-id="05e2f-141">Por ejemplo, si posee un esquema **x**, pero **y** es su esquema predeterminado y usa la instrucción CREATE SYNONYM, debe poner un prefijo al nombre del sinónimo con el esquema **x**, en lugar de asignar un nombre al sinónimo mediante un nombre con una sola parte.</span><span class="sxs-lookup"><span data-stu-id="05e2f-141">For example, if you own a schema **x**, but **y** is your default schema and you use the CREATE SYNONYM statement, you must prefix the name of the synonym with the schema **x**, instead of naming the synonym by using a single-part name.</span></span> <span data-ttu-id="05e2f-142">Para obtener más información sobre cómo crear sinónimos, vea [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="05e2f-142">For more information about how to create synonyms, see [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql).</span></span>  
  
## <a name="granting-permissions-on-a-synonym"></a><span data-ttu-id="05e2f-143">Conceder permisos para un sinónimo</span><span class="sxs-lookup"><span data-stu-id="05e2f-143">Granting Permissions on a Synonym</span></span>  
 <span data-ttu-id="05e2f-144">Solo los propietarios de los sinónimos, miembros de **db_owner**o miembros de **db_ddladmin** pueden conceder permiso para un sinónimo.</span><span class="sxs-lookup"><span data-stu-id="05e2f-144">Only synonym owners, members of **db_owner**, or members of **db_ddladmin** can grant permission on a synonym.</span></span>  
  
 <span data-ttu-id="05e2f-145">Puede conceder (GRANT), denegar (DENY) o revocar (REVOKE) todos o cualquiera de los siguientes permisos para un sinónimo:</span><span class="sxs-lookup"><span data-stu-id="05e2f-145">You can GRANT, DENY, REVOKE all or any of the following permissions on a synonym:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05e2f-146">CONTROL</span><span class="sxs-lookup"><span data-stu-id="05e2f-146">CONTROL</span></span>|<span data-ttu-id="05e2f-147">Delete</span><span class="sxs-lookup"><span data-stu-id="05e2f-147">DELETE</span></span>|  
|<span data-ttu-id="05e2f-148">Ejecute</span><span class="sxs-lookup"><span data-stu-id="05e2f-148">EXECUTE</span></span>|<span data-ttu-id="05e2f-149">INSERT</span><span class="sxs-lookup"><span data-stu-id="05e2f-149">INSERT</span></span>|  
|<span data-ttu-id="05e2f-150">SELECT</span><span class="sxs-lookup"><span data-stu-id="05e2f-150">SELECT</span></span>|<span data-ttu-id="05e2f-151">TAKE OWNERSHIP</span><span class="sxs-lookup"><span data-stu-id="05e2f-151">TAKE OWNERSHIP</span></span>|  
|<span data-ttu-id="05e2f-152">UPDATE</span><span class="sxs-lookup"><span data-stu-id="05e2f-152">UPDATE</span></span>|<span data-ttu-id="05e2f-153">VIEW DEFINITION</span><span class="sxs-lookup"><span data-stu-id="05e2f-153">VIEW DEFINITION</span></span>|  
  
## <a name="using-synonyms"></a><span data-ttu-id="05e2f-154">Usar sinónimos</span><span class="sxs-lookup"><span data-stu-id="05e2f-154">Using Synonyms</span></span>  
 <span data-ttu-id="05e2f-155">Puede usar sinónimos en lugar de los objetos base a los que se hace referencia en varias instrucciones SQL y contextos de expresión.</span><span class="sxs-lookup"><span data-stu-id="05e2f-155">You can use synonyms in place of their referenced base object in several SQL statements and expression contexts.</span></span> <span data-ttu-id="05e2f-156">La siguiente tabla contiene una lista de estas instrucciones y contextos de expresiones:</span><span class="sxs-lookup"><span data-stu-id="05e2f-156">The following table contains a list of these statements and expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05e2f-157">SELECT</span><span class="sxs-lookup"><span data-stu-id="05e2f-157">SELECT</span></span>|<span data-ttu-id="05e2f-158">INSERT</span><span class="sxs-lookup"><span data-stu-id="05e2f-158">INSERT</span></span>|  
|<span data-ttu-id="05e2f-159">UPDATE</span><span class="sxs-lookup"><span data-stu-id="05e2f-159">UPDATE</span></span>|<span data-ttu-id="05e2f-160">Delete</span><span class="sxs-lookup"><span data-stu-id="05e2f-160">DELETE</span></span>|  
|<span data-ttu-id="05e2f-161">Ejecute</span><span class="sxs-lookup"><span data-stu-id="05e2f-161">EXECUTE</span></span>|<span data-ttu-id="05e2f-162">Subselecciones</span><span class="sxs-lookup"><span data-stu-id="05e2f-162">Sub-selects</span></span>|  
  
 <span data-ttu-id="05e2f-163">Al trabajar con sinónimos en los contextos indicados anteriormente, el objeto base se ve afectado.</span><span class="sxs-lookup"><span data-stu-id="05e2f-163">When you are working with synonyms in the contexts previously stated, the base object is affected.</span></span> <span data-ttu-id="05e2f-164">Por ejemplo, si un sinónimo hace referencia a un objeto base que es una tabla e inserta una fila en el sinónimo, realmente está insertando una fila en la tabla a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="05e2f-164">For example, if a synonym references a base object that is a table and you insert a row into the synonym, you are actually inserting a row into the referenced table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05e2f-165">No se puede hacer referencia a un sinónimo situado en un servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="05e2f-165">You cannot reference a synonym that is located on a linked server.</span></span>  
  
 <span data-ttu-id="05e2f-166">Puede usar un sinónimo como parámetro para la función OBJECT_ID; sin embargo, la función devuelve el identificador de objeto del sinónimo y no el objeto base.</span><span class="sxs-lookup"><span data-stu-id="05e2f-166">You can use a synonym as the parameter for the OBJECT_ID function; however, the function returns the object ID of the synonym, not the base object.</span></span>  
  
 <span data-ttu-id="05e2f-167">No puede hacer referencia a un sinónimo en una instrucción DDL.</span><span class="sxs-lookup"><span data-stu-id="05e2f-167">You cannot reference a synonym in a DDL statement.</span></span> <span data-ttu-id="05e2f-168">Por ejemplo, las instrucciones siguientes, que hacen referencia a un sinónimo denominado `dbo.MyProduct`, generan errores:</span><span class="sxs-lookup"><span data-stu-id="05e2f-168">For example, the following statements, which reference a synonym named `dbo.MyProduct`, generate errors:</span></span>  
  
```  
ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null;  
EXEC ('ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null');  
```  
  
 <span data-ttu-id="05e2f-169">Las siguientes instrucciones de permisos solo están asociadas al sinónimo, no al objeto base:</span><span class="sxs-lookup"><span data-stu-id="05e2f-169">The following permission statements are associated only with the synonym and not the base object:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05e2f-170">GRANT</span><span class="sxs-lookup"><span data-stu-id="05e2f-170">GRANT</span></span>|<span data-ttu-id="05e2f-171">DENEGAR</span><span class="sxs-lookup"><span data-stu-id="05e2f-171">DENY</span></span>|  
|<span data-ttu-id="05e2f-172">REVOKE</span><span class="sxs-lookup"><span data-stu-id="05e2f-172">REVOKE</span></span>||  
  
 <span data-ttu-id="05e2f-173">Los sinónimos no están enlazados al esquema, por lo que los siguientes contextos de expresión enlazados al esquema no pueden hacer referencia a sinónimos:</span><span class="sxs-lookup"><span data-stu-id="05e2f-173">Synonyms are not schema-bound and, therefore, cannot be referenced by the following schema-bound expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05e2f-174">CHECK, restricciones</span><span class="sxs-lookup"><span data-stu-id="05e2f-174">CHECK constraints</span></span>|<span data-ttu-id="05e2f-175">Columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="05e2f-175">Computed columns</span></span>|  
|<span data-ttu-id="05e2f-176">Expresiones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="05e2f-176">Default expressions</span></span>|<span data-ttu-id="05e2f-177">Expresiones de reglas</span><span class="sxs-lookup"><span data-stu-id="05e2f-177">Rule expressions</span></span>|  
|<span data-ttu-id="05e2f-178">Vistas enlazadas a esquema</span><span class="sxs-lookup"><span data-stu-id="05e2f-178">Schema-bound views</span></span>|<span data-ttu-id="05e2f-179">Funciones enlazadas a esquema</span><span class="sxs-lookup"><span data-stu-id="05e2f-179">Schema-bound functions</span></span>|  
  
 <span data-ttu-id="05e2f-180">Para obtener más información sobre las funciones enlazadas a esquema, vea [Crear funciones definidas por el usuario &#40;motor de base de datos&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="05e2f-180">For more information about schema-bound functions, see [Create User-defined Functions &#40;Database Engine&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span></span>  
  
## <a name="getting-information-about-synonyms"></a><span data-ttu-id="05e2f-181">Obtener información acerca de sinónimos</span><span class="sxs-lookup"><span data-stu-id="05e2f-181">Getting Information About Synonyms</span></span>  
 <span data-ttu-id="05e2f-182">La vista de catálogo sys.synonyms contiene una entrada para cada sinónimo de una base de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="05e2f-182">The sys.synonyms catalog view contains an entry for each synonym in a given database.</span></span> <span data-ttu-id="05e2f-183">Esta vista de catálogo expone metadatos de sinónimos, como el nombre del sinónimo y el nombre del objeto base.</span><span class="sxs-lookup"><span data-stu-id="05e2f-183">This catalog view exposes synonym metadata such as the name of the synonym and the name of the base object.</span></span> <span data-ttu-id="05e2f-184">Para obtener más información acerca de la `sys.synonyms` vista de catálogo, vea [Sys. sinónimos &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="05e2f-184">For more information about the `sys.synonyms` catalog view, see [sys.synonyms &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span></span>  
  
 <span data-ttu-id="05e2f-185">Mediante las propiedades extendidas, puede agregar texto descriptivo o instrucciones, máscaras de entrada y reglas de formato como propiedades de un sinónimo.</span><span class="sxs-lookup"><span data-stu-id="05e2f-185">By using extended properties, you can add descriptive or instructional text, input masks, and formatting rules as properties of a synonym.</span></span> <span data-ttu-id="05e2f-186">Puesto que la propiedad se almacena en la base de datos, todas las aplicaciones que leen la propiedad pueden evaluar el objeto de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="05e2f-186">Because the property is stored in the database, all applications that read the property can evaluate the object in the same way.</span></span> <span data-ttu-id="05e2f-187">Para obtener más información, vea [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="05e2f-187">For more information, see [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span></span>  
  
 <span data-ttu-id="05e2f-188">Para buscar el tipo base del objeto base de un sinónimo, utilice la función OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="05e2f-188">To find the base type of the base object of a synonym, use the OBJECTPROPERTYEX function.</span></span> <span data-ttu-id="05e2f-189">Para obtener más información, vea [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="05e2f-189">For more information, see [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="05e2f-190">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="05e2f-190">Examples</span></span>  
 <span data-ttu-id="05e2f-191">En el siguiente ejemplo se devuelve el tipo base del objeto base de un sinónimo; el objeto base es un objeto local.</span><span class="sxs-lookup"><span data-stu-id="05e2f-191">The following example returns the base type of a synonym's base object that is a local object.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyEmployee   
FOR AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyEmployee'), 'BaseType') AS BaseType;  
```  
  
 <span data-ttu-id="05e2f-192">En el siguiente ejemplo se devuelve el tipo base del objeto base de un sinónimo; el objeto base es un objeto remoto ubicado en un servidor llamado `Server1`.</span><span class="sxs-lookup"><span data-stu-id="05e2f-192">The following example returns the base type of a synonym's base object that is a remote object located on a server named `Server1`.</span></span>  
  
```  
EXECUTE sp_addlinkedserver Server1;  
GO  
CREATE SYNONYM MyRemoteEmployee  
FOR Server1.AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyRemoteEmployee'), 'BaseType') AS BaseType;  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="05e2f-193">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="05e2f-193">Related Content</span></span>  
 [<span data-ttu-id="05e2f-194">Creación de sinónimos</span><span class="sxs-lookup"><span data-stu-id="05e2f-194">Create Synonyms</span></span>](create-synonyms.md)  
  
 [<span data-ttu-id="05e2f-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="05e2f-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
  
 [<span data-ttu-id="05e2f-196">DROP SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="05e2f-196">DROP SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-synonym-transact-sql)  
  
  
