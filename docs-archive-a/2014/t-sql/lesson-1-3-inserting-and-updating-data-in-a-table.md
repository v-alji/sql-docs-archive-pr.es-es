---
title: Inserción y actualización de datos en una tabla (Tutorial) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- inserting and updating data
ms.assetid: 514dc87a-b829-43b5-8fc8-1a400a260284
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0646019f166e1c2cc126a4cc7d2ed8f27a7bd2f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674472"
---
# <a name="inserting-and-updating-data-in-a-table-tutorial"></a><span data-ttu-id="f0540-102">Insertar y actualizar datos en una tabla (Tutorial)</span><span class="sxs-lookup"><span data-stu-id="f0540-102">Inserting and Updating Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="f0540-103"> Ahora que ha creado la tabla **Products**, ya está listo para insertar datos en la tabla mediante la instrucción INSERT.</span><span class="sxs-lookup"><span data-stu-id="f0540-103">Now that you have created the **Products** table, you are ready to insert data into the table by using the INSERT statement.</span></span> <span data-ttu-id="f0540-104">Después de insertar los datos, cambiará el contenido de una fila con una instrucción UPDATE.</span><span class="sxs-lookup"><span data-stu-id="f0540-104">After the data is inserted, you will change the content of a row by using an UPDATE statement.</span></span> <span data-ttu-id="f0540-105">Utilizará la cláusula WHERE de la instrucción UPDATE para restringir la actualización a una sola fila.</span><span class="sxs-lookup"><span data-stu-id="f0540-105">You will use the WHERE clause of the UPDATE statement to restrict the update to a single row.</span></span> <span data-ttu-id="f0540-106">Las cuatro instrucciones introducirán los siguientes datos.</span><span class="sxs-lookup"><span data-stu-id="f0540-106">The four statements will enter the following data.</span></span>  
  
|<span data-ttu-id="f0540-107">ProductID</span><span class="sxs-lookup"><span data-stu-id="f0540-107">ProductID</span></span>|<span data-ttu-id="f0540-108">ProductName</span><span class="sxs-lookup"><span data-stu-id="f0540-108">ProductName</span></span>|<span data-ttu-id="f0540-109">Price</span><span class="sxs-lookup"><span data-stu-id="f0540-109">Price</span></span>|<span data-ttu-id="f0540-110">ProductDescription</span><span class="sxs-lookup"><span data-stu-id="f0540-110">ProductDescription</span></span>|  
|---------------|-----------------|-----------|------------------------|  
|<span data-ttu-id="f0540-111">1</span><span class="sxs-lookup"><span data-stu-id="f0540-111">1</span></span>|<span data-ttu-id="f0540-112">Clamp</span><span class="sxs-lookup"><span data-stu-id="f0540-112">Clamp</span></span>|<span data-ttu-id="f0540-113">12,48</span><span class="sxs-lookup"><span data-stu-id="f0540-113">12.48</span></span>|<span data-ttu-id="f0540-114">Workbench clamp</span><span class="sxs-lookup"><span data-stu-id="f0540-114">Workbench clamp</span></span>|  
|<span data-ttu-id="f0540-115">50</span><span class="sxs-lookup"><span data-stu-id="f0540-115">50</span></span>|<span data-ttu-id="f0540-116">Screwdriver</span><span class="sxs-lookup"><span data-stu-id="f0540-116">Screwdriver</span></span>|<span data-ttu-id="f0540-117">3,17</span><span class="sxs-lookup"><span data-stu-id="f0540-117">3.17</span></span>|<span data-ttu-id="f0540-118">Flat head</span><span class="sxs-lookup"><span data-stu-id="f0540-118">Flat head</span></span>|  
|<span data-ttu-id="f0540-119">75</span><span class="sxs-lookup"><span data-stu-id="f0540-119">75</span></span>|<span data-ttu-id="f0540-120">Tire Bar</span><span class="sxs-lookup"><span data-stu-id="f0540-120">Tire Bar</span></span>||<span data-ttu-id="f0540-121">Tool for changing tires.</span><span class="sxs-lookup"><span data-stu-id="f0540-121">Tool for changing tires.</span></span>|  
|<span data-ttu-id="f0540-122">3000</span><span class="sxs-lookup"><span data-stu-id="f0540-122">3000</span></span>|<span data-ttu-id="f0540-123">3mm Bracket</span><span class="sxs-lookup"><span data-stu-id="f0540-123">3mm Bracket</span></span>|<span data-ttu-id="f0540-124">,52</span><span class="sxs-lookup"><span data-stu-id="f0540-124">.52</span></span>||  
  
 <span data-ttu-id="f0540-125">La sintaxis básica es: INSERT, nombre de tabla, lista de columnas, VALUES y, a continuación, una lista de los valores que se van a insertar.</span><span class="sxs-lookup"><span data-stu-id="f0540-125">The basic syntax is: INSERT, table name, column list, VALUES, and then a list of the values to be inserted.</span></span> <span data-ttu-id="f0540-126">Los dos guiones dobles antes de cada línea indican que la línea es un comentario y el compilador ignorará el texto.</span><span class="sxs-lookup"><span data-stu-id="f0540-126">The two hyphens in front of a line indicate that the line is a comment and the text will be ignored by the compiler.</span></span> <span data-ttu-id="f0540-127">En este caso, el comentario describe una variación permitida de la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="f0540-127">In this case, the comment describes a permissible variation of the syntax.</span></span>  
  
