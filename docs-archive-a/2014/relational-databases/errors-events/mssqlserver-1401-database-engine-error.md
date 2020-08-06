---
title: MSSQLSERVER_1401 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1401 (Database Engine error)
ms.assetid: 02928770-aa63-4509-8713-406c73e4cedc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 720263939e2f1685649fc41896e8ea10907d92ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675957"
---
# <a name="mssqlserver_1401"></a><span data-ttu-id="54373-102">MSSQLSERVER_1401</span><span class="sxs-lookup"><span data-stu-id="54373-102">MSSQLSERVER_1401</span></span>
    
## <a name="details"></a><span data-ttu-id="54373-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="54373-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54373-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="54373-104">Product Name</span></span>|<span data-ttu-id="54373-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="54373-105">SQL Server</span></span>|  
|<span data-ttu-id="54373-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="54373-106">Event ID</span></span>|<span data-ttu-id="54373-107">1401</span><span class="sxs-lookup"><span data-stu-id="54373-107">1401</span></span>|  
|<span data-ttu-id="54373-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="54373-108">Event Source</span></span>|<span data-ttu-id="54373-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="54373-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="54373-110">Componente</span><span class="sxs-lookup"><span data-stu-id="54373-110">Component</span></span>|<span data-ttu-id="54373-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="54373-111">SQLEngine</span></span>|  
|<span data-ttu-id="54373-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="54373-112">Symbolic Name</span></span>|<span data-ttu-id="54373-113">DBM_MASTERSTARTUP</span><span class="sxs-lookup"><span data-stu-id="54373-113">DBM_MASTERSTARTUP</span></span>|  
|<span data-ttu-id="54373-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="54373-114">Message Text</span></span>|<span data-ttu-id="54373-115">Error en el inicio de la rutina del subproceso maestro de creación de reflejo de la base de datos por el siguiente motivo: %ls.</span><span class="sxs-lookup"><span data-stu-id="54373-115">Startup of the database-mirroring master thread routine failed for the following reason: %ls.</span></span> <span data-ttu-id="54373-116">Corrija la causa de este error y reinicie el servicio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="54373-116">Correct the cause of this error, and restart the SQL Server service.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="54373-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="54373-117">Explanation</span></span>  
 <span data-ttu-id="54373-118">Error al iniciar el subproceso de control de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="54373-118">Startup of the mirroring control thread failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="54373-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="54373-119">User Action</span></span>  
 <span data-ttu-id="54373-120">En el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], busque el error asociado que precedía a este mensaje.</span><span class="sxs-lookup"><span data-stu-id="54373-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, look for the associated error that preceded this message.</span></span> <span data-ttu-id="54373-121">Corrija la causa de este error y reinicie el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="54373-121">Correct the cause of this error, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service (MSSQLSERVER).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54373-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54373-122">See Also</span></span>  
 [<span data-ttu-id="54373-123">Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="54373-123">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
