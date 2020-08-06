---
title: Obtener información sobre los desencadenadores DDL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- status information [SQL Server], DDL triggers
- DDL triggers, metadata
ms.assetid: 462becea-292a-4b9e-bb98-533e89733911
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cd71d188c2f53bd9872359199c07d700688552d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676925"
---
# <a name="get-information-about-ddl-triggers"></a><span data-ttu-id="47bbc-102">Obtener información acerca de los desencadenadores DDL</span><span class="sxs-lookup"><span data-stu-id="47bbc-102">Get Information About DDL Triggers</span></span>
  <span data-ttu-id="47bbc-103">Las vistas de catálogo que se enumeran en esta sección pueden utilizarse para obtener información sobre los desencadenadores DDL.</span><span class="sxs-lookup"><span data-stu-id="47bbc-103">The catalog views listed in this section can be used to get information about DDL Triggers.</span></span>  
  
 <span data-ttu-id="47bbc-104">**Para obtener información sobre los eventos o grupos de eventos en que un desencadenador DDL puede activar**</span><span class="sxs-lookup"><span data-stu-id="47bbc-104">**To get information about the events or event groups on which a DDL trigger can fire.**</span></span>  
  
-   [<span data-ttu-id="47bbc-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-event-types-transact-sql)  
  
 <span data-ttu-id="47bbc-106">**Para ver las dependencias de un desencadenador**</span><span class="sxs-lookup"><span data-stu-id="47bbc-106">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="47bbc-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="47bbc-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="47bbc-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="database-scoped-ddl-triggers"></a><span data-ttu-id="47bbc-110">Desencadenadores DDL con ámbito de base de datos</span><span class="sxs-lookup"><span data-stu-id="47bbc-110">Database-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="47bbc-111">**Para obtener información acerca de los desencadenadores con ámbito de base de datos**</span><span class="sxs-lookup"><span data-stu-id="47bbc-111">**To get information about database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="47bbc-112">sys.triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-112">sys.triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql)  
  
 <span data-ttu-id="47bbc-113">**Para obtener información acerca de los desencadenadores que activan eventos de base de datos**</span><span class="sxs-lookup"><span data-stu-id="47bbc-113">**To get information about database events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="47bbc-114">sys.trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-114">sys.trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql)  
  
 <span data-ttu-id="47bbc-115">**Para ver la definición de un desencadenador con ámbito de base de datos**</span><span class="sxs-lookup"><span data-stu-id="47bbc-115">**To view the definition of a database-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="47bbc-116">sys.sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-116">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
 <span data-ttu-id="47bbc-117">**Para obtener información acerca de los desencadenadores con ámbito de base de datos de CLR**</span><span class="sxs-lookup"><span data-stu-id="47bbc-117">**To get information about CLR database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="47bbc-118">sys.assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-118">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
## <a name="server-scoped-ddl-triggers"></a><span data-ttu-id="47bbc-119">Desencadenadores DDL con ámbito de servidor</span><span class="sxs-lookup"><span data-stu-id="47bbc-119">Server-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="47bbc-120">**Para obtener información acerca de los desencadenadores con ámbito de servidor**</span><span class="sxs-lookup"><span data-stu-id="47bbc-120">**To get information about server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="47bbc-121">sys.server_triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-121">sys.server_triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql)  
  
 <span data-ttu-id="47bbc-122">**Para obtener información acerca de los desencadenadores que activan eventos de base de datos**</span><span class="sxs-lookup"><span data-stu-id="47bbc-122">**To get information about server events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="47bbc-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql)  
  
 <span data-ttu-id="47bbc-124">**Para ver la definición de un desencadenador con ámbito de servidor**</span><span class="sxs-lookup"><span data-stu-id="47bbc-124">**To view the definition of a server-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="47bbc-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql)  
  
 <span data-ttu-id="47bbc-126">**Para obtener información acerca de los desencadenadores con ámbito de servidor de CLR**</span><span class="sxs-lookup"><span data-stu-id="47bbc-126">**To get information about CLR server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="47bbc-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47bbc-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="47bbc-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47bbc-128">See Also</span></span>  
 [<span data-ttu-id="47bbc-129">Desencadenadores DDL</span><span class="sxs-lookup"><span data-stu-id="47bbc-129">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
