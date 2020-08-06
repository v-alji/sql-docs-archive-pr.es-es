---
title: Creación de desencadenadores DML para administrar varias filas de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- multiple row DML triggers
- UPDATE statement [SQL Server], DML triggers
- DELETE statement [SQL Server], DML triggers
- multirow DML triggers [SQL Server]
- INSERT statement [SQL Server], DML triggers
- DML triggers, multirow
ms.assetid: d476c124-596b-4b27-a883-812b6b50a735
author: rothja
ms.author: jroth
ms.openlocfilehash: 11ea7aa457a5cdfcafd4a8c4e0ac170ae0e3b9c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676936"
---
# <a name="create-dml-triggers-to-handle-multiple-rows-of-data"></a><span data-ttu-id="c16b8-102">Crear desencadenadores DML para administrar varias filas de datos</span><span class="sxs-lookup"><span data-stu-id="c16b8-102">Create DML Triggers to Handle Multiple Rows of Data</span></span>
  <span data-ttu-id="c16b8-103">Cuando escriba el código para un desencadenador DML, tenga en cuenta que la instrucción que hace que se active el disparador puede ser una sola instrucción que afecte a varias filas de datos, en lugar de una sola fila.</span><span class="sxs-lookup"><span data-stu-id="c16b8-103">When you write the code for a DML trigger, consider that the statement that causes the trigger to fire can be a single statement that affects multiple rows of data, instead of a single row.</span></span> <span data-ttu-id="c16b8-104">Este comportamiento es habitual para los desencadenadores UPDATE y DELETE, ya que estas instrucciones suelen afectar a varias filas.</span><span class="sxs-lookup"><span data-stu-id="c16b8-104">This behavior is common for UPDATE and DELETE triggers because these statements frequently affect multiple rows.</span></span> <span data-ttu-id="c16b8-105">No es tan corriente para los desencadenadores INSERT, porque la instrucción INSERT básica solo agrega una fila.</span><span class="sxs-lookup"><span data-stu-id="c16b8-105">The behavior is less common for INSERT triggers because the basic INSERT statement adds only a single row.</span></span> <span data-ttu-id="c16b8-106">Pero, dado que un desencadenador INSERT puede ser activado por una instrucción INSERT INTO (*nombre_tabla*) SELECT, la inserción de muchas filas puede tener como resultado la invocación de un solo desencadenador.</span><span class="sxs-lookup"><span data-stu-id="c16b8-106">However, because an INSERT trigger can be fired by an INSERT INTO (*table_name*) SELECT statement, the insertion of many rows may cause a single trigger invocation.</span></span>  
  
 <span data-ttu-id="c16b8-107">Las consideraciones acerca de los procesos que afectan a varias filas son especialmente importantes cuando la función de un desencadenador DML consiste en volver a calcular automáticamente los valores de resumen de una tabla y almacenar los resultados en otra para realizar cálculos continuos.</span><span class="sxs-lookup"><span data-stu-id="c16b8-107">Multirow considerations are especially important when the function of a DML trigger is to automatically recalculate summary values from one table and store the results in another for ongoing tallies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c16b8-108">No se recomienda utilizar cursores en desencadenadores, ya que pueden reducir el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c16b8-108">We do not recommend using cursors in triggers because they could potentially reduce performance.</span></span> <span data-ttu-id="c16b8-109">Para diseñar un desencadenador que afecte a varias filas, utilice la lógica basada en conjuntos de filas, en lugar de cursores.</span><span class="sxs-lookup"><span data-stu-id="c16b8-109">To design a trigger that affects multiple rows, use rowset-based logic instead of cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c16b8-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c16b8-110">Examples</span></span>  
 <span data-ttu-id="c16b8-111">Los desencadenadores DML descritos en los ejemplos siguientes están diseñados para almacenar el total acumulativo de una columna en otra tabla de la base de datos de muestra [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c16b8-111">The DML triggers in the following examples are designed to store a running total of a column in another table of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
### <a name="a-storing-a-running-total-for-a-single-row-insert"></a><span data-ttu-id="c16b8-112">A.</span><span class="sxs-lookup"><span data-stu-id="c16b8-112">A.</span></span> <span data-ttu-id="c16b8-113">Almacenar un total acumulativo para una inserción de una sola fila</span><span class="sxs-lookup"><span data-stu-id="c16b8-113">Storing a running total for a single-row insert</span></span>  
 <span data-ttu-id="c16b8-114">La primera versión del desencadenador DML funcionará correctamente para la inserción de una fila cuando se cargue una fila de datos en la tabla `PurchaseOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="c16b8-114">The first version of the DML trigger works well for a single-row insert when a row of data is loaded into the `PurchaseOrderDetail` table.</span></span> <span data-ttu-id="c16b8-115">El desencadenador DML se activa mediante una instrucción INSERT y la nueva fila se carga en la tabla **inserted** mientras dure la ejecución del desencadenador.</span><span class="sxs-lookup"><span data-stu-id="c16b8-115">An INSERT statement fires the DML trigger, and the new row is loaded into the **inserted** table for the duration of the trigger execution.</span></span> <span data-ttu-id="c16b8-116">La instrucción `UPDATE` lee el valor de la columna `LineTotal` para la fila y lo agrega al valor existente en la columna `SubTotal` de la tabla `PurchaseOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="c16b8-116">The `UPDATE` statement reads the `LineTotal` column value for the row and adds that value to the existing value in the `SubTotal` column in the `PurchaseOrderHeader` table.</span></span> <span data-ttu-id="c16b8-117">La cláusula `WHERE` garantiza que la fila actualizada de la tabla `PurchaseOrderDetail` coincida con el `PurchaseOrderID` de la fila de la tabla **inserted** .</span><span class="sxs-lookup"><span data-stu-id="c16b8-117">The `WHERE` clause makes sure that the updated row in the `PurchaseOrderDetail` table matches the `PurchaseOrderID` of the row in the **inserted** table.</span></span>  
  
```  
-- Trigger is valid for single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID ;  
```  
  
### <a name="b-storing-a-running-total-for-a-multirow-or-single-row-insert"></a><span data-ttu-id="c16b8-118">B.</span><span class="sxs-lookup"><span data-stu-id="c16b8-118">B.</span></span> <span data-ttu-id="c16b8-119">Almacenar un total acumulativo para una inserción de una o varias filas</span><span class="sxs-lookup"><span data-stu-id="c16b8-119">Storing a running total for a multirow or single-row insert</span></span>  
 <span data-ttu-id="c16b8-120">En caso de una inserción de varias filas, el desencadenador DML del ejemplo A no funcionaría correctamente; la expresión situada a la derecha de una asignación de una instrucción UPDATE (`SubTotal` + `LineTotal`) debe tener un solo valor, no una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="c16b8-120">For a multirow insert, the DML trigger in example A might not operate correctly; the expression to the right of an assignment expression in an UPDATE statement (`SubTotal` + `LineTotal`) can be only a single value, not a list of values.</span></span> <span data-ttu-id="c16b8-121">Por lo tanto, el efecto del desencadenador es recuperar un valor de una sola fila de la tabla **inserted** y agregarlo al valor `SubTotal` existente en la tabla `PurchaseOrderHeader` para un valor `PurchaseOrderID` específico.</span><span class="sxs-lookup"><span data-stu-id="c16b8-121">Therefore, the effect of the trigger is to retrieve a value from any single row in the **inserted** table and add that value to the existing `SubTotal` value in the `PurchaseOrderHeader` table for a specific `PurchaseOrderID` value.</span></span> <span data-ttu-id="c16b8-122">Esta operación puede no tener el efecto esperado si se da un solo valor `PurchaseOrderID` más de una vez en la tabla **inserted** .</span><span class="sxs-lookup"><span data-stu-id="c16b8-122">This operation might not have the expected effect if a single `PurchaseOrderID` value occurred more than one time in the **inserted** table.</span></span>  
  
 <span data-ttu-id="c16b8-123">Para actualizar correctamente la tabla `PurchaseOrderHeader` , el desencadenador debe permitir que pueda haber varias filas en la tabla **inserted** .</span><span class="sxs-lookup"><span data-stu-id="c16b8-123">To correctly update the `PurchaseOrderHeader` table, the trigger must allow for the chance of multiple rows in the **inserted** table.</span></span> <span data-ttu-id="c16b8-124">Puede hacerlo utilizando la función `SUM` que calcula el total `LineTotal` para un grupo de filas de la tabla **inserted** para cada `PurchaseOrderID`.</span><span class="sxs-lookup"><span data-stu-id="c16b8-124">You can do this by using the `SUM` function that calculates the total `LineTotal` for a group of rows in the **inserted** table for each `PurchaseOrderID`.</span></span> <span data-ttu-id="c16b8-125">La función `SUM` se incluye en una subconsulta correlacionada (la instrucción `SELECT` entre paréntesis).</span><span class="sxs-lookup"><span data-stu-id="c16b8-125">The `SUM` function is included in a correlated subquery (the `SELECT` statement in parentheses).</span></span> <span data-ttu-id="c16b8-126">Esta subconsulta devuelve un único valor para cada `PurchaseOrderID` de la tabla **inserted** que coincida o esté correlacionado con un `PurchaseOrderID` de la tabla `PurchaseOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="c16b8-126">This subquery returns a single value for each `PurchaseOrderID` in the **inserted** table that matches or is correlated with a `PurchaseOrderID` in the `PurchaseOrderHeader` table.</span></span>  
  
```  
-- Trigger is valid for multirow and single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail2  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted);  
```  
  
 <span data-ttu-id="c16b8-127">Este desencadenador también funciona correctamente para la inserción de una sola fila; la suma de los valores de la columna `LineTotal` corresponde a la suma de una sola fila.</span><span class="sxs-lookup"><span data-stu-id="c16b8-127">This trigger also works correctly in a single-row insert; the sum of the `LineTotal` value column is the sum of a single row.</span></span> <span data-ttu-id="c16b8-128">Sin embargo, con este desencadenador la subconsulta correlacionada y el operador `IN` que se utiliza en la cláusula `WHERE` requieren un procesamiento adicional por parte de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c16b8-128">However, with this trigger the correlated subquery and the `IN` operator that is used in the `WHERE` clause require additional processing from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c16b8-129">Esto no es necesario para una inserción de una sola fila.</span><span class="sxs-lookup"><span data-stu-id="c16b8-129">This is unnecessary for a single-row insert.</span></span>  
  
### <a name="c-storing-a-running-total-based-on-the-type-of-insert"></a><span data-ttu-id="c16b8-130">C.</span><span class="sxs-lookup"><span data-stu-id="c16b8-130">C.</span></span> <span data-ttu-id="c16b8-131">Almacenar un total acumulativo basado en el tipo de inserción</span><span class="sxs-lookup"><span data-stu-id="c16b8-131">Storing a running total based on the type of insert</span></span>  
 <span data-ttu-id="c16b8-132">Puede cambiar el desencadenador a fin de utilizar el método óptimo para el número de filas.</span><span class="sxs-lookup"><span data-stu-id="c16b8-132">You can change the trigger to use the method optimal for the number of rows.</span></span> <span data-ttu-id="c16b8-133">Por ejemplo, es posible utilizar la función `@@ROWCOUNT` en la lógica del desencadenador para que distinga entre la inserción de una fila y la de varias filas.</span><span class="sxs-lookup"><span data-stu-id="c16b8-133">For example, the `@@ROWCOUNT` function can be used in the logic of the trigger to distinguish between a single and a multirow insert.</span></span>  
  
```  
-- Trigger valid for multirow and single row inserts  
-- and optimal for single row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail3  
ON Purchasing.PurchaseOrderDetail  
FOR INSERT AS  
IF @@ROWCOUNT = 1  
BEGIN  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
END  
ELSE  
BEGIN  
      UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted)  
END;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c16b8-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c16b8-134">See Also</span></span>  
 [<span data-ttu-id="c16b8-135">Desencadenadores DML</span><span class="sxs-lookup"><span data-stu-id="c16b8-135">DML Triggers</span></span>](dml-triggers.md)  
  
  
