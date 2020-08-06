---
title: LOCALDB_ERROR_INSUFFICIENT_BUFFER | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: ff67bda8-7e5c-4b06-8d7b-9985b6059a98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 934683cfca1a9a9c0596071824c21a0045e6ebab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677124"
---
# <a name="localdb_error_insufficient_buffer"></a><span data-ttu-id="00af3-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="00af3-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>
    
## <a name="details"></a><span data-ttu-id="00af3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="00af3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00af3-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="00af3-104">Product Name</span></span>|<span data-ttu-id="00af3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="00af3-105">SQL Server</span></span>|  
|<span data-ttu-id="00af3-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="00af3-106">Event ID</span></span>|<span data-ttu-id="00af3-107">276</span><span class="sxs-lookup"><span data-stu-id="00af3-107">276</span></span>|  
|<span data-ttu-id="00af3-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="00af3-108">Event Source</span></span>|<span data-ttu-id="00af3-109">SQL Server Local Database Runtime 12.0</span><span class="sxs-lookup"><span data-stu-id="00af3-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="00af3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="00af3-110">Component</span></span>|<span data-ttu-id="00af3-111">API de Local Database Runtime</span><span class="sxs-lookup"><span data-stu-id="00af3-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="00af3-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="00af3-112">Message Text</span></span>|<span data-ttu-id="00af3-113">El búfer pasado el método de API de la instancia de Local Database no tiene un tamaño suficiente.</span><span class="sxs-lookup"><span data-stu-id="00af3-113">The buffer passed to the Local Database instance API method has insufficient size.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="00af3-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="00af3-114">Explanation</span></span>  
 <span data-ttu-id="00af3-115">El búfer de entrada es demasiado corto y no se ha solicitado truncamiento.</span><span class="sxs-lookup"><span data-stu-id="00af3-115">The input buffer is too short, and truncation was not requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00af3-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="00af3-116">User Action</span></span>  
 <span data-ttu-id="00af3-117">Proporcione un búfer del tamaño especificado.</span><span class="sxs-lookup"><span data-stu-id="00af3-117">Provide a buffer of the specified size.</span></span>  
  
  
