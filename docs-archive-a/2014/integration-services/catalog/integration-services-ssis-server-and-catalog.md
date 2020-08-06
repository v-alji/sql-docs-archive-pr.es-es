---
title: Servidor Integration Services (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing packages [Integration Services]
ms.assetid: 6d667bba-7c25-492a-8f4d-70ebaca28f40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0da83cdac269499dfbde7a6387a4af4690c83ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674279"
---
# <a name="integration-services-ssis-server"></a><span data-ttu-id="82050-102">Servidor de Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="82050-102">Integration Services (SSIS) Server</span></span>
  <span data-ttu-id="82050-103">Después de diseñar y probar paquetes en [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], puede implementar los proyectos que contienen los paquetes en el servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82050-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="82050-104">El servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] es una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda la base de datos de `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="82050-104">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database.</span></span> <span data-ttu-id="82050-105">La base de datos almacena los objetos siguientes: paquetes, proyectos, parámetros, permisos, propiedades del servidor e historial operativo.</span><span class="sxs-lookup"><span data-stu-id="82050-105">The database stores the following objects: packages, projects, parameters, permissions, server properties, and operational history.</span></span>  
  
 <span data-ttu-id="82050-106">La base de datos de `SSISDB` expone la información de objetos en vistas públicas que puede consultar.</span><span class="sxs-lookup"><span data-stu-id="82050-106">The `SSISDB` database exposes the object information in public views that you can query.</span></span> <span data-ttu-id="82050-107">La base de datos también proporciona procedimientos almacenados a los que puede llamar para administrar los objetos.</span><span class="sxs-lookup"><span data-stu-id="82050-107">The database also provides stored procedures that you can call to manage the objects.</span></span>  
  
 <span data-ttu-id="82050-108">Para poder implementar los proyectos en el servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], debe crear el catálogo de `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="82050-108">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, you need to create the `SSISDB` catalog.</span></span>  
  
 <span data-ttu-id="82050-109">Para obtener información general de la funcionalidad del catálogo de SSISDB, consulte [SSIS Catalog (Catálogo de SSIS)](ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="82050-109">For an overview of the SSISDB catalog functionality, see [SSIS Catalog](ssis-catalog.md).</span></span>  
  
## <a name="high-availability"></a><span data-ttu-id="82050-110">Alta disponibilidad</span><span class="sxs-lookup"><span data-stu-id="82050-110">High Availability</span></span>  
 <span data-ttu-id="82050-111">Como otras bases de datos de usuario, la base de datos de `SSISDB` admite la creación de reflejo de la base de datos y la replicación.</span><span class="sxs-lookup"><span data-stu-id="82050-111">Like other user databases, the `SSISDB` database does support database mirroring and replication.</span></span> <span data-ttu-id="82050-112">Para obtener más información sobre la creación de reflejo y la replicación, consulte [Creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="82050-112">For more information about mirroring and replication, see [Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="82050-113">También puede proporcionar alta disponibilidad de SSISDB y de su contenido mediante SSIS y los grupos de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="82050-113">You can also provide high-availability of SSISDB and its contents by making use of SSIS and AlwaysOn Availability Groups.</span></span> <span data-ttu-id="82050-114">Para obtener más información, vea esta entrada de blog de Matt Masson, [SSIS con AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="82050-114">For more information, see this blog post by Matt Masson, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
##  <a name="integration-services-server-in-sql-server-management-studio"></a><a name="ssms"></a><span data-ttu-id="82050-115">Integration Services Server en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="82050-115">Integration Services Server in SQL Server Management Studio</span></span>  
 <span data-ttu-id="82050-116">Al conectarse a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda la base de datos de `SSISDB`, ve los objetos siguientes en el Explorador de objetos:</span><span class="sxs-lookup"><span data-stu-id="82050-116">When you connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database, you see the following objects in Object Explorer:</span></span>  
  
-   <span data-ttu-id="82050-117">**Base de datos SSISDB**</span><span class="sxs-lookup"><span data-stu-id="82050-117">**SSISDB Database**</span></span>  
  
     <span data-ttu-id="82050-118">La `SSISDB` base de datos aparece bajo el nodo **bases** de datos en el explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="82050-118">The `SSISDB` database appears under the **Databases** node in Object Explore.</span></span> <span data-ttu-id="82050-119">Puede consultar las vistas y llamar a los procedimientos almacenados que administran el servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] y los objetos que están almacenados en el servidor.</span><span class="sxs-lookup"><span data-stu-id="82050-119">You can query the views and call the stored procedures that manage the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server and the objects that are stored on the server.</span></span>  
  
-   <span data-ttu-id="82050-120">**Catálogos de Integration Services**</span><span class="sxs-lookup"><span data-stu-id="82050-120">**Integration Services Catalogs**</span></span>  
  
     <span data-ttu-id="82050-121">En el nodo **Catálogos de Integration Services** hay carpetas para los proyectos y los entornos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82050-121">Under the **Integration Services Catalogs** node there are folders for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] projects and environments.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="82050-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="82050-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="82050-123">Crear el catálogo de SSIS</span><span class="sxs-lookup"><span data-stu-id="82050-123">Create the SSIS Catalog</span></span>](../create-the-ssis-catalog.md)  
  
-   [<span data-ttu-id="82050-124">Ver la lista de paquetes en el servidor de Integration Services</span><span class="sxs-lookup"><span data-stu-id="82050-124">View the List of Packages on the Integration Services Server</span></span>](view-the-list-of-packages-on-the-integration-services-server.md)  
  
-   [<span data-ttu-id="82050-125">Implementación de paquetes en el servidor de Integration Services</span><span class="sxs-lookup"><span data-stu-id="82050-125">Deploy Projects to Integration Services Server</span></span>](../deploy-projects-to-integration-services-server.md)  
  
-   [<span data-ttu-id="82050-126">Ejecutar un paquete en el servidor SSIS con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="82050-126">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](../run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="82050-127">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="82050-127">Related Content</span></span>  
 <span data-ttu-id="82050-128">Entrada de blog, [SSIS con AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="82050-128">Blog entry, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
  
