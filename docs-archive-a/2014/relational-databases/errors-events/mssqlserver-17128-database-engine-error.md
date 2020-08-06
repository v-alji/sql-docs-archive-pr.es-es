---
title: MSSQLSERVER_17128 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17128 (Database Engine error)
ms.assetid: 7b15a5e6-fd41-47ce-ba87-54f72acea4bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e08c668acd0a8b2decb14da338b8d1f1e650de5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745318"
---
# <a name="mssqlserver_17128"></a><span data-ttu-id="7d897-102">MSSQLSERVER_17128</span><span class="sxs-lookup"><span data-stu-id="7d897-102">MSSQLSERVER_17128</span></span>
    
## <a name="details"></a><span data-ttu-id="7d897-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7d897-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d897-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7d897-104">Product Name</span></span>|<span data-ttu-id="7d897-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d897-105">SQL Server</span></span>|  
|<span data-ttu-id="7d897-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7d897-106">Event ID</span></span>|<span data-ttu-id="7d897-107">17128</span><span class="sxs-lookup"><span data-stu-id="7d897-107">17128</span></span>|  
|<span data-ttu-id="7d897-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7d897-108">Event Source</span></span>|<span data-ttu-id="7d897-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7d897-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7d897-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7d897-110">Component</span></span>|<span data-ttu-id="7d897-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7d897-111">SQLEngine</span></span>|  
|<span data-ttu-id="7d897-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7d897-112">Symbolic Name</span></span>|<span data-ttu-id="7d897-113">INIT_NOBUFSPACE</span><span class="sxs-lookup"><span data-stu-id="7d897-113">INIT_NOBUFSPACE</span></span>|  
|<span data-ttu-id="7d897-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7d897-114">Message Text</span></span>|<span data-ttu-id="7d897-115">initdata: memoria insuficiente para los búferes del kernel.</span><span class="sxs-lookup"><span data-stu-id="7d897-115">initdata: No memory for kernel buffers.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7d897-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="7d897-116">Explanation</span></span>  
 <span data-ttu-id="7d897-117">Se ha producido un error en las reservas o las asignaciones de memoria iniciales del grupo de búferes, y SQL Server se cierra.</span><span class="sxs-lookup"><span data-stu-id="7d897-117">The buffer pool's initial memory allocations or reservations have failed, and SQL Server exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d897-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7d897-118">User Action</span></span>  
 <span data-ttu-id="7d897-119">Normalmente, se debe a que SQL Server se inicia en un equipo sumamente pequeño, mucho menor de lo que determinan los requisitos mínimos del sistema.</span><span class="sxs-lookup"><span data-stu-id="7d897-119">Usually caused by starting SQL Server on an extremely small machine - far smaller than the minimum system requirements.</span></span>  
  
  
