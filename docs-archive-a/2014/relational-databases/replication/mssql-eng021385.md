---
title: MSSQL_ENG021385 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021385 error
ms.assetid: a2c0444f-d97b-4760-8905-3574791c2e26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b73d3216f07cb44d750a37149634258648f1bd48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745206"
---
# <a name="mssql_eng021385"></a><span data-ttu-id="d2b16-102">MSSQL_ENG021385</span><span class="sxs-lookup"><span data-stu-id="d2b16-102">MSSQL_ENG021385</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d2b16-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="d2b16-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2b16-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d2b16-104">Product Name</span></span>|<span data-ttu-id="d2b16-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d2b16-105">SQL Server</span></span>|  
|<span data-ttu-id="d2b16-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d2b16-106">Event ID</span></span>|<span data-ttu-id="d2b16-107">21385</span><span class="sxs-lookup"><span data-stu-id="d2b16-107">21385</span></span>|  
|<span data-ttu-id="d2b16-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d2b16-108">Event Source</span></span>|<span data-ttu-id="d2b16-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d2b16-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d2b16-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d2b16-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d2b16-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d2b16-111">Symbolic Name</span></span>||  
|<span data-ttu-id="d2b16-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d2b16-112">Message Text</span></span>|<span data-ttu-id="d2b16-113">La instantánea no pudo procesar la publicación '%1!'.</span><span class="sxs-lookup"><span data-stu-id="d2b16-113">Snapshot failed to process publication '%s'.</span></span> <span data-ttu-id="d2b16-114">Puede deberse a un cambio de actividad de esquema activo o a la adición de nuevos artículos.</span><span class="sxs-lookup"><span data-stu-id="d2b16-114">Possibly due to active schema change activity or new articles being added.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d2b16-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="d2b16-115">Explanation</span></span>  
 <span data-ttu-id="d2b16-116">Este error aparece si comienza a ejecutarse el Agente de instantáneas cuando hay cambios en curso en la base de datos de publicaciones, como adiciones o eliminaciones de artículos, y cambios de esquema en objetos publicados.</span><span class="sxs-lookup"><span data-stu-id="d2b16-116">This error is raised if the Snapshot Agent starts running when there are ongoing changes to the publication database, including adding or dropping articles and performing schema changes on published objects.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d2b16-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d2b16-117">User Action</span></span>  
 <span data-ttu-id="d2b16-118">Reinicie el Agente de instantáneas cuando finalicen los cambios en la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="d2b16-118">Restart the Snapshot Agent after changes to the publication database are complete.</span></span> <span data-ttu-id="d2b16-119">Para obtener más información, vea [Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) y [Conceptos de los ejecutables del Agente de replicación](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="d2b16-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b16-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2b16-120">See Also</span></span>  
 [<span data-ttu-id="d2b16-121">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="d2b16-121">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
