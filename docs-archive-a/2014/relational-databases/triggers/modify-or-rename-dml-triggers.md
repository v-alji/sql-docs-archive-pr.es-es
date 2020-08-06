---
title: Modificación o cambio de nombre de desencadenadores DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- renaming triggers
- modifying triggers
- DML triggers, modifying
ms.assetid: c7317eec-c0e9-479e-a4a7-83b6b6c58d59
author: rothja
ms.author: jroth
ms.openlocfilehash: 65bb13552b552d54b5547eadedc412977e423a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676911"
---
# <a name="modify-or-rename-dml-triggers"></a><span data-ttu-id="9aac4-102">Modificar o cambiar el nombre de desencadenadores DML</span><span class="sxs-lookup"><span data-stu-id="9aac4-102">Modify or Rename DML Triggers</span></span>
  <span data-ttu-id="9aac4-103">En este tema se describe cómo modificar o cambiar el nombre de un desencadenador DML en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9aac4-103">This topic describes how to modify or rename a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9aac4-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9aac4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9aac4-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9aac4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9aac4-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9aac4-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9aac4-107">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="9aac4-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="9aac4-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9aac4-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9aac4-109">**Para modificar o cambiar el nombre de un desencadenador DML, usando:**</span><span class="sxs-lookup"><span data-stu-id="9aac4-109">**To modify or rename a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="9aac4-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9aac4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9aac4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9aac4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9aac4-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9aac4-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9aac4-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9aac4-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9aac4-114">Al cambiar el nombre de un desencadenador, el desencadenador debe estar en la base de datos actual y el nuevo nombre debe seguir las reglas para los [identificadores](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="9aac4-114">When you rename a trigger, the trigger must be in the current database, and the new name must follow the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9aac4-115">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="9aac4-115">Recommendations</span></span>  
  
