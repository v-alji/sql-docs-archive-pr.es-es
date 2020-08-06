---
title: Compatibilidad de Transact-SQL con OLTP en memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b1cc7c30-1747-4c21-88ac-e95a5e58baac
author: rothja
ms.author: jroth
ms.openlocfilehash: bf3708a258e3bb97231e45b10bea2c59351a06a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749874"
---
# <a name="transact-sql-support-for-in-memory-oltp"></a><span data-ttu-id="b2263-102">Compatibilidad de Transact-SQL con OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="b2263-102">Transact-SQL Support for In-Memory OLTP</span></span>
  <span data-ttu-id="b2263-103">Puede acceder a las tablas optimizadas para memoria con cualquier consulta de Transact-SQL o instrucción DML (SELECT, INSERT, UPDATE o DELETE), instrucción ad hoc o módulo SQL como, por ejemplo, procedimientos almacenados, funciones con valores de tabla, funciones escalares, desencadenadores y vistas.</span><span class="sxs-lookup"><span data-stu-id="b2263-103">You can access memory-optimized tables using any Transact-SQL query or DML statement (SELECT, INSERT, UPDATE, or DELETE), ad hoc statement, and SQL module such as stored procedures, table-value functions, scalar functions, triggers, and views.</span></span> <span data-ttu-id="b2263-104">Para obtener más información, vea [obtener acceso a tablas optimizadas para memoria mediante Transact-SQL interpretado](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b2263-104">For more information see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span>  
  
 <span data-ttu-id="b2263-105">Los procedimientos almacenados que solo hacen referencia a tablas optimizadas para memoria se pueden compilar de forma nativa en código máquina. Por lo general, proporcionan un rendimiento considerable que los procedimientos almacenados interpretados (basados en disco).</span><span class="sxs-lookup"><span data-stu-id="b2263-105">Stored procedures that only reference memory-optimized tables can be natively compiled into machine code and typically provide significant performance gains over interpreted (disk-based) stored procedures.</span></span> <span data-ttu-id="b2263-106">Para optimizar el acceso a las tablas optimizadas para memoria, utilice procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="b2263-106">For optimized access to memory-optimized tables use natively compiled stored procedures.</span></span> <span data-ttu-id="b2263-107">Para más información, vea [Procedimientos almacenados compilados de forma nativa](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b2263-107">For more information, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="b2263-108">Al crear y modificar objetos de base de datos (instrucciones DDL), se modificaron las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="b2263-108">When creating and modifying database objects (DDL statements), the following statements have been modified:</span></span>  
  
-   <span data-ttu-id="b2263-109">[Opciones File y filegroup de Alter database &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (vea `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="b2263-109">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="b2263-110">[CREATE DATABASE &#40;SQL Server&#41;de Transact-SQL](/sql/t-sql/statements/create-database-sql-server-transact-sql) (vea `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="b2263-110">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="b2263-111">[Create procedure &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) (vea `NATIVE_COMPILATION` , `SCHEMABINDING` , `EXECUTE AS` y `BEGIN ATOMIC` )</span><span class="sxs-lookup"><span data-stu-id="b2263-111">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) (see `NATIVE_COMPILATION`, `SCHEMABINDING`, `EXECUTE AS`, and `BEGIN ATOMIC`)</span></span>  
  
-   <span data-ttu-id="b2263-112">[CREATE TABLE &#40;&#41;de Transact-SQL](/sql/t-sql/statements/create-table-transact-sql) (vea,,, `MEMORY_OPTIMIZED` `DURABILITY` `BUCKET_COUNT` `INDEX` y `HASH` )</span><span class="sxs-lookup"><span data-stu-id="b2263-112">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) (see `MEMORY_OPTIMIZED`, `DURABILITY`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="b2263-113">[Create Type &#40;&#41;de Transact-SQL](/sql/t-sql/statements/create-type-transact-sql) (vea `MEMORY_OPTIMIZED` ,, `BUCKET_COUNT` `INDEX` y `HASH` )</span><span class="sxs-lookup"><span data-stu-id="b2263-113">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) (see `MEMORY_OPTIMIZED`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="b2263-114">[Declare @local_variable &#40;&#41;de TRANSACT-SQL](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (vea `NULL`  |  `NOT NULL` )</span><span class="sxs-lookup"><span data-stu-id="b2263-114">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (see `NULL` | `NOT NULL`)</span></span>  
  
 <span data-ttu-id="b2263-115">Las tablas con optimización para memoria admiten las restricciones `PRIMARY KEY` y `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="b2263-115">Memory-optimized tables support `PRIMARY KEY` and `NOT NULL` constraints.</span></span> <span data-ttu-id="b2263-116">Para obtener información sobre la implementación de restricciones no admitidas, vea [migración de restricciones check y Foreign Key](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="b2263-116">For information on implementing unsupported constraints, see [Migrating Check and Foreign Key Constraints](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span></span>  
  
 <span data-ttu-id="b2263-117">Para obtener más información sobre las características no compatibles, vea [Construcciones Transact-SQL no admitidas por OLTP en memoria](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="b2263-117">For information on unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b2263-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b2263-118">In This Section</span></span>  
  
-   [<span data-ttu-id="b2263-119">Tipos de datos admitidos</span><span class="sxs-lookup"><span data-stu-id="b2263-119">Supported Data Types</span></span>](supported-data-types-for-in-memory-oltp.md)  
  
-   [<span data-ttu-id="b2263-120">Acceso a tablas con optimización para memoria mediante Transact-SQL interpretado</span><span class="sxs-lookup"><span data-stu-id="b2263-120">Accessing Memory-Optimized Tables Using Interpreted Transact-SQL</span></span>](accessing-memory-optimized-tables-using-interpreted-transact-sql.md)  
  
-   [<span data-ttu-id="b2263-121">Vistas del sistema, procedimientos almacenados, tipos de espera para OLTP en memoria y DMV</span><span class="sxs-lookup"><span data-stu-id="b2263-121">System Views, Stored Procedures, DMVs and Wait Types for In-Memory OLTP</span></span>](../../database-engine/system-views-stored-procedures-dmvs-and-wait-types-for-in-memory-oltp.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2263-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2263-122">See Also</span></span>  
 <span data-ttu-id="b2263-123">[OLTP en memoria &#40;optimización en memoria&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="b2263-123">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 <span data-ttu-id="b2263-124">[Problemas de migración para los procedimientos almacenados compilados de forma nativa](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b2263-124">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 <span data-ttu-id="b2263-125">[Características admitidas de SQL Server](unsupported-sql-server-features-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="b2263-125">[Supported SQL Server Features](unsupported-sql-server-features-for-in-memory-oltp.md) </span></span>  
 [<span data-ttu-id="b2263-126">Procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="b2263-126">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
