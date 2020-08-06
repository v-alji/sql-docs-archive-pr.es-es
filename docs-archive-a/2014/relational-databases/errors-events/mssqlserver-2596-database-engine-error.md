---
title: MSSQLSERVER_2596 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2596 (Database Engine error)
ms.assetid: 49ab892f-8ba3-4ba1-b562-ddf205019802
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27b2ceed40274df4ba57c4d61a83fbc60b6a7f80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673038"
---
# <a name="mssqlserver_2596"></a><span data-ttu-id="e12a9-102">MSSQLSERVER_2596</span><span class="sxs-lookup"><span data-stu-id="e12a9-102">MSSQLSERVER_2596</span></span>
    
## <a name="details"></a><span data-ttu-id="e12a9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e12a9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e12a9-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="e12a9-104">Product Name</span></span>|<span data-ttu-id="e12a9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e12a9-105">SQL Server</span></span>|  
|<span data-ttu-id="e12a9-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e12a9-106">Event ID</span></span>|<span data-ttu-id="e12a9-107">2596</span><span class="sxs-lookup"><span data-stu-id="e12a9-107">2596</span></span>|  
|<span data-ttu-id="e12a9-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="e12a9-108">Event Source</span></span>|<span data-ttu-id="e12a9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e12a9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e12a9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e12a9-110">Component</span></span>|<span data-ttu-id="e12a9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e12a9-111">SQLEngine</span></span>|  
|<span data-ttu-id="e12a9-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e12a9-112">Symbolic Name</span></span>|<span data-ttu-id="e12a9-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span><span class="sxs-lookup"><span data-stu-id="e12a9-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span></span>|  
|<span data-ttu-id="e12a9-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e12a9-114">Message Text</span></span>|<span data-ttu-id="e12a9-115">Instrucción de reparación no procesada.</span><span class="sxs-lookup"><span data-stu-id="e12a9-115">The repair statement was not processed.</span></span> <span data-ttu-id="e12a9-116">La base de datos no puede estar en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="e12a9-116">The database cannot be in read-only mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e12a9-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="e12a9-117">Explanation</span></span>  
 <span data-ttu-id="e12a9-118">Este mensaje indica que la base de datos está en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="e12a9-118">This message indicates that the database is in read-only mode.</span></span> <span data-ttu-id="e12a9-119">No es posible llevar a cabo reparaciones cuando una base de datos está en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="e12a9-119">Repairs are not possible when a database is in read-only mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e12a9-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e12a9-120">User Action</span></span>  
 <span data-ttu-id="e12a9-121">Establezca la base de datos en modo de lectura y escritura mediante el uso de ALTER DATABASE y después vuelva a ejecutar el comando DBCC.</span><span class="sxs-lookup"><span data-stu-id="e12a9-121">Set the database to read-write by using ALTER DATABASE, and then re-run the DBCC command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12a9-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e12a9-122">See Also</span></span>  
 [<span data-ttu-id="e12a9-123">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e12a9-123">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
