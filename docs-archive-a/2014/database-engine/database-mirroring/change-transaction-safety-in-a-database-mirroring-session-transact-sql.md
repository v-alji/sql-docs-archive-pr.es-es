---
title: Cambiar la seguridad de las transacciones en una sesión de creación de reflejo de la base de datos (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- transaction safety [SQL Server database mirroring]
ms.assetid: 8b03bb82-8589-4558-8545-9942fe008391
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d8bc9d0fb639770d33507c29a6ec67f60bd0434a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670577"
---
# <a name="change-transaction-safety-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="56bfb-102">Cambiar la seguridad de las transacciones en una sesión de creación de reflejo de la base de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="56bfb-102">Change Transaction Safety in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="56bfb-103">La seguridad de las transacciones es el atributo que controla el modo operativo de la sesión.</span><span class="sxs-lookup"><span data-stu-id="56bfb-103">Transaction safety is the attribute that controls the operating mode of the session.</span></span> <span data-ttu-id="56bfb-104">No obstante, el propietario de la base de datos puede cambiar la seguridad de las transacciones en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="56bfb-104">At any time, however, the database owner can change the transaction safety.</span></span> <span data-ttu-id="56bfb-105">De forma predeterminada, el nivel de seguridad de las transacciones está establecido en FULL (modo operativo sincrónico).</span><span class="sxs-lookup"><span data-stu-id="56bfb-105">By default, the level of transaction safety is set to FULL (synchronous operating mode).</span></span>  
  
 <span data-ttu-id="56bfb-106">Si se desactiva la seguridad de las transacciones, la sesión cambia al modo operativo asincrónico, lo que maximiza el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="56bfb-106">Turning off transaction safety shifts the session into asynchronous operating mode, which maximizes performance.</span></span> <span data-ttu-id="56bfb-107">Si la base de datos principal no está disponible, la base de datos reflejada se detiene pero está disponible como base de datos en espera semiactiva (la conmutación por error requiere forzar el servicio, con una posible pérdida de datos).</span><span class="sxs-lookup"><span data-stu-id="56bfb-107">If the principal becomes unavailable, the mirror stops but is available as a warm standby (failover requires forcing service with possible data loss).</span></span>  
  
### <a name="to-turn-on-transaction-safety"></a><span data-ttu-id="56bfb-108">Para activar la seguridad de las transacciones</span><span class="sxs-lookup"><span data-stu-id="56bfb-108">To turn on transaction safety</span></span>  
  
1.  <span data-ttu-id="56bfb-109">Conéctese al servidor principal.</span><span class="sxs-lookup"><span data-stu-id="56bfb-109">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="56bfb-110">Escriba la instrucción Transact-SQL siguiente:</span><span class="sxs-lookup"><span data-stu-id="56bfb-110">Issue the following Transact-SQL statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY FULL  
    ```  
  
     <span data-ttu-id="56bfb-111">donde *\<database>* es el nombre de la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="56bfb-111">where *\<database>* is the name of the mirrored database.</span></span>  
  
### <a name="to-turn-off-transaction-safety"></a><span data-ttu-id="56bfb-112">Para desactivar la seguridad de las transacciones</span><span class="sxs-lookup"><span data-stu-id="56bfb-112">To turn off transaction safety</span></span>  
  
1.  <span data-ttu-id="56bfb-113">Conéctese al servidor principal.</span><span class="sxs-lookup"><span data-stu-id="56bfb-113">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="56bfb-114">Emita la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="56bfb-114">Issue the following statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY OFF  
    ```  
  
     <span data-ttu-id="56bfb-115">donde *\<database>* es la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="56bfb-115">where *\<database>* is the mirrored database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56bfb-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56bfb-116">See Also</span></span>  
 <span data-ttu-id="56bfb-117">[Reflejo de la base de datos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="56bfb-117">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 [<span data-ttu-id="56bfb-118">Database Mirroring Operating Modes</span><span class="sxs-lookup"><span data-stu-id="56bfb-118">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
