---
title: Seguridad del Agente de registro del LOG | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.LRA.f1
helpviewer_keywords:
- Log Reader Agent Security dialog box
ms.assetid: d6981e74-ddb8-41b8-9ea1-56c2ece63b8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4be41aa9135e20a334616b9cb9d76a773f8d0e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749227"
---
# <a name="log-reader-agent-security"></a><span data-ttu-id="6e7d8-102">Seguridad del Agente de registro del LOG</span><span class="sxs-lookup"><span data-stu-id="6e7d8-102">Log Reader Agent Security</span></span>
  <span data-ttu-id="6e7d8-103">El cuadro de diálogo **Seguridad del Agente de registro del LOG** permite especificar:</span><span class="sxs-lookup"><span data-stu-id="6e7d8-103">The **Log Reader Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="6e7d8-104">La cuenta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con la que se ejecuta el Agente de registro del LOG en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="6e7d8-105">La cuenta de Windows se denomina también *cuenta de proceso*porque el proceso del agente se ejecuta con dicha cuenta.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="6e7d8-106">El contexto en el que el Agente de registro del LOG realiza conexiones al publicador de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e7d8-106">The context under which the Log Reader Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="6e7d8-107">La conexión se puede realizar suplantando la cuenta de Windows o en el contexto de la cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se especifique.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6e7d8-108">El Agente de registro del LOG realiza conexiones al publicador incluso cuando el publicador y el distribuidor se encuentran en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-108">The Log Reader Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="6e7d8-109">El Agente de registro del LOG también realiza conexiones al distribuidor; dichas conexiones se llevan a cabo siempre suplantando la cuenta de Windows con la que se ejecuta el agente.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-109">The Log Reader Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="6e7d8-110">Para los publicadores de Oracle, especifique el contexto en que el Agente de registro del LOG se conecta al publicador en el cuadro de diálogo **Propiedades del publicador** (disponible en el cuadro de diálogo **Propiedades del distribuidor** ).</span><span class="sxs-lookup"><span data-stu-id="6e7d8-110">For Oracle Publishers, specify the context under which the Log Reader Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="6e7d8-111">Para más información, consulte [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6e7d8-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="6e7d8-112">Todas las cuentas deben ser válidas y se debe especificar la contraseña correcta para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="6e7d8-113">Las cuentas y las contraseñas se validan cuando se ejecuta el agente.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6e7d8-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="6e7d8-114">Options</span></span>  
 <span data-ttu-id="6e7d8-115">**Cuenta de proceso**</span><span class="sxs-lookup"><span data-stu-id="6e7d8-115">**Process account**</span></span>  
 <span data-ttu-id="6e7d8-116">Indique la cuenta de Windows con la que se ejecuta el Agente de registro del LOG en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-116">Enter a Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="6e7d8-117">La cuenta de Windows que especifique debe ser, como mínimo, miembro del rol fijo de base de datos **db_owner** de la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-117">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="6e7d8-118">**Contraseña** y **Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="6e7d8-118">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="6e7d8-119">Escriba la contraseña de la cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-119">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="6e7d8-120">**Conectar al publicador**</span><span class="sxs-lookup"><span data-stu-id="6e7d8-120">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="6e7d8-121">Seleccione si el Agente de registro del LOG debe realizar conexiones al publicador suplantando la cuenta especificada en el cuadro de texto **Cuenta de proceso** o utilizando una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e7d8-121">Select whether the Log Reader Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="6e7d8-122">Si selecciona utilizar una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , especifique una contraseña y un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e7d8-122">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="6e7d8-123">recomienda que se seleccione la opción de suplantar la cuenta de Windows en lugar de utilizar una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e7d8-123">recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="6e7d8-124">La cuenta de Windows o la cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizada para conectarse debe ser miembro, como mínimo, del rol fijo de base de datos **db_owner** de la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="6e7d8-124">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e7d8-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e7d8-125">See Also</span></span>  
 <span data-ttu-id="6e7d8-126">[Administrar inicios de sesión y contraseñas en la replicación](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="6e7d8-126">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="6e7d8-127">[Modelo de seguridad del Agente de replicación](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="6e7d8-127">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="6e7d8-128">[Replication Agents Overview](agents/replication-agents-overview.md)  (Información general sobre los agentes de replicación)</span><span class="sxs-lookup"><span data-stu-id="6e7d8-128">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="6e7d8-129">Procedimientos recomendados de seguridad de replicación</span><span class="sxs-lookup"><span data-stu-id="6e7d8-129">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
