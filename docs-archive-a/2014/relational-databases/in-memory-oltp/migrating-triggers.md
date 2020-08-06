---
title: Migración de desencadenadores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: ad5385c5-5a50-40ca-a319-97d5606b8511
author: rothja
ms.author: jroth
ms.openlocfilehash: 25965e7cce84b0dcfcd3b6ce6176e8ad3ddabc6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750985"
---
# <a name="migrating-triggers"></a><span data-ttu-id="6f00b-102">Migrar desencadenadores</span><span class="sxs-lookup"><span data-stu-id="6f00b-102">Migrating Triggers</span></span>
  <span data-ttu-id="6f00b-103">En este tema se describen los desencadenadores DDL y DML, y las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="6f00b-103">This topic discusses DDL and DML triggers and memory-optimized tables.</span></span>  
  
 <span data-ttu-id="6f00b-104">Los desencadenadores LOGON son desencadenadores definidos para activarse en eventos LOGON.</span><span class="sxs-lookup"><span data-stu-id="6f00b-104">LOGON triggers are triggers defined to fire on LOGON events.</span></span> <span data-ttu-id="6f00b-105">Los desencadenadores LOGON no afectan a las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="6f00b-105">LOGON triggers do not affect memory-optimized tables.</span></span>  
  
## <a name="ddl-triggers"></a><span data-ttu-id="6f00b-106">Desencadenadores DDL</span><span class="sxs-lookup"><span data-stu-id="6f00b-106">DDL Triggers</span></span>  
 <span data-ttu-id="6f00b-107">Los desencadenadores DDL son desencadenadores definidos para activarse cuando se ejecuta una instrucción CREATE, ALTER, DROP, GRANT, DENY, REVOKE o UPDATE STATISTICS en la base de datos o el servidor en el que se define.</span><span class="sxs-lookup"><span data-stu-id="6f00b-107">DDL triggers are triggers defined to fire when a CREATE, ALTER, DROP, GRANT, DENY, REVOKE, or UPDATE STATISTICS statement is executed on the database or server on which it is defined.</span></span>  
  
 <span data-ttu-id="6f00b-108">No se pueden crear tablas optimizadas para memoria si la base de datos o el servidor tiene uno o varios desencadenadores DDL definidos en CREATE_TABLE o en cualquier grupo de eventos que lo incluyan.</span><span class="sxs-lookup"><span data-stu-id="6f00b-108">You cannot create memory-optimized tables if the database or server has one or more DDL trigger defined on CREATE_TABLE or any event group that includes it.</span></span> <span data-ttu-id="6f00b-109">No se puede quitar una tabla optimizada para memoria si la base de datos o el servidor tiene uno o varios desencadenadores DDL definidos en DROP_TABLE o en cualquier grupo de eventos que lo incluyan.</span><span class="sxs-lookup"><span data-stu-id="6f00b-109">You cannot drop a memory-optimized table if the database or server has one or more DDL trigger defined on DROP_TABLE or any event group that includes it.</span></span>  
  
 <span data-ttu-id="6f00b-110">No se pueden crear procedimientos almacenados compilados de forma nativa si hay uno o más desencadenadores DDL en CREATE_PROCEDURE, DROP_PROCEDURE o cualquier grupo de eventos que incluya los eventos.</span><span class="sxs-lookup"><span data-stu-id="6f00b-110">You cannot create natively compiled stored procedures if there are one or more DDL triggers on CREATE_PROCEDURE, DROP_PROCEDURE, or any event group that includes those events.</span></span>  
  
