---
title: Eliminación o deshabilitación de desencadenadores DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, disabling
- removing DML triggers
- disabling DML triggers
- dropping DML triggers
- deleting DML triggers
- DML triggers, removing
ms.assetid: 0f97f953-33c5-4b26-afeb-db2a26ce38b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 39b345ade1258987df06938791ac0024e8612365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676928"
---
# <a name="delete-or-disable-dml-triggers"></a><span data-ttu-id="6c90a-102">Eliminar o deshabilitar desencadenadores DML</span><span class="sxs-lookup"><span data-stu-id="6c90a-102">Delete or Disable DML Triggers</span></span>
  <span data-ttu-id="6c90a-103">En este tema se describe cómo eliminar o deshabilitar un desencadenador DML en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c90a-103">This topic describes how to delete or disable a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6c90a-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6c90a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6c90a-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6c90a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6c90a-106">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="6c90a-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="6c90a-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6c90a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6c90a-108">**Para eliminar o deshabilitar un desencadenador DML, usando:**</span><span class="sxs-lookup"><span data-stu-id="6c90a-108">**To delete or disable a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="6c90a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c90a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6c90a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c90a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6c90a-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6c90a-111">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6c90a-112">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="6c90a-112">Recommendations</span></span>  
  
-   <span data-ttu-id="6c90a-113">Cuando el desencadenador se elimina, se quita de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="6c90a-113">When a trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="6c90a-114">Ni la tabla ni los datos en los que se basa se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="6c90a-114">The table and the data upon which it is based are not affected.</span></span> <span data-ttu-id="6c90a-115">Si se elimina una tabla, se eliminarán automáticamente todos los desencadenadores que contenga.</span><span class="sxs-lookup"><span data-stu-id="6c90a-115">Deleting a table automatically deletes any triggers on the table.</span></span>  
  
-   <span data-ttu-id="6c90a-116">Un desencadenador se habilita de forma predeterminada cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="6c90a-116">A trigger is enabled by default when it is created.</span></span>  
  
-   <span data-ttu-id="6c90a-117">Al deshabilitar un desencadenador no se quita.</span><span class="sxs-lookup"><span data-stu-id="6c90a-117">Disabling a trigger does not drop it.</span></span> <span data-ttu-id="6c90a-118">Sigue siendo un objeto de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="6c90a-118">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="6c90a-119">Sin embargo, el desencadenador no se activará cuando se ejecute la instrucción INSERT, UPDATE o DELETE en la que se programó.</span><span class="sxs-lookup"><span data-stu-id="6c90a-119">However, the trigger will not fire when any INSERT, UPDATE, or DELETE statement on which it was programmed is executed.</span></span> <span data-ttu-id="6c90a-120">Los desencadenadores deshabilitados se pueden volver a habilitar.</span><span class="sxs-lookup"><span data-stu-id="6c90a-120">Triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="6c90a-121">Si se habilita un desencadenador, éste no se vuelve a crear.</span><span class="sxs-lookup"><span data-stu-id="6c90a-121">Enabling a trigger does not re-create it.</span></span> <span data-ttu-id="6c90a-122">El desencadenador se activa de la misma forma que cuando se creó originalmente.</span><span class="sxs-lookup"><span data-stu-id="6c90a-122">The trigger fires in the same manner as when it was originally created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6c90a-123">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6c90a-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6c90a-124">Permisos</span><span class="sxs-lookup"><span data-stu-id="6c90a-124">Permissions</span></span>  
 <span data-ttu-id="6c90a-125">Para eliminar un desencadenador DML se necesita el permiso ALTER en la tabla o vista en la que está definido el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="6c90a-125">To delete a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
 <span data-ttu-id="6c90a-126">Para deshabilitar o habilitar un desencadenador DML, el usuario debe contar como mínimo con el permiso ALTER en la tabla o vista en la que se creó el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="6c90a-126">To disable or enable a DML trigger, at a minimum, a user must have ALTER permission on the table or view on which the trigger was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6c90a-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c90a-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="6c90a-128">Para eliminar un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="6c90a-128">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="6c90a-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="6c90a-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6c90a-130">Expanda la base de datos que desee, expanda **Tablas**y, a continuación, expanda la tabla que contiene el desencadenador que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="6c90a-130">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to delete.</span></span>  
  
