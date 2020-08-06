---
title: Configurar la distribución | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], distribution
- distribution configuration [SQL Server replication]
- remote Distributors [SQL Server replication]
- transactional replication, configuring distribution
- distribution databases [SQL Server replication], sizing
- Distributors [SQL Server replication], configuring
- distribution databases [SQL Server replication], about distribution databases
- distribution databases [SQL Server replication]
- merge replication [SQL Server replication], configuring distribution
ms.assetid: 94d52169-384e-4885-84eb-2304e967d9f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b0378fe285ba57e1420b7e6bebf5e2e6fe13d29e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670938"
---
# <a name="configure-distribution"></a><span data-ttu-id="54833-102">Configurar la distribución</span><span class="sxs-lookup"><span data-stu-id="54833-102">Configure Distribution</span></span>
  <span data-ttu-id="54833-103">El distribuidor es un servidor que contiene la base de datos de distribución, que almacena metadatos y datos del historial de todos los tipos de replicación y transacciones para la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="54833-103">The Distributor is a server that contains the distribution database, which stores metadata and history data for all types of replication and transactions for transactional replication.</span></span> <span data-ttu-id="54833-104">Para configurar la replicación, debe configurar un distribuidor.</span><span class="sxs-lookup"><span data-stu-id="54833-104">To set up replication, you must configure a Distributor.</span></span> <span data-ttu-id="54833-105">Un publicador solamente se puede asignar a una instancia del distribuidor, aunque varios publicadores pueden compartir un distribuidor.</span><span class="sxs-lookup"><span data-stu-id="54833-105">Each Publisher can be assigned to only a single Distributor instance, but multiple publishers can share a Distributor.</span></span> <span data-ttu-id="54833-106">El distribuidor utiliza estos recursos adicionales en el servidor en el que se encuentra:</span><span class="sxs-lookup"><span data-stu-id="54833-106">The Distributor uses these additional resources on the server where it is located:</span></span>  
  
-   <span data-ttu-id="54833-107">Espacio de disco adicional, si los archivos de instantáneas de la publicación se almacenan en el distribuidor (la situación habitual)</span><span class="sxs-lookup"><span data-stu-id="54833-107">Additional disk space if the snapshot files for the publication are stored on the Distributor (which they typically are).</span></span>  
  
-   <span data-ttu-id="54833-108">Espacio de disco adicional para almacenar la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="54833-108">Additional disk space to store the distribution database.</span></span>  
  
-   <span data-ttu-id="54833-109">Uso adicional del procesador por los agentes de replicación para las suscripciones de inserción que se ejecutan en el distribuidor</span><span class="sxs-lookup"><span data-stu-id="54833-109">Additional processor usage by replication agents for push subscriptions running on the Distributor.</span></span>  
  
 <span data-ttu-id="54833-110">El servidor seleccionado como distribuidor debe disponer del espacio en disco y la capacidad de proceso adecuados para la replicación y cualquier otra actividad asignada a ese servidor.</span><span class="sxs-lookup"><span data-stu-id="54833-110">The server you select as the Distributor should have adequate disk space and processor power to support replication and any other activities on that server.</span></span> <span data-ttu-id="54833-111">Al configurar el distribuidor, debe especificar:</span><span class="sxs-lookup"><span data-stu-id="54833-111">When you configure the Distributor, you specify the following:</span></span>  
  
