---
title: Las consultas FOR XML AUTO devuelven referencias de tabla derivadas en los modos de compatibilidad 90 o posterior | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FOR XML AUTO [SQL Server]
ms.assetid: 10c32f06-f7e1-40e0-8f79-6d921f2bef1d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 702cb2ca1d437dff03cee09c98d72082500709d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678041"
---
# <a name="for-xml-auto-queries-return-derived-table-references-in-90-or-later-compatibility-modes"></a><span data-ttu-id="a64b3-102">Las consultas FOR XML AUTO devuelven referencias a tablas derivadas en los modos de compatibilidad 90 o superiores</span><span class="sxs-lookup"><span data-stu-id="a64b3-102">FOR XML AUTO queries return derived table references in 90 or later compatibility modes</span></span>
  <span data-ttu-id="a64b3-103">Cuando el nivel de compatibilidad de la base de datos está establecido en 90 o más, las consultas FOR XML que se ejecutan en modo AUTO devuelven referencias a alias de tabla derivadas.</span><span class="sxs-lookup"><span data-stu-id="a64b3-103">When the database compatibility level is set to 90 or later, FOR XML queries that execute in AUTO mode return references to derived table aliases.</span></span> <span data-ttu-id="a64b3-104">Cuando el nivel de compatibilidad de la base de datos está establecido en 80, las consultas FOR XML AUTO devuelven referencias a las tablas base que definen una tabla derivada.</span><span class="sxs-lookup"><span data-stu-id="a64b3-104">When the compatibility level is set to 80, FOR XML AUTO queries return references to the base tables that define a derived table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a64b3-105">Componente</span><span class="sxs-lookup"><span data-stu-id="a64b3-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a64b3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a64b3-106">Description</span></span>  
 <span data-ttu-id="a64b3-107">Considere, por ejemplo, la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="a64b3-107">For example, consider the following table:</span></span>  
  
```  
CREATE TABLE Test(id int);  
INSERT INTO Test VALUES(1);  
INSERT INTO Test VALUES(2);  
```  
  
 <span data-ttu-id="a64b3-108">La siguiente consulta, que incluye una tabla derivada, genera resultados diferentes en los niveles de compatibilidad 80, 90 y posteriores:</span><span class="sxs-lookup"><span data-stu-id="a64b3-108">The following query, which includes a derived table, produces different results under compatibility levels 80, 90, or later:</span></span>  
  
```  
SELECT * FROM   
   (SELECT a.id AS a, b.id AS b   
    FROM Test a JOIN Test b ON a.id=b.id)  
AS DerivedTest   
FOR XML AUTO;  
```  
  
 <span data-ttu-id="a64b3-109">En el nivel de compatibilidad 80, la consulta devuelve los resultados siguientes.</span><span class="sxs-lookup"><span data-stu-id="a64b3-109">Under compatibility level 80, the query returns the following results.</span></span> <span data-ttu-id="a64b3-110">Los resultados hacen referencia a los alias de la tabla base `a` y `b` de la tabla derivada, en lugar del alias de la tabla derivada.</span><span class="sxs-lookup"><span data-stu-id="a64b3-110">The results reference the base table aliases `a` and `b` of the derived table instead of the derived table alias.</span></span>  
  
```  
<a a="1"><b b="1"/></a><a a="2"><b b="2"/></a>  
```  
  
 <span data-ttu-id="a64b3-111">En el nivel de compatibilidad 90 o superior, la consulta devuelve referencias a los alias de la tabla derivada `DerivedTest` en lugar de a las tablas base de la tabla derivada.</span><span class="sxs-lookup"><span data-stu-id="a64b3-111">Under compatibility level 90 or later, the query returns references to the derived table alias `DerivedTest` instead of to the derived table's base tables.</span></span>  
  
```  
<DerivedTest a="1" b="1"/><DerivedTest a="2" b="2"/>  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="a64b3-112">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="a64b3-112">Corrective Action</span></span>  
 <span data-ttu-id="a64b3-113">Modifique su aplicación de acuerdo a los cambios en los resultados de las consultas FOR XML AUTO que incluyen tablas derivadas y que se ejecutan en el nivel de compatibilidad 90 o superior.</span><span class="sxs-lookup"><span data-stu-id="a64b3-113">Modify your application as required to account for the changes in results of FOR XML AUTO queries that include derived tables and that run under compatibility level 90 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a64b3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a64b3-114">See Also</span></span>  
 <span data-ttu-id="a64b3-115">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a64b3-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a64b3-116">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="a64b3-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