## <a name="dml-triggers"></a><span data-ttu-id="6f00b-111">Desencadenadores DML</span><span class="sxs-lookup"><span data-stu-id="6f00b-111">DML Triggers</span></span>  
 <span data-ttu-id="6f00b-112">No se puede definir desencadenadores DML en tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="6f00b-112">DML triggers cannot be defined on memory-optimized tables.</span></span> <span data-ttu-id="6f00b-113">Sin embargo, OLTP en memoria permite conseguir un efecto similar a los desencadenadores DML si se utilizan explícitamente procedimientos almacenados para insertar, actualizar o eliminar datos.</span><span class="sxs-lookup"><span data-stu-id="6f00b-113">However, In-Memory OLTP allows you to achieve an effect similar to DML triggers if you explicitly use stored procedures to insert, update, or delete data.</span></span> <span data-ttu-id="6f00b-114">Si el sistema contiene consultas ad hoc, conviértalas para que utilicen estos procedimientos almacenados en su lugar para simular el efecto de los desencadenadores DML.</span><span class="sxs-lookup"><span data-stu-id="6f00b-114">If your system contains ad-hoc queries, convert them to use these stored procedures instead to simulate the effect of DML triggers.</span></span>  
  
 <span data-ttu-id="6f00b-115">Según el evento de desencadenador (FOR/AFTER o INSTEAD OF), puede incluir el contenido del desencadenador en el procedimiento almacenado adecuado que realiza la operación INSERT, UPDATE o DELETE en esa tabla.</span><span class="sxs-lookup"><span data-stu-id="6f00b-115">Depending on the trigger event (FOR/AFTER or INSTEAD OF), you may include the content of the trigger in the appropriate stored procedure that performs INSERT, UPDATE, or DELETE on that table.</span></span> <span data-ttu-id="6f00b-116">Por ejemplo, al migrar un desencadenador AFTER INSERT, puede modificar el procedimiento almacenado que realiza la operación de inserción si incluye el contenido del desencadenador después de la instrucción INSERT adecuada.</span><span class="sxs-lookup"><span data-stu-id="6f00b-116">For example, when migrating an AFTER INSERT trigger, you could alter the stored procedure that performs the insert operation by including the content of the trigger after the appropriate INSERT statement.</span></span>  
  
 <span data-ttu-id="6f00b-117">Puede utilizar un procedimiento almacenado interpretado o un procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="6f00b-117">You can use an interpreted stored procedure or a natively compiled stored procedure.</span></span> <span data-ttu-id="6f00b-118">La mayoría de las construcciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] de un procedimiento almacenado interpretado pueden ejecutarse en una tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="6f00b-118">Most [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs in an interpreted stored procedure can execute on a memory-optimized table.</span></span> <span data-ttu-id="6f00b-119">Sin embargo, en los procedimientos almacenados compilados de forma nativa solo se admite un subconjunto de construcciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f00b-119">However, only a subset of [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs are supported in natively compiled stored procedures.</span></span> <span data-ttu-id="6f00b-120">Para obtener información acerca de la compatibilidad de [!INCLUDE[tsql](../../includes/tsql-md.md)] en tablas optimizadas para memoria, vea [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6f00b-120">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support on memory-optimized tables, see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span> <span data-ttu-id="6f00b-121">Para obtener información acerca de la compatibilidad de [!INCLUDE[tsql](../../includes/tsql-md.md)] en procedimientos almacenados compilados de forma nativa, vea [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="6f00b-121">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support in natively compiled stored procedures, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="6f00b-122">A continuación se muestra un ejemplo simple de simulación del comportamiento de un desencadenador DML en una tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="6f00b-122">The following is a simple example of simulating DML trigger behavior on a memory-optimized table.</span></span>  
  
 <span data-ttu-id="6f00b-123">La base de datos contiene los siguientes objetos, incluidos en scripts como instrucciones CREATE TABLE, CREATE TRIGGER y CREATE PROCEDURE:</span><span class="sxs-lookup"><span data-stu-id="6f00b-123">The database contains the following objects, scripted as CREATE TABLE, CREATE TRIGGER, and CREATE PROCEDURE statements:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null primary key,  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
)  
GO  
  
CREATE TRIGGER tr_order_details_insteadof_insert  
ON OrderDetails  
INSTEAD OF INSERT AS  
BEGIN  
   DECLARE @pid int, @qty_buy int, @qty_remain int  
   SELECT @pid = ProductId, @qty_buy = Quantity FROM inserted  
   SELECT @qty_remain = Quantity FROM Inventory WHERE ProductId = @pid  
   IF (@qty_remain <= @qty_buy)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      SELECT OrderId, ProductId, SalePrice, Quantity, Total FROM inserted  
      UPDATE Inventory SET Quantity = Quantity - @qty_buy WHERE ProductId = @pid  
   END  
END  
GO  
  
CREATE TRIGGER tr_order_details_after_update  
ON OrderDetails  
AFTER UPDATE AS  
BEGIN  
   INSERT INTO UpdateNotifications (OrderId, UpdateTime) SELECT OrderId, GETDATE() FROM inserted     
END  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
AS BEGIN  
   INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
   VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
AS BEGIN  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
END  
GO  
```  
  
 <span data-ttu-id="6f00b-124">Los objetos siguientes son funcionalmente equivalentes al estado previo a la migración:</span><span class="sxs-lookup"><span data-stu-id="6f00b-124">The following objects are functionally equivalent to the pre-migration state:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 1048576),  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE Inventory  
(  
   ProductId int not null PRIMARY KEY NONCLUSTERED,  
   Quantity int not null  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE UpdateNotifications  
(  
   OrderId int not null,  
   UpdateTime datetime2 not null  
   CONSTRAINT pk_updateNotifications PRIMARY KEY NONCLUSTERED (OrderId, UpdateTime)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   DECLARE @qty_remain int  
   SELECT @qty_remain = Quantity FROM dbo.Inventory WHERE ProductId = @ProductId  
   IF (@qty_remain <= @Quantity)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
      UPDATE dbo.Inventory SET Quantity = Quantity - @Quantity WHERE ProductId = @ProductId  
   END  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
   INSERT INTO dbo.UpdateNotifications (OrderId, UpdateTime) VALUES (@OrderId, GETDATE())  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f00b-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f00b-125">See Also</span></span>  
 [<span data-ttu-id="6f00b-126">Migrar a OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="6f00b-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
