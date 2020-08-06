---
title: Creación de desencadenadores anidados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- recursive DML triggers [SQL Server]
- DML triggers, nested
- triggers [SQL Server], nested
- direct recursion [SQL Server]
- triggers [SQL Server], recursive
- DML triggers, recursive
- RECURSIVE_TRIGGERS option
- indirect recursion [SQL Server]
- nested DML triggers
ms.assetid: cd522dda-b4ab-41b8-82b0-02445bdba7af
author: rothja
ms.author: jroth
ms.openlocfilehash: c0016fc3cdd93ea78ceed56efa076a01bd85be50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676933"
---
# <a name="create-nested-triggers"></a><span data-ttu-id="1dd33-102">Crear desencadenadores anidados</span><span class="sxs-lookup"><span data-stu-id="1dd33-102">Create Nested Triggers</span></span>
  <span data-ttu-id="1dd33-103">Los desencadenadores DML y DDL están anidados cuando un desencadenador realiza una acción que inicia otro desencadenador.</span><span class="sxs-lookup"><span data-stu-id="1dd33-103">Both DML and DDL triggers are nested when a trigger performs an action that initiates another trigger.</span></span> <span data-ttu-id="1dd33-104">Estas acciones pueden iniciar otros desencadenadores y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="1dd33-104">These actions can initiate other triggers, and so on.</span></span> <span data-ttu-id="1dd33-105">Los desencadenadores DML y DDL se pueden anidar hasta un máximo de 32 niveles.</span><span class="sxs-lookup"><span data-stu-id="1dd33-105">DML and DDL triggers can be nested up to 32 levels.</span></span> <span data-ttu-id="1dd33-106">Puede controlar si los desencadenadores AFTER se pueden anidar en la opción de configuración del servidor **nested triggers** .</span><span class="sxs-lookup"><span data-stu-id="1dd33-106">You can control whether AFTER triggers can be nested through the **nested triggers** server configuration option.</span></span> <span data-ttu-id="1dd33-107">Los desencadenadores INSTEAD OF (solo los desencadenadores DML pueden ser desencadenadores INSTEAD OF) se pueden anidar independientemente de esta configuración.</span><span class="sxs-lookup"><span data-stu-id="1dd33-107">INSTEAD OF triggers (only DML triggers can be INSTEAD OF triggers) can be nested regardless of this setting.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1dd33-108">Una referencia a código administrado desde un desencadenador [!INCLUDE[tsql](../../includes/tsql-md.md)] se considera como un nivel en lo que respecta al límite de anidamiento de 32 niveles.</span><span class="sxs-lookup"><span data-stu-id="1dd33-108">Any reference to managed code from a [!INCLUDE[tsql](../../includes/tsql-md.md)] trigger counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="1dd33-109">Los métodos invocados desde el código administrado no cuentan para este límite.</span><span class="sxs-lookup"><span data-stu-id="1dd33-109">Methods invoked from within managed code do not count against this limit.</span></span>  
  
 <span data-ttu-id="1dd33-110">Si se admiten desencadenadores anidados y un desencadenador de la cadena inicia un bucle infinito, se superará el nivel de anidamiento y se terminará el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="1dd33-110">If nested triggers are allowed and a trigger in the chain starts an infinite loop, the nesting level is exceeded and the trigger terminates.</span></span>  
  
 <span data-ttu-id="1dd33-111">Puede utilizar desencadenadores anidados para realizar funciones de mantenimiento, tales como almacenar una copia de seguridad de las filas que han sido afectadas por un desencadenador anterior.</span><span class="sxs-lookup"><span data-stu-id="1dd33-111">You can use nested triggers to perform useful housekeeping functions such as storing a backup copy of rows affected by a previous trigger.</span></span> <span data-ttu-id="1dd33-112">Por ejemplo, puede crear un desencadenador en `PurchaseOrderDetail` que guarde una copia de seguridad de las filas de `PurchaseOrderDetail` que haya eliminado el desencadenador `delcascadetrig` .</span><span class="sxs-lookup"><span data-stu-id="1dd33-112">For example, you can create a trigger on `PurchaseOrderDetail` that saves a backup copy of the `PurchaseOrderDetail` rows that the `delcascadetrig` trigger deleted.</span></span> <span data-ttu-id="1dd33-113">Con el desencadenador `delcascadetrig` activado, la eliminación del valor `PurchaseOrderID` 1965 de `PurchaseOrderHeader` elimina las filas correspondientes de `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="1dd33-113">With the `delcascadetrig` trigger in effect, deleting `PurchaseOrderID` 1965 from `PurchaseOrderHeader` deletes the corresponding row or rows from `PurchaseOrderDetail`.</span></span> <span data-ttu-id="1dd33-114">Para guardar los datos, puede crear un desencadenador DELETE en `PurchaseOrderDetail` que guarde los datos eliminados en una nueva tabla, `del_save`.</span><span class="sxs-lookup"><span data-stu-id="1dd33-114">To save the data, you can create a DELETE trigger on `PurchaseOrderDetail` that saves the deleted data into another separately created table, `del_save`.</span></span> <span data-ttu-id="1dd33-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1dd33-115">For example:</span></span>  
  
```  
CREATE TRIGGER Purchasing.savedel  
   ON Purchasing.PurchaseOrderDetail  