-   <span data-ttu-id="54833-112">Una carpeta de instantáneas que se utiliza, de manera predeterminada, para todos los publicadores que usen este distribuidor.</span><span class="sxs-lookup"><span data-stu-id="54833-112">A snapshot folder, which is used, by default, for all Publishers that use this Distributor.</span></span> <span data-ttu-id="54833-113">Asegúrese de que la carpeta esté compartida y tenga establecidos los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="54833-113">Ensure that this folder is already shared and has the appropriate permissions set.</span></span> <span data-ttu-id="54833-114">Para obtener más información, vea [Proteger la carpeta de instantáneas](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="54833-114">For more information, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span>  
  
-   <span data-ttu-id="54833-115">El nombre y la ubicación de los archivos de la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="54833-115">A name and file locations for the distribution database.</span></span> <span data-ttu-id="54833-116">No se puede cambiar el nombre de la base de datos de distribución una vez creada.</span><span class="sxs-lookup"><span data-stu-id="54833-116">The distribution database cannot be renamed after it is created.</span></span> <span data-ttu-id="54833-117">Si desea utilizar un nombre distinto para la base de datos, debe deshabilitar la distribución y volver a configurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="54833-117">To use a different name for the database, you must disable distribution and reconfigure it.</span></span>  
  
-   <span data-ttu-id="54833-118">Todos los publicadores autorizados para utilizar el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="54833-118">Any Publishers authorized to use the Distributor.</span></span> <span data-ttu-id="54833-119">Si especifica otros publicadores además de la instancia en la que se ejecuta el distribuidor, debe especificar también una contraseña para las conexiones entre los publicadores y el distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="54833-119">If you specify Publishers other than the instance on which the Distributor runs, you must also specify a password for the connections the Publishers make to the remote Distributor.</span></span>  
  
 <span data-ttu-id="54833-120">Para la replicación transaccional después de configurar la distribución, se recomienda:</span><span class="sxs-lookup"><span data-stu-id="54833-120">For transactional replication, after you configure distribution, we recommend that you:</span></span>  
  
-   <span data-ttu-id="54833-121">Ajustar la base de datos de distribución a un tamaño apropiado.</span><span class="sxs-lookup"><span data-stu-id="54833-121">Size the distribution database appropriately.</span></span> <span data-ttu-id="54833-122">Pruebe la replicación con una carga típica para el sistema con el fin de determinar cuánto espacio se necesita para almacenar comandos.</span><span class="sxs-lookup"><span data-stu-id="54833-122">Test replication with a typical load for your system to determine how much space is required to store commands.</span></span> <span data-ttu-id="54833-123">Asegúrese de que la base de datos es lo suficientemente grande para almacenar comandos sin recurrir al crecimiento automático con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="54833-123">Ensure the database is large enough to store commands without having to auto-grow frequently.</span></span> <span data-ttu-id="54833-124">Para más información sobre cómo cambiar el tamaño de una base de datos, vea [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54833-124">For more information about changing the size of a database, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="54833-125">Configurar la opción **sync with backup** en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="54833-125">Set the **sync with backup** option on the distribution database.</span></span> <span data-ttu-id="54833-126">Para más información, vea [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md) (Estrategias para hacer copias de seguridad y restaurar replicación de instantáneas o replicación transaccional) y [Enable Coordinated Backups for Transactional Replication &#40;Replication Transact-SQL Programming&#41;](administration/enable-coordinated-backups-for-transactional-replication.md) (Habilitar copias de seguridad coordinadas para la replicación transaccional &#40;programación de la replicación con Transact-SQL&#41;).</span><span class="sxs-lookup"><span data-stu-id="54833-126">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md) and [Enable Coordinated Backups for Transactional Replication &#40;Replication Transact-SQL Programming&#41;](administration/enable-coordinated-backups-for-transactional-replication.md).</span></span>  
  
## <a name="local-and-remote-distributors"></a><span data-ttu-id="54833-127">Distribuidores locales y remotos</span><span class="sxs-lookup"><span data-stu-id="54833-127">Local and Remote Distributors</span></span>  
 <span data-ttu-id="54833-128">De forma predeterminada, el distribuidor es el mismo servidor que el publicador (un distribuidor local), aunque también puede ser un servidor distinto del publicador (un distribuidor remoto).</span><span class="sxs-lookup"><span data-stu-id="54833-128">By default, the Distributor is the same server as the Publisher (a local Distributor), but it can also be a separate server from the Publisher (a remote Distributor).</span></span> <span data-ttu-id="54833-129">Por lo general, se elige un distribuidor remoto cuando se desea:</span><span class="sxs-lookup"><span data-stu-id="54833-129">Typically, you would choose to use a remote Distributor if you want to:</span></span>  
  
-   <span data-ttu-id="54833-130">Descargar el proceso en otro equipo para que la replicación tenga un impacto mínimo en el publicador (por ejemplo, si el publicador es un servidor OLTP).</span><span class="sxs-lookup"><span data-stu-id="54833-130">Offload processing to another computer if you want minimal impact from replication on the Publisher (for example, if the Publisher is an OLTP server).</span></span>  
  
-   <span data-ttu-id="54833-131">Configurar un distribuidor centralizado para varios publicadores.</span><span class="sxs-lookup"><span data-stu-id="54833-131">Configure a centralized Distributor for multiple Publishers.</span></span>  
  
 <span data-ttu-id="54833-132">Los distribuidores remotos son más frecuentes en la replicación transaccional que en la replicación de mezcla por dos motivos:</span><span class="sxs-lookup"><span data-stu-id="54833-132">Remote Distributors are more common in transactional replication than they are in merge replication for two reasons:</span></span>  
  
-   <span data-ttu-id="54833-133">El distribuidor tiene un rol más amplio en la replicación transaccional porque todas las transacciones replicadas se escriben y se leen en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="54833-133">The Distributor plays a larger role in transactional replication because all replicated transactions are written to and read from the distribution database.</span></span>  
  
-   <span data-ttu-id="54833-134">Las topologías de replicación de mezcla usan por lo general suscripciones de extracción, de forma que los agentes se ejecutan en cada suscriptor en lugar de ejecutarse todos en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="54833-134">Merge replication topologies typically use pull subscriptions, so agents run at each Subscriber, rather than all running at the Distributor.</span></span> <span data-ttu-id="54833-135">Para obtener más información, vea [Suscribirse a publicaciones](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="54833-135">For more information, see [Subscribe to Publications](subscribe-to-publications.md).</span></span> <span data-ttu-id="54833-136">En la mayoría de los casos, debe usar un distribuidor local para la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="54833-136">In most cases, you should use a local Distributor for merge replication.</span></span>  
  
 <span data-ttu-id="54833-137">Para configurar la publicación y la distribución, vea [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="54833-137">To configure publishing and distribution, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  
  
 <span data-ttu-id="54833-138">Para modificar las propiedades del distribuidor y del publicador, vea [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="54833-138">To modify Publisher and Distributor properties, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54833-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54833-139">See Also</span></span>  
 <span data-ttu-id="54833-140">[Publicar datos y objetos de base de datos](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="54833-140">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="54833-141">Proteger el distribuidor</span><span class="sxs-lookup"><span data-stu-id="54833-141">Secure the Distributor</span></span>](security/secure-the-distributor.md)  
  
  
