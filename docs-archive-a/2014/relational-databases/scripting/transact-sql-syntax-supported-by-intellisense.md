---
title: Sintaxis de Transact-SQL compatible con IntelliSense
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL IntelliSense
- IntelliSense [SQL Server], Transact-SQL syntax
ms.assetid: 194e8f4f-fd7e-4f32-a169-f23531128004
author: rothja
ms.author: jroth
ms.openlocfilehash: b3d34fc79dd7817e64b34b61083415477860ce97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746875"
---
# <a name="transact-sql-syntax-supported-by-intellisense"></a><span data-ttu-id="42608-102">Sintaxis de Transact-SQL compatible con IntelliSense</span><span class="sxs-lookup"><span data-stu-id="42608-102">Transact-SQL Syntax Supported by IntelliSense</span></span>
  <span data-ttu-id="42608-103">En este tema se describen las instrucciones y los elementos de sintaxis de [!INCLUDE[tsql](../../includes/tsql-md.md)] que IntelliSense admite en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42608-103">This topic describes the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and syntax elements that are supported by IntelliSense in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="statements-supported-by-intellisense"></a><span data-ttu-id="42608-104">Instrucciones admitidas por IntelliSense</span><span class="sxs-lookup"><span data-stu-id="42608-104">Statements Supported by IntelliSense</span></span>  
 <span data-ttu-id="42608-105">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], IntelliSense solamente admite las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] de uso más frecuente.</span><span class="sxs-lookup"><span data-stu-id="42608-105">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], IntelliSense supports only the most commonly used [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="42608-106">Algunas condiciones generales del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] pueden impedir el funcionamiento de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="42608-106">Some general [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor conditions might prevent IntelliSense from functioning.</span></span> <span data-ttu-id="42608-107">Para obtener más información, vea [Solución de problemas IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="42608-107">For more information, see [Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42608-108">IntelliSense no está disponible para objetos de base de datos cifrados, como funciones definidas por el usuario o procedimientos almacenados cifrados.</span><span class="sxs-lookup"><span data-stu-id="42608-108">IntelliSense is not available for encrypted database objects, such as encrypted stored procedures or user-defined functions.</span></span> <span data-ttu-id="42608-109">La ayuda sobre parámetros y la información rápida no están disponibles para los parámetros de los procedimientos almacenados extendidos y los tipos definidos por el usuario de la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="42608-109">Parameter help and Quick Info are not available for the parameters of extended stored procedures and CLR Integration user-defined types.</span></span>  
  
### <a name="select-statement"></a><span data-ttu-id="42608-110">Instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="42608-110">SELECT Statement</span></span>  
 <span data-ttu-id="42608-111">El Editor de consultas del [!INCLUDE[ssDE](../../includes/ssde-md.md)] proporciona compatibilidad con IntelliSense para los elementos de sintaxis siguientes de la instrucción SELECT:</span><span class="sxs-lookup"><span data-stu-id="42608-111">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor provides IntelliSense support for the following syntax elements in the SELECT statement:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42608-112">SELECT</span><span class="sxs-lookup"><span data-stu-id="42608-112">SELECT</span></span>|<span data-ttu-id="42608-113">WHERE</span><span class="sxs-lookup"><span data-stu-id="42608-113">WHERE</span></span>|  
|<span data-ttu-id="42608-114">FROM</span><span class="sxs-lookup"><span data-stu-id="42608-114">FROM</span></span>|<span data-ttu-id="42608-115">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="42608-115">ORDER BY</span></span>|  
|<span data-ttu-id="42608-116">HAVING</span><span class="sxs-lookup"><span data-stu-id="42608-116">HAVING</span></span>|<span data-ttu-id="42608-117">UNION</span><span class="sxs-lookup"><span data-stu-id="42608-117">UNION</span></span>|  
|<span data-ttu-id="42608-118">FOR</span><span class="sxs-lookup"><span data-stu-id="42608-118">FOR</span></span>|<span data-ttu-id="42608-119">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="42608-119">GROUP BY</span></span>|  
|<span data-ttu-id="42608-120">TOP</span><span class="sxs-lookup"><span data-stu-id="42608-120">TOP</span></span>|<span data-ttu-id="42608-121">OPTION (sugerencia)</span><span class="sxs-lookup"><span data-stu-id="42608-121">OPTION (hint)</span></span>|  
  
### <a name="additional-transact-sql-statements-that-are-supported"></a><span data-ttu-id="42608-122">Instrucciones Transact-SQL adicionales compatibles</span><span class="sxs-lookup"><span data-stu-id="42608-122">Additional Transact-SQL Statements That Are Supported</span></span>  
 <span data-ttu-id="42608-123">El Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] también proporciona compatibilidad con IntelliSense para las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="42608-123">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor also provides IntelliSense support for [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are shown in the following table.</span></span>  
  
|<span data-ttu-id="42608-124">Instrucción Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="42608-124">Transact-SQL statement</span></span>|<span data-ttu-id="42608-125">Sintaxis compatible</span><span class="sxs-lookup"><span data-stu-id="42608-125">Syntax supported</span></span>|  
|-----------------------------|----------------------|  
|[<span data-ttu-id="42608-126">INSERT</span><span class="sxs-lookup"><span data-stu-id="42608-126">INSERT</span></span>](/sql/t-sql/statements/insert-transact-sql)|<span data-ttu-id="42608-127">Toda la sintaxis, excepto la cláusula *execute_statement* .</span><span class="sxs-lookup"><span data-stu-id="42608-127">All syntax, except the *execute_statement* clause.</span></span>|  
|[<span data-ttu-id="42608-128">UPDATE</span><span class="sxs-lookup"><span data-stu-id="42608-128">UPDATE</span></span>](/sql/t-sql/queries/update-transact-sql)|<span data-ttu-id="42608-129">Toda la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="42608-129">All syntax.</span></span>|  
|[<span data-ttu-id="42608-130">DELETE</span><span class="sxs-lookup"><span data-stu-id="42608-130">DELETE</span></span>](/sql/t-sql/statements/delete-transact-sql)|<span data-ttu-id="42608-131">Toda la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="42608-131">All syntax.</span></span>|  
|[<span data-ttu-id="42608-132">DECLARE @local_variable</span><span class="sxs-lookup"><span data-stu-id="42608-132">DECLARE @local_variable</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)|<span data-ttu-id="42608-133">Toda la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="42608-133">All syntax.</span></span>|  
|[<span data-ttu-id="42608-134">CONJUNTO@local_variable</span><span class="sxs-lookup"><span data-stu-id="42608-134">SET @local_variable</span></span>](/sql/t-sql/language-elements/set-local-variable-transact-sql)|<span data-ttu-id="42608-135">Toda la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="42608-135">All syntax.</span></span>|  
|[<span data-ttu-id="42608-136">EXECUTE</span><span class="sxs-lookup"><span data-stu-id="42608-136">EXECUTE</span></span>](/sql/t-sql/language-elements/execute-transact-sql)|<span data-ttu-id="42608-137">Ejecución de procedimientos almacenados definidos por el usuario, procedimientos almacenados del sistema, funciones definidas por el usuario y funciones del sistema.</span><span class="sxs-lookup"><span data-stu-id="42608-137">Execution of user-defined stored procedures, system stored procedures, user-defined functions, and system functions.</span></span>|  
|[<span data-ttu-id="42608-138">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="42608-138">CREATE TABLE</span></span>](/sql/t-sql/statements/create-table-transact-sql)|<span data-ttu-id="42608-139">Toda la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="42608-139">All syntax.</span></span>|  
|[<span data-ttu-id="42608-140">CREATE VIEW</span><span class="sxs-lookup"><span data-stu-id="42608-140">CREATE VIEW</span></span>](/sql/t-sql/statements/create-view-transact-sql)|<span data-ttu-id="42608-141">Toda la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="42608-141">All syntax.</span></span>|  
|[<span data-ttu-id="42608-142">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="42608-142">CREATE PROCEDURE</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)|<span data-ttu-id="42608-143">Toda la sintaxis, con las excepciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="42608-143">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="42608-144">No hay compatibilidad con IntelliSense para la cláusula EXTERNAL NAME.</span><span class="sxs-lookup"><span data-stu-id="42608-144">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="42608-145">En la cláusula AS, IntelliSense solamente es compatible con las instrucciones y la sintaxis que se mencionan en este tema.</span><span class="sxs-lookup"><span data-stu-id="42608-145">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="42608-146">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="42608-146">ALTER PROCEDURE</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)|<span data-ttu-id="42608-147">Toda la sintaxis, con las excepciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="42608-147">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="42608-148">No hay compatibilidad con IntelliSense para la cláusula EXTERNAL NAME.</span><span class="sxs-lookup"><span data-stu-id="42608-148">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="42608-149">En la cláusula AS, IntelliSense solamente es compatible con las instrucciones y la sintaxis que se mencionan en este tema.</span><span class="sxs-lookup"><span data-stu-id="42608-149">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="42608-150">USE</span><span class="sxs-lookup"><span data-stu-id="42608-150">USE</span></span>](/sql/t-sql/language-elements/use-transact-sql)|<span data-ttu-id="42608-151">Toda la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="42608-151">All syntax.</span></span>|  
  
## <a name="intellisense-in-supported-statements"></a><span data-ttu-id="42608-152">IntelliSense en las instrucciones compatibles</span><span class="sxs-lookup"><span data-stu-id="42608-152">IntelliSense in Supported Statements</span></span>  
 <span data-ttu-id="42608-153">La característica IntelliSense del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] es compatible con los elementos de sintaxis siguientes cuando se utilizan en una de las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] compatibles:</span><span class="sxs-lookup"><span data-stu-id="42608-153">IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following syntax elements when they are used in one of the supported [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
-   <span data-ttu-id="42608-154">Todos los tipos de combinación, incluso APPLY</span><span class="sxs-lookup"><span data-stu-id="42608-154">All join types, including APPLY</span></span>  
  
-   <span data-ttu-id="42608-155">PIVOT y UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="42608-155">PIVOT and UNPIVOT</span></span>  
  
-   <span data-ttu-id="42608-156">Referencias a los objetos de base de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="42608-156">References to the following database objects:</span></span>  
  
    -   <span data-ttu-id="42608-157">Bases de datos y esquemas</span><span class="sxs-lookup"><span data-stu-id="42608-157">Databases and schemas</span></span>  
  
    -   <span data-ttu-id="42608-158">Tablas, vistas, funciones con valores de tabla y expresiones de tabla</span><span class="sxs-lookup"><span data-stu-id="42608-158">Tables, views, table-valued functions, and table expressions</span></span>  
  
    -   <span data-ttu-id="42608-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="42608-159">Columns</span></span>  
  
    -   <span data-ttu-id="42608-160">Procedimientos y parámetros de procedimientos</span><span class="sxs-lookup"><span data-stu-id="42608-160">Procedures and procedure parameters</span></span>  
  
    -   <span data-ttu-id="42608-161">Funciones escalares y expresiones escalares</span><span class="sxs-lookup"><span data-stu-id="42608-161">Scalar functions and scalar expressions</span></span>  
  
    -   <span data-ttu-id="42608-162">Variables locales</span><span class="sxs-lookup"><span data-stu-id="42608-162">Local variables</span></span>  
  
    -   <span data-ttu-id="42608-163">Expresiones de tabla común (CTE)</span><span class="sxs-lookup"><span data-stu-id="42608-163">Common table expressions (CTE)</span></span>  
  
-   <span data-ttu-id="42608-164">Objetos de base de datos a los que solo se hace referencia en instrucciones CREATE o ALTER del script o del proceso por lotes, pero que no existen en la base de datos porque el script o el proceso por lotes no se han ejecutado todavía.</span><span class="sxs-lookup"><span data-stu-id="42608-164">Database objects that are referenced only in CREATE or ALTER statements in the script or batch, but which do not exist in the database because the script or batch has not yet been run.</span></span> <span data-ttu-id="42608-165">Estos objetos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="42608-165">These objects are as follows:</span></span>  
  
    -   <span data-ttu-id="42608-166">Tablas y procedimientos especificados en una instrucción CREATE TABLE o CREATE PROCEDURE del script o del proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="42608-166">Tables and procedures that have been specified in a CREATE TABLE or CREATE PROCEDURE statement in the script or batch.</span></span>  
  
    -   <span data-ttu-id="42608-167">Cambios en las tablas y los procedimientos especificados en una instrucción ALTER TABLE o ALTER PROCEDURE del script o del proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="42608-167">Changes to tables and procedures that have been specified in an ALTER TABLE or ALTER PROCEDURE statement in the script or batch.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="42608-168">La característica IntelliSense no estará disponible para las columnas de una instrucción CREATE VIEW hasta que se haya ejecutado la instrucción CREATE VIEW.</span><span class="sxs-lookup"><span data-stu-id="42608-168">IntelliSense is not available for the columns of a CREATE VIEW statement until the CREATE VIEW statement has been executed.</span></span>  
  
 <span data-ttu-id="42608-169">La característica IntelliSense no se proporciona para los elementos enumerados anteriormente cuando se utilizan en otras instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42608-169">IntelliSense is not provided for the previously listed elements when they are used in other [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="42608-170">Por ejemplo, los nombres de columna que se utilizan en una instrucción SELECT son compatibles con IntelliSense, pero no los de columnas que se utilizan en la instrucción CREATE FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="42608-170">For example, there is IntelliSense support for column names that are used in a SELECT statement, but not for columns that are used in the CREATE FUNCTION statement.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="42608-171">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="42608-171">Examples</span></span>  
 <span data-ttu-id="42608-172">Dentro de un script o un proceso por lotes de [!INCLUDE[tsql](../../includes/tsql-md.md)] , la característica IntelliSense del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] solamente es compatible con las instrucciones y la sintaxis mencionadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="42608-172">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports only the statements and syntax that are listed in this topic.</span></span> <span data-ttu-id="42608-173">En los ejemplos de código de [!INCLUDE[tsql](../../includes/tsql-md.md)] siguientes se muestran las instrucciones y los elementos de sintaxis admitidos por IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="42608-173">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code examples show what statements and syntax elements IntelliSense supports.</span></span> <span data-ttu-id="42608-174">Por ejemplo, en el proceso por lotes siguiente, la característica IntelliSense está disponible para la instrucción `SELECT` cuando se codifica por sí misma, pero no cuando la instrucción `SELECT` está contenida en una instrucción `CREATE FUNCTION` .</span><span class="sxs-lookup"><span data-stu-id="42608-174">For example, in the following batch, IntelliSense is available for the `SELECT` statement when it is coded by itself, but not when the `SELECT` is contained in a `CREATE FUNCTION` statement.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Name  
