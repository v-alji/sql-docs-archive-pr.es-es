---
title: Información general del proceso de actualización | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
- Upgrade Advisor [SQL Server], process description
- SQL Server Upgrade Advisor, process description
- upgrade process [Upgrade Advisor]
ms.assetid: f77ffbab-a195-4124-acce-9c538f7ca9ce
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5da6dc3b3e6d6c7058193801100bf2552bfde7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751673"
---
# <a name="upgrade-process-overview"></a><span data-ttu-id="d93bd-102">Información general sobre el proceso de actualización</span><span class="sxs-lookup"><span data-stu-id="d93bd-102">Upgrade Process Overview</span></span>
  <span data-ttu-id="d93bd-103">En este tema se proporciona información sobre el procedimiento recomendado para el Asesor de actualizaciones de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] y un resumen del proceso recomendado para actualizar a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d93bd-103">This topic provides best practice information for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor and a summary of the recommended process for upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="upgrade-process"></a><span data-ttu-id="d93bd-104">Proceso de actualización</span><span class="sxs-lookup"><span data-stu-id="d93bd-104">Upgrade Process</span></span>  
 <span data-ttu-id="d93bd-105">Los servidores que estén ejecutando [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] se pueden actualizar a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d93bd-105">Servers that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] can be upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d93bd-106">Mientras que algunos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componentes se pueden actualizar en su lugar, otros se deben migrar y otros se han sustituido por componentes nuevos.</span><span class="sxs-lookup"><span data-stu-id="d93bd-106">Whereas some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components can be upgraded in place, others must be migrated, and still others have been superseded by new components.</span></span> <span data-ttu-id="d93bd-107">Por ejemplo, a partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) reemplaza Data Transformation Services (DTS) y DTS ya no se admite en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d93bd-107">For example, starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) supersedes Data Transformation Services (DTS), and DTS is no longer supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d93bd-108">Al formular el plan de actualización, es posible que sea necesario planear la actualización de los paquetes DTS a los paquetes [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d93bd-108">When you formulate your upgrade plan, you might need to plan for updating your current DTS packages to [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages.</span></span>  
  
 <span data-ttu-id="d93bd-109">El Asesor de actualizaciones permite evaluar instalaciones, componentes y archivos relacionados de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] actuales para identificar problemas conocidos que aparecerán durante y después de la migración o actualización a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d93bd-109">Upgrade Advisor enables you to evaluate current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installations, components, and related files to identify known issues that will cause problems both during and after you upgrade or migrate to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d93bd-110">Algunos de estos problemas conocidos bloquean la actualización de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d93bd-110">A few of these known issues block the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] upgrade.</span></span> <span data-ttu-id="d93bd-111">En el informe del Asesor de actualizaciones, estos problemas se identifican como Bloqueos de la actualización.</span><span class="sxs-lookup"><span data-stu-id="d93bd-111">In the Upgrade Advisor report, these issues are identified as Upgrade Blockers.</span></span> <span data-ttu-id="d93bd-112">Si no ha solucionado los bloqueos de la actualización antes de ejecutar el programa de instalación, el programa de instalación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sale y recomienda actualizar el Asesor de actualizaciones para identificar los problemas específicos que impiden la actualización.</span><span class="sxs-lookup"><span data-stu-id="d93bd-112">If you have not addressed the Upgrade Blockers before you run Setup, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup exits and recommends that you run Upgrade Advisor to identify the specific issues that are blocking the upgrade.</span></span>  
  
 <span data-ttu-id="d93bd-113">Como práctica recomendada antes de actualizar a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], recomendamos que haga copia de seguridad de sus datos y configuraciones del sistema, y que siga los pasos estratégicos descritos en las instrucciones operativas definidas para su organización.</span><span class="sxs-lookup"><span data-stu-id="d93bd-113">As a best practice before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you back up your data and system settings, and take strategic steps as outlined in the operational guidelines defined for your organization.</span></span> <span data-ttu-id="d93bd-114">Siga los pasos que se detallan a continuación para completar la actualización:</span><span class="sxs-lookup"><span data-stu-id="d93bd-114">Use the following steps to complete the upgrade:</span></span>  
  
1.  <span data-ttu-id="d93bd-115">Vea [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d93bd-115">Review [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="d93bd-116">Haga una copia de seguridad de los datos y de la configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="d93bd-116">Back up data and system settings.</span></span>  
  
3.  <span data-ttu-id="d93bd-117">Ejecute el Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="d93bd-117">Run Upgrade Advisor.</span></span>  
  
     <span data-ttu-id="d93bd-118">El Asesor de actualizaciones no modificará los datos ni cambiará la configuración de su equipo.</span><span class="sxs-lookup"><span data-stu-id="d93bd-118">Upgrade Advisor does not modify your data or change settings on your computer.</span></span>  
  
4.  <span data-ttu-id="d93bd-119">Revise los problemas identificados en el informe del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="d93bd-119">Review the issues identified in the Upgrade Advisor report.</span></span>  
  
5.  <span data-ttu-id="d93bd-120">Resuelva cualquier problema de bloqueo que pudiera impedir la actualización a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d93bd-120">Resolve any blocking issues that would prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
6.  <span data-ttu-id="d93bd-121">Resuelva cualquier otro problema previo a la actualización.</span><span class="sxs-lookup"><span data-stu-id="d93bd-121">Resolve any other pre-upgrade issues.</span></span>  
  
7.  <span data-ttu-id="d93bd-122">Ejecute el Asesor de actualizaciones para comprobar que se han resuelto todos los problemas conocidos.</span><span class="sxs-lookup"><span data-stu-id="d93bd-122">Run Upgrade Advisor to verify that all known issues have been addressed.</span></span>  
  
8.  <span data-ttu-id="d93bd-123">Ejecute el programa de instalación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d93bd-123">Run [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup.</span></span>  
  
9. <span data-ttu-id="d93bd-124">Resuelva cualquier problema de migración o posterior a la actualización.</span><span class="sxs-lookup"><span data-stu-id="d93bd-124">Resolve any post-upgrade and migration issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d93bd-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d93bd-125">See Also</span></span>  
 <span data-ttu-id="d93bd-126">[Ejecutar el asesor de actualizaciones &#40;interfaz de usuario&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="d93bd-126">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 <span data-ttu-id="d93bd-127">[Uso de informes](../../../2014/sql-server/install/using-reports.md) </span><span class="sxs-lookup"><span data-stu-id="d93bd-127">[Using Reports](../../../2014/sql-server/install/using-reports.md) </span></span>  
 [<span data-ttu-id="d93bd-128">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="d93bd-128">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
