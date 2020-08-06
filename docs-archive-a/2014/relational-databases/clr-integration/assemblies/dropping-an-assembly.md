---
title: Quitar un ensamblado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- removing assemblies
- DROP ASSEMBLY statement
- assemblies [CLR integration], removing
- dropping assemblies
ms.assetid: 03481034-dc91-4488-ab24-ba44243e2690
author: rothja
ms.author: jroth
ms.openlocfilehash: 45d02cbb57459a4c1c11330446021c32dc897353
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747623"
---
# <a name="dropping-an-assembly"></a><span data-ttu-id="bf775-102">Quitar un ensamblado</span><span class="sxs-lookup"><span data-stu-id="bf775-102">Dropping an Assembly</span></span>
  <span data-ttu-id="bf775-103">Es posible eliminar o quitar ensamblados registrados en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la instrucción CREATE ASSEMBLY cuando la funcionalidad que proporcionan ya no se necesita.</span><span class="sxs-lookup"><span data-stu-id="bf775-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement can be deleted, or dropped, when the functionality they provide is no longer needed.</span></span> <span data-ttu-id="bf775-104">Cuando se quita un ensamblado se quita el propio ensamblado y todos sus archivos asociados, como los archivos de depuración, de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bf775-104">Dropping an assembly removes the assembly and all of its associated files, such as debug files, from the database.</span></span> <span data-ttu-id="bf775-105">Para quitar un ensamblado, use la instrucción DROP ASSEMBLY con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf775-105">To drop an assembly, use the DROP ASSEMBLY statement with the following syntax:</span></span>  
  
```  
DROP ASSEMBLY MyDotNETAssembly  
```  
  
 <span data-ttu-id="bf775-106">DROP ASSEMBLY no interfiere con ningún código que haga referencia al ensamblado que se está ejecutando en estos momentos, pero después de que se ejecute DROP ASSEMBLY, cualquier intento de invocar al código del ensamblado generará errores.</span><span class="sxs-lookup"><span data-stu-id="bf775-106">DROP ASSEMBLY does not interfere with any code referencing the assembly that is currently running, but after DROP ASSEMBLY executes, any attempts to invoke the assembly code fail.</span></span>  
  
 <span data-ttu-id="bf775-107">DROP ASSEMBLY devuelve un error si hay otro ensamblado en la base de datos que hace referencia al ensamblado o si se utiliza en procedimientos, desencadenadores, tipos definidos por el usuario (UDT), agregados definidos por el usuario (UDA) o funciones de CLR (Common Language Runtime) en la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="bf775-107">DROP ASSEMBLY returns an error if the assembly is referenced by another assembly that exists in the database, or if it is used by common language runtime (CLR) functions, procedures, triggers, user-defined types (UDTs), or user-defined aggregates (UDAs) in the current database.</span></span> <span data-ttu-id="bf775-108">Utilice en primer lugar las instrucciones DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER y DROP TYPE para eliminar cualquier objeto de base de datos administrado incluido en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bf775-108">First use the DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER, and DROP TYPE statements to delete any managed database objects contained in the assembly.</span></span>  
  
## <a name="removing-a-udt-from-the-database"></a><span data-ttu-id="bf775-109">Quitar un UDT de la base de datos</span><span class="sxs-lookup"><span data-stu-id="bf775-109">Removing a UDT from the Database</span></span>  
 <span data-ttu-id="bf775-110">La instrucción DROP TYPE quita un UDT de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="bf775-110">The DROP TYPE statement removes a UDT from the current database.</span></span> <span data-ttu-id="bf775-111">Una vez quitado un UDT, puede utilizar la instrucción DROP ASSEMBLY para quitar el ensamblado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bf775-111">Once a UDT is dropped, you can use the DROP ASSEMBLY statement to drop the assembly from the database.</span></span>  
  
 <span data-ttu-id="bf775-112">Se producen errores en la instrucción DROP TYPE si hay objetos que dependen del UDT, como en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="bf775-112">The DROP TYPE statement fails if objects depend on the UDT, as in the following situations:</span></span>  
  
-   <span data-ttu-id="bf775-113">Tablas de la base de datos que contienen columnas definidas mediante el UDT.</span><span class="sxs-lookup"><span data-stu-id="bf775-113">Tables in the database that contain columns defined using the UDT.</span></span>  
  
-   <span data-ttu-id="bf775-114">Funciones, procedimientos almacenados o desencadenadores que usan variables o parámetros del UDT creados en la base de datos con la cláusula WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="bf775-114">Functions, stored procedures, or triggers that use variables or parameters of the UDT, created in the database with the WITH SCHEMABINDING clause.</span></span>  
  
### <a name="finding-udt-dependencies"></a><span data-ttu-id="bf775-115">Buscar dependencias UDT</span><span class="sxs-lookup"><span data-stu-id="bf775-115">Finding UDT Dependencies</span></span>  
 <span data-ttu-id="bf775-116">Debe quitar primero todos los objetos dependientes y, a continuación, ejecutar la instrucción DROP TYPE.</span><span class="sxs-lookup"><span data-stu-id="bf775-116">You must first drop all dependent objects, and then execute the DROP TYPE statement.</span></span> <span data-ttu-id="bf775-117">La siguiente [!INCLUDE[tsql](../../../includes/tsql-md.md)] consulta busca todas las columnas y parámetros que usan un UDT en la base de datos **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="bf775-117">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] query locates all of the columns and parameters that use a UDT in the **AdventureWorks** database.</span></span>  
  
```  
USE Adventureworks;  
SELECT o.name AS major_name, o.type_desc AS major_type_desc  
     , c.name AS minor_name, c.type_desc AS minor_type_desc  
     , at.assembly_class  
  FROM (  
        SELECT object_id, name, user_type_id, 'SQL_COLUMN' AS type_desc  
          FROM sys.columns  
     UNION ALL  
        SELECT object_id, name, user_type_id, 'SQL_PROCEDURE_PARAMETER'  
          FROM sys.parameters  
     ) AS c  
  JOIN sys.objects AS o  
    ON o.object_id = c.object_id  
  JOIN sys.assembly_types AS at  
    ON at.user_type_id = c.user_type_id;   
```  
  
## <a name="see-also"></a><span data-ttu-id="bf775-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf775-118">See Also</span></span>  
 <span data-ttu-id="bf775-119">[Administrar ensamblados de integración CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="bf775-119">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="bf775-120">[Modificar un ensamblado](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="bf775-120">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="bf775-121">[Crear un ensamblado](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="bf775-121">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="bf775-122">[DROP Aggregate &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bf775-122">[DROP AGGREGATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span></span>  
 <span data-ttu-id="bf775-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bf775-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span></span>  
 <span data-ttu-id="bf775-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bf775-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="bf775-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bf775-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="bf775-126">DROP TYPE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bf775-126">DROP TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-type-transact-sql)  
  
  