FOR DELETE  
AS  
   INSERT del_save;  
   SELECT * FROM deleted;  
```  
  
 <span data-ttu-id="1dd33-116">No se recomienda utilizar desencadenadores anidados en una secuencia que dependa del orden.</span><span class="sxs-lookup"><span data-stu-id="1dd33-116">We do not recommend using nested triggers in an order-dependent sequence.</span></span> <span data-ttu-id="1dd33-117">Utilice desencadenadores diferentes para realizar modificaciones de datos en cascada.</span><span class="sxs-lookup"><span data-stu-id="1dd33-117">Use separate triggers to cascade data modifications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1dd33-118">Dado que los desencadenadores se ejecutan dentro de una transacción, un error en cualquier nivel de un conjunto de desencadenadores anidados anula toda la transacción y provoca que se reviertan todas las modificaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="1dd33-118">Because triggers execute within a transaction, a failure at any level of a set of nested triggers cancels the entire transaction, and all data modifications are rolled back.</span></span> <span data-ttu-id="1dd33-119">Incluya instrucciones PRINT en los desencadenadores para poder determinar dónde se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="1dd33-119">Include PRINT statements in your triggers so that you can determine where the failure has occurred.</span></span>  
  
## <a name="recursive-triggers"></a><span data-ttu-id="1dd33-120">Desencadenadores recursivos</span><span class="sxs-lookup"><span data-stu-id="1dd33-120">Recursive Triggers</span></span>  
 <span data-ttu-id="1dd33-121">Un desencadenador AFTER no se llama a sí mismo de forma recursiva a menos que se active la opción RECURSIVE_TRIGGERS de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1dd33-121">An AFTER trigger does not call itself recursively unless the RECURSIVE_TRIGGERS database option is set.</span></span>  
  
 <span data-ttu-id="1dd33-122">Hay dos tipos de recursividad:</span><span class="sxs-lookup"><span data-stu-id="1dd33-122">There are two types of recursion:</span></span>  
  
-   <span data-ttu-id="1dd33-123">Recursión directa</span><span class="sxs-lookup"><span data-stu-id="1dd33-123">Direct recursion</span></span>  
  
     <span data-ttu-id="1dd33-124">Esta recursividad se produce cuando un desencadenador se activa y realiza una acción que provoca que el mismo desencadenador se vuelva a activar.</span><span class="sxs-lookup"><span data-stu-id="1dd33-124">This recursion occurs when a trigger fires and performs an action that causes the same trigger to fire again.</span></span> <span data-ttu-id="1dd33-125">Por ejemplo, una aplicación actualiza la tabla **T3**y esto provoca la activación del desencadenador **Trig3** .</span><span class="sxs-lookup"><span data-stu-id="1dd33-125">For example, an application updates table **T3**; this causes trigger **Trig3** to fire.</span></span> <span data-ttu-id="1dd33-126">**Trig3** vuelve a actualizar la tabla **T3** , lo que provoca una nueva activación del mismo desencadenador **Trig3** .</span><span class="sxs-lookup"><span data-stu-id="1dd33-126">**Trig3** updates table **T3** again; this causes trigger **Trig3** to fire again.</span></span>  
  
     <span data-ttu-id="1dd33-127">También se puede producir la repetición directa cuando se llama de nuevo al mismo desencadenador, pero después de que se llame a un desencadenador de un tipo diferente (AFTER o INSTEAD OF).</span><span class="sxs-lookup"><span data-stu-id="1dd33-127">Direct recursion can also occur when the same trigger is called again, but after a trigger of a different type (AFTER or INSTEAD OF) is called.</span></span> <span data-ttu-id="1dd33-128">Es decir, la repetición directa de un desencadenador INSTEAD OF puede producirse cuando se llama al mismo desencadenador INSTEAD OF por segunda vez, incluso cuando se llaman a uno o varios desencadenadores AFTER en medio.</span><span class="sxs-lookup"><span data-stu-id="1dd33-128">In other words, direct recursion of an INSTEAD OF trigger can occur when the same INSTEAD OF trigger is called for a second time, even if one or more AFTER triggers are called in between.</span></span> <span data-ttu-id="1dd33-129">Del mismo modo, la repetición directa de un desencadenador AFTER puede producirse cuando se llama al mismo desencadenador AFTER por segunda vez, incluso cuando se llaman a uno o varios desencadenadores INSTEAD OF en medio.</span><span class="sxs-lookup"><span data-stu-id="1dd33-129">Likewise, direct recursion of an AFTER trigger can occur when the same AFTER trigger is called for a second time, even if one or more INSTEAD OF triggers are called in between.</span></span> <span data-ttu-id="1dd33-130">Por ejemplo, una aplicación actualiza la tabla **T4**.</span><span class="sxs-lookup"><span data-stu-id="1dd33-130">For example, an application updates table **T4**.</span></span> <span data-ttu-id="1dd33-131">Esta actualización hace que se active el desencadenador INSTEAD OF **Trig4** .</span><span class="sxs-lookup"><span data-stu-id="1dd33-131">This update causes INSTEAD OF trigger **Trig4** to fire.</span></span> <span data-ttu-id="1dd33-132">**Trig4** actualiza la tabla **T5**.</span><span class="sxs-lookup"><span data-stu-id="1dd33-132">**Trig4** updates table **T5**.</span></span> <span data-ttu-id="1dd33-133">Esta actualización hace que se active el desencadenador AFTER **Trig5** .</span><span class="sxs-lookup"><span data-stu-id="1dd33-133">This update causes AFTER trigger **Trig5** to fire.</span></span> <span data-ttu-id="1dd33-134">**Trig5** actualiza la tabla **T4**y esta actualización hace que se active de nuevo el desencadenador INSTEAD OF **Trig4** .</span><span class="sxs-lookup"><span data-stu-id="1dd33-134">**Trig5** updates table **T4**, and this update causes INSTEAD OF trigger **Trig4** to fire again.</span></span> <span data-ttu-id="1dd33-135">Esta cadena de eventos se considera una repetición directa de **Trig4**.</span><span class="sxs-lookup"><span data-stu-id="1dd33-135">This chain of events is considered direct recursion for **Trig4**.</span></span>  
  
-   <span data-ttu-id="1dd33-136">Recursión indirecta</span><span class="sxs-lookup"><span data-stu-id="1dd33-136">Indirect recursion</span></span>  
  
     <span data-ttu-id="1dd33-137">Esta repetición se produce cuando se activa un desencadenador y realiza una acción que provoca la activación de otro desencadenador del mismo tipo (AFTER o INSTEAD OF).</span><span class="sxs-lookup"><span data-stu-id="1dd33-137">This recursion occurs when a trigger fires and performs an action that causes another trigger of the same type (AFTER or INSTEAD OF) to fire.</span></span> <span data-ttu-id="1dd33-138">Este segundo desencadenador realiza una acción que provoca una nueva activación del desencadenador original.</span><span class="sxs-lookup"><span data-stu-id="1dd33-138">This second trigger performs an action that causes the original trigger to fire again.</span></span> <span data-ttu-id="1dd33-139">Es decir, la repetición indirecta se puede producir cuando se llama a un desencadenador INSTEAD OF por segunda vez, pero no hasta que se llama a otro desencadenador INSTEAD OF en medio.</span><span class="sxs-lookup"><span data-stu-id="1dd33-139">In other words, indirect recursion can occur when an INSTEAD OF trigger is called for a second time, but not until another INSTEAD OF trigger is called in between.</span></span> <span data-ttu-id="1dd33-140">Del mismo modo, la repetición indirecta se puede producir cuando se llama a un desencadenador AFTER por segunda vez, pero no hasta que se llama a otro desencadenador AFTER en medio.</span><span class="sxs-lookup"><span data-stu-id="1dd33-140">Likewise, indirect recursion can occur when an AFTER trigger is called for a second time, but not until another AFTER trigger is called in between.</span></span> <span data-ttu-id="1dd33-141">Por ejemplo, una aplicación actualiza la tabla **T1**.</span><span class="sxs-lookup"><span data-stu-id="1dd33-141">For example, an application updates table **T1**.</span></span> <span data-ttu-id="1dd33-142">Esta actualización hace que se active el desencadenador AFTER **Trig1** .</span><span class="sxs-lookup"><span data-stu-id="1dd33-142">This update causes AFTER trigger **Trig1** to fire.</span></span> <span data-ttu-id="1dd33-143">**Trig1** actualiza la tabla **T2**y esta actualización hace que se active el desencadenador AFTER **Trig2** .</span><span class="sxs-lookup"><span data-stu-id="1dd33-143">**Trig1** updates table **T2**, and this update causes AFTER trigger **Trig2** to fire.</span></span> <span data-ttu-id="1dd33-144">A su vez,**Trig2** actualiza la tabla **T1** , lo que provoca que se vuelva a activar el desencadenador AFTER **Trig1** .</span><span class="sxs-lookup"><span data-stu-id="1dd33-144">**Trig2** in turn updates table **T1** that causes AFTER trigger **Trig1** to fire again.</span></span>  
  
 <span data-ttu-id="1dd33-145">La repetición directa de los desencadenadores AFTER solo se impide si la opción RECURSIVE_TRIGGERS de la base de datos se establece en OFF.</span><span class="sxs-lookup"><span data-stu-id="1dd33-145">Only direct recursion of AFTER triggers is prevented when the RECURSIVE_TRIGGERS database option is set to OFF.</span></span> <span data-ttu-id="1dd33-146">Para deshabilitar la repetición indirecta de los desencadenadores AFTER, también debe establecer la opción **nested triggers** del servidor en **0**.</span><span class="sxs-lookup"><span data-stu-id="1dd33-146">To disable indirect recursion of AFTER triggers, also set the **nested triggers** server option to **0**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1dd33-147">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1dd33-147">Examples</span></span>  
 <span data-ttu-id="1dd33-148">En el ejemplo siguiente se muestra la utilización de desencadenadores recursivos para solucionar una relación con referencia a sí misma (también denominada clausura transitiva).</span><span class="sxs-lookup"><span data-stu-id="1dd33-148">The following example shows using recursive triggers to solve a self-referencing relationship (also known as transitive closure).</span></span> <span data-ttu-id="1dd33-149">Por ejemplo, la tabla `emp_mgr` define los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1dd33-149">For example, the table `emp_mgr` defines the following:</span></span>  
  
-   <span data-ttu-id="1dd33-150">Un empleado (`emp`) de una empresa.</span><span class="sxs-lookup"><span data-stu-id="1dd33-150">An employee (`emp`) in a company.</span></span>  
  
-   <span data-ttu-id="1dd33-151">El director de cada empleado (`mgr`).</span><span class="sxs-lookup"><span data-stu-id="1dd33-151">The manager for each employee (`mgr`).</span></span>  
  
-   <span data-ttu-id="1dd33-152">El número total de empleados en la estructura de la organización que dependen de cada empleado (`NoOfReports`).</span><span class="sxs-lookup"><span data-stu-id="1dd33-152">The total number of employees in the organizational tree reporting to each employee (`NoOfReports`).</span></span>  
  
 <span data-ttu-id="1dd33-153">Un desencadenador UPDATE recursivo puede servir para mantener actualizada la columna `NoOfReports` a medida que se insertan nuevos registros de empleado.</span><span class="sxs-lookup"><span data-stu-id="1dd33-153">A recursive UPDATE trigger can be used to keep the `NoOfReports` column up-to-date as new employee records are inserted.</span></span> <span data-ttu-id="1dd33-154">El desencadenador INSERT actualiza la columna `NoOfReports` del registro de directores, que actualiza de modo recursivo la columna `NoOfReports` de otros registros superiores de la jerarquía de administración.</span><span class="sxs-lookup"><span data-stu-id="1dd33-154">The INSERT trigger updates the `NoOfReports` column of the manager record, which recursively updates the `NoOfReports` column of other records up the management hierarchy.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Turn recursive triggers ON in the database.  
ALTER DATABASE AdventureWorks2012  
   SET RECURSIVE_TRIGGERS ON;  
GO  
CREATE TABLE dbo.emp_mgr (  
   emp char(30) PRIMARY KEY,  
    mgr char(30) NULL FOREIGN KEY REFERENCES emp_mgr(emp),  
    NoOfReports int DEFAULT 0  
);  
GO  
CREATE TRIGGER dbo.emp_mgrins ON dbo.emp_mgr  
FOR INSERT  
AS  
DECLARE @e char(30), @m char(30);  
DECLARE c1 CURSOR FOR  
   SELECT emp_mgr.emp  
   FROM   emp_mgr, inserted  
   WHERE emp_mgr.emp = inserted.mgr;  
  
OPEN c1;  
FETCH NEXT FROM c1 INTO @e;  
WHILE @@fetch_status = 0  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Add 1 for newly  
   WHERE emp_mgr.emp = @e ;                           -- added employee.  
  
   FETCH NEXT FROM c1 INTO @e;  
END  
CLOSE c1;  
DEALLOCATE c1;  
GO  
-- This recursive UPDATE trigger works assuming:  
--   1. Only singleton updates on emp_mgr.  
--   2. No inserts in the middle of the org tree.  
CREATE TRIGGER dbo.emp_mgrupd ON dbo.emp_mgr FOR UPDATE  
AS  
IF UPDATE (mgr)  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Increment mgr's  
   FROM inserted                            -- (no. of reports) by  
   WHERE emp_mgr.emp = inserted.mgr;         -- 1 for the new report.  
  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports - 1 -- Decrement mgr's  
   FROM deleted                             -- (no. of reports) by 1  
   WHERE emp_mgr.emp = deleted.mgr;          -- for the new report.  
END  
GO  
-- Insert some test data rows.  
INSERT dbo.emp_mgr(emp, mgr) VALUES  
    ('Harry', NULL)  
    ,('Alice', 'Harry')  
    ,('Paul', 'Alice')  
    ,('Joe', 'Alice')  
    ,('Dave', 'Joe');  
GO  
SELECT emp,mgr,NoOfReports  
FROM dbo.emp_mgr;  
GO  
-- Change Dave's manager from Joe to Harry  
UPDATE dbo.emp_mgr SET mgr = 'Harry'  
WHERE emp = 'Dave';  
GO  
SELECT emp,mgr,NoOfReports FROM emp_mgr;  
  
GO  
```  
  
 <span data-ttu-id="1dd33-155">Resultados antes de la actualización.</span><span class="sxs-lookup"><span data-stu-id="1dd33-155">Here are the results before the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Joe                            0  
Harry                          NULL                           1  
Joe                            Alice                          1  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="1dd33-156">Resultados tras la actualización.</span><span class="sxs-lookup"><span data-stu-id="1dd33-156">Here are the results after the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Harry                          0  
Harry                          NULL                           2  
Joe                            Alice                          0  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="1dd33-157">**Para establecer la opción nested triggers**</span><span class="sxs-lookup"><span data-stu-id="1dd33-157">**To set the nested triggers option**</span></span>  
  
-   [<span data-ttu-id="1dd33-158">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1dd33-158">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
 <span data-ttu-id="1dd33-159">**Para establecer la opción de base de datos RECURSIVE_TRIGGERS**</span><span class="sxs-lookup"><span data-stu-id="1dd33-159">**To set the RECURSIVE_TRIGGERS database option**</span></span>  
  
-   [<span data-ttu-id="1dd33-160">Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1dd33-160">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="1dd33-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1dd33-161">See Also</span></span>  
 <span data-ttu-id="1dd33-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1dd33-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="1dd33-163">Establecer la opción de configuración del servidor Desencadenadores anidados</span><span class="sxs-lookup"><span data-stu-id="1dd33-163">Configure the nested triggers Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-nested-triggers-server-configuration-option.md)  
  
  
