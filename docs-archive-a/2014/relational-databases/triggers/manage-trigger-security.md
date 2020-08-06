---
title: Administración de la seguridad de los desencadenadores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], security
ms.assetid: e94720a8-a3a2-4364-b0a3-bbe86e3ce4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: fdc176dcad50c3bf28f058c3724a01267975bfc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676912"
---
# <a name="manage-trigger-security"></a><span data-ttu-id="adf3b-102">Administrar la seguridad de los desencadenadores</span><span class="sxs-lookup"><span data-stu-id="adf3b-102">Manage Trigger Security</span></span>
  <span data-ttu-id="adf3b-103">De forma predeterminada, los desencadenadores DML y DDL se ejecutan en el contexto del usuario que llama al desencadenador.</span><span class="sxs-lookup"><span data-stu-id="adf3b-103">By default, both DML and DDL triggers execute under the context of the user that calls the trigger.</span></span> <span data-ttu-id="adf3b-104">El autor de la llamada a un desencadenador es el usuario que ejecuta la instrucción que hace que el desencadenador se ejecute.</span><span class="sxs-lookup"><span data-stu-id="adf3b-104">The caller of a trigger is the user that executes the statement that causes the trigger to run.</span></span> <span data-ttu-id="adf3b-105">Por ejemplo, si el usuario **Mary** ejecuta una instrucción DELETE que hace que el desencadenador DML **DML_trigMary** se ejecute, el código incluido en **DML_trigMary** se ejecutará en el contexto de los privilegios de usuario de **Mary**.</span><span class="sxs-lookup"><span data-stu-id="adf3b-105">For example, if user **Mary** executes a DELETE statement that causes DML trigger **DML_trigMary** to run, the code inside **DML_trigMary** executes in the context of the user privileges for **Mary**.</span></span> <span data-ttu-id="adf3b-106">Este comportamiento predeterminado podría ser utilizado por usuarios que deseen introducir código dañino en la base de datos o la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="adf3b-106">This default behavior can be exploited by users who want to introduce malicious code in the database or server instance.</span></span> <span data-ttu-id="adf3b-107">Por ejemplo, el usuario `JohnDoe`crea el siguiente desencadenador DDL:</span><span class="sxs-lookup"><span data-stu-id="adf3b-107">For example, the following DDL trigger is created by user `JohnDoe`:</span></span>  
  
 `CREATE TRIGGER DDL_trigJohnDoe`  
  
 `ON DATABASE`  
  
 `FOR ALTER_TABLE`  
  
 `AS`  
  
 `GRANT CONTROL SERVER TO JohnDoe ;`  
  
 `GO`  
  
 <span data-ttu-id="adf3b-108">Este desencadenador significa que cuando un usuario con permiso para ejecutar una instrucción `GRANT CONTROL SERVER` , por ejemplo, un miembro del rol fijo de servidor **sysadmin** , ejecute una instrucción `ALTER TABLE` , `JohnDoe` obtendrá el permiso `CONTROL SERVER` .</span><span class="sxs-lookup"><span data-stu-id="adf3b-108">What this trigger means is that as soon as a user that has permission to execute a `GRANT CONTROL SERVER` statement, such as a member of the **sysadmin** fixed server role, executes an `ALTER TABLE` statement, `JohnDoe` is granted `CONTROL SERVER` permission.</span></span> <span data-ttu-id="adf3b-109">En otras palabras, aunque `JohnDoe` no puede otorgarse el permiso `CONTROL SERVER` a sí mismo, ha habilitado el código de desencadenador que le otorga permiso para ejecutar instrucciones con privilegios aumentados.</span><span class="sxs-lookup"><span data-stu-id="adf3b-109">In other words, although `JohnDoe` cannot grant `CONTROL SERVER` permission to himself, he enabled the trigger code that grants him this permission to execute under escalated privileges.</span></span> <span data-ttu-id="adf3b-110">Tanto el desencadenador DML como el DLL están sujetos a este tipo de amenaza de seguridad.</span><span class="sxs-lookup"><span data-stu-id="adf3b-110">Both DML and DDL triggers are open to this kind of security threat.</span></span>  
  
