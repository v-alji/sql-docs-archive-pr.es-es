---
title: Servicio Integration Services (servicio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, about Integration Services service
- SQL Server Integration Services service
- service [Integration Services],about Integration Services service
- service [Integration Services]
- SQL Server Integration Services, service
ms.assetid: 2c785b3b-4a0c-4df7-b5cd-23756dc87842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 04b24f0f0d54009c50654904d606a208504f229c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751289"
---
# <a name="integration-services-service-ssis-service"></a><span data-ttu-id="a1779-102">Servicio Integration Services (servicio SSIS)</span><span class="sxs-lookup"><span data-stu-id="a1779-102">Integration Services Service (SSIS Service)</span></span>
  <span data-ttu-id="a1779-103">Los temas de esta sección describen el servicio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , un servicio de Windows para administrar paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1779-103">The topics in this section discuss the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="a1779-104">No se requiere este servicio para crear, guardar y ejecutar los paquetes de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="a1779-104">This service is not required to create, save, and run Integration Services packages.</span></span> [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] <span data-ttu-id="a1779-105">admite el servicio de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para mantener la compatibilidad con versiones anteriores de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1779-105">supports the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a1779-106">A partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] almacena objetos, valores y datos operativos en la `SSISDB` base de datos para los proyectos que se han implementado en el [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] servidor mediante el modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="a1779-106">Starting in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] stores objects, settings, and operational data in the `SSISDB` database for projects that you've deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server using the project deployment model.</span></span> <span data-ttu-id="a1779-107">El servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , que es una instancia del motor de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , hospeda la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a1779-107">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, which is an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine, hosts the database.</span></span> <span data-ttu-id="a1779-108">Para obtener más información sobre la base de datos, vea [Catálogo de SSIS](../catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="a1779-108">For more information about the database, see [SSIS Catalog](../catalog/ssis-catalog.md).</span></span> <span data-ttu-id="a1779-109">Para más información sobre la implementación de proyectos en el servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , vea [Implementación de paquetes en el servidor de Integration Services](../deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="a1779-109">For more information about deploying projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, see [Deploy Projects to Integration Services Server](../deploy-projects-to-integration-services-server.md).</span></span>  
  
## <a name="management-capabilities"></a><span data-ttu-id="a1779-110">Capacidades de administración</span><span class="sxs-lookup"><span data-stu-id="a1779-110">Management Capabilities</span></span>  
 <span data-ttu-id="a1779-111">El servicio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] es un servicio de Windows para administrar paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1779-111">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="a1779-112">El servicio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solo está disponible en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1779-112">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is available only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a1779-113">Ejecutar el servicio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] proporciona las siguientes capacidades de administración:</span><span class="sxs-lookup"><span data-stu-id="a1779-113">Running the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service provides the following management capabilities:</span></span>  
  
-   <span data-ttu-id="a1779-114">Iniciar paquetes almacenados en ubicaciones locales y remotas</span><span class="sxs-lookup"><span data-stu-id="a1779-114">Starting remote and locally stored packages</span></span>  
  
-   <span data-ttu-id="a1779-115">Detener paquetes que se ejecutan en ubicaciones locales y remotas</span><span class="sxs-lookup"><span data-stu-id="a1779-115">Stopping remote and locally running packages</span></span>  
  
-   <span data-ttu-id="a1779-116">Supervisar paquetes que se ejecutan en ubicaciones locales y remotas</span><span class="sxs-lookup"><span data-stu-id="a1779-116">Monitoring remote and locally running packages</span></span>  
  
-   <span data-ttu-id="a1779-117">Importar y exportar paquetes</span><span class="sxs-lookup"><span data-stu-id="a1779-117">Importing and exporting packages</span></span>  
  
-   <span data-ttu-id="a1779-118">Administrar el almacenamiento de paquetes</span><span class="sxs-lookup"><span data-stu-id="a1779-118">Managing package storage</span></span>  
  
-   <span data-ttu-id="a1779-119">Personalizar carpetas de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="a1779-119">Customizing storage folders</span></span>  
  
-   <span data-ttu-id="a1779-120">Detener paquetes que se están ejecutando cuando se detiene el servicio</span><span class="sxs-lookup"><span data-stu-id="a1779-120">Stopping running packages when the service is stopped</span></span>  
  
-   <span data-ttu-id="a1779-121">Ver el registro de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="a1779-121">Viewing the Windows Event log</span></span>  
  
-   <span data-ttu-id="a1779-122">Conectar con varios servidores de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1779-122">Connecting to multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] servers</span></span>  
  
## <a name="startup-type-for-integration-services-service"></a><span data-ttu-id="a1779-123">Tipo de inicio para el servicio Integration Services</span><span class="sxs-lookup"><span data-stu-id="a1779-123">Startup Type for Integration Services Service</span></span>  
 <span data-ttu-id="a1779-124">El servicio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] se instala al instalar el componente [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1779-124">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is installed when you install the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a1779-125">De forma predeterminada, el servicio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] se inicia y el tipo de inicio del servicio se establece en automático.</span><span class="sxs-lookup"><span data-stu-id="a1779-125">By default, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span> <span data-ttu-id="a1779-126">El servicio se debe ejecutar para poder supervisar los paquetes almacenados en el Almacén de paquetes [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1779-126">The service must be running to monitor the packages that are stored in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span> <span data-ttu-id="a1779-127">El Almacén de paquetes [!INCLUDE[ssIS](../../includes/ssis-md.md)] puede ser la base de datos msdb en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o las carpetas designadas en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="a1779-127">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store can be either the msdb database in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the designated folders in the file system.</span></span>  
  
 <span data-ttu-id="a1779-128">El servicio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no es necesario si únicamente desea diseñar y ejecutar paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1779-128">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is not required if you only want to design and execute [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="a1779-129">Sin embargo, sí se necesita para ver la lista de paquetes y supervisarlos con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1779-129">However, the service is required to list and monitor packages using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a1779-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a1779-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a1779-131">Establecer las propiedades del servicio Integration Services</span><span class="sxs-lookup"><span data-stu-id="a1779-131">Set the Properties of the Integration Services Service</span></span>](../set-the-properties-of-the-integration-services-service.md)  
  
-   [<span data-ttu-id="a1779-132">Ver los eventos para el servicio Integration Services</span><span class="sxs-lookup"><span data-stu-id="a1779-132">View Events for the Integration Services Service</span></span>](../view-events-for-the-integration-services-service.md)  
  
  
