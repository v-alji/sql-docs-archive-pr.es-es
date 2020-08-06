---
title: MSSQLSERVER_5245 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5245 (Database Engine error)
ms.assetid: 6005c9ec-ccdd-4def-9eb4-37cdb599ddb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f98c831642580587552bf60c604d84c38fffca8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675878"
---
# <a name="mssqlserver_5245"></a><span data-ttu-id="e8509-102">MSSQLSERVER_5245</span><span class="sxs-lookup"><span data-stu-id="e8509-102">MSSQLSERVER_5245</span></span>
    
## <a name="details"></a><span data-ttu-id="e8509-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e8509-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8509-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="e8509-104">Product Name</span></span>|<span data-ttu-id="e8509-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8509-105">SQL Server</span></span>|  
|<span data-ttu-id="e8509-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e8509-106">Event ID</span></span>|<span data-ttu-id="e8509-107">5245</span><span class="sxs-lookup"><span data-stu-id="e8509-107">5245</span></span>|  
|<span data-ttu-id="e8509-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="e8509-108">Event Source</span></span>|<span data-ttu-id="e8509-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e8509-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e8509-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e8509-110">Component</span></span>|<span data-ttu-id="e8509-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e8509-111">SQLEngine</span></span>|  
|<span data-ttu-id="e8509-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e8509-112">Symbolic Name</span></span>|<span data-ttu-id="e8509-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="e8509-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span></span>|  
|<span data-ttu-id="e8509-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e8509-114">Message Text</span></span>|<span data-ttu-id="e8509-115">Id. de objeto O_ID (objeto "NAME"): DBCC no pudo obtener un bloqueo en este objeto porque se superó el tiempo de espera de la solicitud de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e8509-115">Object ID O_ID (object 'NAME'): DBCC could not obtain a lock on this object because the lock request time-out period was exceeded.</span></span> <span data-ttu-id="e8509-116">Este objeto ha sido omitido y no se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="e8509-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e8509-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="e8509-117">Explanation</span></span>  
 <span data-ttu-id="e8509-118">Se produjo un tiempo de espera de bloqueo mientras DBCC estaba esperando un bloqueo de tabla para el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="e8509-118">A lock time-out occurred while DBCC was waiting on a table lock for the specified object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8509-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e8509-119">User Action</span></span>  
 <span data-ttu-id="e8509-120">Vuelva a ejecutar el comando DBCC.</span><span class="sxs-lookup"><span data-stu-id="e8509-120">Rerun the DBCC command.</span></span>  
  
  
