---
title: Migración de columnas calculadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 64a9eade-22c3-4a9d-ab50-956219e08df1
author: rothja
ms.author: jroth
ms.openlocfilehash: feb50ef64f42d95913ad4e13f9a79e6e0e4ecad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750994"
---
# <a name="migrating-computed-columns"></a><span data-ttu-id="c66e0-102">Migrar columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="c66e0-102">Migrating Computed Columns</span></span>
  <span data-ttu-id="c66e0-103">Las tablas optimizadas para memoria no admiten columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="c66e0-103">Computed columns are not supported in memory-optimized tables.</span></span> <span data-ttu-id="c66e0-104">Sin embargo, puede simular una columna calculada.</span><span class="sxs-lookup"><span data-stu-id="c66e0-104">However, you can simulate a computed column.</span></span>  
  
 <span data-ttu-id="c66e0-105">Debe considerar la necesidad de conservar sus columnas calculadas al migrar las tablas basadas en disco a tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="c66e0-105">You should consider the need to persist your computed columns when you migrate your disk-based tables to memory-optimized tables.</span></span> <span data-ttu-id="c66e0-106">Las diferentes características de rendimiento de las tablas optimizadas para memoria y los procedimientos almacenados compilados de forma nativa pueden invalidar la necesidad de persistencia.</span><span class="sxs-lookup"><span data-stu-id="c66e0-106">The different performance characteristics of memory-optimized tables and natively compiled stored procedures may negate the need for persistence.</span></span>  
  
## <a name="non-persisted-computed-columns"></a><span data-ttu-id="c66e0-107">Columnas calculadas no persistentes</span><span class="sxs-lookup"><span data-stu-id="c66e0-107">Non-Persisted Computed Columns</span></span>  
 <span data-ttu-id="c66e0-108">Para simular los efectos de una columna calculada no persistente, cree una vista en la tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="c66e0-108">To simulate the effects of a non-persisted computed column, create a view on the memory-optimized table.</span></span> <span data-ttu-id="c66e0-109">En la instrucción SELECT que define la vista, agregue la definición de columna calculada en la vista.</span><span class="sxs-lookup"><span data-stu-id="c66e0-109">In the SELECT statement that defines the view, add the computed column definition into the view.</span></span> <span data-ttu-id="c66e0-110">Excepto en un procedimiento almacenado compilado de forma nativa, las consultas que utilizan los valores de la columna calculada deben leerse en la vista.</span><span class="sxs-lookup"><span data-stu-id="c66e0-110">Except in a natively compiled stored procedure, queries that use values from the computed column should read from the view.</span></span> <span data-ttu-id="c66e0-111">Dentro de los procedimientos almacenados compilados de forma nativa, debe actualizar cualquier instrucción de selección, actualización o eliminación según la definición de la columna calculada.</span><span class="sxs-lookup"><span data-stu-id="c66e0-111">Inside natively compiled stored procedures, you should update any select, update, or delete statement according to your computed column definition.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is not persisted.  
CREATE VIEW dbo.v_order_details AS  
   SELECT  
      OrderId,  
      ProductId,  
      SalePrice,  
      Quantity,  
      Quantity * SalePrice AS Total  
   FROM dbo.order_details  
```  
  
## <a name="persisted-computed-columns"></a><span data-ttu-id="c66e0-112">Columnas calculadas persistentes</span><span class="sxs-lookup"><span data-stu-id="c66e0-112">Persisted Computed Columns</span></span>  
 <span data-ttu-id="c66e0-113">Para simular los efectos de una columna calculada persistente, cree un procedimiento almacenado para insertar en la tabla y otro procedimiento almacenado para actualizar la tabla.</span><span class="sxs-lookup"><span data-stu-id="c66e0-113">To simulate the effects of a persisted computed column, create a stored procedure for inserting into the table and another stored procedure for updating the table.</span></span> <span data-ttu-id="c66e0-114">Al insertar o actualizar la tabla, invoque estos procedimientos almacenados para realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="c66e0-114">When inserting or updating the table, invoke these stored procedures to perform these tasks.</span></span> <span data-ttu-id="c66e0-115">En los procedimientos almacenados, calcule el valor para el campo calculado según las entradas, igual que se define la columna calculada en la tabla basada en disco original.</span><span class="sxs-lookup"><span data-stu-id="c66e0-115">Inside the stored procedures, calculate the value for the computed field according to the inputs, much like how the computed column is defined on the original disk-based table.</span></span> <span data-ttu-id="c66e0-116">A continuación, inserte en la tabla o actualícela según se necesite en el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="c66e0-116">Then, insert or update the table as needed inside the stored procedure.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is persisted.  
-- we need to create insert and update procedures to calculate Total.  
CREATE PROCEDURE sp_insert_order_details   
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
-- for bulk inserts, accept a table-valued parameter into the stored procedure  
-- and use an INSERT INTO SELECT statement.  
DECLARE @total money = @SalePrice * @Quantity  
INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
DECLARE @total money = @SalePrice * @Quantity  
UPDATE dbo.OrderDetails   
SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
WHERE OrderId = @OrderId  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c66e0-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c66e0-117">See Also</span></span>  
 [<span data-ttu-id="c66e0-118">Migrar a OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="c66e0-118">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
