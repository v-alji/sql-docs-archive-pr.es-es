---
title: Quitar referencias a procedimientos almacenados del sistema desusados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system stored procedures [SQL Server]
- system stored procedures [SQL Server]
ms.assetid: 487d24fc-41d5-495e-843c-0ac974ec472f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65e7da666beaf84050dd8d60caf4cac5bfc013c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747894"
---
# <a name="remove-references-to-deprecated-system-stored-procedures"></a><span data-ttu-id="307c0-102">Quitar referencias a procedimientos almacenados del sistema desusados</span><span class="sxs-lookup"><span data-stu-id="307c0-102">Remove references to deprecated system stored procedures</span></span>
  <span data-ttu-id="307c0-103">El Asesor de actualizaciones ha detectado instrucciones que hacen referencia a procedimientos almacenados del sistema y a procedimientos almacenados extendidos no documentados que ya no están disponibles en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="307c0-103">Upgrade Advisor detected statements that reference undocumented system stored procedures and extended stored procedures that are no longer available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="307c0-104">Las instrucciones que hagan referencia a dichos objetos producirán un error.</span><span class="sxs-lookup"><span data-stu-id="307c0-104">Statements that reference these objects will fail.</span></span> <span data-ttu-id="307c0-105">No utilice objetos de sistema o API no documentados, ya que en futuras versiones podría cambiar o quitarse esta funcionalidad sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="307c0-105">Do not use undocumented system objects or APIs as the functionality might change or be removed without notification in a future release.</span></span>  
  
## <a name="component"></a><span data-ttu-id="307c0-106">Componente</span><span class="sxs-lookup"><span data-stu-id="307c0-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="307c0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="307c0-107">Description</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="307c0-108">Procedimientos almacenados del sistema documentados</span><span class="sxs-lookup"><span data-stu-id="307c0-108">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="307c0-109">Se han quitado los siguientes procedimientos almacenados del sistema documentados:</span><span class="sxs-lookup"><span data-stu-id="307c0-109">The following documented system stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="307c0-110">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="307c0-110">sp_addalias</span></span>  
  
-   <span data-ttu-id="307c0-111">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="307c0-111">sp_addgroup</span></span>  
  
-   <span data-ttu-id="307c0-112">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="307c0-112">sp_changegroup</span></span>  
  
-   <span data-ttu-id="307c0-113">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="307c0-113">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="307c0-114">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="307c0-114">sp_helpgroup</span></span>  
  
### <a name="undocumented-system-stored-procedures"></a><span data-ttu-id="307c0-115">Procedimientos almacenados del sistema no documentados</span><span class="sxs-lookup"><span data-stu-id="307c0-115">Undocumented System Stored Procedures</span></span>  
 <span data-ttu-id="307c0-116">Se han quitado los siguientes procedimientos almacenados del sistema y procedimientos almacenados extendidos no documentados:</span><span class="sxs-lookup"><span data-stu-id="307c0-116">The following undocumented system stored procedures and extended stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="307c0-117">sp_articlesynctranprocs</span><span class="sxs-lookup"><span data-stu-id="307c0-117">sp_articlesynctranprocs</span></span>  
  
-   <span data-ttu-id="307c0-118">sp_diskdefault</span><span class="sxs-lookup"><span data-stu-id="307c0-118">sp_diskdefault</span></span>  
  
-   <span data-ttu-id="307c0-119">sp_EventLog</span><span class="sxs-lookup"><span data-stu-id="307c0-119">sp_EventLog</span></span>  
  
-   <span data-ttu-id="307c0-120">sp_GetMBCSCharLen</span><span class="sxs-lookup"><span data-stu-id="307c0-120">sp_GetMBCSCharLen</span></span>  
  
-   <span data-ttu-id="307c0-121">sp_helplog</span><span class="sxs-lookup"><span data-stu-id="307c0-121">sp_helplog</span></span>  
  
-   <span data-ttu-id="307c0-122">sp_helpsql</span><span class="sxs-lookup"><span data-stu-id="307c0-122">sp_helpsql</span></span>  
  
-   <span data-ttu-id="307c0-123">sp_IsMBCSLeadByte</span><span class="sxs-lookup"><span data-stu-id="307c0-123">sp_IsMBCSLeadByte</span></span>  
  
-   <span data-ttu-id="307c0-124">sp_lock2</span><span class="sxs-lookup"><span data-stu-id="307c0-124">sp_lock2</span></span>  
  
-   <span data-ttu-id="307c0-125">sp_MSget_current_activity</span><span class="sxs-lookup"><span data-stu-id="307c0-125">sp_MSget_current_activity</span></span>  
  
-   <span data-ttu-id="307c0-126">sp_MSset_current_activity</span><span class="sxs-lookup"><span data-stu-id="307c0-126">sp_MSset_current_activity</span></span>  
  
-   <span data-ttu-id="307c0-127">sp_MSobjessearch</span><span class="sxs-lookup"><span data-stu-id="307c0-127">sp_MSobjessearch</span></span>  
  
-   <span data-ttu-id="307c0-128">xp_enum_ActiveScriptEngines</span><span class="sxs-lookup"><span data-stu-id="307c0-128">xp_enum_ActiveScriptEngines</span></span>  
  
