---
title: Seguridad del Agente de mezcla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.MA.f1
helpviewer_keywords:
- Merge Agent Security dialog box
ms.assetid: 9b86171a-4381-4b39-869a-cdc161e7cd15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecbb044ca87ccfc74c5cb39a016667d15cf7a859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746965"
---
# <a name="merge-agent-security"></a><span data-ttu-id="25fef-102">Seguridad del Agente de mezcla</span><span class="sxs-lookup"><span data-stu-id="25fef-102">Merge Agent Security</span></span>
  <span data-ttu-id="25fef-103">El cuadro de diálogo **Seguridad del Agente de mezcla** permite especificar la cuenta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows en la que se ejecuta el Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="25fef-103">The **Merge Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Merge Agent runs.</span></span> <span data-ttu-id="25fef-104">El Agente de mezcla se ejecuta en el distribuidor para las suscripciones de inserción y en el suscriptor para las suscripciones de extracción.</span><span class="sxs-lookup"><span data-stu-id="25fef-104">The Merge Agent runs at the Distributor for push subscriptions and at the Subscriber for pull subscriptions.</span></span> <span data-ttu-id="25fef-105">La cuenta de Windows se denomina también *cuenta de proceso*porque el proceso del agente se ejecuta con dicha cuenta.</span><span class="sxs-lookup"><span data-stu-id="25fef-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span> <span data-ttu-id="25fef-106">Las opciones adicionales disponibles en el cuadro de diálogo dependen de cómo se tenga acceso al mismo:</span><span class="sxs-lookup"><span data-stu-id="25fef-106">Additional options available in the dialog box depend on how you access it:</span></span>  
  
