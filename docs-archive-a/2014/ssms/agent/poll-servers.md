---
title: Sondear servidores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- target servers [SQL Server], polling interval
- polling master servers [SQL Server]
- server polling [SQL Server]
- master servers [SQL Server], polling
- polling interval [SQL Server]
ms.assetid: 96f5fd43-3edd-4418-9dd0-4d34e618890e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6370e53083d2cf818e8c8b09752d49e092755a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674531"
---
# <a name="poll-servers"></a><span data-ttu-id="c2c3a-102">Sondear servidores</span><span class="sxs-lookup"><span data-stu-id="c2c3a-102">Poll Servers</span></span>
  <span data-ttu-id="c2c3a-103">Cuando se implementa la administración multiservidor, los servidores de destino se ponen en contacto periódicamente con el servidor maestro para cargar información sobre los trabajos que se han ejecutado y descargar nuevos trabajos.</span><span class="sxs-lookup"><span data-stu-id="c2c3a-103">When multiserver administration is implemented, target servers periodically contact the master server to upload information on jobs that have been executed, and download new jobs.</span></span> <span data-ttu-id="c2c3a-104">El proceso de ponerse en contacto con el servidor maestro se denomina *sondeo de servidor* y tiene lugar a *intervalos de sondeo*regulares.</span><span class="sxs-lookup"><span data-stu-id="c2c3a-104">The process of contacting the master server is called *server polling,* which takes place at regular *polling intervals.*</span></span>  
  
## <a name="polling-intervals"></a><span data-ttu-id="c2c3a-105">Intervalos de sondeo</span><span class="sxs-lookup"><span data-stu-id="c2c3a-105">Polling Intervals</span></span>  
 <span data-ttu-id="c2c3a-106">El intervalo de sondeo (de manera predeterminada un minuto) controla la frecuencia con la que el servidor de destino se conecta al servidor maestro para descargar instrucciones y cargar los resultados de la ejecución de trabajos.</span><span class="sxs-lookup"><span data-stu-id="c2c3a-106">The polling interval (one minute by default) controls how frequently the target server connects to the master server to download instructions and upload the results of job execution.</span></span>  
  
 <span data-ttu-id="c2c3a-107">Cuando un servidor de destino sondea el servidor maestro, lee las operaciones asignadas al servidor de destino en la tabla **sysdownloadlist** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="c2c3a-107">When a target server polls the master server, it reads the operations assigned to the target server from the **sysdownloadlist** table in the **msdb** database.</span></span> <span data-ttu-id="c2c3a-108">Estas operaciones controlan trabajos multiservidor y diversos aspectos del comportamiento del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="c2c3a-108">These operations control multiserver jobs and various aspects of the behavior of a target server.</span></span> <span data-ttu-id="c2c3a-109">Algunos ejemplos de operaciones son eliminar, insertar e iniciar trabajos, y actualizar el intervalo de sondeo de un servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="c2c3a-109">Examples of operations include deleting a job, inserting a job, starting a job, and updating the polling interval of a target server.</span></span>  
  
 <span data-ttu-id="c2c3a-110">Las operaciones se exponen en la tabla **sysdownloadlist** de una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="c2c3a-110">Operations are posted to the **sysdownloadlist** table in either of the following ways:</span></span>  
  
-   <span data-ttu-id="c2c3a-111">Explícitamente mediante el procedimiento almacenado **sp_post_msx_operation** .</span><span class="sxs-lookup"><span data-stu-id="c2c3a-111">Explicitly by using the **sp_post_msx_operation** stored procedure.</span></span>  
  
-   <span data-ttu-id="c2c3a-112">Implícitamente mediante otros procedimientos almacenados de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c2c3a-112">Implicitly by using other job stored procedures.</span></span>  
  
 <span data-ttu-id="c2c3a-113">Si utiliza procedimientos almacenados de trabajo para modificar pasos de trabajos o programaciones de trabajos multiservidor, o bien Objetos de administración distribuida de SQL (SQL-DMO) para controlar trabajos multiservidor, utilice este comando después de modificar los pasos o las programaciones de un trabajo multiservidor:</span><span class="sxs-lookup"><span data-stu-id="c2c3a-113">If you use job stored procedures to modify multiserver job schedules or job steps, or SQL Distributed Management Objects (SQL-DMO) to control multiserver jobs, issue the following command after modifying a multiserver job's steps or schedules:</span></span>  
  
```  
EXECUTE msdb.dbo.sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="c2c3a-114">Utilice este comando para mantener sincronizados los servidores de destino con la definición del trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="c2c3a-114">Issue this command keeps the target servers synchronized with the current job definition.</span></span>  
  
 <span data-ttu-id="c2c3a-115">No es necesario exponer explícitamente las operaciones si utiliza:</span><span class="sxs-lookup"><span data-stu-id="c2c3a-115">You do not have to post operations explicitly if you use the following:</span></span>  
  
-   <span data-ttu-id="c2c3a-116">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para controlar trabajos multiservidor.</span><span class="sxs-lookup"><span data-stu-id="c2c3a-116">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to control multiserver jobs.</span></span>  
  
-   <span data-ttu-id="c2c3a-117">Procedimientos almacenados de trabajo que no modifican pasos de trabajos ni programaciones de trabajos.</span><span class="sxs-lookup"><span data-stu-id="c2c3a-117">Job stored procedures that do not modify job schedules or job steps.</span></span>  
  
 <span data-ttu-id="c2c3a-118">**Para forzar que un servidor de destino sondee el servidor maestro**</span><span class="sxs-lookup"><span data-stu-id="c2c3a-118">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="c2c3a-119">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c2c3a-119">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="c2c3a-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c2c3a-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="c2c3a-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2c3a-121">See Also</span></span>  
 [<span data-ttu-id="c2c3a-122">Administrar eventos</span><span class="sxs-lookup"><span data-stu-id="c2c3a-122">Manage Events</span></span>](manage-events.md)  
  
  
