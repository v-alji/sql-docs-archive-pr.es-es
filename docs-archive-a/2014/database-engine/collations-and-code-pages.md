---
title: Intercalaciones y páginas de códigos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c626dcac-0474-432d-acc0-cfa643345372
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab904771fa8ac4acf25a624cbf3e1139f7e96434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674357"
---
# <a name="collations-and-code-pages"></a><span data-ttu-id="ba586-102">Intercalaciones y páginas de códigos</span><span class="sxs-lookup"><span data-stu-id="ba586-102">Collations and Code Pages</span></span>
  [!INCLUDE[hek_2](../includes/hek-2-md.md)] <span data-ttu-id="ba586-103">tiene restricciones en cuanto a las páginas de códigos compatibles para las columnas (var)char en las tablas optimizadas para memoria y las intercalaciones compatibles empleadas en índices y procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="ba586-103">has restrictions on supported code pages for (var)char columns in memory-optimized tables and supported collations used in indexes and natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="ba586-104">La página de códigos para un valor (var)char determina la asignación entre los caracteres y la representación de bytes que se almacena en la tabla.</span><span class="sxs-lookup"><span data-stu-id="ba586-104">The code page for a (var)char value determines the mapping between characters and the byte representation that is stored in the table.</span></span> <span data-ttu-id="ba586-105">Por ejemplo, con la página de códigos del alfabeto Latin 1 de Windows (1252; el valor predeterminado de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]), el carácter 'a' corresponde al byte 0x61.</span><span class="sxs-lookup"><span data-stu-id="ba586-105">For example, with the Windows Latin 1 code page (1252; the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default), the character 'a' corresponds to the byte 0x61.</span></span>  
  
 <span data-ttu-id="ba586-106">La página de códigos de un valor (var)char determina la intercalación asociada al valor.</span><span class="sxs-lookup"><span data-stu-id="ba586-106">The code page of a (var)char value is determined by the collation associated with the value.</span></span> <span data-ttu-id="ba586-107">Por ejemplo, la intercalación SQL_Latin1_General_CP1_CI_AS tiene la página de códigos asociada 1252.</span><span class="sxs-lookup"><span data-stu-id="ba586-107">For example, the collation SQL_Latin1_General_CP1_CI_AS has the associated code page 1252.</span></span>  
  
 <span data-ttu-id="ba586-108">La intercalación de un valor se hereda de la intercalación de la base de datos o se puede especificar explícitamente mediante la palabra clave COLLATE.</span><span class="sxs-lookup"><span data-stu-id="ba586-108">The collation of a value is either inherited from the database collation, or can be specified explicitly using the COLLATE keyword.</span></span> <span data-ttu-id="ba586-109">La intercalación de base de datos no se puede cambiar si la base de datos contiene tablas optimizadas para memoria o procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="ba586-109">Database collation cannot be changed if the database contains memory-optimized tables or natively compiled stored procedures.</span></span> <span data-ttu-id="ba586-110">El ejemplo siguiente establece la intercalación de base de datos y crea una tabla, que tiene una columna con una intercalación diferente.</span><span class="sxs-lookup"><span data-stu-id="ba586-110">The following example sets the database collation and creates a table, which has a column with a different collation.</span></span> <span data-ttu-id="ba586-111">La base de datos utiliza la intercalación sin distinción entre mayúsculas y minúsculas latina.</span><span class="sxs-lookup"><span data-stu-id="ba586-111">The database uses Latin case-insensitive collation.</span></span>  
  
 <span data-ttu-id="ba586-112">Los índices se pueden crear en columnas de cadena si utilizan una intercalación BIN2.</span><span class="sxs-lookup"><span data-stu-id="ba586-112">Indexes can only be created on string columns if they use a BIN2 collation.</span></span> <span data-ttu-id="ba586-113">La variable LastName utiliza la intercalación BIN2.</span><span class="sxs-lookup"><span data-stu-id="ba586-113">The LastName variable uses BIN2 collation.</span></span> <span data-ttu-id="ba586-114">FirstName utiliza el valor predeterminado de la base de datos, que es CI_AS (sin distinción entre mayúsculas y minúsculas, y con distinción de acentos).</span><span class="sxs-lookup"><span data-stu-id="ba586-114">FirstName uses the database default, which is CI_AS (case-insensitive, accent-sensitive).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ba586-115">No puede usar order by o group by en columnas de cadena de índice que no empleen la intercalación BIN2.</span><span class="sxs-lookup"><span data-stu-id="ba586-115">You cannot use order by or group by on index string columns that do not use BIN2 collation.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP  
  
