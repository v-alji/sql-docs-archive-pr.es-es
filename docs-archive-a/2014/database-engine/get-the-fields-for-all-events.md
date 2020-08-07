---
title: Obtener los campos de todos los eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], getting fields
- xe
ms.assetid: 4e4ee03f-5bca-42ed-a37c-db1c82e3aad2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 01d98e827121a0c47111dd601c6e1772f796849d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746421"
---
# <a name="get-the-fields-for-all-events"></a><span data-ttu-id="233fe-102">Obtener los campos de todos los eventos</span><span class="sxs-lookup"><span data-stu-id="233fe-102">Get the Fields for All Events</span></span>
  <span data-ttu-id="233fe-103">Esta tarea se lleva a cabo con el Editor de consultas en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="233fe-103">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="233fe-104">Una vez finalizadas las instrucciones de este procedimiento, la pestaña **Resultados** del Editor de consultas mostrará las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="233fe-104">After the statements in this procedure finish, the **Results** tab of Query Editor displays the following columns:</span></span>  
  
-   <span data-ttu-id="233fe-105">package_name</span><span class="sxs-lookup"><span data-stu-id="233fe-105">package_name</span></span>  
  
-   <span data-ttu-id="233fe-106">event_name</span><span class="sxs-lookup"><span data-stu-id="233fe-106">event_name</span></span>  
  
-   <span data-ttu-id="233fe-107">event_field</span><span class="sxs-lookup"><span data-stu-id="233fe-107">event_field</span></span>  
  
-   <span data-ttu-id="233fe-108">field_type</span><span class="sxs-lookup"><span data-stu-id="233fe-108">field_type</span></span>  
  
-   <span data-ttu-id="233fe-109">column_type</span><span class="sxs-lookup"><span data-stu-id="233fe-109">column_type</span></span>  
  
 <span data-ttu-id="233fe-110">Puede utilizar la información anterior al configurar sesiones de evento que utilizan el destino de creación de depósitos.</span><span class="sxs-lookup"><span data-stu-id="233fe-110">You can use the preceding information when configuring event sessions that use the bucketing target.</span></span> <span data-ttu-id="233fe-111">Para más información, consulte [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="233fe-111">For more information, see [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="233fe-112">Introducción</span><span class="sxs-lookup"><span data-stu-id="233fe-112">Before you Begin</span></span>  
 <span data-ttu-id="233fe-113">Antes de crear una sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events, resulta útil obtener información sobre los campos asociados a los eventos.</span><span class="sxs-lookup"><span data-stu-id="233fe-113">Before you create a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events session, it is useful to get information about the fields associated with events.</span></span>  
  
## <a name="to-get-the-fields-for-all-events-using-query-editor"></a><span data-ttu-id="233fe-114">Para obtener los campos de todos los eventos mediante el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="233fe-114">To get the fields for all events using Query Editor</span></span>  
  
-   <span data-ttu-id="233fe-115">En el Editor de consultas, emita las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="233fe-115">In Query Editor, issue the following statements.</span></span>  
  
    ```  
    select p.name package_name, o.name event_name, c.name event_field, c.type_name field_type, c.column_type column_type  
    from sys.dm_xe_objects o  
    join sys.dm_xe_packages p  
          on o.package_guid = p.guid  
    join sys.dm_xe_object_columns c  
          on o.name = c.object_name  
    where o.object_type = 'event'  
    order by package_name, event_name  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="233fe-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="233fe-116">See Also</span></span>  
 <span data-ttu-id="233fe-117">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="233fe-117">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span></span>  
 [<span data-ttu-id="233fe-118">sys.dm_xe_packages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="233fe-118">sys.dm_xe_packages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql)  
  
  
