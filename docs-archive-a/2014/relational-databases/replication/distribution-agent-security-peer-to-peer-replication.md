---
title: Seguridad del Agente de distribución (replicación punto a punto) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.p2pwizard.DA.f1
ms.assetid: def6bf26-c640-4caf-ad30-05d1e649541d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72b5a52fbb3ddc11d0ea6f2c0b26786463e08eaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663391"
---
# <a name="distribution-agent-security-peer-to-peer-replication"></a><span data-ttu-id="dd755-102">Seguridad del Agente de distribución (replicación punto a punto)</span><span class="sxs-lookup"><span data-stu-id="dd755-102">Distribution Agent Security (Peer-to-Peer Replication)</span></span>
  <span data-ttu-id="dd755-103">La página **Seguridad del Agente de distribución** permite especificar las cuentas con las que el Agente de distribución se ejecuta y realiza conexiones con los equipos de una topología punto a punto.</span><span class="sxs-lookup"><span data-stu-id="dd755-103">The **Distribution Agent Security** page allows you to specify the accounts under which the Distribution Agent runs and makes connections to the computers in a peer-to-peer topology.</span></span> <span data-ttu-id="dd755-104">Para obtener información sobre los permisos requeridos por los agentes y las prácticas recomendadas que se aplican a la seguridad de replicación, vea [Modelo de seguridad del Agente de replicación](security/replication-agent-security-model.md) y [Prácticas recomendadas de seguridad de replicación](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="dd755-104">For information on permissions required by agents and best practices for replication security, see [Replication Agent Security Model](security/replication-agent-security-model.md) and [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd755-105">Si el Agente de distribución de una suscripción ya se ha configurado en una ejecución anterior de este asistente, no se pueden cambiar las credenciales que utiliza en este asistente.</span><span class="sxs-lookup"><span data-stu-id="dd755-105">If the Distribution Agent for a subscription has already been configured in a previous run of this wizard, you cannot change the credentials it uses in this wizard.</span></span> <span data-ttu-id="dd755-106">Si especifica credenciales nuevas, se omitirán.</span><span class="sxs-lookup"><span data-stu-id="dd755-106">If you specify new credentials, they are ignored.</span></span> <span data-ttu-id="dd755-107">Para cambiar las credenciales, utilice el cuadro de diálogo **Propiedades de suscripción** .</span><span class="sxs-lookup"><span data-stu-id="dd755-107">To change credentials, use the **Subscription Properties** dialog box.</span></span> <span data-ttu-id="dd755-108">Para más información, consulte [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="dd755-108">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dd755-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="dd755-109">Options</span></span>  
 <span data-ttu-id="dd755-110">Haga clic en el botón de propiedades ( **...** ) de la fila de cada suscriptor para tener acceso al cuadro de diálogo **Seguridad del Agente de distribución** .</span><span class="sxs-lookup"><span data-stu-id="dd755-110">Click the properties button (**...**) in the row for each Subscriber to access the **Distribution Agent Security** dialog box.</span></span> <span data-ttu-id="dd755-111">Haga clic en **Ayuda** en el cuadro de diálogo **Seguridad del Agente de distribución** que se muestra para obtener más información sobre los permisos requeridos para las cuentas utilizadas por los agentes.</span><span class="sxs-lookup"><span data-stu-id="dd755-111">Click **Help** on the **Distribution Agent Security** dialog box that is launched for more information on the permissions required for accounts used by the agents.</span></span>  
  
 <span data-ttu-id="dd755-112">Una vez especificadas las opciones en uno de los cuadros de diálogo, la información de conexión del suscriptor aparece en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="dd755-112">After settings have been entered in one of the dialog boxes, connection information for the Subscriber is displayed in the grid.</span></span>  
  
 <span data-ttu-id="dd755-113">**Agente para el suscriptor**</span><span class="sxs-lookup"><span data-stu-id="dd755-113">**Agent for Subscriber**</span></span>  
 <span data-ttu-id="dd755-114">El nombre de cada elemento del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="dd755-114">The name of each peer.</span></span>  
  
 <span data-ttu-id="dd755-115">**Base de datos del mismo nivel**</span><span class="sxs-lookup"><span data-stu-id="dd755-115">**Peer Database**</span></span>  
 <span data-ttu-id="dd755-116">La base de datos del mismo nivel que servirá tanto de base de datos de publicaciones como de base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="dd755-116">The database at the peer that will serve as both a publication database and subscription database.</span></span>  
  
 <span data-ttu-id="dd755-117">**Conexión al distribuidor**</span><span class="sxs-lookup"><span data-stu-id="dd755-117">**Connection to Distributor**</span></span>  
 <span data-ttu-id="dd755-118">Contexto en el que se realiza la conexión al distribuidor.</span><span class="sxs-lookup"><span data-stu-id="dd755-118">The context under which the connection to the Distributor is made.</span></span> <span data-ttu-id="dd755-119">Las conexiones locales se realizan siempre utilizando el contexto de la cuenta de Windows con la que se ejecuta el agente.</span><span class="sxs-lookup"><span data-stu-id="dd755-119">Local connections are always made using the context of the Windows account under which the agent runs.</span></span> <span data-ttu-id="dd755-120">Este asistente crea suscripciones de inserción (la conexión local es la conexión al distribuidor), por lo que este campo muestra siempre: **Impersonate "\<Domain>\\<Login\>"** o **Impersonate "\<Computer>\\<Login\>"** .</span><span class="sxs-lookup"><span data-stu-id="dd755-120">This wizard creates push subscriptions (the local connection is the connection to the Distributor), so this field will always display: **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span>  
  
 <span data-ttu-id="dd755-121">**Conexión al suscriptor**</span><span class="sxs-lookup"><span data-stu-id="dd755-121">**Connection to Subscriber**</span></span>  
 <span data-ttu-id="dd755-122">Contexto en el que se realiza la conexión al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="dd755-122">The context under which the connection to the Subscriber is made.</span></span> <span data-ttu-id="dd755-123">La conexión se puede realizar utilizando el contexto de una cuenta de Windows con la que se ejecute el agente o en el contexto de un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd755-123">The connection can be made using the context of the Windows account under which the agent runs or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="dd755-124">En el campo se muestra uno de los siguientes: **Use login "\<Login>"** , **Impersonate "\<Domain>\\<Login\>"** o **Impersonate "\<Computer>\\<Login\>"** .</span><span class="sxs-lookup"><span data-stu-id="dd755-124">The field displays one of the following: **Use login '\<Login>'**, **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="dd755-125">recomienda que todas las conexiones se realicen utilizando el contexto de la cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="dd755-125">recommends that all connections be made using the context of the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd755-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd755-126">See Also</span></span>  
 <span data-ttu-id="dd755-127">[Administrar una topología punto a punto &#40;programación de la replicación con Transact-SQL&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span><span class="sxs-lookup"><span data-stu-id="dd755-127">[Administer a Peer-to-Peer Topology &#40;Replication Transact-SQL Programming&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span></span>  
 [<span data-ttu-id="dd755-128">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="dd755-128">Peer-to-Peer Transactional Replication</span></span>](transactional/peer-to-peer-transactional-replication.md)  
  
  