ALTER DATABASE IMOLTP ADD FILEGROUP IMOLTP_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP ADD FILE( NAME = 'IMOLTP_mod' , FILENAME = 'c:\data\IMOLTP_mod') TO FILEGROUP IMOLTP_mod;  
--GO  
  
--  set the database collations  
ALTER DATABASE IMOLTP COLLATE Latin1_General_100_CI_AS  
GO  
  
--  
USE IMOLTP   
GO  
  
-- create a table with collation  
CREATE TABLE Employees (  
  EmployeeID int NOT NULL ,   
  LastName nvarchar(20) COLLATE Latin1_General_100_BIN2 NOT NULL INDEX IX_LastName NONCLUSTERED,   
  FirstName nvarchar(10) NOT NULL ,  
  CONSTRAINT PK_Employees PRIMARY KEY NONCLUSTERED HASH(EmployeeID)  WITH (BUCKET_COUNT=1024)  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY=SCHEMA_AND_DATA)  
GO  
```  
  
 <span data-ttu-id="ba586-116">Las restricciones siguientes se aplican a las tablas optimizadas para memoria y a los procedimientos almacenados compilados de forma nativa:</span><span class="sxs-lookup"><span data-stu-id="ba586-116">The following restrictions apply to memory-optimized tables and natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="ba586-117">Las columnas (var)char de las tablas optimizadas para memoria deben utilizar la intercalación de la página de códigos 1252.</span><span class="sxs-lookup"><span data-stu-id="ba586-117">(var)char columns in memory-optimized tables must use code page 1252 collation.</span></span> <span data-ttu-id="ba586-118">Esta restricción no se aplica a las columnas n(var)char.</span><span class="sxs-lookup"><span data-stu-id="ba586-118">This restriction does not apply to n(var)char columns.</span></span> <span data-ttu-id="ba586-119">El código siguiente recupera todas las intercalaciones 1252:</span><span class="sxs-lookup"><span data-stu-id="ba586-119">The following code retrieves all 1252 collations:</span></span>  
  
    ```sql  
    -- all supported collations for (var)char columns in memory-optimized tables  
    select * from sys.fn_helpcollations()  
    where collationproperty(name, 'codepage') = 1252;  
    ```  
  
     <span data-ttu-id="ba586-120">Si necesita almacenar caracteres que no sean Latin, use columnas n(var)char.</span><span class="sxs-lookup"><span data-stu-id="ba586-120">If you need to store non-Latin characters, use n(var)char columns.</span></span>  
  
-   <span data-ttu-id="ba586-121">Los índices en columnas (n)(var)char solo se pueden especificar con intercalaciones BIN2 (vea el primer ejemplo).</span><span class="sxs-lookup"><span data-stu-id="ba586-121">Indexes on (n)(var)char columns can only be specified with BIN2 collations (see the first example).</span></span> <span data-ttu-id="ba586-122">La consulta siguiente recupera todas las intercalaciones BIN2 admitidas:</span><span class="sxs-lookup"><span data-stu-id="ba586-122">The following query retrieves all supported BIN2 collations:</span></span>  
  
    ```sql  
    -- all supported collations for indexes on memory-optimized tables and   
    -- comparison/sorting in natively compiled stored procedures  
    select * from sys.fn_helpcollations() where name like '%BIN2'  
    ```  
  
     <span data-ttu-id="ba586-123">Si tiene acceso a la tabla con [!INCLUDE[tsql](../includes/tsql-md.md)]interpretado, puede utilizar la palabra clave `COLLATE` para cambiar la intercalación con expresiones o con operaciones de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ba586-123">If you access the table through interpreted [!INCLUDE[tsql](../includes/tsql-md.md)], you can use the `COLLATE` keyword to change the collation with expressions or sort operations.</span></span> <span data-ttu-id="ba586-124">Vea el ejemplo anterior para obtener un ejemplo de esto.</span><span class="sxs-lookup"><span data-stu-id="ba586-124">See the last example for a sample of this.</span></span>  
  
-   <span data-ttu-id="ba586-125">Los procedimientos almacenados compilados de forma nativa no pueden utilizar parámetros, variables locales ni constantes de cadena de tipo (var)char si la intercalación de base de datos no es una intercalación de página de códigos 1252.</span><span class="sxs-lookup"><span data-stu-id="ba586-125">Natively compiled stored procedures cannot use parameters, local variables, or string constants of (var)char type if the database collation is not a code page 1252 collation.</span></span>  
  
-   <span data-ttu-id="ba586-126">Todas las expresiones y operaciones de ordenación dentro de procedimientos almacenados compilados de forma nativa deben utilizar intercalaciones BIN2.</span><span class="sxs-lookup"><span data-stu-id="ba586-126">All expressions and sort operations inside natively compiled stored procedures must use BIN2 collations.</span></span> <span data-ttu-id="ba586-127">La implicación es que todas las comparaciones y las operaciones de ordenación están basadas en los puntos de código Unicode de los caracteres (representaciones binarias).</span><span class="sxs-lookup"><span data-stu-id="ba586-127">The implication is that all comparisons and sort operations are based on the Unicode code points of the characters (binary representations).</span></span> <span data-ttu-id="ba586-128">Por ejemplo, toda la clasificación distingue entre mayúsculas y minúsculas (la “Z” va antes de la “a”).</span><span class="sxs-lookup"><span data-stu-id="ba586-128">For example all sorting is case sensitive ('Z' comes before 'a').</span></span> <span data-ttu-id="ba586-129">Si fuera necesario, utilice [!INCLUDE[tsql](../includes/tsql-md.md)] interpretado para la ordenación sin distinción entre mayúsculas y minúsculas y la comparación.</span><span class="sxs-lookup"><span data-stu-id="ba586-129">If necessary, use interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] for case-insensitive sorting and comparison.</span></span>  
  
-   <span data-ttu-id="ba586-130">El truncamiento de los datos UTF-16 no se admite dentro de procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="ba586-130">Truncation of UTF-16 data is not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="ba586-131">Esto significa que los valores n (var) Char (*n*) no se pueden convertir al tipo n (var) Char (*i*) *, si*  <  *n*, si la intercalación tiene _SC propiedad.</span><span class="sxs-lookup"><span data-stu-id="ba586-131">This means that n(var)char(*n*) values cannot be converted to type n(var)char(*i*), if *i* < *n*, if the collation has _SC property.</span></span> <span data-ttu-id="ba586-132">Por ejemplo, la siguiente vista no se admite:</span><span class="sxs-lookup"><span data-stu-id="ba586-132">For example, the following is not supported:</span></span>  
  
    ```sql  
    -- column definition using an _SC collation  
     c2 nvarchar(200) collate Latin1_General_100_CS_AS_SC not null   
    -- assignment to a smaller variable, requiring truncation  
     declare @c2 nvarchar(100) = '';  
     select @c2 = c2  
    ```  
  
     <span data-ttu-id="ba586-133">Las funciones de manipulación de cadenas, como LEN, SUBSTRING, LTRIM y RTRIM y con datos UTF-16 no son procedimientos almacenados compilados de forma nativa admitidos.</span><span class="sxs-lookup"><span data-stu-id="ba586-133">String manipulation functions, such as LEN, SUBSTRING, LTRIM, and RTRIM with UTF-16 data are not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="ba586-134">No puede utilizar estas funciones de manipulación de cadenas para valores n(var)char que tengan una intercalación _SC.</span><span class="sxs-lookup"><span data-stu-id="ba586-134">You cannot use these string manipulation functions for n(var)char values that have an _SC collation.</span></span>  
  
     <span data-ttu-id="ba586-135">Declare las variables con tipos lo suficientemente grandes para evitar el truncamiento.</span><span class="sxs-lookup"><span data-stu-id="ba586-135">Declare variables using types that are large enough to avoid truncation.</span></span>  
  
 <span data-ttu-id="ba586-136">El ejemplo siguiente muestra algunas de las implicaciones y las soluciones alternativas para las limitaciones de la intercalación en OLTP en memoria.</span><span class="sxs-lookup"><span data-stu-id="ba586-136">The following example shows some of the implications and workarounds for the collation limitations in In-Memory OLTP.</span></span> <span data-ttu-id="ba586-137">El ejemplo utiliza la tabla employees especificada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ba586-137">The example uses the Employees table specified above.</span></span> <span data-ttu-id="ba586-138">En este ejemplo se enumeran todos los empleados.</span><span class="sxs-lookup"><span data-stu-id="ba586-138">This sample list all employees .</span></span> <span data-ttu-id="ba586-139">Observe que, para LastName, debido a la intercalación binaria, los nombres en mayúsculas se clasifican antes que los nombres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ba586-139">Notice that for LastName, due to the binary collation, the upper case names are sorted before lower case.</span></span> <span data-ttu-id="ba586-140">Por consiguiente, 'Thomas' viene antes de 'nolan' porque los caracteres en mayúsculas tienen puntos de código inferiores.</span><span class="sxs-lookup"><span data-stu-id="ba586-140">Therefore, 'Thomas' comes before 'nolan' because upper case characters have lower code points.</span></span> <span data-ttu-id="ba586-141">FirstName tiene una intercalación sin distinción entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ba586-141">FirstName has a case-insensitive collation.</span></span> <span data-ttu-id="ba586-142">Así, la clasificación se realiza según la letra del alfabeto, no por el punto de código de los caracteres.</span><span class="sxs-lookup"><span data-stu-id="ba586-142">So, sorting is by letter of the alphabet, not code point of the characters.</span></span>  
  
```sql  
-- insert a number of values  
INSERT Employees VALUES (1,'thomas', 'john')  
INSERT Employees VALUES (2,'Thomas', 'rupert')  
INSERT Employees VALUES (3,'Thomas', 'Jack')  
INSERT Employees VALUES (4,'Thomas', 'annie')  
INSERT Employees VALUES (5,'nolan', 'John')  
GO  
  
