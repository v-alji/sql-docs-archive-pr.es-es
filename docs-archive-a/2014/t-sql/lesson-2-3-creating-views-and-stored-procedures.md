---
title: Crear vistas y procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating views and stored procedures
ms.assetid: 53a0426d-07d8-4b7c-aa21-22632753bad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 76f6ecec446536191e8be4b05547ba5fd44c9d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743823"
---
# <a name="creating-views-and-stored-procedures"></a><span data-ttu-id="53136-102">Crear vistas y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="53136-102">Creating Views and Stored Procedures</span></span>
  <span data-ttu-id="53136-103">Ahora que Mary puede tener acceso a la base de datos **TestData** , puede que desee crear algunos objetos de base de datos, como una vista o un procedimiento almacenado y concederle a Mary acceso a los mismos.</span><span class="sxs-lookup"><span data-stu-id="53136-103">Now that Mary can access the **TestData** database, you may want to create some database objects, such as a view and a stored procedure, and then grant Mary access to them.</span></span> <span data-ttu-id="53136-104">Una vista es una instrucción SELECT almacenada y un procedimiento almacenado es una o varias instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] que se ejecutan como un lote.</span><span class="sxs-lookup"><span data-stu-id="53136-104">A view is a stored SELECT statement, and a stored procedure is one or more [!INCLUDE[tsql](../includes/tsql-md.md)] statements that execute as a batch.</span></span>  
  
 <span data-ttu-id="53136-105">Las vistas se consultan como las tablas y no aceptan parámetros.</span><span class="sxs-lookup"><span data-stu-id="53136-105">Views are queried like tables and do not accept parameters.</span></span> <span data-ttu-id="53136-106">Los procedimientos almacenados son más complejos que las vistas.</span><span class="sxs-lookup"><span data-stu-id="53136-106">Stored procedures are more complex than views.</span></span> <span data-ttu-id="53136-107">Los procedimientos almacenados pueden tener parámetros de entrada y salida y pueden contener instrucciones para controlar el flujo del código, como instrucciones IF y WHILE.</span><span class="sxs-lookup"><span data-stu-id="53136-107">Stored procedures can have both input and output parameters and can contain statements to control the flow of the code, such as IF and WHILE statements.</span></span> <span data-ttu-id="53136-108">Una práctica recomendable de programación es usar procedimientos almacenados para realizar todas las tareas repetitivas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="53136-108">It is good programming practice to use stored procedures for all repetitive actions in the database.</span></span>  
  
 <span data-ttu-id="53136-109">Para este ejemplo, usará CREATE VIEW para crear una vista que seleccione solo dos de las columnas de la tabla **Products** .</span><span class="sxs-lookup"><span data-stu-id="53136-109">For this example, you will use CREATE VIEW to create a view that selects only two of the columns in the **Products** table.</span></span> <span data-ttu-id="53136-110">A continuación, usará CREATE PROCEDURE para crear un procedimiento almacenado que acepta un parámetro de precio y devuelve solo los productos cuyo costo es menor que el valor del parámetro especificado.</span><span class="sxs-lookup"><span data-stu-id="53136-110">Then, you will use CREATE PROCEDURE to create a stored procedure that accepts a price parameter and returns only those products that cost less than the specified parameter value.</span></span>  
  
### <a name="to-create-a-view"></a><span data-ttu-id="53136-111">Para crear una vista</span><span class="sxs-lookup"><span data-stu-id="53136-111">To create a view</span></span>  
  
1.  <span data-ttu-id="53136-112">Ejecute la instrucción siguiente para crear una vista muy sencilla que ejecuta una instrucción SELECT y devuelve los nombres y los precios de nuestros productos al usuario.</span><span class="sxs-lookup"><span data-stu-id="53136-112">Execute the following statement to create a very simple view that executes a select statement, and returns the names and prices of our products to the user.</span></span>  
  
    ```  
    CREATE VIEW vw_Names  
       AS  
       SELECT ProductName, Price FROM Products;  
    GO  
  
    ```  
  
