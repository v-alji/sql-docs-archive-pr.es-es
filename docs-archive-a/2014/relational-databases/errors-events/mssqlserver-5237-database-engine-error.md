---
title: MSSQLSERVER_5237 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5237 (Database Engine error)
ms.assetid: 9ff28935-d1eb-47ee-99b3-1a65cb948ce7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 224317e290ce15aaed979129733b6273b3b663df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675881"
---
# <a name="mssqlserver_5237"></a><span data-ttu-id="e4b95-102">MSSQLSERVER_5237</span><span class="sxs-lookup"><span data-stu-id="e4b95-102">MSSQLSERVER_5237</span></span>
    
## <a name="details"></a><span data-ttu-id="e4b95-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e4b95-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e4b95-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="e4b95-104">Product Name</span></span>|<span data-ttu-id="e4b95-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4b95-105">SQL Server</span></span>|  
|<span data-ttu-id="e4b95-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e4b95-106">Event ID</span></span>|<span data-ttu-id="e4b95-107">5237</span><span class="sxs-lookup"><span data-stu-id="e4b95-107">5237</span></span>|  
|<span data-ttu-id="e4b95-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="e4b95-108">Event Source</span></span>|<span data-ttu-id="e4b95-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e4b95-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e4b95-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e4b95-110">Component</span></span>|<span data-ttu-id="e4b95-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e4b95-111">SQLEngine</span></span>|  
|<span data-ttu-id="e4b95-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e4b95-112">Symbolic Name</span></span>|<span data-ttu-id="e4b95-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span><span class="sxs-lookup"><span data-stu-id="e4b95-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span></span>|  
|<span data-ttu-id="e4b95-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e4b95-114">Message Text</span></span>|<span data-ttu-id="e4b95-115">Error de comprobación del conjunto de filas cruzadas de DBCC para el objeto 'NAME' (Id. de objeto O_ID) debido a un error de consulta interno.</span><span class="sxs-lookup"><span data-stu-id="e4b95-115">DBCC cross-rowset check failed for object 'NAME' (object ID O_ID) due to an internal query error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e4b95-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="e4b95-116">Explanation</span></span>  
 <span data-ttu-id="e4b95-117">Un error interno ha provocado que DBCC no pueda ejecutar la consulta para comprobar las vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="e4b95-117">An internal error resulted in DBCC not being able to execute the query to check indexed views.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e4b95-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e4b95-118">User Action</span></span>  
 <span data-ttu-id="e4b95-119">Vuelva a ejecutar el comando DBCC.</span><span class="sxs-lookup"><span data-stu-id="e4b95-119">Rerun the DBCC command.</span></span>  
  
  
