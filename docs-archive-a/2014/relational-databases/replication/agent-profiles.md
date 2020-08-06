---
title: Perfiles de agente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofiles.f1
helpviewer_keywords:
- Agent Profiles dialog box
ms.assetid: 0422e99c-e688-419b-bb4c-c7bebeef1d8d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7584670088da1ac7a9c81f1f8f0cbdce8b040c7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670955"
---
# <a name="agent-profiles"></a><span data-ttu-id="7b74b-102">Perfiles de agente</span><span class="sxs-lookup"><span data-stu-id="7b74b-102">Agent Profiles</span></span>
  <span data-ttu-id="7b74b-103">Utilice el cuadro de diálogo **Perfiles de agente** para administrar los perfiles de agente.</span><span class="sxs-lookup"><span data-stu-id="7b74b-103">Use the **Agent Profiles** dialog box to manage agent profiles.</span></span> <span data-ttu-id="7b74b-104">Los perfiles de agente proporcionan una manera cómoda de administrar los parámetros en tiempo de ejecución para cada agente.</span><span class="sxs-lookup"><span data-stu-id="7b74b-104">Agent profiles provide a convenient way to manage the runtime parameters for each agent.</span></span> <span data-ttu-id="7b74b-105">Cada agente tiene un perfil predeterminado y algunos tienen perfiles adicionales predefinidos.</span><span class="sxs-lookup"><span data-stu-id="7b74b-105">Each agent has a default profile, and some agents have additional predefined profiles.</span></span> <span data-ttu-id="7b74b-106">Por ejemplo, el Agente de mezcla tiene un perfil de "vínculo lento" diseñado para conexiones de banda ancha lentas.</span><span class="sxs-lookup"><span data-stu-id="7b74b-106">For example, the Merge Agent has a "slow link" profile designed for low bandwidth connections.</span></span> <span data-ttu-id="7b74b-107">Los perfiles predefinidos son suficientes para la mayoría de las aplicaciones, pero también pueden crearse perfiles definidos por el usuario, que permiten personalizar el comportamiento del agente.</span><span class="sxs-lookup"><span data-stu-id="7b74b-107">Predefined profiles are sufficient for most applications, but you can also create user-defined profiles, allowing you to customize agent behavior.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7b74b-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="7b74b-108">Options</span></span>  
 <span data-ttu-id="7b74b-109">**Seleccionar una página**</span><span class="sxs-lookup"><span data-stu-id="7b74b-109">**Select a page**</span></span>  
 <span data-ttu-id="7b74b-110">Seleccione un agente en el panel izquierdo y los perfiles del agente se mostrarán en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="7b74b-110">Select an agent in the left pane, and the profiles for the agent are displayed in the right pane.</span></span>  
  
 <span data-ttu-id="7b74b-111">**Predeterminado para nuevos**</span><span class="sxs-lookup"><span data-stu-id="7b74b-111">**Default for New**</span></span>  
 <span data-ttu-id="7b74b-112">Seleccione el perfil que se utilizará al crear los trabajos de un determinado tipo de agente.</span><span class="sxs-lookup"><span data-stu-id="7b74b-112">Select the profile that will be used when jobs are created for an agent of a given type.</span></span> <span data-ttu-id="7b74b-113">Por ejemplo, si crea varias suscripciones para una publicación de combinación, el trabajo del Agente de mezcla de cada suscripción utilizará el perfil seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7b74b-113">For example, if you create a number of subscriptions to a merge publication, the Merge Agent job for each subscription will use the profile selected.</span></span> <span data-ttu-id="7b74b-114">Si desea cambiar el perfil de los trabajos existentes, seleccione un perfil y, a continuación, haga clic en **Cambiar agentes existentes**.</span><span class="sxs-lookup"><span data-stu-id="7b74b-114">If you want to change the profile for existing jobs, select a profile, and then click **Change Existing Agents**.</span></span>  
  
 <span data-ttu-id="7b74b-115">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7b74b-115">**Name**</span></span>  
 <span data-ttu-id="7b74b-116">Nombre del perfil.</span><span class="sxs-lookup"><span data-stu-id="7b74b-116">The name of the profile.</span></span>  
  
 <span data-ttu-id="7b74b-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7b74b-117">**Type**</span></span>  
 <span data-ttu-id="7b74b-118">Indica el tipo de perfil: **Usuario** (definido por el usuario) o **Sistema** (predefinido).</span><span class="sxs-lookup"><span data-stu-id="7b74b-118">The type of profile: **User** (user-defined) or **System** (predefined).</span></span>  
  
 <span data-ttu-id="7b74b-119">**Propiedades (...)**</span><span class="sxs-lookup"><span data-stu-id="7b74b-119">**Properties (...)**</span></span>  
 <span data-ttu-id="7b74b-120">Haga clic para ver los valores utilizados por cada parámetro en el perfil del agente.</span><span class="sxs-lookup"><span data-stu-id="7b74b-120">Click to view the values used for each parameter in the agent profile.</span></span>  
  
 <span data-ttu-id="7b74b-121">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="7b74b-121">**New**</span></span>  
 <span data-ttu-id="7b74b-122">Haga clic para crear un perfil nuevo.</span><span class="sxs-lookup"><span data-stu-id="7b74b-122">Click to create a new profile.</span></span>  
  
 <span data-ttu-id="7b74b-123">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="7b74b-123">**Delete**</span></span>  
 <span data-ttu-id="7b74b-124">Seleccione un perfil definido por el usuario y, a continuación, haga clic en **Eliminar** para eliminar ese perfil.</span><span class="sxs-lookup"><span data-stu-id="7b74b-124">Select a user-defined profile, and then click **Delete** to delete that profile.</span></span> <span data-ttu-id="7b74b-125">Los perfiles predefinidos no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="7b74b-125">Predefined profiles cannot be deleted.</span></span>  
  
 <span data-ttu-id="7b74b-126">**Cambiar agentes existentes**</span><span class="sxs-lookup"><span data-stu-id="7b74b-126">**Change Existing Agents**</span></span>  
 <span data-ttu-id="7b74b-127">Seleccione un perfil y, a continuación, haga clic en **Cambiar agentes existentes** para especificar que todos los trabajos existentes de un determinado tipo de agente deben utilizar el perfil seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7b74b-127">Select a profile, and then click **Change Existing Agents** to specify that all existing jobs for an agent of a given type should use the selected profile.</span></span> <span data-ttu-id="7b74b-128">Por ejemplo, si ha creado varias suscripciones para una publicación de combinación y desea cambiar el perfil para especificar que el trabajo del Agente de mezcla de cada una de esas suscripciones debe utilizar el **Perfil de agente de conexión lenta**, seleccione ese perfil y, a continuación, haga clic en **Cambiar agentes existentes**.</span><span class="sxs-lookup"><span data-stu-id="7b74b-128">For example, if you have created a number of subscriptions to a merge publication, and you want to change the profile to specify that the Merge Agent job for each of these subscriptions should use the **Slow link agent profile**, select that profile, and then click **Change Existing Agents**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b74b-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b74b-129">See Also</span></span>  
 <span data-ttu-id="7b74b-130">[Trabajar con perfiles del Agente de replicación](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="7b74b-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="7b74b-131">[Replication Agents Overview](agents/replication-agents-overview.md)  (Información general sobre los agentes de replicación)</span><span class="sxs-lookup"><span data-stu-id="7b74b-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="7b74b-132">Perfiles del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="7b74b-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
