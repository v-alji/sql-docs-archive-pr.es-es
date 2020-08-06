---
title: Suscriptores | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscribers.f1
helpviewer_keywords:
- Subscribers [SQL Server replication]
ms.assetid: 43fb2454-c220-4d25-a826-83c332eb00d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c5281a53b755bc171cdf96e7856e38ee6a54a1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670915"
---
# <a name="subscribers"></a><span data-ttu-id="57078-102">Suscriptores</span><span class="sxs-lookup"><span data-stu-id="57078-102">Subscribers</span></span>
  <span data-ttu-id="57078-103">Especifique los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suscriptores de o que no sean de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que recibirán una suscripción a la publicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="57078-103">Specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers that will receive a subscription to the selected publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="57078-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="57078-104">Options</span></span>  
 <span data-ttu-id="57078-105">**Suscriptores**</span><span class="sxs-lookup"><span data-stu-id="57078-105">**Subscribers**</span></span>  
 <span data-ttu-id="57078-106">Active la casilla de la cuadrícula para habilitar el origen de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o no[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondiente como suscriptor a la publicación seleccionada en la página **Publicación** .</span><span class="sxs-lookup"><span data-stu-id="57078-106">Select the check box in the grid to enable the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source as a Subscriber to the publication chosen on the **Publication** page.</span></span> <span data-ttu-id="57078-107">Si el suscriptor no aparece, haga clic en **Agregar suscriptor** o **Agregar suscriptor de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="57078-107">If the Subscriber is not listed, click **Add Subscriber** or **Add SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="57078-108">**Base de datos de suscripciones**</span><span class="sxs-lookup"><span data-stu-id="57078-108">**Subscription database**</span></span>  
 <span data-ttu-id="57078-109">La información mostrada y las acciones disponibles en esta columna dependen del tipo de suscriptor que aparece en la columna **Suscriptores** :</span><span class="sxs-lookup"><span data-stu-id="57078-109">The information displayed in and actions available from this column depend on the type of Subscriber listed in the **Subscribers** column:</span></span>  
  
-   <span data-ttu-id="57078-110">Para suscriptores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , seleccione una base de datos de suscripciones de la lista **Base de datos de suscripciones** o cree una nueva base de datos seleccionando el comando **Base de datos nueva** de la misma lista.</span><span class="sxs-lookup"><span data-stu-id="57078-110">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, select a subscription database from the **Subscription Database** list or create a new database by selecting the **New database** command from the same list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57078-111">Si va a habilitar el publicador como suscriptor, la base de datos de suscripciones debe ser diferente de la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="57078-111">If you are enabling the Publisher as a Subscriber, the subscription database must be different from the publication database.</span></span>  
  
-   <span data-ttu-id="57078-112">Para suscriptores que no sean de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la base de datos de suscripciones no aparece.</span><span class="sxs-lookup"><span data-stu-id="57078-112">For non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, the subscription database is not displayed.</span></span> <span data-ttu-id="57078-113">Especifique la base de datos, junto con otra información de conexión, en el campo **Nombre del origen de datos** del cuadro de diálogo **Agregar suscriptor que no sea de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="57078-113">Specify the database, along with other connection information, in the **Data source name** field of the **Add Non-SQL Server** dialog box.</span></span> <span data-ttu-id="57078-114">Este cuadro de diálogo está disponible si hace clic en **Agregar suscriptor** y, a continuación, en **Agregar suscriptor que no sea de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="57078-114">This dialog box is available by clicking **Add Subscriber** and then clicking **Add Non-SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="57078-115">**Agregar suscriptor**</span><span class="sxs-lookup"><span data-stu-id="57078-115">**Add Subscriber**</span></span>  
 <span data-ttu-id="57078-116">Agregue un servidor a la lista de servidores que pueda habilitarse como suscriptores.</span><span class="sxs-lookup"><span data-stu-id="57078-116">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="57078-117">Este botón aparece cuando se cumplen todas las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="57078-117">This button is displayed when all of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="57078-118">La publicación que ha seleccionado es una publicación de instantáneas o transaccional que no admite la actualización de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="57078-118">The publication you selected is a snapshot or transactional publication that does not support updating subscriptions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57078-119">Si la publicación a la que se va a suscribir tiene suscripciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y no está habilitada todavía para suscriptores que no sean de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no se puede agregar una suscripción que no sea de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57078-119">If the publication you are subscribing to has [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscriptions and the publication is not already enabled for non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, you cannot add a non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscription.</span></span>  
  
-   <span data-ttu-id="57078-120">La suscripción es una suscripción de inserción.</span><span class="sxs-lookup"><span data-stu-id="57078-120">The subscription is a push subscription.</span></span>  
  
-   <span data-ttu-id="57078-121">El publicador de la publicación seleccionada es [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o posterior.</span><span class="sxs-lookup"><span data-stu-id="57078-121">The Publisher of the selected publication is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later.</span></span>  
  
 <span data-ttu-id="57078-122">Al hacer clic en **Agregar suscriptor** , aparece un menú con dos opciones: **Agregar suscriptor de SQL Server** y **Agregar suscriptor que no sea de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="57078-122">Clicking **Add Subscriber** shows a menu with two choices: **Add SQL Server Subscriber** and **Add Non-SQL Server Subscriber**.</span></span> <span data-ttu-id="57078-123">Haga clic en **Agregar suscriptor que no sea de SQL Server** para agregar un suscriptor de Oracle o IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="57078-123">Click **Add Non-SQL Server Subscriber** to add an Oracle or IBM DB2 Subscriber.</span></span>  
  
 <span data-ttu-id="57078-124">**Agregar suscriptor de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="57078-124">**Add SQL Server Subscriber**</span></span>  
 <span data-ttu-id="57078-125">Agregue un servidor a la lista de servidores que pueda habilitarse como suscriptores.</span><span class="sxs-lookup"><span data-stu-id="57078-125">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="57078-126">Este botón aparece cuando se cumplen una o varias de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="57078-126">This button is displayed when one or more of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="57078-127">La publicación que ha seleccionado es una publicación de combinación, o una publicación de instantáneas o transaccional que admite actualización de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="57078-127">The publication you selected is a merge publication, or a snapshot or transactional publication that supports updating subscriptions.</span></span>  
  
-   <span data-ttu-id="57078-128">La suscripción es una suscripción de extracción.</span><span class="sxs-lookup"><span data-stu-id="57078-128">The subscription is a pull subscription.</span></span>  
  
-   <span data-ttu-id="57078-129">El publicador de la publicación seleccionada es anterior a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57078-129">The Publisher of the selected publication is earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="57078-130">Para versiones anteriores, este botón solamente aparece cuando se cumplen una o varias de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="57078-130">For earlier versions, the button is displayed only if one or more of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="57078-131">Es miembro del rol fijo de servidor **sysadmin** en el publicador.</span><span class="sxs-lookup"><span data-stu-id="57078-131">You are a member of the **sysadmin** fixed server role at the Publisher.</span></span>  
  
    -   <span data-ttu-id="57078-132">Se ha agregado el suscriptor a la página **Suscriptores** del cuadro de diálogo **Propiedades del publicador** .</span><span class="sxs-lookup"><span data-stu-id="57078-132">The Subscriber has been added on the **Subscribers** page of the **Publisher Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="57078-133">La publicación permite suscripciones anónimas.</span><span class="sxs-lookup"><span data-stu-id="57078-133">The publication allows anonymous subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57078-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57078-134">See Also</span></span>  
 <span data-ttu-id="57078-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="57078-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="57078-136">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="57078-136">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="57078-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="57078-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="57078-138">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="57078-138">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
