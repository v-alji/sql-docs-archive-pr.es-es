---
title: Creación de desencadenadores DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], DML triggers
- deferred name resolution, DML triggers
- WITH ENCRYPTION clause
- IF UPDATE
- SET statement, DML triggers
- DML triggers, programming
- testing column changes
- results [SQL Server], DML triggers
ms.assetid: b2b52258-642b-462e-8e0f-18c09d2eccf4
author: rothja
ms.author: jroth
ms.openlocfilehash: f843513ba634bcb3479e373eb9ac978ab584588d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676931"
---
# <a name="create-dml-triggers"></a><span data-ttu-id="e7046-102">Crear desencadenadores DML</span><span class="sxs-lookup"><span data-stu-id="e7046-102">Create DML Triggers</span></span>
  <span data-ttu-id="e7046-103">En este tema se describe cómo crear un desencadenador DML de [!INCLUDE[tsql](../../includes/tsql-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y usando la instrucción CREATE TRIGGER de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7046-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] DML trigger by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement.</span></span>  
  
##  <a name="before-you-begin"></a><a name="Top"></a> <span data-ttu-id="e7046-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e7046-104">Before You Begin</span></span>  
  
### <a name="limitations-and-restrictions"></a><span data-ttu-id="e7046-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="e7046-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e7046-106">Para obtener una lista de las limitaciones y restricciones relacionadas con la creación de desencadenadores DML, vea [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7046-106">For a list of limitations and restrictions related to creating DML triggers, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e7046-107">Permisos</span><span class="sxs-lookup"><span data-stu-id="e7046-107">Permissions</span></span>  
 <span data-ttu-id="e7046-108">Es necesario contar con permiso ALTER sobre la tabla o vista en la que se crea el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="e7046-108">Requires ALTER permission on the table or view on which the trigger is being created.</span></span>  
  
##  <a name="how-to-create-a-dml-trigger"></a><a name="Procedures"></a> <span data-ttu-id="e7046-109">Cómo crear un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="e7046-109">How to Create a DML Trigger</span></span>  
 <span data-ttu-id="e7046-110">Puede usar cualquiera de los siguientes medios:</span><span class="sxs-lookup"><span data-stu-id="e7046-110">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="e7046-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7046-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="e7046-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7046-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e7046-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7046-113">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="e7046-114">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="e7046-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e7046-115">Expanda **Databases**, expanda la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , expanda **Tablas** y a continuación expanda la tabla **Purchasing.PurchaseOrderHeader**.</span><span class="sxs-lookup"><span data-stu-id="e7046-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, expand **Tables** and then expand the table **Purchasing.PurchaseOrderHeader**.</span></span>  
  
3.  <span data-ttu-id="e7046-116">Haga clic con el botón derecho en **Desencadenadores**y, después, seleccione **Nuevo desencadenador**.</span><span class="sxs-lookup"><span data-stu-id="e7046-116">Right-click **Triggers**, and then select **New Trigger**.</span></span>  
  
4.  <span data-ttu-id="e7046-117">En el menú **Consulta** , haga clic en **Especificar valores para parámetros de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="e7046-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span> <span data-ttu-id="e7046-118">También puede pulsar (Ctrl+Mayús+M) para abrir el cuadro de diálogo **Especificar valores para parámetros de plantilla** .</span><span class="sxs-lookup"><span data-stu-id="e7046-118">Alternatively, you can press (Ctrl-Shift-M) to open the **Specify Values for Template Parameters** dialog box.</span></span>  
  
5.  <span data-ttu-id="e7046-119">En el cuadro de diálogo **Especificar valores para parámetros de plantilla** , especifique los siguientes valores para los parámetros mostrados.</span><span class="sxs-lookup"><span data-stu-id="e7046-119">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="e7046-120">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e7046-120">Parameter</span></span>|<span data-ttu-id="e7046-121">Value</span><span class="sxs-lookup"><span data-stu-id="e7046-121">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="e7046-122">Autor</span><span class="sxs-lookup"><span data-stu-id="e7046-122">Author</span></span>|<span data-ttu-id="e7046-123">*Su nombre.*</span><span class="sxs-lookup"><span data-stu-id="e7046-123">*Your name*</span></span>|  
    |<span data-ttu-id="e7046-124">Create Date</span><span class="sxs-lookup"><span data-stu-id="e7046-124">Create Date</span></span>|<span data-ttu-id="e7046-125">*La fecha de hoy.*</span><span class="sxs-lookup"><span data-stu-id="e7046-125">*Today's date*</span></span>|  
    |<span data-ttu-id="e7046-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7046-126">Description</span></span>|<span data-ttu-id="e7046-127">Comprueba la solvencia del proveedor antes de permitir que se inserte un nuevo pedido de compra con el proveedor.</span><span class="sxs-lookup"><span data-stu-id="e7046-127">Checks the vendor credit rating before allowing a new purchase order with the vendor to be inserted.</span></span>|  
    |<span data-ttu-id="e7046-128">Schema_Name</span><span class="sxs-lookup"><span data-stu-id="e7046-128">Schema_Name</span></span>|<span data-ttu-id="e7046-129">Compra</span><span class="sxs-lookup"><span data-stu-id="e7046-129">Purchasing</span></span>|  
    |<span data-ttu-id="e7046-130">Trigger_Name</span><span class="sxs-lookup"><span data-stu-id="e7046-130">Trigger_Name</span></span>|<span data-ttu-id="e7046-131">NewPODetail2</span><span class="sxs-lookup"><span data-stu-id="e7046-131">NewPODetail2</span></span>|  
    |<span data-ttu-id="e7046-132">Table_Name</span><span class="sxs-lookup"><span data-stu-id="e7046-132">Table_Name</span></span>|<span data-ttu-id="e7046-133">PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="e7046-133">PurchaseOrderDetail</span></span>|  
    |<span data-ttu-id="e7046-134">Data_Modification_Statement</span><span class="sxs-lookup"><span data-stu-id="e7046-134">Data_Modification_Statement</span></span>|<span data-ttu-id="e7046-135">Quite UPDATE y DELETE de la lista.</span><span class="sxs-lookup"><span data-stu-id="e7046-135">Remove UPDATE and DELETE from the list.</span></span>|  
  
6.  <span data-ttu-id="e7046-136">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7046-136">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="e7046-137">En el **Editor de consultas**, reemplace el comentario `-- Insert statements for trigger here` con la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7046-137">In the **Query Editor**, replace the comment `-- Insert statements for trigger here` with the following statement:</span></span>  
  
    ```sql  
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
  
8.  <span data-ttu-id="e7046-138">Para comprobar que la sintaxis es válida, en el menú **Consulta** , haga clic en **Analizar**.</span><span class="sxs-lookup"><span data-stu-id="e7046-138">To verify the syntax is valid, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="e7046-139">Si se devuelve un mensaje de error, compare la instrucción con la información anterior y corrija lo que sea necesario y repita este paso.</span><span class="sxs-lookup"><span data-stu-id="e7046-139">If an error message is returned, compare the statement with the information above and correct as needed and repeat this step.</span></span>  
  
9. <span data-ttu-id="e7046-140">Para crear el desencadenador DML, en el menú **Consulta** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e7046-140">To create the DML trigger, from the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="e7046-141">El desencadenador DML se crea como un objeto de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e7046-141">The DML trigger is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="e7046-142">Para ver el desencadenador DML que aparece en el Explorador de objetos, haga clic con el botón derecho en **Desencadenadores** y seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="e7046-142">To see the DML trigger listed in Object Explorer, right-click **Triggers** and select **Refresh**.</span></span>  
  
 [<span data-ttu-id="e7046-143">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e7046-143">Before You Begin</span></span>](#Top)  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e7046-144">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7046-144">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="e7046-145">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="e7046-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e7046-146">En el menú **Archivo** , haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e7046-146">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e7046-147">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e7046-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e7046-148">Este ejemplo crea el mismo desencadenador DML almacenado que antes.</span><span class="sxs-lookup"><span data-stu-id="e7046-148">This example creates the same stored DML trigger as above.</span></span>  
  
    ```sql
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
