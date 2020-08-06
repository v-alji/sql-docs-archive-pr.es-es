---
title: Configurar la base de datos y el sitio web para Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
f1_keywords:
- sql12.mds.configmanager.general.f1
ms.assetid: d50863e7-50d9-4ab8-aabb-fd68e2d132a1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da797bc6f9838a2baab6cc440cc7d778a7a6e186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677744"
---
# <a name="set-up-the-database-and-website-for-master-data-services"></a><span data-ttu-id="acb42-102">Configurar la base de datos y el sitio web para Master Data Services</span><span class="sxs-lookup"><span data-stu-id="acb42-102">Set up the Database and Website for Master Data Services</span></span>
  <span data-ttu-id="acb42-103">Use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] para configurar la base de datos y el sitio web para [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span><span class="sxs-lookup"><span data-stu-id="acb42-103">Use the [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to set up the database and website for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span></span>  
  
 <span data-ttu-id="acb42-104">Para configurar la base de datos y el sitio web, realice las tareas siguientes.</span><span class="sxs-lookup"><span data-stu-id="acb42-104">To set up the database and website, complete the following tasks.</span></span>  
  
1.  <span data-ttu-id="acb42-105">Cree una base de datos mediante la página **configuración de base de datos** en [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="acb42-105">Create a database using the **Database Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="acb42-106">Para obtener más información, vea [página Configuración de base de datos &#40;administrador de configuración de Master Data Services](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) [Asistente para&#41;y crear base de datos &#40;administrador de configuración de Master Data Services ](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md)&#41;.</span><span class="sxs-lookup"><span data-stu-id="acb42-106">For information, see [Database Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) and [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
2.  <span data-ttu-id="acb42-107">Cree un nuevo sitio web, seleccione el sitio web predeterminado o seleccione otro sitio web existente mediante la página **configuración Web** en [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="acb42-107">Create a new website, select the default website, or select another existing website, using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="acb42-108">Luego, asocie la base de datos de MDS a la aplicación web que seleccione o cree.</span><span class="sxs-lookup"><span data-stu-id="acb42-108">Then associate the MDS database with the web application you select or create.</span></span>  
  
     <span data-ttu-id="acb42-109">Para obtener más información, vea [página Configuración Web &#40;administrador de configuración de Master Data Services](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) cuadro de diálogo&#41;y [crear sitio web &#40;administrador de configuración de Master Data Services ](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md)&#41;.</span><span class="sxs-lookup"><span data-stu-id="acb42-109">For information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
3.  <span data-ttu-id="acb42-110">Opta Habilite la integración con Data Quality Services mediante la página **configuración Web** en [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="acb42-110">(Optional) Enable integration with Data Quality Services using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="acb42-111">Para obtener más información, vea la [página Configuración Web &#40;Administrador de configuración de Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) y [Habilitar la integración de Data Quality Services con Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="acb42-111">For more information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Enable Data Quality Services Integration with Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span></span>  
  
 <span data-ttu-id="acb42-112">También puede usar [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] para especificar la configuración de las aplicaciones web y los servicios asociados a la base de datos de MDS.</span><span class="sxs-lookup"><span data-stu-id="acb42-112">You can also use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to specify settings for the web applications and services associated with the MDS database.</span></span> <span data-ttu-id="acb42-113">Por ejemplo, puede especificar la frecuencia con la que se cargan los datos o con la que se envían correos electrónico de validación.</span><span class="sxs-lookup"><span data-stu-id="acb42-113">For example, you can specify how frequently data is loaded or how often validation emails are sent.</span></span> <span data-ttu-id="acb42-114">Para obtener más información, vea [Configuración del sistema &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="acb42-114">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb42-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acb42-115">See Also</span></span>  
 <span data-ttu-id="acb42-116">[Master Data Services base de datos](../../2014/master-data-services/master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="acb42-116">[Master Data Services Database](../../2014/master-data-services/master-data-services-database.md) </span></span>  
 [<span data-ttu-id="acb42-117">Aplicación web Master Data Services</span><span class="sxs-lookup"><span data-stu-id="acb42-117">Master Data Manager Web Application</span></span>](../../2014/master-data-services/master-data-manager-web-application.md)  
  
  
