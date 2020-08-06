---
title: Identificadores de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- regular identifiers [SQL Server]
- identifiers [SQL Server]
- names [SQL Server], identifiers
- identifiers [SQL Server], about identifiers
- SQL Server identifiers
- Transact-SQL identifiers
- database objects [SQL Server], names
ms.assetid: 171291bb-f57f-4ad1-8cea-0b092d5d150c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 347b20c12a0ac5edd82172741377617aa0fe12c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672108"
---
# <a name="database-identifiers"></a><span data-ttu-id="1084b-102">Identificadores de base de datos</span><span class="sxs-lookup"><span data-stu-id="1084b-102">Database Identifiers</span></span>
  <span data-ttu-id="1084b-103">El nombre de un objeto de base de datos se conoce como su identificador.</span><span class="sxs-lookup"><span data-stu-id="1084b-103">The database object name is referred to as its identifier.</span></span> <span data-ttu-id="1084b-104">Cualquier elemento de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede tener un identificador.</span><span class="sxs-lookup"><span data-stu-id="1084b-104">Everything in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can have an identifier.</span></span> <span data-ttu-id="1084b-105">Servidores, bases de datos y objetos de bases de datos, como tablas, vistas, columnas, índices, desencadenadores, procedimientos, restricciones, reglas, etc. pueden tener identificadores.</span><span class="sxs-lookup"><span data-stu-id="1084b-105">Servers, databases, and database objects, such as tables, views, columns, indexes, triggers, procedures, constraints, and rules, can have identifiers.</span></span> <span data-ttu-id="1084b-106">Se requiere que la mayor parte de los objetos tengan identificadores; pero para ciertos objetos, como las restricciones, son opcionales.</span><span class="sxs-lookup"><span data-stu-id="1084b-106">Identifiers are required for most objects, but are optional for some objects such as constraints.</span></span>  
  
 <span data-ttu-id="1084b-107">El identificador de un objeto se crea cuando se define el objeto.</span><span class="sxs-lookup"><span data-stu-id="1084b-107">An object identifier is created when the object is defined.</span></span> <span data-ttu-id="1084b-108">A continuación, el identificador se utiliza para hacer referencia al objeto.</span><span class="sxs-lookup"><span data-stu-id="1084b-108">The identifier is then used to reference the object.</span></span> <span data-ttu-id="1084b-109">Por ejemplo, la instrucción siguiente crea una tabla con el identificador `TableX`y dos columnas con los identificadores `KeyCol` y `Description`:</span><span class="sxs-lookup"><span data-stu-id="1084b-109">For example, the following statement creates a table with the identifier `TableX`, and two columns with the identifiers `KeyCol` and `Description`:</span></span>  
  
```  
CREATE TABLE TableX  
(KeyCol INT PRIMARY KEY, Description nvarchar(80))  
```  
  
 <span data-ttu-id="1084b-110">Esta tabla tiene también una restricción sin nombre.</span><span class="sxs-lookup"><span data-stu-id="1084b-110">This table also has an unnamed constraint.</span></span> <span data-ttu-id="1084b-111">La restricción `PRIMARY KEY` no tiene ningún identificador.</span><span class="sxs-lookup"><span data-stu-id="1084b-111">The `PRIMARY KEY` constraint has no identifier.</span></span>  
  
 <span data-ttu-id="1084b-112">La intercalación de un identificador depende del nivel en que está definido.</span><span class="sxs-lookup"><span data-stu-id="1084b-112">The collation of an identifier depends on the level at which it is defined.</span></span> <span data-ttu-id="1084b-113">Se asigna a los identificadores de objetos de instancia, como los inicios de sesión y los nombres de base de datos, la intercalación predeterminada de la instancia.</span><span class="sxs-lookup"><span data-stu-id="1084b-113">Identifiers of instance-level objects, such as logins and database names, are assigned the default collation of the instance.</span></span> <span data-ttu-id="1084b-114">A los identificadores de objetos de una base de datos, como nombres de tablas, vistas y columnas, se asigna la intercalación predeterminada de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1084b-114">Identifiers of objects in a database, such as tables, views, and column names, are assigned the default collation of the database.</span></span> <span data-ttu-id="1084b-115">Por ejemplo, es posible crear dos tablas con nombres que solo se diferencian en las mayúsculas en una base de datos con intercalación que distinga entre mayúsculas y minúsculas, pero no se pueden crear en una base de datos con intercalación que no distinga entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1084b-115">For example, two tables with names that differ only in case can be created in a database that has case-sensitive collation, but cannot be created in a database that has case-insensitive collation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1084b-116">Los nombres de variables o los parámetros de funciones y procedimientos almacenados deben cumplir las reglas para los identificadores de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1084b-116">The names of variables, or the parameters of functions and stored procedures must comply with the rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
