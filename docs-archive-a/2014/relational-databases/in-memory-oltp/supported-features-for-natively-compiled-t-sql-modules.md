---
title: Construcciones admitidas en procedimientos almacenados compilados de forma nativa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 05515013-28b5-4ccf-9a54-ae861448945b
author: rothja
ms.author: jroth
ms.openlocfilehash: 65e6e794c5858a68c4b2a9b298513911b487cf52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677103"
---
# <a name="supported-constructs-in-natively-compiled-stored-procedures"></a><span data-ttu-id="85b90-102">Construcciones admitidas en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="85b90-102">Supported Constructs in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="85b90-103">Este tema contiene una lista de características admitidas para los procedimientos almacenados compilados de forma nativa ([CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)):</span><span class="sxs-lookup"><span data-stu-id="85b90-103">This topic contains a list of supported features for natively compiled stored procedures ([CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)):</span></span>  
  
-   [<span data-ttu-id="85b90-104">Programación en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="85b90-104">Programmability in Natively Compiled Stored Procedures</span></span>](#pncsp)  
  
-   [<span data-ttu-id="85b90-105">Operadores admitidos</span><span class="sxs-lookup"><span data-stu-id="85b90-105">Supported Operators</span></span>](#so)  
  
-   [<span data-ttu-id="85b90-106">Funciones integradas en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="85b90-106">Built-in Functions in Natively Compiled Stored Procedures</span></span>](#bfncsp)  
  
-   [<span data-ttu-id="85b90-107">Área expuesta de consulta en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="85b90-107">Query Surface Area in Natively Compiled Stored Procedures</span></span>](#qsancsp)  
  
-   [<span data-ttu-id="85b90-108">Auditoría</span><span class="sxs-lookup"><span data-stu-id="85b90-108">Auditing</span></span>](#auditing)  
  
-   [<span data-ttu-id="85b90-109">Sugerencias de tablas, consultas y combinaciones</span><span class="sxs-lookup"><span data-stu-id="85b90-109">Table, Query, and Join Hints</span></span>](#tqh)  
  
-   [<span data-ttu-id="85b90-110">Limitaciones de la ordenación</span><span class="sxs-lookup"><span data-stu-id="85b90-110">Limitations on Sorting</span></span>](#los)  
  
 <span data-ttu-id="85b90-111">Para obtener información sobre los tipos de datos que se admiten en los procedimientos almacenados compilados de forma nativa, consulte [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="85b90-111">For information on data types supported in natively compiled stored procedures, see [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="85b90-112">Para obtener información completa sobre las construcciones no admitidas y sobre cómo evitar algunas de las características no admitidas en los procedimientos almacenados compilados de forma nativa, vea [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="85b90-112">For complete information about unsupported constructs, and for information about how to work around some of the unsupported features in natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span> <span data-ttu-id="85b90-113">Para obtener más información sobre las características no compatibles, vea [Construcciones Transact-SQL no admitidas por OLTP en memoria](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="85b90-113">For more information about unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
##  <a name="programmability-in-natively-compiled-stored-procedures"></a><a name="pncsp"></a><span data-ttu-id="85b90-114">Programación en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="85b90-114">Programmability in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="85b90-115">Se admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85b90-115">The following are supported:</span></span>  
  
-   <span data-ttu-id="85b90-116">BEGIN ATOMIC (en el nivel externo del procedimiento almacenado), LANGUAGE, ISOLATION LEVEL, DATEFORMAT y DATEFIRST.</span><span class="sxs-lookup"><span data-stu-id="85b90-116">BEGIN ATOMIC (at the outer level of the stored procedure), LANGUAGE, ISOLATION LEVEL, DATEFORMAT, and DATEFIRST.</span></span>  
  
-   <span data-ttu-id="85b90-117">Declaración de variables como NULL o NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="85b90-117">Declaring variables as NULL or NOT NULL.</span></span> <span data-ttu-id="85b90-118">Si una variable se declara como NOT NULL, la declaración debe tener un inicializador.</span><span class="sxs-lookup"><span data-stu-id="85b90-118">If a variable is declared as NOT NULL, the declaration must have an initializer.</span></span> <span data-ttu-id="85b90-119">Si una variable se declara como NOT NULL, el inicializador es opcional.</span><span class="sxs-lookup"><span data-stu-id="85b90-119">If a variable is not declared as NOT NULL, an initializer is optional.</span></span>  
  
-   <span data-ttu-id="85b90-120">IF y WHILE</span><span class="sxs-lookup"><span data-stu-id="85b90-120">IF and WHILE</span></span>  
  
-   <span data-ttu-id="85b90-121">INSERT/UPDATE/DELETE</span><span class="sxs-lookup"><span data-stu-id="85b90-121">INSERT/UPDATE/DELETE</span></span>  
  
     <span data-ttu-id="85b90-122">No se admiten las subconsultas.</span><span class="sxs-lookup"><span data-stu-id="85b90-122">Subqueries are not supported.</span></span> <span data-ttu-id="85b90-123">En las cláusulas WHERE o HAVING, AND y BETWEEN son compatibles; OR, NOT, y IN no se admiten.</span><span class="sxs-lookup"><span data-stu-id="85b90-123">In the WHERE or HAVING clause, AND and BETWEEN are supported; OR, NOT, and IN are not supported.</span></span>  
  
-   <span data-ttu-id="85b90-124">Variables de tabla y tipos de tabla con optimización para memoria.</span><span class="sxs-lookup"><span data-stu-id="85b90-124">Memory-optimized table types and table variables.</span></span>  
  
-   <span data-ttu-id="85b90-125">RETURN</span><span class="sxs-lookup"><span data-stu-id="85b90-125">RETURN</span></span>  
  
-   <span data-ttu-id="85b90-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="85b90-126">SELECT</span></span>  
  
-   <span data-ttu-id="85b90-127">SET</span><span class="sxs-lookup"><span data-stu-id="85b90-127">SET</span></span>  
  
-   <span data-ttu-id="85b90-128">TRY/CATCH/THROW</span><span class="sxs-lookup"><span data-stu-id="85b90-128">TRY/CATCH/THROW</span></span>  
  
     <span data-ttu-id="85b90-129">Para optimizar el rendimiento, use un solo bloque TRY/CATCH para un procedimiento almacenado compilado de forma nativa completo.</span><span class="sxs-lookup"><span data-stu-id="85b90-129">To optimize performance, use a single TRY/CATCH block for an entire natively compiled stored procedure.</span></span>  
  
##  <a name="supported-operators"></a><a name="so"></a> <span data-ttu-id="85b90-130">Operadores admitidos</span><span class="sxs-lookup"><span data-stu-id="85b90-130">Supported Operators</span></span>  
 <span data-ttu-id="85b90-131">Se admiten los siguientes operadores.</span><span class="sxs-lookup"><span data-stu-id="85b90-131">The following operators are supported.</span></span>  
  
-   <span data-ttu-id="85b90-132">Los [operadores de comparación &#40;&#41;de Transact-SQL](/sql/t-sql/language-elements/comparison-operators-transact-sql) (por ejemplo, >, \<, > = y <=) se admiten en los condicionales (si, while).</span><span class="sxs-lookup"><span data-stu-id="85b90-132">[Comparison Operators &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/comparison-operators-transact-sql) (for example, >, \<, >=, and <=) are supported in conditionals (IF, WHILE).</span></span>  
  
-   <span data-ttu-id="85b90-133">Operadores unarios (+, -).</span><span class="sxs-lookup"><span data-stu-id="85b90-133">Unary operators (+, -).</span></span>  
  
-   <span data-ttu-id="85b90-134">Operadores binarios ((\*, /, +, -, % (módulo)).</span><span class="sxs-lookup"><span data-stu-id="85b90-134">Binary operators (\*, /, +, -, % (modulo)).</span></span>  
  
     <span data-ttu-id="85b90-135">Se admite el operador más (+) en ambos números y cadenas.</span><span class="sxs-lookup"><span data-stu-id="85b90-135">The plus operator (+) is supported on both numbers and strings.</span></span>  
  
-   <span data-ttu-id="85b90-136">Operadores lógicos (AND, OR, NOT).</span><span class="sxs-lookup"><span data-stu-id="85b90-136">Logical operators (AND, OR, NOT).</span></span> <span data-ttu-id="85b90-137">OR y NOT se admiten en las instrucciones IF y WHILE pero no en las cláusulas WHERE o HAVING.</span><span class="sxs-lookup"><span data-stu-id="85b90-137">OR and NOT are supported in IF and WHILE statements but not in WHERE or HAVING clauses.</span></span>  
  
-   <span data-ttu-id="85b90-138">Operadores ~, &, | y ^ bit a bit</span><span class="sxs-lookup"><span data-stu-id="85b90-138">Bitwise operators ~, &, |, and ^</span></span>  
  
##  <a name="built-in-functions-in-natively-compiled-stored-procedures"></a><a name="bfncsp"></a><span data-ttu-id="85b90-139">Funciones integradas en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="85b90-139">Built-in Functions in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="85b90-140">Se admiten las funciones siguientes en restricciones DEFAULT de tablas optimizadas para memoria y procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="85b90-140">The following functions are supported in default constraints on memory-optimized tables and in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="85b90-141">Funciones matemáticas: ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANES, RAND, SIN, SQRT, SQUARE y TAN</span><span class="sxs-lookup"><span data-stu-id="85b90-141">Math Functions: ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANS, RAND, SIN, SQRT, SQUARE, and TAN</span></span>  
  
-   <span data-ttu-id="85b90-142">Funciones de fecha: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME y YEAR.</span><span class="sxs-lookup"><span data-stu-id="85b90-142">Date Functions: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME, and YEAR.</span></span>  
  
-   <span data-ttu-id="85b90-143">Funciones de cadena: LEN, LTRIM, RTRIM y SUBSTRING</span><span class="sxs-lookup"><span data-stu-id="85b90-143">String Functions: LEN, LTRIM, RTRIM, and SUBSTRING</span></span>  
  
-   <span data-ttu-id="85b90-144">Función de identidad: SCOPE_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="85b90-144">Identity Function: SCOPE_IDENTITY</span></span>  
  
-   <span data-ttu-id="85b90-145">Funciones NULL: ISNULL</span><span class="sxs-lookup"><span data-stu-id="85b90-145">NULL functions: ISNULL</span></span>  
  
-   <span data-ttu-id="85b90-146">Funciones uniqueidentifier: NEWID y NEWSEQUENTIALID</span><span class="sxs-lookup"><span data-stu-id="85b90-146">Uniqueidentifier functions: NEWID and NEWSEQUENTIALID</span></span>  
  
-   <span data-ttu-id="85b90-147">Funciones de error: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY y ERROR_STATE</span><span class="sxs-lookup"><span data-stu-id="85b90-147">Error Functions: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY, and ERROR_STATE</span></span>  
  
-   <span data-ttu-id="85b90-148">Conversiones: CAST y CONVERT.</span><span class="sxs-lookup"><span data-stu-id="85b90-148">Conversions: CAST and CONVERT.</span></span> <span data-ttu-id="85b90-149">No se admiten las conversiones entre cadenas de caracteres Unicode y no Unicode (n(var)char y (var)char).</span><span class="sxs-lookup"><span data-stu-id="85b90-149">Conversions between Unicode and non-Unicode character strings (n(var)char and (var)char) are not supported.</span></span>  
  
-   <span data-ttu-id="85b90-150">Funciones del sistema: @@rowcount.</span><span class="sxs-lookup"><span data-stu-id="85b90-150">System Functions: @@rowcount.</span></span> <span data-ttu-id="85b90-151">Las instrucciones de los procedimientos almacenados compilados de forma nativa actualizan @@rowcount y puede usar @@rowcount en un procedimiento almacenado compilado de forma nativa para determinar el número de filas afectadas por la última instrucción ejecutada dentro de ese procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="85b90-151">Statements inside natively compiled stored procedures update @@rowcount and you can use @@rowcount in a natively compiled stored procedure to determine the number of rows affected by the last statement executed within that natively compiled stored procedure.</span></span> <span data-ttu-id="85b90-152">Pero @@rowcount se restablece en 0 al principio y al final de la ejecución de un procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="85b90-152">However, @@rowcount is reset to 0 at the start and at the end of the execution of a natively compiled stored procedure.</span></span>  
  
##  <a name="query-surface-area-in-natively-compiled-stored-procedures"></a><a name="qsancsp"></a><span data-ttu-id="85b90-153">Área expuesta de consulta en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="85b90-153">Query Surface Area in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="85b90-154">Se admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85b90-154">The following are supported:</span></span>  
  
-   <span data-ttu-id="85b90-155">BETWEEN</span><span class="sxs-lookup"><span data-stu-id="85b90-155">BETWEEN</span></span>  
  
-   <span data-ttu-id="85b90-156">Alias de nombre de columna (con sintaxis AS o =).</span><span class="sxs-lookup"><span data-stu-id="85b90-156">Column name aliases (using either AS or = syntax).</span></span>  
  
-   <span data-ttu-id="85b90-157">CROSS JOIN y INNER JOIN, solo se admiten con consultas SELECT.</span><span class="sxs-lookup"><span data-stu-id="85b90-157">CROSS JOIN and INNER JOIN, supported only with SELECT queries.</span></span>  
  
-   <span data-ttu-id="85b90-158">Las expresiones se admiten en la lista de selección y [donde &#40;cláusula de Transact-SQL&#41;](/sql/t-sql/queries/where-transact-sql) si usan un operador admitido.</span><span class="sxs-lookup"><span data-stu-id="85b90-158">Expressions are supported in SELECT list and [WHERE &#40;Transact-SQL&#41;](/sql/t-sql/queries/where-transact-sql) clause if they use a supported operator.</span></span> <span data-ttu-id="85b90-159">Consulte [Operadores admitidos](#so) para ver la lista de los operadores que se admiten actualmente.</span><span class="sxs-lookup"><span data-stu-id="85b90-159">See [Supported Operators](#so) for the list of currently-supported operators.</span></span>  
  
-   <span data-ttu-id="85b90-160">Predicado de filtro IS [NOT] NULL</span><span class="sxs-lookup"><span data-stu-id="85b90-160">Filter predicate IS [NOT] NULL</span></span>  
  
-   <span data-ttu-id="85b90-161">FROM \<memory optimized table></span><span class="sxs-lookup"><span data-stu-id="85b90-161">FROM \<memory optimized table></span></span>  
  
-   <span data-ttu-id="85b90-162">Se admite [GROUP BY &#40;&#41;de Transact-SQL](/sql/t-sql/queries/select-group-by-transact-sql) , junto con las funciones de agregado AVG, COUNT, COUNT_BIG, min, Max y sum.</span><span class="sxs-lookup"><span data-stu-id="85b90-162">[GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) is supported, along with the aggregate functions AVG, COUNT, COUNT_BIG, MIN, MAX, and SUM.</span></span> <span data-ttu-id="85b90-163">MIN o MAX no se admiten para los tipos nvarchar, char, varchar, varchar, varbinary y binary.</span><span class="sxs-lookup"><span data-stu-id="85b90-163">MIN and MAX are not supported for types nvarchar, char, varchar, varchar, varbinary, and binary.</span></span> <span data-ttu-id="85b90-164">La [cláusula order by &#40;Transact-sql&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) es compatible con [Group by &#40;transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) si una expresión de la lista order by aparece literalmente en la lista Group by.</span><span class="sxs-lookup"><span data-stu-id="85b90-164">[ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) is supported with [GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) if an expression in the ORDER BY list appears verbatim in the GROUP BY list.</span></span> <span data-ttu-id="85b90-165">Por ejemplo, se admite GROUP BY a + b ORDER BY a + b pero no GROUP BY a, b ORDER BY a + b.</span><span class="sxs-lookup"><span data-stu-id="85b90-165">For example, GROUP BY a + b ORDER BY a + b is supported, but GROUP BY a, b ORDER BY a + b is not.</span></span>  
  
-   <span data-ttu-id="85b90-166">HAVING, sujeto a las mismas limitaciones de expresión que la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="85b90-166">HAVING, subject to the same expression limitations as the WHERE clause.</span></span>  
  
-   <span data-ttu-id="85b90-167">INSERT VALUES (una fila por instrucción) e INSERT SELECT</span><span class="sxs-lookup"><span data-stu-id="85b90-167">INSERT VALUES (one row per statement) and INSERT SELECT</span></span>  
  
-   <span data-ttu-id="85b90-168">ORDENAR por <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="85b90-168">ORDER BY <sup>1</sup></span></span>  
  
-   <span data-ttu-id="85b90-169">Predicados que no hacen referencia a una columna.</span><span class="sxs-lookup"><span data-stu-id="85b90-169">Predicates not referencing a column.</span></span>  
  
-   <span data-ttu-id="85b90-170">SELECT, UPDATE y DELETE</span><span class="sxs-lookup"><span data-stu-id="85b90-170">SELECT, UPDATE, and DELETE</span></span>  
  
-   <span data-ttu-id="85b90-171">TOP <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="85b90-171">TOP <sup>1</sup></span></span>  
  
-   <span data-ttu-id="85b90-172">Asignación de variable de la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="85b90-172">Variable assignment in the SELECT list.</span></span>  
  
-   <span data-ttu-id="85b90-173">DÓNDE... ETC</span><span class="sxs-lookup"><span data-stu-id="85b90-173">WHERE ... AND</span></span>  
  
 <span data-ttu-id="85b90-174"><sup>1</sup> order by y Top se admiten en procedimientos almacenados compilados de forma nativa, con algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="85b90-174"><sup>1</sup> ORDER BY and TOP are supported in natively compiled stored procedures, with some restrictions:</span></span>  
  
-   <span data-ttu-id="85b90-175">No hay compatibilidad con `DISTINCT` en la cláusula `SELECT` ni `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="85b90-175">There is no support for `DISTINCT` in the `SELECT` or `ORDER BY` clause.</span></span>  
  
-   <span data-ttu-id="85b90-176">No hay compatibilidad con `WITH TIES` ni `PERCENT` en la cláusula `TOP`.</span><span class="sxs-lookup"><span data-stu-id="85b90-176">There is no support for `WITH TIES` or `PERCENT` in the `TOP` clause.</span></span>  
  
-   <span data-ttu-id="85b90-177">`TOP` combinada con `ORDER BY` no admite más de 8.192 elementos cuando se utiliza una constante en la cláusula `TOP`.</span><span class="sxs-lookup"><span data-stu-id="85b90-177">`TOP` combined with `ORDER BY` does not support more than 8,192 when using a constant in the `TOP` clause.</span></span> <span data-ttu-id="85b90-178">Este límite puede reducirse en caso de que la consulta contenga combinaciones o funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="85b90-178">This limit may be lowered in case the query contains joins or aggregate functions.</span></span> <span data-ttu-id="85b90-179">(Por ejemplo, con una combinación (dos tablas), el límite es de 4.096 filas.</span><span class="sxs-lookup"><span data-stu-id="85b90-179">(For example, with one join (two tables), the limit is 4,096 rows.</span></span> <span data-ttu-id="85b90-180">Con dos combinaciones (tres tablas), el límite es de 2.730 filas).</span><span class="sxs-lookup"><span data-stu-id="85b90-180">With two joins (three tables), the limit is 2,730 rows.)</span></span>  
  
     <span data-ttu-id="85b90-181">Puede obtener más de 8.192 resultados si almacena el número de filas en una variable:</span><span class="sxs-lookup"><span data-stu-id="85b90-181">You can obtain results greater than 8,192 by storing the number of rows in a variable:</span></span>  
  
    ```sql  
    DECLARE @v INT = 9000  
    SELECT TOP (@v) ... FROM ... ORDER BY ...  
    ```  
  
 <span data-ttu-id="85b90-182">Sin embargo, una constante en la cláusula `TOP` produce un rendimiento mejor en comparación con el uso de una variable.</span><span class="sxs-lookup"><span data-stu-id="85b90-182">However, a constant in the `TOP` clause results in better performance compared to using a variable.</span></span>  
  
 <span data-ttu-id="85b90-183">Estas restricciones no se aplican al acceso mediante [!INCLUDE[tsql](../../includes/tsql-md.md)] interpretado a las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="85b90-183">These restrictions do not apply to interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] access on memory-optimized tables.</span></span>  
  
##  <a name="auditing"></a><a name="auditing"></a> <span data-ttu-id="85b90-184">Auditoría</span><span class="sxs-lookup"><span data-stu-id="85b90-184">Auditing</span></span>  
 <span data-ttu-id="85b90-185">Se admite la auditoría a nivel de procedimiento en los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="85b90-185">Procedure level auditing is supported in natively compiled stored procedures.</span></span> <span data-ttu-id="85b90-186">La auditoría de nivel de instrucción no se admite.</span><span class="sxs-lookup"><span data-stu-id="85b90-186">Statement level auditing is not supported.</span></span>  
  
 <span data-ttu-id="85b90-187">Para obtener más información sobre la auditoría, vea [Crear una especificación de auditoría de servidor y de auditoría de base de datos](../security/auditing/create-a-server-audit-and-database-audit-specification.md)</span><span class="sxs-lookup"><span data-stu-id="85b90-187">For more information about auditing, see [Create a Server Audit and Database Audit Specification](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span></span>  
  
##  <a name="table-query-and-join-hints"></a><a name="tqh"></a><span data-ttu-id="85b90-188">Sugerencias de tabla, consulta y combinación</span><span class="sxs-lookup"><span data-stu-id="85b90-188">Table, Query, and Join Hints</span></span>  
 <span data-ttu-id="85b90-189">Se admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="85b90-189">The following are supported:</span></span>  
  
-   <span data-ttu-id="85b90-190">Las sugerencias INDEX, FORCESCAN y FORCESEEK, ya sea en la sintaxis de sugerencias de tabla o en la [cláusula OPTION &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) de la consulta.</span><span class="sxs-lookup"><span data-stu-id="85b90-190">INDEX, FORCESCAN, and FORCESEEK hints, either in table hints syntax or in [OPTION Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) of the query.</span></span>  
  
-   <span data-ttu-id="85b90-191">FORCE ORDER</span><span class="sxs-lookup"><span data-stu-id="85b90-191">FORCE ORDER</span></span>  
  
-   <span data-ttu-id="85b90-192">INNER LOOP JOIN</span><span class="sxs-lookup"><span data-stu-id="85b90-192">INNER LOOP JOIN</span></span>  
  
-   <span data-ttu-id="85b90-193">OPTIMIZE FOR</span><span class="sxs-lookup"><span data-stu-id="85b90-193">OPTIMIZE FOR</span></span>  
  
 <span data-ttu-id="85b90-194">Para obtener más información, vea [sugerencias &#40;&#41;de Transact-SQL ](/sql/t-sql/queries/hints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85b90-194">For more information, see [Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql).</span></span>  
  
##  <a name="limitations-on-sorting"></a><a name="los"></a> <span data-ttu-id="85b90-195">Limitaciones de ordenación</span><span class="sxs-lookup"><span data-stu-id="85b90-195">Limitations on Sorting</span></span>  
 <span data-ttu-id="85b90-196">Puede ordenar más de 8000 filas en una consulta que use [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) y una [cláusula ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85b90-196">You can sort greater than 8,000 rows in a query that uses [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span> <span data-ttu-id="85b90-197">Pero sin la [cláusula ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) puede ordenar hasta 8000 filas (si hay combinaciones, menos filas).</span><span class="sxs-lookup"><span data-stu-id="85b90-197">However, without [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) can sort up to 8,000 rows (fewer rows if there are joins).</span></span>  
  
 <span data-ttu-id="85b90-198">Si la consulta usa el operador [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) y una [cláusula ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), puede especificar hasta 8192 filas para el operador TOP.</span><span class="sxs-lookup"><span data-stu-id="85b90-198">If your query uses both the [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) operator and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), you can specify up to 8192 rows for the TOP operator.</span></span> <span data-ttu-id="85b90-199">Si especifica más de 8192 filas, obtiene el mensaje de error: **Mensaje 41398, Nivel 16, Estado 1, Procedimiento *\<procedureName>\* , Línea *\<lineNumber>\* El operador TOP puede devolver un máximo de 8192 filas; el número solicitado es *\<number>* .\*\*</span><span class="sxs-lookup"><span data-stu-id="85b90-199">If you specify more than 8192 rows you get the error message: **Msg 41398, Level 16, State 1, Procedure *\<procedureName>*, Line *\<lineNumber>* The TOP operator can return a maximum of 8192 rows; *\<number>* was requested.**</span></span>  
  
 <span data-ttu-id="85b90-200">Si no tiene una cláusula TOP, puede ordenar cualquier número de filas con ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="85b90-200">If you do not have a TOP clause, you can sort any number of rows with ORDER BY.</span></span>  
  
 <span data-ttu-id="85b90-201">Si no utiliza una cláusula ORDER BY, puede utilizar un valor entero con el operador TOP.</span><span class="sxs-lookup"><span data-stu-id="85b90-201">If you do not use an ORDER BY clause, you can use any integer value with the TOP operator.</span></span>  
  
 <span data-ttu-id="85b90-202">Ejemplo con TOP N = 8192: se compila.</span><span class="sxs-lookup"><span data-stu-id="85b90-202">Example with TOP N = 8192: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8192 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="85b90-203">Ejemplo con TOP N > 8192: no se compila.</span><span class="sxs-lookup"><span data-stu-id="85b90-203">Example with TOP N > 8192: Fails to compile.</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8193 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="85b90-204">La limitación de 8192 filas solo se aplica a `TOP N` donde `N` es una constante, como en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="85b90-204">The 8192 row limitation only applies to `TOP N` where `N` is a constant, as in the preceding examples.</span></span>  <span data-ttu-id="85b90-205">Si necesita un número `N` mayor que 8192 puede asignar el valor a una variable y utilizar esa variable con `TOP`.</span><span class="sxs-lookup"><span data-stu-id="85b90-205">If you need `N` greater than 8192 you can assign the value to a variable and use that variable with `TOP`.</span></span>  
  
 <span data-ttu-id="85b90-206">Ejemplo con una variable: se compila.</span><span class="sxs-lookup"><span data-stu-id="85b90-206">Example using a variable: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    DECLARE @v int = 8193   
    SELECT TOP (@v) ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="85b90-207">**Limitaciones para las filas devueltas:** hay dos casos en los que se puede reducir el número de filas que puede devolver el operador TOP:</span><span class="sxs-lookup"><span data-stu-id="85b90-207">**Limitations on rows returned:** There are two cases where that can potentially reduce the number of rows that can be returned by the TOP operator:</span></span>  
  
-   <span data-ttu-id="85b90-208">Usar JOIN en la consulta.</span><span class="sxs-lookup"><span data-stu-id="85b90-208">Using JOINs in the query.</span></span>  <span data-ttu-id="85b90-209">El efecto de JOIN en la limitación depende del plan de consulta.</span><span class="sxs-lookup"><span data-stu-id="85b90-209">The influence of JOINs on the limitation depends on the query plan.</span></span>  
  
-   <span data-ttu-id="85b90-210">Usar funciones de agregado o referencias a funciones de agregado en la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="85b90-210">Using aggregate functions or references to aggregate functions in the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="85b90-211">La fórmula para calcular un N máximo de peor caso admitido en TOP N es: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span><span class="sxs-lookup"><span data-stu-id="85b90-211">The formula to calculate a worst case maximum supported N in TOP N is: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b90-212">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85b90-212">See Also</span></span>  
 <span data-ttu-id="85b90-213">[Procedimientos almacenados compilados de forma nativa](natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="85b90-213">[Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="85b90-214">Problemas de migración para los procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="85b90-214">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
  
