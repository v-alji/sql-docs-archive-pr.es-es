---
title: Almacén remoto de blobs (RBS) y Grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 01a70258-d4fd-40bc-bc44-c490b5d6c420
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12a11162d286731b2b510a9051183e6c3025b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670602"
---
# <a name="remote-blob-store-rbs-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="57759-102">Almacén remoto de blobs (RBS) y grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="57759-102">Remote Blob Store (RBS) and AlwaysOn Availability Groups (SQL Server)</span></span>
  [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]<span data-ttu-id="57759-103">puede proporcionar una solución de alta disponibilidad y recuperación ante desastres para los [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] objetos BLOB (blobs) del [almacén remoto de blobs (RBS](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) ).</span><span class="sxs-lookup"><span data-stu-id="57759-103">can provide a high-availability and disaster recovery solution for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][Remote Blob Store (RBS)](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) BLOB objects (blobs).</span></span> [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] <span data-ttu-id="57759-104">protege los metadatos y esquema de RBS almacenados en una base de datos de disponibilidad replicándolos en las réplicas secundarias.</span><span class="sxs-lookup"><span data-stu-id="57759-104">protects any RBS metadata and schemas stored in an availability database by replicating them to the secondary replicas.</span></span> <span data-ttu-id="57759-105">Se trata de la base de datos de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="57759-105">This is the SharePoint Content Database.</span></span> <span data-ttu-id="57759-106">En general, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] almacena estos metadatos de RBS independientemente del blob.</span><span class="sxs-lookup"><span data-stu-id="57759-106">Generally speaking, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stores this RBS metadata independently from the blob.</span></span>  
  
 <span data-ttu-id="57759-107">La protección de los datos BLOB de RBS depende de la ubicación del almacén de BLOB, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="57759-107">The protection for RBD BLOB data depends on the BLOB Store Location, as follows:</span></span>  
  
|<span data-ttu-id="57759-108">Ubicación del almacén de BLOB</span><span class="sxs-lookup"><span data-stu-id="57759-108">BLOB Store Location</span></span>|<span data-ttu-id="57759-109">¿Pueden los grupos de disponibilidad proteger estos datos BLOB?</span><span class="sxs-lookup"><span data-stu-id="57759-109">Can Availability Groups Protect This BLOB Data?</span></span>|  
|-------------------------|-----------------------------------------------------|  
|<span data-ttu-id="57759-110">La misma base de datos que contiene los metadatos de RBS (almacenada mediante un proveedor remoto FILESTREAM de RBS)</span><span class="sxs-lookup"><span data-stu-id="57759-110">The same database that contains the RBS metadata  (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="57759-111">Sí</span><span class="sxs-lookup"><span data-stu-id="57759-111">Yes</span></span>|  
|<span data-ttu-id="57759-112">Otra base de datos de la misma instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (almacenada mediante un proveedor remoto FILESTREAM de RBS)</span><span class="sxs-lookup"><span data-stu-id="57759-112">Another database in the same instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="57759-113">Sí</span><span class="sxs-lookup"><span data-stu-id="57759-113">Yes</span></span><br /><br /> <span data-ttu-id="57759-114">Se recomienda que esta base de datos esté en el mismo grupo de disponibilidad que la base de datos que contiene los metadatos de RBS.</span><span class="sxs-lookup"><span data-stu-id="57759-114">We recommend that you put this database in the same availability group as the database that contains the RBS metadata.</span></span>|  
|<span data-ttu-id="57759-115">Otra base de datos de otra instancia diferente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (almacenada mediante un proveedor remoto FILESTREAM de RBS)</span><span class="sxs-lookup"><span data-stu-id="57759-115">Another database in a different instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="57759-116">Sí</span><span class="sxs-lookup"><span data-stu-id="57759-116">Yes</span></span><br /><br /> <span data-ttu-id="57759-117">Esta base de datos debe estar en un grupo de disponibilidad diferente.</span><span class="sxs-lookup"><span data-stu-id="57759-117">This database must be in a separate availability group.</span></span>|  
|<span data-ttu-id="57759-118">Un almacén de blobs de terceros</span><span class="sxs-lookup"><span data-stu-id="57759-118">A third-party BLOB store</span></span>|<span data-ttu-id="57759-119">No</span><span class="sxs-lookup"><span data-stu-id="57759-119">No</span></span><br /><br /> <span data-ttu-id="57759-120">Para proteger estos datos BLOB, use los mecanismos de alta disponibilidad del proveedor de almacenes de blobs.</span><span class="sxs-lookup"><span data-stu-id="57759-120">To protect this BLOB data, use the high-availability mechanisms of the BLOB store provider.</span></span>|  
  
##  <a name="limitations"></a><a name="Limitations"></a> <span data-ttu-id="57759-121">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="57759-121">Limitations</span></span>  
  
-   <span data-ttu-id="57759-122">Los mantenedores de RBS deben tener como destino la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="57759-122">RBS maintainers need to be targeted on the primary replica.</span></span>  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="57759-123">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="57759-123">Recommendations</span></span>  
  
-   <span data-ttu-id="57759-124">Use un agente de escucha del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="57759-124">Use an availability group listener.</span></span> <span data-ttu-id="57759-125">Para obtener más información, vea [Agentes de escucha de grupo de disponibilidad, conectividad de cliente y conmutación por error de una aplicación &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="57759-125">For more information, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="57759-126">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="57759-126">Related Content</span></span>  
  
-   <span data-ttu-id="57759-127">[Mantener un almacén remoto de blobs](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (en los Libros en pantalla de [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="57759-127">[Maintaining Remote BLOB Store](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
-   <span data-ttu-id="57759-128">[Ejecutar el Mantenedor de RBS](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (blog)</span><span class="sxs-lookup"><span data-stu-id="57759-128">[Running RBS Maintainer](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (blog)</span></span>  
  
-   <span data-ttu-id="57759-129">[Configurar el almacenamiento remoto de blobs (RBS) con el proveedor FILESTREAM (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (blog)</span><span class="sxs-lookup"><span data-stu-id="57759-129">[Configure Remote BLOB Storage (RBS) with the FILESTREAM provider (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57759-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57759-130">See Also</span></span>  
 <span data-ttu-id="57759-131">[SQL Server de conectividad de cliente de AlwaysOn &#40;&#41;](always-on-client-connectivity-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="57759-131">[AlwaysOn Client Connectivity &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md) </span></span>  
 [<span data-ttu-id="57759-132">Almacén remoto de blobs &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="57759-132">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md)  
  
  