FROM Production.Product  
WHERE Name LIKE N'Road-250%' and Color = N'Red';  
GO  
CREATE FUNCTION Production.ufn_Red250 ()  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT Name  
    FROM AdventureWorks2012.Production.Product  
    WHERE Name LIKE N'Road-250%'  
      AND Color = N'Red'  
);GO  
```  
  
 <span data-ttu-id="42608-175">Esta funcionalidad también se aplica a los conjuntos de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] de la cláusula AS de una instrucción CREATE PROCEDURE o ALTER PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="42608-175">This functionality also applies to the sets of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the AS clause of a CREATE PROCEDURE or ALTER PROCEDURE statement.</span></span>  
  
 <span data-ttu-id="42608-176">Dentro de un script o un proceso por lotes de [!INCLUDE[tsql](../../includes/tsql-md.md)] , la característica IntelliSense es compatible con los objetos que se han especificado en una instrucción CREATE o ALTER; sin embargo, estos objetos no existen en la base de datos porque no se han ejecutado las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="42608-176">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense supports objects that have been specified in a CREATE or ALTER statement; however, these objects do not exist in the database because the statements have not been executed.</span></span> <span data-ttu-id="42608-177">Por ejemplo, puede escribir el código siguiente en el Editor de consultas:</span><span class="sxs-lookup"><span data-stu-id="42608-177">For example, you might enter the following code in the Query Editor:</span></span>  
  
```  
USE MyTestDB;  
GO  
CREATE TABLE MyTable  
    (PrimaryKeyCol   INT PRIMARY KEY,  
    FirstNameCol      NVARCHAR(50),  
   LastNameCol       NVARCHAR(50));  
GO  
SELECT   
```  
  
 <span data-ttu-id="42608-178">Después de escribir `SELECT`, IntelliSense enumera **PrimaryKeyCol**, **FirstNameCol**y **LastNameCol** como posibles elementos en la lista de selección, aunque no se haya ejecutado el script y `MyTable` no exista todavía en `MyTestDB`.</span><span class="sxs-lookup"><span data-stu-id="42608-178">After you type `SELECT`, IntelliSense lists **PrimaryKeyCol**, **FirstNameCol**, and **LastNameCol** as possible elements in the select list, even if the script has not been executed and `MyTable` does not yet exist in `MyTestDB`.</span></span>  
  
  
