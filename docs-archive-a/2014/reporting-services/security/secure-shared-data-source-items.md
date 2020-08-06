---
title: Proteger elementos de orígenes de datos compartidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
- security [Reporting Services], data sources
ms.assetid: 7299e498-0a1a-4821-a22a-5199bb773ce0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4177834a90e2852f4079e3b2bf5a1dd85b9cd51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673467"
---
# <a name="secure-shared-data-source-items"></a><span data-ttu-id="a6fdf-102">Proteger elementos de orígenes de datos compartidos</span><span class="sxs-lookup"><span data-stu-id="a6fdf-102">Secure Shared Data Source Items</span></span>
  <span data-ttu-id="a6fdf-103">Puede establecer la seguridad en un origen de datos compartido para habilitar o deshabilitar el acceso a él.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-103">You can set security on a shared data source item to enable or disable access to it.</span></span>  
  
 <span data-ttu-id="a6fdf-104">Un usuario con acceso mínimo a un origen de datos compartido (por ejemplo, el acceso concedido con el rol **Explorador** ) puede ver la lista de informes que usan el elemento, siempre que el usuario también esté autorizado a ver los informes.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-104">A user who has minimal access to a shared data source (for example, the access granted through the **Browser** role) can view the list of reports that use the item, provided the user is also authorized to view the reports themselves.</span></span>  
  
 <span data-ttu-id="a6fdf-105">Un usuario con acceso adicional (como el concedido con el rol **Administrador de contenido** ) puede ver y establecer propiedades para el origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-105">A user who has additional access (such as that granted through the **Content Manager** role) can view and set properties for the shared data source.</span></span>  
  
 <span data-ttu-id="a6fdf-106">Para establecer la seguridad, cree una asignación de roles que especifique la cuenta de usuario o de grupo que tiene acceso al origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-106">To set security, you create a role assignment that specifies which user or group account has access to the shared data source.</span></span> <span data-ttu-id="a6fdf-107">Los usuarios con acceso a un origen de datos compartido pueden cambiar su nombre, descripción, cadena de conexión o información de credenciales.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-107">Users who have access to a shared data source item can change its name, description, connection string, or credential information.</span></span>  
  
## <a name="tasks-and-access-to-items"></a><span data-ttu-id="a6fdf-108">Tareas y acceso a elementos</span><span class="sxs-lookup"><span data-stu-id="a6fdf-108">Tasks and Access to Items</span></span>  
 <span data-ttu-id="a6fdf-109">Cuando cree asignaciones de roles, utilice un rol que tenga estas tareas para asignar los permisos apropiados a usuarios y grupos.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-109">When creating role assignments, use a role that has these tasks to assign appropriate permissions to users and groups.</span></span>  
  
|<span data-ttu-id="a6fdf-110">Seleccione esta tarea</span><span class="sxs-lookup"><span data-stu-id="a6fdf-110">Select this task</span></span>|<span data-ttu-id="a6fdf-111">Para conceder a los usuarios permiso para</span><span class="sxs-lookup"><span data-stu-id="a6fdf-111">To give users permission to</span></span>|  
|----------------------|---------------------------------|  
|<span data-ttu-id="a6fdf-112">Ver orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="a6fdf-112">View data sources</span></span>|<span data-ttu-id="a6fdf-113">Ver el origen de datos compartido en la jerarquía de carpetas.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-113">View the shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="a6fdf-114">Sin esta tarea, el elemento no está visible para los usuarios y no pueden saber que el origen de datos está disponible.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-114">Without this task, the item is not visible to users and they may not be aware that the data source is available.</span></span>|  
|<span data-ttu-id="a6fdf-115">Administración de orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="a6fdf-115">Manage data sources</span></span>|<span data-ttu-id="a6fdf-116">Ver propiedades que especifican el nombre, la descripción y la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-116">View properties that specify the name, description, and connection information.</span></span> <span data-ttu-id="a6fdf-117">Esta tarea también se utiliza para mostrar un origen de datos compartido en la jerarquía de carpetas.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-117">This task is also used to display a shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="a6fdf-118">Si elige esta tarea, puede omitir la tarea "Ver orígenes de datos".</span><span class="sxs-lookup"><span data-stu-id="a6fdf-118">If you choose this task, you can omit the "View data sources" task.</span></span>|  
|<span data-ttu-id="a6fdf-119">Establecer la seguridad de elementos individuales</span><span class="sxs-lookup"><span data-stu-id="a6fdf-119">Set security on items</span></span>|<span data-ttu-id="a6fdf-120">Crear y modificar asignaciones de roles que controlen el acceso al origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-120">Create and modify role assignments that control access to the shared data source.</span></span> <span data-ttu-id="a6fdf-121">Esta tarea debe utilizarse con las tareas "Ver orígenes de datos" o "Administrar orígenes de datos".</span><span class="sxs-lookup"><span data-stu-id="a6fdf-121">This task must be used with either "View data source" or "Manage data sources" tasks.</span></span> <span data-ttu-id="a6fdf-122">De lo contrario, no surte efecto porque el usuario no puede seleccionar el elemento.</span><span class="sxs-lookup"><span data-stu-id="a6fdf-122">If it is not, it has no effect because the user cannot select the item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6fdf-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6fdf-123">See Also</span></span>  
 <span data-ttu-id="a6fdf-124">[Administrar orígenes de datos de informe](../report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="a6fdf-124">[Manage Report Data Sources](../report-data/manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="a6fdf-125">[Proteger carpetas](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="a6fdf-125">[Secure Folders](secure-folders.md) </span></span>  
 <span data-ttu-id="a6fdf-126">[Proteger informes y recursos](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="a6fdf-126">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="a6fdf-127">[Conceder permisos en un servidor de informes en modo nativo](granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="a6fdf-127">[Granting Permissions on a Native Mode Report Server](granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="a6fdf-128">Almacenamiento de las credenciales en un origen de datos de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a6fdf-128">Store Credentials in a Reporting Services Data Source</span></span>](../report-data/store-credentials-in-a-reporting-services-data-source.md)  
  
  
