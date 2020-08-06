---
title: Copias de seguridad y restauración de publicadores de Oracle| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], Oracle publishing
- backups [SQL Server replication], Oracle publishing
- Oracle publishing [SQL Server replication], backup and restore
- restoring [SQL Server replication], Oracle publishing
ms.assetid: e5f181d0-cacf-442b-8b7a-202b3cfc358b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6b994c34e4f4bebc010fe6d71bbd43f6e557cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662820"
---
# <a name="backup-and-restore-for-oracle-publishers"></a><span data-ttu-id="533d0-102">Copias de seguridad y restauración de publicadores de Oracle</span><span class="sxs-lookup"><span data-stu-id="533d0-102">Backup and Restore for Oracle Publishers</span></span>
  <span data-ttu-id="533d0-103">Siga estas instrucciones para hacer copias de seguridad y restaurar:</span><span class="sxs-lookup"><span data-stu-id="533d0-103">Follow these guidelines when backing up and restoring:</span></span>  
  
-   <span data-ttu-id="533d0-104">Asegúrese de que el Agente de registro del LOG no se ejecuta y que no se produce ninguna otra actividad de base de datos en las tablas publicadas cuando esté haciendo copias de seguridad del publicador.</span><span class="sxs-lookup"><span data-stu-id="533d0-104">Ensure the Log Reader Agent does not run and that other database activity on the published tables does not occur while the Publisher is being backed up.</span></span>  
  
-   <span data-ttu-id="533d0-105">Haga copias de seguridad del publicador y del distribuidor a la vez.</span><span class="sxs-lookup"><span data-stu-id="533d0-105">Backup up the Publisher and Distributor at the same time.</span></span>  
  
-   <span data-ttu-id="533d0-106">Si es necesario restaurar el publicador o el distribuidor, reinicialice todas las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="533d0-106">If the Publisher or Distributor must be restored, reinitialize all subscriptions.</span></span>  
  
-   <span data-ttu-id="533d0-107">Para restaurar un suscriptor desde una copia de seguridad (sin tener que reinicializar todas las suscripciones), las transacciones entregadas en la base de datos del distribuidor después de haber realizado la copia de seguridad de la base de datos de la última suscripción deben estar todavía disponibles.</span><span class="sxs-lookup"><span data-stu-id="533d0-107">To restore a Subscriber from a backup (without having to reinitialize subscriptions), the transactions delivered to the distribution database after the last subscription database backup was completed must still be available.</span></span> <span data-ttu-id="533d0-108">El período de tiempo que las transacciones están disponibles depende de la configuración de retención de la distribución.</span><span class="sxs-lookup"><span data-stu-id="533d0-108">The length of time transactions are available depends on distribution retention settings.</span></span> <span data-ttu-id="533d0-109">Para más información, vea [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md) (Desactivación y expiración de las suscripciones).</span><span class="sxs-lookup"><span data-stu-id="533d0-109">For information on these settings, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="533d0-110">Si el publicador o el distribuidor no están sincronizados como resultado de una restauración de la base de datos, los agentes de replicación registran mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="533d0-110">If the Publisher or Distributor becomes out of sync as the result of a database restore, the replication agents log error messages.</span></span> <span data-ttu-id="533d0-111">En ese caso, debe quitar y volver a crear todas las publicaciones y suscripciones relevantes:</span><span class="sxs-lookup"><span data-stu-id="533d0-111">At this point, you must drop and recreate all relevant publications and subscriptions:</span></span>  
  
    1.  <span data-ttu-id="533d0-112">Genere script para la definición de las publicaciones y las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="533d0-112">Script the definition of the publications and subscriptions.</span></span> <span data-ttu-id="533d0-113">Para más información, consulte [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="533d0-113">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
         <span data-ttu-id="533d0-114">Si la definición de las publicaciones ha cambiado entre las versiones de los estados del publicador y el distribuidor, será necesario que modifique los scripts.</span><span class="sxs-lookup"><span data-stu-id="533d0-114">If the definition of the publications has changed between the versions of the Publisher and Distributor states, you will need to modify the scripts.</span></span>  
  
    2.  <span data-ttu-id="533d0-115">Quite las publicaciones y las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="533d0-115">Drop the publications and subscriptions.</span></span>  
  
    3.  <span data-ttu-id="533d0-116">Ejecute los scripts creados en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="533d0-116">Run the scripts created in step 1.</span></span>  
  
     <span data-ttu-id="533d0-117">Si es necesario quitar y volver a configurar el publicador, quite el sinónimo público **MSSQLSERVERDISTRIBUTOR** y el usuario de replicación de Oracle configurado con la opción **CASCADE** para quitar todos los objetos de la replicación del publicador de Oracle.</span><span class="sxs-lookup"><span data-stu-id="533d0-117">If the Publisher must be dropped and reconfigured, drop the **MSSQLSERVERDISTRIBUTOR** public synonym and the configured Oracle replication user with the **CASCADE** option to remove all replication objects from the Oracle Publisher.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="533d0-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="533d0-118">See Also</span></span>  
 <span data-ttu-id="533d0-119">[Hacer copias de seguridad y restaurar bases de datos replicadas](../administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="533d0-119">[Back Up and Restore Replicated Databases](../administration/back-up-and-restore-replicated-databases.md) </span></span>  
 <span data-ttu-id="533d0-120">[Configurar un publicador de Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="533d0-120">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="533d0-121">Información general de la publicación de Oracle</span><span class="sxs-lookup"><span data-stu-id="533d0-121">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