## <a name="classes-of-identifiers"></a><span data-ttu-id="1084b-117">Clases de identificadores</span><span class="sxs-lookup"><span data-stu-id="1084b-117">Classes of Identifiers</span></span>  
 <span data-ttu-id="1084b-118">Existen dos clases de identificadores:</span><span class="sxs-lookup"><span data-stu-id="1084b-118">There are two classes of identifiers:</span></span>  
  
 <span data-ttu-id="1084b-119">Identificadores normales</span><span class="sxs-lookup"><span data-stu-id="1084b-119">Regular identifiers</span></span>  
 <span data-ttu-id="1084b-120">Siguen las reglas de formato de los identificadores.</span><span class="sxs-lookup"><span data-stu-id="1084b-120">Comply with the rules for the format of identifiers.</span></span> <span data-ttu-id="1084b-121">Los identificadores normales no están delimitados cuando se usan en instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1084b-121">Regular identifiers are not delimited when they are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
SELECT *  
FROM TableX  
WHERE KeyCol = 124  
```  
  
 <span data-ttu-id="1084b-122">Identificadores delimitados</span><span class="sxs-lookup"><span data-stu-id="1084b-122">Delimited identifiers</span></span>  
 <span data-ttu-id="1084b-123">Se incluyen entre comillas dobles (") o corchetes ([ ]).</span><span class="sxs-lookup"><span data-stu-id="1084b-123">Are enclosed in double quotation marks (") or brackets ([ ]).</span></span> <span data-ttu-id="1084b-124">Los identificadores que siguen las reglas de formato de los identificadores pueden no estar delimitados.</span><span class="sxs-lookup"><span data-stu-id="1084b-124">Identifiers that comply with the rules for the format of identifiers might not be delimited.</span></span> <span data-ttu-id="1084b-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1084b-125">For example:</span></span>  
  
```  
SELECT *  
FROM [TableX]         --Delimiter is optional.  
WHERE [KeyCol] = 124  --Delimiter is optional.  
```  
  
 <span data-ttu-id="1084b-126">Los identificadores que no cumplen las reglas de los identificadores deben estar delimitados en las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1084b-126">Identifiers that do not comply with all the rules for identifiers must be delimited in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="1084b-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1084b-127">For example:</span></span>  
  
```  
SELECT *  
FROM [My Table]      --Identifier contains a space and uses a reserved keyword.  
WHERE [order] = 10   --Identifier is a reserved keyword.  
```  
  
 <span data-ttu-id="1084b-128">Ambos identificadores, normales y delimitados, deben tener entre 1 y 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="1084b-128">Both regular and delimited identifiers must contain from 1 through 128 characters.</span></span> <span data-ttu-id="1084b-129">En el caso de las tablas temporales locales, el identificador puede tener un máximo de 116 caracteres.</span><span class="sxs-lookup"><span data-stu-id="1084b-129">For local temporary tables, the identifier can have a maximum of 116 characters.</span></span>  
  
## <a name="rules-for-regular-identifiers"></a><span data-ttu-id="1084b-130">Reglas de los identificadores normales</span><span class="sxs-lookup"><span data-stu-id="1084b-130">Rules for Regular Identifiers</span></span>  
 <span data-ttu-id="1084b-131">Los nombres de variables, funciones y procedimientos almacenados deben cumplir las siguientes reglas para los identificadores de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1084b-131">The names of variables, functions, and stored procedures must comply with the following rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
1.  <span data-ttu-id="1084b-132">El primer carácter debe ser alguno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1084b-132">The first character must be one of the following:</span></span>  
  
    -   <span data-ttu-id="1084b-133">Una letra, tal como se define en el estándar Unicode 3,2.</span><span class="sxs-lookup"><span data-stu-id="1084b-133">A letter as defined by the Unicode Standard 3.2.</span></span> <span data-ttu-id="1084b-134">La definición Unicode de letras incluye los caracteres latinos de la “a” a la “z” y de la “A” a la “Z”, además de los caracteres de letras de otros idiomas.</span><span class="sxs-lookup"><span data-stu-id="1084b-134">The Unicode definition of letters includes Latin characters from a through z, from A through Z, and also letter characters from other languages.</span></span>  
  
    -   <span data-ttu-id="1084b-135">El signo de subrayado (_), arroba (@) o número (#).</span><span class="sxs-lookup"><span data-stu-id="1084b-135">The underscore (_), at sign (@), or number sign (#).</span></span>  
  
         <span data-ttu-id="1084b-136">Ciertos símbolos al principio de un identificador tienen un significado especial en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1084b-136">Certain symbols at the beginning of an identifier have special meaning in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1084b-137">Un identificador normal que comience por el signo arroba siempre denotará una variable local o un parámetro, y no se puede usar como nombre de ningún otro tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="1084b-137">A regular identifier that starts with the at sign always denotes a local variable or parameter and cannot be used as the name of any other type of object.</span></span> <span data-ttu-id="1084b-138">Un identificador que empieza con el signo de número indica una tabla o procedimiento temporal.</span><span class="sxs-lookup"><span data-stu-id="1084b-138">An identifier that starts with a number sign denotes a temporary table or procedure.</span></span> <span data-ttu-id="1084b-139">Un identificador que empieza con un signo de número doble (##) indica un objeto temporal global.</span><span class="sxs-lookup"><span data-stu-id="1084b-139">An identifier that starts with double number signs (##) denotes a global temporary object.</span></span> <span data-ttu-id="1084b-140">Aunque es posible utilizar los caracteres de signo de número o doble signo de número para comenzar los nombres de otros tipos de objetos, no se recomienda hacerlo.</span><span class="sxs-lookup"><span data-stu-id="1084b-140">Although the number sign or double number sign characters can be used to begin the names of other types of objects, we do not recommend this practice.</span></span>  
  
         <span data-ttu-id="1084b-141">Algunas funciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] tienen nombres que empiezan con un doble signo de arroba (@@).</span><span class="sxs-lookup"><span data-stu-id="1084b-141">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] functions have names that start with double at signs (@@).</span></span> <span data-ttu-id="1084b-142">Para evitar confusiones con estas funciones, se recomienda no utilizar nombres que empiecen con @@.</span><span class="sxs-lookup"><span data-stu-id="1084b-142">To avoid confusion with these functions, you should not use names that start with @@.</span></span>  
  
2.  <span data-ttu-id="1084b-143">Los caracteres subsiguientes pueden ser:</span><span class="sxs-lookup"><span data-stu-id="1084b-143">Subsequent characters can include the following:</span></span>  
  
    -   <span data-ttu-id="1084b-144">Letras, tal como se definen en el estándar Unicode 3,2.</span><span class="sxs-lookup"><span data-stu-id="1084b-144">Letters as defined in the Unicode Standard 3.2.</span></span>  
  
    -   <span data-ttu-id="1084b-145">Números decimales del alfabeto Latín básico u otros alfabetos de otros idiomas.</span><span class="sxs-lookup"><span data-stu-id="1084b-145">Decimal numbers from either Basic Latin or other national scripts.</span></span>  
  
    -   <span data-ttu-id="1084b-146">El signo de arroba, dólar ($), número o subrayado.</span><span class="sxs-lookup"><span data-stu-id="1084b-146">The at sign, dollar sign ($), number sign, or underscore.</span></span>  
  
3.  <span data-ttu-id="1084b-147">El identificador no debe ser una palabra reservada de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1084b-147">The identifier must not be a [!INCLUDE[tsql](../../includes/tsql-md.md)] reserved word.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1084b-148">se reserva las versiones en mayúsculas y minúsculas de las palabras reservadas.</span><span class="sxs-lookup"><span data-stu-id="1084b-148">reserves both the uppercase and lowercase versions of reserved words.</span></span> <span data-ttu-id="1084b-149">Cuando se utilizan en instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] , los identificadores que no cumplan estas reglas deben aparecer delimitados por comillas dobles o corchetes.</span><span class="sxs-lookup"><span data-stu-id="1084b-149">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span> <span data-ttu-id="1084b-150">Las palabras reservadas dependen del nivel de compatibilidad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1084b-150">The words that are reserved depend on the database compatibility level.</span></span> <span data-ttu-id="1084b-151">Este nivel se puede establecer mediante la instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) .</span><span class="sxs-lookup"><span data-stu-id="1084b-151">This level can be set by using the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) statement.</span></span>  
  
4.  <span data-ttu-id="1084b-152">No se permiten los caracteres especiales o los espacios incrustados.</span><span class="sxs-lookup"><span data-stu-id="1084b-152">Embedded spaces or special characters are not allowed.</span></span>  
  
5.  <span data-ttu-id="1084b-153">Los caracteres complementarios no están permitidos.</span><span class="sxs-lookup"><span data-stu-id="1084b-153">Supplementary characters are not allowed.</span></span>  
  
 <span data-ttu-id="1084b-154">Cuando se utilizan en instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] , los identificadores que no cumplan estas reglas deben aparecer delimitados por comillas dobles o corchetes.</span><span class="sxs-lookup"><span data-stu-id="1084b-154">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1084b-155">Algunas reglas de formato de los identificadores normales dependen del nivel de compatibilidad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1084b-155">Some rules for the format of regular identifiers depend on the database compatibility level.</span></span> <span data-ttu-id="1084b-156">Este nivel se puede establecer mediante [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="1084b-156">This level can be set by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1084b-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1084b-157">See Also</span></span>  
 <span data-ttu-id="1084b-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="1084b-159">[CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-159">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="1084b-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span></span>  
 <span data-ttu-id="1084b-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="1084b-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span></span>  
 <span data-ttu-id="1084b-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="1084b-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="1084b-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 <span data-ttu-id="1084b-166">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-166">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="1084b-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="1084b-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="1084b-169">[Palabras clave reservadas &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-169">[Reserved Keywords &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span></span>  
 <span data-ttu-id="1084b-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1084b-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="1084b-171">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1084b-171">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
