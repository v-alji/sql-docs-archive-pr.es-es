---
title: Quitar las operaciones DDL en las tablas insertadas y eliminadas dentro de los desencadenadores DML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- data definition language [SQL Server]
- DDL statements [SQL Server]
- DML triggers, removing DDL operations
ms.assetid: e49ba7d5-787f-4052-b985-b699195d982b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 61f7ab78b5ab6251b7f27401d36423ec27141c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747914"
---
# <a name="remove-ddl-operations-on-the-inserted-and-deleted-tables-inside-dml-triggers"></a><span data-ttu-id="9095b-102">Quitar las operaciones DDL en las tablas insertadas y eliminadas en los desencadenadores DML</span><span class="sxs-lookup"><span data-stu-id="9095b-102">Remove DDL operations on the inserted and deleted tables inside DML triggers</span></span>
  <span data-ttu-id="9095b-103">Las instrucciones del lenguaje de definición de datos (DDL), como CREATE INDEX, no se pueden realizar en las tablas insertadas y eliminadas dentro de los desencadenadores DML.</span><span class="sxs-lookup"><span data-stu-id="9095b-103">Data definition language (DDL) statements, such as CREATE INDEX, cannot be performed on the inserted and deleted tables inside DML triggers.</span></span> <span data-ttu-id="9095b-104">Algunas instrucciones de DDL en dichas tablas están permitidas en versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9095b-104">Some DDL statements on the inserted and deleted tables are permitted in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9095b-105">Para obtener más información, vea "Usar las tablas insertadas y eliminadas" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9095b-105">For more information, see "Using the inserted and deleted Tables" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="9095b-106">Componente</span><span class="sxs-lookup"><span data-stu-id="9095b-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="9095b-107">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="9095b-107">Corrective Action</span></span>  
 <span data-ttu-id="9095b-108">Quite cualquier operación DDL que se lleve a cabo en las tablas insertadas y eliminadas dentro de los desencadenadores DML.</span><span class="sxs-lookup"><span data-stu-id="9095b-108">Remove any DDL operations that are performed on the inserted and deleted tables inside DML triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9095b-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9095b-109">See Also</span></span>  
 <span data-ttu-id="9095b-110">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="9095b-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="9095b-111">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="9095b-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
