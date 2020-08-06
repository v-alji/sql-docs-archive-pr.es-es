---
title: Requisitos de hardware y software para Reporting Services en modo de SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ed91877d-4f74-4266-a932-b824b4810c99
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a4fc19b2871d7d5731649c61a8d5231d7e3479dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676845"
---
# <a name="hardware-and-software-requirements-for-reporting-services-in-sharepoint-mode"></a><span data-ttu-id="f9450-102">Requisitos de hardware y software para Reporting Services en modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="f9450-102">Hardware and Software Requirements for Reporting Services in SharePoint Mode</span></span>

  <span data-ttu-id="f9450-103">En este tema se describen los requisitos previos, los requisitos de hardware y las consideraciones de instalación para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ejecutar en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f9450-103">This topic describes prerequisites, hardware requirements, and installation considerations for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] running in SharePoint mode.</span></span> <span data-ttu-id="f9450-104">Puesto que el modo de SharePoint de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] requiere un servidor de SharePoint, la mayoría de los requisitos se basan en el entorno de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f9450-104">Because [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode requires a SharePoint server, most of the requirements are based on the SharePoint environment.</span></span> <span data-ttu-id="f9450-105">Para los servidores de informes en modo nativo, el hardware debe cumplir los requisitos mínimos de hardware y software para ejecutar [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9450-105">For native mode report servers, your hardware should meet minimum hardware and software requirements for running [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="f9450-106">Para obtener más información, vea [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f9450-106">For more information, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="f9450-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f9450-107">Prerequisites</span></span>](#bkmk_prereq)  
  
-   [<span data-ttu-id="f9450-108">Requisitos de base de datos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="f9450-108">Report Server Database Requirements</span></span>](#bkmk_report_server_database)  
  
-   [<span data-ttu-id="f9450-109">Requisitos de Power View</span><span class="sxs-lookup"><span data-stu-id="f9450-109">Power View Requirements</span></span>](#bkmk_powerview)  
  
-   [<span data-ttu-id="f9450-110">Más información</span><span class="sxs-lookup"><span data-stu-id="f9450-110">More Information</span></span>](#bkmk_more_information)  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq"></a> <span data-ttu-id="f9450-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f9450-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="f9450-112">Para las instalaciones locales, la cuenta con la que se ha iniciado sesión durante la instalación de SharePoint y [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] debe ser miembro del grupo de administradores del sistema operativo local.</span><span class="sxs-lookup"><span data-stu-id="f9450-112">For local installations, the account logged in during installation of SharePoint and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] needs to be a member of the administrators group in the local operating system.</span></span> <span data-ttu-id="f9450-113">No es necesario que la cuenta de instalación sea miembro del grupo administradores de la granja de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f9450-113">The setup account does not need to be a member of the SharePoint farm administrators group.</span></span>  
  
     <span data-ttu-id="f9450-114">Para obtener más información, vea [Configurar la seguridad y los permisos de cuenta en SharePoint 2013](https://technet.microsoft.com/library/cc678863.aspx).</span><span class="sxs-lookup"><span data-stu-id="f9450-114">For more information, see [Account permissions and security settings in SharePoint 2013](https://technet.microsoft.com/library/cc678863.aspx).</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="f9450-115">en modo de SharePoint necesita SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="f9450-115">running in SharePoint mode requires SharePoint Server.</span></span> <span data-ttu-id="f9450-116">Para obtener más información acerca de los requisitos y las configuraciones de SharePoint, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9450-116">For more information about SharePoint requirements and configurations, see the following:</span></span>  
  
    -   <span data-ttu-id="f9450-117">[Requisitos de hardware y software (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=256365) (https://go.microsoft.com/fwlink/p/?LinkId=256365)</span><span class="sxs-lookup"><span data-stu-id="f9450-117">[Hardware and software requirements (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=256365) (https://go.microsoft.com/fwlink/p/?LinkId=256365)</span></span>  
  
    -   [<span data-ttu-id="f9450-118">Administración y ajuste de tamaño de la capacidad de SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9450-118">Capacity management and sizing for SharePoint Server 2013</span></span>](https://technet.microsoft.com/library/cc261700.aspx)  
  
    -   [<span data-ttu-id="f9450-119">Requisitos de software para Business Intelligence (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="f9450-119">Software requirements for business intelligence (SharePoint 2013)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=256367)  
  
    -   <span data-ttu-id="f9450-120">[Requisitos de hardware y software (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262485\(v=office.14\))</span><span class="sxs-lookup"><span data-stu-id="f9450-120">[Hardware and software requirements (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262485\(v=office.14\))</span></span>  
  
    -   <span data-ttu-id="f9450-121">[Administración y ajuste de tamaño de la capacidad de SharePoint Server 2010](https://technet.microsoft.com/library/cc261700.aspx\(v=office.14\))</span><span class="sxs-lookup"><span data-stu-id="f9450-121">[Capacity management and sizing for SharePoint Server 2010](https://technet.microsoft.com/library/cc261700.aspx\(v=office.14\))</span></span>  
  
-   <span data-ttu-id="f9450-122">Si desea actualizar una instalación existente de SharePoint de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] con [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], vea [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f9450-122">If you want to upgrade or update existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint installation with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="f9450-123">Compruebe que el servicio **Administración de SharePoint 2013** está iniciado en Windows Server Manager.</span><span class="sxs-lookup"><span data-stu-id="f9450-123">Verify the **SharePoint 2013 Administration** service is started in Windows Server Manager.</span></span>  
  
###  <a name="report-server-database-requirements"></a><a name="bkmk_report_server_database"></a> <span data-ttu-id="f9450-124">Requisitos de base de datos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="f9450-124">Report Server Database Requirements</span></span>  
  
-   <span data-ttu-id="f9450-125">Tanto [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] como Productos y tecnologías de SharePoint usan bases de datos relacionales de SQL Server para almacenar datos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f9450-125">Both [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and SharePoint products and technologies use SQL Server relational databases to store application data.</span></span>  
  
-   [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)] <span data-ttu-id="f9450-126">necesita una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] de una edición de SQL Server compatible.</span><span class="sxs-lookup"><span data-stu-id="f9450-126">requires an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] of a compatible SQL Server edition.</span></span> <span data-ttu-id="f9450-127">Para obtener más información sobre los requisitos de hardware y software, vea [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f9450-127">For more information on hardware and software requirements, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   <span data-ttu-id="f9450-128">Los productos de SharePoint pueden utilizar una instancia de base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="f9450-128">SharePoint products can use an existing database instance.</span></span> <span data-ttu-id="f9450-129">Si no se instala ninguna instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , el programa de instalación de Productos de SharePoint instala SQL Server Express Edition para las bases de datos de aplicación de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f9450-129">If an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] is not installed, the SharePoint Products Setup program installs SQL Server Express Edition for the SharePoint application databases.</span></span>  
  
-   <span data-ttu-id="f9450-130">La instancia del servidor de informes no puede utilizar SQL Server Express Edition para su base de datos.</span><span class="sxs-lookup"><span data-stu-id="f9450-130">The report server instance cannot use the SQL Server Express Edition for its database.</span></span> <span data-ttu-id="f9450-131">Sin embargo, la instancia de SQL Server Express Edition instalada por el producto de SharePoint puede coexistir con otras ediciones del Motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="f9450-131">However, the SQL Server Express Edition instance installed by the SharePoint product can exist side-by-side with other Database Engine editions.</span></span>  
  
##  <a name="sscrescent-requirements"></a><a name="bkmk_powerview"></a><span data-ttu-id="f9450-132">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f9450-132">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] Requirements</span></span>

 <span data-ttu-id="f9450-133">Examine la [documentación de Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx) más actualizada en Office.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f9450-133">Review the most up-to-date [Power View documentation](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx) on Office.Microsoft.com.</span></span> [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="f9450-134">es una característica de Microsoft Excel 2013 y forma parte del complemento [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Reporting Services para las ediciones Enterprise de Microsoft SharePoint Server 2010 y 2013.</span><span class="sxs-lookup"><span data-stu-id="f9450-134">is a feature of Microsoft Excel 2013, and is part of the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Reporting Services add-in for Microsoft SharePoint Server 2010 and 2013 Enterprise Editions.</span></span>  
  
##  <a name="more-information"></a><a name="bkmk_more_information"></a> <span data-ttu-id="f9450-135">Más información</span><span class="sxs-lookup"><span data-stu-id="f9450-135">More Information</span></span>

 <span data-ttu-id="f9450-136">Para obtener información sobre los cambios de SharePoint, vea [cambios de sharepoint 2010 a sharepoint 2013](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) ( https://technet.microsoft.com/library/ff607742(office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="f9450-136">For information on SharePoint changes, see [Changes from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) (https://technet.microsoft.com/library/ff607742(office.15).aspx).</span></span>  
  
 <span data-ttu-id="f9450-137">[SQL Server notas](https://go.microsoft.com/fwlink/?LinkID=296445)de la versión de 2014.</span><span class="sxs-lookup"><span data-stu-id="f9450-137">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
