---
title: Índices en columnas calculadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, index creation
- index creation [SQL Server], computed columns
- imprecise columns
- persisted computed columns
- precise [SQL Server]
ms.assetid: 8d17ac9c-f3af-4bbb-9cc1-5cf647e994c4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ecbca9e7838c4c9395a8bcb6e11351c40f7037f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750958"
---
# <a name="indexes-on-computed-columns"></a><span data-ttu-id="63390-102">Índices en columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="63390-102">Indexes on Computed Columns</span></span>
  <span data-ttu-id="63390-103">Los índices se pueden definir en columnas calculadas si se cumplen estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="63390-103">You can define indexes on computed columns as long as the following requirements are met:</span></span>  
  
-   <span data-ttu-id="63390-104">Requisitos de propiedad</span><span class="sxs-lookup"><span data-stu-id="63390-104">Ownership requirements</span></span>  
  
-   <span data-ttu-id="63390-105">Requisitos de determinismo</span><span class="sxs-lookup"><span data-stu-id="63390-105">Determinism requirements</span></span>  
  
-   <span data-ttu-id="63390-106">Requisitos de precisión</span><span class="sxs-lookup"><span data-stu-id="63390-106">Precision requirements</span></span>  
  
-   <span data-ttu-id="63390-107">Requisitos de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="63390-107">Data type requirements</span></span>  
  
