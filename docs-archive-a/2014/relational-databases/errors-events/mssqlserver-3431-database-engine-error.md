---
title: MSSQLSERVER_3431 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3431 (Database Engine error)
ms.assetid: 9541217f-e5c6-4a12-a19a-006058f1d3f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9b62047a25d71ca05dc3ab03651e5672353bc0a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675891"
---
# <a name="mssqlserver_3431"></a><span data-ttu-id="87c33-102">MSSQLSERVER_3431</span><span class="sxs-lookup"><span data-stu-id="87c33-102">MSSQLSERVER_3431</span></span>
    
## <a name="details"></a><span data-ttu-id="87c33-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="87c33-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87c33-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="87c33-104">Product Name</span></span>|<span data-ttu-id="87c33-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="87c33-105">SQL Server</span></span>|  
|<span data-ttu-id="87c33-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="87c33-106">Event ID</span></span>|<span data-ttu-id="87c33-107">3431</span><span class="sxs-lookup"><span data-stu-id="87c33-107">3431</span></span>|  
|<span data-ttu-id="87c33-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="87c33-108">Event Source</span></span>|<span data-ttu-id="87c33-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="87c33-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="87c33-110">Componente</span><span class="sxs-lookup"><span data-stu-id="87c33-110">Component</span></span>|<span data-ttu-id="87c33-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="87c33-111">SQLEngine</span></span>|  
|<span data-ttu-id="87c33-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="87c33-112">Symbolic Name</span></span>|<span data-ttu-id="87c33-113">UNRESOLVED_XACT</span><span class="sxs-lookup"><span data-stu-id="87c33-113">UNRESOLVED_XACT</span></span>|  
|<span data-ttu-id="87c33-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="87c33-114">Message Text</span></span>|<span data-ttu-id="87c33-115">No se pudo recuperar la base de datos '%.\*ls' (id. %d) debido a resultados de transacciones sin resolver.</span><span class="sxs-lookup"><span data-stu-id="87c33-115">Could not recover database '%.\*ls' (database ID %d) because of unresolved transaction outcomes.</span></span> <span data-ttu-id="87c33-116">Se prepararon transacciones del Microsoft DTC (Coordinador de transacciones distribuidas), pero Microsoft DTC no pudo determinar la resolución.</span><span class="sxs-lookup"><span data-stu-id="87c33-116">Microsoft Distributed Transaction Coordinator (MS DTC) transactions were prepared, but MS DTC was unable to determine the resolution.</span></span> <span data-ttu-id="87c33-117">Para solucionar este problema, corrija MS DTC, realice una restauración a partir de una copia de seguridad completa o repare la base de datos.</span><span class="sxs-lookup"><span data-stu-id="87c33-117">To resolve, either fix MS DTC, restore from a full backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="87c33-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="87c33-118">Explanation</span></span>  
 <span data-ttu-id="87c33-119">Una o más transacciones distribuidas que estaban usando el Coordinador de transacciones distribuidas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] (MS DTC) estaban incompletas cuando se cerró la base de datos.</span><span class="sxs-lookup"><span data-stu-id="87c33-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="87c33-120">Se originó un error al recuperar esta base de datos debido a que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no puede completar o revertir las transacciones sin más información de MS DTC.</span><span class="sxs-lookup"><span data-stu-id="87c33-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot complete the transactions or roll back the transactions without more information from MS DTC.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="87c33-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="87c33-121">User Action</span></span>  
 <span data-ttu-id="87c33-122">Para recuperar esta base de datos, primero debe resolver el problema con MS DTC.</span><span class="sxs-lookup"><span data-stu-id="87c33-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="87c33-123">Para estudiar el problema con MS DTC, examine los registros de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="87c33-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="87c33-124">Si no puede resolver el problema con MS DTC y recuperar la base de datos, restaure una copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="87c33-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
