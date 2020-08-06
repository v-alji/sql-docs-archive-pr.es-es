---
title: FILESTREAM y FileTable con Grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], Availability Groups
- FILESTREAM [SQL Server], Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: fdceda9a-a9db-4d1d-8745-345992164a98
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7de7b4d66890bb5f1fe49799844f666de81f4db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672271"
---
# <a name="filestream-and-filetable-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="28de6-102">FILESTREAM y FileTable con grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="28de6-102">FILESTREAM and FileTable with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="28de6-103">Este tema contiene información sobre cómo usar las características FILESTREAM y FileTable con [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28de6-103">This topic contains information about the using the FILESTREAM and FileTable features with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="28de6-104">Se admite toda la funcionalidad de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="28de6-104">All FILESTREAM functionality is supported.</span></span> <span data-ttu-id="28de6-105">Después de una conmutación por error, los datos de FILESTREAM son accesibles tanto en las réplicas secundarias legibles como en la nueva réplica principal.</span><span class="sxs-lookup"><span data-stu-id="28de6-105">After a failover, FILESTREAM data is accessible on both readable secondary replicas and on the new primary.</span></span>  
  
 <span data-ttu-id="28de6-106">Se admite parcialmente la funcionalidad de FileTable.</span><span class="sxs-lookup"><span data-stu-id="28de6-106">FileTable functionality is partially supported.</span></span> <span data-ttu-id="28de6-107">Después de una conmutación por error, es posible tener acceso a los datos de FileTable en la réplica principal, pero no en las réplicas secundarias legibles.</span><span class="sxs-lookup"><span data-stu-id="28de6-107">After a failover, FileTable data is accessible on the primary replica, but FileTable data is not accessible on readable secondary replicas.</span></span>  
  
 <span data-ttu-id="28de6-108">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="28de6-108">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="28de6-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="28de6-109">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="28de6-110">Usar nombres de red virtual (VNN) para el acceso de FILESTREAM y FileTable</span><span class="sxs-lookup"><span data-stu-id="28de6-110">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>](#vnn)  
  
-   [<span data-ttu-id="28de6-111">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="28de6-111">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="28de6-112">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="28de6-112">Related Content</span></span>](#RelatedContent)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="28de6-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="28de6-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="28de6-114">Para poder agregar una base de datos que utiliza FILESTREAM, con o sin FileTable, a un grupo de disponibilidad, asegúrese de que FILESTREAM está habilitada en cada instancia de servidor que hospeda una replicación de disponibilidad para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="28de6-114">Before adding a database that uses FILESTREAM, with or without FileTable, to an availability group, ensure that FILESTREAM is enabled on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="28de6-115">Para obtener más información, consulte [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="28de6-115">For more information, see [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span></span>  
  
##  <a name="using-virtual-network-names-vnns-for-filestream-and-filetable-access"></a><a name="vnn"></a><span data-ttu-id="28de6-116">Usar nombres de Virtual Network (VNN) para el acceso de FILESTREAM y FileTable</span><span class="sxs-lookup"><span data-stu-id="28de6-116">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>  
 <span data-ttu-id="28de6-117">Al habilitar FILESTREAM en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], se crea un recurso compartido de nivel de instancia para proporcionar acceso a los datos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="28de6-117">When you enable FILESTREAM on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], an instance-level share is created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="28de6-118">Puede obtener acceso a este recurso compartido mediante el nombre de equipo en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="28de6-118">You access this share by using the computer name in the following format:</span></span>  
  
 `\\<computer_name>\<filestream_share_name>`  
  
 <span data-ttu-id="28de6-119">Sin embargo, en un grupo de disponibilidad AlwaysOn, el nombre del equipo está virtualizado con un nombre de red virtual, o VNN.</span><span class="sxs-lookup"><span data-stu-id="28de6-119">In an AlwaysOn availability group, however, the name of the computer is virtualized by using a Virtual Network Name, or VNN.</span></span> <span data-ttu-id="28de6-120">Si el equipo es la replicación primaria de un grupo de disponibilidad y las bases de datos del grupo de disponibilidad contienen datos de FILESTREAM, también se crea un recurso compartido de ámbito de VNN para proporcionar acceso a los datos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="28de6-120">When the computer is the primary replica in an availability group, and databases in the availability group contain FILESTREAM data, then a VNN-scoped share is also created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="28de6-121">Esto no afecta al acceso de Transact-SQL a los datos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="28de6-121">This does not affect Transact-SQL access to FILESTREAM data.</span></span> <span data-ttu-id="28de6-122">Sin embargo, las aplicaciones que usan las API del sistema de archivos tienen que utilizar el recurso compartido de ámbito de VNN, que tiene una ruta de acceso con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="28de6-122">However applications that use file system APIs have to use the VNN-scoped share, which has a path in the following format:</span></span>  
  
 `\\<VNN>\<filestream_share_name>`  
  
 <span data-ttu-id="28de6-123">Se crea este recurso compartido de ámbito de VNN cuando tiene lugar uno de los siguientes eventos.</span><span class="sxs-lookup"><span data-stu-id="28de6-123">This VNN-scoped share is created when one of the following events occurs.</span></span>  
  
