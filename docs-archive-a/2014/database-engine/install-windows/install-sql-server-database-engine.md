---
title: Acerca del Motor de base de datos de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], installing
ms.assetid: d0876e7f-aa52-4dd7-bd5c-029e2ffded5f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 93e3d7a749fe6be47cc84d43509a6f378476b2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746410"
---
# <a name="about-the-sql-server-database-engine"></a><span data-ttu-id="d86d3-102">Acerca del motor de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d86d3-102">About the SQL Server Database Engine</span></span>
  <span data-ttu-id="d86d3-103">El componente [!INCLUDE[ssDE](../../includes/ssde-md.md)] de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es el servicio principal para almacenar, procesar y proteger los datos.</span><span class="sxs-lookup"><span data-stu-id="d86d3-103">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="d86d3-104">El [!INCLUDE[ssDE](../../includes/ssde-md.md)] proporciona un acceso controlado y un procesamiento de transacciones rápido para cumplir los requisitos de las aplicaciones consumidoras de datos más exigentes de su empresa.</span><span class="sxs-lookup"><span data-stu-id="d86d3-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications in your enterprise.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d86d3-105">admite hasta 50 instancias del [!INCLUDE[ssDE](../../includes/ssde-md.md)] en un solo equipo.</span><span class="sxs-lookup"><span data-stu-id="d86d3-105">supports up to 50 instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a single computer.</span></span> <span data-ttu-id="d86d3-106">Para crear una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalación típica, consulte Instalación [de SQL Server 2014 desde el Asistente para la instalación &#40;&#41;de instalación ](install-sql-server-from-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="d86d3-106">To create a typical [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
 <span data-ttu-id="d86d3-107">**Importante** : en las instalaciones locales, debe ejecutar el programa de instalación como administrador.</span><span class="sxs-lookup"><span data-stu-id="d86d3-107">**Important** For local installations, you must run Setup as an administrator.</span></span> <span data-ttu-id="d86d3-108">Si instala [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde un recurso compartido remoto, deberá usar una cuenta de dominio que tenga permisos de lectura y ejecución para dicho recurso.</span><span class="sxs-lookup"><span data-stu-id="d86d3-108">If you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a remote share, you must use a domain account that has read and execute permissions on the remote share.</span></span>  
  
 <span data-ttu-id="d86d3-109">Las siguientes características se instalan al seleccionar **Motor de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** en la página Componentes para instalar del Asistente para la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d86d3-109">The following features are installed when you select **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine** on the Components to Install page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   <span data-ttu-id="d86d3-110">Replicación: es un componente opcional</span><span class="sxs-lookup"><span data-stu-id="d86d3-110">Replication - is an optional component</span></span>  
  
-   <span data-ttu-id="d86d3-111">Búsqueda de texto completo: es un componente opcional</span><span class="sxs-lookup"><span data-stu-id="d86d3-111">Full-Text Search - is an optional component</span></span>  
  
-   <span data-ttu-id="d86d3-112">Data Quality Services: es un componente opcional</span><span class="sxs-lookup"><span data-stu-id="d86d3-112">Data Quality Services - is an optional component</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d86d3-113">En esta versión, al activar la casilla **Data Quality Services** en el programa de instalación, no se instala el servidor de Quality Data Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="d86d3-113">In this release, selecting the **Data Quality Services** check box in setup does not install the Data Quality Services (DQS) server.</span></span> <span data-ttu-id="d86d3-114">Tendrá que realizar pasos adicionales después de la instalación para instalar el servidor DQS.</span><span class="sxs-lookup"><span data-stu-id="d86d3-114">You will have to perform additional steps post installation to install DQS server.</span></span> <span data-ttu-id="d86d3-115">Para más información, consulte [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="d86d3-115">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
 <span data-ttu-id="d86d3-116">Las siguientes características adicionales son opciones para muchos escenarios de usuario habituales:</span><span class="sxs-lookup"><span data-stu-id="d86d3-116">The following additional features are options for many typical user scenarios:</span></span>  
  
-   <span data-ttu-id="d86d3-117">Cliente de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="d86d3-117">Data Quality Client</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   <span data-ttu-id="d86d3-118">Componentes de conectividad</span><span class="sxs-lookup"><span data-stu-id="d86d3-118">Connectivity components</span></span>  
  
-   <span data-ttu-id="d86d3-119">Modelos de programación</span><span class="sxs-lookup"><span data-stu-id="d86d3-119">Programming models</span></span>  
  
-   <span data-ttu-id="d86d3-120">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="d86d3-120">Management tools</span></span>  
  
-   [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]  
  
-   <span data-ttu-id="d86d3-121">Componentes de documentación</span><span class="sxs-lookup"><span data-stu-id="d86d3-121">Documentation components</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d86d3-122">De forma predeterminada, las bases de datos y el código de ejemplo no se instalan como parte del programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d86d3-122">By default, sample databases and sample code are not installed as part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="d86d3-123">Para instalar las bases de datos y el código de ejemplo, vea el [sitio web de CodePlex](https://go.microsoft.com/fwlink/?LinkId=87843).</span><span class="sxs-lookup"><span data-stu-id="d86d3-123">To install sample databases and sample code, see the [CodePlex Web site](https://go.microsoft.com/fwlink/?LinkId=87843).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d86d3-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d86d3-124">See Also</span></span>  
 <span data-ttu-id="d86d3-125">[Características admitidas por las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="d86d3-125">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="d86d3-126">[Ediciones y componentes de SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="d86d3-126">[Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span></span>  
 <span data-ttu-id="d86d3-127">[Planear una instalación de SQL Server](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="d86d3-127">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="d86d3-128">[Soluciones de alta disponibilidad &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d86d3-128">[High Availability Solutions &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span></span>  
 [<span data-ttu-id="d86d3-129">Actualice a SQL Server 2014 mediante el Asistente para la instalación &#40;la instalación&#41;</span><span class="sxs-lookup"><span data-stu-id="d86d3-129">Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;</span></span>](upgrade-sql-server-using-the-installation-wizard-setup.md)  
  
  
