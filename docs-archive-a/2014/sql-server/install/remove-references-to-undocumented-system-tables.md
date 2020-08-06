---
title: Quitar referencias a tablas del sistema no documentadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system tables [SQL Server]
- system tables [SQL Server]
ms.assetid: 010b1236-2219-4bf4-a6db-e3fc3abfa37a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 45c38038ee3d3214e4303c0ddbe0110be926c37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747895"
---
# <a name="remove-references-to-undocumented-system-tables"></a><span data-ttu-id="d2f34-102">Quitar referencias a tablas del sistema no documentadas</span><span class="sxs-lookup"><span data-stu-id="d2f34-102">Remove references to undocumented system tables</span></span>
  <span data-ttu-id="d2f34-103">Muchas tablas del sistema que no estaban documentadas en las versiones anteriores han cambiado o ya no existen; por consiguiente, si se utilizan dichas tablas, se pueden producir errores tras la actualización.</span><span class="sxs-lookup"><span data-stu-id="d2f34-103">Many system tables that were undocumented in prior releases have changed or no longer exist; therefore, using these tables may cause errors after upgrading.</span></span> <span data-ttu-id="d2f34-104">Dado que el Asesor de actualizaciones busca referencias a nombres de tablas del sistema, le informará sobre aquellas referencias a tablas del usuario que tengan el mismo nombre que una tabla del sistema.</span><span class="sxs-lookup"><span data-stu-id="d2f34-104">Because Upgrade Advisor looks for references to system table names, it will report references to any user tables that have the same names as system tables.</span></span>  
  
## <a name="component"></a><span data-ttu-id="d2f34-105">Componente</span><span class="sxs-lookup"><span data-stu-id="d2f34-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="d2f34-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2f34-106">Description</span></span>  
 <span data-ttu-id="d2f34-107">Las siguientes tablas del sistema no documentadas se han quitado:</span><span class="sxs-lookup"><span data-stu-id="d2f34-107">The following undocumented system tables are removed:</span></span>  
  
-   <span data-ttu-id="d2f34-108">**spt_datatype_info**</span><span class="sxs-lookup"><span data-stu-id="d2f34-108">**spt_datatype_info**</span></span>  
  
-   <span data-ttu-id="d2f34-109">**spt_datatype_info_ext**</span><span class="sxs-lookup"><span data-stu-id="d2f34-109">**spt_datatype_info_ext**</span></span>  
  
-   <span data-ttu-id="d2f34-110">**spt_provider_types**</span><span class="sxs-lookup"><span data-stu-id="d2f34-110">**spt_provider_types**</span></span>  
  
-   <span data-ttu-id="d2f34-111">**spt_server_info**</span><span class="sxs-lookup"><span data-stu-id="d2f34-111">**spt_server_info**</span></span>  
  
-   <span data-ttu-id="d2f34-112">**spt_values**</span><span class="sxs-lookup"><span data-stu-id="d2f34-112">**spt_values**</span></span>  
  
-   <span data-ttu-id="d2f34-113">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="d2f34-113">**sysfulltextnotify**</span></span>  
  
-   <span data-ttu-id="d2f34-114">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="d2f34-114">**syslocks**</span></span>  
  
-   <span data-ttu-id="d2f34-115">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="d2f34-115">**sysproperties**</span></span>  
  
-   <span data-ttu-id="d2f34-116">**sysprotects_aux**</span><span class="sxs-lookup"><span data-stu-id="d2f34-116">**sysprotects_aux**</span></span>  
  
-   <span data-ttu-id="d2f34-117">**sysprotects_view**</span><span class="sxs-lookup"><span data-stu-id="d2f34-117">**sysprotects_view**</span></span>  
  
-   <span data-ttu-id="d2f34-118">**SYSREMOTE_CATALOGS**</span><span class="sxs-lookup"><span data-stu-id="d2f34-118">**SYSREMOTE_CATALOGS**</span></span>  
  
-   <span data-ttu-id="d2f34-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="d2f34-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="d2f34-120">**SYSREMOTE_COLUMNS**</span><span class="sxs-lookup"><span data-stu-id="d2f34-120">**SYSREMOTE_COLUMNS**</span></span>  
  
-   <span data-ttu-id="d2f34-121">**SYSREMOTE_FOREIGN_KEYS**</span><span class="sxs-lookup"><span data-stu-id="d2f34-121">**SYSREMOTE_FOREIGN_KEYS**</span></span>  
  
