---
title: Crear una tabla (Tutorial) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating tables
ms.assetid: 653f2dd3-36a2-4bd5-8703-71a57d244661
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: c772f2527bd5ddb8a6759cbaa72d8aed9277f5cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674476"
---
# <a name="creating-a-table-tutorial"></a><span data-ttu-id="7d506-102">Crear una tabla (Tutorial)</span><span class="sxs-lookup"><span data-stu-id="7d506-102">Creating a Table (Tutorial)</span></span>
  <span data-ttu-id="7d506-103">Para crear una tabla, debe proporcionar un nombre para ésta además de los nombres y los tipos de datos de cada columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="7d506-103">To create a table, you must provide a name for the table, and the names and data types of each column in the table.</span></span> <span data-ttu-id="7d506-104">También es recomendable indicar si se permiten valores NULL en cada columna.</span><span class="sxs-lookup"><span data-stu-id="7d506-104">It is also a good practice to indicate whether null values are allowed in each column.</span></span>  
  
 <span data-ttu-id="7d506-105">La mayoría de las tablas tienen una clave principal, que se compone de una o varias columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="7d506-105">Most tables have a primary key, made up of one or more columns of the table.</span></span> <span data-ttu-id="7d506-106">Una clave principal siempre es única.</span><span class="sxs-lookup"><span data-stu-id="7d506-106">A primary key is always unique.</span></span> <span data-ttu-id="7d506-107">[!INCLUDE[ssDE](../includes/ssde-md.md)] exigirá la restricción de que el valor de la clave principal no se puede repetir en la tabla.</span><span class="sxs-lookup"><span data-stu-id="7d506-107">The [!INCLUDE[ssDE](../includes/ssde-md.md)] will enforce the restriction that any primary key value cannot be repeated in the table.</span></span>  
  
 <span data-ttu-id="7d506-108">Para obtener una lista de tipos de datos y vínculos para una descripción de cada uno, consulte [Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7d506-108">For a list of data types and links for a description of each, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d506-109">[!INCLUDE[ssDE](../includes/ssde-md.md)] se puede instalar para distinguir mayúsculas de minúsculas o no distinguir mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7d506-109">The [!INCLUDE[ssDE](../includes/ssde-md.md)] can be installed as case sensitive or non-case sensitive.</span></span> <span data-ttu-id="7d506-110">Si se instala [!INCLUDE[ssDE](../includes/ssde-md.md)] para distinguir mayúsculas de minúsculas, los nombres de objetos siempre deben tener las mismas mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7d506-110">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as case sensitive, object names must always have the same case.</span></span> <span data-ttu-id="7d506-111">Por ejemplo, una tabla denominada OrderData es diferente de la denominada ORDERDATA.</span><span class="sxs-lookup"><span data-stu-id="7d506-111">For example, a table named OrderData is a different table from a table named ORDERDATA.</span></span> <span data-ttu-id="7d506-112">Si se instala [!INCLUDE[ssDE](../includes/ssde-md.md)] para no distinguir mayúsculas de minúsculas, esos dos nombres de tablas se consideran la misma tabla y ese nombre solo se puede utilizar una vez.</span><span class="sxs-lookup"><span data-stu-id="7d506-112">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as non-case sensitive, those two table names are considered to be the same table, and that name can only be used one time.</span></span>  
  
### <a name="to-create-a-database-to-contain-the-new-table"></a><span data-ttu-id="7d506-113">Para crear una base de datos que contenga la nueva tabla</span><span class="sxs-lookup"><span data-stu-id="7d506-113">To create a database to contain the new table</span></span>  
  
-   <span data-ttu-id="7d506-114">Escriba el código siguiente en una ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="7d506-114">Enter the following code into a Query Editor window.</span></span>  
  
    ```  
    USE master;  
    GO  
  
    --Delete the TestData database if it exists.  
    IF EXISTS(SELECT * from sys.databases WHERE name='TestData')  
    BEGIN  
        DROP DATABASE TestData;  
    END  
  
    --Create a new database called TestData.  
    CREATE DATABASE TestData;  
    Press the F5 key to execute the code and create the database.  
    ```  
  
### <a name="switch-the-query-editor-connection-to-the-testdata-database"></a><span data-ttu-id="7d506-115">Cambie la conexión del Editor de consultas a la base de datos TestData</span><span class="sxs-lookup"><span data-stu-id="7d506-115">Switch the Query Editor connection to the TestData database</span></span>  
  
-   <span data-ttu-id="7d506-116">En una ventana del Editor de consultas, escriba y ejecute el siguiente código para cambiar la conexión a la base de datos `TestData` .</span><span class="sxs-lookup"><span data-stu-id="7d506-116">In a Query Editor window, type and execute the following code to change your connection to the `TestData` database.</span></span>  
  
    ```  
    USE TestData  
    GO  
    ```  
  
### <a name="to-create-a-table"></a><span data-ttu-id="7d506-117">Para crear una tabla</span><span class="sxs-lookup"><span data-stu-id="7d506-117">To create a table</span></span>  
  
-   <span data-ttu-id="7d506-118">En una ventana del Editor de consultas, escriba y ejecute el siguiente código para crear una tabla sencilla denominada `Products`.</span><span class="sxs-lookup"><span data-stu-id="7d506-118">In a Query Editor window, type and execute the following code to create a simple table named `Products`.</span></span> <span data-ttu-id="7d506-119">Las columnas de la tabla son `ProductID`, `ProductName`, `Price`y `ProductDescription`.</span><span class="sxs-lookup"><span data-stu-id="7d506-119">The columns in the table are named `ProductID`, `ProductName`, `Price`, and `ProductDescription`.</span></span> <span data-ttu-id="7d506-120">La columna `ProductID` es la clave principal de la tabla.</span><span class="sxs-lookup"><span data-stu-id="7d506-120">The `ProductID` column is the primary key of the table.</span></span> <span data-ttu-id="7d506-121">`int`, `varchar(25)`, `money`y `text` son todos los tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="7d506-121">`int`, `varchar(25)`, `money`, and `text` are all data types.</span></span> <span data-ttu-id="7d506-122">Solo las columnas `Price` y `ProductionDescription` pueden no tener datos cuando se inserta o cambia una fila.</span><span class="sxs-lookup"><span data-stu-id="7d506-122">Only the `Price` and `ProductionDescription` columns can have no data when a row is inserted or changed.</span></span> <span data-ttu-id="7d506-123">Esta instrucción contiene un elemento opcional (`dbo.`) denominado esquema.</span><span class="sxs-lookup"><span data-stu-id="7d506-123">This statement contains an optional element (`dbo.`) called a schema.</span></span> <span data-ttu-id="7d506-124">El esquema es el objeto de base de datos propietario de la tabla.</span><span class="sxs-lookup"><span data-stu-id="7d506-124">The schema is the database object that owns the table.</span></span> <span data-ttu-id="7d506-125">Si es un administrador, `dbo` es el esquema predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7d506-125">If you are an administrator, `dbo` is the default schema.</span></span> <span data-ttu-id="7d506-126">`dbo` hace referencia al propietario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7d506-126">`dbo` stands for database owner.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products  
       (ProductID int PRIMARY KEY NOT NULL,  
        ProductName varchar(25) NOT NULL,  
        Price money NULL,  
        ProductDescription text NULL)  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7d506-127">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="7d506-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7d506-128">Insertar y actualizar datos en una tabla &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="7d506-128">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](../t-sql/lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d506-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d506-129">See Also</span></span>  
 [<span data-ttu-id="7d506-130">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7d506-130">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
