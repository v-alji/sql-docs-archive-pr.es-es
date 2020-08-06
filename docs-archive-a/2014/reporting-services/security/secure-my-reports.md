---
title: Proteger Mis informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- denying My Reports folder access
- private folders [Reporting Services]
- user workspace [Reporting Services]
- security [Reporting Services], My Reports folder
- My Reports folder [Reporting Services]
ms.assetid: 3b23a382-13b8-4196-9a93-7fe62d03a63c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b0a832133852e05c54a80b73fad8a91426840467
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744999"
---
# <a name="secure-my-reports"></a><span data-ttu-id="d600b-102">Proteger Mis informes</span><span class="sxs-lookup"><span data-stu-id="d600b-102">Secure My Reports</span></span>
  <span data-ttu-id="d600b-103">La característica Mis informes proporciona un área de trabajo administrada por el usuario para trabajar con informes.</span><span class="sxs-lookup"><span data-stu-id="d600b-103">The My Reports feature provides a user-managed workspace for working with reports.</span></span> <span data-ttu-id="d600b-104">A fin de cumplir su propósito, la carpeta Mis informes precisa permisos menos restrictivos que otras carpetas disponibles para uso general.</span><span class="sxs-lookup"><span data-stu-id="d600b-104">In order to serve its intended purpose, the My Reports folder requires less restrictive permissions than other folders that are available for general use.</span></span> <span data-ttu-id="d600b-105">Los usuarios que solo tienen permisos para ver y ejecutar informes en otras carpetas pueden necesitar un conjunto expandido de permisos para administrar sus carpetas Mis informes y el contenido que poseen.</span><span class="sxs-lookup"><span data-stu-id="d600b-105">Users who have permissions to only view and run reports in other folders might require an expanded set of permissions to manage their My Reports folders and content that they own.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="d600b-106">proporciona una asignación de roles especializada y una definición de roles para este fin.</span><span class="sxs-lookup"><span data-stu-id="d600b-106">provides a specialized role assignment and role definition for this purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d600b-107">Mis informes solo está disponible en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="d600b-107">My Reports is available only in Report Manager.</span></span> <span data-ttu-id="d600b-108">No se encuentra disponible en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d600b-108">It is not available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="role-assignment-for-my-reports"></a><span data-ttu-id="d600b-109">Asignación de roles para Mis informes</span><span class="sxs-lookup"><span data-stu-id="d600b-109">Role Assignment for My Reports</span></span>  
 <span data-ttu-id="d600b-110">La asignación de roles para Mis informes tiene elementos predefinidos y se crea automáticamente para cada usuario que active una carpeta Mis informes.</span><span class="sxs-lookup"><span data-stu-id="d600b-110">The role assignment for My Reports has preset elements and is automatically created for each user who activates a My Reports folder.</span></span> <span data-ttu-id="d600b-111">El hecho de que el servidor de informes asigne seguridad automáticamente resulta especialmente útil para las organizaciones que usen Mis informes ampliamente, ya que los administradores no tienen que habilitar el acceso para cada usuario de Mis informes.</span><span class="sxs-lookup"><span data-stu-id="d600b-111">Having the report server automatically assign security is especially useful for organizations that use My Reports widely because administrators do not have to enable access for each My Reports user.</span></span>  
  
 <span data-ttu-id="d600b-112">Una asignación de roles de **Mis informes** se compone de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="d600b-112">A **My Reports** role assignment consists of the following elements:</span></span>  
  
-   <span data-ttu-id="d600b-113">La carpeta Mis informes del usuario, que se encuentra en carpetas de usuarios \\ *\<username>* \Mis informes carpeta.</span><span class="sxs-lookup"><span data-stu-id="d600b-113">The user's My Reports folder, which is located in Users Folders\\*\<username>* \My Reports folder.</span></span>  
  
-   <span data-ttu-id="d600b-114">La cuenta de usuario, que se determina cuando se activa la carpeta Mis informes.</span><span class="sxs-lookup"><span data-stu-id="d600b-114">The user account, which is determined when the My Reports folder is activated.</span></span> <span data-ttu-id="d600b-115">La carpeta se activa cuando un usuario hace clic en una carpeta Mis informes en el Administrador de informes o cuando publica un informe a una carpeta Mis informes desde el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="d600b-115">A folder is activated when a user clicks a My Reports folder in Report Manager or when publishing a report to a My Reports folder from Report Designer.</span></span> <span data-ttu-id="d600b-116">Esta carpeta también se activa cuando un usuario solicita propiedades en el vínculo Mis informes.</span><span class="sxs-lookup"><span data-stu-id="d600b-116">This folder is also activated when a user requests properties on the My Reports link.</span></span>  
  
-   <span data-ttu-id="d600b-117">La definición de roles predefinida para Mis informes.</span><span class="sxs-lookup"><span data-stu-id="d600b-117">The predefined role definition for My Reports.</span></span>  
  
