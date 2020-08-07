---
title: Sincronizar una suscripción mediante el administrador de sincronización de Windows (Administrador de sincronización de Windows) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], Windows Synchronization Manager
- Windows Synchronization Manager
ms.assetid: 80f15dd6-e84d-4f96-9866-5b34ea531f1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bb31c344f91c68b04e03dd218f22b09bec44830b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746236"
---
# <a name="synchronize-a-subscription-using-windows-synchronization-manager-windows-synchronization-manager"></a><span data-ttu-id="b3268-102">Sincronizar una suscripción mediante el Administrador de sincronización de Windows (Administrador de sincronización de Windows)</span><span class="sxs-lookup"><span data-stu-id="b3268-102">Synchronize a Subscription Using Windows Synchronization Manager (Windows Synchronization Manager)</span></span>
  <span data-ttu-id="b3268-103">El Administrador de sincronización de[!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows solo se puede usar para sincronizar suscripciones con publicaciones de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se está ejecutando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el mismo equipo que el Administrador de sincronización (también se puede usar para sincronizar archivos y páginas web sin conexión).</span><span class="sxs-lookup"><span data-stu-id="b3268-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Synchronization Manager can only be used to synchronize subscriptions to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publications if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running on the same computer as Synchronization Manager (it can also be used to synchronize offline files and Web pages).</span></span> <span data-ttu-id="b3268-104">Para utilizar el Administrador de sincronización:</span><span class="sxs-lookup"><span data-stu-id="b3268-104">To use Synchronization Manager:</span></span>  
  
1.  <span data-ttu-id="b3268-105">Habilite la sincronización de suscripciones de extracción con el Administrador de sincronización de Windows en el cuadro de diálogo **Propiedades de suscripción - \<Subscriber>: \<SubscriptionDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="b3268-105">Enable the synchronization of pull subscriptions with Windows Synchronization Manager in the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box.</span></span> <span data-ttu-id="b3268-106">Para más información sobre el acceso a este cuadro de diálogo, vea [View and Modify Publication Properties](view-and-modify-pull-subscription-properties.md) (Ver y modificar las propiedades de una suscripción de extracción).</span><span class="sxs-lookup"><span data-stu-id="b3268-106">For more information about accessing this dialog box, see [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
2.  <span data-ttu-id="b3268-107">Obtenga acceso al Administrador de sincronización a través del menú **Inicio** en Windows.</span><span class="sxs-lookup"><span data-stu-id="b3268-107">Access Synchronization Manager through the **Start** menu in Windows.</span></span>  
  
 <span data-ttu-id="b3268-108">El Administrador de sincronización permite utilizar el Solucionador interactivo para las suscripciones de mezcla.</span><span class="sxs-lookup"><span data-stu-id="b3268-108">Synchronization Manager allows you to use the Interactive Resolver for merge subscriptions.</span></span> <span data-ttu-id="b3268-109">Generalmente, los conflictos detectados durante la sincronización se resuelven automáticamente, pero si se habilita la resolución interactiva, el usuario puede solucionarlos durante la sincronización.</span><span class="sxs-lookup"><span data-stu-id="b3268-109">Typically, conflicts detected during synchronization are resolved automatically, but if interactive resolution is enabled, conflicts can be resolved by a user during synchronization.</span></span> <span data-ttu-id="b3268-110">Si se realiza una sincronización fuera del Administrador de sincronización de Windows (por ejemplo, una sincronización programada o una sincronización a petición en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o en el Monitor de replicación), los conflictos se resuelven automáticamente sin intervención del usuario, según la resolución especificada para el artículo.</span><span class="sxs-lookup"><span data-stu-id="b3268-110">If a synchronization is performed outside of Windows Synchronization Manager (as a scheduled synchronization or an on demand synchronization in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Replication Monitor), conflicts are resolved automatically without user intervention, according to the resolver specified for the article.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3268-111">A partir de [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] y [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], las versiones de 64 bits del Administrador de sincronización de Windows no pueden detectar las suscripciones de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="b3268-111">Beginning with [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] and [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], 64-bit versions of the Windows Synchronization Manager cannot detect 32-bit subscriptions.</span></span>  
  
### <a name="to-enable-the-synchronization-of-pull-subscriptions-with-windows-synchronization-manager"></a><span data-ttu-id="b3268-112">Para habilitar la sincronización de suscripciones de extracción con el Administrador de sincronización de Windows</span><span class="sxs-lookup"><span data-stu-id="b3268-112">To enable the synchronization of pull subscriptions with Windows Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="b3268-113">En la página **General** del cuadro de diálogo **Propiedades de suscripción - \<Subscriber>: \<SubscriptionDatabase>** , seleccione un valor de **Habilitar** para la opción **Utilizar el Administrador de sincronización de Windows**.</span><span class="sxs-lookup"><span data-stu-id="b3268-113">On the **General** page of the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select a value of **Enable** for the **Use Windows Synchronization Manager** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-synchronize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="b3268-114">Para sincronizar una suscripción de extracción con el Administrador de sincronización</span><span class="sxs-lookup"><span data-stu-id="b3268-114">To synchronize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="b3268-115">Inicie el Administrador de sincronización mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3268-115">Launch Synchronization Manager using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b3268-116">En Internet Explorer, haga clic en el menú **Herramientas**y, a continuación, en **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="b3268-116">In Internet Explorer, click **Tools**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="b3268-117">Haga clic en **Inicio**, seleccione **Programas** o **Todos los programas**, **Accesorios**y, después, haga clic en **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="b3268-117">Click **Start**, point to **Programs** or **All Programs**, point to **Accessories**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="b3268-118">Haga clic en **Inicio**y, a continuación, en **Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="b3268-118">Click **Start**, and then click **Run.**</span></span> <span data-ttu-id="b3268-119">En el cuadro de diálogo **Ejecutar** , escriba `mobsync.exe` en el campo **abrir** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b3268-119">In the **Run** dialog box, type `mobsync.exe` in the **Open** field, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="b3268-120">En el cuadro de diálogo **Elementos para sincronizar** , seleccione las suscripciones para sincronizar.</span><span class="sxs-lookup"><span data-stu-id="b3268-120">In the **Items to Synchronize** dialog box, select the subscriptions to synchronize.</span></span> <span data-ttu-id="b3268-121">Las suscripciones se enumeran en las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b3268-121">Subscriptions are listed under the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
3.  <span data-ttu-id="b3268-122">Haga clic en **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="b3268-122">Click **Synchronize**.</span></span>  
  
### <a name="to-reinitialize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="b3268-123">Para reinicializar una suscripción de extracción con el Administrador de sincronización</span><span class="sxs-lookup"><span data-stu-id="b3268-123">To reinitialize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="b3268-124">En el cuadro de diálogo **Elementos para sincronizar** , seleccione una suscripción y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b3268-124">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b3268-125">En el cuadro de diálogo **Propiedades de suscripción de SQL Server** , haga clic en **Reinicializar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="b3268-125">In the **SQL Server Subscription Properties** dialog box, click **Reinitialize Subscription**.</span></span>  
  
3.  <span data-ttu-id="b3268-126">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b3268-126">Click **Yes**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="b3268-127">La próxima vez que se sincronice la suscripción, se aplicará de manera predeterminada una nueva instantánea a la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="b3268-127">The next time the subscription is synchronized, by default a new snapshot is applied to the subscription database.</span></span> <span data-ttu-id="b3268-128">Para obtener más información, vea [Reinicializar suscripciones](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="b3268-128">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3268-129">La replicación de mezcla permite que cualquier cambio pendiente se cargue en el publicador antes de que se aplique la instantánea, pero esta opción no está disponible en el Administrador de sincronización.</span><span class="sxs-lookup"><span data-stu-id="b3268-129">Merge replication allows any outstanding changes to be uploaded to the Publisher before the snapshot is applied, but this option is not available from Synchronization Manager.</span></span> <span data-ttu-id="b3268-130">Para cargar los cambios, sincronice la suscripción antes de reinicializarla.</span><span class="sxs-lookup"><span data-stu-id="b3268-130">To upload changes, synchronize the subscription before reinitializing it.</span></span>  
  
### <a name="to-set-properties-for-a-pull-subscription-in-synchronization-manager"></a><span data-ttu-id="b3268-131">Para establecer propiedades de una suscripción de extracción en el Administrador de sincronización.</span><span class="sxs-lookup"><span data-stu-id="b3268-131">To set properties for a pull subscription in Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="b3268-132">En el cuadro de diálogo **Elementos para sincronizar** , seleccione una suscripción y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b3268-132">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b3268-133">Vea y modifique las propiedades de las siguientes pestañas:</span><span class="sxs-lookup"><span data-stu-id="b3268-133">View and modify properties on the following tabs:</span></span>  
  
    -   <span data-ttu-id="b3268-134">**Identificación**</span><span class="sxs-lookup"><span data-stu-id="b3268-134">**Identification**</span></span>  
  
    -   <span data-ttu-id="b3268-135">**Inicio de sesión del suscriptor**, **Inicio de sesión del distribuidor**e **Inicio de sesión del publicador** (solamente para la replicación de mezcla)</span><span class="sxs-lookup"><span data-stu-id="b3268-135">**Subscriber Login**, **Distributor Login**, and **Publisher Login** (for merge replication only)</span></span>  
  
    -   <span data-ttu-id="b3268-136">**Información del servidor web** (para suscripciones de mezcla en suscriptores que ejecuten SQL Server 2005 o posterior)</span><span class="sxs-lookup"><span data-stu-id="b3268-136">**Web Server Information** (for merge subscriptions on Subscribers running SQL Server 2005 or later)</span></span>  
  
    -   <span data-ttu-id="b3268-137">**Otros**</span><span class="sxs-lookup"><span data-stu-id="b3268-137">**Other**</span></span>  
  
     <span data-ttu-id="b3268-138">Se recomienda utilizar la autenticación de Windows para todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="b3268-138">It is recommended to use Windows Authentication for all connections.</span></span> <span data-ttu-id="b3268-139">Para obtener información sobre los permisos que requieren el Agente de distribución y el Agente de mezcla, vea [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="b3268-139">For information about the permissions required by the Distribution Agent and the Merge Agent, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-a-pull-subscription-from-synchronization-manager"></a><span data-ttu-id="b3268-140">Para quitar una suscripción de extracción en el Administrador de sincronización</span><span class="sxs-lookup"><span data-stu-id="b3268-140">To remove a pull subscription from Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="b3268-141">En el cuadro de diálogo **Elementos para sincronizar** , seleccione una suscripción y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b3268-141">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b3268-142">En el cuadro de diálogo **Propiedades de suscripción de SQL Server** , haga clic en **Quitar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="b3268-142">In the **SQL Server Subscription Properties** dialog box, click **Remove Subscription**.</span></span>  
  
3.  <span data-ttu-id="b3268-143">Seleccione una opción en el cuadro de diálogo **Quitar suscripción** .</span><span class="sxs-lookup"><span data-stu-id="b3268-143">Select an option in the **Remove Subscription** dialog box.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-interactive-resolver"></a><span data-ttu-id="b3268-144">Para utilizar el Solucionador interactivo</span><span class="sxs-lookup"><span data-stu-id="b3268-144">To use the Interactive Resolver</span></span>  
  
1.  <span data-ttu-id="b3268-145">Habilite el artículo y la suscripción para utilizar la resolución interactiva.</span><span class="sxs-lookup"><span data-stu-id="b3268-145">Enable the article and subscription to use interactive resolution.</span></span> <span data-ttu-id="b3268-146">Para más información, vea [Especificar la resolución interactiva de conflictos para artículos de mezcla](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span><span class="sxs-lookup"><span data-stu-id="b3268-146">For more information, see [Specify Interactive Conflict Resolution for Merge Articles](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span></span>
  
2.  <span data-ttu-id="b3268-147">Después de que la suscripción comienza la sincronización en el Administrador de sincronización, el Solucionador interactivo se inicia automáticamente si la resolución interactiva de conflictos está habilitada y hay conflictos en uno o varios artículos.</span><span class="sxs-lookup"><span data-stu-id="b3268-147">After the subscription begins synchronizing in Synchronization Manager, the Interactive Resolver launches automatically if interactive conflict resolution is enabled and there are conflicts for one or more articles.</span></span> <span data-ttu-id="b3268-148">El Solucionador interactivo muestra un conflicto cada vez, con una sugerencia de resolución para cada conflicto (basada en el solucionador especificado al crear la publicación y la suscripción).</span><span class="sxs-lookup"><span data-stu-id="b3268-148">The Interactive Resolver displays conflicts one at a time, with a suggested resolution for each conflict (based on the resolver specified when the publication and subscription were created).</span></span>  
  
3.  <span data-ttu-id="b3268-149">Opcionalmente, edite cualquiera de las columnas que se muestran en el Solucionador interactivo y, a continuación, haga clic en uno de los siguientes botones para solucionar el conflicto:</span><span class="sxs-lookup"><span data-stu-id="b3268-149">Optionally edit any of the columns displayed in the Interactive Resolver, and then click one of the following buttons to resolve the conflict:</span></span>  
  
    -   <span data-ttu-id="b3268-150">**Aceptar sugerencia**</span><span class="sxs-lookup"><span data-stu-id="b3268-150">**Accept Suggested**</span></span>  
  
    -   <span data-ttu-id="b3268-151">**Aceptar publicador**</span><span class="sxs-lookup"><span data-stu-id="b3268-151">**Accept Publisher**</span></span>  
  
    -   <span data-ttu-id="b3268-152">**Aceptar suscriptor**</span><span class="sxs-lookup"><span data-stu-id="b3268-152">**Accept Subscriber**</span></span>  
  
    -   <span data-ttu-id="b3268-153">**Resolver todos automáticamente** (se resuelven todos los conflictos actuales sin más intervención)</span><span class="sxs-lookup"><span data-stu-id="b3268-153">**Resolve All Automatically** (all current conflicts are resolved without further input)</span></span>  
  
     <span data-ttu-id="b3268-154">A continuación, se aplica la fila seleccionada al publicador y/o suscriptor; se propaga a otros nodos de la topología durante sincronizaciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b3268-154">The selected row is then applied to the Publisher and/or Subscriber; it is propagated to other nodes in the topology during subsequent synchronizations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3268-155">Las ediciones se aplican solamente si son parte de la fila que se ha seleccionado para la resolución.</span><span class="sxs-lookup"><span data-stu-id="b3268-155">Edits are only applied if they are part of the row that is chosen for resolution.</span></span> <span data-ttu-id="b3268-156">Por ejemplo, si realiza ediciones en **Publicador**, y, a continuación, hace clic en **Aceptar suscriptor**, se descartan las ediciones.</span><span class="sxs-lookup"><span data-stu-id="b3268-156">For example, if you make edits under **Publisher**, and then click **Accept Subscriber**, the edits are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3268-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3268-157">See Also</span></span>  
 [<span data-ttu-id="b3268-158">Interactive Conflict Resolution</span><span class="sxs-lookup"><span data-stu-id="b3268-158">Interactive Conflict Resolution</span></span>](merge/advanced-merge-replication-conflict-interactive-resolution.md)  
  
