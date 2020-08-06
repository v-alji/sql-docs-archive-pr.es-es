---
title: MSSQLSERVER_21871 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21871 (Database Engine error)
ms.assetid: d3215378-9282-444f-a18b-00b96fd0133d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f26211da21829a0a898dfb36ff9fefd453c7ad44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745779"
---
# <a name="mssqlserver_21871"></a><span data-ttu-id="ddfb5-102">MSSQLSERVER_21871</span><span class="sxs-lookup"><span data-stu-id="ddfb5-102">MSSQLSERVER_21871</span></span>
    
## <a name="details"></a><span data-ttu-id="ddfb5-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ddfb5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddfb5-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="ddfb5-104">Product Name</span></span>|<span data-ttu-id="ddfb5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddfb5-105">SQL Server</span></span>|  
|<span data-ttu-id="ddfb5-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ddfb5-106">Event ID</span></span>|<span data-ttu-id="ddfb5-107">21871</span><span class="sxs-lookup"><span data-stu-id="ddfb5-107">21871</span></span>|  
|<span data-ttu-id="ddfb5-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="ddfb5-108">Event Source</span></span>|<span data-ttu-id="ddfb5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ddfb5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ddfb5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ddfb5-110">Component</span></span>|<span data-ttu-id="ddfb5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ddfb5-111">SQLEngine</span></span>|  
|<span data-ttu-id="ddfb5-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ddfb5-112">Symbolic Name</span></span>|<span data-ttu-id="ddfb5-113">SQLErrorNum21871</span><span class="sxs-lookup"><span data-stu-id="ddfb5-113">SQLErrorNum21871</span></span>|  
|<span data-ttu-id="ddfb5-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ddfb5-114">Message Text</span></span>|<span data-ttu-id="ddfb5-115">El publicador %s de la base de datos %s no ha sido redirigido.</span><span class="sxs-lookup"><span data-stu-id="ddfb5-115">Publisher %s of database %s has not been redirected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ddfb5-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ddfb5-116">Explanation</span></span>  
 <span data-ttu-id="ddfb5-117">`sp_validate_replica_hosts_as_publishers` busca en la tabla MSredirected_publishers en la base de datos de distribución una entrada para el publicador identificado y la base de datos del publicador.</span><span class="sxs-lookup"><span data-stu-id="ddfb5-117">`sp_validate_replica_hosts_as_publishers` checks the table MSredirected_publishers in the distribution database for an entry for the identified publisher and publisher database.</span></span>  <span data-ttu-id="ddfb5-118">`sp_validate_replica_hosts_as_publishers` devuelve el error 21871 cuando no se encuentra ninguna entrada.</span><span class="sxs-lookup"><span data-stu-id="ddfb5-118">`sp_validate_replica_hosts_as_publishers` returns error 21871 when no entry is found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ddfb5-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ddfb5-119">User Action</span></span>  
 <span data-ttu-id="ddfb5-120">`sp_validate_replica_hosts_as_publishers` solo es relevante para los publicadores redirigidos.</span><span class="sxs-lookup"><span data-stu-id="ddfb5-120">`sp_validate_replica_hosts_as_publishers` is only relevant for redirected publishers.</span></span> <span data-ttu-id="ddfb5-121">Si la base de datos del publicador es miembro de un grupo de disponibilidad, use el procedimiento almacenado `sp_redirect_publisher` para asociar el publicador y la base de datos del publicador con el nombre de escucha de grupo de disponibilidad del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="ddfb5-121">If the publisher database is a member of an availability group, use the stored procedure `sp_redirect_publisher` to associate the publisher and publisher database with the Availability Group Listener Name of the availability group.</span></span>  
  
  
