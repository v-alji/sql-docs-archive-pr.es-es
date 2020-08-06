---
title: MSSQLSERVER_3619 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3619 (Database Engine error)
ms.assetid: 7d94f8d9-65ca-4fde-9c17-7b83e94a3779
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2328ee6366d47130a02c444bce65b7b655af7965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675885"
---
# <a name="mssqlserver_3619"></a><span data-ttu-id="aa277-102">MSSQLSERVER_3619</span><span class="sxs-lookup"><span data-stu-id="aa277-102">MSSQLSERVER_3619</span></span>
    
## <a name="details"></a><span data-ttu-id="aa277-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="aa277-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa277-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="aa277-104">Product Name</span></span>|<span data-ttu-id="aa277-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aa277-105">SQL Server</span></span>|  
|<span data-ttu-id="aa277-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="aa277-106">Event ID</span></span>|<span data-ttu-id="aa277-107">3619</span><span class="sxs-lookup"><span data-stu-id="aa277-107">3619</span></span>|  
|<span data-ttu-id="aa277-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="aa277-108">Event Source</span></span>|<span data-ttu-id="aa277-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aa277-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aa277-110">Componente</span><span class="sxs-lookup"><span data-stu-id="aa277-110">Component</span></span>|<span data-ttu-id="aa277-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aa277-111">SQLEngine</span></span>|  
|<span data-ttu-id="aa277-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="aa277-112">Symbolic Name</span></span>|<span data-ttu-id="aa277-113">SYS_NOLOG</span><span class="sxs-lookup"><span data-stu-id="aa277-113">SYS_NOLOG</span></span>|  
|<span data-ttu-id="aa277-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="aa277-114">Message Text</span></span>|<span data-ttu-id="aa277-115">No se pudo escribir un registro de punto de comprobación en la base de datos con id. %d. Espacio insuficiente para el registro.</span><span class="sxs-lookup"><span data-stu-id="aa277-115">Could not write a checkpoint record in database ID %d because the log is out of space.</span></span> <span data-ttu-id="aa277-116">Póngase en contacto con el administrador de la base de datos para truncar el registro o asignar más espacio a los archivos de registro de base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa277-116">Contact the database administrator to truncate the log or allocate more space to the database log files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aa277-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="aa277-117">Explanation</span></span>  
 <span data-ttu-id="aa277-118">El registro de transacciones se ha quedado sin espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="aa277-118">The transaction log is out of disk space.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa277-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="aa277-119">User Action</span></span>  
 <span data-ttu-id="aa277-120">Trunque el registro para liberar espacio o asigne más espacio al registro.</span><span class="sxs-lookup"><span data-stu-id="aa277-120">Truncate the log to release some space, or allocate more space to the log.</span></span> <span data-ttu-id="aa277-121">Para obtener más información, vea "Solucionar problemas de un registro de transacciones lleno (Error 9002)" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aa277-121">For more information see, "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
  