-   <span data-ttu-id="d2f34-122">**SYSREMOTE_INDEXES**</span><span class="sxs-lookup"><span data-stu-id="d2f34-122">**SYSREMOTE_INDEXES**</span></span>  
  
-   <span data-ttu-id="d2f34-123">**SYSREMOTE_PRIMARY_KEYS**</span><span class="sxs-lookup"><span data-stu-id="d2f34-123">**SYSREMOTE_PRIMARY_KEYS**</span></span>  
  
-   <span data-ttu-id="d2f34-124">**SYSREMOTE_PROVIDER_TYPES**</span><span class="sxs-lookup"><span data-stu-id="d2f34-124">**SYSREMOTE_PROVIDER_TYPES**</span></span>  
  
-   <span data-ttu-id="d2f34-125">**SYSREMOTE_SCHEMATA**</span><span class="sxs-lookup"><span data-stu-id="d2f34-125">**SYSREMOTE_SCHEMATA**</span></span>  
  
-   <span data-ttu-id="d2f34-126">**SYSREMOTE_STATISTICS**</span><span class="sxs-lookup"><span data-stu-id="d2f34-126">**SYSREMOTE_STATISTICS**</span></span>  
  
-   <span data-ttu-id="d2f34-127">**SYSREMOTE_TABLE_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="d2f34-127">**SYSREMOTE_TABLE_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="d2f34-128">**SYSREMOTE_TABLES**</span><span class="sxs-lookup"><span data-stu-id="d2f34-128">**SYSREMOTE_TABLES**</span></span>  
  
-   <span data-ttu-id="d2f34-129">**SYSREMOTE_VIEWS**</span><span class="sxs-lookup"><span data-stu-id="d2f34-129">**SYSREMOTE_VIEWS**</span></span>  
  
-   <span data-ttu-id="d2f34-130">**syssegments**</span><span class="sxs-lookup"><span data-stu-id="d2f34-130">**syssegments**</span></span>  
  
-   <span data-ttu-id="d2f34-131">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="d2f34-131">**sysxlogins**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="d2f34-132">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="d2f34-132">Corrective Action</span></span>  
 <span data-ttu-id="d2f34-133">Modifique las aplicaciones según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2f34-133">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="d2f34-134">En lugar de</span><span class="sxs-lookup"><span data-stu-id="d2f34-134">Instead of</span></span>|<span data-ttu-id="d2f34-135">Uso</span><span class="sxs-lookup"><span data-stu-id="d2f34-135">Use</span></span>|  
|----------------|---------|  
|<span data-ttu-id="d2f34-136">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="d2f34-136">**sysfulltextnotify**</span></span>|<span data-ttu-id="d2f34-137">La propiedad**TableFulltextPendingChanges** de la función OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="d2f34-137">**TableFulltextPendingChanges** property of the OBJECTPROPERTYEX function.</span></span>|  
|<span data-ttu-id="d2f34-138">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="d2f34-138">**syslocks**</span></span>|<span data-ttu-id="d2f34-139">La vista de administración dinámica**sys.dm_tran_locks** , sp_lock o la vista de compatibilidad **sys.syslockinfo** .</span><span class="sxs-lookup"><span data-stu-id="d2f34-139">**sys.dm_tran_locks** dynamic management view, or sp_lock, or the **sys.syslockinfo** compatibility view.</span></span>|  
|<span data-ttu-id="d2f34-140">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="d2f34-140">**sysproperties**</span></span>|<span data-ttu-id="d2f34-141">La vista de catálogo**sys.extended_properties** o la función **fn_listextendedproperty**</span><span class="sxs-lookup"><span data-stu-id="d2f34-141">**sys.extended_properties** catalog view or the **fn_listextendedproperty** function</span></span>|  
|<span data-ttu-id="d2f34-142">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="d2f34-142">**sysxlogins**</span></span>|<span data-ttu-id="d2f34-143">La vista de catálogo**sys.server_principals** o la vista de compatibilidad **syslogins** .</span><span class="sxs-lookup"><span data-stu-id="d2f34-143">**sys.server_principals** catalog view or **syslogins** compatibility view.</span></span>|  
|<span data-ttu-id="d2f34-144">todas las tablas **spt_**</span><span class="sxs-lookup"><span data-stu-id="d2f34-144">all **spt_** tables</span></span>|<span data-ttu-id="d2f34-145">Ningún reemplazo disponible</span><span class="sxs-lookup"><span data-stu-id="d2f34-145">No replacement available</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2f34-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2f34-146">See Also</span></span>  
 <span data-ttu-id="d2f34-147">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="d2f34-147">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="d2f34-148">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="d2f34-148">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
