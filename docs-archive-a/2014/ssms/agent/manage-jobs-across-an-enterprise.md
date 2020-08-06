---
title: Administrar trabajos en una empresa | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver job management [SQL Server]
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
- target servers [SQL Server], job changes
ms.assetid: 4fe7f6c6-f89b-4430-979c-4994a5dcf7a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 385435302b2e987c86afb17eaebf90e91bc93e56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671344"
---
# <a name="manage-jobs-across-an-enterprise"></a><span data-ttu-id="e5fa8-102">Administrar trabajos en una empresa</span><span class="sxs-lookup"><span data-stu-id="e5fa8-102">Manage Jobs Across an Enterprise</span></span>
  <span data-ttu-id="e5fa8-103">Si realiza cambios en definiciones de trabajos multiservidor fuera [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] de, debe publicar los cambios en la lista de descarga para que los servidores de destino puedan volver a descargar el trabajo actualizado.</span><span class="sxs-lookup"><span data-stu-id="e5fa8-103">If you make changes to multiserver job definitions outside [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must post the changes to the download list so that target servers can download the updated job again.</span></span> <span data-ttu-id="e5fa8-104">Para asegurarse de que los servidores de destino tienen las definiciones de trabajos actuales, exponga una instrucción INSERT después de actualizar el trabajo multiservidor, como se explica a continuación:</span><span class="sxs-lookup"><span data-stu-id="e5fa8-104">To ensure that target servers have current job definitions, post an INSERT instruction after you update the multiserver job, as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="e5fa8-105">Para notificar a los servidores de destino de que se ha modificado un trabajo multiservidor, debe invocar el comando anterior después de utilizar uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="e5fa8-105">To notify target servers that a multiserver job has been modified, you must invoke the preceding command after using any of the following procedures:</span></span>  
  
-   [<span data-ttu-id="e5fa8-106">sp_add_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e5fa8-106">sp_add_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="e5fa8-107">sp_update_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e5fa8-107">sp_update_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql)  
  
-   [<span data-ttu-id="e5fa8-108">sp_delete_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e5fa8-108">sp_delete_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql)  
  
-   [<span data-ttu-id="e5fa8-109">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5fa8-109">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="e5fa8-110">sp_detach_schedule &#40;&#41;de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5fa8-110">sp_detach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-schedule-transact-sql)  
  
    > [!NOTE]  
    >  <span data-ttu-id="e5fa8-111">No es necesario llamar a **sp_post_msx_operation** después de llamar a **sp_update_job** o **sp_delete_job**, ya que estos procedimientos almacenados exponen automáticamente los cambios necesarios en la lista de descarga.</span><span class="sxs-lookup"><span data-stu-id="e5fa8-111">It is not necessary to call **sp_post_msx_operation** after you call **sp_update_job** or **sp_delete_job**, because these stored procedures post the required changes to the download list automatically.</span></span>  
  
 <span data-ttu-id="e5fa8-112">A continuación se muestran tareas comunes para la administración de trabajos en una empresa:</span><span class="sxs-lookup"><span data-stu-id="e5fa8-112">The following are common tasks for managing jobs across an enterprise:</span></span>  
  
 <span data-ttu-id="e5fa8-113">**Para comprobar el estado de un servidor de destino**</span><span class="sxs-lookup"><span data-stu-id="e5fa8-113">**To check the status of a target server**</span></span>  
  
-   [<span data-ttu-id="e5fa8-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5fa8-114">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-targetserver-transact-sql)  
  
-   [<span data-ttu-id="e5fa8-115">Objetos de administración de SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="e5fa8-115">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="e5fa8-116">**Para modificar los servidores de destino para un trabajo**</span><span class="sxs-lookup"><span data-stu-id="e5fa8-116">**To change the target servers for a job**</span></span>  
  
-   [<span data-ttu-id="e5fa8-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5fa8-117">SQL Server Management Studio</span></span>](modify-the-target-servers-for-a-job.md)  
  
-   [<span data-ttu-id="e5fa8-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5fa8-118">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
-   [<span data-ttu-id="e5fa8-119">Objetos de administración de SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="e5fa8-119">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="e5fa8-120">**Para modificar la ubicación de un servidor de destino**</span><span class="sxs-lookup"><span data-stu-id="e5fa8-120">**To change the location of a target server**</span></span>  
  
-   [<span data-ttu-id="e5fa8-121">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5fa8-121">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="e5fa8-122">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5fa8-122">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)  
  
-   [<span data-ttu-id="e5fa8-123">Objetos de administración de SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="e5fa8-123">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="e5fa8-124">**Para sincronizar los relojes de los servidores de destino**</span><span class="sxs-lookup"><span data-stu-id="e5fa8-124">**To synchronize target server clocks**</span></span>  
  
-   [<span data-ttu-id="e5fa8-125">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5fa8-125">SQL Server Management Studio</span></span>](synchronize-target-server-clocks-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="e5fa8-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5fa8-126">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql)  
  
 <span data-ttu-id="e5fa8-127">**Para forzar que un servidor de destino sondee el servidor maestro**</span><span class="sxs-lookup"><span data-stu-id="e5fa8-127">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="e5fa8-128">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5fa8-128">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="e5fa8-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5fa8-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="e5fa8-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5fa8-130">See Also</span></span>  
 [<span data-ttu-id="e5fa8-131">Administrar eventos</span><span class="sxs-lookup"><span data-stu-id="e5fa8-131">Manage Events</span></span>](manage-events.md)  
  
  
