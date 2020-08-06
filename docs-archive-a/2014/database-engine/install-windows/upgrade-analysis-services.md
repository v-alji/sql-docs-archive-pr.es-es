---
title: Actualizar Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- upgrading databases
- databases [Analysis Services], upgrading
- installing Analysis Services, side-by-side installations
- Analysis Services upgrades
- Analysis Services upgrades, about upgrading Analysis Services
- SSAS, database migration
- upgrading Analysis Services
- installing Analysis Services, upgrading
- SSAS, upgrading
ms.assetid: a131d329-386e-4470-aaa9-ffcde4e5ec0c
author: Minewiskan
ms.author: owend
ms.openlocfilehash: 78bf7f27233bcfd46bc1f189324eddc72adcc961
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671159"
---
# <a name="upgrade-analysis-services"></a><span data-ttu-id="0c819-102">Actualizar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0c819-102">Upgrade Analysis Services</span></span>
  <span data-ttu-id="0c819-103">Use el programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para actualizar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c819-103">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0c819-104">Para obtener información detallada sobre cómo actualizar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en modo de SharePoint, vea [Actualizar PowerPivot para SharePoint](upgrade-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="0c819-104">For detailed information on upgrading [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in SharePoint mode, see [Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md).</span></span> <span data-ttu-id="0c819-105">Para obtener más información acerca de la actualización de una instancia de SQL Server existente, consulte [actualización a SQL Server 2014 mediante el Asistente para la instalación &#40;&#41;de instalación ](upgrade-sql-server-using-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="0c819-105">For more information about upgrading an existing SQL Server instance, see [Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;](upgrade-sql-server-using-the-installation-wizard-setup.md).</span></span>  
  
## <a name="known-upgrade-issues"></a><span data-ttu-id="0c819-106">Problemas de actualización conocidos</span><span class="sxs-lookup"><span data-stu-id="0c819-106">Known Upgrade Issues</span></span>  
 <span data-ttu-id="0c819-107">Antes de actualizarse a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], revise lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c819-107">Before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], review the following:</span></span>  
  
-   <span data-ttu-id="0c819-108">[SQL Server notas](https://go.microsoft.com/fwlink/?LinkID=296445)de la versión de 2014.</span><span class="sxs-lookup"><span data-stu-id="0c819-108">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
-   <span data-ttu-id="0c819-109">Para saber qué [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] características y funcionalidades se han dejado de usar, están en desuso o han cambiado, consulte [Analysis Services compatibilidad con versiones anteriores](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span><span class="sxs-lookup"><span data-stu-id="0c819-109">To learn which [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] features and functionality have been discontinued, deprecated, or changed see [Analysis Services Backward Compatibility](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span></span>  
  
## <a name="pre-upgrade-checklist"></a><span data-ttu-id="0c819-110">Lista de comprobación previa a la actualización</span><span class="sxs-lookup"><span data-stu-id="0c819-110">Pre-Upgrade Checklist</span></span>  
 <span data-ttu-id="0c819-111">Antes de actualizar, revise la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c819-111">Before upgrading, review the following information:</span></span>  
  
-   [<span data-ttu-id="0c819-112">Actualizaciones de ediciones y versiones admitidas</span><span class="sxs-lookup"><span data-stu-id="0c819-112">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="0c819-113">Requisitos de hardware y software para instalar SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0c819-113">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
-   [<span data-ttu-id="0c819-114">Comprobar los parámetros del Comprobador de configuración del sistema</span><span class="sxs-lookup"><span data-stu-id="0c819-114">Check Parameters for the System Configuration Checker</span></span>](check-parameters-for-the-system-configuration-checker.md)  
  
-   [<span data-ttu-id="0c819-115">Consideraciones de seguridad para una instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0c819-115">Security Considerations for a SQL Server Installation</span></span>](../../sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
-   [<span data-ttu-id="0c819-116">Realizar una copia de seguridad y restaurar las bases de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0c819-116">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
-   [<span data-ttu-id="0c819-117">Usar el Asesor de actualizaciones para preparar las actualizaciones</span><span class="sxs-lookup"><span data-stu-id="0c819-117">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
## <a name="upgrading-analysis-services"></a><span data-ttu-id="0c819-118">Actualizar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0c819-118">Upgrading Analysis Services</span></span>  
 <span data-ttu-id="0c819-119">Puede elegir entre varios enfoques para actualizar el servidor y los datos:</span><span class="sxs-lookup"><span data-stu-id="0c819-119">You can choose from several approaches to upgrade server and data:</span></span>  
  
-   <span data-ttu-id="0c819-120">Una **actualización en contexto** reemplaza los archivos de programa existentes por [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] los archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="0c819-120">An **in-place upgrade** replaces the existing program files with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] program files.</span></span> <span data-ttu-id="0c819-121">Las bases de datos permanecen en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="0c819-121">Databases remain in the same location.</span></span> <span data-ttu-id="0c819-122">Las carpetas de programas se actualizan para reflejar el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="0c819-122">Program folders are updated to reflect the new name.</span></span>  
  
-   <span data-ttu-id="0c819-123">Una **actualización en paralelo** es una nueva instalación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en el mismo equipo que tiene una instancia de Analysis Services existente.</span><span class="sxs-lookup"><span data-stu-id="0c819-123">A **side-by-side upgrade** is a new installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on the same computer that has an existing Analysis Services instance.</span></span> <span data-ttu-id="0c819-124">Puede mover bases de datos a la nueva instancia en el mismo equipo y desinstalar después la versión anterior si ya no la utiliza.</span><span class="sxs-lookup"><span data-stu-id="0c819-124">You can move databases over to the new instance on the same computer, and then uninstall the old version if you no longer use it.</span></span>  
  
-   <span data-ttu-id="0c819-125">También puede instalar Analysis Services en el nuevo hardware y migrar después las bases de datos existentes a ese servidor.</span><span class="sxs-lookup"><span data-stu-id="0c819-125">You can also install Analysis Services on new hardware and then migrate existing databases to that server.</span></span>  
  
## <a name="in-place-upgrade"></a><span data-ttu-id="0c819-126">Actualización en contexto</span><span class="sxs-lookup"><span data-stu-id="0c819-126">In-place Upgrade</span></span>  
 <span data-ttu-id="0c819-127">Puede actualizar una instancia existente de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y, como parte del proceso de actualización, migrar automáticamente las bases de datos existentes de la antigua instancia a la nueva instancia de.</span><span class="sxs-lookup"><span data-stu-id="0c819-127">You can upgrade an existing instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and, as part of the upgrade process, automatically migrate existing databases from the old instance to the new instance.</span></span> <span data-ttu-id="0c819-128">Dado que los metadatos y los datos binarios son compatibles entre las dos versiones, después de actualizar se conservarán los datos y no es necesario migrarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="0c819-128">Because the metadata and binary data is compatible between the two versions, you will retain the data after you upgrade and you do not have to manually migrate the data.</span></span>  
  
 <span data-ttu-id="0c819-129">Para actualizar una instancia existente, ejecute el programa de instalación y especifique el nombre de la instancia existente como nombre de la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="0c819-129">To upgrade an existing instance, run Setup and specify the name of the existing instance as the name of the new instance.</span></span>  
  
## <a name="upgrading-databases"></a><span data-ttu-id="0c819-130">Actualizar bases de datos</span><span class="sxs-lookup"><span data-stu-id="0c819-130">Upgrading Databases</span></span>  
 <span data-ttu-id="0c819-131">Las bases de datos creadas en versiones anteriores de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se ejecutan en el servidor actualizado con la configuración de nivel de compatibilidad de base de datos más antigua.</span><span class="sxs-lookup"><span data-stu-id="0c819-131">Databases that were created in previous versions of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] run on the upgraded server under an older database compatibility level setting.</span></span> <span data-ttu-id="0c819-132">Las bases de datos creadas en las siguientes versiones tienen un nivel de compatibilidad de base de datos de 105.</span><span class="sxs-lookup"><span data-stu-id="0c819-132">Databases created in the following versions, have a database compatibility level of 105.</span></span> <span data-ttu-id="0c819-133">Puede cambiar el nivel de compatibilidad si desea utilizar las características que requieren un nivel de compatibilidad de base de datos más reciente.</span><span class="sxs-lookup"><span data-stu-id="0c819-133">You can change the compatibility level if you want to use features that require a newer database compatibility level.</span></span> <span data-ttu-id="0c819-134">De lo contrario, puede ejecutar las bases de datos del servidor actualizado utilizando la configuración original.</span><span class="sxs-lookup"><span data-stu-id="0c819-134">Otherwise, you can run the databases on the upgraded server using the original settings.</span></span> <span data-ttu-id="0c819-135">Para obtener más información, vea [establecer el nivel de compatibilidad de una base de datos multidimensional &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="0c819-135">For more information, see [Set the Compatibility Level of a Multidimensional Database &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span></span>  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c819-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c819-136">See Also</span></span>  
 <span data-ttu-id="0c819-137">[Características admitidas por las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="0c819-137">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="0c819-138">[Planear una instalación de SQL Server](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="0c819-138">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="0c819-139">[Descripción de la arquitectura OLAP de Microsoft](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span><span class="sxs-lookup"><span data-stu-id="0c819-139">[Understanding Microsoft OLAP Architecture](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span></span>  
 <span data-ttu-id="0c819-140">[PowerPivot para SharePoint de actualización](upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="0c819-140">[Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="0c819-141">[Instalar Analysis Services en modo multidimensional y de minería de datos](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span><span class="sxs-lookup"><span data-stu-id="0c819-141">[Install Analysis Services in Multidimensional and Data Mining Mode](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span></span>  
 [<span data-ttu-id="0c819-142">Instalación de PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="0c819-142">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  