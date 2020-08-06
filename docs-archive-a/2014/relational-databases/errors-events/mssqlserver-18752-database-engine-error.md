---
title: MSSQLSERVER_18752 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18752 (Database Engine error)
ms.assetid: 234c58d8-7a1e-4b07-a64b-32a311527980
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a463e4019875f4a233ae2920f32bc2252376a41c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672072"
---
# <a name="mssqlserver_18752"></a><span data-ttu-id="b6fc9-102">MSSQLSERVER_18752</span><span class="sxs-lookup"><span data-stu-id="b6fc9-102">MSSQLSERVER_18752</span></span>
    
## <a name="details"></a><span data-ttu-id="b6fc9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b6fc9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6fc9-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b6fc9-104">Product Name</span></span>|<span data-ttu-id="b6fc9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b6fc9-105">SQL Server</span></span>|  
|<span data-ttu-id="b6fc9-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b6fc9-106">Event ID</span></span>|<span data-ttu-id="b6fc9-107">18752</span><span class="sxs-lookup"><span data-stu-id="b6fc9-107">18752</span></span>|  
|<span data-ttu-id="b6fc9-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b6fc9-108">Event Source</span></span>|<span data-ttu-id="b6fc9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b6fc9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b6fc9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b6fc9-110">Component</span></span>|<span data-ttu-id="b6fc9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b6fc9-111">SQLEngine</span></span>|  
|<span data-ttu-id="b6fc9-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b6fc9-112">Symbolic Name</span></span>|<span data-ttu-id="b6fc9-113">REPL_INUSE</span><span class="sxs-lookup"><span data-stu-id="b6fc9-113">REPL_INUSE</span></span>|  
|<span data-ttu-id="b6fc9-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b6fc9-114">Message Text</span></span>|<span data-ttu-id="b6fc9-115">El Agente de registro del LOG y los procedimientos relacionados con el registro (sp_repldone, sp_replcmds y sp_replshowcmds) solamente pueden conectarse a la base de datos de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-115">Only one Log Reader Agent or log-related procedure (sp_repldone, sp_replcmds, and sp_replshowcmds) can connect to a database at a time.</span></span> <span data-ttu-id="b6fc9-116">Si ejecutó un procedimiento relacionado con el registro, quite la conexión mediante la cual se ejecutó el procedimiento o ejecute sp_replflush en esa conexión antes de iniciar el Agente de registro del LOG o de ejecutar otro procedimiento relacionado con el registro.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-116">If you executed a log-related procedure, drop the connection over which the procedure was executed or execute sp_replflush over that connection before starting the Log Reader Agent or executing another log-related procedure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b6fc9-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="b6fc9-117">Explanation</span></span>  
 <span data-ttu-id="b6fc9-118">Solo un Agente de registro del LOG o un procedimiento relacionado con el registro pueden conectarse a una base de datos a la vez.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-118">Only one Log Reader agent or log-related procedure can connect to a database at a time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b6fc9-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b6fc9-119">User Action</span></span>  
 <span data-ttu-id="b6fc9-120">Asegúrese de que ningún otro lector del registro se esté ejecutando para la misma base de datos de publicación y que ninguna otra conexión activa se había ejecutado sp_replcmds/sp_repltrans/sp_repldone previamente sin ejecutarse sp_replflush después o desconectarse.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-120">Make sure no other logreader is running for the same publishing database, and no other active connection had previously run sp_replcmds/sp_repltrans/sp_repldone without running sp_replflush afterwards or disconnecting.</span></span>  
  
  
