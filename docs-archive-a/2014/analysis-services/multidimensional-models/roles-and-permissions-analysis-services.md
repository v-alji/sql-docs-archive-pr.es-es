---
title: Roles y permisos (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], about security
- security [Analysis Services - multidimensional data], about security
ms.assetid: bb885447-868b-4686-853c-8241f63d4370
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6595d931b2c2760e5fd3013ff6bec88f85106d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752441"
---
# <a name="roles-and-permissions-analysis-services"></a><span data-ttu-id="8f512-102">Roles y permisos (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="8f512-102">Roles and Permissions (Analysis Services)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="8f512-103">proporciona un modelo de autorización basada en roles que concede acceso a operaciones, objetos y datos.</span><span class="sxs-lookup"><span data-stu-id="8f512-103">provides a role-based authorization model that grants access to operations, objects, and data.</span></span> <span data-ttu-id="8f512-104">Todos los usuarios que acceden a una base de datos o a una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deben hacerlo en el contexto de un rol.</span><span class="sxs-lookup"><span data-stu-id="8f512-104">All users who access an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance or database must do so within the context of a role.</span></span>  
  
 <span data-ttu-id="8f512-105">Como administrador del sistema de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , se va a encargar de conceder la pertenencia al **rol de administrador del servidor** que proporciona acceso sin restricciones a las operaciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="8f512-105">As an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] system administrator, you are in charge of granting membership to the **server administrator role** that conveys unrestricted access to operations on the server.</span></span> <span data-ttu-id="8f512-106">Este rol tiene permisos fijos y no puede personalizarse.</span><span class="sxs-lookup"><span data-stu-id="8f512-106">This role has fixed permissions and cannot be customized.</span></span> <span data-ttu-id="8f512-107">De forma predeterminada, los miembros del grupo local de administradores son automáticamente administradores del sistema de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="8f512-107">By default, members of the local Administrators group are automatically Analysis Services system administrators.</span></span>  
  
 <span data-ttu-id="8f512-108">Los usuarios que no sean administradores y que realicen consultas o procesen datos se les concede acceso con los **roles de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="8f512-108">Non-administrative users who query or process data are granted access through **database roles**.</span></span> <span data-ttu-id="8f512-109">Los administradores del sistema y de base de datos deben crear roles que describan los diferentes niveles de acceso en una determinada base de datos y, a continuación, asignar la pertenencia a cada usuario que requiera acceso.</span><span class="sxs-lookup"><span data-stu-id="8f512-109">Both system administrators and database administrators can create the roles that describe different levels of access within a given database, and then assign membership to every user who requires access.</span></span> <span data-ttu-id="8f512-110">Cada rol cuenta con un conjunto personalizado de permisos para obtener acceso a objetos y operaciones en una base de datos en particular.</span><span class="sxs-lookup"><span data-stu-id="8f512-110">Each role has a customized set of permissions for accessing objects and operations within a particular database.</span></span> <span data-ttu-id="8f512-111">Puede asignar permisos en los siguientes niveles: base de datos, objetos interiores, como cubos y dimensiones (pero no perspectivas), y filas.</span><span class="sxs-lookup"><span data-stu-id="8f512-111">You can assign permissions at these levels: database, interior objects such as cubes and dimensions (but not perspectives), and rows.</span></span>  
  
 <span data-ttu-id="8f512-112">Una práctica habitual es crear roles y asignar miembros en operaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="8f512-112">It is common practice to create roles and assign membership as separate operations.</span></span> <span data-ttu-id="8f512-113">A menudo, el diseñador del modelo agrega roles durante la fase de diseño.</span><span class="sxs-lookup"><span data-stu-id="8f512-113">Often, the model designer adds roles during the design phase.</span></span> <span data-ttu-id="8f512-114">De este modo, todas las definiciones de roles se reflejan en los archivos de proyecto que definen el modelo.</span><span class="sxs-lookup"><span data-stu-id="8f512-114">This way, all role definitions are reflected in the project files that define the model.</span></span> <span data-ttu-id="8f512-115">La asignación de pertenencia a los roles normalmente se lleva a cabo después, cuando la base de datos pasa a producción, y suelen hacerlo los administradores de bases de datos, que crean scripts que se pueden desarrollar, probar y ejecutar en una operación independiente.</span><span class="sxs-lookup"><span data-stu-id="8f512-115">Role membership is typically rolled out later as the database moves into production, usually by database administrators who create scripts that can be developed, tested, and run as an independent operation.</span></span>  
  
 <span data-ttu-id="8f512-116">Toda la autorización se basa en una identidad de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="8f512-116">All authorization is predicated on a valid Windows user identity.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="8f512-117">usa la autenticación de Windows solamente para autenticar identidades de usuario.</span><span class="sxs-lookup"><span data-stu-id="8f512-117">uses Windows authentication exclusively to authenticate user identities.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="8f512-118">no proporciona ningún método de autenticación de propiedad. Consulte [metodologías de autenticación admitidas por Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="8f512-118">provides no proprietary authentication method.See [Authentication methodologies supported by Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8f512-119">Los permisos se van sumando en cada usuario o grupo de Windows, en todos los roles de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8f512-119">Permissions are additive for each Windows user or group, across all roles in the database.</span></span> <span data-ttu-id="8f512-120">Si un rol impide que un permiso de usuario o grupo realice determinadas tareas o vea ciertos datos, pero hay otro rol que concede este mismo permiso a ese usuario o grupo, el usuario o grupo tendrá permiso para realizar la tarea o ver los datos.</span><span class="sxs-lookup"><span data-stu-id="8f512-120">If one role denies a user or group permission to perform certain tasks or view certain data, but another role grants this permission to that user or group, the user or group will have permission to perform the task or view the data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f512-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8f512-121">In this section</span></span>  
  
-   [<span data-ttu-id="8f512-122">Cómo autorizar el acceso a objetos y operaciones &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-122">Authorizing access to objects and operations &#40;Analysis Services&#41;</span></span>](authorizing-access-to-objects-and-operations-analysis-services.md)  
  
-   [<span data-ttu-id="8f512-123">Otorgar permisos de base de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-123">Grant database permissions &#40;Analysis Services&#41;</span></span>](grant-database-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="8f512-124">Otorgar permisos para cubos o modelos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-124">Grant cube or model permissions &#40;Analysis Services&#41;</span></span>](grant-cube-or-model-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="8f512-125">Otorgar permisos de procesamiento &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-125">Grant process permissions &#40;Analysis Services&#41;</span></span>](grant-process-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="8f512-126">Otorgar permisos Leer definición en metadatos de objetos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-126">Grant read definition permissions on object metadata &#40;Analysis Services&#41;</span></span>](grant-read-definition-permissions-on-object-metadata-analysis-services.md)  
  
-   [<span data-ttu-id="8f512-127">Otorgar permisos para un objeto de origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-127">Grant permissions on a data source object &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-data-source-object-analysis-services.md)  
  
-   [<span data-ttu-id="8f512-128">Otorgar permisos para estructuras y modelos de minería de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-128">Grant permissions on data mining structures and models &#40;Analysis Services&#41;</span></span>](grant-permissions-on-data-mining-structures-and-models-analysis-services.md)  
  
-   [<span data-ttu-id="8f512-129">Otorgar permisos para una dimensión &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-129">Grant permissions on a dimension &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-dimension-analysis-services.md)  
  
-   [<span data-ttu-id="8f512-130">Conceder acceso personalizado a datos de dimensión &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-130">Grant custom access to dimension data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-dimension-data-analysis-services.md)  
  
-   [<span data-ttu-id="8f512-131">Otorgar acceso personalizado a los datos de las celdas &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-131">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="8f512-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f512-132">See Also</span></span>  
 [<span data-ttu-id="8f512-133">Crear y administrar roles &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="8f512-133">Create and Manage Roles &#40;SSAS Tabular&#41;</span></span>](../tabular-models/roles-ssas-tabular.md)  
  
  
