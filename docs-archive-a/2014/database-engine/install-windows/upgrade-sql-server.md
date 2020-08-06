---
title: Actualizar a SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
ms.assetid: 5064e35b-b70d-4a0b-a9e9-fff04162f9d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 857bbd6d7269b7675653b11a9d7c0acd07927f62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745401"
---
# <a name="upgrade-to-sql-server-2014"></a><span data-ttu-id="90a74-102">Actualizar a SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="90a74-102">Upgrade to SQL Server 2014</span></span>
  <span data-ttu-id="90a74-103">Puede actualizar instancias de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a74-103">You can upgrade instances of, [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="90a74-104">Antes de ejecutar la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para actualizar a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], consulte la [Guía técnica de actualización de SQL Server 2014](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf) (descarga en PDF), revise los temas sobre el proceso de actualización incluidos en esta sección y lea las [notas de la versión SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="90a74-104">Before running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], check out the [SQL Server 2014 Upgrade Technical Guide](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf) (PDF download), review the topics about the upgrade process in this section, and read the [SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90a74-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="90a74-105">In This Section</span></span>  
 <span data-ttu-id="90a74-106">Esta sección contiene los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="90a74-106">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="90a74-107">Actualizaciones de ediciones y versiones admitidas</span><span class="sxs-lookup"><span data-stu-id="90a74-107">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="90a74-108">Usar el Asesor de actualizaciones para preparar las actualizaciones</span><span class="sxs-lookup"><span data-stu-id="90a74-108">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
-   [<span data-ttu-id="90a74-109">Emplear Distributed Replay Utility para preparar las actualizaciones</span><span class="sxs-lookup"><span data-stu-id="90a74-109">Use the Distributed Replay Utility to Prepare for Upgrades</span></span>](../../sql-server/install/use-the-distributed-replay-utility-to-prepare-for-upgrades.md)  
  
-   [<span data-ttu-id="90a74-110">Actualizar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="90a74-110">Upgrade Analysis Services</span></span>](upgrade-analysis-services.md)  
  
-   [<span data-ttu-id="90a74-111">Actualizar el motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="90a74-111">Upgrade Database Engine</span></span>](upgrade-database-engine.md)  
  
-   [<span data-ttu-id="90a74-112">Actualizar Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="90a74-112">Upgrade Data Quality Services</span></span>](upgrade-data-quality-services.md)  
  
-   [<span data-ttu-id="90a74-113">Actualizar Integration Services</span><span class="sxs-lookup"><span data-stu-id="90a74-113">Upgrade Integration Services</span></span>](../../integration-services/install-windows/upgrade-integration-services.md)  
  
-   [<span data-ttu-id="90a74-114">Actualizar Master Data Services</span><span class="sxs-lookup"><span data-stu-id="90a74-114">Upgrade Master Data Services</span></span>](upgrade-master-data-services.md)  
  
-   [<span data-ttu-id="90a74-115">Actualizar PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="90a74-115">Upgrade PowerPivot for SharePoint</span></span>](upgrade-power-pivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="90a74-116">Actualizar bases de datos replicadas</span><span class="sxs-lookup"><span data-stu-id="90a74-116">Upgrade Replicated Databases</span></span>](../../database-engine/install-windows/upgrade-replicated-databases.md)  
  
-   [<span data-ttu-id="90a74-117">Actualizar y migrar Reporting Services</span><span class="sxs-lookup"><span data-stu-id="90a74-117">Upgrade and Migrate Reporting Services</span></span>](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md)  
  
-   [<span data-ttu-id="90a74-118">Actualizar las herramientas de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="90a74-118">Upgrade SQL Server Management Tools</span></span>](upgrade-sql-server-management-tools.md)  
  
-   [<span data-ttu-id="90a74-119">Temas de procedimientos de actualización</span><span class="sxs-lookup"><span data-stu-id="90a74-119">Upgrade How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="90a74-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90a74-120">See Also</span></span>  
 <span data-ttu-id="90a74-121">[Actualizar el motor de base de datos](upgrade-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="90a74-121">[Upgrade Database Engine](upgrade-database-engine.md) </span></span>  
 <span data-ttu-id="90a74-122">[Actualizar Analysis Services](upgrade-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="90a74-122">[Upgrade Analysis Services](upgrade-analysis-services.md) </span></span>  
 <span data-ttu-id="90a74-123">[Actualizar y migrar Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="90a74-123">[Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md) </span></span>  
 <span data-ttu-id="90a74-124">[Actualizar Integration Services](../../integration-services/install-windows/upgrade-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="90a74-124">[Upgrade Integration Services](../../integration-services/install-windows/upgrade-integration-services.md) </span></span>  
 <span data-ttu-id="90a74-125">[Actualizar bases de datos replicadas](../../database-engine/install-windows/upgrade-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="90a74-125">[Upgrade Replicated Databases](../../database-engine/install-windows/upgrade-replicated-databases.md) </span></span>  
 <span data-ttu-id="90a74-126">[Actualizar Master Data Services](upgrade-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="90a74-126">[Upgrade Master Data Services](upgrade-master-data-services.md) </span></span>  
 <span data-ttu-id="90a74-127">[SQL Server 2012 Analizador de procedimientos recomendados](https://www.microsoft.com/download/details.aspx?id=29302) </span><span class="sxs-lookup"><span data-stu-id="90a74-127">[SQL Server 2012 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=29302) </span></span>  
 <span data-ttu-id="90a74-128">[Best Practices Analyzer para SQL Server 2008 R2](https://www.microsoft.com/download/details.aspx?id=436) </span><span class="sxs-lookup"><span data-stu-id="90a74-128">[SQL Server 2008 R2 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=436) </span></span>  
 [<span data-ttu-id="90a74-129">Compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="90a74-129">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
