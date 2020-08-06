---
title: Configurar una base de datos reflejada para usar la propiedad Trustworthy (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database option
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 6993b076-78ef-453e-b0ea-e341b8e5ee3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd46a08037bcb6eee178a96d84bdab358e5350d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746482"
---
# <a name="set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql"></a><span data-ttu-id="1fff3-102">Configurar una base de datos reflejada para usar la propiedad Trustworthy (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1fff3-102">Set Up a Mirror Database to Use the Trustworthy Property (Transact-SQL)</span></span>
  <span data-ttu-id="1fff3-103">Cuando se realiza una copia de seguridad de una base de datos, la propiedad TRUSTWORTHY de la base de datos se establece en OFF.</span><span class="sxs-lookup"><span data-stu-id="1fff3-103">When a database is backed up, the TRUSTWORTHY database property is set to OFF.</span></span> <span data-ttu-id="1fff3-104">Por lo tanto, TRUSTWORTHY siempre está en OFF en una nueva base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="1fff3-104">Therefore, on a new mirror database TRUSTWORTHY is always OFF.</span></span> <span data-ttu-id="1fff3-105">Si la base de datos necesita marcarse como de confianza después de una conmutación por error, es necesario realizar pasos adicionales de configuración después de iniciar la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="1fff3-105">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1fff3-106">Para obtener información sobre esta propiedad de base de datos, vea [Propiedad de base de datos TRUSTWORTHY](../../relational-databases/security/trustworthy-database-property.md).</span><span class="sxs-lookup"><span data-stu-id="1fff3-106">For information about this database property, see [TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="1fff3-107">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="1fff3-107">Procedure</span></span>  
  
#### <a name="to-setup-a-mirror-database-to-use-the-trustworthy-property"></a><span data-ttu-id="1fff3-108">Para configurar una base de datos reflejada para usar la propiedad Trustworthy</span><span class="sxs-lookup"><span data-stu-id="1fff3-108">To setup a mirror database to use the Trustworthy Property</span></span>  
  
1.  <span data-ttu-id="1fff3-109">En la instancia del servidor principal, compruebe que la base de datos principal tiene habilitada la propiedad Trustworthy.</span><span class="sxs-lookup"><span data-stu-id="1fff3-109">On the principal server instance, verify that the principal database has the Trustworthy property turned on.</span></span>  
  
    ```  
    SELECT name, database_id, is_trustworthy_on FROM sys.databases   
    ```  
  
     <span data-ttu-id="1fff3-110">Para obtener más información, vea [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1fff3-110">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span>  
  
2.  <span data-ttu-id="1fff3-111">Después de iniciar la creación de reflejo, compruebe que la base de datos es actualmente la base de datos principal, que la sesión utiliza un modo de funcionamiento sincrónico y que la sesión ya está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="1fff3-111">After starting mirroring, verify that the database is currently the principal database, the session is using a synchronous operating mode, and the session is already synchronized.</span></span>  
  
    ```  
    SELECT database_id, mirroring_role, mirroring_safety_level_desc, mirroring_state_desc FROM sys.database_mirroring  
    ```  
  
     <span data-ttu-id="1fff3-112">Para obtener más información, vea [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1fff3-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
3.  <span data-ttu-id="1fff3-113">Una vez sincronizada la sesión de creación de reflejo, realice una conmutación manual por error a la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="1fff3-113">Once the mirroring session is synchronized, manually fail over to the mirror database.</span></span>  
  
     <span data-ttu-id="1fff3-114">Puede hacer esto en SQL Server Management Studio o mediante Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="1fff3-114">This can be done in either SQL Server Management Studio or using Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="1fff3-115">Realizar manualmente la conmutación por error de una sesión de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1fff3-115">Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;</span></span>](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md)  
  
    -   [<span data-ttu-id="1fff3-116">Realizar una conmutación por error manualmente de una sesión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1fff3-116">Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](manually-fail-over-a-database-mirroring-session-transact-sql.md)  
  
4.  <span data-ttu-id="1fff3-117">Active la propiedad de base de datos TRUSTWORTHY mediante el siguiente comando ALTER DATABASE:</span><span class="sxs-lookup"><span data-stu-id="1fff3-117">Turn on the trustworthy database property using the following ALTER DATABASE command:</span></span>  
  
    ```  
    ALTER DATABASE <database_name> SET TRUSTWORTHY ON  
    ```  
  
     <span data-ttu-id="1fff3-118">Para obtener más información, vea [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1fff3-118">For more information, see[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
5.  <span data-ttu-id="1fff3-119">Si lo desea, realice la conmutación manual por error para regresar a la base de datos principal original.</span><span class="sxs-lookup"><span data-stu-id="1fff3-119">Optionally, manually failover again to return to the original principal.</span></span>  
  
6.  <span data-ttu-id="1fff3-120">Opcionalmente, cambie al modo asincrónico de alto rendimiento estableciendo SAFETY en OFF y asegurándose de que WITNESS también se ha establecido en OFF.</span><span class="sxs-lookup"><span data-stu-id="1fff3-120">Optionally, switch to asynchronous, high-performance mode by setting SAFETY to OFF and ensuring that WITNESS is also set to OFF.</span></span>  
  
     <span data-ttu-id="1fff3-121">En Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="1fff3-121">In Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="1fff3-122">Cambiar la seguridad de las transacciones en una sesión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1fff3-122">Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md)  
  
    -   [<span data-ttu-id="1fff3-123">Quitar el testigo de una sesión de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1fff3-123">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
     <span data-ttu-id="1fff3-124">En SQL Server Management Studio:</span><span class="sxs-lookup"><span data-stu-id="1fff3-124">In SQL Server Management Studio:</span></span>  
  
    -   [<span data-ttu-id="1fff3-125">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1fff3-125">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="1fff3-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1fff3-126">See Also</span></span>  
 <span data-ttu-id="1fff3-127">[Propiedad de base de datos TRUSTWORTHY](../../relational-databases/security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="1fff3-127">[TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="1fff3-128">Establecer una base de datos reflejada cifrada</span><span class="sxs-lookup"><span data-stu-id="1fff3-128">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
