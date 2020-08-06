---
title: Roles y permisos (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- access controls [Reporting Services]
- permissions [Reporting Services], about permissions
- security [Reporting Services], identity and access control
- authentication [Reporting Services]
- permissions [Reporting Services]
- security [Reporting Services], role-based
- identity [Reporting Services]
ms.assetid: eea655fe-43ed-418d-8233-b288a8f4daa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0e6098a51afde04164e3ef0dfa5e5297457b4440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673473"
---
# <a name="roles-and-permissions-reporting-services"></a><span data-ttu-id="76331-102">Roles y permisos (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="76331-102">Roles and Permissions (Reporting Services)</span></span>
  <span data-ttu-id="76331-103">Reporting Services proporciona un subsistema de autenticación y un modelo de autorización basada en roles.</span><span class="sxs-lookup"><span data-stu-id="76331-103">Reporting Services provides an authentication subsystem and role-based authorization model.</span></span> <span data-ttu-id="76331-104">Los modelos de autenticación y autorización varían en función de que el servidor de informes se ejecute en modo nativo o en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="76331-104">Authentication and authorization models vary depending on whether the report server runs in native mode or SharePoint mode.</span></span> <span data-ttu-id="76331-105">Si el servidor de informes forma parte de una implementación de SharePoint, los permisos de SharePoint determinarán quién tiene acceso a dicho servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="76331-105">If the report server is part of a SharePoint deployment, SharePoint permissions determine who has access to the report server.</span></span>  
  
## <a name="identity-and-access-control-for-native-mode"></a><span data-ttu-id="76331-106">Identidad y control de acceso para el modo nativo</span><span class="sxs-lookup"><span data-stu-id="76331-106">Identity and Access Control for Native Mode</span></span>  
 <span data-ttu-id="76331-107">La autenticación predeterminada se basa en la autenticación de Windows y en la seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="76331-107">Default authentication is based on Windows Authentication and integrated security.</span></span> <span data-ttu-id="76331-108">Puede cambiar los valores de autenticación para permitir al servidor de informes responder a solicitudes de autenticación diferentes, o también reemplazar las características de seguridad predeterminadas por una extensión de autenticación personalizada.</span><span class="sxs-lookup"><span data-stu-id="76331-108">You can change the authentication settings to allow the report server to respond to different authentication requests, or even replace the default security features with a custom authentication extension that you provide.</span></span>  
  
 <span data-ttu-id="76331-109">La autorización se basa en roles que el usuario asigna a un principio.</span><span class="sxs-lookup"><span data-stu-id="76331-109">Authorization is based on roles that you assign to a principle.</span></span> <span data-ttu-id="76331-110">Cada rol se compone de un conjunto de tareas relacionadas compuestas, a su vez, de operaciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="76331-110">Each role consists of a set of related tasks, which are in turn composed of related operations.</span></span> <span data-ttu-id="76331-111">Por ejemplo, la tarea **Administrar informes** concede acceso a las siguientes operaciones del servidor de informes: ver informes, agregar informe, actualizar informe, eliminar informe, programar informe y actualizar propiedades del informe.</span><span class="sxs-lookup"><span data-stu-id="76331-111">For example, the **Manage reports** task grants access to the following report server operations: view reports, add report, update report, delete report, schedule report, and update report properties.</span></span>  
  
## <a name="identity-and-access-control-for-sharepoint-mode"></a><span data-ttu-id="76331-112">Identidad y control de acceso para el modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="76331-112">Identity and Access Control for SharePoint Mode</span></span>  
 <span data-ttu-id="76331-113">En el modo integrado de SharePoint, la autenticación y la autorización se administran en el sitio de SharePoint, antes de que las solicitudes lleguen al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="76331-113">In SharePoint integrated mode, authentication and authorization are handled on the SharePoint site, before requests reach the report server.</span></span> <span data-ttu-id="76331-114">Dependiendo de cómo configure la autenticación, las solicitudes procedentes de un sitio de SharePoint incluyen un token de seguridad o un nombre de usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="76331-114">Depending on how you configure authentication, requests from a SharePoint site include a security token or a trusted user name.</span></span> <span data-ttu-id="76331-115">Los permisos que establezca para los usuarios y los grupos de SharePoint autorizarán el acceso a los elementos del servidor de informes situados en bibliotecas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="76331-115">Permissions that you set for SharePoint users and groups authorize access to report server items that are placed in SharePoint libraries.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76331-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="76331-116">In This Section</span></span>  
 [<span data-ttu-id="76331-117">Concesión de permisos en un servidor de informes en modo nativo</span><span class="sxs-lookup"><span data-stu-id="76331-117">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
 <span data-ttu-id="76331-118">Describe el modelo de autorización basada en roles que proporciona acceso al contenido y a las operaciones.</span><span class="sxs-lookup"><span data-stu-id="76331-118">Describes the role-based authorization model that provides access to content and operations.</span></span>  
  
 [<span data-ttu-id="76331-119">Concesión de permisos sobre elementos del servidor de informes en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="76331-119">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
 <span data-ttu-id="76331-120">Explica cómo se usan los grupos de SharePoint, los niveles de permiso y los permisos para controlar el acceso a un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="76331-120">Explains how SharePoint groups, permission levels, and permissions are used to control access to a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76331-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76331-121">See Also</span></span>  
 <span data-ttu-id="76331-122">[Autenticación con el servidor de informes](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="76331-122">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 [<span data-ttu-id="76331-123">Concesión de permisos en un servidor de informes en modo nativo</span><span class="sxs-lookup"><span data-stu-id="76331-123">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
