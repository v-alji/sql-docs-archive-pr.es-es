---
title: 'rsAccessedDenied: error de Reporting Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsAccessDenied error
ms.assetid: 2f76b1bf-96a2-4755-b76b-84e933220efc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 194006c2ef6f22b9bc27e9e8cbe1eebd027ed6b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673453"
---
# <a name="rsaccesseddenied---reporting-services-error"></a><span data-ttu-id="af895-102">rsAccessedDenied - Error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="af895-102">rsAccessedDenied - Reporting Services Error</span></span>
  <span data-ttu-id="af895-103">El error [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] rsAccessedDenied **en** se produce cuando un usuario no dispone de permiso para realizar una acción.</span><span class="sxs-lookup"><span data-stu-id="af895-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] error **rsAccessedDenied** occurs when a user does not have permission to perform an action.</span></span> <span data-ttu-id="af895-104">Por ejemplo, el usuario no dispone de una asignación de rol que le permita abrir un informe o no abrió el explorador con los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="af895-104">For, example, they do not have a role assignment that allows them to open a report or they did not open their browser with the required permissions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="af895-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; Modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="af895-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; SharePoint mode</span></span>|  
  
-   <span data-ttu-id="af895-106">Si el error se produce al obtener acceso al servidor de informes directamente a través de una dirección URL, la excepción se asigna a un error de HTTP 401.</span><span class="sxs-lookup"><span data-stu-id="af895-106">If the error occurred while accessing the report server directly through a URL, the exception is mapped to an HTTP 401 error.</span></span>  
  
-   <span data-ttu-id="af895-107">Si el error se produce al utilizar el Administrador de informes u otra herramienta, aparece en una página de error.</span><span class="sxs-lookup"><span data-stu-id="af895-107">If the error occurred while using Report Manager or another tool, the error appears in an error page.</span></span>  
  
-   <span data-ttu-id="af895-108">Si el error se produce durante una operación programada, suscripción o entrega, aparecerá solamente en el archivo de registro del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af895-108">If the error occurred during a scheduled operation, subscription, or delivery, the error will appear in the report server log file only.</span></span>  
  
## <a name="details"></a><span data-ttu-id="af895-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="af895-109">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af895-110">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="af895-110">**Product Name**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="af895-111">**Identificador del evento**</span><span class="sxs-lookup"><span data-stu-id="af895-111">**Event ID**</span></span>|<span data-ttu-id="af895-112">en</span><span class="sxs-lookup"><span data-stu-id="af895-112">rsAccessedDenied</span></span>|  
|<span data-ttu-id="af895-113">**Origen del evento**</span><span class="sxs-lookup"><span data-stu-id="af895-113">**Event Source**</span></span>|<span data-ttu-id="af895-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="af895-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="af895-115">**Componente**</span><span class="sxs-lookup"><span data-stu-id="af895-115">**Component**</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="af895-116">**Texto del mensaje**</span><span class="sxs-lookup"><span data-stu-id="af895-116">**Message Text**</span></span>|<span data-ttu-id="af895-117">Los permisos otorgados al usuario 'miDominio\miCuenta' son insuficientes para realizar esta operación.</span><span class="sxs-lookup"><span data-stu-id="af895-117">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="af895-118">(rsAccessDenied) (ReportingServicesLibrary)</span><span class="sxs-lookup"><span data-stu-id="af895-118">(rsAccessDenied) (ReportingServicesLibrary)</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="af895-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="af895-119">User Action</span></span>  
 <span data-ttu-id="af895-120">El permiso para obtener acceso al contenido y a las operaciones del servidor de informes se concede mediante asignaciones de roles.</span><span class="sxs-lookup"><span data-stu-id="af895-120">Permission to access report server content and operations are granted through role assignments.</span></span> <span data-ttu-id="af895-121">En una nueva instalación, solo los administradores locales tienen acceso a un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af895-121">On a new installation, only local administrators have access to a report server.</span></span> <span data-ttu-id="af895-122">Para conceder acceso a otros usuarios, el administrador local debe crear una asignación de roles que especifique una cuenta de grupo o usuario de dominio, uno o más roles que definan las tareas que el usuario puede realizar y un ámbito (normalmente la carpeta Inicio o el nodo raíz de la jerarquía de carpetas del servidor de informes).</span><span class="sxs-lookup"><span data-stu-id="af895-122">To grant access to other users, a local administrator must create a role assignment that specifies a domain user or group account, one or more roles that define the tasks the user can perform, and a scope (usually the Home folder or root node of the report server folder hierarchy).</span></span> <span data-ttu-id="af895-123">Puede usar el Administrador de informes para crear las asignaciones de roles.</span><span class="sxs-lookup"><span data-stu-id="af895-123">You can use Report Manager to create the role assignments.</span></span> <span data-ttu-id="af895-124">Para obtener más información, busque "Asignaciones de roles" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af895-124">For more information, search for "Role Assignments" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="af895-125">Este error también se produce por la administración local del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af895-125">This error is also caused by local administration of the report server.</span></span> <span data-ttu-id="af895-126">Para más información, vea [Configurar un servidor de informes en modo nativo para la administración local &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="af895-126">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af895-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af895-127">See Also</span></span>  
 <span data-ttu-id="af895-128">[Asignaciones de roles](../security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="af895-128">[Role Assignments](../security/role-assignments.md) </span></span>  
 <span data-ttu-id="af895-129">[Conceder permisos en un servidor de informes en modo nativo](../security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="af895-129">[Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="af895-130">Roles y permisos &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="af895-130">Roles and Permissions &#40;Reporting Services&#41;</span></span>](../security/roles-and-permissions-reporting-services.md)  
  
  