-   <span data-ttu-id="307c0-129">xp_eventlog</span><span class="sxs-lookup"><span data-stu-id="307c0-129">xp_eventlog</span></span>  
  
-   <span data-ttu-id="307c0-130">xp_GetAdminGroupName</span><span class="sxs-lookup"><span data-stu-id="307c0-130">xp_GetAdminGroupName</span></span>  
  
-   <span data-ttu-id="307c0-131">xp_GetFileDetails</span><span class="sxs-lookup"><span data-stu-id="307c0-131">xp_GetFileDetails</span></span>  
  
-   <span data-ttu-id="307c0-132">xp_GetLocalSystemAccountName</span><span class="sxs-lookup"><span data-stu-id="307c0-132">xp_GetLocalSystemAccountName</span></span>  
  
-   <span data-ttu-id="307c0-133">xp_IsNTAdmin</span><span class="sxs-lookup"><span data-stu-id="307c0-133">xp_IsNTAdmin</span></span>  
  
-   <span data-ttu-id="307c0-134">xp_MSLocalSystem</span><span class="sxs-lookup"><span data-stu-id="307c0-134">xp_MSLocalSystem</span></span>  
  
-   <span data-ttu-id="307c0-135">xp_MSnt2000</span><span class="sxs-lookup"><span data-stu-id="307c0-135">xp_MSnt2000</span></span>  
  
-   <span data-ttu-id="307c0-136">xp_MSplatform</span><span class="sxs-lookup"><span data-stu-id="307c0-136">xp_MSplatform</span></span>  
  
-   <span data-ttu-id="307c0-137">xp_SetSecurity</span><span class="sxs-lookup"><span data-stu-id="307c0-137">xp_SetSecurity</span></span>  
  
-   <span data-ttu-id="307c0-138">xp_varbintohexstr</span><span class="sxs-lookup"><span data-stu-id="307c0-138">xp_varbintohexstr</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="307c0-139">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="307c0-139">Corrective Action</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="307c0-140">Procedimientos almacenados del sistema documentados</span><span class="sxs-lookup"><span data-stu-id="307c0-140">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="307c0-141">Modifique las aplicaciones según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="307c0-141">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="307c0-142">En lugar de</span><span class="sxs-lookup"><span data-stu-id="307c0-142">Instead of</span></span>|<span data-ttu-id="307c0-143">Haga esto</span><span class="sxs-lookup"><span data-stu-id="307c0-143">Do this</span></span>|  
|----------------|-------------|  
|<span data-ttu-id="307c0-144">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="307c0-144">sp_addalias</span></span>|<span data-ttu-id="307c0-145">Reemplace los alias por una combinación de cuentas de usuario y roles de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="307c0-145">Replace aliases with a combination of user accounts and database roles.</span></span> <span data-ttu-id="307c0-146">Para obtener más información, vea "CREATE USER (Transact-SQL)" y "CREATE ROLE (Transact-SQL)" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="307c0-146">For more information, see "CREATE USER (Transact-SQL)" and "CREATE ROLE (Transact-SQL)" in SQL Server Books Online.</span></span> <span data-ttu-id="307c0-147">Quite los alias de las bases de datos actualizadas usando sp_dropalias.</span><span class="sxs-lookup"><span data-stu-id="307c0-147">Remove aliases in upgraded databases by using sp_dropalias.</span></span>|  
|<span data-ttu-id="307c0-148">sp_addgroupsp_changegroup</span><span class="sxs-lookup"><span data-stu-id="307c0-148">sp_addgroupsp_changegroup</span></span><br /><br /> <span data-ttu-id="307c0-149">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="307c0-149">sp_dropgroup</span></span><br /><br /> <span data-ttu-id="307c0-150">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="307c0-150">sp_helpgroup</span></span>|<span data-ttu-id="307c0-151">Utilice roles.</span><span class="sxs-lookup"><span data-stu-id="307c0-151">Use roles.</span></span> <span data-ttu-id="307c0-152">Para obtener más información, vea "Roles de nivel de servidor" y "Roles de nivel de base de datos" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="307c0-152">For more information, see "Server-Level Roles" and "Database-Level Roles" in SQL Server Books Online.</span></span>|  
  
### <a name="undocmented-system-stored-procedures"></a><span data-ttu-id="307c0-153">Procedimientos almacenados del sistema Undocmented</span><span class="sxs-lookup"><span data-stu-id="307c0-153">Undocmented System Stored Procedures</span></span>  
 <span data-ttu-id="307c0-154">Puede crear procedimientos almacenados de CLR con una funcionalidad equivalente para reemplazar a los procedimientos almacenados del sistema no documentados.</span><span class="sxs-lookup"><span data-stu-id="307c0-154">You can create CLR stored procedures with equivalent functionality to replace the undocumented system stored procedures.</span></span> <span data-ttu-id="307c0-155">Para obtener más información, consulte el tema "Procedimientos almacenados del CLR" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="307c0-155">For more information, see the topic "CLR Stored Procedures" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307c0-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="307c0-156">See Also</span></span>  
 <span data-ttu-id="307c0-157">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="307c0-157">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="307c0-158">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="307c0-158">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
