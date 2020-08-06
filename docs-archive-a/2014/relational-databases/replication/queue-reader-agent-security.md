---
title: Seguridad del Agente de lectura de cola | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.QRA.f1
helpviewer_keywords:
- Queue Reader Agent Security dialog box
ms.assetid: 77938da0-2afd-4455-8826-f4a6a9440cb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 22a5e5751184b626ab1af86f01782a42028b5ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676468"
---
# <a name="queue-reader-agent-security"></a><span data-ttu-id="abca9-102">Seguridad del Agente de lectura de cola</span><span class="sxs-lookup"><span data-stu-id="abca9-102">Queue Reader Agent Security</span></span>
  <span data-ttu-id="abca9-103">El cuadro de diálogo **Seguridad del Agente de lectura de cola** le permitirá especificar la cuenta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con la que se ejecutará el Agente de lectura de cola y establecerá las conexiones locales al distribuidor.</span><span class="sxs-lookup"><span data-stu-id="abca9-103">The **Queue Reader Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Queue Reader Agent runs and makes local connections to the Distributor.</span></span> <span data-ttu-id="abca9-104">El agente se conecta al publicador a través de la cuenta especificada en el cuadro de diálogo **Propiedades del publicador** (disponible en el cuadro de diálogo **Propiedades del distribuidor** ); el agente se conectará al suscriptor a través del mismo contexto que el Agente de distribución para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="abca9-104">The agent connects to the Publisher using the account specified in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box); the agent connects to the Subscriber using the same context as the Distribution Agent for the subscription.</span></span> <span data-ttu-id="abca9-105">Para más información, consulte [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="abca9-105">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="abca9-106">La cuenta deberá ser válida y deberá especificarse la contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="abca9-106">The account must be valid with the correct password specified.</span></span> <span data-ttu-id="abca9-107">Las cuentas y las contraseñas se validan cuando se ejecuta el agente.</span><span class="sxs-lookup"><span data-stu-id="abca9-107">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="abca9-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="abca9-108">Options</span></span>  
 <span data-ttu-id="abca9-109">**Cuenta de proceso**</span><span class="sxs-lookup"><span data-stu-id="abca9-109">**Process account**</span></span>  
 <span data-ttu-id="abca9-110">Escriba la cuenta de Windows con la que se ejecutará el Agente de lectura de cola en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="abca9-110">Enter a Windows account under which the Queue Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="abca9-111">La cuenta de Windows que especifique debe ser, como mínimo, miembro del rol fijo de base de datos **db_owner** de la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="abca9-111">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="abca9-112">**Contraseña** y **Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="abca9-112">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="abca9-113">Escriba la contraseña de la cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="abca9-113">Enter the password for the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abca9-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="abca9-114">See Also</span></span>  
 <span data-ttu-id="abca9-115">[Administrar inicios de sesión y contraseñas en la replicación](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="abca9-115">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="abca9-116">[Modelo de seguridad del Agente de replicación](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="abca9-116">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="abca9-117">[Replication Agents Overview](agents/replication-agents-overview.md)  (Información general sobre los agentes de replicación)</span><span class="sxs-lookup"><span data-stu-id="abca9-117">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="abca9-118">Procedimientos recomendados de seguridad de replicación</span><span class="sxs-lookup"><span data-stu-id="abca9-118">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
