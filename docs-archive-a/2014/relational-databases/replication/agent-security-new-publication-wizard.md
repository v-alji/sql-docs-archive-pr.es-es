---
title: Seguridad del agente (Asistente para nueva publicación) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.agentsecurity.articles.f1
ms.assetid: 05ae44df-8e9f-46ea-95f6-972ad109c6c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a0da30cb49a73024ca83d8587a4f6477d21c49c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670957"
---
# <a name="agent-security-new-publication-wizard"></a><span data-ttu-id="ff318-102">Seguridad del agente (Asistente para nueva publicación)</span><span class="sxs-lookup"><span data-stu-id="ff318-102">Agent Security (New Publication Wizard)</span></span>
  <span data-ttu-id="ff318-103">La página **Seguridad del agente** permite especificar las cuentas en las que se ejecutarán los siguientes agentes y a partir de las cuales establecerán conexiones con los equipos que conforman una topología de replicación:</span><span class="sxs-lookup"><span data-stu-id="ff318-103">The **Agent Security** page allows you to specify the accounts under which the following agents run and make connections to the computers in a replication topology:</span></span>  
  
-   <span data-ttu-id="ff318-104">Agente de instantáneas para todas las publicaciones.</span><span class="sxs-lookup"><span data-stu-id="ff318-104">The Snapshot Agent for all publications.</span></span>  
  
-   <span data-ttu-id="ff318-105">Agente de registro del LOG para todas las publicaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="ff318-105">The Log Reader Agent for all transactional publications.</span></span>  
  
