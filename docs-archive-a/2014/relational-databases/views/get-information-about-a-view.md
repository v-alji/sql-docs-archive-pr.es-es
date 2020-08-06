---
title: Obtener información sobre una vista | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.viewproperties.general.f1
helpviewer_keywords:
- views [SQL Server], status information
- metadata [SQL Server], views
- dependencies [SQL Server], views
- displaying view information
- views [SQL Server], metadata
- viewing view information
- status information [SQL Server], views
- view dependencies
ms.assetid: 05a73e33-8f85-4fb6-80c1-1b659e753403
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4277aad4c1de0140606575c7ba437408518b3c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662729"
---
# <a name="get-information-about-a-view"></a><span data-ttu-id="5bf46-102">Obtener información acerca de una vista</span><span class="sxs-lookup"><span data-stu-id="5bf46-102">Get Information About a View</span></span>
  <span data-ttu-id="5bf46-103">Puede obtener información sobre la definición o las propiedades de una vista de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bf46-103">You can gain information about a view's definition or properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5bf46-104">Es posible que necesite ver la definición de la vista para entender cómo derivan sus datos de las tablas de origen o para ver los datos que ella misma define.</span><span class="sxs-lookup"><span data-stu-id="5bf46-104">You may need to see the definition of the view to understand how its data is derived from the source tables or to see the data defined by the view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5bf46-105">Si cambia el nombre de un objeto al que hace referencia una vista, deberá modificar ésta para que el texto refleje el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="5bf46-105">If you change the name of an object referenced by a view, you must modify the view so that its text reflects the new name.</span></span> <span data-ttu-id="5bf46-106">Por lo tanto, antes de cambiar el nombre de un objeto, observe las dependencias del mismo a fin de determinar si el cambio propuesto afecta a alguna vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any views are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="5bf46-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5bf46-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5bf46-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5bf46-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5bf46-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5bf46-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5bf46-110">**Para obtener información acerca de una vista, use:**</span><span class="sxs-lookup"><span data-stu-id="5bf46-110">**To get information about a view, using:**</span></span>  
  
     [<span data-ttu-id="5bf46-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5bf46-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5bf46-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5bf46-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5bf46-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5bf46-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5bf46-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5bf46-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5bf46-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="5bf46-115">Permissions</span></span>  
 <span data-ttu-id="5bf46-116">La utilización de `sp_helptext` para devolver la definición de una vista requiere la pertenencia al rol **público** .</span><span class="sxs-lookup"><span data-stu-id="5bf46-116">Using `sp_helptext` to return the definition of a view requires membership in the **public** role.</span></span> <span data-ttu-id="5bf46-117">La utilización de `sys.sql_expression_dependencies` para buscar todas las dependencias de una vista requiere el permiso VIEW DEFINITION en la base de datos y el permiso SELECT en `sys.sql_expression_dependencies` para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5bf46-117">Using `sys.sql_expression_dependencies` to find all the dependencies on a view requires VIEW DEFINITION permission on the database and SELECT permission on `sys.sql_expression_dependencies` for the database.</span></span> <span data-ttu-id="5bf46-118">Las definiciones de objeto del sistema, como las que se devuelven en SELECT OBJECT_DEFINITION, son visibles de forma pública.</span><span class="sxs-lookup"><span data-stu-id="5bf46-118">System object definitions, like the ones returned in SELECT OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5bf46-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5bf46-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="get-view-properties-by-using-object-explorer"></a><span data-ttu-id="5bf46-120">Obtener las propiedades de la vista mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="5bf46-120">Get view properties by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="5bf46-121">En el **Explorador de objetos**, haga clic en el signo más situado junto a la base de datos que contiene la vista cuyas propiedades desea ver y haga clic en el signo más para expandir la carpeta **Vistas** .</span><span class="sxs-lookup"><span data-stu-id="5bf46-121">In **Object Explorer**, click the plus sign next to the database that contains the view to which you want to view the properties, and then click the plus sign to expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="5bf46-122">Haga clic con el botón derecho en la vista cuyas propiedades quiere ver y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5bf46-122">Right-click the view of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="5bf46-123">Las propiedades siguientes se muestran en el cuadro de diálogo **Propiedades de la vista** .</span><span class="sxs-lookup"><span data-stu-id="5bf46-123">The following properties show in the **View Properties** dialog box.</span></span>  
  
     <span data-ttu-id="5bf46-124">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="5bf46-124">**Database**</span></span>  
     <span data-ttu-id="5bf46-125">Nombre de la base de datos que contiene esta vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-125">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="5bf46-126">**Server**</span><span class="sxs-lookup"><span data-stu-id="5bf46-126">**Server**</span></span>  
     <span data-ttu-id="5bf46-127">Nombre de la instancia de servidor actual.</span><span class="sxs-lookup"><span data-stu-id="5bf46-127">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="5bf46-128">**User**</span><span class="sxs-lookup"><span data-stu-id="5bf46-128">**User**</span></span>  
     <span data-ttu-id="5bf46-129">Nombre del usuario de esta conexión.</span><span class="sxs-lookup"><span data-stu-id="5bf46-129">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="5bf46-130">**Fecha de creación**</span><span class="sxs-lookup"><span data-stu-id="5bf46-130">**Created date**</span></span>  
     <span data-ttu-id="5bf46-131">Muestra la fecha en la que se creó la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-131">Displays the date the view was created.</span></span>  
  
     <span data-ttu-id="5bf46-132">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5bf46-132">**Name**</span></span>  
     <span data-ttu-id="5bf46-133">Nombre de la vista actual.</span><span class="sxs-lookup"><span data-stu-id="5bf46-133">The name of the current view.</span></span>  
  
     <span data-ttu-id="5bf46-134">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="5bf46-134">**Schema**</span></span>  
     <span data-ttu-id="5bf46-135">Muestra el esquema al que pertenece la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-135">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="5bf46-136">**Objeto de sistema**</span><span class="sxs-lookup"><span data-stu-id="5bf46-136">**System object**</span></span>  
     <span data-ttu-id="5bf46-137">Indica si la vista es un objeto de sistema.</span><span class="sxs-lookup"><span data-stu-id="5bf46-137">Indicates whether the view is a system object.</span></span> <span data-ttu-id="5bf46-138">Los valores son True y False.</span><span class="sxs-lookup"><span data-stu-id="5bf46-138">Values are True and False.</span></span>  
  
     <span data-ttu-id="5bf46-139">**Valores NULL ANSI**</span><span class="sxs-lookup"><span data-stu-id="5bf46-139">**ANSI NULLs**</span></span>  
     <span data-ttu-id="5bf46-140">Indica si el objeto se ha creado con la opción Valores NULL ANSI.</span><span class="sxs-lookup"><span data-stu-id="5bf46-140">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="5bf46-141">**Cifrado**</span><span class="sxs-lookup"><span data-stu-id="5bf46-141">**Encrypted**</span></span>  
     <span data-ttu-id="5bf46-142">Indica si la vista está cifrada.</span><span class="sxs-lookup"><span data-stu-id="5bf46-142">Indicates whether the view is encrypted.</span></span> <span data-ttu-id="5bf46-143">Los valores son True y False.</span><span class="sxs-lookup"><span data-stu-id="5bf46-143">Values are True and False.</span></span>  
  
     <span data-ttu-id="5bf46-144">**Identificador entre comillas**</span><span class="sxs-lookup"><span data-stu-id="5bf46-144">**Quoted identifier**</span></span>  
     <span data-ttu-id="5bf46-145">Indica si el objeto se ha creado con la opción Identificador entre comillas.</span><span class="sxs-lookup"><span data-stu-id="5bf46-145">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="5bf46-146">**Enlazada a un esquema**</span><span class="sxs-lookup"><span data-stu-id="5bf46-146">**Schema bound**</span></span>  
     <span data-ttu-id="5bf46-147">Indica si la vista está enlazada a un esquema.</span><span class="sxs-lookup"><span data-stu-id="5bf46-147">Indicates whether the view is schema-bound.</span></span> <span data-ttu-id="5bf46-148">Los valores son True y False.</span><span class="sxs-lookup"><span data-stu-id="5bf46-148">Values are True and False.</span></span> <span data-ttu-id="5bf46-149">Para obtener más información sobre las vistas enlazadas a esquemas, vea la sección SCHEMABINDING de [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5bf46-149">For information about schema-bound views, see the SCHEMABINDING portion of [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
#### <a name="getting-view-properties-by-using-the-view-designer-tool"></a><span data-ttu-id="5bf46-150">Obtener propiedades de la vista con la herramienta Diseñador de vistas</span><span class="sxs-lookup"><span data-stu-id="5bf46-150">Getting view properties by using the View Designer tool</span></span>  
  
1.  <span data-ttu-id="5bf46-151">En el **Explorador de objetos**, expanda la base de datos que contiene la vista cuyas propiedades desea ver y, a continuación, expanda la carpeta **Vistas** .</span><span class="sxs-lookup"><span data-stu-id="5bf46-151">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="5bf46-152">Haga clic con el botón derecho en la vista cuyas propiedades quiere ver y seleccione **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="5bf46-152">Right-click the view of which you want to view the properties and select **Design**.</span></span>  
  
3.  <span data-ttu-id="5bf46-153">Haga clic con el botón derecho en el espacio en blanco del panel Diagrama y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5bf46-153">Right-click in the blank space of the Diagram pane and click **Properties**.</span></span>  
  
     <span data-ttu-id="5bf46-154">En el panel **Propiedades** se muestran las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="5bf46-154">The following properties show in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="5bf46-155">**(Nombre)**</span><span class="sxs-lookup"><span data-stu-id="5bf46-155">**(Name)**</span></span>  
     <span data-ttu-id="5bf46-156">Nombre de la vista actual.</span><span class="sxs-lookup"><span data-stu-id="5bf46-156">The name of the current view.</span></span>  
  
     <span data-ttu-id="5bf46-157">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="5bf46-157">**Database Name**</span></span>  
     <span data-ttu-id="5bf46-158">Nombre de la base de datos que contiene esta vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-158">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="5bf46-159">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5bf46-159">**Description**</span></span>  
     <span data-ttu-id="5bf46-160">Descripción breve de la vista actual.</span><span class="sxs-lookup"><span data-stu-id="5bf46-160">A brief description of the current view.</span></span>  
  
     <span data-ttu-id="5bf46-161">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="5bf46-161">**Schema**</span></span>  
     <span data-ttu-id="5bf46-162">Muestra el esquema al que pertenece la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-162">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="5bf46-163">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="5bf46-163">**Server Name**</span></span>  
     <span data-ttu-id="5bf46-164">Nombre de la instancia de servidor actual.</span><span class="sxs-lookup"><span data-stu-id="5bf46-164">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="5bf46-165">**Enlace a esquema**</span><span class="sxs-lookup"><span data-stu-id="5bf46-165">**Bind to Schema**</span></span>  
     <span data-ttu-id="5bf46-166">Evita que los usuarios modifiquen los objetos subyacentes que contribuyen a esta vista de cualquier forma que invalide la definición de la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-166">Prevents users from modifying the underlying objects that contribute to this view in any way that would invalidate the view definition.</span></span>  
  
     <span data-ttu-id="5bf46-167">**Determinista**</span><span class="sxs-lookup"><span data-stu-id="5bf46-167">**Deterministic**</span></span>  
     <span data-ttu-id="5bf46-168">Muestra si se puede determinar con exactitud el tipo de datos de la columna seleccionada</span><span class="sxs-lookup"><span data-stu-id="5bf46-168">Shows whether the data type of the selected column can be determined with certainty</span></span>  
  
     <span data-ttu-id="5bf46-169">**Valores DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="5bf46-169">**Distinct Values**</span></span>  
     <span data-ttu-id="5bf46-170">Especifica que la consulta filtrará los duplicados en la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-170">Specifies that the query will filter out duplicates in the view.</span></span> <span data-ttu-id="5bf46-171">Esta opción es útil cuando solo se usan algunas columnas de una tabla y dichas columnas podrían contener valores duplicados, o cuando el proceso de combinar dos o más tablas genera filas duplicadas en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5bf46-171">This option is useful when you are using only some of the columns from a table and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="5bf46-172">Elegir esta opción equivale a insertar la palabra clave DISTINCT en la instrucción en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="5bf46-172">Choosing this option is equivalent to inserting the keyword DISTINCT into the statement in the SQL pane.</span></span>  
  
     <span data-ttu-id="5bf46-173">**Extensión GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="5bf46-173">**GROUP BY Extension**</span></span>  
     <span data-ttu-id="5bf46-174">Especifica que están disponibles las opciones adicionales para vistas basadas en consultas de agregado.</span><span class="sxs-lookup"><span data-stu-id="5bf46-174">Specifies that additional options for views based on aggregate queries are available.</span></span>  
  
     <span data-ttu-id="5bf46-175">**Todas las columnas**</span><span class="sxs-lookup"><span data-stu-id="5bf46-175">**Output All Columns**</span></span>  
     <span data-ttu-id="5bf46-176">Indica si la vista seleccionada devuelve todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="5bf46-176">Shows whether all columns are returned by the selected view.</span></span> <span data-ttu-id="5bf46-177">Esto se establece en el momento de crear la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-177">This is set at the time the view is created.</span></span>  
  
     <span data-ttu-id="5bf46-178">**Comentario de SQL**</span><span class="sxs-lookup"><span data-stu-id="5bf46-178">**SQL Comment**</span></span>  
     <span data-ttu-id="5bf46-179">Muestra una descripción de las instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="5bf46-179">Shows a description of the SQL statements.</span></span> <span data-ttu-id="5bf46-180">Para ver o editar la descripción completa, haga clic en la descripción y después en el botón de puntos suspensivos **(...)** situado a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5bf46-180">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="5bf46-181">Los comentarios pueden incluir información, como quién usa la vista y cuándo.</span><span class="sxs-lookup"><span data-stu-id="5bf46-181">Your comments might include information such as who uses the view and when they use it.</span></span>  
  
     <span data-ttu-id="5bf46-182">**Especificación superior**</span><span class="sxs-lookup"><span data-stu-id="5bf46-182">**Top Specification**</span></span>  
     <span data-ttu-id="5bf46-183">Se expande para mostrar las propiedades **Superior**, **Expresión**, **Porcentaje**y **Con valores equivalentes** .</span><span class="sxs-lookup"><span data-stu-id="5bf46-183">Expands to show properties for the **Top**, **Expression**, **Percent**, and **With Ties** properties.</span></span>  
  
     <span data-ttu-id="5bf46-184">**(Superior)**</span><span class="sxs-lookup"><span data-stu-id="5bf46-184">**(Top)**</span></span>  
     <span data-ttu-id="5bf46-185">Especifica que la vista incluirá una cláusula TOP, que solo devuelve las primeras n filas o el primer n por cierto de filas en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5bf46-185">Specifies that the view will include a TOP clause, which returns only the first n rows or first n percentage of rows in the result set.</span></span> <span data-ttu-id="5bf46-186">De forma predeterminada, la vista devolverá las diez primeras filas en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5bf46-186">The default is that the view returns the first 10 rows in the result set.</span></span> <span data-ttu-id="5bf46-187">Use esto para cambiar el número de filas que se van a devolver o para especificar un porcentaje diferente.</span><span class="sxs-lookup"><span data-stu-id="5bf46-187">Use this to change the number of rows to return or to specify a different percentage</span></span>  
  
     <span data-ttu-id="5bf46-188">**Expression**</span><span class="sxs-lookup"><span data-stu-id="5bf46-188">**Expression**</span></span>  
     <span data-ttu-id="5bf46-189">Muestra qué porcentaje (si **Porcentaje** está establecido en **Sí**) o registros (si **Porcentaje** está establecido en **No**) devolverá la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-189">Shows what percent (if **Percent** is set to **Yes**) or records (if **Percent** is set to **No**) that the view will return.</span></span>  
  
     <span data-ttu-id="5bf46-190">**Porcentaje**</span><span class="sxs-lookup"><span data-stu-id="5bf46-190">**Percent**</span></span>  
     <span data-ttu-id="5bf46-191">Especifica que la consulta incluirá una cláusula **TOP** y solo devolverá el primer n por ciento de filas en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5bf46-191">Specifies that the query will include a **TOP** clause, returning only the first n percentage of rows in the result set</span></span>  
  
     <span data-ttu-id="5bf46-192">**Con valores equivalentes**</span><span class="sxs-lookup"><span data-stu-id="5bf46-192">**With Ties**</span></span>  
     <span data-ttu-id="5bf46-193">Especifica que la vista incluirá una cláusula **WITH TIES** .</span><span class="sxs-lookup"><span data-stu-id="5bf46-193">Specifies that the view will include a **WITH TIES** clause.</span></span> <span data-ttu-id="5bf46-194">**WITH TIES** resulta útil si una vista incluye una cláusula **ORDER BY** y una cláusula **TOP** basadas en un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="5bf46-194">**WITH TIES** is useful if a view includes an **ORDER BY** clause and a **TOP** clause based on percentage.</span></span> <span data-ttu-id="5bf46-195">Si se establece esta opción y el límite del porcentaje queda dentro de un conjunto de filas con valores idénticos en la cláusula **ORDER BY** , se ampliará la vista hasta que incluya todas esas filas.</span><span class="sxs-lookup"><span data-stu-id="5bf46-195">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the **ORDER BY** clause, the view is extended to include all such rows.</span></span>  
  
     <span data-ttu-id="5bf46-196">**Especificación de actualización**</span><span class="sxs-lookup"><span data-stu-id="5bf46-196">**Update Specification**</span></span>  
     <span data-ttu-id="5bf46-197">Se expande para mostrar las propiedades de **Actualizar con reglas de vista** y de **Opción CHECK** .</span><span class="sxs-lookup"><span data-stu-id="5bf46-197">Expands to show properties for the **Update Using View Rules** and **Check Option** properties.</span></span>  
  
     <span data-ttu-id="5bf46-198">**(Actualizar con reglas de vista)**</span><span class="sxs-lookup"><span data-stu-id="5bf46-198">**(Update Using View Rules)**</span></span>  
     <span data-ttu-id="5bf46-199">Indica que Microsoft Data Access Components (MDAC) traducirá todas las actualizaciones e inserciones de la vista a instrucciones SQL que hacen referencia a la vista, en lugar de a las instrucciones SQL que hacen referencia directamente a las tablas base de la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-199">Indicates that all updates and insertions to the view will be translated by Microsoft Data Access Components (MDAC) into SQL statements that refer to the view, rather than into SQL statements that refer directly to the view's base tables.</span></span>  
  
     <span data-ttu-id="5bf46-200">En algunos casos, MDAC indica las operaciones de inserción y actualización de la vista como actualizaciones y las inserta en las tablas base subyacentes de la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-200">In some cases, MDAC manifests view update and view insert operations as updates and inserts against the view's underlying base tables.</span></span> <span data-ttu-id="5bf46-201">Si selecciona **Actualizar con reglas de vista**, puede asegurarse de que MDAC generará las operaciones de inserción y actualización en la propia vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-201">By selecting **Update Using View Rules**, you can ensure that MDAC generates update and insert operations against the view itself.</span></span>  
  
     <span data-ttu-id="5bf46-202">**Opción CHECK**</span><span class="sxs-lookup"><span data-stu-id="5bf46-202">**Check Option**</span></span>  
     <span data-ttu-id="5bf46-203">Indica que al abrir esta vista y modificar el panel **Resultados** , el origen de datos comprueba si los datos agregados o modificados cumplen la cláusula **WHERE** de la definición de la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-203">Indicates that when you open this view and modify the **Results** pane, the data source checks whether the added or modified data satisfies the **WHERE** clause of the view definition.</span></span> <span data-ttu-id="5bf46-204">Si la edición no cumple la cláusula **WHERE** , aparecerá un error con más información.</span><span class="sxs-lookup"><span data-stu-id="5bf46-204">If your modification do not satisfy the **WHERE** clause, you will see an error with more information.</span></span>  
  
#### <a name="to-get-dependencies-on-the-view"></a><span data-ttu-id="5bf46-205">Para obtener las dependencias de la vista</span><span class="sxs-lookup"><span data-stu-id="5bf46-205">To get dependencies on the view</span></span>  
  
1.  <span data-ttu-id="5bf46-206">En el **Explorador de objetos**, expanda la base de datos que contiene la vista cuyas propiedades desea ver y, a continuación, expanda la carpeta **Vistas** .</span><span class="sxs-lookup"><span data-stu-id="5bf46-206">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="5bf46-207">Haga clic con el botón derecho en la vista cuyas propiedades quiere ver y seleccione **Ver dependencias**.</span><span class="sxs-lookup"><span data-stu-id="5bf46-207">Right-click the view of which you want to view the properties and select **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="5bf46-208">Seleccione **Objetos que dependen de [nombre de vista]** para mostrar los objetos que hacen referencia a la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-208">Select **Objects that depend on [view name]** to display the objects that refer to the view.</span></span>  
  
4.  <span data-ttu-id="5bf46-209">Seleccione **Objetos de los que depende [nombre de vista]** para mostrar los objetos a los que hace referencia la vista.</span><span class="sxs-lookup"><span data-stu-id="5bf46-209">Select **Objects on which [view name] depends** to display the objects that are referenced by the view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5bf46-210">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5bf46-210">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-view"></a><span data-ttu-id="5bf46-211">Para obtener la definición y propiedades de una vista</span><span class="sxs-lookup"><span data-stu-id="5bf46-211">To get the definition and properties of a view</span></span>  
  
1.  <span data-ttu-id="5bf46-212">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bf46-212">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5bf46-213">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5bf46-213">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5bf46-214">Copie y pegue uno de los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5bf46-214">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition, uses_ansi_nulls, uses_quoted_identifier, is_schema_bound  
    FROM sys.sql_modules  
    WHERE object_id = OBJECT_ID('HumanResources.vEmployee');   
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID('HumanResources.vEmployee')) AS ObjectDefinition;   
    GO  
    ```  
  
    ```  
    EXEC sp_helptext 'HumanResources.vEmployee';  
    ```  
  
 <span data-ttu-id="5bf46-215">Para obtener más información, vea [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) y [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5bf46-215">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) and [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-view"></a><span data-ttu-id="5bf46-216">Para obtener las dependencias de una vista</span><span class="sxs-lookup"><span data-stu-id="5bf46-216">To get the dependencies of a view</span></span>  
  
1.  <span data-ttu-id="5bf46-217">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bf46-217">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5bf46-218">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5bf46-218">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5bf46-219">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5bf46-219">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');  
    GO  
    ```  
  
 <span data-ttu-id="5bf46-220">Para obtener más información, vea [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) y [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5bf46-220">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