3.  <span data-ttu-id="6c90a-131">Expanda **Desencadenadores**, haga clic con el botón derecho en el desencadenador que quiera eliminar y luego haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="6c90a-131">Expand **Triggers**, right-click the trigger to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="6c90a-132">En el cuadro de diálogo **Eliminar objeto** , compruebe que se ha especificado el desencadenador deseado y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c90a-132">In the **Delete Object** dialog box, verify the trigger to delete, and then click **OK**.</span></span>  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="6c90a-133">Para deshabilitar y habilitar un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="6c90a-133">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="6c90a-134">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="6c90a-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6c90a-135">Expanda la base de datos que desee, expanda **Tablas**y, a continuación, expanda la tabla que contiene el desencadenador que desea deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="6c90a-135">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to disable.</span></span>  
  
3.  <span data-ttu-id="6c90a-136">Expanda **Desencadenadores**, haga clic con el botón derecho en el desencadenador que quiera deshabilitar y luego haga clic en **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="6c90a-136">Expand **Triggers**, right-click the trigger to disable, and then click **Disable**.</span></span>  
  
4.  <span data-ttu-id="6c90a-137">Para habilitar el desencadenador, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="6c90a-137">To enable the trigger, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6c90a-138">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c90a-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="6c90a-139">Para eliminar un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="6c90a-139">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="6c90a-140">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c90a-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6c90a-141">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6c90a-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6c90a-142">Copie y pegue los ejemplos siguientes en la ventana de consultas.</span><span class="sxs-lookup"><span data-stu-id="6c90a-142">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="6c90a-143">Ejecute la instrucción [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) para crear el desencadenador `Sales.bonus_reminder` .</span><span class="sxs-lookup"><span data-stu-id="6c90a-143">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="6c90a-144">Para eliminar el desencadenador, ejecute la instrucción [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="6c90a-144">To delete the trigger, execute the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) statement.</span></span>  
  
```sql  
--Create the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
```sql  
--Delete the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ('Sales.bonus_reminder', 'TR') IS NOT NULL  
   DROP TRIGGER Sales.bonus_reminder;  
GO  
  
```  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="6c90a-145">Para deshabilitar y habilitar un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="6c90a-145">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="6c90a-146">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c90a-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6c90a-147">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6c90a-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6c90a-148">Copie y pegue los ejemplos siguientes en la ventana de consultas.</span><span class="sxs-lookup"><span data-stu-id="6c90a-148">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="6c90a-149">Ejecute la instrucción [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) para crear el desencadenador `Sales.bonus_reminder` .</span><span class="sxs-lookup"><span data-stu-id="6c90a-149">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="6c90a-150">Para deshabilitar y habilitar el desencadenador, ejecute las instrucciones [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) y [HABILITE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6c90a-150">To disable and enable the trigger, execute the [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) and [ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) statements, respectively.</span></span>  
  
```sql  
--Create the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
```sql  
--Disable the trigger.  
USE AdventureWorks2012;  
GO  
DISABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
  
```  
  
```sql  
--Enable the trigger.  
USE AdventureWorks2012;  
GO  
ENABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c90a-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c90a-151">See Also</span></span>  
 <span data-ttu-id="6c90a-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-158">[Obtener información acerca de los desencadenadores DML](dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="6c90a-158">[Get Information About DML Triggers](dml-triggers.md) </span></span>  
 <span data-ttu-id="6c90a-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="6c90a-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c90a-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="6c90a-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c90a-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
