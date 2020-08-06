---
title: Trabajar con perfiles del Agente de replicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], agents and profiles
- replication agent profiles [SQL Server]
- agents [SQL Server replication], profiles
- profiles [SQL Server], replication agents
ms.assetid: 9c290a88-4e9f-4a7e-aab5-4442137a9918
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fc20451edfb1096fca7e468effb14df78b51f758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663409"
---
# <a name="work-with-replication-agent-profiles"></a><span data-ttu-id="70d2e-102">Trabajar con perfiles del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="70d2e-102">Work with Replication Agent Profiles</span></span>
  <span data-ttu-id="70d2e-103">En este tema, se describe cómo trabajar con perfiles de agente de replicación en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="70d2e-103">This topic describes how to work with Replication Agent Profiles in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span> <span data-ttu-id="70d2e-104">El comportamiento de cada agente de replicación está controlado por un conjunto de parámetros que se pueden establecer a través de perfiles de agente.</span><span class="sxs-lookup"><span data-stu-id="70d2e-104">The behavior of each replication agent is controlled by a set of parameters that can be set through agent profiles.</span></span> <span data-ttu-id="70d2e-105">Cada agente tiene un perfil predeterminado y algunos tienen perfiles adicionales predefinidos; solo hay un perfil activo para un agente en cada momento.</span><span class="sxs-lookup"><span data-stu-id="70d2e-105">Each agent has a default profile, and some have additional predefined profiles; at a given time, only one profile is active for an agent.</span></span>  
  
 <span data-ttu-id="70d2e-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="70d2e-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="70d2e-107">**Para trabajar con perfiles de agente de replicación con:**</span><span class="sxs-lookup"><span data-stu-id="70d2e-107">**To work with Replication Agent Profiles, using:**</span></span>  
  
     [<span data-ttu-id="70d2e-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70d2e-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   <span data-ttu-id="70d2e-109">Obtener acceso al cuadro de diálogo Perfiles de agente</span><span class="sxs-lookup"><span data-stu-id="70d2e-109">Access the Agent Profiles dialog box</span></span>  
  
    -   <span data-ttu-id="70d2e-110">Especificar un perfil para un agente</span><span class="sxs-lookup"><span data-stu-id="70d2e-110">Specify a profile for an agent</span></span>  
  
    -   <span data-ttu-id="70d2e-111">Crear un perfil</span><span class="sxs-lookup"><span data-stu-id="70d2e-111">Create a profile</span></span>  
  
    -   <span data-ttu-id="70d2e-112">Modificar un perfil</span><span class="sxs-lookup"><span data-stu-id="70d2e-112">Modify a profile</span></span>  
  
    -   <span data-ttu-id="70d2e-113">Eliminar un perfil</span><span class="sxs-lookup"><span data-stu-id="70d2e-113">Delete a profile</span></span>  
  
     [<span data-ttu-id="70d2e-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="70d2e-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   <span data-ttu-id="70d2e-115">Crear un perfil</span><span class="sxs-lookup"><span data-stu-id="70d2e-115">Create a profile</span></span>  
  
    -   <span data-ttu-id="70d2e-116">Modificar un perfil</span><span class="sxs-lookup"><span data-stu-id="70d2e-116">Modify a profile</span></span>  
  
    -   <span data-ttu-id="70d2e-117">Eliminar un perfil</span><span class="sxs-lookup"><span data-stu-id="70d2e-117">Delete a profile</span></span>  
  
    -   <span data-ttu-id="70d2e-118">Usar perfiles de agente durante la sincronización</span><span class="sxs-lookup"><span data-stu-id="70d2e-118">Use agent profiles during synchronization</span></span>  
  
    -   <span data-ttu-id="70d2e-119">Ejemplo de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="70d2e-119">Transact-SQL example</span></span>  
  
     [<span data-ttu-id="70d2e-120">Replication Management Objects</span><span class="sxs-lookup"><span data-stu-id="70d2e-120">Replication Management Objects</span></span>](#RMOProcedure)  
  
    -   <span data-ttu-id="70d2e-121">Crear un perfil</span><span class="sxs-lookup"><span data-stu-id="70d2e-121">Create a profile</span></span>  
  
    -   <span data-ttu-id="70d2e-122">Modificar un perfil</span><span class="sxs-lookup"><span data-stu-id="70d2e-122">Modify a profile</span></span>  
  
    -   <span data-ttu-id="70d2e-123">Eliminar un perfil</span><span class="sxs-lookup"><span data-stu-id="70d2e-123">Delete a profile</span></span>  
  
-   <span data-ttu-id="70d2e-124">**Seguimiento:**  [después de cambiar los parámetros de agente](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="70d2e-124">**Follow Up:**  [After Changing Agent Parameters](#FollowUp)</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="70d2e-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70d2e-125">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-access-the-agent-profiles-dialog-box-from-sql-server-management-studio"></a><a name="Access_SSMS"></a> <span data-ttu-id="70d2e-126">Para obtener acceso al cuadro de diálogo Perfiles de agente en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70d2e-126">To access the Agent Profiles dialog box from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="70d2e-127">En la página **General** del cuadro de diálogo **Propiedades del distribuidor: \<Distributor>** , haga clic en **Valores predeterminados de perfil**.</span><span class="sxs-lookup"><span data-stu-id="70d2e-127">On the **General** page of the **Distributor Properties - \<Distributor>** dialog box, click **Profile Defaults**.</span></span>  
  
#### <a name="to-access-the-agent-profiles-dialog-box-from-replication-monitor"></a><span data-ttu-id="70d2e-128">Para obtener acceso al cuadro de diálogo Perfiles de agente en el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="70d2e-128">To access the Agent Profiles dialog box from Replication Monitor</span></span>  
  
-   <span data-ttu-id="70d2e-129">Para abrir el cuadro de diálogo para todos los agentes, haga clic con el botón secundario en un publicador y, a continuación, en **Perfiles de agente**.</span><span class="sxs-lookup"><span data-stu-id="70d2e-129">To open the dialog box for all agents, right-click a Publisher, and then click **Agent Profiles**.</span></span>  
  
-   <span data-ttu-id="70d2e-130">Para abrir el cuadro de diálogo para un solo agente:</span><span class="sxs-lookup"><span data-stu-id="70d2e-130">To open the dialog box for a single agent:</span></span>  
  
    1.  <span data-ttu-id="70d2e-131">Expanda un grupo de publicador en el panel izquierdo del Monitor de replicación, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="70d2e-131">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="70d2e-132">Para los perfiles del Agente de distribución y el Agente de mezcla, haga clic con el botón secundario en una suscripción de la pestaña **Todas las suscripciones** y, a continuación, en **Perfil del agente**.</span><span class="sxs-lookup"><span data-stu-id="70d2e-132">For Distribution Agent and Merge Agent profiles, right-click a subscription on the **All Subscriptions** tab, and then click **Agent Profile**.</span></span> <span data-ttu-id="70d2e-133">Para otros agentes, haga clic con el botón secundario en la pestaña **Agentes** y, a continuación, haga click en **Perfil del agente**.</span><span class="sxs-lookup"><span data-stu-id="70d2e-133">For other agents, right-click the agent on the **Agents** tab, and then click **Agent Profile**.</span></span>  
  
###  <a name="to-specify-a-profile-for-an-agent"></a><a name="Specify_SSMS"></a> <span data-ttu-id="70d2e-134">Para especificar un perfil para un agente</span><span class="sxs-lookup"><span data-stu-id="70d2e-134">To specify a profile for an agent</span></span>  
  
1.  <span data-ttu-id="70d2e-135">Si el cuadro de diálogo **Perfiles de agente** muestra perfiles para varios agentes, seleccione un agente.</span><span class="sxs-lookup"><span data-stu-id="70d2e-135">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="70d2e-136">Seleccione un perfil en la columna **Predeterminado para nuevos** de la cuadrícula **Perfiles de agente** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-136">Select a profile in the **Default for new** column of the **Agent profiles** grid.</span></span> <span data-ttu-id="70d2e-137">De forma predeterminada, el perfil solamente se aplica a los agentes para las publicaciones y suscripciones nuevas.</span><span class="sxs-lookup"><span data-stu-id="70d2e-137">By default, the profile is only applied to agents for new publications and subscriptions.</span></span>  
  
3.  <span data-ttu-id="70d2e-138">Para especificar que utilicen el perfil todos los agentes del tipo seleccionado para las publicaciones o suscripciones existentes, haga clic en **Cambiar agentes existentes**.</span><span class="sxs-lookup"><span data-stu-id="70d2e-138">To specify that all agents of the selected type for existing publications or subscriptions should use this profile, click **Change existing agents**.</span></span>  
  
###  <a name="to-view-and-edit-the-parameters-associated-with-a-profile"></a><a name="Modify_SSMS"></a> <span data-ttu-id="70d2e-139">Para ver y modificar los parámetros asociados con un perfil</span><span class="sxs-lookup"><span data-stu-id="70d2e-139">To view and edit the parameters associated with a profile</span></span>  
  
1.  <span data-ttu-id="70d2e-140">Si el cuadro de diálogo **Perfiles de agente** muestra perfiles para varios agentes, seleccione un agente.</span><span class="sxs-lookup"><span data-stu-id="70d2e-140">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="70d2e-141">Haga clic en el botón Propiedades ( **...** ) que aparece junto a un perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-141">Click the properties button (**...**) next to a profile.</span></span>  
  
3.  <span data-ttu-id="70d2e-142">Vea los parámetros y los valores en el cuadro de diálogo **Propiedades del perfil \<ProfileName>** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-142">View the parameters and values in the **\<ProfileName> Profile Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="70d2e-143">Los parámetros de los perfiles definidos por el usuario se pueden modificar, a diferencia de los parámetros de los perfiles predefinidos del sistema, que no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="70d2e-143">Parameters in user-defined profiles can be edited; parameters in predefined system profiles cannot.</span></span>  
  
    -   <span data-ttu-id="70d2e-144">Para ver todos los parámetros de un agente, desactive la casilla **Mostrar solamente los parámetros utilizados en este perfil** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-144">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="70d2e-145">Para obtener información acerca de los parámetros de agentes, vea los vínculos que aparecen al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="70d2e-145">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
4.  <span data-ttu-id="70d2e-146">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="70d2e-146">Click **Close**.</span></span>  
  
###  <a name="to-create-a-user-defined-profile"></a><a name="Create_SSMS"></a> <span data-ttu-id="70d2e-147">Para crear un perfil definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="70d2e-147">To create a user-defined profile</span></span>  
  
1.  <span data-ttu-id="70d2e-148">Si el cuadro de diálogo **Perfiles de agente** muestra perfiles para varios agentes, seleccione un agente.</span><span class="sxs-lookup"><span data-stu-id="70d2e-148">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="70d2e-149">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="70d2e-149">Click **New**.</span></span>  
  
3.  <span data-ttu-id="70d2e-150">En el cuadro de diálogo de inicialización **Nuevo perfil de agente** , seleccione el perfil existente en el que desea basar el nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-150">In the **New Agent Profile** initialization dialog box, select an existing profile on which to base the new profile.</span></span>  
  
4.  <span data-ttu-id="70d2e-151">En el cuadro de diálogo **Nuevo perfil de agente** , escriba valores en los cuadros de texto **Nombre** y **Descripción** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-151">In the **New Agent Profile** dialog box, enter values in the **Name** and **Description** text boxes.</span></span>  
  
5.  <span data-ttu-id="70d2e-152">Modifique los parámetros para personalizar el perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-152">Modify parameters to tailor the profile.</span></span> <span data-ttu-id="70d2e-153">Para ver todos los parámetros de un agente, desactive la casilla **Mostrar solamente los parámetros utilizados en este perfil** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-153">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="70d2e-154">Para obtener información acerca de los parámetros de agentes, vea los vínculos que aparecen al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="70d2e-154">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
###  <a name="to-delete-a-user-defined-profile"></a><a name="Delete_SSMS"></a> <span data-ttu-id="70d2e-155">Para eliminar un perfil definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="70d2e-155">To delete a user-defined profile</span></span>  
  
1.  <span data-ttu-id="70d2e-156">Si el cuadro de diálogo **Perfiles de agente** muestra perfiles para varios agentes, seleccione un agente.</span><span class="sxs-lookup"><span data-stu-id="70d2e-156">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="70d2e-157">Si un perfil está asociado con uno o más agentes, cambie el perfil para esos agentes:</span><span class="sxs-lookup"><span data-stu-id="70d2e-157">If a profile is associated with one or more agents, change the profile for those agents:</span></span>  
  
    1.  <span data-ttu-id="70d2e-158">Seleccione un perfil distinto en la cuadrícula **Perfiles de agente** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-158">Select a different profile in the **Agent profiles** grid.</span></span>  
  
    2.  <span data-ttu-id="70d2e-159">Haga clic en **Cambiar agentes existentes**.</span><span class="sxs-lookup"><span data-stu-id="70d2e-159">Click **Change existing agents**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="70d2e-160">Al hacer esto, cambiará el perfil de todos los agentes del tipo seleccionado para las publicaciones y suscripciones existentes, y no solo de los que usen el perfil que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="70d2e-160">This will change the profile for all agents of the selected type for existing publications or subscriptions, not only the ones using the profile you want to delete.</span></span>  
  
3.  <span data-ttu-id="70d2e-161">Seleccione el perfil que desea eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="70d2e-161">Select the profile you want to delete, and then click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="70d2e-162">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="70d2e-162">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_tsql"></a> <span data-ttu-id="70d2e-163">Para crear un nuevo perfil de agente</span><span class="sxs-lookup"><span data-stu-id="70d2e-163">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="70d2e-164">En el distribuidor, ejecute [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70d2e-164">At the Distributor, execute [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span></span> <span data-ttu-id="70d2e-165">Especifique **@name** un valor de **1** para **@profile_type** y uno de los siguientes valores para **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="70d2e-165">Specify **@name**, a value of **1** for **@profile_type**, and one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="70d2e-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="70d2e-171">Si este perfil se va a convertir en el nuevo perfil predeterminado para su tipo de agente de replicación, especifique el valor **1** para **@default**.</span><span class="sxs-lookup"><span data-stu-id="70d2e-171">If this profile will become the new default profile for its type of replication agent, specify a value of **1** for **@default**.</span></span> <span data-ttu-id="70d2e-172">El identificador del nuevo perfil se devuelve mediante el parámetro de **@profile_id** salida.</span><span class="sxs-lookup"><span data-stu-id="70d2e-172">The identifier for the new profile is returned using the **@profile_id** output parameter.</span></span> <span data-ttu-id="70d2e-173">De esta forma crea un nuevo perfil con un conjunto de parámetros de perfil basados en el perfil predeterminado del tipo de agente indicado.</span><span class="sxs-lookup"><span data-stu-id="70d2e-173">This creates a new profile with a set of profile parameters based on the default profile for the given agent type.</span></span>  
  
2.  <span data-ttu-id="70d2e-174">Una vez creado el nuevo perfil, agregue, quite o modifique los parámetros predeterminados para personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="70d2e-174">After the new profile has been created, add, remove, or modify the default parameters to customize the profile.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_tsql"></a> <span data-ttu-id="70d2e-175">Para modificar un perfil de agente existente</span><span class="sxs-lookup"><span data-stu-id="70d2e-175">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="70d2e-176">En el distribuidor, ejecute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70d2e-176">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="70d2e-177">Especifique uno de los siguientes valores para **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="70d2e-177">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="70d2e-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="70d2e-183">De esta forma se devuelven todos los perfiles del tipo de agente especificado.</span><span class="sxs-lookup"><span data-stu-id="70d2e-183">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="70d2e-184">Anote el valor de **profile_id** en el conjunto de resultados correspondiente al perfil que va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="70d2e-184">Note the value of **profile_id** in the result set for the profile to change.</span></span>  
  
2.  <span data-ttu-id="70d2e-185">En el distribuidor, ejecute [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70d2e-185">At the Distributor, execute [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span></span> <span data-ttu-id="70d2e-186">Especifique el identificador de perfil del paso 1 para **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-186">Specify the profile identifier from step 1 for **@profile_id**.</span></span> <span data-ttu-id="70d2e-187">De esta forma se devuelven todos los parámetros del perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-187">This returns all parameters for the profile.</span></span> <span data-ttu-id="70d2e-188">Anote el nombre de cualquier parámetro que desee modificar o quitar del perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-188">Note the name of any parameters to modify or remove from the profile.</span></span>  
  
3.  <span data-ttu-id="70d2e-189">Para cambiar el valor de un parámetro en un perfil, ejecute [sp_change_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70d2e-189">To change the value of a parameter in a profile, execute [sp_change_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span></span> <span data-ttu-id="70d2e-190">Especifique el identificador de perfil del paso 1 para **@profile_id** , el nombre del parámetro que se va a cambiar para **@property** y un nuevo valor para el parámetro para **@value** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-190">Specify the profile identifier from step 1 for **@profile_id**, the name of the parameter to change for **@property**, and a new value for the parameter for **@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70d2e-191">No puede cambiar un perfil de agente existente para convertirlo en el perfil predeterminado de un agente.</span><span class="sxs-lookup"><span data-stu-id="70d2e-191">You cannot change an existing agent profile to become the default profile for an agent.</span></span> <span data-ttu-id="70d2e-192">Debe crear un nuevo perfil como perfil predeterminado, como se muestra en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="70d2e-192">You must instead create a new profile as the default profile, as shown in the previous procedure.</span></span>  
  
4.  <span data-ttu-id="70d2e-193">Para quitar un parámetro de un perfil, ejecute [sp_drop_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70d2e-193">To remove a parameter from a profile, execute [sp_drop_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span></span> <span data-ttu-id="70d2e-194">Especifique el identificador de perfil del paso 1 para **@profile_id** y el nombre del parámetro que se va a quitar para **@parameter_name** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-194">Specify the profile identifier from step 1 for **@profile_id** and the name of the parameter to remove for **@parameter_name**.</span></span>  
  
5.  <span data-ttu-id="70d2e-195">Para agregar un nuevo parámetro a un perfil, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70d2e-195">To add a new parameter to a profile, you must do the following:</span></span>  
  
    -   <span data-ttu-id="70d2e-196">Consulte la tabla [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) en el distribuidor para determinar qué parámetros de perfil se pueden establecer en cada tipo de agente.</span><span class="sxs-lookup"><span data-stu-id="70d2e-196">Query the [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) table at the Distributor to determine which profile parameters can be set for each agent type.</span></span>  
  
    -   <span data-ttu-id="70d2e-197">En el distribuidor, ejecute [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70d2e-197">At the Distributor, execute [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span></span> <span data-ttu-id="70d2e-198">Especifique el identificador de perfil del paso 1 para **@profile_id** , el nombre de un parámetro válido que se va a agregar para **@parameter_name** y el valor del parámetro para **@parameter_value** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-198">Specify the profile identifier from step 1 for **@profile_id**, the name of a valid parameter to add for **@parameter_name**, and the value of the parameter for **@parameter_value**.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_tsql"></a> <span data-ttu-id="70d2e-199">Para eliminar un perfil de agente</span><span class="sxs-lookup"><span data-stu-id="70d2e-199">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="70d2e-200">En el distribuidor, ejecute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70d2e-200">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="70d2e-201">Especifique uno de los siguientes valores para **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="70d2e-201">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="70d2e-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="70d2e-207">De esta forma se devuelven todos los perfiles del tipo de agente especificado.</span><span class="sxs-lookup"><span data-stu-id="70d2e-207">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="70d2e-208">Anote el valor de **profile_id** en el conjunto de resultados correspondiente al perfil que va a quitar.</span><span class="sxs-lookup"><span data-stu-id="70d2e-208">Note the value of **profile_id** in the result set for the profile to remove.</span></span>  
  
2.  <span data-ttu-id="70d2e-209">En el distribuidor, ejecute [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70d2e-209">At the Distributor, execute [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span></span> <span data-ttu-id="70d2e-210">Especifique el identificador de perfil del paso 1 para **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-210">Specify the profile identifier from step 1 for **@profile_id**.</span></span>  
  
###  <a name="to-use-agent-profiles-during-synchronization"></a><a name="Synch_tsql"></a> <span data-ttu-id="70d2e-211">Para usar perfiles de agente durante la sincronización</span><span class="sxs-lookup"><span data-stu-id="70d2e-211">To use agent profiles during synchronization</span></span>  
  
1.  <span data-ttu-id="70d2e-212">En el distribuidor, ejecute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70d2e-212">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="70d2e-213">Especifique uno de los siguientes valores para **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="70d2e-213">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="70d2e-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="70d2e-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="70d2e-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="70d2e-219">De esta forma se devuelven todos los perfiles del tipo de agente especificado.</span><span class="sxs-lookup"><span data-stu-id="70d2e-219">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="70d2e-220">Tenga en cuenta el valor de `profile_name` en el conjunto de resultados para el perfil que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="70d2e-220">Note the value of `profile_name` in the result set for the profile to use.</span></span>  
  
2.  <span data-ttu-id="70d2e-221">Si el agente se inicia desde un trabajo del agente, edite el paso de trabajo que inicia el agente para especificar el valor de `profile_name` obtenido en el paso 1 después del parámetro de línea de comandos **-ProfileName** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-221">If the agent is started from an agent job, edit the job step that starts the agent to specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span> <span data-ttu-id="70d2e-222">Para obtener más información, consulte [Ver y modificar parámetros del símbolo del sistema de los agentes de replicación &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="70d2e-222">For more information, see [View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span></span>  
  
3.  <span data-ttu-id="70d2e-223">Al iniciar el agente desde el símbolo del sistema, especifique el valor de `profile_name` obtenido en el paso 1 después del parámetro de línea de comandos **-ProfileName** .</span><span class="sxs-lookup"><span data-stu-id="70d2e-223">When starting the agent from the command prompt, specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="70d2e-224">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="70d2e-224">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="70d2e-225">Este ejemplo crea un perfil personalizado para el Agente de mezcla denominado **custom_merge**, cambia el valor del parámetro **-UploadReadChangesPerBatch** , agrega un nuevo parámetro **-ExchangeType** y devuelve información sobre el perfil que se crea.</span><span class="sxs-lookup"><span data-stu-id="70d2e-225">This example creates a custom profile for the Merge Agent named **custom_merge**, changes the value of the **-UploadReadChangesPerBatch** parameter, adds a new **-ExchangeType** parameter, and returns information on the profile that is created.</span></span>  
  
 [!code-sql[HowTo#sp_addagentprofileparam](../../../snippets/tsql/SQL15/replication/howto/tsql/createperfparammerge.sql#sp_addagentprofileparam)]  
  
##  <a name="using-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="70d2e-226">Usar RMO</span><span class="sxs-lookup"><span data-stu-id="70d2e-226">Using RMO</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_RMO"></a> <span data-ttu-id="70d2e-227">Para crear un nuevo perfil de agente</span><span class="sxs-lookup"><span data-stu-id="70d2e-227">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="70d2e-228">Cree una conexión al distribuidor utilizando una instancia de la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-228">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="70d2e-229">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.AgentProfile>.</span><span class="sxs-lookup"><span data-stu-id="70d2e-229">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span>  
  
3.  <span data-ttu-id="70d2e-230">Establezca las siguientes propiedades en el objeto:</span><span class="sxs-lookup"><span data-stu-id="70d2e-230">Set the following properties on the object:</span></span>  
  
    -   <span data-ttu-id="70d2e-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> : nombre del perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> - the name for the profile.</span></span>  
  
    -   <span data-ttu-id="70d2e-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> : un valor <xref:Microsoft.SqlServer.Replication.AgentType> que especifica el tipo de Agente de replicación para el que se crea el perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> - an <xref:Microsoft.SqlServer.Replication.AgentType> value that specifies the type of replication agent for which the profile is being created.</span></span>  
  
    -   <span data-ttu-id="70d2e-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> : la <xref:Microsoft.SqlServer.Management.Common.ServerConnection> creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="70d2e-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> created in step 1.</span></span>  
  
    -   <span data-ttu-id="70d2e-234">(Opcional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> : una descripción del perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-234">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> - a description of the profile.</span></span>  
  
    -   <span data-ttu-id="70d2e-235">(Opcional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A>: establezca esta propiedad en `true` si todos los nuevos trabajos de agente para <xref:Microsoft.SqlServer.Replication.AgentType> van a utilizar de forma predeterminada este perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-235">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A> - set this property to `true` if all new agent jobs for this <xref:Microsoft.SqlServer.Replication.AgentType> will use this profile by default.</span></span>  
  
4.  <span data-ttu-id="70d2e-236">Llame al método <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> para crear el perfil en el servidor.</span><span class="sxs-lookup"><span data-stu-id="70d2e-236">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> method to create the profile on the server.</span></span>  
  
5.  <span data-ttu-id="70d2e-237">Una vez que el perfil existe en el servidor, puede personalizarlo agregando, quitando o cambiando los valores de parámetros de agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="70d2e-237">Once the profile exists on the server, you can customize it by adding, removing, or changing the values of replication agent parameters.</span></span>  
  
6.  <span data-ttu-id="70d2e-238">Para asignar el perfil a un trabajo del agente de replicación existente, llame al método <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-238">To assign the profile to an existing replication agent job, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> method.</span></span> <span data-ttu-id="70d2e-239">Pase el nombre de la base de datos de distribución para *distributionDBName* y el Id. del trabajo para *agentID*.</span><span class="sxs-lookup"><span data-stu-id="70d2e-239">Pass the name of the distribution database for *distributionDBName* and the ID of the job for *agentID*.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_RMO"></a> <span data-ttu-id="70d2e-240">Para modificar un perfil de agente existente</span><span class="sxs-lookup"><span data-stu-id="70d2e-240">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="70d2e-241">Cree una conexión al distribuidor utilizando una instancia de la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-241">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="70d2e-242">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="70d2e-242">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="70d2e-243">Pase el objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="70d2e-243">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object created in step 1.</span></span>  
  
3.  <span data-ttu-id="70d2e-244">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-244">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="70d2e-245">Si este método devuelve `false`, compruebe que el distribuidor existe.</span><span class="sxs-lookup"><span data-stu-id="70d2e-245">If this method returns `false`, verify that the Distributor exists.</span></span>  
  
4.  <span data-ttu-id="70d2e-246">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-246">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> method.</span></span> <span data-ttu-id="70d2e-247">Pase un valor <xref:Microsoft.SqlServer.Replication.AgentType> para reducir los perfiles devueltos a un tipo específico de agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="70d2e-247">Pass an <xref:Microsoft.SqlServer.Replication.AgentType> value to narrow down the returned profiles to a specific type of replication agent.</span></span>  
  
5.  <span data-ttu-id="70d2e-248">Obtenga el objeto <xref:Microsoft.SqlServer.Replication.AgentProfile> que desea del <xref:System.Collections.ArrayList>devuelto, donde la propiedad <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> del objeto coincide con el nombre del perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-248">Get the desired <xref:Microsoft.SqlServer.Replication.AgentProfile> object from the returned <xref:System.Collections.ArrayList>, where the <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> property of the object matches the profile name.</span></span>  
  
6.  <span data-ttu-id="70d2e-249">Llame a uno de los métodos siguientes de <xref:Microsoft.SqlServer.Replication.AgentProfile> para cambiar el perfil:</span><span class="sxs-lookup"><span data-stu-id="70d2e-249">Call one of the following methods of <xref:Microsoft.SqlServer.Replication.AgentProfile> to change the profile:</span></span>  
  
    -   <span data-ttu-id="70d2e-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> : agrega un parámetro compatible al perfil, donde *name* es el nombre del parámetro del Agente de replicación y *value* es el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="70d2e-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> - adds a supported parameter to the profile, where *name* is the name of the replication agent parameter and *value* is the specified value.</span></span> <span data-ttu-id="70d2e-251">Para enumerar todos los parámetros del agente compatibles para un tipo de agente determinado, llame al método <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-251">To enumerate all supported agent parameters for a given agent type, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="70d2e-252">Este método devuelve <xref:System.Collections.ArrayList> de objetos <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> que representa todos los parámetros compatibles.</span><span class="sxs-lookup"><span data-stu-id="70d2e-252">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent all supported parameters.</span></span>  
  
    -   <span data-ttu-id="70d2e-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> : quita un parámetro existente del perfil, donde *name* es el nombre del parámetro de Agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="70d2e-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> - removes an existing parameter from the profile, where *name* is the name of the replication agent parameter.</span></span> <span data-ttu-id="70d2e-254">Para enumerar todos los parámetros de agente actuales definidos para el perfil, llame al método <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-254">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="70d2e-255">Este método devuelve <xref:System.Collections.ArrayList> de objetos <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> que representan el parámetro existente para este perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-255">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span>  
  
    -   <span data-ttu-id="70d2e-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> : cambia la configuración de un parámetro existente en el perfil, donde *name* es el nombre del parámetro del agente y *newValue* es el valor al que se cambia el parámetro.</span><span class="sxs-lookup"><span data-stu-id="70d2e-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> - changes the setting of an existing parameter in the profile, where *name* is the name of the agent parameter and *newValue* is the value to which the parameter is being changed.</span></span> <span data-ttu-id="70d2e-257">Para enumerar todos los parámetros de agente actuales definidos para el perfil, llame al método <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-257">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="70d2e-258">Este método devuelve <xref:System.Collections.ArrayList> de objetos <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> que representan el parámetro existente para este perfil.</span><span class="sxs-lookup"><span data-stu-id="70d2e-258">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span> <span data-ttu-id="70d2e-259">Para enumerar todos los valores de parámetro del agente compatibles, llame al método <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-259">To enumerate all supported agent parameter settings, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="70d2e-260">Este método devuelve <xref:System.Collections.ArrayList> de objetos <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> que representa los valores compatibles para todos los parámetros.</span><span class="sxs-lookup"><span data-stu-id="70d2e-260">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent the supported values for all parameters.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_RMO"></a> <span data-ttu-id="70d2e-261">Para eliminar un perfil de agente</span><span class="sxs-lookup"><span data-stu-id="70d2e-261">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="70d2e-262">Cree una conexión al distribuidor utilizando una instancia de la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-262">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="70d2e-263">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.AgentProfile>.</span><span class="sxs-lookup"><span data-stu-id="70d2e-263">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span> <span data-ttu-id="70d2e-264">Establezca el nombre del perfil para <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> y la <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 1 para <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="70d2e-264">Set the name of the profile for <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="70d2e-265">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="70d2e-265">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="70d2e-266">Si este método devuelve `false`, significa que el nombre especificado era incorrecto o el perfil no existe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="70d2e-266">If this method returns `false`, either the specified name was incorrect or the profile does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="70d2e-267">Compruebe que la propiedad <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> está establecida en <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, que indica un perfil del cliente.</span><span class="sxs-lookup"><span data-stu-id="70d2e-267">Verify that the <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> property is set to <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, which indicates a customer profile.</span></span> <span data-ttu-id="70d2e-268">No debería quitar ningún perfil que tenga un valor de <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> para <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span><span class="sxs-lookup"><span data-stu-id="70d2e-268">You should not remove a profile that has a value of <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> for <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span></span>  
  
5.  <span data-ttu-id="70d2e-269">Llame al método <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> para quitar el perfil definido por el usuario representado por este objeto del servidor.</span><span class="sxs-lookup"><span data-stu-id="70d2e-269">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> method to remove the user-defined profile represented by this object from the server.</span></span>  
  
##  <a name="follow-up-after-changing-agent-parameters"></a><a name="FollowUp"></a> <span data-ttu-id="70d2e-270">Seguimiento: después de cambiar los parámetros de agente</span><span class="sxs-lookup"><span data-stu-id="70d2e-270">Follow Up: After Changing Agent Parameters</span></span>  
 <span data-ttu-id="70d2e-271">Los cambios en los parámetros del agente tendrán efecto la próxima vez que se inicie el agente.</span><span class="sxs-lookup"><span data-stu-id="70d2e-271">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="70d2e-272">Si el agente se ejecuta sin interrupción, debe detenerlo y reiniciarlo.</span><span class="sxs-lookup"><span data-stu-id="70d2e-272">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d2e-273">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70d2e-273">See Also</span></span>  
 <span data-ttu-id="70d2e-274">[Perfiles del Agente de replicación](replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="70d2e-274">[Replication Agent Profiles](replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="70d2e-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span><span class="sxs-lookup"><span data-stu-id="70d2e-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span></span>  
 <span data-ttu-id="70d2e-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="70d2e-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="70d2e-277">[Replication Distribution Agent](replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="70d2e-277">[Replication Distribution Agent](replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="70d2e-278">[Replication Merge Agent](replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="70d2e-278">[Replication Merge Agent](replication-merge-agent.md) </span></span>  
 [<span data-ttu-id="70d2e-279">Agente de lectura de cola de replicación</span><span class="sxs-lookup"><span data-stu-id="70d2e-279">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)  
  
  
