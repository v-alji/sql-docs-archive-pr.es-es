---
title: Leer datos de una tabla (Tutorial) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- reading data in a table
ms.assetid: 532232c9-3d41-45cd-9150-de67a1cbfcf5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4bdaaeeddf8f35792c536624abfe6ff11b2dbd2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674473"
---
# <a name="reading-the-data-in-a-table-tutorial"></a><span data-ttu-id="fd266-102">Leer datos de una tabla (Tutorial)</span><span class="sxs-lookup"><span data-stu-id="fd266-102">Reading the Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="fd266-103">Use la instrucción SELECT para leer los datos de una tabla.</span><span class="sxs-lookup"><span data-stu-id="fd266-103">Use the SELECT statement to read the data in a table.</span></span> <span data-ttu-id="fd266-104">La instrucción SELECT es una de las instrucciones de [!INCLUDE[tsql](../includes/tsql-md.md)] más importantes y tiene muchas variaciones en la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="fd266-104">The SELECT statement is one of the most important [!INCLUDE[tsql](../includes/tsql-md.md)] statements, and there are many variations in the syntax.</span></span> <span data-ttu-id="fd266-105">Para este tutorial, trabajará con cinco versiones sencillas.</span><span class="sxs-lookup"><span data-stu-id="fd266-105">For this tutorial, you will work with five simple versions.</span></span>  
  
### <a name="to-read-the-data-in-a-table"></a><span data-ttu-id="fd266-106">Para leer los datos de una tabla</span><span class="sxs-lookup"><span data-stu-id="fd266-106">To read the data in a table</span></span>  
  
1.  <span data-ttu-id="fd266-107">Escriba y ejecute las siguientes instrucciones para leer los datos de la tabla `Products` .</span><span class="sxs-lookup"><span data-stu-id="fd266-107">Type and execute the following statements to read the data in the `Products` table.</span></span>  
  
    ```  
    -- The basic syntax for reading data from a single table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
    GO  
  
    ```  
  
2.  <span data-ttu-id="fd266-108">Puede usar un asterisco para seleccionar todas las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="fd266-108">You can use an asterisk to select all the columns in the table.</span></span> <span data-ttu-id="fd266-109">Esto se suele usar en las consultas ad hoc.</span><span class="sxs-lookup"><span data-stu-id="fd266-109">This is often used in ad hoc queries.</span></span> <span data-ttu-id="fd266-110">Debe proporcionar la lista de columnas en el código permanente de modo que la instrucción devuelva las columnas previstas, incluso si más tarde se agrega una columna nueva a la tabla.</span><span class="sxs-lookup"><span data-stu-id="fd266-110">You should provide the column list in you permanent code so that the statement will return the predicted columns, even if a new column is added to the table later.</span></span>  
  
    ```  
    -- Returns all columns in the table  
    -- Does not use the optional schema, dbo  
    SELECT * FROM Products  
    GO  
  
    ```  
  
3.  <span data-ttu-id="fd266-111">Puede omitir columnas que ya no desea que se devuelvan.</span><span class="sxs-lookup"><span data-stu-id="fd266-111">You can omit columns that you do not want to return.</span></span> <span data-ttu-id="fd266-112">Las columnas se devolverán en el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="fd266-112">The columns will be returned in the order that they are listed.</span></span>  
  
    ```  
    -- Returns only two of the columns from the table  
    SELECT ProductName, Price  
        FROM dbo.Products  
    GO  
  
    ```  
  
4.  <span data-ttu-id="fd266-113">Use una cláusula `WHERE` para limitar las filas que se devuelven al usuario.</span><span class="sxs-lookup"><span data-stu-id="fd266-113">Use a `WHERE` clause to limit the rows that are returned to the user.</span></span>  
  
    ```  
    -- Returns only two of the records in the table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
        WHERE ProductID < 60  
    GO  
  
    ```  
  
5.  <span data-ttu-id="fd266-114">Puede trabajar con los valores de las columnas según se devuelven.</span><span class="sxs-lookup"><span data-stu-id="fd266-114">You can work with the values in the columns as they are returned.</span></span> <span data-ttu-id="fd266-115">En el siguiente ejemplo se realiza una operación matemática en la columna `Price` .</span><span class="sxs-lookup"><span data-stu-id="fd266-115">The following example performs a mathematical operation on the `Price` column.</span></span> <span data-ttu-id="fd266-116">Las columnas que se han cambiado de esta manera no tendrán un nombre, a menos que proporcione uno mediante la palabra clave `AS` .</span><span class="sxs-lookup"><span data-stu-id="fd266-116">Columns that have been changed in this way will not have a name unless you provide one by using the `AS` keyword.</span></span>  
  
    ```  
    -- Returns ProductName and the Price including a 7% tax  
    -- Provides the name CustomerPays for the calculated column  
    SELECT ProductName, Price * 1.07 AS CustomerPays  
        FROM dbo.Products  
    GO  
    ```  
  
## <a name="functions-that-are-useful-in-a-select-statement"></a><span data-ttu-id="fd266-117">Funciones útiles en una instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="fd266-117">Functions That Are Useful in a SELECT Statement</span></span>  
 <span data-ttu-id="fd266-118">Para obtener información sobre algunas de las funciones que puede usar para trabajar con datos en instrucciones SELECT, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="fd266-118">For information about some functions that you can use to work with data in SELECT statements, see the following topics:</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="fd266-119">Funciones de cadena &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd266-119">String Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/string-functions-transact-sql)|[<span data-ttu-id="fd266-120">Tipos de datos y funciones de fecha y hora &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd266-120">Date and Time Data Types and Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|  
|[<span data-ttu-id="fd266-121">Funciones matemáticas &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd266-121">Mathematical Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)|[<span data-ttu-id="fd266-122">Funciones de texto e imagen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd266-122">Text and Image Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/text-and-image-functions-textptr-transact-sql)|  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="fd266-123">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="fd266-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="fd266-124">Resumen: Creación de objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="fd266-124">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="fd266-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd266-125">See Also</span></span>  
 [<span data-ttu-id="fd266-126">SELECT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd266-126">SELECT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/select-transact-sql)  
  
  
