---
title: Especifique la palabra clave WITH al utilizar sugerencias de tabla en el modo de compatibilidad 90 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- table hints [SQL Server]
ms.assetid: 7636cc85-5155-44db-baf6-df807761adb8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ecd13475395cef4257d97eb7480f32420932e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672442"
---
# <a name="specify-the-with-keyword-when-using-table-hints-in-90-compatibility-mode"></a><span data-ttu-id="35260-102">Especificar la palabra clave WITH al utilizar sugerencias de tabla en el modo de compatibilidad 90</span><span class="sxs-lookup"><span data-stu-id="35260-102">Specify the WITH keyword when using table hints in 90 compatibility mode</span></span>
  <span data-ttu-id="35260-103">Con algunas excepciones, las sugerencias de tabla solo se admiten en la cláusula FROM de una consulta cuando se especifican con la palabra clave WITH.</span><span class="sxs-lookup"><span data-stu-id="35260-103">With some exceptions, table hints are supported in the FROM clause of a query only when the hints are specified by using the WITH keyword.</span></span> <span data-ttu-id="35260-104">Para obtener más información, vea los temas "FROM ([!INCLUDE[tsql](../../includes/tsql-md.md)])" y "Sugerencia de tabla ([!INCLUDE[tsql](../../includes/tsql-md.md)])" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35260-104">For more information, see the topics "FROM ([!INCLUDE[tsql](../../includes/tsql-md.md)])" and "Table Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="35260-105">Componente</span><span class="sxs-lookup"><span data-stu-id="35260-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="35260-106">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="35260-106">Corrective Action</span></span>  
 <span data-ttu-id="35260-107">Modifique las consultas que incluyan sugerencias de tabla en la cláusula FROM incluyendo la palabra clave WITH antes de la sugerencia de tabla.</span><span class="sxs-lookup"><span data-stu-id="35260-107">Modify queries that include table hints in the FROM clause by including the WITH keyword before the table hints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35260-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35260-108">See Also</span></span>  
 <span data-ttu-id="35260-109">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="35260-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="35260-110">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="35260-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