-   <span data-ttu-id="63390-108">Requisitos de la opción SET</span><span class="sxs-lookup"><span data-stu-id="63390-108">SET option requirements</span></span>  
  
 <span data-ttu-id="63390-109">**Ownership Requirements**</span><span class="sxs-lookup"><span data-stu-id="63390-109">**Ownership Requirements**</span></span>  
  
 <span data-ttu-id="63390-110">Todas las referencias a funciones de la columna calculada deben tener el mismo propietario que la tabla.</span><span class="sxs-lookup"><span data-stu-id="63390-110">All function references in the computed column must have the same owner as the table.</span></span>  
  
 <span data-ttu-id="63390-111">**Determinism Requirements**</span><span class="sxs-lookup"><span data-stu-id="63390-111">**Determinism Requirements**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="63390-112">Las expresiones son deterministas si siempre devuelven el mismo resultado para un conjunto de entradas específico.</span><span class="sxs-lookup"><span data-stu-id="63390-112">Expressions are deterministic if they always return the same result for a specified set of inputs.</span></span> <span data-ttu-id="63390-113">La propiedad **IsDeterministic** de la función [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) informa de si una expresión *computed_column_expression* es determinista.</span><span class="sxs-lookup"><span data-stu-id="63390-113">The **IsDeterministic** property of the [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) function reports whether a *computed_column_expression* is deterministic.</span></span>  
  
 <span data-ttu-id="63390-114">La expresión *computed_column_expression* debe ser determinista.</span><span class="sxs-lookup"><span data-stu-id="63390-114">The *computed_column_expression* must be deterministic.</span></span> <span data-ttu-id="63390-115">Una expresión *computed_column_expression* es determinista si se cumplen una o varias de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="63390-115">A *computed_column_expression* is deterministic when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="63390-116">Todas las funciones a las que hace referencia la expresión son deterministas y precisas.</span><span class="sxs-lookup"><span data-stu-id="63390-116">All functions that are referenced by the expression are deterministic and precise.</span></span> <span data-ttu-id="63390-117">Esto incluye las funciones definidas por el usuario y las funciones integradas.</span><span class="sxs-lookup"><span data-stu-id="63390-117">These functions include both user-defined and built-in functions.</span></span> <span data-ttu-id="63390-118">Para obtener más información, consulte [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span><span class="sxs-lookup"><span data-stu-id="63390-118">For more information, see [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span></span> <span data-ttu-id="63390-119">Puede que las funciones sean imprecisas si el valor de la columna calculada es PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="63390-119">Functions might be imprecise if the computed column is PERSISTED.</span></span> <span data-ttu-id="63390-120">Para obtener más información, vea [Crear índices en columnas calculadas persistentes](#BKMK_persisted) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="63390-120">For more information, see [Creating Indexes on Persisted Computed Columns](#BKMK_persisted) later in this topic.</span></span>  
  
-   <span data-ttu-id="63390-121">Todas las columnas a las que hace referencia la expresión pertenecen a la tabla que contiene la columna calculada.</span><span class="sxs-lookup"><span data-stu-id="63390-121">All columns that are referenced in the expression come from the table that contains the computed column.</span></span>  
  
-   <span data-ttu-id="63390-122">Ninguna referencia a las columnas extrae datos de varias filas.</span><span class="sxs-lookup"><span data-stu-id="63390-122">No column reference pulls data from multiple rows.</span></span> <span data-ttu-id="63390-123">Por ejemplo, las funciones de agregado como SUM o AVG dependen de datos de varias filas y convertirán a *computed_column_expression* en una expresión no determinista.</span><span class="sxs-lookup"><span data-stu-id="63390-123">For example, aggregate functions such as SUM or AVG depend on data from multiple rows and would make a *computed_column_expression* nondeterministic.</span></span>  
  
-   <span data-ttu-id="63390-124">La expresión *computed_column_expression* no tiene acceso a los datos del sistema o de usuario.</span><span class="sxs-lookup"><span data-stu-id="63390-124">The *computed_column_expression* has no system data access or user data access.</span></span>  
  
 <span data-ttu-id="63390-125">Cualquier columna calculada que contenga una expresión CLR (Common Language Runtime) debe ser determinista y se debe marcar como PERSISTED para poder indizarla.</span><span class="sxs-lookup"><span data-stu-id="63390-125">Any computed column that contains a common language runtime (CLR) expression must be deterministic and marked PERSISTED before the column can be indexed.</span></span> <span data-ttu-id="63390-126">Las expresiones con el tipo definido por el usuario CLR se pueden utilizar en las definiciones de columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="63390-126">CLR user-defined type expressions are allowed in computed column definitions.</span></span> <span data-ttu-id="63390-127">Las columnas calculadas con el tipo definido por el usuario CLR se podrán indizar siempre que el tipo sea comparable.</span><span class="sxs-lookup"><span data-stu-id="63390-127">Computed columns whose type is a CLR user-defined type can be indexed as long as the type is comparable.</span></span> <span data-ttu-id="63390-128">Para obtener más información, vea [Tipos definidos por el usuario de CLR](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="63390-128">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63390-129">Cuando haga referencia a los literales de cadena del tipo de datos de fecha en las columnas calculadas indizadas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se recomienda convertir explícitamente el literal al tipo de datos deseado mediante un estilo de formato de fecha determinista.</span><span class="sxs-lookup"><span data-stu-id="63390-129">When you refer to string literals of the date data type in indexed computed columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], we recommend that you explicitly convert the literal to the date type that you want by using a deterministic date format style.</span></span> <span data-ttu-id="63390-130">Para obtener una lista de los estilos de formato de fecha deterministas, vea [CAST y CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="63390-130">For a list of the date format styles that are deterministic, see [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span> <span data-ttu-id="63390-131">Las expresiones que impliquen la conversión implícita de cadenas de caracteres en tipos de datos de fecha se consideran no deterministas, a menos que el nivel de compatibilidad de la base de datos se establezca en 80 o menos.</span><span class="sxs-lookup"><span data-stu-id="63390-131">Expressions that involve implicit conversion of character strings to date data types are considered nondeterministic, unless the database compatibility level is set to 80 or earlier.</span></span> <span data-ttu-id="63390-132">Esto es así porque los resultados dependen de la configuración de [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) y [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) de la sesión del servidor.</span><span class="sxs-lookup"><span data-stu-id="63390-132">This is because the results depend on the [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) and [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) settings of the server session.</span></span> <span data-ttu-id="63390-133">Por ejemplo, los resultados de la expresión `CONVERT (datetime, '30 listopad 1996', 113)` dependen del valor de LANGUAGE porque la cadena '`30 listopad 1996`' significa distintos meses en distintos idiomas.</span><span class="sxs-lookup"><span data-stu-id="63390-133">For example, the results of the expression `CONVERT (datetime, '30 listopad 1996', 113)` depend on the LANGUAGE setting because the string '`30 listopad 1996`' means different months in different languages.</span></span> <span data-ttu-id="63390-134">De forma similar, en la expresión `DATEADD(mm,3,'2000-12-01')`, el [!INCLUDE[ssDE](../../../includes/ssde-md.md)] interpretará la cadena `'2000-12-01'` en función del valor de DATEFORMAT.</span><span class="sxs-lookup"><span data-stu-id="63390-134">Similarly, in the expression `DATEADD(mm,3,'2000-12-01')`, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] interprets the string `'2000-12-01'` based on the DATEFORMAT setting.</span></span>  
>   
>  <span data-ttu-id="63390-135">La conversión implícita de datos de caracteres no Unicode entre intercalaciones también se considera no determinista, a menos que el nivel de compatibilidad se establezca en 80 o menos.</span><span class="sxs-lookup"><span data-stu-id="63390-135">Implicit conversion of non-Unicode character data between collations is also considered nondeterministic, unless the compatibility level is set to 80 or earlier.</span></span>  
>   
>  <span data-ttu-id="63390-136">Cuando el valor del nivel de compatibilidad de la base de datos es 90, no se pueden crear índices en columnas calculadas que incluyan estas expresiones.</span><span class="sxs-lookup"><span data-stu-id="63390-136">When the database compatibility level setting is 90, you cannot create indexes on computed columns that contain these expressions.</span></span> <span data-ttu-id="63390-137">Sin embargo, se pueden mantener las columnas calculadas existentes que contengan estas expresiones procedentes de una base de datos actualizada.</span><span class="sxs-lookup"><span data-stu-id="63390-137">However, existing computed columns that contain these expressions from an upgraded database are maintainable.</span></span> <span data-ttu-id="63390-138">Si utiliza columnas calculadas indizadas que contienen conversiones implícitas de cadena a fecha, para evitar posibles daños en las vistas indizadas, asegúrese de que las opciones LANGUAGE y DATEFORMAT son coherentes en las bases de datos y las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="63390-138">If you use indexed computed columns that contain implicit string to date conversions, to avoid possible index corruption, make sure that the LANGUAGE and DATEFORMAT settings are consistent in your databases and applications.</span></span>  
  
 <span data-ttu-id="63390-139">**Precision Requirements**</span><span class="sxs-lookup"><span data-stu-id="63390-139">**Precision Requirements**</span></span>  
  
 <span data-ttu-id="63390-140">La expresión *computed_column_expression* debe ser precisa.</span><span class="sxs-lookup"><span data-stu-id="63390-140">The *computed_column_expression* must be precise.</span></span> <span data-ttu-id="63390-141">Una expresión *computed_column_expression* es precisa si se cumplen una o varias de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="63390-141">A *computed_column_expression* is precise when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="63390-142">No es una expresión del tipo de datos `float` o `real`.</span><span class="sxs-lookup"><span data-stu-id="63390-142">It is not an expression of the `float` or `real` data types.</span></span>  
  
-   <span data-ttu-id="63390-143">No utiliza en su definición un tipo de datos `float` o `real`.</span><span class="sxs-lookup"><span data-stu-id="63390-143">It does not use a `float` or `real` data type in its definition.</span></span> <span data-ttu-id="63390-144">Por ejemplo, en la instrucción siguiente, la columna `y` es `int` y determinista, pero no precisa.</span><span class="sxs-lookup"><span data-stu-id="63390-144">For example, in the following statement, column `y` is `int` and deterministic but not precise.</span></span>  
  
    ```  
    CREATE TABLE t2 (a int, b int, c int, x float,   
       y AS CASE x   
             WHEN 0 THEN a   
             WHEN 1 THEN b   
             ELSE c   
          END);  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="63390-145">Las expresiones `float` o `real` se consideran imprecisas y no pueden ser la clave de un índice; una expresión `float` o `real` puede utilizarse en una vista indizada, pero no como clave.</span><span class="sxs-lookup"><span data-stu-id="63390-145">Any `float` or `real` expression is considered imprecise and cannot be a key of an index; a `float` or `real` expression can be used in an indexed view but not as a key.</span></span> <span data-ttu-id="63390-146">Esto también se aplica a las columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="63390-146">This is true also for computed columns.</span></span> <span data-ttu-id="63390-147">Las funciones, expresiones o funciones definidas por el usuario se considerarán imprecisas si incluyen expresiones `float` o `real`.</span><span class="sxs-lookup"><span data-stu-id="63390-147">Any function, expression, or user-defined function is considered imprecise if it contains any `float` or `real` expressions.</span></span> <span data-ttu-id="63390-148">Esto incluye a las lógicas (comparaciones).</span><span class="sxs-lookup"><span data-stu-id="63390-148">This includes logical ones (comparisons).</span></span>  
  
 <span data-ttu-id="63390-149">La propiedad **IsPrecise** de la función COLUMNPROPERTY informa de si una expresión *computed_column_expression* es precisa.</span><span class="sxs-lookup"><span data-stu-id="63390-149">The **IsPrecise** property of the COLUMNPROPERTY function reports whether a *computed_column_expression* is precise.</span></span>  
  
 <span data-ttu-id="63390-150">**Data Type Requirements**</span><span class="sxs-lookup"><span data-stu-id="63390-150">**Data Type Requirements**</span></span>  
  
-   <span data-ttu-id="63390-151">Los *computed_column_expression* definidos para la columna calculada no se pueden evaluar `text` como `ntext` tipos de `image` datos, o.</span><span class="sxs-lookup"><span data-stu-id="63390-151">The *computed_column_expression* defined for the computed column cannot evaluate to the `text`, `ntext`, or `image` data types.</span></span>  
  
-   <span data-ttu-id="63390-152">Las columnas calculadas derivadas de los tipos de datos `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)` y `xml` se pueden indizar, siempre que el tipo de datos esté disponible como una columna de clave de índice.</span><span class="sxs-lookup"><span data-stu-id="63390-152">Computed columns derived from `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, and `xml` data types can be indexed as long as the computed column data type is allowable as an index key column.</span></span>  
  
-   <span data-ttu-id="63390-153">Las columnas calculadas derivadas de los tipos de datos `image`, `ntext` y `text` pueden ser columnas sin clave (incluidas) en un índice no clúster, siempre que el tipo de datos esté disponible como una columna de índice sin clave.</span><span class="sxs-lookup"><span data-stu-id="63390-153">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey (included) columns in a nonclustered index as long as the computed column data type is allowable as a nonkey index column.</span></span>  
  
 <span data-ttu-id="63390-154">**Requisitos de la opción SET**</span><span class="sxs-lookup"><span data-stu-id="63390-154">**SET Option Requirements**</span></span>  
  
-   <span data-ttu-id="63390-155">La opción de nivel de conexión ANSI_NULLS debe estar establecida en ON si se ejecuta la instrucción CREATE TABLE o ALTER TABLE que define la columna calculada.</span><span class="sxs-lookup"><span data-stu-id="63390-155">The ANSI_NULLS connection-level option must be set to ON when the CREATE TABLE or ALTER TABLE statement that defines the computed column is executed.</span></span> <span data-ttu-id="63390-156">La función [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) informa de si la opción está activada a través de la propiedad **IsAnsiNullsOn** .</span><span class="sxs-lookup"><span data-stu-id="63390-156">The [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) function reports whether the option is on through the **IsAnsiNullsOn** property.</span></span>  
  
-   <span data-ttu-id="63390-157">La conexión en la que se crea el índice y todos los intentos de conexión de las instrucciones INSERT, UPDATE o DELETE que cambiarán los valores del índice deben tener seis opciones SET con el valor ON y una con el valor OFF.</span><span class="sxs-lookup"><span data-stu-id="63390-157">The connection on which the index is created, and all connections trying INSERT, UPDATE, or DELETE statements that will change values in the index, must have six SET options set to ON and one option set to OFF.</span></span> <span data-ttu-id="63390-158">El optimizador omitirá un índice de una columna calculada para cualquier instrucción SELECT que se ejecute mediante una conexión que no tenga la misma configuración de las opciones.</span><span class="sxs-lookup"><span data-stu-id="63390-158">The optimizer ignores an index on a computed column for any SELECT statement executed by a connection that does not have these same option settings.</span></span>  
  
    -   <span data-ttu-id="63390-159">El valor de la opción NUMERIC_ROUNDABORT debe ser OFF y el de las opciones siguientes debe ser ON:</span><span class="sxs-lookup"><span data-stu-id="63390-159">The NUMERIC_ROUNDABORT option must be set to OFF, and the following options must be set to ON:</span></span>  
  
    -   <span data-ttu-id="63390-160">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="63390-160">ANSI_NULLS</span></span>  
  
    -   <span data-ttu-id="63390-161">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="63390-161">ANSI_PADDING</span></span>  
  
    -   <span data-ttu-id="63390-162">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="63390-162">ANSI_WARNINGS</span></span>  
  
    -   <span data-ttu-id="63390-163">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="63390-163">ARITHABORT</span></span>  
  
    -   <span data-ttu-id="63390-164">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="63390-164">CONCAT_NULL_YIELDS_NULL</span></span>  
  
    -   <span data-ttu-id="63390-165">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="63390-165">QUOTED_IDENTIFIER</span></span>  
  
     <span data-ttu-id="63390-166">Al establecer ANSI_WARNINGS en ON, ARITHABORT se establece de forma implícita en ON cuando el nivel de compatibilidad de base de datos está establecido en 90 o un valor superior.</span><span class="sxs-lookup"><span data-stu-id="63390-166">Setting ANSI_WARNINGS to ON implicitly sets ARITHABORT to ON when the database compatibility level is set to 90 or higher.</span></span>  
  
##  <a name="creating-indexes-on-persisted-computed-columns"></a><a name="BKMK_persisted"></a> <span data-ttu-id="63390-167">Crear índices en columnas calculadas persistentes</span><span class="sxs-lookup"><span data-stu-id="63390-167">Creating Indexes on Persisted Computed Columns</span></span>  
 <span data-ttu-id="63390-168">Puede crear un índice en una columna calculada definida con una expresión determinista pero imprecisa si se marca la columna como PERSISTED en la instrucción CREATE TABLE o ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="63390-168">You can create an index on a computed column that is defined with a deterministic, but imprecise, expression if the column is marked PERSISTED in the CREATE TABLE or ALTER TABLE statement.</span></span> <span data-ttu-id="63390-169">Esto significa que [!INCLUDE[ssDE](../../../includes/ssde-md.md)] utiliza estos valores persistentes cuando crea un índice en la columna y cuando se hace referencia al índice en una consulta.</span><span class="sxs-lookup"><span data-stu-id="63390-169">This means that the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] uses these persisted values when it creates an index on the column, and when the index is referenced in a query.</span></span> <span data-ttu-id="63390-170">Esta opción permite crear un índice en una columna calculada cuando [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)] es determinista y precisa.</span><span class="sxs-lookup"><span data-stu-id="63390-170">This option enables you to create an index on a computed column when [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)], is both deterministic and precise.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="63390-171">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="63390-171">Related Content</span></span>  
 [<span data-ttu-id="63390-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="63390-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/columnproperty-transact-sql)  
  
  
