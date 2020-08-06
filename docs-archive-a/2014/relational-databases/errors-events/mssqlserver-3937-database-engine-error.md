---
title: MSSQLSERVER_3937 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3937 (Database Engine error)
ms.assetid: 312d5bbe-c8de-42db-af4b-4ccb448ce6ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac466e6eb50ad4b7a8848a1159963cb0fd35e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745771"
---
# <a name="mssqlserver_3937"></a><span data-ttu-id="2b742-102">MSSQLSERVER_3937</span><span class="sxs-lookup"><span data-stu-id="2b742-102">MSSQLSERVER_3937</span></span>
    
## <a name="details"></a><span data-ttu-id="2b742-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2b742-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b742-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="2b742-104">Product Name</span></span>|<span data-ttu-id="2b742-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2b742-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2b742-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2b742-106">Event ID</span></span>|<span data-ttu-id="2b742-107">3937</span><span class="sxs-lookup"><span data-stu-id="2b742-107">3937</span></span>|  
|<span data-ttu-id="2b742-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="2b742-108">Event Source</span></span>|<span data-ttu-id="2b742-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2b742-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2b742-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2b742-110">Component</span></span>|<span data-ttu-id="2b742-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2b742-111">SQLEngine</span></span>|  
|<span data-ttu-id="2b742-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2b742-112">Symbolic Name</span></span>|<span data-ttu-id="2b742-113">XACT_FILESTREAM_ROLLBACK_ERROR</span><span class="sxs-lookup"><span data-stu-id="2b742-113">XACT_FILESTREAM_ROLLBACK_ERROR</span></span>|  
|<span data-ttu-id="2b742-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2b742-114">Message Text</span></span>|<span data-ttu-id="2b742-115">Error al intentar notificar al controlador de filtro de secuencias de archivo que se revirtió una transacción.</span><span class="sxs-lookup"><span data-stu-id="2b742-115">An error occurred while trying to notify the FILESTREAM filter driver that a transaction was rolled back.</span></span> <span data-ttu-id="2b742-116">Código de error: 0x%0x.</span><span class="sxs-lookup"><span data-stu-id="2b742-116">Error code: 0x%0x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2b742-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="2b742-117">Explanation</span></span>  
 <span data-ttu-id="2b742-118">El controlador RsFx ha devuelto un error al emitir una notificación de reversión de una transacción.</span><span class="sxs-lookup"><span data-stu-id="2b742-118">An error was returned by the RsFx driver when issuing a rollback notification for a transaction.</span></span> <span data-ttu-id="2b742-119">Este error suele provocarlo la escasez de recursos.</span><span class="sxs-lookup"><span data-stu-id="2b742-119">This is probably caused by a resource shortage.</span></span> <span data-ttu-id="2b742-120">Esto puede producir una pequeña pérdida de memoria en el controlador de filtro RsFx, pero ésta se liberará cuando se cierre el proceso sqlservr.exe que creó la transacción.</span><span class="sxs-lookup"><span data-stu-id="2b742-120">This can cause a small memory leak in the RsFx filter driver, but this will be freed when the sqlservr.exe process that created the transaction exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2b742-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2b742-121">User Action</span></span>  
  