-   <span data-ttu-id="ff318-106">Agente de lectura de cola para publicaciones transaccionales que permiten suscripciones actualizables.</span><span class="sxs-lookup"><span data-stu-id="ff318-106">The Queue Reader Agent for transactional publications that allow updatable subscriptions.</span></span> <span data-ttu-id="ff318-107">Se crea el trabajo de Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondiente a este agente si se ha especificado **Publicación transaccional con suscripciones actualizables** en la página **Tipo de publicación**, independientemente del tipo de suscripciones actualizables que se use.</span><span class="sxs-lookup"><span data-stu-id="ff318-107">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job for this agent is created if you specified **Transactional publication with updatable subscriptions** on the **Publication Type** page, regardless of the type of updatable subscriptions you use.</span></span> <span data-ttu-id="ff318-108">Para obtener más información sobre las suscripciones actualizables, vea [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ff318-108">For more information about updatable subscriptions, see [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="ff318-109">Para obtener información sobre los permisos requeridos por los agentes y las prácticas recomendadas que se aplican a la seguridad de replicación, vea [Replication Agent Security Model](security/replication-agent-security-model.md) y [Replication Security Best Practices](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="ff318-109">For information about permissions required by agents and best practices for replication security, see [Replication Agent Security Model](security/replication-agent-security-model.md) and [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ff318-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="ff318-110">Options</span></span>  
 <span data-ttu-id="ff318-111">**Agente de instantáneas**</span><span class="sxs-lookup"><span data-stu-id="ff318-111">**Snapshot Agent**</span></span>  
 <span data-ttu-id="ff318-112">Se muestra en todas las publicaciones.</span><span class="sxs-lookup"><span data-stu-id="ff318-112">Displayed for all publications.</span></span> <span data-ttu-id="ff318-113">Haga clic en **Configuración de seguridad** para especificar la configuración de seguridad en el cuadro de diálogo **Seguridad del Agente de instantáneas** .</span><span class="sxs-lookup"><span data-stu-id="ff318-113">Click **Security Settings** to specify security settings in the **Snapshot Agent Security** dialog box.</span></span>  
  
 <span data-ttu-id="ff318-114">Haga clic en **Ayuda** en el cuadro de diálogo **Seguridad del Agente de instantáneas** para obtener más información sobre los permisos requeridos para las cuentas utilizadas por el Agente de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="ff318-114">Click **Help** on the **Snapshot Agent Security** dialog box for more information about the permissions required for accounts used by the Snapshot Agent.</span></span>  
  
 <span data-ttu-id="ff318-115">**Agente de lector del registro**</span><span class="sxs-lookup"><span data-stu-id="ff318-115">**Log Reader Agent**</span></span>  
 <span data-ttu-id="ff318-116">Se muestra en todas las publicaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="ff318-116">Displayed for all transactional publications.</span></span> <span data-ttu-id="ff318-117">Haga clic en **Configuración de seguridad** para especificar la configuración de seguridad en el cuadro de diálogo **Seguridad del Agente de registro del LOG** .</span><span class="sxs-lookup"><span data-stu-id="ff318-117">Click **Security Settings** to specify security settings in the **Log Reader Agent Security** dialog box.</span></span>  
  
 <span data-ttu-id="ff318-118">Haga clic en **Ayuda** en el cuadro de diálogo **Seguridad del Agente de registro del LOG** para obtener más información sobre los permisos requeridos para las cuentas utilizadas por el Agente de registro del LOG.</span><span class="sxs-lookup"><span data-stu-id="ff318-118">Click **Help** on the **Log Reader Agent Security** dialog box for more information about the permissions required for accounts used by the Log Reader Agent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff318-119">Existe un Agente de registro del LOG para cada base de datos que se publica utilizando la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="ff318-119">There is one Log Reader Agent for each database that is published using transactional replication.</span></span> <span data-ttu-id="ff318-120">Si ya existe una publicación transaccional en la base de datos, la configuración de seguridad será de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="ff318-120">If a transactional publication already exists in the database, the security settings are read-only.</span></span> <span data-ttu-id="ff318-121">Es posible modificar la configuración del cuadro de diálogo **Propiedades de la publicación** , aunque los cambios afectarán a todas las publicaciones transaccionales de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ff318-121">You can change the settings in the **Publication Properties** dialog box, but changes affect all transactional publications in the database.</span></span>  
  
 <span data-ttu-id="ff318-122">**Agente de lectura de cola**</span><span class="sxs-lookup"><span data-stu-id="ff318-122">**Queue Reader Agent**</span></span>  
 <span data-ttu-id="ff318-123">Se muestra para las publicaciones transaccionales que admiten suscripciones actualizables</span><span class="sxs-lookup"><span data-stu-id="ff318-123">Displayed for transactional publications that allow updatable subscriptions.</span></span> <span data-ttu-id="ff318-124">Haga clic en **Configuración de seguridad** para especificar la configuración de seguridad en el cuadro de diálogo **Seguridad del Agente de lectura de cola** .</span><span class="sxs-lookup"><span data-stu-id="ff318-124">Click **Security Settings** to specify security settings in the **Queue Reader Agent Security** dialog box.</span></span> <span data-ttu-id="ff318-125">Se crea un trabajo de Agente de lectura de cola cuando finaliza este asistente. Esto no depende de que se hayan creado suscripciones de actualización en cola.</span><span class="sxs-lookup"><span data-stu-id="ff318-125">A Queue Reader Agent job is created when this wizard completes; it does not depend on you creating any queued updating subscriptions.</span></span> <span data-ttu-id="ff318-126">Si no tiene previsto crear una suscripción de actualización en cola, puede deshabilitar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="ff318-126">If you do not plan to create any queued updating subscriptions, you can disable the job.</span></span> <span data-ttu-id="ff318-127">Haga clic con el botón derecho en el trabajo (con el formato de nombre *[\<Publisher>].\<integer>* .) en la carpeta **Trabajos** del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y, después, haga clic en **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="ff318-127">Right-click the job (named in the form: *[\<Publisher>].\<integer>*.) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **Jobs** folder, and then click **Disable**.</span></span>  
  
 <span data-ttu-id="ff318-128">Haga clic en **Ayuda** en el cuadro de diálogo **Seguridad del Agente de lectura de cola** para obtener más información sobre los permisos requeridos para las cuentas utilizadas por el Agente de lectura de cola.</span><span class="sxs-lookup"><span data-stu-id="ff318-128">Click **Help** on the **Queue Reader Agent Security** dialog box for more information about the permissions required for accounts used by the Queue Reader Agent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff318-129">Hay un Agente de lectura de cola para cada base de datos de distribución (y para todos los publicadores que sirve).</span><span class="sxs-lookup"><span data-stu-id="ff318-129">There is one Queue Reader Agent for each distribution database (and all Publishers that it serves).</span></span> <span data-ttu-id="ff318-130">Si ya existe una publicación transaccional que permite suscripciones de actualización en cola en cualquiera de los publicadores que usa una determinada base de datos de distribución, la configuración de seguridad será de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="ff318-130">If a transactional publication that allows queued updating subscriptions already exists on any of the Publishers that use a given distribution database, the security settings are read-only.</span></span> <span data-ttu-id="ff318-131">Se pueden realizar cambios en la cuenta en la que el Agente de lectura de cola se ejecuta y establece conexiones en el cuadro de diálogo **Propiedades del distribuidor** , aunque los cambios afectarán a todos los publicadores que usen la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="ff318-131">You can change the account under which the Queue Reader Agent runs and makes connections in the **Distributor Properties** dialog box, but changes affect publications at all Publishers that use the distribution database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff318-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff318-132">See Also</span></span>  
 <span data-ttu-id="ff318-133">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="ff318-133">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="ff318-134">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span><span class="sxs-lookup"><span data-stu-id="ff318-134">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span></span>  
 <span data-ttu-id="ff318-135">[Ver y modificar las propiedades del distribuidor y del publicador](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ff318-135">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 <span data-ttu-id="ff318-136">[Ver y modificar propiedades de publicación](publish/view-and-modify-publication-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ff318-136">[View and Modify Publication Properties](publish/view-and-modify-publication-properties.md) </span></span>  
 <span data-ttu-id="ff318-137">[Administrar inicios de sesión y contraseñas en la replicación](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="ff318-137">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="ff318-138">[Publicar datos y objetos de base de datos](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="ff318-138">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="ff318-139">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="ff318-139">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  