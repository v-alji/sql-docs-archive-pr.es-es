---
title: Los operadores de combinación externa *= y =* no se admiten en los modos de compatibilidad 90 o posteriores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- =* join
- '*= join'
- joins [SQL Server]
ms.assetid: ca4aa11f-1048-411f-9c6c-3d0a8e319f2f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 357c729e6d53cc17f2e4c169dd66613b6cfd2f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747901"
---
# <a name="outer-join-operators--and--are-not-supported-in-90-or-later-compatibility-modes"></a><span data-ttu-id="971a5-102">No se admiten los operadores de combinación externa \*= y =\* en los modos de compatibilidad 90 o posteriores</span><span class="sxs-lookup"><span data-stu-id="971a5-102">Outer join operators \*= and =\* are not supported in 90 or later compatibility modes</span></span>
  <span data-ttu-id="971a5-103">El asesor de actualizaciones ha detectado el uso de operadores de combinación externa \* = y = \* .</span><span class="sxs-lookup"><span data-stu-id="971a5-103">Upgrade Advisor detected the use of outer join operators \*= and =\*.</span></span> <span data-ttu-id="971a5-104">Estos operadores no se admiten en los modos de compatibilidad 90 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="971a5-104">These operators are not supported in 90 or later compatibility modes.</span></span> <span data-ttu-id="971a5-105">Cuando actualiza, las bases de datos de usuarios conservan su modo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="971a5-105">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="971a5-106">Las instrucciones que usan estos operadores generarán un error.</span><span class="sxs-lookup"><span data-stu-id="971a5-106">Statements that use these operators will fail.</span></span>  
  
## <a name="component"></a><span data-ttu-id="971a5-107">Componente</span><span class="sxs-lookup"><span data-stu-id="971a5-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="971a5-108">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="971a5-108">Corrective Action</span></span>  
 <span data-ttu-id="971a5-109">Antes de cambiar el modo de compatibilidad de la base de datos a 90 o posterior, modifique las instrucciones que utilizan los operadores de combinación externa \* = y = \* para usar palabras clave equivalentes de combinación externa.</span><span class="sxs-lookup"><span data-stu-id="971a5-109">Before you change the database compatibility mode to 90 or later, modify statements that use the outer join operators \*= and =\* to use equivalent OUTER JOIN keywords.</span></span> <span data-ttu-id="971a5-110">El ejemplo siguiente muestra una consulta que utiliza el operador `\*=` y una consulta equivalente que utiliza las palabras clave `LEFT OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="971a5-110">The following example shows a query that uses the `\*=` operator and an equivalent query that uses the `LEFT OUTER JOIN` keywords.</span></span>  
  
```  
-- This query uses an old-style outer join operator.  
USE pubs  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee, jobs   
WHERE employee.job_id *= jobs.job_id  
ORDER BY employee.job_id  
  
-- This query uses the ANSI standard keywords LEFT OUTER JOIN.  
USE pubs;  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
ORDER BY employee.job_id  
```  
  
 <span data-ttu-id="971a5-111">Para obtener más información sobre combinaciones externas, vea "Usar combinaciones externas" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="971a5-111">For more information about outer joins, see "Using Outer Joins" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="971a5-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="971a5-112">See Also</span></span>  
 <span data-ttu-id="971a5-113">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="971a5-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="971a5-114">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="971a5-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
