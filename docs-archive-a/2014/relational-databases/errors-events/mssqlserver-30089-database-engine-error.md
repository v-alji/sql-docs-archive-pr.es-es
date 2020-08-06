---
title: MSSQLSERVER_30089 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9992 (Database Engine error)
ms.assetid: 188e5bde-6865-4740-a2b2-582be8f55c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d0b9c71ea620174f993ae87befed8a21bb3d0bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673026"
---
# <a name="mssqlserver_30089"></a><span data-ttu-id="3edcb-102">MSSQLSERVER_30089</span><span class="sxs-lookup"><span data-stu-id="3edcb-102">MSSQLSERVER_30089</span></span>
    
## <a name="details"></a><span data-ttu-id="3edcb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3edcb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3edcb-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="3edcb-104">Product Name</span></span>|<span data-ttu-id="3edcb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3edcb-105">SQL Server</span></span>|  
|<span data-ttu-id="3edcb-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="3edcb-106">Event ID</span></span>|<span data-ttu-id="3edcb-107">30089</span><span class="sxs-lookup"><span data-stu-id="3edcb-107">30089</span></span>|  
|<span data-ttu-id="3edcb-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="3edcb-108">Event Source</span></span>|<span data-ttu-id="3edcb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3edcb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3edcb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3edcb-110">Component</span></span>|<span data-ttu-id="3edcb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3edcb-111">SQLEngine</span></span>|  
|<span data-ttu-id="3edcb-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3edcb-112">Symbolic Name</span></span>|<span data-ttu-id="3edcb-113">IFTS_FDHOST_TERMINATEDABNORMAL</span><span class="sxs-lookup"><span data-stu-id="3edcb-113">IFTS_FDHOST_TERMINATEDABNORMAL</span></span>|  
|<span data-ttu-id="3edcb-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3edcb-114">Message Text</span></span>|<span data-ttu-id="3edcb-115">El proceso de host de demonio de filtro (FDHost) de texto completo se ha detenido de forma anormal.</span><span class="sxs-lookup"><span data-stu-id="3edcb-115">The fulltext filter daemon host (FDHost) process has stopped abnormally.</span></span> <span data-ttu-id="3edcb-116">Esto puede ocurrir si un componente lingüístico mal configurado o con un funcionamiento incorrecto, como un separador de palabras, un lematizador o un filtro, ha causado un error irrecuperable durante la indización de texto completo o el procesamiento de consultas.</span><span class="sxs-lookup"><span data-stu-id="3edcb-116">This can occur if an incorrectly configured or malfunctioning linguistic component, such as a wordbreaker, stemmer or filter has caused an irrecoverable error during full-text indexing or query processing.</span></span> <span data-ttu-id="3edcb-117">El proceso se reiniciará de forma automática.</span><span class="sxs-lookup"><span data-stu-id="3edcb-117">The process will be restarted automatically.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3edcb-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="3edcb-118">Explanation</span></span>  
 <span data-ttu-id="3edcb-119">El host de demonio de filtro de texto completo ha encontrado algún problema que le ha obligado a detenerse de forma anómala.</span><span class="sxs-lookup"><span data-stu-id="3edcb-119">The full-text filter daemon host has encountered some problem that has forced it to stop abnormally.</span></span> <span data-ttu-id="3edcb-120">La causa del problema puede ser un documento con un formato incorrecto, un error en el filtro o en el separador de palabras, o un problema en el demonio de filtro.</span><span class="sxs-lookup"><span data-stu-id="3edcb-120">The cause of the problem could be a badly formatted document, a bug in the filter or word-breaker, or a problem in filter daemon.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3edcb-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3edcb-121">User Action</span></span>  
 <span data-ttu-id="3edcb-122">Normalmente, el demonio se recuperará del error.</span><span class="sxs-lookup"><span data-stu-id="3edcb-122">Typically, the daemon will recover from the error.</span></span> <span data-ttu-id="3edcb-123">Si el error se produce sistemáticamente, hay que investigar y solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="3edcb-123">If it is consistently failing, troubleshooting is necessary.</span></span> <span data-ttu-id="3edcb-124">Intente la siguiente acción para solucionarlo:</span><span class="sxs-lookup"><span data-stu-id="3edcb-124">Try the following to isolate the issue:</span></span>  
  
1.  <span data-ttu-id="3edcb-125">Si se ha instalado recientemente un nuevo componente lingüístico, quítelo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3edcb-125">If a new linguistic component has been installed recently, remove it from the system.</span></span>  
  
2.  <span data-ttu-id="3edcb-126">Examine el registro de rastreo para identificar los documentos nuevos cuya indización de texto completo no ha sido posible y quítelos.</span><span class="sxs-lookup"><span data-stu-id="3edcb-126">Look at the crawl log to identify any new document that failed to be full-text indexed, and remove it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3edcb-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3edcb-127">See Also</span></span>  
 <span data-ttu-id="3edcb-128">[sp_help_fulltext_system_components &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3edcb-128">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="3edcb-129">[Configurar y administrar separadores de palabras y lematizadores para la búsqueda](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="3edcb-129">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="3edcb-130">Configurar y administrar filtros para búsquedas</span><span class="sxs-lookup"><span data-stu-id="3edcb-130">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