### <a name="test-the-view"></a><span data-ttu-id="53136-113">Pruebe la vista</span><span class="sxs-lookup"><span data-stu-id="53136-113">Test the view</span></span>  
  
1.  <span data-ttu-id="53136-114">Las vistas se tratan como tablas.</span><span class="sxs-lookup"><span data-stu-id="53136-114">Views are treated just like tables.</span></span> <span data-ttu-id="53136-115">Use una instrucción `SELECT` para tener acceso a la vista.</span><span class="sxs-lookup"><span data-stu-id="53136-115">Use a `SELECT` statement to access a view.</span></span>  
  
    ```  
    SELECT * FROM vw_Names;  
    GO  
  
    ```  
  
### <a name="to-create-a-stored-procedure"></a><span data-ttu-id="53136-116">Para crear un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="53136-116">To create a stored procedure</span></span>  
  
1.  <span data-ttu-id="53136-117">La siguiente instrucción crea un procedimiento almacenado denominado `pr_Names`, acepta un parámetro de entrada denominado `@VarPrice` del tipo de datos `money`.</span><span class="sxs-lookup"><span data-stu-id="53136-117">The following statement creates a stored procedure name `pr_Names`, accepts an input parameter named `@VarPrice` of data type `money`.</span></span> <span data-ttu-id="53136-118">El procedimiento almacenado imprime la instrucción `Products less than` concatenada con el parámetro de entrada que cambia del tipo de datos `money` a un tipo de datos de carácter `varchar(10)` .</span><span class="sxs-lookup"><span data-stu-id="53136-118">The stored procedure prints the statement `Products less than` concatenated with the input parameter that is changed from the `money` data type into a `varchar(10)` character data type.</span></span> <span data-ttu-id="53136-119">A continuación, el procedimiento ejecuta una instrucción `SELECT` en la vista y le pasa el parámetro de entrada como parte de la cláusula `WHERE` .</span><span class="sxs-lookup"><span data-stu-id="53136-119">Then, the procedure executes a `SELECT` statement on the view, passing the input parameter as part of the `WHERE` clause.</span></span> <span data-ttu-id="53136-120">Esto devuelve todos los productos cuyo costo es menor que el valor del parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="53136-120">This returns all products that cost less than the input parameter value.</span></span>  
  
    ```  
    CREATE PROCEDURE pr_Names @VarPrice money  
       AS  
       BEGIN  
          -- The print statement returns text to the user  
          PRINT 'Products less than ' + CAST(@VarPrice AS varchar(10));  
          -- A second statement starts here  
          SELECT ProductName, Price FROM vw_Names  
                WHERE Price < @varPrice;  
       END  
    GO  
  
    ```  
  
### <a name="test-the-stored-procedure"></a><span data-ttu-id="53136-121">Probar el procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="53136-121">Test the stored procedure</span></span>  
  
1.  <span data-ttu-id="53136-122">Para probar el procedimiento almacenado, escriba y ejecute la instrucción siguiente.</span><span class="sxs-lookup"><span data-stu-id="53136-122">To test the stored procedure, type and execute the following statement.</span></span> <span data-ttu-id="53136-123">El procedimiento debe devolver los nombres de dos productos introducidos en la tabla `Products` en la lección 1 con un precio menor que `10.00`.</span><span class="sxs-lookup"><span data-stu-id="53136-123">The procedure should return the names of the two products entered into the `Products` table in Lesson 1 with a price that is less than `10.00`.</span></span>  
  
    ```  
    EXECUTE pr_Names 10.00;  
    GO  
  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="53136-124">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="53136-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="53136-125">Conceder acceso a un objeto de base de datos</span><span class="sxs-lookup"><span data-stu-id="53136-125">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
## <a name="see-also"></a><span data-ttu-id="53136-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53136-126">See Also</span></span>  
 <span data-ttu-id="53136-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="53136-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 [<span data-ttu-id="53136-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="53136-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
