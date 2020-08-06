---
title: MSSQLSERVER_2516 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2516 (Database Engine error)
ms.assetid: 79ed14b5-f53c-40c6-8334-8a083f732207
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6be0809b3560d94bb883cf3a4acfa3d2c484b8b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744716"
---
# <a name="mssqlserver_2516"></a><span data-ttu-id="9c44e-102">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="9c44e-102">MSSQLSERVER_2516</span></span>
    
## <a name="details"></a><span data-ttu-id="9c44e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9c44e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9c44e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="9c44e-104">Product Name</span></span>|<span data-ttu-id="9c44e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9c44e-105">SQL Server</span></span>|  
|<span data-ttu-id="9c44e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="9c44e-106">Event ID</span></span>|<span data-ttu-id="9c44e-107">2516</span><span class="sxs-lookup"><span data-stu-id="9c44e-107">2516</span></span>|  
|<span data-ttu-id="9c44e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="9c44e-108">Event Source</span></span>|<span data-ttu-id="9c44e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9c44e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9c44e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9c44e-110">Component</span></span>|<span data-ttu-id="9c44e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9c44e-111">SQLEngine</span></span>|  
|<span data-ttu-id="9c44e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9c44e-112">Symbolic Name</span></span>|<span data-ttu-id="9c44e-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span><span class="sxs-lookup"><span data-stu-id="9c44e-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span></span>|  
|<span data-ttu-id="9c44e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9c44e-114">Message Text</span></span>|<span data-ttu-id="9c44e-115">La reparación ha invalidado el mapa de bits diferencial de la base de datos NAME.</span><span class="sxs-lookup"><span data-stu-id="9c44e-115">Repair has invalidated the differential bitmap for database NAME.</span></span> <span data-ttu-id="9c44e-116">La cadena de la copia de seguridad diferencial está rota.</span><span class="sxs-lookup"><span data-stu-id="9c44e-116">The differential backup chain is broken.</span></span> <span data-ttu-id="9c44e-117">Debe realizar una copia de seguridad completa de la base de datos para poder realizar una copia de seguridad diferencial.</span><span class="sxs-lookup"><span data-stu-id="9c44e-117">You must perform a full database backup before you can perform a differential backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9c44e-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="9c44e-118">Explanation</span></span>  
 <span data-ttu-id="9c44e-119">Este mensaje informativo se devuelve cuando se repara el error MSSQLEngine_2515.</span><span class="sxs-lookup"><span data-stu-id="9c44e-119">This informational message is returned when error MSSQLEngine_2515 is repaired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9c44e-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9c44e-120">User Action</span></span>  
 <span data-ttu-id="9c44e-121">Realice una copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9c44e-121">Perform a full database backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c44e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c44e-122">See Also</span></span>  
 [<span data-ttu-id="9c44e-123">Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9c44e-123">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
  