-   <span data-ttu-id="9aac4-116">Se recomienda no usar el procedimiento almacenado [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) para cambiar el nombre de un desencadenador.</span><span class="sxs-lookup"><span data-stu-id="9aac4-116">We recommend you do not use the [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) stored procedure to rename a trigger.</span></span> <span data-ttu-id="9aac4-117">Al cambiar cualquier parte del nombre de un objeto se pueden interrumpir scripts y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="9aac4-117">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="9aac4-118">Al cambiar el nombre de un desencadenador no se cambia el nombre del objeto correspondiente en la columna de definición de la vista de catálogo [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="9aac4-118">Renaming a trigger does not change the name of the corresponding object name in the definition column of the [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) catalog view.</span></span> <span data-ttu-id="9aac4-119">En su lugar, se recomienda quitar y volver a crear el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="9aac4-119">We recommend that you drop and re-create the trigger instead.</span></span>  
  
-   <span data-ttu-id="9aac4-120">Si cambia el nombre de un objeto al que hace referencia un desencadenador DML, deberá modificar este último para que el texto refleje el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="9aac4-120">If you change the name of an object referenced by a DML trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="9aac4-121">Por tanto, antes de cambiar el nombre de un objeto, vea primero las dependencias del mismo para determinar si algún desencadenador va a verse afectado por el cambio propuesto.</span><span class="sxs-lookup"><span data-stu-id="9aac4-121">Therefore, before you rename an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
-   <span data-ttu-id="9aac4-122">También es posible modificar un desencadenador DML para cifrar su definición.</span><span class="sxs-lookup"><span data-stu-id="9aac4-122">A DML trigger can also be modified to encrypt its definition.</span></span>  
  
-   <span data-ttu-id="9aac4-123">Para ver las dependencias de un desencadenador, puede usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o la función y las vistas de catálogo siguientes:</span><span class="sxs-lookup"><span data-stu-id="9aac4-123">To view the dependencies of a trigger, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the following function and catalog views:</span></span>  
  
    -   [<span data-ttu-id="9aac4-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9aac4-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
    -   [<span data-ttu-id="9aac4-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9aac4-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
    -   [<span data-ttu-id="9aac4-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9aac4-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9aac4-127">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9aac4-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9aac4-128">Permisos</span><span class="sxs-lookup"><span data-stu-id="9aac4-128">Permissions</span></span>  
 <span data-ttu-id="9aac4-129">Para modificar un desencadenador DML se requiere el permiso ALTER en la tabla o vista en la que se define el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="9aac4-129">To alter a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9aac4-130">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9aac4-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-dml-trigger"></a><span data-ttu-id="9aac4-131">Para modificar un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="9aac4-131">To modify a DML trigger</span></span>  
  
1.  <span data-ttu-id="9aac4-132">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="9aac4-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9aac4-133">Expanda la base de datos que desee, expanda **Tablas**y, a continuación, expanda la tabla que contiene el desencadenador que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="9aac4-133">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to modify.</span></span>  
  
3.  <span data-ttu-id="9aac4-134">Expanda **Desencadenadores**, haga clic con el botón derecho en el desencadenador que quiera cambiar y, luego, haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="9aac4-134">Expand **Triggers**, right-click the trigger to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="9aac4-135">Modifique el desencadenador y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="9aac4-135">Modify the trigger, and then click **Execute**.</span></span>  
  
#### <a name="to-rename-a-dml-trigger"></a><span data-ttu-id="9aac4-136">Para cambiar el nombre de un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="9aac4-136">To rename a DML trigger</span></span>  
  
1.  <span data-ttu-id="9aac4-137">[Elimine el desencadenador](../triggers/dml-triggers.md) cuyo nombre desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="9aac4-137">[Delete the trigger](../triggers/dml-triggers.md) that you want to rename.</span></span>  
  
2.  <span data-ttu-id="9aac4-138">[Vuelva a crear el desencadenador](../triggers/create-dml-triggers.md), especificando el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="9aac4-138">[Re-create the trigger](../triggers/create-dml-triggers.md), specifying the new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9aac4-139">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9aac4-139">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-trigger-using-alter-trigger"></a><span data-ttu-id="9aac4-140">Para modificar un desencadenador mediante ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="9aac4-140">To modify a trigger using ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="9aac4-141">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9aac4-141">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9aac4-142">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="9aac4-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9aac4-143">Copie y pegue los ejemplos siguientes en la consulta.</span><span class="sxs-lookup"><span data-stu-id="9aac4-143">Copy and paste the following examples into the query.</span></span> <span data-ttu-id="9aac4-144">Ejecute el primer ejemplo para crear un desencadenador DML que muestre al cliente un mensaje definido por el usuario cuando un usuario intente agregar o cambiar los datos de la tabla `SalesPersonQuotaHistory` .</span><span class="sxs-lookup"><span data-stu-id="9aac4-144">Execute the first example to create a DML trigger that prints a user-defined message to the client when a user tries to add or change data in the `SalesPersonQuotaHistory` table.</span></span> <span data-ttu-id="9aac4-145">Ejecute la instrucción [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) para modificar el desencadenador de manera que solo se active en las actividades `INSERT` .</span><span class="sxs-lookup"><span data-stu-id="9aac4-145">Execute the [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statement to modify the trigger to fire only on `INSERT` activities.</span></span> <span data-ttu-id="9aac4-146">Este desencadenador es útil porque recuerda al usuario que actualiza o inserta filas en esta tabla que debe notificar también al departamento `Compensation` .</span><span class="sxs-lookup"><span data-stu-id="9aac4-146">This trigger is helpful because it reminds the user that updates or inserts rows into this table to also notify the `Compensation` department.</span></span>  
  
```sql  
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
USE AdventureWorks2012;  
GO  
ALTER TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
AFTER INSERT  
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
#### <a name="to-rename-a-trigger-using-drop-trigger-and-alter-trigger"></a><span data-ttu-id="9aac4-147">Para cambiar el nombre de un desencadenador mediante DROP TRIGGER y ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="9aac4-147">To rename a trigger using DROP TRIGGER and ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="9aac4-148">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9aac4-148">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9aac4-149">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="9aac4-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9aac4-150">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="9aac4-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9aac4-151">En este ejemplo se usan las instrucciones [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) y [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) para cambiar el nombre del desencadenador `Sales.bonus_reminder` a `Sales.bonus_reminder_2`.</span><span class="sxs-lookup"><span data-stu-id="9aac4-151">This example use the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) and [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statements to rename the `Sales.bonus_reminder` trigger to `Sales.bonus_reminder_2`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder_2  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="9aac4-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9aac4-152">See Also</span></span>  
 <span data-ttu-id="9aac4-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-160">[Obtener información acerca de los desencadenadores DML](../triggers/get-information-about-dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="9aac4-160">[Get Information About DML Triggers](../triggers/get-information-about-dml-triggers.md) </span></span>  
 <span data-ttu-id="9aac4-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="9aac4-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9aac4-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="9aac4-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9aac4-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
