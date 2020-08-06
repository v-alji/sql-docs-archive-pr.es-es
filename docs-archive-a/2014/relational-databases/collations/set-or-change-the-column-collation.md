---
title: Establecer o cambiar la intercalación de columnas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tempdb database [SQL Server], collations
- collations [SQL Server], column
ms.assetid: d7a9638b-717c-4680-9b98-8849081e08be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8211569b6ce83faaec043e5eb527a60f0ddab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677693"
---
# <a name="set-or-change-the-column-collation"></a><span data-ttu-id="59f0b-102">Establecer o cambiar la intercalación de columnas</span><span class="sxs-lookup"><span data-stu-id="59f0b-102">Set or Change the Column Collation</span></span>
  <span data-ttu-id="59f0b-103">Puede invalidar la intercalación de base de datos para los datos `char`, `varchar`, `text`, `nchar`, `nvarchar` y `ntext` especificando una intercalación diferente para una columna específica de una tabla y utilizando una de las siguientes cláusulas:</span><span class="sxs-lookup"><span data-stu-id="59f0b-103">You can override the database collation for `char`, `varchar`, `text`, `nchar`, `nvarchar`, and `ntext` data by specifying a different collation for a specific column of a table and using one of the following:</span></span>  
  
-   <span data-ttu-id="59f0b-104">La cláusula COLLATE de [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) y [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59f0b-104">The COLLATE clause of [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) and [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span> <span data-ttu-id="59f0b-105">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="59f0b-105">For example:</span></span>  
  
    ```  
    CREATE TABLE dbo.MyTable  
      (PrimaryKey   int PRIMARY KEY,  
       CharCol      varchar(10) COLLATE French_CI_AS NOT NULL  
      );  
    GO  
    ALTER TABLE dbo.MyTable ALTER COLUMN CharCol  
                varchar(10)COLLATE Latin1_General_CI_AS NOT NULL;  
    GO  
    ```  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="59f0b-106">.</span><span class="sxs-lookup"><span data-stu-id="59f0b-106">.</span></span> <span data-ttu-id="59f0b-107">Para obtener más información, vea [Collation and Unicode Support](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="59f0b-107">For more information, [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="59f0b-108">Usar la `Column.Collation` propiedad en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objetos de administración de (SMO).</span><span class="sxs-lookup"><span data-stu-id="59f0b-108">Using the `Column.Collation` property in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="59f0b-109">No puede cambiar una intercalación de una columna a la que se hace referencia mediante uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="59f0b-109">You cannot change the collation of a column that is currently referenced by any one of the following:</span></span>  
  
-   <span data-ttu-id="59f0b-110">Una columna calculada</span><span class="sxs-lookup"><span data-stu-id="59f0b-110">A computed column</span></span>  
  
-   <span data-ttu-id="59f0b-111">Un índice</span><span class="sxs-lookup"><span data-stu-id="59f0b-111">An index</span></span>  
  
-   <span data-ttu-id="59f0b-112">Estadísticas de distribución, ya sean generadas automáticamente o mediante la instrucción CREATE STATISTICS</span><span class="sxs-lookup"><span data-stu-id="59f0b-112">Distribution statistics, either generated automatically or by the CREATE STATISTICS statement</span></span>  
  
-   <span data-ttu-id="59f0b-113">Una restricción CHECK</span><span class="sxs-lookup"><span data-stu-id="59f0b-113">A CHECK constraint</span></span>  
  
-   <span data-ttu-id="59f0b-114">Una restricción FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="59f0b-114">A FOREIGN KEY constraint</span></span>  
  
 <span data-ttu-id="59f0b-115">Al trabajar con la base de datos **tempdb**, la cláusula [COLLATE](/sql/t-sql/statements/collations) incluye una opción *database_default* para especificar que una columna de una tabla temporal use el valor predeterminado de intercalación de la base de datos del usuario actual para la conexión en lugar de la intercalación de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="59f0b-115">When you work with **tempdb**, the [COLLATE](/sql/t-sql/statements/collations) clause includes a *database_default* option to specify that a column in a temporary table uses the collation default of the current user database for the connection instead of the collation of **tempdb**.</span></span>  
  
## <a name="collations-and-text-columns"></a><span data-ttu-id="59f0b-116">Intercalaciones y columnas de texto</span><span class="sxs-lookup"><span data-stu-id="59f0b-116">Collations and text Columns</span></span>  
 <span data-ttu-id="59f0b-117">Puede insertar o actualizar los valores de una columna `text` cuya intercalación sea diferente a la de la página de códigos de la intercalación predeterminada de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="59f0b-117">You can insert or update values in a `text` column whose collation is different from the code page of the default collation of the database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="59f0b-118">convierte implícitamente los valores a la intercalación de la columna.</span><span class="sxs-lookup"><span data-stu-id="59f0b-118">implicitly converts the values to the collation of the column.</span></span>  
  
## <a name="collations-and-tempdb"></a><span data-ttu-id="59f0b-119">Intercalación y tempdb</span><span class="sxs-lookup"><span data-stu-id="59f0b-119">Collations and tempdb</span></span>  
 <span data-ttu-id="59f0b-120">La base de datos **tempdb** se crea cada vez que se inicia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y tiene la misma intercalación predeterminada que la base de datos **model** .</span><span class="sxs-lookup"><span data-stu-id="59f0b-120">The **tempdb** database is built every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started and has the same default collation as the **model** database.</span></span> <span data-ttu-id="59f0b-121">Suele ser la misma que la intercalación predeterminada de la instancia.</span><span class="sxs-lookup"><span data-stu-id="59f0b-121">This is typically the same as the default collation of the instance.</span></span> <span data-ttu-id="59f0b-122">Si crea una base de datos de usuario y especifica una intercalación predeterminada distinta de **model**, la base de datos de usuario tiene una intercalación predeterminada distinta de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="59f0b-122">If you create a user database and specify a different default collation than **model**, the user database has a different default collation than **tempdb**.</span></span> <span data-ttu-id="59f0b-123">Todos los procedimientos almacenados temporales o tablas temporales se crean y se almacenan en **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="59f0b-123">All temporary stored procedures or temporary tables are created and stored in **tempdb**.</span></span> <span data-ttu-id="59f0b-124">Esto significa que todas las columnas implícitas de las tablas temporales y todas las constantes, variables y parámetros coaccionable-predeterminados en los procedimientos almacenados temporales tienen intercalaciones distintas de los objetos comparables creados en las tablas y procedimientos almacenados permanentes.</span><span class="sxs-lookup"><span data-stu-id="59f0b-124">This means that all implicit columns in temporary tables and all coercible-default constants, variables, and parameters in temporary stored procedures have collations that are different from comparable objects created in permanent tables and stored procedures.</span></span>  
  
 <span data-ttu-id="59f0b-125">Esto puede causar problemas con una discrepancia en intercalaciones entre bases de datos definidas por el usuario y objetos de base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="59f0b-125">This could lead to problems with a mismatch in collations between user-defined databases and system database objects.</span></span> <span data-ttu-id="59f0b-126">Por ejemplo, una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliza la intercalación Latin1_General_CS_AS y se ejecutan las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="59f0b-126">For example, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the Latin1_General_CS_AS collation and you execute the following statements:</span></span>  
  
```  
CREATE DATABASE TestDB COLLATE Estonian_CS_AS;  
USE TestDB;  
CREATE TABLE TestPermTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
```  
  
 <span data-ttu-id="59f0b-127">En este sistema, la base de datos **tempdb** usa la intercalación Latin1_General_CS_AS con la página de códigos 1252, y `TestDB` y `TestPermTab.Col1` usan la intercalación `Estonian_CS_AS` con la página de códigos 1257.</span><span class="sxs-lookup"><span data-stu-id="59f0b-127">In this system, the **tempdb** database uses the Latin1_General_CS_AS collation with code page 1252, and `TestDB` and `TestPermTab.Col1` use the `Estonian_CS_AS` collation with code page 1257.</span></span> <span data-ttu-id="59f0b-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="59f0b-128">For example:</span></span>  
  
```  
USE TestDB;  
GO  
-- Create a temporary table with the same column declarations  
-- as TestPermTab  
CREATE TABLE #TestTempTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
INSERT INTO #TestTempTab  
         SELECT * FROM TestPermTab;  
GO  
```  
  
 <span data-ttu-id="59f0b-129">Con el ejemplo anterior, la base de datos **tempdb** usa la intercalación Latin1_General_CS_AS collation, y `TestDB` y `TestTab.Col1` usan la intercalación `Estonian_CS_AS` .</span><span class="sxs-lookup"><span data-stu-id="59f0b-129">With the previous example, the **tempdb** database uses the Latin1_General_CS_AS collation, and `TestDB` and `TestTab.Col1` use the `Estonian_CS_AS` collation.</span></span> <span data-ttu-id="59f0b-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="59f0b-130">For example:</span></span>  
  
```  
SELECT * FROM TestPermTab AS a INNER JOIN #TestTempTab on a.Col1 = #TestTempTab.Col1;  
```  
  
 <span data-ttu-id="59f0b-131">Dado que **tempdb** usa la intercalación de servidor predeterminada y `TestPermTab.Col1` usa una intercalación diferente, SQL Server devuelve este error: "No se puede resolver el conflicto de intercalación entre 'Latin1_General_CI_AS_KS_WS' y 'Estonian_CS_AS' en la operación Igual a".</span><span class="sxs-lookup"><span data-stu-id="59f0b-131">Because **tempdb** uses the default server collation and `TestPermTab.Col1` uses a different collation, SQL Server returns this error: "Cannot resolve collation conflict between 'Latin1_General_CI_AS_KS_WS' and 'Estonian_CS_AS' in equal to operation."</span></span>  
  
 <span data-ttu-id="59f0b-132">Para evitar el error, puede utilizar cualquiera de las alternativas siguientes:</span><span class="sxs-lookup"><span data-stu-id="59f0b-132">To prevent the error, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="59f0b-133">Especifique que la columna de la tabla temporal utilice la intercalación predeterminada de la base de datos de usuario, no **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="59f0b-133">Specify that the temporary table column use the default collation of the user database, not **tempdb**.</span></span> <span data-ttu-id="59f0b-134">Esto permite que la tabla temporal trabaje con tablas de un formato parecido en varias bases de datos, si es un requisito de su sistema.</span><span class="sxs-lookup"><span data-stu-id="59f0b-134">This enables the temporary table to work with similarly formatted tables in multiple databases, if that is required of your system.</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE database_default  
       );  
    ```  
  
-   <span data-ttu-id="59f0b-135">Especifique la intercalación correcta de la columna `#TestTempTab` :</span><span class="sxs-lookup"><span data-stu-id="59f0b-135">Specify the correct collation for the `#TestTempTab` column:</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE Estonian_CS_AS  
       );  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="59f0b-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59f0b-136">See Also</span></span>  
 <span data-ttu-id="59f0b-137">[Establecer o cambiar la intercalación del servidor](set-or-change-the-server-collation.md) </span><span class="sxs-lookup"><span data-stu-id="59f0b-137">[Set or Change the Server Collation](set-or-change-the-server-collation.md) </span></span>  
 <span data-ttu-id="59f0b-138">[Establecer o cambiar la intercalación de base de datos](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="59f0b-138">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 [<span data-ttu-id="59f0b-139">Compatibilidad con la intercalación y Unicode</span><span class="sxs-lookup"><span data-stu-id="59f0b-139">Collation and Unicode Support</span></span>](collation-and-unicode-support.md)  
  
  
