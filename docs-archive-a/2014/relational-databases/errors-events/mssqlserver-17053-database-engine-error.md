---
title: MSSQLSERVER_17053 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17053 (Database Engine error)
ms.assetid: e0a01f3d-d0aa-4c38-8bcc-82e59de50512
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11137ba334b66f20c7d9a6caaaf7d1ef42c15dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662069"
---
# <a name="mssqlserver_17053"></a><span data-ttu-id="dfcbf-102">MSSQLSERVER_17053</span><span class="sxs-lookup"><span data-stu-id="dfcbf-102">MSSQLSERVER_17053</span></span>
    
## <a name="details"></a><span data-ttu-id="dfcbf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="dfcbf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dfcbf-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="dfcbf-104">Product Name</span></span>|<span data-ttu-id="dfcbf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dfcbf-105">SQL Server</span></span>|  
|<span data-ttu-id="dfcbf-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="dfcbf-106">Event ID</span></span>|<span data-ttu-id="dfcbf-107">17053</span><span class="sxs-lookup"><span data-stu-id="dfcbf-107">17053</span></span>|  
|<span data-ttu-id="dfcbf-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="dfcbf-108">Event Source</span></span>|<span data-ttu-id="dfcbf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dfcbf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dfcbf-110">Componente</span><span class="sxs-lookup"><span data-stu-id="dfcbf-110">Component</span></span>|<span data-ttu-id="dfcbf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dfcbf-111">SQLEngine</span></span>|  
|<span data-ttu-id="dfcbf-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="dfcbf-112">Symbolic Name</span></span>|<span data-ttu-id="dfcbf-113">OS_ERROR</span><span class="sxs-lookup"><span data-stu-id="dfcbf-113">OS_ERROR</span></span>|  
|<span data-ttu-id="dfcbf-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="dfcbf-114">Message Text</span></span>|<span data-ttu-id="dfcbf-115">%ls: error %ls del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dfcbf-115">%ls: Operating system error %ls encountered.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dfcbf-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="dfcbf-116">Explanation</span></span>  
 <span data-ttu-id="dfcbf-117">Se produjo un error genérico del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dfcbf-117">Generic operating system error occurred.</span></span>  <span data-ttu-id="dfcbf-118">No está claro cuál es el estado resultante.</span><span class="sxs-lookup"><span data-stu-id="dfcbf-118">Not clear what the resulting state is.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dfcbf-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="dfcbf-119">User Action</span></span>  
 <span data-ttu-id="dfcbf-120">Normalmente este error se produce junto con algún otro y se debería usar como ayuda para diagnosticar dicho error.</span><span class="sxs-lookup"><span data-stu-id="dfcbf-120">Usually this is in conjunction with some other error and should be used to help diagnose that failure.</span></span> <span data-ttu-id="dfcbf-121">Algunos ejemplos incluirían las lecturas o escrituras de datos o archivos de registro en los que se producen errores, operaciones de lectura y escritura en el Registro u otros errores inesperados de Win32API.</span><span class="sxs-lookup"><span data-stu-id="dfcbf-121">Examples would include reads or writes to data or log files that fail, registry read/write operations, or other unexpected Win32API failures.</span></span>  
  
  
