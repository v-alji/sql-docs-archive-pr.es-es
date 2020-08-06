---
title: Implementar una extensión de seguridad | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
- forms-based authentication [Reporting Services]
- custom authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: d2327e7c-0d48-49e3-bcd9-3bba4e67a68b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e5cf1fa6ce0e0a02a52e6a27f693c152d1f97152
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673506"
---
# <a name="implementing-a-security-extension"></a><span data-ttu-id="a412c-102">Implementar una extensión de seguridad</span><span class="sxs-lookup"><span data-stu-id="a412c-102">Implementing a Security Extension</span></span>
  <span data-ttu-id="a412c-103">La autenticación de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows constituye el sistema principal para proteger los informes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a412c-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Authentication is the primary system for securing reports in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="a412c-104">En ciertos casos, sin embargo, puede necesitar extender el sistema de seguridad de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para organizar la seguridad personalizada en una empresa.</span><span class="sxs-lookup"><span data-stu-id="a412c-104">In certain cases, however, you may need to extend the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security system to accommodate custom security in your enterprise.</span></span> <span data-ttu-id="a412c-105">Para ello, puede usar la plataforma de desarrollo que proporciona la API de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a412c-105">You can do this using the development platform provided by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="a412c-106">En esta sección se presentará información general sobre las extensiones de seguridad en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a412c-106">This section will present an overview of security extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a412c-107">Para obtener información detallada sobre cómo implementar y quitar una extensión de seguridad de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], vea [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Muestras de productos de SQL Server Reporting Services).</span><span class="sxs-lookup"><span data-stu-id="a412c-107">For complete details about implementing, deploying, and removing a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension, please see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a412c-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a412c-108">In This Section</span></span>  
 [<span data-ttu-id="a412c-109">Información general de extensiones de seguridad</span><span class="sxs-lookup"><span data-stu-id="a412c-109">Security Extensions Overview</span></span>](security-extensions-overview.md)  
 <span data-ttu-id="a412c-110">Proporciona información general de las extensiones de seguridad de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="a412c-110">Provides an overview of Reporting Services Security Extensions.</span></span>  
  
 [<span data-ttu-id="a412c-111">Autenticación de Windows en Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a412c-111">Authentication in Reporting Services</span></span>](authentication-in-reporting-services.md)  
 <span data-ttu-id="a412c-112">Explica la autenticación en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a412c-112">Discusses authentication in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="a412c-113">Autorización en Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a412c-113">Authorization in Reporting Services</span></span>](authorization-in-reporting-services.md)  
 <span data-ttu-id="a412c-114">Trata la autorización en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a412c-114">Covers authorization in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a412c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a412c-115">See Also</span></span>  
 <xref:Microsoft.ReportingServices.Interfaces>   
 <span data-ttu-id="a412c-116">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="a412c-116">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="a412c-117">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a412c-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
