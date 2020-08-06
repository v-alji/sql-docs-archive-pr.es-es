---
title: Agente de instantáneas (Asistente para nueva publicación) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.configuresnapshotagent.f1
ms.assetid: 0257d4ee-1f7b-49fd-b4ef-65bfc1ef6951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c45fa3444fb2f81436a40a2bfb80519aea105c47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677538"
---
# <a name="snapshot-agent-new-publication-wizard"></a><span data-ttu-id="3eaa1-102">Agente de instantáneas (Asistente para nueva publicación)</span><span class="sxs-lookup"><span data-stu-id="3eaa1-102">Snapshot Agent (New Publication Wizard)</span></span>
  <span data-ttu-id="3eaa1-103">El Agente de instantáneas crea archivos que contienen el esquema y los datos de publicación que se utilizan para inicializar nuevas suscripciones.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-103">The Snapshot Agent creates files containing the publication schema and data that are used to initialize new subscriptions.</span></span> <span data-ttu-id="3eaa1-104">De forma predeterminada, el Agente de instantáneas se ejecuta inmediatamente después de la creación de la publicación en el Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-104">By default, the Snapshot Agent runs immediately after the publication is created in the New Publication Wizard.</span></span> <span data-ttu-id="3eaa1-105">Posteriormente, el agente se ejecuta de acuerdo con la programación que el usuario haya especificado.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-105">Subsequently, the agent runs according to a schedule you specify.</span></span> <span data-ttu-id="3eaa1-106">Que el agente cree nuevos archivos de instantáneas cada vez que se ejecute depende del tipo de replicación y de las opciones que se hayan elegido.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-106">Whether the agent creates new snapshot files each time it runs depends on the type of replication and options chosen.</span></span> <span data-ttu-id="3eaa1-107">Para obtener más información, vea [Crear y aplicar una instantánea](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="3eaa1-107">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="3eaa1-108">Para las publicaciones de combinación que utilizan filtros con parámetros, debe crear una instantánea para cada partición de datos después de haber finalizado la instantánea de publicación.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-108">For merge publications that use parameterized filters, you must create a snapshot for each partition of data after the publication snapshot has completed.</span></span> <span data-ttu-id="3eaa1-109">Para más información, consulte [Instantáneas para publicaciones de combinación con filtros con parámetros](snapshots-for-merge-publications-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="3eaa1-109">For more information, see [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3eaa1-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="3eaa1-110">Options</span></span>  
 <span data-ttu-id="3eaa1-111">**Crear una instantánea inmediatamente** (replicación de mezcla) o **Crear una instantánea inmediatamente y mantenerla disponible para inicializar suscripciones** (replicación transaccional)</span><span class="sxs-lookup"><span data-stu-id="3eaa1-111">**Create a snapshot immediately** (merge replication) or **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** (transactional replication)</span></span>  
 <span data-ttu-id="3eaa1-112">Active esta casilla para crear una instantánea inmediatamente después de que finalice el Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-112">Select this check box to create a snapshot immediately after the New Publication Wizard is completed.</span></span> <span data-ttu-id="3eaa1-113">Desactive esta casilla si tiene previsto cambiar las propiedades de la instantánea en el cuadro de diálogo **Propiedades de la publicación** antes de generar una instantánea o bien si inicializa el suscriptor sin una instantánea.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-113">Clear this check box if you plan to change snapshot properties in the **Publication Properties** dialog box before generating a snapshot, or if you will initialize the Subscriber without a snapshot.</span></span> <span data-ttu-id="3eaa1-114">Para obtener más información, consulte [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="3eaa1-114">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3eaa1-115">El asistente podría solicitar una conexión al distribuidor para iniciar un trabajo adecuado del Agente de distribución o el Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-115">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
 <span data-ttu-id="3eaa1-116">**Programar el Agente de instantáneas para ejecutarse**</span><span class="sxs-lookup"><span data-stu-id="3eaa1-116">**Schedule the Snapshot Agent to run at the following times**</span></span>  
 <span data-ttu-id="3eaa1-117">Acepte el programa predeterminado para la ejecución del Agente de instantáneas o haga clic en **Cambiar** para especificar un programa.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-117">Accept the default schedule for running the Snapshot Agent, or click **Change** to specify a schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eaa1-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3eaa1-118">See Also</span></span>  
 <span data-ttu-id="3eaa1-119">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="3eaa1-119">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="3eaa1-120">[Crear y aplicar la instantánea inicial](create-and-apply-the-initial-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="3eaa1-120">[Create and Apply the Initial Snapshot](create-and-apply-the-initial-snapshot.md) </span></span>  
 <span data-ttu-id="3eaa1-121">[Ver y modificar propiedades de publicación](publish/view-and-modify-publication-properties.md) </span><span class="sxs-lookup"><span data-stu-id="3eaa1-121">[View and Modify Publication Properties](publish/view-and-modify-publication-properties.md) </span></span>  
 <span data-ttu-id="3eaa1-122">[Inicializar una suscripción con una instantánea](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="3eaa1-122">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="3eaa1-123">[Publicar datos y objetos de base de datos](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="3eaa1-123">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="3eaa1-124">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="3eaa1-124">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