### <a name="to-insert-data-into-a-table"></a><span data-ttu-id="f0540-128">Para insertar datos en una tabla</span><span class="sxs-lookup"><span data-stu-id="f0540-128">To insert data into a table</span></span>  
  
1.  <span data-ttu-id="f0540-129">Ejecute la instrucción siguiente para insertar una fila en la tabla `Products` que se ha creado en la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="f0540-129">Execute the following statement to insert a row into the `Products` table that was created in the previous task.</span></span> <span data-ttu-id="f0540-130">Ésta es la sintaxis básica.</span><span class="sxs-lookup"><span data-stu-id="f0540-130">This is the basic syntax.</span></span>  
  
    ```  
    -- Standard syntax  
    INSERT dbo.Products (ProductID, ProductName, Price, ProductDescription)  
        VALUES (1, 'Clamp', 12.48, 'Workbench clamp')  
    GO  
  
    ```  
  
2.  <span data-ttu-id="f0540-131">La instrucción siguiente muestra cómo se puede cambiar el orden en que se proporcionan los parámetros modificando la situación de `ProductID` y `ProductName` en la lista de campos (entre paréntesis) y en la lista de valores.</span><span class="sxs-lookup"><span data-stu-id="f0540-131">The following statement shows how you can change the order in which the parameters are provided by switching the placement of the `ProductID` and `ProductName` in both the field list (in parentheses) and in the values list.</span></span>  
  
    ```  
    -- Changing the order of the columns  
    INSERT dbo.Products (ProductName, ProductID, Price, ProductDescription)  
        VALUES ('Screwdriver', 50, 3.17, 'Flat head')  
    GO  
  
    ```  
  
3.  <span data-ttu-id="f0540-132">La instrucción siguiente demuestra que los nombres de las columnas son opcionales, siempre y cuando los valores se enumeren en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="f0540-132">The following statement demonstrates that the names of the columns are optional, as long as the values are listed in the correct order.</span></span> <span data-ttu-id="f0540-133">Esta sintaxis es habitual, pero no se recomienda porque podría ser difícil para otros comprender su código.</span><span class="sxs-lookup"><span data-stu-id="f0540-133">This syntax is common but is not recommended because it might be harder for others to understand your code.</span></span> <span data-ttu-id="f0540-134">`NULL` se especifica para la columna `Price` porque el precio de este producto no se conoce todavía.</span><span class="sxs-lookup"><span data-stu-id="f0540-134">`NULL` is specified for the `Price` column because the price for this product is not yet known.</span></span>  
  
    ```  
    -- Skipping the column list, but keeping the values in order  
    INSERT dbo.Products  
        VALUES (75, 'Tire Bar', NULL, 'Tool for changing tires.')  
    GO  
  
    ```  
  
4.  <span data-ttu-id="f0540-135">El nombre de esquema es opcional mientras tenga acceso a una tabla del esquema predeterminado y la modifique.</span><span class="sxs-lookup"><span data-stu-id="f0540-135">The schema name is optional as long as you are accessing and changing a table in your default schema.</span></span> <span data-ttu-id="f0540-136">Puesto que la columna `ProductDescription` permite valores NULL y no se ha proporcionado ningún valor, el nombre de columna y el valor de `ProductDescription` se pueden quitar por completo de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="f0540-136">Because the `ProductDescription` column allows null values and no value is being provided, the `ProductDescription` column name and value can be dropped from the statement completely.</span></span>  
  
    ```  
    -- Dropping the optional dbo and dropping the ProductDescription column  
    INSERT Products (ProductID, ProductName, Price)  
        VALUES (3000, '3mm Bracket', .52)  
    GO  
    ```  
  
### <a name="to-update-the-products-table"></a><span data-ttu-id="f0540-137">Para actualizar la tabla de productos</span><span class="sxs-lookup"><span data-stu-id="f0540-137">To update the products table</span></span>  
  
1.  <span data-ttu-id="f0540-138">Escriba y ejecute la siguiente instrucción `UPDATE` para cambiar el `ProductName` del segundo producto de `Screwdriver`a `Flat Head Screwdriver`.</span><span class="sxs-lookup"><span data-stu-id="f0540-138">Type and execute the following `UPDATE` statement to change the `ProductName` of the second product from `Screwdriver`, to `Flat Head Screwdriver`.</span></span>  
  
    ```  
    UPDATE dbo.Products  
        SET ProductName = 'Flat Head Screwdriver'  
        WHERE ProductID = 50  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f0540-139">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="f0540-139">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f0540-140">Leer datos de una tabla &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="f0540-140">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="f0540-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0540-141">See Also</span></span>  
 <span data-ttu-id="f0540-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0540-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 [<span data-ttu-id="f0540-143">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0540-143">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
