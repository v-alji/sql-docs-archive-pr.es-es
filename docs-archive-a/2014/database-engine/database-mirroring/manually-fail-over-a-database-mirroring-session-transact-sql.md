---
title: Realizar una conmutación por error manualmente de una sesión de creación de reflejo de la base de datos (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 36218d61-b5f5-4194-905a-608e0e903db4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c04ea4908ccbc4cfe4f6bb3606347dd444ef416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663660"
---
# <a name="manually-fail-over-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="ebc1f-102">Realizar una conmutación por error manualmente de una sesión de creación de reflejo de la base de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ebc1f-102">Manually Fail Over a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="ebc1f-103">Cuando la base de datos reflejada se sincroniza (es decir, cuando el estado de la base de datos es SYNCHRONIZED), el propietario de la base de datos puede iniciar una conmutación por error manual en el servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="ebc1f-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span> <span data-ttu-id="ebc1f-104">La conmutación por error manual solo se puede iniciar desde el servidor principal.</span><span class="sxs-lookup"><span data-stu-id="ebc1f-104">Manual failover can be initiated only from the principal server.</span></span>  
  
### <a name="to-manually-fail-over-a-database-mirroring-session"></a><span data-ttu-id="ebc1f-105">Para realizar una conmutación por error manual en una sesión de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="ebc1f-105">To manually fail over a database mirroring session</span></span>  
  
1.  <span data-ttu-id="ebc1f-106">Conéctese al servidor principal.</span><span class="sxs-lookup"><span data-stu-id="ebc1f-106">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="ebc1f-107">Establezca el contexto de la base de datos en la base de datos **maestra** :</span><span class="sxs-lookup"><span data-stu-id="ebc1f-107">Set the database context to the **master** database:</span></span>  
  
     `USE master;`  
  
3.  <span data-ttu-id="ebc1f-108">Emita la siguiente instrucción en el servidor principal:</span><span class="sxs-lookup"><span data-stu-id="ebc1f-108">Issue the following statement on the principal server:</span></span>  
  
     <span data-ttu-id="ebc1f-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *nombre_de_base_de_datos* SET PARTNER FAILOVER, donde *nombre_de_base_de_datos* es la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="ebc1f-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET PARTNER FAILOVER, where *database_name* is the mirrored database.</span></span>  
  
     <span data-ttu-id="ebc1f-110">Esto inicia una transición inmediata del servidor reflejado hacia el rol principal.</span><span class="sxs-lookup"><span data-stu-id="ebc1f-110">This initiates an immediate transition of the mirror server to the principal role.</span></span>  
  
 <span data-ttu-id="ebc1f-111">En el principal antiguo, los clientes se desconectan de la base de datos y las transacciones en curso se revierten.</span><span class="sxs-lookup"><span data-stu-id="ebc1f-111">On the former principal, clients are disconnected from the database and in-flight transactions are rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ebc1f-112">Las transacciones que se han preparado mediante el Coordinador de transacciones distribuidas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] pero que aún no están confirmadas en el momento de la conmutación por error se consideran anuladas tras la conmutación por error de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ebc1f-112">Transactions that have been prepared by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator but are still not committed when a failover occurs are considered aborted after the database has failed over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc1f-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ebc1f-113">See Also</span></span>  
 <span data-ttu-id="ebc1f-114">[Reflejo de la base de datos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="ebc1f-114">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="ebc1f-115">[Conmutar por error manualmente una sesión de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="ebc1f-115">[Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="ebc1f-116">Conmutación de roles durante una sesión de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ebc1f-116">Role Switching During a Database Mirroring Session &#40;SQL Server&#41;</span></span>](role-switching-during-a-database-mirroring-session-sql-server.md)  
  
  