-- ===========  
SELECT EmployeeID, LastName, FirstName FROM Employees  
ORDER BY LastName, FirstName  
GO  
  
-- ===========  
-- specify collation: sorting uses case-insensitive collation, thus 'nolan' comes before 'Thomas'  
SELECT * FROM Employees  
ORDER BY LastName COLLATE Latin1_General_100_CI_AS, FirstName  
GO  
  
-- ===========  
-- retrieve employee by Name  
-- must use BIN2 collation for comparison in natively compiled stored procedures  
CREATE PROCEDURE usp_EmployeeByName @LastName nvarchar(20), @FirstName nvarchar(10)  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH   
(  TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
  LANGUAGE = N'us_english'  
)  
  SELECT EmployeeID, LastName, FirstName FROM dbo.Employees  
  WHERE   
    LastName = @LastName AND  
    FirstName COLLATE Latin1_General_100_BIN2 = @FirstName  
  
END  
GO  
  
-- this does not return any rows, as EmployeeID 1 has first name 'john', which is not equal to 'John' in a binary collation  
EXEC usp_EmployeeByName 'thomas', 'John'  
  
-- this retrieves EmployeeID 1  
EXEC usp_EmployeeByName 'thomas', 'john'  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba586-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba586-143">See Also</span></span>  
 [<span data-ttu-id="ba586-144">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="ba586-144">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
