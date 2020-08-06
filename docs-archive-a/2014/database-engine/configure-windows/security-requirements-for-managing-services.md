---
title: Requisitos de seguridad para administrar servicios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent service, security
- services [SQL Server], security
- SQL Server services, security
- WMI Providers [SQL Server]
- server configuration [SQL Server]
- security [SQL Server], services
- services [SQL Server], WMI
ms.assetid: 1874a317-ddb2-425d-98d9-b53e1be6fc6a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 46a777858c01bf3057093d34b29b9a2093668e97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748913"
---
# <a name="security-requirements-for-managing-services"></a><span data-ttu-id="37f35-102">Requisitos de seguridad para administrar servicios</span><span class="sxs-lookup"><span data-stu-id="37f35-102">Security Requirements for Managing Services</span></span>
  <span data-ttu-id="37f35-103">Para administrar los servicios de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use el Administrador de configuración de SQL Server o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f35-103">To manage the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Services, use either SQL Server Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="37f35-104">Los servicios de los servidores en clúster se administran con el Administrador de clústeres.</span><span class="sxs-lookup"><span data-stu-id="37f35-104">Manage the services on clustered servers with the Cluster Administrator.</span></span>  
  
 <span data-ttu-id="37f35-105">Para poder administrar el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y establecer las opciones de configuración del servidor, debe ser miembro del rol fijo de servidor **serveradmin** o **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="37f35-105">To manage the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service and set the server configuration options, you must be a member of the **serveradmin** fixed server role or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="37f35-106">Los miembros del grupo **Administradores** de Windows pueden iniciar y detener servicios, así como configurar las opciones del servidor que ofrece Windows.</span><span class="sxs-lookup"><span data-stu-id="37f35-106">Members of the Windows **Administrators** group can start and stop services and configure the server options that Windows provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37f35-107">Para que funcionen correctamente, las cuentas utilizadas por los servicios deben estar configurar con el dominio, el sistema de archivos y los permisos de registro correctos.</span><span class="sxs-lookup"><span data-stu-id="37f35-107">To operate properly, the accounts used for the services must be configured with the correct domain, file system, and registry permissions.</span></span> <span data-ttu-id="37f35-108">Para obtener información sobre los permisos necesarios, vea [Configurar los permisos y las cuentas de servicio de Windows](configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="37f35-108">For information about the required permissions, see [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md).</span></span>  
  
## <a name="windows-management-instrumentation"></a><span data-ttu-id="37f35-109">Instrumental de administración de Windows</span><span class="sxs-lookup"><span data-stu-id="37f35-109">Windows Management Instrumentation</span></span>  
 <span data-ttu-id="37f35-110">El Administrador de configuración de SQL Server y [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] utilizan Instrumental de administración de Windows (WMI) para visualizar y modificar algunas de las propiedades del servidor.</span><span class="sxs-lookup"><span data-stu-id="37f35-110">SQL Server Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] use Windows Management Instrumentation (WMI) to display and modify some of the server properties.</span></span> <span data-ttu-id="37f35-111">Para administrar servicios y obtener su estado, el usuario debe tener los derechos necesarios para el acceso al objeto de WMI.</span><span class="sxs-lookup"><span data-stu-id="37f35-111">To manage services and obtain the status of the services, the user must have rights to access the WMI object.</span></span> <span data-ttu-id="37f35-112">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], utilizan WMI las páginas de propiedades del servidor siguientes:</span><span class="sxs-lookup"><span data-stu-id="37f35-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the following server property pages use WMI:</span></span>  
  
-   <span data-ttu-id="37f35-113">Servicios de inicio automático</span><span class="sxs-lookup"><span data-stu-id="37f35-113">Autostart Services</span></span>  
  
-   <span data-ttu-id="37f35-114">Parámetros de inicio</span><span class="sxs-lookup"><span data-stu-id="37f35-114">Startup Parameters</span></span>  
  
-   <span data-ttu-id="37f35-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="37f35-115">Security</span></span>  
  
-   <span data-ttu-id="37f35-116">Configuración adicional del servidor</span><span class="sxs-lookup"><span data-stu-id="37f35-116">Misc Server Settings</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="37f35-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="37f35-117">Related Tasks</span></span>  
 [<span data-ttu-id="37f35-118">Configurar WMI para mostrar el estado del servidor en Herramientas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="37f35-118">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
## <a name="related-content"></a><span data-ttu-id="37f35-119">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="37f35-119">Related Content</span></span>  
 [<span data-ttu-id="37f35-120">Conceptos del proveedor WMI de administración de configuración</span><span class="sxs-lookup"><span data-stu-id="37f35-120">WMI Provider for Configuration Management Concepts</span></span>](../../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
