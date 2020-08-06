---
title: Seguridad del Agente de instantáneas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.SSA.f1
helpviewer_keywords:
- Snapshot Agent Security dialog box
ms.assetid: 64e84c67-acc6-4906-98d4-3451767363fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 288dc294b7ace9ea5cb098c8deec53c3ae4569a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677537"
---
# <a name="snapshot-agent-security"></a><span data-ttu-id="1ed59-102">Seguridad del Agente de instantáneas</span><span class="sxs-lookup"><span data-stu-id="1ed59-102">Snapshot Agent Security</span></span>
  <span data-ttu-id="1ed59-103">El cuadro de diálogo **Seguridad del Agente de instantáneas** le permite especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ed59-103">The **Snapshot Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="1ed59-104">La cuenta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows bajo la cual el Agente de instantáneas se ejecuta en el Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="1ed59-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Snapshot Agent runs at the Distributor.</span></span> <span data-ttu-id="1ed59-105">La cuenta de Windows se denomina también *cuenta de proceso*porque el proceso del agente se ejecuta con dicha cuenta.</span><span class="sxs-lookup"><span data-stu-id="1ed59-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="1ed59-106">El contexto bajo el cual el Agente de instantáneas establece conexiones con el publicador de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ed59-106">The context under which the Snapshot Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="1ed59-107">La conexión se puede realizar suplantando la cuenta de Windows o en el contexto de la cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se especifique.</span><span class="sxs-lookup"><span data-stu-id="1ed59-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1ed59-108">El Agente de instantáneas establece conexiones con el publicador aun cuando el publicador y el distribuidor se encuentren en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="1ed59-108">The Snapshot Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="1ed59-109">El Agente de instantáneas también establece conexiones con el distribuidor; estas conexiones siempre se establecen suplantando la cuenta de Windows bajo la cual se ejecuta el agente.</span><span class="sxs-lookup"><span data-stu-id="1ed59-109">The Snapshot Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="1ed59-110">Para publicadores de Oracle, especifique el contexto bajo el cual el Agente de instantáneas se conecta con el publicador en el cuadro de diálogo **Propiedades del publicador** (disponible desde el cuadro de diálogo **Propiedades del distribuidor** ).</span><span class="sxs-lookup"><span data-stu-id="1ed59-110">For Oracle Publishers, specify the context under which the Snapshot Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="1ed59-111">Para más información, consulte [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1ed59-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="1ed59-112">Todas las cuentas deben ser válidas y se debe especificar la contraseña correcta para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="1ed59-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="1ed59-113">Las cuentas y las contraseñas se validan cuando se ejecuta el agente.</span><span class="sxs-lookup"><span data-stu-id="1ed59-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1ed59-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="1ed59-114">Options</span></span>  
 <span data-ttu-id="1ed59-115">**Cuenta de proceso**</span><span class="sxs-lookup"><span data-stu-id="1ed59-115">**Process account**</span></span>  
 <span data-ttu-id="1ed59-116">Especifique una cuenta de Windows bajo la cual el Agente de instantáneas se ejecuta en el Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="1ed59-116">Enter a Windows account under which the Snapshot Agent runs at the Distributor.</span></span> <span data-ttu-id="1ed59-117">La cuenta de Windows que especifique debe cumplir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ed59-117">The Windows account you specify must:</span></span>  
  
-   <span data-ttu-id="1ed59-118">Ser como mínimo miembro del rol fijo de base de datos **db_owner** en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="1ed59-118">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
-   <span data-ttu-id="1ed59-119">Tener permisos de escritura en el recurso compartido de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="1ed59-119">Have write permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="1ed59-120">**Contraseña** y **Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="1ed59-120">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="1ed59-121">Escriba la contraseña de la cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="1ed59-121">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="1ed59-122">**Conectar al publicador**</span><span class="sxs-lookup"><span data-stu-id="1ed59-122">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="1ed59-123">Seleccione si el Agente de instantáneas debe establecer conexiones con el publicador mediante la suplantación de la cuenta especificada en el cuadro de texto **Cuenta de proceso** o utilizando una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ed59-123">Select whether the Snapshot Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="1ed59-124">Si selecciona utilizar una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , especifique una contraseña y un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ed59-124">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ed59-125">Se recomienda usar la suplantación de la cuenta de Windows en lugar de usar una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ed59-125">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="1ed59-126">La cuenta de Windows o la cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizada para conectarse debe ser miembro, como mínimo, del rol fijo de base de datos **db_owner** de la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="1ed59-126">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed59-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ed59-127">See Also</span></span>  
 <span data-ttu-id="1ed59-128">[Administrar inicios de sesión y contraseñas en la replicación](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="1ed59-128">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="1ed59-129">[Modelo de seguridad del Agente de replicación](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="1ed59-129">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="1ed59-130">[Replication Agents Overview](agents/replication-agents-overview.md)  (Información general sobre los agentes de replicación)</span><span class="sxs-lookup"><span data-stu-id="1ed59-130">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="1ed59-131">Procedimientos recomendados de seguridad de replicación</span><span class="sxs-lookup"><span data-stu-id="1ed59-131">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
