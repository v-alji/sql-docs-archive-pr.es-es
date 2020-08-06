---
title: Grupos de cargas de trabajo del regulador de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group
- workload groups [SQL Server]
- workload groups [SQL Server], overview
ms.assetid: a84c3c3f-55b6-4a30-9c42-13f082d9281e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c6fa8f6fe960571f10d6a8505329fbe8f400e6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745687"
---
# <a name="resource-governor-workload-group"></a><span data-ttu-id="579b6-102">Grupos de cargas de trabajo del regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="579b6-102">Resource Governor Workload Group</span></span>
  <span data-ttu-id="579b6-103">En el regulador de recursos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , un grupo de cargas de trabajo actúa como un contenedor de las solicitudes de sesión que tienen criterios de clasificación similares.</span><span class="sxs-lookup"><span data-stu-id="579b6-103">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resource Governor, a workload group serves as a container for session requests that have similar classification criteria.</span></span> <span data-ttu-id="579b6-104">Una carga de trabajo permite la supervisión agregada de las sesiones y define directivas para estas.</span><span class="sxs-lookup"><span data-stu-id="579b6-104">A workload allows for aggregate monitoring of the sessions, and defines policies for the sessions.</span></span> <span data-ttu-id="579b6-105">Cada grupo de cargas de trabajo está en un grupo de recursos de servidor, que representa un subconjunto de los recursos físicos de una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="579b6-105">Each workload group is in a resource pool, which represents a subset of the physical resources of an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="579b6-106">Cuando se inicia una sesión, el clasificador del regulador de recursos asigna la sesión a un grupo de cargas de trabajo concreto, y la sesión se debe ejecutar utilizando las directivas asignadas al grupo de cargas de trabajo y los recursos definidos para el grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="579b6-106">When a session is started, the Resource Governor classifier assigns the session to a specific workload group, and the session must run using the policies assigned to the workload group and the resources defined for the resource pool.</span></span>  
  
## <a name="workload-group-concepts"></a><span data-ttu-id="579b6-107">Conceptos del grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="579b6-107">Workload Group Concepts</span></span>  
 <span data-ttu-id="579b6-108">Un grupo de cargas de trabajo sirve como contenedor para las solicitudes de sesión que sean similares de acuerdo con los criterios de clasificación que se aplican a cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="579b6-108">A workload group serves as a container for session requests that are similar according to the classification criteria that are applied to each request.</span></span> <span data-ttu-id="579b6-109">Un grupo de cargas de trabajo permite la supervisión agregada del consumo de recursos y la aplicación de una directiva uniforme a todas las solicitudes en el grupo.</span><span class="sxs-lookup"><span data-stu-id="579b6-109">A workload group allows the aggregate monitoring of resource consumption and the application of a uniform policy to all the requests in the group.</span></span> <span data-ttu-id="579b6-110">Un grupo define las directivas para sus miembros.</span><span class="sxs-lookup"><span data-stu-id="579b6-110">A group defines the policies for its members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="579b6-111">Los grupos de cargas de trabajo definidos por el usuario se pueden mover de un grupo de recursos de servidor a otro.</span><span class="sxs-lookup"><span data-stu-id="579b6-111">User-defined workload groups can be moved from one resource pool to another.</span></span>  
  
 <span data-ttu-id="579b6-112">El regulador de recursos predefine dos grupos de cargas de trabajo: el grupo interno y el grupo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="579b6-112">Resource Governor predefines two workload groups: the internal group and the default group.</span></span> <span data-ttu-id="579b6-113">Un usuario no puede cambiar nada que esté clasificado como grupo interno, pero puede supervisarlo.</span><span class="sxs-lookup"><span data-stu-id="579b6-113">A user cannot change anything classified as an internal group, but can monitor it.</span></span> <span data-ttu-id="579b6-114">Las solicitudes se clasifican en el grupo predeterminado cuando se dan las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="579b6-114">Requests are classified into the default group when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="579b6-115">No hay ningún criterio para clasificar una solicitud.</span><span class="sxs-lookup"><span data-stu-id="579b6-115">There are no criteria to classify a request.</span></span>  
  
-   <span data-ttu-id="579b6-116">Hay un intento de clasificar la solicitud en un grupo inexistente.</span><span class="sxs-lookup"><span data-stu-id="579b6-116">There is an attempt to classify the request into a non-existent group.</span></span>  
  
-   <span data-ttu-id="579b6-117">Hay un error de clasificación general.</span><span class="sxs-lookup"><span data-stu-id="579b6-117">There is a general classification failure.</span></span>  
  
 <span data-ttu-id="579b6-118">El regulador de recursos también proporciona instrucciones DLL para crear, cambiar y quitar grupos de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="579b6-118">Resource Governor also provides DDL statements for creating, changing, and dropping workload groups.</span></span>  
  
## <a name="workload-group-tasks"></a><span data-ttu-id="579b6-119">Tareas de grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="579b6-119">Workload Group Tasks</span></span>  
  
|<span data-ttu-id="579b6-120">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="579b6-120">Task Description</span></span>|<span data-ttu-id="579b6-121">Tema</span><span class="sxs-lookup"><span data-stu-id="579b6-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="579b6-122">Describe cómo crear un grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="579b6-122">Describes how to create a workload group.</span></span>|[<span data-ttu-id="579b6-123">Crear un grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="579b6-123">Create a Workload Group</span></span>](create-a-workload-group.md)|  
|<span data-ttu-id="579b6-124">Describe cómo cambiar la configuración del grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="579b6-124">Describes how to change workload group settings.</span></span>|[<span data-ttu-id="579b6-125">Cambiar la configuración del grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="579b6-125">Change Workload Group Settings</span></span>](change-workload-group-settings.md)|  
|<span data-ttu-id="579b6-126">Describe cómo eliminar un grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="579b6-126">Describes how to delete a workload group.</span></span>|[<span data-ttu-id="579b6-127">Eliminar un grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="579b6-127">Delete a Workload Group</span></span>](delete-a-workload-group.md)|  
  
## <a name="see-also"></a><span data-ttu-id="579b6-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="579b6-128">See Also</span></span>  
 <span data-ttu-id="579b6-129">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="579b6-129">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="579b6-130">[Habilitar el regulador de recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="579b6-130">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="579b6-131">[Grupo de recursos de servidor del regulador de recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="579b6-131">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="579b6-132">[Función clasificadora del regulador de recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="579b6-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="579b6-133">[Configurar el regulador de recursos utilizando una plantilla](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="579b6-133">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="579b6-134">Ver las propiedades del regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="579b6-134">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
