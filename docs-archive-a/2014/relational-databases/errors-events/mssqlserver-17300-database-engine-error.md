---
title: MSSQLSERVER_17300 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17300 (Database Engine error)
ms.assetid: c1d6bfb6-28af-4df6-8087-25807602d282
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f77e39c71901166085d011d6d00f9a4a379bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744730"
---
# <a name="mssqlserver_17300"></a><span data-ttu-id="12c75-102">MSSQLSERVER_17300</span><span class="sxs-lookup"><span data-stu-id="12c75-102">MSSQLSERVER_17300</span></span>
    
## <a name="details"></a><span data-ttu-id="12c75-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="12c75-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="12c75-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="12c75-104">Product Name</span></span>|<span data-ttu-id="12c75-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="12c75-105">SQL Server</span></span>|  
|<span data-ttu-id="12c75-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="12c75-106">Event ID</span></span>|<span data-ttu-id="12c75-107">17300</span><span class="sxs-lookup"><span data-stu-id="12c75-107">17300</span></span>|  
|<span data-ttu-id="12c75-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="12c75-108">Event Source</span></span>|<span data-ttu-id="12c75-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="12c75-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="12c75-110">Componente</span><span class="sxs-lookup"><span data-stu-id="12c75-110">Component</span></span>|<span data-ttu-id="12c75-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="12c75-111">SQLEngine</span></span>|  
|<span data-ttu-id="12c75-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="12c75-112">Symbolic Name</span></span>|<span data-ttu-id="12c75-113">PROC_OUT_OF_SYSTASK_SESSIONS</span><span class="sxs-lookup"><span data-stu-id="12c75-113">PROC_OUT_OF_SYSTASK_SESSIONS</span></span>|  
|<span data-ttu-id="12c75-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="12c75-114">Message Text</span></span>|<span data-ttu-id="12c75-115">SQL Server no pudo ejecutar una nueva tarea de sistema porque la memoria no es suficiente o porque el número de sesiones configuradas supera el máximo permitido en el servidor.</span><span class="sxs-lookup"><span data-stu-id="12c75-115">SQL Server was unable to run a new system task, either because there is insufficient memory or the number of configured sessions exceeds the maximum allowed in the server.</span></span> <span data-ttu-id="12c75-116">Compruebe que el servidor tiene la memoria necesaria.</span><span class="sxs-lookup"><span data-stu-id="12c75-116">Verify that the server has adequate memory.</span></span> <span data-ttu-id="12c75-117">Utilice sp_configure con la opción 'user connections' para comprobar el número máximo de conexiones de usuario permitido.</span><span class="sxs-lookup"><span data-stu-id="12c75-117">Use sp_configure with option 'user connections' to check the maximum number of user connections allowed.</span></span> <span data-ttu-id="12c75-118">Utilice sys.dm_exec_sessions para comprobar el número de sesiones actual, incluidos los procesos de usuario.</span><span class="sxs-lookup"><span data-stu-id="12c75-118">Use sys.dm_exec_sessions to check the current number of sessions, including user processes.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="12c75-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="12c75-119">Explanation</span></span>  
 <span data-ttu-id="12c75-120">Se ha producido un error en un intento de ejecutar una nueva tarea de sistema porque la memoria no es suficiente o porque se ha superado el número de sesiones configuradas en el servidor.</span><span class="sxs-lookup"><span data-stu-id="12c75-120">An attempt to run a new system task failed because of insufficient memory or because the number of configured sessions in the server was exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="12c75-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="12c75-121">User Action</span></span>  
 <span data-ttu-id="12c75-122">Compruebe que el servidor tiene memoria suficiente.</span><span class="sxs-lookup"><span data-stu-id="12c75-122">Verify that the server has enough memory.</span></span> <span data-ttu-id="12c75-123">Compruebe el número actual de tareas de sistema utilizando sys.dm_exec_sessions, y compruebe el valor configurado de conexiones de usuario máximas utilizando sp_configure.</span><span class="sxs-lookup"><span data-stu-id="12c75-123">Verify the current number of system tasks by using sys.dm_exec_sessions, and verify the configured value of maximum user connections by using sp_configure.</span></span>  
  
 <span data-ttu-id="12c75-124">Realice las siguientes tareas, según corresponda:</span><span class="sxs-lookup"><span data-stu-id="12c75-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="12c75-125">Agregue más memoria al servidor.</span><span class="sxs-lookup"><span data-stu-id="12c75-125">Add more memory to the server.</span></span>  
  
-   <span data-ttu-id="12c75-126">Finalice una o más sesiones.</span><span class="sxs-lookup"><span data-stu-id="12c75-126">Terminate one or more sessions.</span></span>  
  
-   <span data-ttu-id="12c75-127">Aumente el número máximo de conexiones de usuario permitido en el servidor.</span><span class="sxs-lookup"><span data-stu-id="12c75-127">Increase the maximum number of user connections allowed on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c75-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12c75-128">See Also</span></span>  
 <span data-ttu-id="12c75-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12c75-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="12c75-130">[Opciones de configuración de servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="12c75-130">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="12c75-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12c75-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span></span>  
 <span data-ttu-id="12c75-132">[Establecer la opción de configuración del servidor conexiones de usuario](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="12c75-132">[Configure the user connections Server Configuration Option](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="12c75-133">KILL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="12c75-133">KILL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/kill-transact-sql)  
  
  
