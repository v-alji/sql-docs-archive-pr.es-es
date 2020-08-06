---
title: MSSQLSERVER_8642 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8642 (Database Engine error)
ms.assetid: fc498059-202f-4d0b-8599-4e784b47c186
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e30296fa569599b91ca74edc7535d330119e1680
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674851"
---
# <a name="mssqlserver_8642"></a><span data-ttu-id="41476-102">MSSQLSERVER_8642</span><span class="sxs-lookup"><span data-stu-id="41476-102">MSSQLSERVER_8642</span></span>
    
## <a name="details"></a><span data-ttu-id="41476-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="41476-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41476-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="41476-104">Product Name</span></span>|<span data-ttu-id="41476-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="41476-105">SQL Server</span></span>|  
|<span data-ttu-id="41476-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="41476-106">Event ID</span></span>|<span data-ttu-id="41476-107">8642</span><span class="sxs-lookup"><span data-stu-id="41476-107">8642</span></span>|  
|<span data-ttu-id="41476-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="41476-108">Event Source</span></span>|<span data-ttu-id="41476-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="41476-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="41476-110">Componente</span><span class="sxs-lookup"><span data-stu-id="41476-110">Component</span></span>|<span data-ttu-id="41476-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="41476-111">SQLEngine</span></span>|  
|<span data-ttu-id="41476-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="41476-112">Symbolic Name</span></span>|<span data-ttu-id="41476-113">EXCHNGSTART_ERR</span><span class="sxs-lookup"><span data-stu-id="41476-113">EXCHNGSTART_ERR</span></span>|  
|<span data-ttu-id="41476-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="41476-114">Message Text</span></span>|<span data-ttu-id="41476-115">El procesador de consultas no puede iniciar los recursos de subproceso necesarios para la ejecución en paralelo.</span><span class="sxs-lookup"><span data-stu-id="41476-115">The query processor could not start the necessary thread resources for parallel query execution.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="41476-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="41476-116">Explanation</span></span>  
 <span data-ttu-id="41476-117">No hay suficientes recursos de subproceso en el servidor.</span><span class="sxs-lookup"><span data-stu-id="41476-117">Thread resources are low in the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="41476-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="41476-118">User Action</span></span>  
 <span data-ttu-id="41476-119">Reduzca la carga en el servidor y ejecute de nuevo la consulta.</span><span class="sxs-lookup"><span data-stu-id="41476-119">Reduce load on the server, and run the query again.</span></span>  
  
  
