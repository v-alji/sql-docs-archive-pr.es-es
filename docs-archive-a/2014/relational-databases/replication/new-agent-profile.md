---
title: Nuevo perfil de agente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.newperfprofile.f1
helpviewer_keywords:
- New Agent Profile dialog box
ms.assetid: ebf59330-a421-45a5-9020-0484a96852bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1d7848e44585fd35a5b5a33cf431e15de96c9375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748060"
---
# <a name="new-agent-profile"></a><span data-ttu-id="27731-102">Nuevo perfil de agente</span><span class="sxs-lookup"><span data-stu-id="27731-102">New Agent Profile</span></span>
  <span data-ttu-id="27731-103">Utilice el cuadro de diálogo **Nuevo perfil de agente** para crear un perfil nuevo.</span><span class="sxs-lookup"><span data-stu-id="27731-103">Use the **New Agent Profile** dialog box to create a new profile.</span></span> <span data-ttu-id="27731-104">Los perfiles nuevos siempre se basan en perfiles existentes, pero pueden modificarse para satisfacer los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="27731-104">New profiles are always based on existing profiles, but they can be modified to meet application requirements.</span></span> <span data-ttu-id="27731-105">Después de crear el perfil, éste puede aplicarse a trabajos de agente existentes y futuros en el cuadro de diálogo **Perfiles de agente** .</span><span class="sxs-lookup"><span data-stu-id="27731-105">After a profile has been created, it can be applied to existing and future agent jobs in the **Agent Profiles** dialog box.</span></span> <span data-ttu-id="27731-106">Los valores de los parámetros de agente pueden modificarse en el cuadro de diálogo Propiedades de \<**AgentProfileName>\*\*.</span><span class="sxs-lookup"><span data-stu-id="27731-106">Agent parameter values can be edited in the \<**AgentProfileName> Properties\*\* dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="27731-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="27731-107">Options</span></span>  
 <span data-ttu-id="27731-108">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="27731-108">**Name**</span></span>  
 <span data-ttu-id="27731-109">Escriba un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="27731-109">Enter a name for the profile.</span></span>  
  
 <span data-ttu-id="27731-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="27731-110">**Description**</span></span>  
 <span data-ttu-id="27731-111">Escriba una descripción para el perfil.</span><span class="sxs-lookup"><span data-stu-id="27731-111">Enter a description for the profile.</span></span>  
  
 <span data-ttu-id="27731-112">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="27731-112">**Parameter**</span></span>  
 <span data-ttu-id="27731-113">Parámetros de agente incluidos en el perfil.</span><span class="sxs-lookup"><span data-stu-id="27731-113">The agent parameters included in the profile.</span></span> <span data-ttu-id="27731-114">El perfil en el que se basa el nuevo perfil no especifica necesariamente un valor para cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="27731-114">The profile on which the new profile is based does not necessarily specify a value for each parameter.</span></span> <span data-ttu-id="27731-115">Para ver todos los parámetros válidos para un agente determinado, desactive la casilla **Mostrar solo los parámetros utilizados en este perfil** .</span><span class="sxs-lookup"><span data-stu-id="27731-115">To see all parameters that are valid for a given agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="27731-116">Para obtener una descripción de cada parámetro, vea:</span><span class="sxs-lookup"><span data-stu-id="27731-116">For descriptions of each parameter, see:</span></span>  
  
-   [<span data-ttu-id="27731-117">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="27731-117">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
-   [<span data-ttu-id="27731-118">Agente de registro del LOG de replicación</span><span class="sxs-lookup"><span data-stu-id="27731-118">Replication Log Reader Agent</span></span>](agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="27731-119">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="27731-119">Replication Distribution Agent</span></span>](agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="27731-120">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="27731-120">Replication Merge Agent</span></span>](agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="27731-121">Agente de lectura de cola de replicación</span><span class="sxs-lookup"><span data-stu-id="27731-121">Replication Queue Reader Agent</span></span>](agents/replication-queue-reader-agent.md)  
  
 <span data-ttu-id="27731-122">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="27731-122">**Default Value**</span></span>  
 <span data-ttu-id="27731-123">Valor predeterminado para cada parámetro de agente.</span><span class="sxs-lookup"><span data-stu-id="27731-123">The default value for each agent parameter.</span></span>  
  
 <span data-ttu-id="27731-124">**Valor**</span><span class="sxs-lookup"><span data-stu-id="27731-124">**Value**</span></span>  
 <span data-ttu-id="27731-125">Valor especificado para el parámetro en el perfil en el que se basa el perfil nuevo.</span><span class="sxs-lookup"><span data-stu-id="27731-125">The value specified for the parameter in the profile on which the new profile is based.</span></span> <span data-ttu-id="27731-126">Modifique este campo para todos los parámetros que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="27731-126">Edit this field for any parameter values you want to change.</span></span>  
  
 <span data-ttu-id="27731-127">**Mostrar solo los parámetros utilizados en este perfil**</span><span class="sxs-lookup"><span data-stu-id="27731-127">**Show only parameters used in this profile**</span></span>  
 <span data-ttu-id="27731-128">Desactive esta opción si desea mostrar todos los parámetros válidos para un agente determinado.</span><span class="sxs-lookup"><span data-stu-id="27731-128">Clear to show all valid parameters for a given agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27731-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27731-129">See Also</span></span>  
 <span data-ttu-id="27731-130">[Trabajar con perfiles del Agente de replicación](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="27731-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="27731-131">[Replication Agents Overview](agents/replication-agents-overview.md)  (Información general sobre los agentes de replicación)</span><span class="sxs-lookup"><span data-stu-id="27731-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="27731-132">Perfiles del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="27731-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
