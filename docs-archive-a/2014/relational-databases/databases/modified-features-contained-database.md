---
title: Características modificadas (base de datos independiente) | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, modifications to DBs
ms.assetid: a2942509-39a2-4903-b504-ae80a300a9de
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc52821deeb879022881f838c61823b23c0c10c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751057"
---
# <a name="modified-features-contained-database"></a><span data-ttu-id="33c7d-102">Características modificadas (base de datos contenida)</span><span class="sxs-lookup"><span data-stu-id="33c7d-102">Modified Features (Contained Database)</span></span>
  <span data-ttu-id="33c7d-103">Las siguientes características se han modificado de forma que las bases de datos parcialmente independientes las admitan.</span><span class="sxs-lookup"><span data-stu-id="33c7d-103">The following features have been modified to be supported by a partially contained database.</span></span> <span data-ttu-id="33c7d-104">Normalmente, las características se modifican de modo que no crucen el límite de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="33c7d-104">Features are usually modified so they do not cross the database boundary.</span></span>  
  
 <span data-ttu-id="33c7d-105">Para más información, consulte [Contained Databases](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="33c7d-105">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
## <a name="alter-database"></a><span data-ttu-id="33c7d-106">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="33c7d-106">ALTER DATABASE</span></span>  
  
### <a name="application-level"></a><span data-ttu-id="33c7d-107">Nivel de aplicación</span><span class="sxs-lookup"><span data-stu-id="33c7d-107">Application Level</span></span>  
 <span data-ttu-id="33c7d-108">Al utilizar la instrucción ALTER DATABASE desde dentro de una base de datos contenida, la sintaxis difiere de la que se usa para una base de datos dependiente.</span><span class="sxs-lookup"><span data-stu-id="33c7d-108">When using the ALTER DATABASE statement from inside of a contained database, the syntax differs from that used for a non-contained database.</span></span> <span data-ttu-id="33c7d-109">Esta diferencia incluye restricciones de los elementos de la instrucción que se extienden más allá de la base de datos y llegan a la instancia.</span><span class="sxs-lookup"><span data-stu-id="33c7d-109">This difference includes restrictions of elements of the statement that extend beyond the database to the instance.</span></span> <span data-ttu-id="33c7d-110">Para obtener más información, vea [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="33c7d-110">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
### <a name="instance-level"></a><span data-ttu-id="33c7d-111">Nivel de instancia</span><span class="sxs-lookup"><span data-stu-id="33c7d-111">Instance Level</span></span>  
 <span data-ttu-id="33c7d-112">La sintaxis de ALTER DATABASE cuando se utiliza fuera de una base de datos contenida difiere de la que se usa para bases de datos dependientes.</span><span class="sxs-lookup"><span data-stu-id="33c7d-112">The syntax for the ALTER DATABASE when used outside of a contained database differs from that used for non-contained databases.</span></span> <span data-ttu-id="33c7d-113">Estos cambios impiden cruzar el límite de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="33c7d-113">These changes prevent crossing the database boundary.</span></span> <span data-ttu-id="33c7d-114">Para obtener más información, vea [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="33c7d-114">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="create-database"></a><span data-ttu-id="33c7d-115">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="33c7d-115">CREATE DATABASE</span></span>  
 <span data-ttu-id="33c7d-116">La sintaxis de CREATE DATABASE para una base de datos contenida difiere de que se usa para una base de datos dependiente.</span><span class="sxs-lookup"><span data-stu-id="33c7d-116">The CREATE DATABASE syntax for a contained database differs from that for a non-contained database.</span></span> <span data-ttu-id="33c7d-117">Vea [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) para obtener más información sobre los nuevos requisitos de sintaxis y valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="33c7d-117">See [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)for information about new syntax requirements and allowances.</span></span>  
  
## <a name="temporary-tables"></a><span data-ttu-id="33c7d-118">Tablas temporales</span><span class="sxs-lookup"><span data-stu-id="33c7d-118">Temporary Tables</span></span>  
 <span data-ttu-id="33c7d-119">Las tablas temporales locales se permiten en una base de datos independiente, pero su comportamiento difiere del de las tablas temporales locales en bases de datos dependientes.</span><span class="sxs-lookup"><span data-stu-id="33c7d-119">Local temporary tables are permitted within a contained database, but their behavior differs from those in non-contained databases.</span></span> <span data-ttu-id="33c7d-120">En las bases de datos dependientes, los datos de las tablas temporales se intercalan en la intercalación de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="33c7d-120">In non-contained databases, temporary table data is collated in the collation of **tempdb**.</span></span> <span data-ttu-id="33c7d-121">En una base de datos independiente, los datos de las tablas temporales se intercalan en la intercalación de la base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="33c7d-121">In a contained database temporary table data is collated in the collation of the contained database.</span></span>  
  
 <span data-ttu-id="33c7d-122">Todos los metadatos asociados a tablas temporales (por ejemplo, los nombres, índices, etc. de tablas y columnas) estarán en la intercalación del catálogo.</span><span class="sxs-lookup"><span data-stu-id="33c7d-122">All metadata associated with temporary tables (for example, table and column names, indexes, and so on) will be in the catalog collation.</span></span>  
  
 <span data-ttu-id="33c7d-123">En las tablas temporales no se pueden utilizar restricciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="33c7d-123">Named constraints may not be used in temporary tables.</span></span>  
  
 <span data-ttu-id="33c7d-124">Las tablas temporales no pueden hacer referencia a tipos definidos por el usuario, colecciones de esquemas XML ni funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="33c7d-124">Temporary tables may not refer to user-defined types, XML schema collections, or user-defined functions.</span></span>  
  
## <a name="collation"></a><span data-ttu-id="33c7d-125">Intercalación</span><span class="sxs-lookup"><span data-stu-id="33c7d-125">Collation</span></span>  
 <span data-ttu-id="33c7d-126">En el modelo de base de datos dependiente, hay tres tipos distintos de intercalación: intercalación de base de datos, intercalación de instancia e intercalación de tempdb.</span><span class="sxs-lookup"><span data-stu-id="33c7d-126">In the non-contained database model, there are three separate types of collation: Database collation, Instance collation, and tempdb collation.</span></span> <span data-ttu-id="33c7d-127">Las bases de datos contenidas solo usan dos intercalaciones, la intercalación de base de datos y la nueva intercalación de catálogo.</span><span class="sxs-lookup"><span data-stu-id="33c7d-127">Contained databases use only two collations, database collation and the new catalog collation.</span></span> <span data-ttu-id="33c7d-128">Vea [Contained Database Collations](contained-database-collations.md) para obtener más información sobre la intercalación de base de datos contenida.</span><span class="sxs-lookup"><span data-stu-id="33c7d-128">See [Contained Database Collations](contained-database-collations.md) for more details on contained database collation.</span></span>  
  
## <a name="user-options"></a><span data-ttu-id="33c7d-129">Opciones de usuario</span><span class="sxs-lookup"><span data-stu-id="33c7d-129">User Options</span></span>  
 <span data-ttu-id="33c7d-130">Al habilitar bases de datos independientes, la opción [user options](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) se debe establecer en 0 para la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33c7d-130">When enabling contained databases, the [user options Option](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) must be set to 0 for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c7d-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33c7d-131">See Also</span></span>  
 <span data-ttu-id="33c7d-132">[Intercalaciones de bases de datos independientes](contained-database-collations.md) </span><span class="sxs-lookup"><span data-stu-id="33c7d-132">[Contained Database Collations](contained-database-collations.md) </span></span>  
 [<span data-ttu-id="33c7d-133">Bases de datos independientes</span><span class="sxs-lookup"><span data-stu-id="33c7d-133">Contained Databases</span></span>](contained-databases.md)  
  
  
