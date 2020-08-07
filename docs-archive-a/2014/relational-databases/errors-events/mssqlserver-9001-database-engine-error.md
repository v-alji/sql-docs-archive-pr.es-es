---
title: MSSQLSERVER_9001 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9001 (Database Engine error)
ms.assetid: a54de936-90c6-4845-aa96-29d32f154601
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e61894d0d071fbdb36dcfb77895c46c61d0bbd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747596"
---
# <a name="mssqlserver_9001"></a><span data-ttu-id="ebc64-102">MSSQLSERVER_9001</span><span class="sxs-lookup"><span data-stu-id="ebc64-102">MSSQLSERVER_9001</span></span>
    
## <a name="details"></a><span data-ttu-id="ebc64-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ebc64-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ebc64-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="ebc64-104">Product Name</span></span>|<span data-ttu-id="ebc64-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ebc64-105">SQL Server</span></span>|  
|<span data-ttu-id="ebc64-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ebc64-106">Event ID</span></span>|<span data-ttu-id="ebc64-107">9001</span><span class="sxs-lookup"><span data-stu-id="ebc64-107">9001</span></span>|  
|<span data-ttu-id="ebc64-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="ebc64-108">Event Source</span></span>|<span data-ttu-id="ebc64-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ebc64-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ebc64-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ebc64-110">Component</span></span>|<span data-ttu-id="ebc64-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ebc64-111">SQLEngine</span></span>|  
|<span data-ttu-id="ebc64-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ebc64-112">Symbolic Name</span></span>|<span data-ttu-id="ebc64-113">LOG_NOT_AVAIL</span><span class="sxs-lookup"><span data-stu-id="ebc64-113">LOG_NOT_AVAIL</span></span>|  
|<span data-ttu-id="ebc64-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ebc64-114">Message Text</span></span>|<span data-ttu-id="ebc64-115">El registro de la base de datos '%.\*ls' no está disponible.</span><span class="sxs-lookup"><span data-stu-id="ebc64-115">The log for database '%.\*ls' is not available.</span></span> <span data-ttu-id="ebc64-116">Vea los mensajes de error relacionados en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="ebc64-116">Check the event log for related error messages.</span></span> <span data-ttu-id="ebc64-117">Corrija los errores y reinicie la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ebc64-117">Resolve any errors and restart the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ebc64-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="ebc64-118">Explanation</span></span>  
 <span data-ttu-id="ebc64-119">El registro de la base de datos se dejó sin conexión.</span><span class="sxs-lookup"><span data-stu-id="ebc64-119">The database log was taken offline.</span></span> <span data-ttu-id="ebc64-120">Normalmente esto indica un error grave que requiere reiniciar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ebc64-120">Usually this signifies a catastrophic failure that requires the database to restart.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ebc64-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ebc64-121">User Action</span></span>  
 <span data-ttu-id="ebc64-122">Diagnostique otros errores y reinicie la sesión de SQL Server si aún no se ha reiniciado.</span><span class="sxs-lookup"><span data-stu-id="ebc64-122">Diagnose other errors and restart the instance of SQL Server if it has not already restarted itself.</span></span>  
  
  