-   <span data-ttu-id="25fef-107">Si se tiene acceso al cuadro de diálogo desde el Asistente para nueva suscripción, también permite especificar el contexto para el que el Agente de mezcla realiza las conexiones con el suscriptor (para suscripciones de inserción) o con el publicador y el distribuidor (para las suscripciones de extracción).</span><span class="sxs-lookup"><span data-stu-id="25fef-107">If the dialog box is accessed from the New Subscription Wizard, it also allows you to specify the context under which the Merge Agent makes connections to the Subscriber (for push subscriptions) or the Publisher and Distributor (for pull subscriptions).</span></span> <span data-ttu-id="25fef-108">La conexión puede realizarse con la cuenta Windows o en el contexto de una cuenta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que especifique.</span><span class="sxs-lookup"><span data-stu-id="25fef-108">The connection can be made using the Windows account or under the context of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
-   <span data-ttu-id="25fef-109">Si se tiene acceso al cuadro de diálogo desde el cuadro de diálogo **Propiedades de suscripción** , se debe especificar el contexto en que el Agente de mezcla realiza las conexiones haciendo clic en el botón de propiedades ( **...** ) de la fila **Conexión de suscriptor** o **Conexión de publicador** de dicho cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="25fef-109">If the dialog box is accessed from the **Subscription Properties** dialog box, specify the context under which the Merge Agent makes connections by clicking the properties button (**...**) in the **Subscriber Connection** or **Publisher Connection** row of that dialog box.</span></span> <span data-ttu-id="25fef-110">Para más información sobre cómo acceder al cuadro de diálogo **Propiedades de suscripción**, vea [Ver y modificar las propiedades de una suscripción de inserción](view-and-modify-push-subscription-properties.md) y [Ver y modificar las propiedades de una suscripción de extracción](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="25fef-110">For more information about accessing the **Subscription Properties** dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and how to: [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
 <span data-ttu-id="25fef-111">Todas las cuentas deben ser válidas y se debe especificar la contraseña correcta para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="25fef-111">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="25fef-112">Las cuentas y las contraseñas se validan cuando se ejecuta el agente.</span><span class="sxs-lookup"><span data-stu-id="25fef-112">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="25fef-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="25fef-113">Options</span></span>  
 <span data-ttu-id="25fef-114">**Process Account**</span><span class="sxs-lookup"><span data-stu-id="25fef-114">**Process Account**</span></span>  
 <span data-ttu-id="25fef-115">Escriba la cuenta de Windows con la que se ejecutará el Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="25fef-115">Enter a Windows account under which the Merge Agent runs.</span></span>  
  
-   <span data-ttu-id="25fef-116">Para las suscripciones de inserción, la cuenta debe:</span><span class="sxs-lookup"><span data-stu-id="25fef-116">For push subscriptions, the account must:</span></span>  
  
    -   <span data-ttu-id="25fef-117">Ser como mínimo miembro del rol fijo de base de datos **db_owner** en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="25fef-117">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
    -   <span data-ttu-id="25fef-118">Ser miembro de la PAL.</span><span class="sxs-lookup"><span data-stu-id="25fef-118">Be a member of the PAL.</span></span>  
  
    -   <span data-ttu-id="25fef-119">Ser un inicio de sesión asociado a un usuario en la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="25fef-119">Be a login associated with a user in the publication database.</span></span>  
  
    -   <span data-ttu-id="25fef-120">Tener permisos de lectura en el recurso compartido de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="25fef-120">Have read permissions on the snapshot share.</span></span>  
  
-   <span data-ttu-id="25fef-121">Para las suscripciones de extracción, la cuenta debe ser como mínimo miembro del rol fijo de base de datos **db_owner** en la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="25fef-121">For pull subscriptions, the account must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
 <span data-ttu-id="25fef-122">Si se suplanta la cuenta de proceso al realizar las conexiones serán necesarios permisos adicionales.</span><span class="sxs-lookup"><span data-stu-id="25fef-122">Additional permissions are required if the process account is impersonated when connections are made.</span></span> <span data-ttu-id="25fef-123">Vea las secciones **Conectar al publicador y distribuidor** y **Conectar al suscriptor** a continuación.</span><span class="sxs-lookup"><span data-stu-id="25fef-123">See the **Connect to the Publisher and Distributor** and **Connect to the Subscriber** sections below.</span></span>  
  
 <span data-ttu-id="25fef-124">No se puede especificar **Cuenta de proceso** para las suscripciones de extracción a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], ya que el Agente de mezcla no se ejecuta en instancias de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25fef-124">**Process Account** cannot be specified for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], because the Merge Agent does not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
 <span data-ttu-id="25fef-125">**Contraseña** y **Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="25fef-125">**Password** and **Confirm Password**</span></span>  
 <span data-ttu-id="25fef-126">Escriba la contraseña de la cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="25fef-126">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="25fef-127">**Conectar al publicador y distribuidor**</span><span class="sxs-lookup"><span data-stu-id="25fef-127">**Connect to the Publisher and Distributor**</span></span>  
 <span data-ttu-id="25fef-128">Para las suscripciones de inserción, las conexiones con el publicador y el distribuidor siempre se realizan suplantando la cuenta especificada en el cuadro de texto **Cuenta de proceso** .</span><span class="sxs-lookup"><span data-stu-id="25fef-128">For push subscriptions, connections to the Publisher and Distributor are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="25fef-129">Para las suscripciones de extracción, debe elegir si el Agente de mezcla debe realizar las conexiones con el publicador y el distribuidor mediante la suplantación de la cuenta especificada en el cuadro de texto **Cuenta de proceso** o bien usar una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25fef-129">For pull subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="25fef-130">Si selecciona utilizar una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , especifique una contraseña y un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25fef-130">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="25fef-131">recomienda que se seleccione la opción de suplantar la cuenta de Windows en lugar de utilizar una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25fef-131">recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="25fef-132">La cuenta de Windows o la cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usada para la conexión debe:</span><span class="sxs-lookup"><span data-stu-id="25fef-132">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must:</span></span>  
  
-   <span data-ttu-id="25fef-133">Ser miembro de la PAL.</span><span class="sxs-lookup"><span data-stu-id="25fef-133">Be a member of the PAL.</span></span>  
  
-   <span data-ttu-id="25fef-134">Ser un inicio de sesión asociado a un usuario en la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="25fef-134">Be a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="25fef-135">Ser un inicio de sesión asociado a un usuario en la base de datos de distribución (el usuario puede ser el usuario Guest).</span><span class="sxs-lookup"><span data-stu-id="25fef-135">Be a login associated with a user in the distribution database (the user can be the Guest user).</span></span>  
  
-   <span data-ttu-id="25fef-136">Tener permisos de lectura en el recurso compartido de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="25fef-136">Have read permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="25fef-137">**Conectar al suscriptor**</span><span class="sxs-lookup"><span data-stu-id="25fef-137">**Connect to the Subscriber**</span></span>  
 <span data-ttu-id="25fef-138">Para las suscripciones de extracción, las conexiones con el suscriptor siempre se realizan suplantando la cuenta especificada en el cuadro de texto **Cuenta de proceso** .</span><span class="sxs-lookup"><span data-stu-id="25fef-138">For pull subscriptions, connections to the Subscriber are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="25fef-139">Para las suscripciones de inserción, debe elegir si el Agente de mezcla debe realizar las conexiones con el publicador y el distribuidor mediante la suplantación de la cuenta especificada en el cuadro de texto **Cuenta de proceso** o mediante una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25fef-139">For push subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="25fef-140">Si selecciona utilizar una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , especifique una contraseña y un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25fef-140">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25fef-141">Se recomienda usar la suplantación de la cuenta de Windows en lugar de usar una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25fef-141">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="25fef-142">La cuenta de Windows o la cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usada para la conexión con el suscriptor debe ser como mínimo miembro del rol fijo de base de datos **db_owner** en la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="25fef-142">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection to the Subscriber must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25fef-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25fef-143">See Also</span></span>  
 <span data-ttu-id="25fef-144">[Administrar inicios de sesión y contraseñas en la replicación](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="25fef-144">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="25fef-145">[Modelo de seguridad del Agente de replicación](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="25fef-145">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="25fef-146">[Replication Agents Overview](agents/replication-agents-overview.md)  (Información general sobre los agentes de replicación)</span><span class="sxs-lookup"><span data-stu-id="25fef-146">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 <span data-ttu-id="25fef-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="25fef-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="25fef-148">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="25fef-148">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
