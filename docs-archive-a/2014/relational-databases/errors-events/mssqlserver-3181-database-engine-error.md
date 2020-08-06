---
title: MSSQLSERVER_3181 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3181 (Database Engine error)
ms.assetid: e6d2e716-5263-477c-ad0e-7bcbfef4c1f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f18509d9a18ba8be1f4e40c93bff5abfcae3d69c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673014"
---
# <a name="mssqlserver_3181"></a><span data-ttu-id="9b4b3-102">MSSQLSERVER_3181</span><span class="sxs-lookup"><span data-stu-id="9b4b3-102">MSSQLSERVER_3181</span></span>
    
## <a name="details"></a><span data-ttu-id="9b4b3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9b4b3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b4b3-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="9b4b3-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="9b4b3-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="9b4b3-105">Event ID</span></span>|<span data-ttu-id="9b4b3-106">3181</span><span class="sxs-lookup"><span data-stu-id="9b4b3-106">3181</span></span>|  
|<span data-ttu-id="9b4b3-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="9b4b3-107">Event Source</span></span>|<span data-ttu-id="9b4b3-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9b4b3-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9b4b3-109">Componente</span><span class="sxs-lookup"><span data-stu-id="9b4b3-109">Component</span></span>|<span data-ttu-id="9b4b3-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9b4b3-110">SQLEngine</span></span>|  
|<span data-ttu-id="9b4b3-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9b4b3-111">Symbolic Name</span></span>|<span data-ttu-id="9b4b3-112">LDDB_STORAGE_VERIFY</span><span class="sxs-lookup"><span data-stu-id="9b4b3-112">LDDB_STORAGE_VERIFY</span></span>|  
|<span data-ttu-id="9b4b3-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9b4b3-113">Message Text</span></span>|<span data-ttu-id="9b4b3-114">Si intenta restaurar esta copia de seguridad, podría sufrir problemas de espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="9b4b3-114">Attempting to restore this backup may encounter storage space problems.</span></span> <span data-ttu-id="9b4b3-115">Los mensajes siguientes proporcionarán más detalles.</span><span class="sxs-lookup"><span data-stu-id="9b4b3-115">Subsequent messages will provide details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9b4b3-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="9b4b3-116">Explanation</span></span>  
 <span data-ttu-id="9b4b3-117">La instrucción RESTORE VERIFYONLY comprueba el espacio de almacenamiento disponible en el disco en el que se restaurará la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9b4b3-117">The RESTORE VERIFYONLY statement checks the available storage space on the disk to which the database is to be restored.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="9b4b3-118">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="9b4b3-118">Possible Causes</span></span>  
 <span data-ttu-id="9b4b3-119">El espacio en disco disponible puede ser insuficiente para restaurar la copia de seguridad comprobada.</span><span class="sxs-lookup"><span data-stu-id="9b4b3-119">The available disk space may be insufficient to restore the backup being verified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9b4b3-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9b4b3-120">User Action</span></span>  
 <span data-ttu-id="9b4b3-121">Restaure la copia de seguridad en una ubicación con suficiente espacio en disco o libere más espacio en el disco.</span><span class="sxs-lookup"><span data-stu-id="9b4b3-121">Restore the backup to a location with sufficient disk space, or provide more space on the disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4b3-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b4b3-122">See Also</span></span>  
 <span data-ttu-id="9b4b3-123">[Restaurar una base de datos a una nueva ubicación &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b4b3-123">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="9b4b3-124">[Restaurar archivos en una nueva ubicación &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b4b3-124">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="9b4b3-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b4b3-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="9b4b3-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9b4b3-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql)  
  
  
