---
title: MSSQLSERVER_3437 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3437 (Database Engine error)
ms.assetid: b38216e2-b650-43bd-97af-061d54f60031
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ed8f2050f6f1b38bc5f3fcb7a9700b80e52f2763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675886"
---
# <a name="mssqlserver_3437"></a><span data-ttu-id="a0c3f-102">MSSQLSERVER_3437</span><span class="sxs-lookup"><span data-stu-id="a0c3f-102">MSSQLSERVER_3437</span></span>
    
## <a name="details"></a><span data-ttu-id="a0c3f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a0c3f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0c3f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a0c3f-104">Product Name</span></span>|<span data-ttu-id="a0c3f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a0c3f-105">SQL Server</span></span>|  
|<span data-ttu-id="a0c3f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a0c3f-106">Event ID</span></span>|<span data-ttu-id="a0c3f-107">3437</span><span class="sxs-lookup"><span data-stu-id="a0c3f-107">3437</span></span>|  
|<span data-ttu-id="a0c3f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a0c3f-108">Event Source</span></span>|<span data-ttu-id="a0c3f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a0c3f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a0c3f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a0c3f-110">Component</span></span>|<span data-ttu-id="a0c3f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a0c3f-111">SQLEngine</span></span>|  
|<span data-ttu-id="a0c3f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a0c3f-112">Symbolic Name</span></span>|<span data-ttu-id="a0c3f-113">NODTC</span><span class="sxs-lookup"><span data-stu-id="a0c3f-113">NODTC</span></span>|  
|<span data-ttu-id="a0c3f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a0c3f-114">Message Text</span></span>|<span data-ttu-id="a0c3f-115">Error al recuperar la base de datos '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-115">An error occurred while recovering database '%.\*ls'.</span></span> <span data-ttu-id="a0c3f-116">No se puede conectar con Microsoft DTC (Coordinador de transacciones distribuidas) para comprobar el estado de finalización de la transacción %S_XID.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-116">Unable to connect to Microsoft Distributed Transaction Coordinator (MS DTC) to check the completion status of transaction %S_XID.</span></span> <span data-ttu-id="a0c3f-117">Corrija MS DTC y vuelva a ejecutar la recuperación.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-117">Fix MS DTC, and run recovery again.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a0c3f-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="a0c3f-118">Explanation</span></span>  
 <span data-ttu-id="a0c3f-119">Una o más transacciones distribuidas que estaban usando el Coordinador de transacciones distribuidas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] (MS DTC) estaban incompletas cuando se cerró la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="a0c3f-120">Se originó un error al recuperar la base de datos debido a que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se puede conectar a MS DTC para completar o revertir las transacciones.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot connect to MS DTC to complete or roll back the transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a0c3f-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a0c3f-121">User Action</span></span>  
 <span data-ttu-id="a0c3f-122">Para recuperar esta base de datos, primero debe resolver el problema con MS DTC.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="a0c3f-123">Para estudiar el problema con MS DTC, examine los registros de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="a0c3f-124">Si no puede resolver el problema con MS DTC y recuperar la base de datos, restaure una copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
