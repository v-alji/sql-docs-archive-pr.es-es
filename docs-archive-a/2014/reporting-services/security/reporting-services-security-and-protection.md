---
title: Seguridad y protección de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- security [Reporting Services]
- Reporting Services, security
ms.assetid: 270075c5-bf12-4467-a775-abbda3d954a5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0f8c7a4186c5236260fb27d8de107ce8c97bd363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676858"
---
# <a name="reporting-services-security-and-protection"></a><span data-ttu-id="34ce0-102">Seguridad y protección de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="34ce0-102">Reporting Services Security and Protection</span></span>
  <span data-ttu-id="34ce0-103">Puede usar la información de esta sección para obtener información acerca de las características de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34ce0-103">You can use information in this section to learn about the security features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="34ce0-104">También se explican en ella los modelos de autorización y los proveedores de autenticación que se admiten en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34ce0-104">This section also explains the authorization models and authentication providers supported in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="extended-protection-for-authentication"></a><span data-ttu-id="34ce0-105">Protección ampliada para la autenticación</span><span class="sxs-lookup"><span data-stu-id="34ce0-105">Extended Protection for Authentication</span></span>  
 <span data-ttu-id="34ce0-106">A partir de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], se admite la protección ampliada para autenticación.</span><span class="sxs-lookup"><span data-stu-id="34ce0-106">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], support for Extended Protection for Authentication is available.</span></span> <span data-ttu-id="34ce0-107">La característica de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite el uso del enlace de canal y del enlace de servicio para mejorar la protección de la autenticación.</span><span class="sxs-lookup"><span data-stu-id="34ce0-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature supports the use of channel binding and service binding to enhance protection of authentication.</span></span> <span data-ttu-id="34ce0-108">Las características de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tienen que usarse con un sistema operativo que admita la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="34ce0-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features need to be used with an operating system that supports Extended Protection.</span></span> <span data-ttu-id="34ce0-109">Para más información, consulte [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="34ce0-109">For more information, see [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span></span>  
  
## <a name="authentication-and-authorization"></a><span data-ttu-id="34ce0-110">Autenticación y autorización</span><span class="sxs-lookup"><span data-stu-id="34ce0-110">Authentication and Authorization</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="34ce0-111">proporciona diferentes tipos de autenticación para que los usuarios y las aplicaciones cliente se autentiquen en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="34ce0-111">provides different authentication types for users and client applications to authenticate with the report server.</span></span> <span data-ttu-id="34ce0-112">La utilización del tipo de autenticación adecuado para el servidor de informes permite a su organización lograr el nivel de seguridad necesario.</span><span class="sxs-lookup"><span data-stu-id="34ce0-112">Using the right authentication type for your report server enables your organization to achieve the appropriate level of security required by your organization.</span></span> <span data-ttu-id="34ce0-113">Para más información, consulte [Authentication with the Report Server](authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="34ce0-113">For more information, see [Authentication with the Report Server](authentication-with-the-report-server.md).</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="34ce0-114">también emplea roles y permisos para controlar el acceso de usuario al contenido del catálogo del servidor de informes (es decir, quién tiene acceso a qué y cómo puede obtener acceso).</span><span class="sxs-lookup"><span data-stu-id="34ce0-114">also employs roles and permissions to control user access to content in the report server catalog (in other words, who can access what, and how s/he can access it).</span></span> <span data-ttu-id="34ce0-115">Para obtener más información, vea [Roles y permisos &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="34ce0-115">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="34ce0-116">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="34ce0-116">Related Tasks</span></span>  
  
|<span data-ttu-id="34ce0-117">Descripciones de las tareas</span><span class="sxs-lookup"><span data-stu-id="34ce0-117">Task Descriptions</span></span>|<span data-ttu-id="34ce0-118">Vínculos</span><span class="sxs-lookup"><span data-stu-id="34ce0-118">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="34ce0-119">Configurar SSL (Capa de sockets seguros) para proteger las conexiones de cliente al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="34ce0-119">Configure the Secure Socket Layer (SSL) to secure client connections to the report server.</span></span>|[<span data-ttu-id="34ce0-120">Configurar conexiones SSL en un servidor de informes en modo nativo</span><span class="sxs-lookup"><span data-stu-id="34ce0-120">Configure SSL Connections on a Native Mode Report Server</span></span>](configure-ssl-connections-on-a-native-mode-report-server.md)|  
  
  
