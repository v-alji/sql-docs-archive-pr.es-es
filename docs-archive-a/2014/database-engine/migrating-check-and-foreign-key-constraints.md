---
title: Migración de restricciones check y Foreign Key | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: e0a1a1e4-0062-4872-93c3-cd91b7a43c23
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4bacd7a9c5c00fc6abbb763eaa02dca9493fa513
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673873"
---
# <a name="migrating-check-and-foreign-key-constraints"></a><span data-ttu-id="d6764-102">Migrar restricciones CHECK y de clave externa</span><span class="sxs-lookup"><span data-stu-id="d6764-102">Migrating Check and Foreign Key Constraints</span></span>
  <span data-ttu-id="d6764-103">Las restricciones CHECK y de clave externa no se admiten en [!INCLUDE[hek_2](../includes/hek-2-md.md)] en [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6764-103">Check and foreign key constraints are not supported in [!INCLUDE[hek_2](../includes/hek-2-md.md)] in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="d6764-104">Estas construcciones se suelen usar para aplicar la integridad lógica de los datos en el esquema y pueden ser importantes para mantener el correcto funcionamiento de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d6764-104">These constructs are usually used to enforce logical data integrity in the schema and can be important to maintaining the functional correctness of applications.</span></span>  
  
 <span data-ttu-id="d6764-105">Las comprobaciones de integridad lógica de una tabla, como las restricciones CHECK y de clave externa, requieren un procesamiento adicional en las transacciones y se deben evitar normalmente para las aplicaciones sensibles al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d6764-105">Logical integrity checks on a table such as check and foreign key constraints require additional processing on transactions and should generally be avoided for performance-sensitive applications.</span></span> <span data-ttu-id="d6764-106">Sin embargo, si estas comprobaciones son cruciales para la aplicación, existen dos soluciones alternativas.</span><span class="sxs-lookup"><span data-stu-id="d6764-106">However, if such checks are crucial to your application, there exist two workarounds.</span></span>  
  
## <a name="checking-constraints-after-an-insert-update-or-delete-operation"></a><span data-ttu-id="d6764-107">Comprobar las restricciones después de una operación de inserción, actualización o eliminación</span><span class="sxs-lookup"><span data-stu-id="d6764-107">Checking Constraints After an Insert, Update, or Delete Operation</span></span>  
 <span data-ttu-id="d6764-108">Esta solución alternativa es optimista y se basa en el supuesto de que la mayoría de cambios no infringen las restricciones.</span><span class="sxs-lookup"><span data-stu-id="d6764-108">This workaround is optimistic, based on the assumption that the majority of changes do not violate the constraints.</span></span> <span data-ttu-id="d6764-109">En esta solución alternativa, se modifican los datos antes de que se evalúan las restricciones.</span><span class="sxs-lookup"><span data-stu-id="d6764-109">In this workaround, data is modified first before the constraints are evaluated.</span></span> <span data-ttu-id="d6764-110">Si se infringe una restricción, se detectaría pero el cambio no se revertirá.</span><span class="sxs-lookup"><span data-stu-id="d6764-110">If a constraint is violated, it would be detected, but the change will not be rolled back.</span></span>  
  
 <span data-ttu-id="d6764-111">Esta solución alternativa presenta la ventaja de que tiene un impacto mínimo sobre el rendimiento porque la modificación de los datos no está bloqueada por las comprobaciones de las restricciones.</span><span class="sxs-lookup"><span data-stu-id="d6764-111">This workaround has the advantage of having minimal impact on performance because data modification is not blocked by constraint checks.</span></span> <span data-ttu-id="d6764-112">Sin embargo, si se realiza un cambio que infringe una o más restricciones, el proceso para revertir ese cambio puede tardar mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="d6764-112">However, if a change that violates one or more constraints does occur, the process to roll back that change could take a long time.</span></span>  
  
## <a name="enforcing-constraints-before-an-insert-update-or-delete-operation"></a><span data-ttu-id="d6764-113">Aplicar las restricciones antes de una operación de inserción, actualización o eliminación</span><span class="sxs-lookup"><span data-stu-id="d6764-113">Enforcing Constraints Before an Insert, Update, or Delete Operation</span></span>  
 <span data-ttu-id="d6764-114">Esta solución alternativa emula el comportamiento de las restricciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6764-114">This workaround emulates the behavior of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] constraints.</span></span> <span data-ttu-id="d6764-115">Las restricciones se comprueban antes de modificar los datos y finalizarán la transacción si se produce un error en una comprobación.</span><span class="sxs-lookup"><span data-stu-id="d6764-115">The constraints are checked before data modification occurs and will terminate the transaction if a check fails.</span></span> <span data-ttu-id="d6764-116">Este método incurre en una penalización de rendimiento en las modificaciones de datos, pero garantiza que los datos de una tabla satisfacen siempre las restricciones.</span><span class="sxs-lookup"><span data-stu-id="d6764-116">This method incurs a performance penalty on data modifications, but ensures that data inside a table always satisfies the constraints.</span></span>  
  
 <span data-ttu-id="d6764-117">Use esta solución alternativa cuando la integridad lógica de los datos sea fundamental para la exactitud y sea probable que haya modificaciones que infrinjan una restricción.</span><span class="sxs-lookup"><span data-stu-id="d6764-117">Use this workaround when logical data integrity is crucial to correctness and modifications that violate a constraint are likely.</span></span> <span data-ttu-id="d6764-118">Sin embargo, para garantizar la integridad, todas las modificaciones de datos deben realizarse mediante procedimientos almacenados que incluyan estos cumplimientos.</span><span class="sxs-lookup"><span data-stu-id="d6764-118">However, to guarantee integrity, all data modifications must occur through stored procedures that include these enforcements.</span></span> <span data-ttu-id="d6764-119">Las modificaciones realizadas con consultas ad hoc y otros procedimientos almacenados no aplicarán estas restricciones y, por tanto, pueden infringirlas sin mostrar ninguna advertencia.</span><span class="sxs-lookup"><span data-stu-id="d6764-119">Modifications through ad-hoc queries and other stored procedures will not enforce these constraints and therefore may violate them with no warning.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="d6764-120">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6764-120">Sample Code</span></span>  
 <span data-ttu-id="d6764-121">Los ejemplos siguientes se basan en la base de datos AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="d6764-121">The following samples are based on the AdventureWorks2012 database.</span></span> <span data-ttu-id="d6764-122">En concreto, estos ejemplos se basan en la tabla [Sales].[SalesOrderDetail] y sus restricciones CHECK y de clave externa asociadas además del índice único.</span><span class="sxs-lookup"><span data-stu-id="d6764-122">Specifically, these samples are based on the [Sales].[SalesOrderDetail] table and its associated check and foreign key constraints in addition to the unique index.</span></span>  
  
 <span data-ttu-id="d6764-123">Los procedimientos almacenados especificados aquí son para operaciones de inserción únicamente.</span><span class="sxs-lookup"><span data-stu-id="d6764-123">The stored procedures specified here are for inset operations only.</span></span> <span data-ttu-id="d6764-124">Los procedimientos almacenados para las operaciones de actualización y eliminación deben tener estructuras similares.</span><span class="sxs-lookup"><span data-stu-id="d6764-124">Stored procedures for update and delete operations should have similar structures.</span></span>  
  
## <a name="table-definition-for-the-workarounds"></a><span data-ttu-id="d6764-125">Definición de tabla para las soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="d6764-125">Table Definition for the Workarounds</span></span>  
 <span data-ttu-id="d6764-126">Antes de convertirse a una tabla optimizada para memoria, la definición de [Sales].[SalesOrderDetail] es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6764-126">Before converting to a memory-optimized table, the definition for [Sales].[SalesOrderDetail] is as follows:</span></span>  
  
```sql  
USE [AdventureWorks2012]  
GO  
  
CREATE TABLE [Sales].[SalesOrderDetail]([SalesOrderID] [int] NOT NULL,  
   [SalesOrderDetailID] [int] IDENTITY(1,1) NOT NULL,  
   [CarrierTrackingNumber] [nvarchar](25) NULL,  
   [OrderQty] [smallint] NOT NULL,  
   [ProductID] [int] NOT NULL,  
   [SpecialOfferID] [int] NOT NULL,  
   [UnitPrice] [money] NOT NULL,  
   [UnitPriceDiscount] [money] NOT NULL CONSTRAINT [DF_SalesOrderDetail_UnitPriceDiscount]  DEFAULT ((0.0)),  
   [LineTotal]  AS (isnull(([UnitPrice]*((1.0)-[UnitPriceDiscount]))*[OrderQty],(0.0))),  
   [rowguid] [uniqueidentifier] ROWGUIDCOL  NOT NULL CONSTRAINT [DF_SalesOrderDetail_rowguid]  DEFAULT (newid()),  
   [ModifiedDate] [datetime] NOT NULL CONSTRAINT [DF_SalesOrderDetail_ModifiedDate]  DEFAULT (getdate()),  
 CONSTRAINT [PK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID] PRIMARY KEY CLUSTERED   
(  
   [SalesOrderID] ASC,  
   [SalesOrderDetailID] ASC  
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID] FOREIGN KEY([SalesOrderID])  
REFERENCES [Sales].[SalesOrderHeader] ([SalesOrderID])  
ON DELETE CASCADE  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID] FOREIGN KEY([SpecialOfferID], [ProductID])  
REFERENCES [Sales].[SpecialOfferProduct] ([SpecialOfferID], [ProductID])  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_OrderQty] CHECK  (([OrderQty]>(0)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_OrderQty]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_UnitPrice] CHECK  (([UnitPrice]>=(0.00)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_UnitPrice]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_UnitPriceDiscount] CHECK  (([UnitPriceDiscount]>=(0.00)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_UnitPriceDiscount]  
GO  
```  
  
 <span data-ttu-id="d6764-127">Después de convertirse a una tabla optimizada para memoria, la definición de [Sales].[SalesOrderDetail] es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6764-127">After converting to a memory-optimized table, the definition for [Sales].[SalesOrderDetail] is as follows:</span></span>  
  
 <span data-ttu-id="d6764-128">Observe que rowguid ya no es un ROWGUIDCOL porque no se admite en [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6764-128">Note that rowguid is no longer a ROWGUIDCOL as it is not supported in [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="d6764-129">Se ha quitado la columna.</span><span class="sxs-lookup"><span data-stu-id="d6764-129">The column has been removed.</span></span> <span data-ttu-id="d6764-130">Además, LineTotal es una columna calculada y queda fuera del ámbito de este artículo, por lo que también se ha quitado.</span><span class="sxs-lookup"><span data-stu-id="d6764-130">In addition, LineTotal is a computed column and out of scope for this article, so it also has been removed.</span></span>  
  
```sql  
USE [AdventureWorks2012]  
GO  
  
CREATE TABLE [Sales].[SalesOrderDetail]([SalesOrderID] [int] NOT NULL,  
   [SalesOrderDetailID] [int] IDENTITY(1,1) NOT NULL,  
   [CarrierTrackingNumber] [nvarchar](25) NULL,  
   [OrderQty] [smallint] NOT NULL,  
   [ProductID] [int] NOT NULL,  
   [SpecialOfferID] [int] NOT NULL,  
   [UnitPrice] [money] NOT NULL,  
   [UnitPriceDiscount] [money] NOT NULL CONSTRAINT [DF_SalesOrderDetail_UnitPriceDiscount]  DEFAULT ((0.0)),  
   [ModifiedDate] [datetime] NOT NULL CONSTRAINT [DF_SalesOrderDetail_ModifiedDate]  DEFAULT (getdate()),  
   CONSTRAINT [PK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID] PRIMARY KEY NONCLUSTERED   
   (  
      [SalesOrderID] ASC,  
      [SalesOrderDetailID] ASC  
   ),  
   INDEX [AK_SalesOrderDetail_rowguid] NONCLUSTERED HASH ([rowguid]) WITH (BUCKET_COUNT = 1048576),  
   INDEX [IX_SalesOrderDetail_ProductId] NONCLUSTERED ([ProductId] ASC)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
  
GO  
```  
  
## <a name="checking-constraints-after-an-insert-update-or-delete-operation"></a><span data-ttu-id="d6764-131">Comprobar las restricciones después de una operación de inserción, actualización o eliminación</span><span class="sxs-lookup"><span data-stu-id="d6764-131">Checking Constraints After an Insert, Update, or Delete Operation</span></span>  
  
```sql  
USE AdventureWorks2012  
GO  
  
CREATE PROCEDURE Sales.usp_insert_SalesOrderDetails   
   @SalesOrderId int, @CarrierTrackingNumber nvarchar(25) = null, @OrderQty smallint, @ProductId int, @SpecialOfferID int,   
   @UnitPrice money, @UnitPriceDiscount money = 0.00, @ModifiedDate datetime = null  
AS  
BEGIN  
BEGIN TRANSACTION   
   -- handle defaults for the insert.  
   -- This is to make the insert logic less complex. Default constraints on the table should be in sync with this logic.  
   -- Conversely, you can write an INSERT statement for each case where one or more values for the three columns with default constraints are not specified.  
   IF @ModifiedDate = null SET @ModifiedDate = GETDATE()  
  
   -- Insert the row.  
   INSERT INTO Sales.SalesOrderDetail   
      (SalesOrderID, CarrierTrackingNumber, OrderQty, ProductID, SpecialOfferID, UnitPrice, UnitPriceDiscount, ModifiedDate)  
   VALUES   
      (@SalesOrderId, @CarrierTrackingNumber, @OrderQty, @ProductID, @SpecialOfferID, @UnitPrice, @UnitPriceDiscount, , @ModifiedDate)   
  
   -- Now handle constraints  
   DECLARE @violations TABLE   
   (   
      ConstraintName sysname,  
      ViolatedValue1 sql_variant,  
      ViolatedValue2 sql_variant  
   )  
  
   -- FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID  
   IF NOT EXISTS (SELECT soh.SalesOrderId AS [Exists] FROM Sales.SalesOrderHeader soh WHERE soh.SalesOrderID = @SalesOrderId)   
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID', @SalesOrderId, NULL)  
   -- FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID  
   IF NOT EXISTS (SELECT sop.SpecialOfferID, sop.ProductID FROM [Sales].[SpecialOfferProduct] sop WHERE sop.SpecialOfferID = @SpecialOfferID AND sop.ProductID = @ProductId)  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID', @SpecialOfferId, @ProductId)  
   -- CK_SalesOrderDetail_OrderQty  
   IF NOT @OrderQty > 0   
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_OrderQty', @OrderQty, NULL)  
   -- CK_SalesOrderDetail_UnitPrice  
   IF NOT @UnitPrice >= 0.00  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_UnitPrice', @UnitPrice, NULL)  
   -- CK_SalesOrderDetail_UnitPriceDiscout  
   IF NOT @UnitPriceDiscount >= 0.00  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_UnitPriceDiscount', @UnitPriceDiscount, NULL)  
  
   -- Return a rowset containing violated constraints. On an item that doesn't violate anything, should return an empty rowset.  
   SELECT ConstraintName, ViolatedValue1, ViolatedValue2 FROM @violations  
   COMMIT TRANSACTION  
END  
```  
  
## <a name="enforcing-constraints-before-an-insert-update-or-delete-operation"></a><span data-ttu-id="d6764-132">Aplicar las restricciones antes de una operación de inserción, actualización o eliminación</span><span class="sxs-lookup"><span data-stu-id="d6764-132">Enforcing Constraints Before an Insert, Update or Delete Operation</span></span>  
  
```sql  
USE AdventureWorks2012  
GO  
  
CREATE PROCEDURE Sales.usp_insert_SalesOrderDetails   
   @SalesOrderId int, @CarrierTrackingNumber nvarchar(25) = null, @OrderQty smallint, @ProductId int, @SpecialOfferID int,   
   @UnitPrice money, @UnitPriceDiscount money = 0.00, @ModifiedDate datetime = null  
AS  
BEGIN  
BEGIN TRY  
   BEGIN TRANSACTION  
   -- Verify the constraints first.  
   -- FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID  
   IF NOT EXISTS (SELECT soh.SalesOrderId FROM Sales.SalesOrderHeader soh WHERE soh.SalesOrderID = @SalesOrderId)   
      THROW 50547, N'This SalesOrderId does not exist in SalesOrderHeader', 1  
   -- FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID  
   IF NOT EXISTS (SELECT sop.SpecialOfferID, sop.ProductID FROM [Sales].[SpecialOfferProduct] sop WHERE sop.SpecialOfferID = @SpecialOfferID AND sop.ProductID = @ProductId)  
      THROW 50547, N'This combination of SpecialOfferID and ProductID does not exist in SpecialOfferProduct', 1   
   -- CK_SalesOrderDetail_OrderQty  
   IF NOT @OrderQty > 0   
      THROW 50547, N'OrderQty must be greater than zero.', 1  
   -- CK_SalesOrderDetail_UnitPrice  
   IF NOT @UnitPrice >= 0.00  
      THROW 50547, N'UnitPrice cannot be negative.', 1  
   -- CK_SalesOrderDetail_UnitPriceDiscout  
   IF NOT @UnitPriceDiscount >= 0.00  
      THROW 50547, N'UnitPriceDiscount cannot be negative', 1  
  
   -- All verifications have now passed. Proceed to insert.  
  
   -- handle defaults for the insert.  
   -- This is to make the insert logic less complex. Default constraints on the table should be in sync with this logic.  
   -- Conversely, you can write an INSERT statement for each case where one or more values for the three columns with default constraints are not specified.  
  
   IF @ModifiedDate = null SET @ModifiedDate = GETDATE()  
  
   -- Calculate computed columnn and store it.  
   DECLARE @LineTotal numeric(38, 6)  
   SET @LineTotal = (isnull((@UnitPrice * ((1.0) - @UnitPriceDiscount)) * @OrderQty, (0.0)))  
  
   -- Insert the row.  
   INSERT INTO Sales.SalesOrderDetail   
      (SalesOrderID, CarrierTrackingNumber, OrderQty, ProductID, SpecialOfferID, UnitPrice, UnitPriceDiscount, ModifiedDate)  
   VALUES   
      (@SalesOrderId, @CarrierTrackingNumber, @OrderQty, @ProductID, @SpecialOfferID, @UnitPrice, @UnitPriceDiscount, @ModifiedDate)  
   COMMIT TRANSACTION  
END TRY  
BEGIN CATCH  
   IF @@TRANCOUNT > 0  
      ROLLBACK TRANSACTION  
      THROW;  
END CATCH  
END  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6764-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6764-133">See Also</span></span>  
 [<span data-ttu-id="d6764-134">Migrar a OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="d6764-134">Migrating to In-Memory OLTP</span></span>](../relational-databases/in-memory-oltp/migrating-to-in-memory-oltp.md)  
  
  