## <a name="trigger-security-best-practices"></a><span data-ttu-id="adf3b-111">Prácticas recomendadas de seguridad de los desencadenadores</span><span class="sxs-lookup"><span data-stu-id="adf3b-111">Trigger Security Best Practices</span></span>  
 <span data-ttu-id="adf3b-112">Para evitar que se ejecute código de desencadenador con privilegios aumentados, puede adoptar las siguientes medidas:</span><span class="sxs-lookup"><span data-stu-id="adf3b-112">You can take the following measures to prevent trigger code from executing under escalated privileges:</span></span>  
  
-   <span data-ttu-id="adf3b-113">Tenga en cuenta los desencadenadores DML y DDL que se encuentran en la base de datos y en la instancia del servidor al consultar la vistas de catálogo [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) y [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="adf3b-113">Be aware of the DML and DDL triggers that exist in the database and on the server instance by querying the [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) and [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) catalog views.</span></span> <span data-ttu-id="adf3b-114">La consulta siguiente devuelve todos los desencadenadores DML y DLL de base de datos para la base de datos actual, además de todos los desencadenadores DDL de servidor para la instancia de servidor:</span><span class="sxs-lookup"><span data-stu-id="adf3b-114">The following query returns all DML and database-level DDL triggers in the current database, and all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    SELECT type, name, parent_class_desc FROM sys.triggers  
    UNION  
    SELECT type, name, parent_class_desc FROM sys.server_triggers ;  
    ```  
  
-   <span data-ttu-id="adf3b-115">Utilice [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) para deshabilitar desencadenadores que podrían dañar la integridad de la base de datos o el servidor si se ejecutan con privilegios aumentados.</span><span class="sxs-lookup"><span data-stu-id="adf3b-115">Use [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) to disable triggers that can harm the integrity of the database or server if the triggers execute under escalated privileges.</span></span> <span data-ttu-id="adf3b-116">La siguiente instrucción deshabilita todos los desencadenadores DDL de base de datos para la base de datos actual:</span><span class="sxs-lookup"><span data-stu-id="adf3b-116">The following statement disables all database-level DDL triggers in the current database:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON DATABASE  
    ```  
  
     <span data-ttu-id="adf3b-117">Esta instrucción deshabilita todos los desencadenadores DDL en la instancia de servidor:</span><span class="sxs-lookup"><span data-stu-id="adf3b-117">This statement disables all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON ALL SERVER  
    ```  
  
     <span data-ttu-id="adf3b-118">Esta instrucción deshabilita todos los desencadenadores DML en la base de datos actual:</span><span class="sxs-lookup"><span data-stu-id="adf3b-118">This statement disables all DML triggers in the current database:</span></span>  
  
    ```  
    DECLARE @schema_name sysname, @trigger_name sysname, @object_name sysname ;  
    DECLARE @sql nvarchar(max) ;  
    DECLARE trig_cur CURSOR FORWARD_ONLY READ_ONLY FOR  
        SELECT SCHEMA_NAME(schema_id) AS schema_name,  
            name AS trigger_name,  
            OBJECT_NAME(parent_object_id) as object_name  
        FROM sys.objects WHERE type in ('TR', 'TA') ;  
  
    OPEN trig_cur ;  
    FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        SELECT @sql = 'DISABLE TRIGGER ' + QUOTENAME(@schema_name) + '.'  
            + QUOTENAME(@trigger_name) +  
            ' ON ' + QUOTENAME(@schema_name) + '.'   
            + QUOTENAME(@object_name) + ' ; ' ;  
        EXEC (@sql) ;  
        FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
    END  
    GO  
  
    -- Verify triggers are disabled. Should return an empty result set.  
    SELECT * FROM sys.triggers WHERE is_disabled = 0 ;  
    GO  
  
    CLOSE trig_cur ;  
    DEALLOCATE trig_cur;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="adf3b-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="adf3b-119">See Also</span></span>  
 <span data-ttu-id="adf3b-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="adf3b-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="adf3b-121">[Desencadenadores DML](../triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="adf3b-121">[DML Triggers](../triggers/dml-triggers.md) </span></span>  
 [<span data-ttu-id="adf3b-122">Desencadenadores DDL</span><span class="sxs-lookup"><span data-stu-id="adf3b-122">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
