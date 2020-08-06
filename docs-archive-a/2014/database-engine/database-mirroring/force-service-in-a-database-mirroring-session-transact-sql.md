---
title: Forzar el servicio en una sesión de creación de reflejo de la base de datos (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- forced service [SQL Server]
- database mirroring [SQL Server], forcing service
ms.assetid: 8b6ffe77-35f3-4e2a-a658-8a38a8e1c794
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b909f3602a78f3244ab3cf4479b8745956a7bd62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751466"
---
# <a name="force-service-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="2e8a4-102">Forzar el servicio en una sesión de creación de reflejo de la base de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2e8a4-102">Force Service in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="2e8a4-103">En los modos de alto rendimiento y de alta seguridad sin conmutación automática por error, si se produce un error en el servidor principal mientras el servidor reflejado está disponible, el propietario de la base de datos puede hacer que ésta esté disponible forzando la conmutación por error del servicio (con una posible pérdida de datos) para la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-103">In high-performance mode and high-safety mode without automatic failover, if the principal server fails while the mirror server is available, the database owner can make the database available by forcing service to fail over (with possible data loss) to the mirror database.</span></span> <span data-ttu-id="2e8a4-104">Esta opción está disponible solamente si se cumplen todas las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2e8a4-104">This option is available only under all the following conditions:</span></span>  
  
-   <span data-ttu-id="2e8a4-105">El servidor principal está inactivo.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-105">The principal server is down.</span></span>  
  
-   <span data-ttu-id="2e8a4-106">WITNESS está establecido en OFF o está conectado al servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-106">WITNESS is set to OFF or is connected to the mirror server.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="2e8a4-107">El servicio forzado es estrictamente un método de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-107">Forced service is strictly a disaster recovery method.</span></span> <span data-ttu-id="2e8a4-108">Si se fuerza el servicio, pueden perderse datos.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-108">Forcing service may involve some data loss.</span></span> <span data-ttu-id="2e8a4-109">Por consiguiente, fuerce el servicio solo si es aceptable el riesgo de perder datos para restaurar el servicio en la base de datos inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-109">Therefore, force service only if you are willing to risk losing some data in order to restore service to the database immediately.</span></span> <span data-ttu-id="2e8a4-110">Si forzar el servicio supone una posible pérdida de un gran volumen de datos, se recomienda detener la creación del reflejo y sincronizar manualmente las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-110">If forcing service risks losing significant data, we recommend that you stop mirroring and manually resynchronize the databases.</span></span> <span data-ttu-id="2e8a4-111">Para obtener más información acerca de los riesgos que supone forzar el servicio, vea [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="2e8a4-111">For more information about the risks of forcing service, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
 <span data-ttu-id="2e8a4-112">Al forzar el servicio se suspende la sesión y se inicia un nuevo punto de bifurcación de recuperación.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-112">Forcing service suspends the session and starts a new recovery fork.</span></span> <span data-ttu-id="2e8a4-113">El efecto de forzar el servicio es parecido al de quitar la creación del reflejo y recuperar la base de datos principal anterior.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-113">The effect of forcing service is similar to removing mirroring and recovering the former principal database.</span></span> <span data-ttu-id="2e8a4-114">No obstante, forzar el servicio facilita la resincronización de las bases de datos (con posible pérdida de datos) cuando se reanuda la creación del reflejo.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-114">However, forcing service facilitates resynchronizing the databases (with possible data loss) when mirroring resumes.</span></span>  
  
### <a name="to-force-service-in-a-database-mirroring-session"></a><span data-ttu-id="2e8a4-115">Para forzar el servicio en una sesión de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="2e8a4-115">To force service in a database mirroring session</span></span>  
  
1.  <span data-ttu-id="2e8a4-116">Conéctese al servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-116">Connect to the mirror server.</span></span>  
  
2.  <span data-ttu-id="2e8a4-117">Emita la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="2e8a4-117">Issue the following statement:</span></span>  
  
     <span data-ttu-id="2e8a4-118">ALTER DATABASE *<database_name>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span><span class="sxs-lookup"><span data-stu-id="2e8a4-118">ALTER DATABASE *<database_name>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span></span>  
  
     <span data-ttu-id="2e8a4-119">Donde *<database_name>* es la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-119">where *<database_name>* is the mirrored database.</span></span>  
  
     <span data-ttu-id="2e8a4-120">El servidor reflejado pasa inmediatamente al servidor principal y la creación del reflejo se suspende.</span><span class="sxs-lookup"><span data-stu-id="2e8a4-120">The mirror server immediately transitions to principal server, and mirroring is suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e8a4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e8a4-121">See Also</span></span>  
 <span data-ttu-id="2e8a4-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2e8a4-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="2e8a4-123">Database Mirroring Operating Modes</span><span class="sxs-lookup"><span data-stu-id="2e8a4-123">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