-   <span data-ttu-id="28de6-124">Agrega una base de datos que contiene datos de FILESTREAM a un grupo de disponibilidad AlwaysOn de la replicación primaria.</span><span class="sxs-lookup"><span data-stu-id="28de6-124">You add a database that contains FILESTREAM data to an AlwaysOn availability group on the primary replica.</span></span> <span data-ttu-id="28de6-125">En este caso, el recurso compartido `\\<computer_name>\<filestream_share_name>` ya existe.</span><span class="sxs-lookup"><span data-stu-id="28de6-125">In this case, the share `\\<computer_name>\<filestream_share_name>` already exists.</span></span> <span data-ttu-id="28de6-126">Se crea el recurso compartido `\\<VNN>\<filestream_share_name>` .</span><span class="sxs-lookup"><span data-stu-id="28de6-126">The share `\\<VNN>\<filestream_share_name>` is created.</span></span>  
  
-   <span data-ttu-id="28de6-127">Habilita FILESTREAM para el acceso de transmisión por secuencias de E/S de archivo en una replicación primaria que incluye grupos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="28de6-127">You enable FILESTREAM for file i/o streaming access on a primary replica that has availability groups.</span></span> <span data-ttu-id="28de6-128">Se crean los siguientes recursos compartidos:</span><span class="sxs-lookup"><span data-stu-id="28de6-128">The following shares are created:</span></span>  
  
    1.  `\\<computer_name>\<filestream_share_name>`  
  
    2.  <span data-ttu-id="28de6-129">`\\<VNN1>\<filestream_share_name>` para el grupo de disponibilidad 1.</span><span class="sxs-lookup"><span data-stu-id="28de6-129">`\\<VNN1>\<filestream_share_name>` for availability group 1.</span></span>  
  
    3.  <span data-ttu-id="28de6-130">`\\<VNN2>\<filestream_share_name>` para el grupo de disponibilidad 2.</span><span class="sxs-lookup"><span data-stu-id="28de6-130">`\\<VNN2>\<filestream_share_name>` for availability group 2.</span></span>  
  
 <span data-ttu-id="28de6-131">Estos recursos compartidos de ámbito de VNN también se propagan a todas las réplicas secundarias.</span><span class="sxs-lookup"><span data-stu-id="28de6-131">These VNN-scoped shares are also propagated to all secondary replicas.</span></span>  
  
 <span data-ttu-id="28de6-132">Cuando la base de datos que contiene datos de FILESTREAM o FileTable pertenece a un grupo de disponibilidad AlwaysOn:</span><span class="sxs-lookup"><span data-stu-id="28de6-132">When the database that contains FILESTREAM or FileTable data belongs to an AlwaysOn availability group:</span></span>  
  
-   <span data-ttu-id="28de6-133">Las funciones FILESTREAM y FileTable aceptan o devuelven nombres de red virtual (VNN) en lugar de nombres de equipo.</span><span class="sxs-lookup"><span data-stu-id="28de6-133">The FILESTREAM and FileTable functions accept or return virtual network names (VNNs) instead of computer names.</span></span> <span data-ttu-id="28de6-134">Para obtener más información sobre estas funciones, vea [Funciones FILESTREAM y FileTable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="28de6-134">For more information about these functions, see [Filestream and FileTable Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span></span>  
  
-   <span data-ttu-id="28de6-135">Todo acceso a los datos de FILESTREAM o FileTable a través de las API del sistema de archivos debe utilizar VNN en lugar de nombres de equipo.</span><span class="sxs-lookup"><span data-stu-id="28de6-135">All access to FILESTREAM or FileTable data through the file system APIs should use VNNs instead of computer names.</span></span>  
  
 <span data-ttu-id="28de6-136">Si la aplicación intenta tener acceso al recurso compartido mediante el nombre del equipo en formato `\\<computer_name>\<filestream_share_name>` cuando la base de datos forma parte de un grupo de disponibilidad, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="28de6-136">If your application tries to access the share by using the computer name in the format `\\<computer_name>\<filestream_share_name>` when the database is part of an availability group, then an error is raised.</span></span>  
  
 <span data-ttu-id="28de6-137">Si la aplicación intenta tener acceso al recurso compartido con una ruta de acceso de ámbito de VNN cuando la base de datos no forma parte de un grupo de disponibilidad, la solicitud puede realizarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="28de6-137">If your application tries to access the share by using a VNN-scoped path when the database is not part of an availability group, then the request may succeed.</span></span> <span data-ttu-id="28de6-138">En este caso, el nombre de red virtual se resuelve en el nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="28de6-138">In this case, the virtual network name is resolved to the computer name.</span></span> <span data-ttu-id="28de6-139">Sin embargo, este uso no se recomienda en absoluto, ya que la ruta de acceso de ámbito de VNN dejará de funcionar si se quita el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="28de6-139">However this usage is strongly discouraged, since the VNN-scoped path will stop working if the availability group is dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="28de6-140">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="28de6-140">Related Tasks</span></span>  
  
-   [<span data-ttu-id="28de6-141">Enable and Configure FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="28de6-141">Enable and Configure FILESTREAM</span></span>](../../../relational-databases/blob/enable-and-configure-filestream.md)  
  
-   [<span data-ttu-id="28de6-142">Habilitar los requisitos previos de FileTables</span><span class="sxs-lookup"><span data-stu-id="28de6-142">Enable the Prerequisites for FileTable</span></span>](../../../relational-databases/blob/enable-the-prerequisites-for-filetable.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="28de6-143">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="28de6-143">Related Content</span></span>  
 <span data-ttu-id="28de6-144">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="28de6-144">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28de6-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28de6-145">See Also</span></span>  
 [<span data-ttu-id="28de6-146">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28de6-146">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
