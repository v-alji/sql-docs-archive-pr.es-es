---
title: Activar la integración de características de PowerPivot para colecciones de sitios en administración central | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 62a27e53-446a-42d7-b5db-c009e02d4904
author: minewiskan
ms.author: owend
ms.openlocfilehash: b565434cba197d04327e833d4ac6eab3caf96646
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745421"
---
# <a name="activate-powerpivot-feature-integration-for-site-collections-in-central-administration"></a><span data-ttu-id="415f7-102">Activar la integración de características de PowerPivot para colecciones de sitios en Administración central</span><span class="sxs-lookup"><span data-stu-id="415f7-102">Activate PowerPivot Feature Integration for Site Collections in Central Administration</span></span>
  <span data-ttu-id="415f7-103">Activar la integración de características de PowerPivot para colecciones de sitios concretos es necesario si usó la opción de instalación Granja existente para instalar SQL Server PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="415f7-103">Activating PowerPivot feature integration for specific site collections is required if you used the Existing Farm installation option to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="415f7-104">Si instaló PowerPivot para SharePoint con la opción Nuevo servidor, puede omitir esta tarea, porque el programa de instalación de SQL Server ya activó la integración de características de PowerPivot para la colección de sitios raíz al configurar la implementación.</span><span class="sxs-lookup"><span data-stu-id="415f7-104">If you installed PowerPivot for SharePoint using the New Server option, you can skip this task because SQL Server Setup already activated PowerPivot feature integration for the root site collection when it configured your deployment.</span></span>  
  
 <span data-ttu-id="415f7-105">La activación de características en el nivel de colección de sitios es necesario para que las plantillas y las páginas de las aplicaciones estén disponibles para los sitios, incluidas las páginas de configuración para la actualización de datos programada y las páginas de aplicación para las bibliotecas de Galería de PowerPivot y de fuentes de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="415f7-105">Feature activation at the site collection level is necessary to make application pages and templates available to your sites, including configuration pages for scheduled data refresh and application pages for PowerPivot Gallery and Data Feed libraries.</span></span>  
  
 <span data-ttu-id="415f7-106">Debe activar la integración de PowerPivot para cada colección de sitios que admita el procesamiento de consultas de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="415f7-106">You must activate PowerPivot integration for each site collection that supports PowerPivot query processing.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="415f7-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="415f7-107">Prerequisites</span></span>  
 <span data-ttu-id="415f7-108">Debe ser administrador de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="415f7-108">You must be a site collection administrator.</span></span>  
  
## <a name="activate-powerpivot-features"></a><span data-ttu-id="415f7-109">Activar las características de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="415f7-109">Activate PowerPivot Features</span></span>  
  
1.  <span data-ttu-id="415f7-110">En un sitio de SharePoint, haga clic en **Acciones de sitio**.</span><span class="sxs-lookup"><span data-stu-id="415f7-110">On a SharePoint site, click **Site Actions**.</span></span>  
  
     <span data-ttu-id="415f7-111">De forma predeterminada, se tiene acceso a las aplicaciones web de SharePoint a través del puerto 80.</span><span class="sxs-lookup"><span data-stu-id="415f7-111">By default, SharePoint web applications are accessed through port 80.</span></span> <span data-ttu-id="415f7-112">Esto significa que normalmente puede acceder a un sitio de SharePoint si escribe http://\<computer name> para abrir la colección de sitios raíz.</span><span class="sxs-lookup"><span data-stu-id="415f7-112">This means that you can often access a SharePoint site by entering http://\<computer name> to open the root site collection.</span></span>  
  
2.  <span data-ttu-id="415f7-113">Haga clic en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="415f7-113">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="415f7-114">En Administración de la colección de sitios, haga clic en **Características de la colección de sitios**.</span><span class="sxs-lookup"><span data-stu-id="415f7-114">In Site Collection Administration, click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="415f7-115">Desplácese hacia abajo en la página hasta que encuentre la **característica de colección de sitios de integración de PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="415f7-115">Scroll down the page until you find **PowerPivot Integration Site Collection Feature**.</span></span>  
  
5.  <span data-ttu-id="415f7-116">Haga clic en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="415f7-116">Click **Activate**.</span></span>  
  
6.  <span data-ttu-id="415f7-117">Repita este procedimiento con las demás colecciones de sitios abriendo cada sitio y haciendo clic en **Acciones de sitio**.</span><span class="sxs-lookup"><span data-stu-id="415f7-117">Repeat for additional site collections by opening each site and clicking **Site Actions**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="415f7-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="415f7-118">See Also</span></span>  
 <span data-ttu-id="415f7-119">[Administración y configuración del servidor de PowerPivot en administración central](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="415f7-119">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 <span data-ttu-id="415f7-120">[PowerPivot para SharePoint de &#40;de configuración inicial&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="415f7-120">[Initial Configuration &#40;PowerPivot for SharePoint&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="415f7-121">Instalación de PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="415f7-121">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
