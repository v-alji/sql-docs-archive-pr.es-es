---
title: Introducción a la nube híbrida de SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6dc42752-1fcd-4ab9-8194-c3001ea342e7
author: rothja
ms.author: jroth
ms.openlocfilehash: b3ff6773752570b9afc83764ca0f973eb22764da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674297"
---
# <a name="introduction-to-sql-server-2014-hybrid-cloud"></a><span data-ttu-id="c0fda-102">Introducción a la nube híbrida de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c0fda-102">Introduction to SQL Server 2014 Hybrid Cloud</span></span>
 <span data-ttu-id="c0fda-103">La mayoría de las aplicaciones presentan algunos desafíos importantes, como alta eficacia, valor empresarial, configuraciones de hardware complejas, picos masivos a petición, y cumplimiento con las normativas del sector y corporativas.</span><span class="sxs-lookup"><span data-stu-id="c0fda-103">Most applications have some key challenges, such as high efficiency, business value, complex hardware configurations, massive peaks on demand, and complying with industry and corporate regulations.</span></span> <span data-ttu-id="c0fda-104">Tener en cuenta todos estos factores y generar una tecnología de clase empresarial puede resultar muy complicado.</span><span class="sxs-lookup"><span data-stu-id="c0fda-104">Considering all these factors and building an enterprise-grade technology can be very challenging.</span></span> <span data-ttu-id="c0fda-105">La estrategia de nube híbrida de Microsoft proporciona compatibilidad con los entornos tradicional, de nube privada, de nube pública y de nube híbrida para superar estos desafíos.</span><span class="sxs-lookup"><span data-stu-id="c0fda-105">Microsoft Hybrid Cloud Strategy provides support for traditional, private cloud, public cloud, and hybrid cloud environments to overcome these key challenges.</span></span> 
 
 <span data-ttu-id="c0fda-106">Cuando su empresa requiere una infraestructura de TI flexible que se pueda escalar a petición, puede crear una nube privada en su centro de datos o en una nube pública en centros de datos globales de Azure.</span><span class="sxs-lookup"><span data-stu-id="c0fda-106">When your business requires a flexible IT infrastructure that can scale on demand, you can build a private cloud in your data center or a public cloud in Azure global data centers.</span></span> <span data-ttu-id="c0fda-107">Al extender su centro de datos a la nube pública, se crea un modelo de nube híbrida.</span><span class="sxs-lookup"><span data-stu-id="c0fda-107">When you extend your data center to meet the public cloud, you build a hybrid cloud model.</span></span> 
 
 <span data-ttu-id="c0fda-108">En este tema se presentan las características de SQL Server 2014 que admiten escenarios de nube híbrida.</span><span class="sxs-lookup"><span data-stu-id="c0fda-108">This topic introduces the SQL Server 2014 features that support Hybrid Cloud scenarios.</span></span> <span data-ttu-id="c0fda-109">Para obtener información detallada sobre la estrategia de nube híbrida de Microsoft y SQL Server, vea el sitio web [TI híbrida de SQL Server](https://www.microsoft.com/sqlserver/solutions-technologies/hybrid-It.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c0fda-109">For detailed information on Microsoft Hybrid Cloud Strategy and SQL Server, see [SQL Server Hybrid IT](https://www.microsoft.com/sqlserver/solutions-technologies/hybrid-It.aspx) web site.</span></span> 
 
## <a name="sql-server-azure-and-hybrid-cloud"></a><span data-ttu-id="c0fda-110">SQL Server, Azure y la nube híbrida</span><span class="sxs-lookup"><span data-stu-id="c0fda-110">SQL Server, Azure, and Hybrid Cloud</span></span> 
 <span data-ttu-id="c0fda-111">Con las tecnologías de Microsoft, puede ejecutar código tanto de forma local como en la nube, en la nube con datos locales o completamente en la nube aprovechando más de un centro de datos.</span><span class="sxs-lookup"><span data-stu-id="c0fda-111">By using Microsoft technologies, you can run code both on-premises and in the cloud, run in the cloud using on-premises data, or run entirely in the cloud leveraging more than one data center.</span></span> <span data-ttu-id="c0fda-112">Por tanto, puede mover sus aplicaciones a la nube a su propio ritmo mientras conserva el valor de las inversiones de TI existentes.</span><span class="sxs-lookup"><span data-stu-id="c0fda-112">Therefore, you can move your applications to the cloud at your own pace while preserving the value of existing legacy IT investments.</span></span> 
 
 <span data-ttu-id="c0fda-113">En este artículo, nos centraremos en los escenarios de nube híbrida que abarcan las ofertas de SQL Server local a la nube pública de Azure: [SQL Server en Azure virtual machines](https://msdn.microsoft.com/library/azure/jj823132.aspx) y [Azure Storage](https://www.azure.com/documentation/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="c0fda-113">In this article, we'll focus on the hybrid cloud scenarios that span from on-premises SQL Server to Azure public cloud offerings: [SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/azure/jj823132.aspx) and [Azure Storage](https://www.azure.com/documentation/services/storage/).</span></span> <span data-ttu-id="c0fda-114">En concreto, trataremos los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0fda-114">Specifically, we'll discuss the following scenarios:</span></span> 
 
-  [<span data-ttu-id="c0fda-115">Copia de seguridad y restauración de bases de datos a y desde Azure Storage</span><span class="sxs-lookup"><span data-stu-id="c0fda-115">Backup and Restore Databases to/from Azure Storage</span></span>](../../2014/getting-started/introduction-to-sql-server-2014-hybrid-cloud.md#backup) 
 
-  [<span data-ttu-id="c0fda-116">Mantenimiento de réplicas de base de datos en Azure Virtual Machines</span><span class="sxs-lookup"><span data-stu-id="c0fda-116">Maintain Database Replicas on Azure Virtual Machines</span></span>](../../2014/getting-started/introduction-to-sql-server-2014-hybrid-cloud.md#replica) 
 
-  [<span data-ttu-id="c0fda-117">Almacenar archivos de datos de SQL Server en Azure Storage</span><span class="sxs-lookup"><span data-stu-id="c0fda-117">Store SQL Server Data Files in Azure Storage</span></span>](../../2014/getting-started/introduction-to-sql-server-2014-hybrid-cloud.md#store) 
 
-  [<span data-ttu-id="c0fda-118">Migre las bases de datos de SQL Server existentes a Azure Virtual Machines</span><span class="sxs-lookup"><span data-stu-id="c0fda-118">Migrate existing SQL Server databases to Azure Virtual Machines</span></span>](../../2014/getting-started/introduction-to-sql-server-2014-hybrid-cloud.md#migrate) 
 
### <a name="hybrid-cloud-scenarios-for-sql-server-and-microsoft-azure"></a><span data-ttu-id="c0fda-119">Escenarios de nube híbrida para SQL Server y Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="c0fda-119">Hybrid Cloud Scenarios for SQL Server and Microsoft Azure</span></span> 
 
#### <a name="backup-and-restore-databases-tofrom-azure-storage"></a><a name="backup"></a><span data-ttu-id="c0fda-120">Copia de seguridad y restauración de bases de datos a y desde Azure Storage</span><span class="sxs-lookup"><span data-stu-id="c0fda-120">Backup and Restore Databases to/from Azure Storage</span></span> 
 <span data-ttu-id="c0fda-121">Una de las tareas más fundamentales de los administradores consiste en hacer copia de seguridad y restaurar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c0fda-121">One of the most fundamental administrator tasks is backing up and restoring databases.</span></span> <span data-ttu-id="c0fda-122">Con SQL Server y Azure, puede realizar copias de seguridad de las bases de datos en la nube de forma segura.</span><span class="sxs-lookup"><span data-stu-id="c0fda-122">With SQL Server and Azure, you can safely backup your databases in the cloud.</span></span> 
 
 <span data-ttu-id="c0fda-123">Entre las ventajas principales de usar las capacidades de copia de seguridad y restauración de SQL Server con Azure Storage como destino de copia de seguridad se incluyen:</span><span class="sxs-lookup"><span data-stu-id="c0fda-123">The key benefits of using the backup and restore capabilities of SQL Server with Azure Storage as a backup destination include:</span></span> 
 
-  <span data-ttu-id="c0fda-124">Almacenamiento ilimitado de bajo costo</span><span class="sxs-lookup"><span data-stu-id="c0fda-124">Limitless low-cost storage</span></span> 
 
-  <span data-ttu-id="c0fda-125">Almacenamiento de alta disponibilidad (replicado geográficamente para asegurar que no haya pérdida de datos)</span><span class="sxs-lookup"><span data-stu-id="c0fda-125">Highly available storage (geographically replicated to ensure no data loss)</span></span> 
 
-  <span data-ttu-id="c0fda-126">Almacenamiento externo que puede admitir requisitos de cumplimiento y de recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="c0fda-126">Off-site storage that can support disaster recovery and compliance requirements</span></span> 
 
-  <span data-ttu-id="c0fda-127">Proceso remoto de copia de seguridad y restauración simplificado</span><span class="sxs-lookup"><span data-stu-id="c0fda-127">Simplified remote backup and restore process</span></span> 
 
 <span data-ttu-id="c0fda-128">A continuación se muestra una lista de capacidades de copia de seguridad y restauración de SQL Server para escenarios en la nube y locales:</span><span class="sxs-lookup"><span data-stu-id="c0fda-128">The following is a list of backup and restore capabilities of SQL Server for cloud and on-premises scenarios:</span></span> 
 
-  <span data-ttu-id="c0fda-129">La característica [SQL Server copia de seguridad en dirección URL](../relational-databases/backup-restore/sql-server-backup-to-url.md) le permite realizar una copia de seguridad en Azure Storage especificando la dirección URL como destino de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c0fda-129">The [SQL Server Backup to URL](../relational-databases/backup-restore/sql-server-backup-to-url.md) feature enables you to back up to Azure Storage by specifying URL as the backup destination.</span></span> <span data-ttu-id="c0fda-130">Con esta característica, puede realizar una copia de seguridad manual o configurar su propia estrategia de copia de seguridad como haría para un almacenamiento local u otras opciones externas.</span><span class="sxs-lookup"><span data-stu-id="c0fda-130">With this feature, you can perform a manual backup or configure your own backup strategy like you would for a local storage or other off-site options.</span></span> 
 
-  <span data-ttu-id="c0fda-131">La característica de [cifrado de copia de seguridad](../relational-databases/backup-restore/backup-encryption.md) le permite cifrar los datos mientras crea una copia de seguridad para los destinos de almacenamiento: local y Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="c0fda-131">The [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md) feature enables you to encrypt the data while creating a backup for your storage destinations: on-premises and Azure Storage.</span></span> 
 
-  <span data-ttu-id="c0fda-132">La característica de [compresión de copia de seguridad (SQL Server)](../relational-databases/backup-restore/backup-compression-sql-server.md) le permite crear una copia de seguridad, que es menor que una copia de seguridad sin comprimir de los mismos datos.</span><span class="sxs-lookup"><span data-stu-id="c0fda-132">The [Backup Compression (SQL Server)](../relational-databases/backup-restore/backup-compression-sql-server.md) feature enables you to create a backup, which is smaller than an uncompressed backup of the same data.</span></span> <span data-ttu-id="c0fda-133">La compresión de una copia de seguridad necesita menos E/S de dispositivo, lo que suele aumentar la velocidad considerablemente.</span><span class="sxs-lookup"><span data-stu-id="c0fda-133">Compressing a backup needs less device I/O and therefore usually increases backup speed significantly.</span></span> <span data-ttu-id="c0fda-134">Esto puede aportar grandes ventajas al almacenar archivos de copia de seguridad en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="c0fda-134">This can bring great benefits when storing backup files in Azure Storage.</span></span> 
 
-  <span data-ttu-id="c0fda-135">La característica [SQL Server copia de seguridad administrada en Azure](https://msdn.microsoft.com/library/dn606152(v=sql.120).aspx) permite hacer copia de seguridad automáticamente de las bases de datos SQL Server en [Azure Storage](https://www.azure.com/documentation/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="c0fda-135">The [SQL Server Managed Backup to Azure](https://msdn.microsoft.com/library/dn606152(v=sql.120).aspx) feature enables you to automatically backup SQL Server databases to [Azure Storage](https://www.azure.com/documentation/services/storage/).</span></span> <span data-ttu-id="c0fda-136">Con esta característica, puede configurar SQL Server para administrar la estrategia de copia de seguridad y programar las copias de seguridad de una sola base de datos, o de varias, o establecer los valores predeterminados en el nivel de instancia.</span><span class="sxs-lookup"><span data-stu-id="c0fda-136">With this feature, you can configure SQL Server to manage the backup strategy and schedule backups for a single database, or several databases, or set defaults at the instance level.</span></span> 
 
-  <span data-ttu-id="c0fda-137">La [herramienta copia de seguridad de SQL Server en Azure](https://www.microsoft.com/download/details.aspx?id=40740) permite que la copia de seguridad Azure BLOB Storage y cifra y comprime SQL Server copias de seguridad almacenadas localmente o en la nube.</span><span class="sxs-lookup"><span data-stu-id="c0fda-137">The [SQL Server Backup to Azure Tool](https://www.microsoft.com/download/details.aspx?id=40740) enables backup to Azure Blob Storage and encrypts and compresses SQL Server backups stored locally or in the cloud.</span></span> <span data-ttu-id="c0fda-138">Esta herramienta hace posible tener una única estrategia de copia de seguridad en la nube en varias versiones de SQL Server, como SQL Server 2005, 2008, 2008 R2 y 2014.</span><span class="sxs-lookup"><span data-stu-id="c0fda-138">This tool enables a single cloud backup strategy across for several versions of SQL Server, such as SQL Server 2005, 2008, 2008 R2, and 2014.</span></span> 
 
#### <a name="maintain-database-replicas-on-azure-virtual-machines"></a><a name="replica"></a><span data-ttu-id="c0fda-139">Mantenimiento de réplicas de base de datos en Azure Virtual Machines</span><span class="sxs-lookup"><span data-stu-id="c0fda-139">Maintain Database Replicas on Azure Virtual Machines</span></span> 
 <span data-ttu-id="c0fda-140">Tener una solución de recuperación ante desastres estable para las bases de datos es esencial para el éxito de su empresa.</span><span class="sxs-lookup"><span data-stu-id="c0fda-140">Having a stable disaster recovery solution for your databases is essential for your business's success.</span></span> <span data-ttu-id="c0fda-141">La mayoría de los clientes necesitan configurar un sitio de recuperación ante desastres y adquirir hardware adicional para las réplicas de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c0fda-141">Most customers need to configure a disaster recovery site and purchase additional hardware for database replicas.</span></span> <span data-ttu-id="c0fda-142">Con SQL Server y Azure, puede mantener una o varias réplicas de las bases de datos en la nube.</span><span class="sxs-lookup"><span data-stu-id="c0fda-142">With SQL Server and Azure, you can maintain one or more replicas of your databases in the cloud.</span></span> 
 
 <span data-ttu-id="c0fda-143">Entre las ventajas principales de mantener réplicas secundarias en Azure se incluyen:</span><span class="sxs-lookup"><span data-stu-id="c0fda-143">The key benefits of maintaining secondary replicas in Azure include:</span></span> 
 
-  <span data-ttu-id="c0fda-144">Solución de bajo costo de recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="c0fda-144">Low-cost disaster recovery solution</span></span> 
 
-  <span data-ttu-id="c0fda-145">Conmutación por error transparente de la aplicación</span><span class="sxs-lookup"><span data-stu-id="c0fda-145">Transparent application failover</span></span> 
 
-  <span data-ttu-id="c0fda-146">Réplicas disponibles para descargar las cargas de trabajo de lectura y las copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="c0fda-146">Available replicas to offload read workloads and backups</span></span> 
 
 <span data-ttu-id="c0fda-147">Puede mantener las réplicas secundarias en Azure mediante cualquiera de las técnicas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0fda-147">You can maintain secondary replicas in Azure by using any of the following techniques:</span></span> 
 
-  <span data-ttu-id="c0fda-148">El [Asistente para agregar réplica de Azure](https://msdn.microsoft.com/library/dn463980\(v=sql.120\).aspx) permite implementar una o varias réplicas de las bases de datos en una máquina virtual de Azure para la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="c0fda-148">The [Add Azure Replica Wizard](https://msdn.microsoft.com/library/dn463980\(v=sql.120\).aspx) allows you to deploy one or more replicas of your databases to a virtual machine in Azure for disaster recovery.</span></span> 
 
-  <span data-ttu-id="c0fda-149">Grupos de disponibilidad AlwaysOn, creación de reflejo de la base de datos y trasvase de registros son las tecnologías más comunes que puede usar para satisfacer las necesidades de alta disponibilidad y recuperación ante desastres de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0fda-149">AlwaysOn Availability Groups, database mirroring, and log shipping are the most common technologies that you can use to address your application's high availability and disaster recovery needs.</span></span> <span data-ttu-id="c0fda-150">Para obtener más información, consulte [alta disponibilidad y recuperación ante desastres para SQL Server en Azure virtual machines](https://msdn.microsoft.com/library/azure/jj870962.aspx).</span><span class="sxs-lookup"><span data-stu-id="c0fda-150">For information, see [High Availability and Disaster Recovery for SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/azure/jj870962.aspx).</span></span> 
 
#### <a name="store-sql-server-data-files-in-azure-storage"></a><a name="store"></a><span data-ttu-id="c0fda-151">Almacenar archivos de datos de SQL Server en Azure Storage</span><span class="sxs-lookup"><span data-stu-id="c0fda-151">Store SQL Server Data Files in Azure Storage</span></span> 
 <span data-ttu-id="c0fda-152">El almacenamiento de archivos de datos de SQL Server local en Azure Storage proporciona un almacenamiento fuera de la ubicación flexible, confiable e ilimitado para las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c0fda-152">Storing on-premises SQL Server data files in Azure Storage provides a flexible, reliable, and limitless off-site storage for your databases.</span></span> <span data-ttu-id="c0fda-153">A partir de SQL Server 2014, puede usar [SQL Server archivos de datos en Miceosoft Azure](https://docs.microsoft.com/sql/relational-databases/databases/sql-server-data-files-in-microsoft-azure) para almacenar archivos de base de datos de SQL Server en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="c0fda-153">Starting with SQL Server 2014, you can use [SQL Server Data Files in Miceosoft Azure](https://docs.microsoft.com/sql/relational-databases/databases/sql-server-data-files-in-microsoft-azure) to store SQL Server database files in Azure Storage.</span></span> <span data-ttu-id="c0fda-154">Con esta característica, puede trasladar los archivos de datos y de registro de la base de datos local a Azure Storage, manteniendo el nodo de proceso de SQL Server ejecutándose en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="c0fda-154">With this feature, you can move data and log files from on-premises database into Azure Storage, while keeping the compute node of SQL Server running on-premises.</span></span> <span data-ttu-id="c0fda-155">Esta característica permite tener una capacidad de almacenamiento ilimitada en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="c0fda-155">This feature enables you to have unlimited storage capacity in Azure Storage.</span></span> 
 
 <span data-ttu-id="c0fda-156">Entre las ventajas principales de almacenar archivos de datos de SQL Server Azure Storage se incluyen:</span><span class="sxs-lookup"><span data-stu-id="c0fda-156">The key benefits of storing SQL Server data files Azure Storage include:</span></span> 
 
-  <span data-ttu-id="c0fda-157">Almacenamiento ilimitado de bajo costo en Azure Storage</span><span class="sxs-lookup"><span data-stu-id="c0fda-157">Unlimited low-cost storage in Azure Storage</span></span> 
 
-  <span data-ttu-id="c0fda-158">Más indicado para traspasar las cargas de trabajo de lectura históricas en la nube con el fin de admitir aplicaciones de informes locales</span><span class="sxs-lookup"><span data-stu-id="c0fda-158">Best suited for offloading historical read workloads to the cloud to support on-premises reporting applications</span></span> 
 
-  <span data-ttu-id="c0fda-159">Facilite la recuperación ante desastres separando la instancia de proceso (una instancia de SQL Server) y los datos (archivos de datos de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="c0fda-159">Facilitate disaster recovery by separating the compute instance (an instance of SQL Server) and the data (SQL Server data files).</span></span> <span data-ttu-id="c0fda-160">Esto le permite adjuntar fácilmente la base de datos a otra instancia de SQL Server en un entorno local o en una máquina virtual de Azure en caso de desastre.</span><span class="sxs-lookup"><span data-stu-id="c0fda-160">This allows you to easily attach the database to another instance of SQL Server in an on-premises environment or in an Azure virtual machine in case of a disaster.</span></span> 
 
#### <a name="migrate-existing-sql-server-databases-to-azure-virtual-machines"></a><a name="migrate"></a><span data-ttu-id="c0fda-161">Migre las bases de datos de SQL Server existentes a Azure Virtual Machines</span><span class="sxs-lookup"><span data-stu-id="c0fda-161">Migrate existing SQL Server databases to Azure Virtual Machines</span></span> 
 <span data-ttu-id="c0fda-162">La informática en nube aporta algunas ventajas importantes a las empresas, como la disponibilidad de recursos virtualizados ilimitados según un modelo de pago por uso; puede aprovechar los centros de datos en la nube que están disponibles de forma pública en lugar de crear y administrar sus propios centros de datos, por lo que puede reducir los costos de TI y de hardware.</span><span class="sxs-lookup"><span data-stu-id="c0fda-162">The cloud computing brings some key benefits to enterprises, such as limitless virtualized resources are available for you on a pay-per-use basis, you can leverage publicly available cloud data centers rather than building out and manage data centers on your own, and therefore you can lower IT and hardware costs.</span></span> 
 
 <span data-ttu-id="c0fda-163">Con [SQL Server en azure virtual machines](https://msdn.microsoft.com/library/azure/jj823132.aspx), puede trasladar las aplicaciones locales existentes a Azure con cambios mínimos en el código.</span><span class="sxs-lookup"><span data-stu-id="c0fda-163">With [SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/azure/jj823132.aspx), you can move the existing on-premises applications to Azure with minimal or no code changes.</span></span> <span data-ttu-id="c0fda-164">Los administradores y los desarrolladores pueden seguir usando las mismas herramientas de desarrollo y administración que tienen disponibles de forma local.</span><span class="sxs-lookup"><span data-stu-id="c0fda-164">Administrators and developers can still use the same development and administration tools that are available on-premises.</span></span> 
 
 <span data-ttu-id="c0fda-165">Mover una base de datos de SQL Server local a SQL Server que se ejecuta en una máquina virtual de Azure suele tomar una de estas rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="c0fda-165">Moving a database from on-premises SQL Server to SQL Server running in an Azure Virtual Machine typically takes one of these paths:</span></span> 
 
-  <span data-ttu-id="c0fda-166">**Mover solo la base de datos:** Hay varias herramientas y técnicas disponibles para migrar bases de datos locales existentes a SQL Server en Azure Virtual Machines.</span><span class="sxs-lookup"><span data-stu-id="c0fda-166">**Moving just the database:** There are several tools and techniques available to move existing on-premises databases to SQL Server in Azure Virtual Machines.</span></span> <span data-ttu-id="c0fda-167">Para obtener instrucciones y recomendaciones sobre la migración a SQL Server en Azure Virtual Machines, consulte [preparación para migrar a SQL Server en azure virtual machines](https://msdn.microsoft.com/library/dn133142.aspx) y [migración a SQL Server en una máquina virtual de Azure](https://msdn.microsoft.com/library/jj156165.aspx).</span><span class="sxs-lookup"><span data-stu-id="c0fda-167">For guidelines and recommendations on migration to SQL Server in Azure Virtual Machines, see [Getting Ready to Migrate to SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133142.aspx) and also [Migrating to SQL Server in an Azure Virtual Machine](https://msdn.microsoft.com/library/jj156165.aspx).</span></span> 
 
   <span data-ttu-id="c0fda-168">Además, a partir de SQL Server 2014, hay disponible un nuevo Asistente para [implementar una base de datos de SQL Server en una máquina virtual de Microsoft Azure](../relational-databases/databases/deploy-a-sql-server-database-to-a-microsoft-azure-virtual-machine.md) para implementar la base de datos en otra instancia de SQL Server que se ejecute en una máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="c0fda-168">In addition, starting with SQL Server 2014, a new wizard, [Deploy a SQL Server Database to a Microsoft Azure Virtual Machine](../relational-databases/databases/deploy-a-sql-server-database-to-a-microsoft-azure-virtual-machine.md) is available for you to deploy the database to another SQL Server instance running in an Azure Virtual Machine.</span></span> 
 
-  <span data-ttu-id="c0fda-169">**Mover toda la máquina virtual:** Puede traer sus propias SQL Server máquinas virtuales a Azure o crear una con la imagen de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="c0fda-169">**Moving the entire virtual machine:** You can bring your own SQL Server virtual machines to Azure or create one by using the platform image.</span></span> <span data-ttu-id="c0fda-170">Después, puede cargar y conectar a la máquina virtual un disco de datos que ya contenga datos, o conectar un disco vacío a la máquina.</span><span class="sxs-lookup"><span data-stu-id="c0fda-170">Then, you can upload and attach a data disk that already contains data to the virtual machine, or attach an empty disk to the machine.</span></span> <span data-ttu-id="c0fda-171">Tener una instancia de datos de SQL Server en Azure Virtual Machines con discos de datos conectados proporciona otro almacenamiento persistente para los archivos de datos y los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0fda-171">Having a SQL Server data instance on Azure Virtual Machines with attached data disks provides another persistent storage for your data files and application data.</span></span> <span data-ttu-id="c0fda-172">Para obtener información completa y procedimientos, consulte [SQL Server implementación en Azure virtual machines](https://msdn.microsoft.com/library/dn133141.aspx).</span><span class="sxs-lookup"><span data-stu-id="c0fda-172">For comprehensive information and how-tos, see [SQL Server Deployment in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133141.aspx).</span></span> 
 
 <span data-ttu-id="c0fda-173">Si tiene previsto trasladar las capas de aplicación (como el nivel de presentación, el nivel empresarial y el nivel de base de datos) a Azure Virtual Machines, se recomienda que revise las recomendaciones proporcionadas en el artículo [patrones de aplicaciones y estrategias de desarrollo para SQL Server en azure virtual machines](https://msdn.microsoft.com/library/dn574746.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c0fda-173">If you plan to move the application tiers (such as the presentation tier, the business tier, and the database tier) to Azure Virtual Machines, we recommend that you review the recommendations given in the [Application Patterns and Development Strategies for SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/dn574746.aspx) article.</span></span> <span data-ttu-id="c0fda-174">El objetivo de este artículo es proporcionar a los desarrolladores y arquitectos de soluciones una base para la buena arquitectura y diseño de aplicaciones, que pueden seguir al migrar las aplicaciones existentes a Azure, así como al desarrollar nuevas aplicaciones en Azure.</span><span class="sxs-lookup"><span data-stu-id="c0fda-174">The goal of this article is to provide solution architects and developers a foundation for good application architecture and design, which they can follow when migrating existing applications to Azure as well as developing new applications in Azure.</span></span> <span data-ttu-id="c0fda-175">Para cada patrón de aplicación, el artículo describe un escenario local, su solución habilitada para la nube correspondiente y las recomendaciones técnicas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="c0fda-175">For each application pattern, the article describes an on-premises scenario, its respective cloud-enabled solution, and the related technical recommendations.</span></span> <span data-ttu-id="c0fda-176">Además, el artículo describe estrategias de desarrollo específicas de Azure para que pueda diseñar sus aplicaciones correctamente.</span><span class="sxs-lookup"><span data-stu-id="c0fda-176">In addition, the article discusses Azure specific development strategies so that you can design your applications correctly.</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="c0fda-177">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0fda-177">See also</span></span> 
 [<span data-ttu-id="c0fda-178">Guía del producto SQL Server 2014 CTP2</span><span class="sxs-lookup"><span data-stu-id="c0fda-178">SQL Server 2014 CTP2 Product Guide</span></span>](https://www.microsoft.com/download/details.aspx?id=39269)  
 [<span data-ttu-id="c0fda-179">SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c0fda-179">SQL Server 2014</span></span>](https://www.microsoft.com/sqlserver/sql-server-2014.aspx)  
 [<span data-ttu-id="c0fda-180">Series de blogs de nube híbrida de Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="c0fda-180">Microsoft SQL Server Hybrid Cloud Blog Series</span></span>](https://azure.microsoft.com/blog/microsoft-sql-server-hybrid-cloud-blog-series/)  
 [<span data-ttu-id="c0fda-181">Migración de aplicaciones centradas en datos a Azure</span><span class="sxs-lookup"><span data-stu-id="c0fda-181">Migrating Data-Centric Applications to Azure</span></span>](https://azure.microsoft.com/blog/cloud-services-series-migrating-data-centric-applications-to-windows-azure/) 
 