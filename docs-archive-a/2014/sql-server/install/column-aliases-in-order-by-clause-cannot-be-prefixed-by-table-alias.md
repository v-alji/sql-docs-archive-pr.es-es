---
title: Los alias de columna en la cláusula ORDER BY no pueden ir precedidos por un alias de tabla | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], columns
ms.assetid: fee7328f-6e8d-4005-930b-56fb6f17e0b2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 44333d778753a2f8761d32d181681b798e3bc409
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672488"
---
# <a name="column-aliases-in-order-by-clause-cannot-be-prefixed-by-table-alias"></a><span data-ttu-id="ca981-102">El alias de tabla no puede asignar un prefijo a los alias de columna de la cláusula ORDER BY</span><span class="sxs-lookup"><span data-stu-id="ca981-102">Column aliases in ORDER BY clause cannot be prefixed by table alias</span></span>
  <span data-ttu-id="ca981-103">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o posterior, los alias de columna de la cláusula ORDER BY no pueden tener el prefijo del alias de tabla.</span><span class="sxs-lookup"><span data-stu-id="ca981-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, column aliases in the ORDER BY clause cannot be prefixed by the table alias.</span></span>  
  
## <a name="component"></a><span data-ttu-id="ca981-104">Componente</span><span class="sxs-lookup"><span data-stu-id="ca981-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="ca981-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca981-105">Description</span></span>  
 <span data-ttu-id="ca981-106">Por ejemplo, la siguiente consulta se ejecuta correctamente en [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], pero devuelve un error en [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ca981-106">For example, the following query executes in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but returns an error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.l  
```  
  
 <span data-ttu-id="ca981-107">[!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] no interpreta `p.l` en la cláusula `ORDER BY` como una columna válida de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ca981-107">The [!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] does not match `p.l` in the `ORDER BY` clause to a valid column in the table.</span></span>  
  
### <a name="exception"></a><span data-ttu-id="ca981-108">Excepción</span><span class="sxs-lookup"><span data-stu-id="ca981-108">Exception</span></span>  
 <span data-ttu-id="ca981-109">Si el alias de columna con prefijo que se especifica en la cláusula ORDER BY es un nombre de columna válido de la tabla especificada, la consulta se ejecutará sin errores; en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], la semántica de la instrucción podría ser diferente.</span><span class="sxs-lookup"><span data-stu-id="ca981-109">If the prefixed column alias that is specified in the ORDER BY clause is a valid column name in the specified table, the query executes without error; in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the semantics of the statement might be different.</span></span> <span data-ttu-id="ca981-110">Por ejemplo, el alias de columna (`id`) especificado en la siguiente instrucción es un nombre de columna válido de la tabla `sysobjects`.</span><span class="sxs-lookup"><span data-stu-id="ca981-110">For example, the column alias (`id`) specified in the following statement is a valid column name in the `sysobjects` table.</span></span> <span data-ttu-id="ca981-111">En [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], cuando se ejecuta la instrucción, se realiza la operación `CAST` una vez ordenado el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="ca981-111">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], when the statement executes, the `CAST` operation is performed after the result set is sorted.</span></span> <span data-ttu-id="ca981-112">Esto significa que la columna `name` se utiliza en la operación de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ca981-112">This means the `name` column is used in the sort operation.</span></span> <span data-ttu-id="ca981-113">En [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], la operación `CAST` se produce antes de la operación de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ca981-113">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the `CAST` operation occurs before the sort operation.</span></span> <span data-ttu-id="ca981-114">Esto significa que la columna `id` de la tabla se utiliza en la operación de ordenación y devuelve el conjunto de resultados con un orden diferente al esperado.</span><span class="sxs-lookup"><span data-stu-id="ca981-114">This means the `id` column in the table is used in the sort operation and returns the result set in an unexpected order.</span></span>  
  
```  
SELECT CAST (o.name AS char(128)) AS id  
FROM sysobjects AS o  
ORDER BY o.id;  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="ca981-115">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="ca981-115">Corrective Action</span></span>  
 <span data-ttu-id="ca981-116">Modifique las consultas que utilicen alias de columna precedidos por alias de tabla en la cláusula ORDER BY de alguna de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ca981-116">Modify queries that use column aliases prefixed by table aliases in the ORDER BY clause in either of the following ways:</span></span>  
  
-   <span data-ttu-id="ca981-117">Si es posible, no asigne ningún prefijo al alias de columna en la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="ca981-117">Do not prefix the column alias in the ORDER BY clause, if possible.</span></span>  
  
-   <span data-ttu-id="ca981-118">Reemplace el alias de columna por el nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="ca981-118">Replace the column alias with the column name.</span></span>  
  
 <span data-ttu-id="ca981-119">Por ejemplo, las siguientes consultas se ejecutan correctamente en [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ca981-119">For example, both of the following queries execute without error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY l  
  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.LastName  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca981-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca981-120">See Also</span></span>  
 <span data-ttu-id="ca981-121">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="ca981-121">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="ca981-122">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="ca981-122">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