## <a name="role-definition-for-my-reports"></a><span data-ttu-id="d600b-118">Definición de roles para Mis informes</span><span class="sxs-lookup"><span data-stu-id="d600b-118">Role Definition for My Reports</span></span>  
 <span data-ttu-id="d600b-119">La definición del rol **Mis informes** incluye tareas que permiten administrar el contenido de una carpeta Mis informes.</span><span class="sxs-lookup"><span data-stu-id="d600b-119">The **My Reports** role definition includes tasks that support content management of a My Reports folder.</span></span> <span data-ttu-id="d600b-120">El rol **Mis informes** está destinado a ser un rol con un solo fin.</span><span class="sxs-lookup"><span data-stu-id="d600b-120">The **My Reports** role is intended to be a single-purpose role.</span></span> <span data-ttu-id="d600b-121">Aunque puede elegirla para cualquier directiva de seguridad de nivel de elemento, debería evitar hacerlo para reducir al mínimo la posibilidad de que la modifique para adaptarse a otros requisitos de carpetas.</span><span class="sxs-lookup"><span data-stu-id="d600b-121">Although you can choose it for any item-level security policy, you should avoid doing so to minimize the chance that you will modify it to accommodate other folder requirements.</span></span> <span data-ttu-id="d600b-122">Al reservar el rol **Mis informes** para la característica Mis informes, ayudará a lograr que todos los usuarios la puedan utilizar de igual manera.</span><span class="sxs-lookup"><span data-stu-id="d600b-122">Reserving the **My Reports** role for the My Reports feature can help you maintain a consistent experience for users.</span></span>  
  
 <span data-ttu-id="d600b-123">De manera predeterminada, solo los administradores del servidor de informes pueden modificar el rol **Mis informes** .</span><span class="sxs-lookup"><span data-stu-id="d600b-123">By default, only report server administrators modify the **My Reports** role.</span></span> <span data-ttu-id="d600b-124">Puede personalizar el rol **Mis informes** cambiando las tareas que contiene.</span><span class="sxs-lookup"><span data-stu-id="d600b-124">You can customize the **My Reports** role by changing the tasks it contains.</span></span> <span data-ttu-id="d600b-125">También puede sustituir un rol diferente.</span><span class="sxs-lookup"><span data-stu-id="d600b-125">You can also substitute a different role.</span></span>  
  
## <a name="denying-access-to-my-reports"></a><span data-ttu-id="d600b-126">Denegar acceso a Mis informes</span><span class="sxs-lookup"><span data-stu-id="d600b-126">Denying Access to My Reports</span></span>  
 <span data-ttu-id="d600b-127">Puede impedir que los usuarios tengan acceso a Mis informes:</span><span class="sxs-lookup"><span data-stu-id="d600b-127">You can prevent users from accessing My Reports by:</span></span>  
  
-   <span data-ttu-id="d600b-128">Mediante la deshabilitación de Mis informes en la página Configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="d600b-128">Disabling My Reports on the Site Settings page.</span></span> <span data-ttu-id="d600b-129">Para más información, vea [Habilitar y deshabilitar Mis informes](../report-server/enable-and-disable-my-reports.md).</span><span class="sxs-lookup"><span data-stu-id="d600b-129">For more information, see [Enable and Disable My Reports](../report-server/enable-and-disable-my-reports.md).</span></span>  
  
-   <span data-ttu-id="d600b-130">Mediante la eliminación de todas las tareas del rol **Mis informes** .</span><span class="sxs-lookup"><span data-stu-id="d600b-130">Removing all tasks from the **My Reports** role.</span></span>  
  
 <span data-ttu-id="d600b-131">Cuando deshabilite Mis informes, el vínculo a una carpeta Mis informes se quita del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="d600b-131">When you disable My Reports, the link to a My Reports folder is removed from Report Manager.</span></span> <span data-ttu-id="d600b-132">La estructura de carpetas subyacente que se utiliza para Mis informes (es decir, la carpeta Carpetas de usuarios y sus subcarpetas) todavía está disponible y accesible si el usuario conoce la ruta de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="d600b-132">The underlying folder structure that supports My Reports (that is, the Users Folders folder and subfolders) is still available and can be accessed if a user knows the folder path.</span></span> <span data-ttu-id="d600b-133">La eliminación de tareas del rol **Mis informes** garantiza que se impida el acceso.</span><span class="sxs-lookup"><span data-stu-id="d600b-133">Removing tasks from **My Reports** role ensures that access is prevented.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d600b-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d600b-134">See Also</span></span>  
 <span data-ttu-id="d600b-135">[Proteger informes y recursos](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="d600b-135">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="d600b-136">[Proteger carpetas](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="d600b-136">[Secure Folders](secure-folders.md) </span></span>  
 [<span data-ttu-id="d600b-137">Concesión de permisos en un servidor de informes en modo nativo</span><span class="sxs-lookup"><span data-stu-id="d600b-137">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
