---
title: MSSQL_ENG020598 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020598 error
ms.assetid: 1c3032f2-23d1-4ead-94ee-16ac4d75cd0c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cef26001c353dea94ec9b658dfb38285231bc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745213"
---
# <a name="mssql_eng020598"></a><span data-ttu-id="013c7-102">MSSQL_ENG020598</span><span class="sxs-lookup"><span data-stu-id="013c7-102">MSSQL_ENG020598</span></span>
    
## <a name="message-details"></a><span data-ttu-id="013c7-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="013c7-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="013c7-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="013c7-104">Product Name</span></span>|<span data-ttu-id="013c7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="013c7-105">SQL Server</span></span>|  
|<span data-ttu-id="013c7-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="013c7-106">Event ID</span></span>|<span data-ttu-id="013c7-107">20598</span><span class="sxs-lookup"><span data-stu-id="013c7-107">20598</span></span>|  
|<span data-ttu-id="013c7-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="013c7-108">Event Source</span></span>|<span data-ttu-id="013c7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="013c7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="013c7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="013c7-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="013c7-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="013c7-111">Symbolic Name</span></span>||  
|<span data-ttu-id="013c7-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="013c7-112">Message Text</span></span>|<span data-ttu-id="013c7-113">No se encontró la fila en el suscriptor al aplicar el comando replicado.</span><span class="sxs-lookup"><span data-stu-id="013c7-113">The row was not found at the Subscriber when applying the replicated command.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="013c7-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="013c7-114">Explanation</span></span>  
 <span data-ttu-id="013c7-115">Este error se produce en la replicación transaccional si el Agente de distribución intenta actualizar una fila en el suscriptor, pero la fila se ha eliminado o se ha cambiado su clave principal.</span><span class="sxs-lookup"><span data-stu-id="013c7-115">This error is raised in transactional replication if the Distribution Agent attempts to update a row at the Subscriber, but the row has been deleted or the primary key of the row has been changed.</span></span> <span data-ttu-id="013c7-116">De forma predeterminada, los suscriptores de publicaciones transaccionales deben tratarse como de solo lectura, porque los cambios no se propagan de vuelta al publicador.</span><span class="sxs-lookup"><span data-stu-id="013c7-116">By default, Subscribers to transactional publications should be treated as read-only, because changes are not propagated back to the Publisher.</span></span> <span data-ttu-id="013c7-117">En la replicación transaccional, los cambios de usuario deben realizarse solo en el suscriptor si se utilizan suscripciones actualizables o replicación del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="013c7-117">For transactional replication, user changes should be made at the Subscriber only if updatable subscriptions or peer-to-peer replication is used.</span></span> <span data-ttu-id="013c7-118">Para obtener información acerca de estas opciones, vea [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) y [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="013c7-118">For information about these options, see [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) and [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="013c7-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="013c7-119">User Action</span></span>  
 <span data-ttu-id="013c7-120">**Para resolver este problema:**</span><span class="sxs-lookup"><span data-stu-id="013c7-120">**To resolve this problem:**</span></span>  
  
1.  <span data-ttu-id="013c7-121">Si la replicación debe continuar mientras identifica el origen del error, especifique el parámetro **SkipErrors 20598** para el agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="013c7-121">If replication must continue while you identify the source of the error, specify the parameter **-SkipErrors 20598** for the Distribution Agent.</span></span> <span data-ttu-id="013c7-122">Esto permite al agente omitir los cambios que provocan el error 20598, a la vez que permite que se repliquen otros cambios.</span><span class="sxs-lookup"><span data-stu-id="013c7-122">This allows the agent to skip changes that result in error 20598, while allowing other changes to be replicated.</span></span>  
  
2.  <span data-ttu-id="013c7-123">Identifique qué filas del suscriptor se han eliminado o tienen una clave principal distinta que las filas correspondientes en el publicador.</span><span class="sxs-lookup"><span data-stu-id="013c7-123">Identify which rows at the Subscriber have been deleted or have a different primary key than the corresponding rows at the Publisher.</span></span> <span data-ttu-id="013c7-124">Puede utilizar la [tablediff Utility](../../tools/tablediff-utility.md) para determinar qué filas de las bases de datos de publicaciones y suscripciones son diferentes.</span><span class="sxs-lookup"><span data-stu-id="013c7-124">You can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span> <span data-ttu-id="013c7-125">Para obtener información sobre el uso de esta utilidad con bases de datos replicadas, vea [Comparar tablas replicadas para buscar diferencias &#40;programación de la replicación&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span><span class="sxs-lookup"><span data-stu-id="013c7-125">For information about using this utility with replicated databases, see [Compare Replicated Tables for Differences &#40;Replication Programming&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span></span>  
  
3.  <span data-ttu-id="013c7-126">Corrija las filas del suscriptor con la utilidad **tablediff** u otro método.</span><span class="sxs-lookup"><span data-stu-id="013c7-126">Correct the rows at the Subscriber using the **tablediff** utility or another method.</span></span>  
  
4.  <span data-ttu-id="013c7-127">(Opcional) Quite el parámetro **- SkipErrors** .</span><span class="sxs-lookup"><span data-stu-id="013c7-127">(Optional) Remove the **-SkipErrors** parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="013c7-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="013c7-128">See Also</span></span>  
 [<span data-ttu-id="013c7-129">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="013c7-129">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
