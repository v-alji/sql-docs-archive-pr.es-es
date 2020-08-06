---
title: Ver los destinos de eventos extendidos para los paquetes registrados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events]
- viewing event targets
- extended events [SQL Server], viewing targets
ms.assetid: 4985aa5f-ac99-49f6-852c-9d25916549e9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8e796d141ef943399fc2469c232b34b1956cef3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677804"
---
# <a name="view-the-extended-events-targets-for-registered-packages"></a><span data-ttu-id="430ce-102">Ver los destinos de eventos extendidos de los paquetes registrados</span><span class="sxs-lookup"><span data-stu-id="430ce-102">View the Extended Events Targets for Registered Packages</span></span>
  <span data-ttu-id="430ce-103">Antes de crear una sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events, es útil determinar qué destinos de eventos extendidos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="430ce-103">Before you create a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events session, it is useful to determine what Extended Events targets are available.</span></span> <span data-ttu-id="430ce-104">Esta tarea implica el uso del Editor de consultas en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para realizar el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="430ce-104">This task involves using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to perform the following procedure.</span></span>  
  
 <span data-ttu-id="430ce-105">Una vez finalizadas las instrucciones de este procedimiento, la pestaña **Resultados** del Editor de consultas mostrará las dos columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="430ce-105">After the statements in this procedure finish, the **Results** tab of Query Editor displays the following two columns:</span></span>  
  
-   <span data-ttu-id="430ce-106">package_name</span><span class="sxs-lookup"><span data-stu-id="430ce-106">package_name</span></span>  
  
-   <span data-ttu-id="430ce-107">target_name</span><span class="sxs-lookup"><span data-stu-id="430ce-107">target_name</span></span>  
  
## <a name="to-view-the-extended-events-targets-for-registered-packages-using-query-editor"></a><span data-ttu-id="430ce-108">Para ver los destinos de eventos extendidos para los paquetes registrados mediante el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="430ce-108">To view the Extended Events targets for registered packages using Query Editor</span></span>  
  
-   <span data-ttu-id="430ce-109">En el Editor de consultas, emita las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="430ce-109">In Query Editor, issue the following statements.</span></span>  
  
    ```  
    USE msdb  
    SELECT p.name package_name, o.name target_name  
    FROM sys.dm_xe_objects o  
    JOIN sys.dm_xe_packages p  
         ON o.package_guid = p.guid  
    WHERE o.object_type = 'target'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="430ce-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="430ce-110">See Also</span></span>  
 <span data-ttu-id="430ce-111">[Destinos de SQL Server Extended Events](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="430ce-111">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="430ce-112">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="430ce-112">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span></span>  
 [<span data-ttu-id="430ce-113">sys.dm_xe_packages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="430ce-113">sys.dm_xe_packages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql)  
  
  
