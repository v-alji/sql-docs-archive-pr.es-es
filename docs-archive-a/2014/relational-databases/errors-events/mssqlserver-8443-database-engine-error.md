---
title: MSSQLSERVER_8443 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8443 (Database Engine error)
ms.assetid: a3541b9c-b1a8-4280-add1-275f08696b62
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae02cc0d9e5661f4069884c22bf6eea0697bd2d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747597"
---
# <a name="mssqlserver_8443"></a><span data-ttu-id="540b6-102">MSSQLSERVER_8443</span><span class="sxs-lookup"><span data-stu-id="540b6-102">MSSQLSERVER_8443</span></span>
    
## <a name="details"></a><span data-ttu-id="540b6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="540b6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="540b6-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="540b6-104">Product Name</span></span>|<span data-ttu-id="540b6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="540b6-105">SQL Server</span></span>|  
|<span data-ttu-id="540b6-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="540b6-106">Event ID</span></span>|<span data-ttu-id="540b6-107">8443</span><span class="sxs-lookup"><span data-stu-id="540b6-107">8443</span></span>|  
|<span data-ttu-id="540b6-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="540b6-108">Event Source</span></span>|<span data-ttu-id="540b6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="540b6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="540b6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="540b6-110">Component</span></span>|<span data-ttu-id="540b6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="540b6-111">SQLEngine</span></span>|  
|<span data-ttu-id="540b6-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="540b6-112">Symbolic Name</span></span>|<span data-ttu-id="540b6-113">SB_DIALOG_WO_CONV_GROUP</span><span class="sxs-lookup"><span data-stu-id="540b6-113">SB_DIALOG_WO_CONV_GROUP</span></span>|  
|<span data-ttu-id="540b6-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="540b6-114">Message Text</span></span>|<span data-ttu-id="540b6-115">La conversación con id. '%.\*ls' y el iniciador %d hace referencia a un grupo de conversaciones que falta ('%.\*ls').</span><span class="sxs-lookup"><span data-stu-id="540b6-115">The conversation with ID '%.\*ls' and initiator %d references a missing conversation group '%.\*ls'.</span></span> <span data-ttu-id="540b6-116">Ejecute DBCC CHECKDB para analizar y reparar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="540b6-116">Run DBCC CHECKDB to analyze and repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="540b6-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="540b6-117">Explanation</span></span>  
 <span data-ttu-id="540b6-118">La capa de metadatos devolvió NULL para el grupo de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="540b6-118">The metadata layer returned NULL for the conversation group.</span></span> <span data-ttu-id="540b6-119">La base de datos ha resultado dañada de alguna manera.</span><span class="sxs-lookup"><span data-stu-id="540b6-119">The database has been corrupted in some way.</span></span> <span data-ttu-id="540b6-120">Un posible origen de los daños es un error de disco.</span><span class="sxs-lookup"><span data-stu-id="540b6-120">One possible source of corruption is a disk error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="540b6-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="540b6-121">User Action</span></span>  
 <span data-ttu-id="540b6-122">Ejecute DBCC CHECKDB en el modo de reparación para restaurar la base de datos a un estado coherente.</span><span class="sxs-lookup"><span data-stu-id="540b6-122">Run DBCC CHECKDB in repair mode to bring the database back into a consistent state.</span></span> <span data-ttu-id="540b6-123">Puede que se eliminen mensajes si es necesario para restablecer la coherencia.</span><span class="sxs-lookup"><span data-stu-id="540b6-123">It may delete messages if necessary to restore consistency.</span></span> <span data-ttu-id="540b6-124">Investigue en los registros de errores del sistema para ver si la causa de este error es otro error del sistema.</span><span class="sxs-lookup"><span data-stu-id="540b6-124">Investigate system error logs to see if this error was caused by another failure in the system.</span></span>  
  
  
