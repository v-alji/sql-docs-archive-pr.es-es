---
title: Prácticas recomendadas de seguridad de replicación | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- security [SQL Server replication], best practices
- security [SQL Server replication], between domains
- authentication [SQL Server replication]
- Internet [SQL Server replication], security
ms.assetid: 1ab2635d-0992-4c99-b17d-041d02ec9a7c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e5918bfed52a6ed1befd81d2fdb7910062060e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661899"
---
# <a name="replication-security-best-practices"></a><span data-ttu-id="0e47d-102">Prácticas recomendadas de seguridad de replicación</span><span class="sxs-lookup"><span data-stu-id="0e47d-102">Replication Security Best Practices</span></span>
  <span data-ttu-id="0e47d-103">La replicación mueve datos en entornos distribuidos que incluyen desde intranets con un solo dominio hasta aplicaciones que tienen acceso a datos entre dominios sin confianza y por Internet.</span><span class="sxs-lookup"><span data-stu-id="0e47d-103">Replication moves data in distributed environments ranging from intranets on a single domain to applications that access data between untrusted domains and over the Internet.</span></span> <span data-ttu-id="0e47d-104">Es importante comprender el mejor método que se debe utilizar para proteger las conexiones de replicación en diferentes circunstancias.</span><span class="sxs-lookup"><span data-stu-id="0e47d-104">It is important to understand the best approach for securing replication connections under these different circumstances.</span></span>  
  
 <span data-ttu-id="0e47d-105">La siguiente información es importante para la replicación en todos los entornos:</span><span class="sxs-lookup"><span data-stu-id="0e47d-105">The following information is relevant to replication in all environments:</span></span>  
  
-   <span data-ttu-id="0e47d-106">Cifre las conexiones entre equipos en una topología de replicación mediante un método estándar, como Red privada virtual (VPN), Capa de sockets seguros (SSL) o Seguridad IP (IPSEC).</span><span class="sxs-lookup"><span data-stu-id="0e47d-106">Encrypt the connections between computers in a replication topology using an industry standard method, such as Virtual Private Networks (VPN), Secure Sockets Layer (SSL), or IP Security (IPSEC).</span></span> <span data-ttu-id="0e47d-107">Para obtener más información, vea [Habilitar conexiones cifradas en el motor de base de datos &#40;Administrador de configuración de SQL Server&#41;](../../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="0e47d-107">For more information, see [Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;](../../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span></span> <span data-ttu-id="0e47d-108">Para obtener información sobre cómo utilizar VPN y SSL para replicar datos en Internet, vea [Securing Replication Over the Internet](securing-replication-over-the-internet.md).</span><span class="sxs-lookup"><span data-stu-id="0e47d-108">For information about using VPN and SSL for replicating data over the Internet, see [Securing Replication Over the Internet](securing-replication-over-the-internet.md).</span></span>  
  
     <span data-ttu-id="0e47d-109">Si utiliza SSL para proteger las conexiones entre equipos en una topología de replicación, especifique un valor de **1** o **2** para el parámetro **EncryptionLevel** de cada agente de replicación (se recomienda utilizar el valor **2** ).</span><span class="sxs-lookup"><span data-stu-id="0e47d-109">If you use SSL to secure the connections between computers in a replication topology, specify a value of **1** or **2** for the **-EncryptionLevel** parameter of each replication agent (a value of **2** is recommended).</span></span> <span data-ttu-id="0e47d-110">El valor **1** especifica que se debe utilizar el cifrado, pero el agente no comprueba si el certificado de servidor SSL está firmado por una entidad de confianza; el valor **2** especifica que se debe comprobar el certificado.</span><span class="sxs-lookup"><span data-stu-id="0e47d-110">A value of **1** specifies that encryption is used, but the agent does not verify that the SSL server certificate is signed by a trusted issuer; a value of **2** specifies that the certificate is verified.</span></span> <span data-ttu-id="0e47d-111">Los parámetros del agente se pueden especificar en los perfiles del agente y en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0e47d-111">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="0e47d-112">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="0e47d-112">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="0e47d-113">Trabajar con perfiles del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="0e47d-113">Work with Replication Agent Profiles</span></span>](../agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="0e47d-114">Ver y modificar parámetros del símbolo del sistema de los agentes de replicación &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0e47d-114">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](../agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   [<span data-ttu-id="0e47d-115">Conceptos de los ejecutables del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="0e47d-115">Replication Agent Executables Concepts</span></span>](../concepts/replication-agent-executables-concepts.md)  
  
-   <span data-ttu-id="0e47d-116">Ejecute cada agente de replicación en una cuenta de Windows diferente y utilice Autenticación de Windows para todas las conexiones de agentes de replicación.</span><span class="sxs-lookup"><span data-stu-id="0e47d-116">Run each replication agent under a different Windows account, and use Windows Authentication for all replication agent connections.</span></span> <span data-ttu-id="0e47d-117">Para obtener más información sobre cómo especificar cuentas, vea [Manage Logins and Passwords in Replication](identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) (Administrar inicios de sesión y contraseñas en la replicación).</span><span class="sxs-lookup"><span data-stu-id="0e47d-117">For more information about specifying accounts, see [Manage Logins and Passwords in Replication](identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication).</span></span>  
  
-   <span data-ttu-id="0e47d-118">Conceda solamente los permisos requeridos a cada agente.</span><span class="sxs-lookup"><span data-stu-id="0e47d-118">Grant only the required permissions to each agent.</span></span> <span data-ttu-id="0e47d-119">Para obtener más información, vea la sección sobre los permisos necesarios para los agentes en el tema [Replication Agent Security Model](replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="0e47d-119">For more information, see the "Permissions Required by Agents" section of [Replication Agent Security Model](replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="0e47d-120">Asegúrese de que las cuentas del Agente de mezcla y el Agente de distribución están en la lista de acceso a la publicación (PAL).</span><span class="sxs-lookup"><span data-stu-id="0e47d-120">Ensure all Merge Agent and Distribution Agent accounts are in the publication access list (PAL).</span></span> <span data-ttu-id="0e47d-121">Para obtener más información, vea [Proteger el publicador](secure-the-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="0e47d-121">For more information, see [Secure the Publisher](secure-the-publisher.md).</span></span>  
  
-   <span data-ttu-id="0e47d-122">Siga el principio de privilegios mínimos permitiendo que las cuentas de la PAL solo tengan los permisos que necesitan para realizar tareas de replicación.</span><span class="sxs-lookup"><span data-stu-id="0e47d-122">Follow the principle of least privilege by allowing accounts in the PAL only the permissions they need to perform replication tasks.</span></span> <span data-ttu-id="0e47d-123">No agregue los inicios de sesión a ningún rol fijo de servidor que no sea necesario para la replicación.</span><span class="sxs-lookup"><span data-stu-id="0e47d-123">Do not add the logins to any fixed server roles that are not required for replication.</span></span>  
  
-   <span data-ttu-id="0e47d-124">Configure el recurso compartido de instantánea para permitir acceso de lectura a todos los agentes de mezcla y agentes de distribución.</span><span class="sxs-lookup"><span data-stu-id="0e47d-124">Configure the snapshot share to allow read access by all Merge Agents and Distribution Agents.</span></span> <span data-ttu-id="0e47d-125">En el caso de instantáneas para publicaciones mediante filtros con parámetros, asegúrese de que cada carpeta está configurada para permitir acceso solo a las cuentas de Agente de mezcla correctas.</span><span class="sxs-lookup"><span data-stu-id="0e47d-125">In the case of snapshots for publications with parameterized filters, ensure that each folder is configured to allow access only to the appropriate Merge Agent accounts.</span></span>  
  
-   <span data-ttu-id="0e47d-126">Configure el recurso compartido de instantánea para permitir acceso de escritura al Agente de instantánea.</span><span class="sxs-lookup"><span data-stu-id="0e47d-126">Configure the snapshot share to allow write access by the Snapshot Agent.</span></span>  
  
-   <span data-ttu-id="0e47d-127">Si utiliza suscripciones de extracción, use un recurso de red compartido en vez de una ruta de acceso local para la carpeta de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="0e47d-127">If you use pull subscriptions, use a network share rather than a local path for the snapshot folder.</span></span>  
  
 <span data-ttu-id="0e47d-128">Si la topología de replicación incluye equipos que no se encuentran en el mismo dominio o están en dominios que no tienen relaciones de confianza entre sí, puede utilizar Autenticación de Windows o Autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para las conexiones realizadas por agentes (Para obtener más información acerca de los dominios, vea la documentación de Windows).</span><span class="sxs-lookup"><span data-stu-id="0e47d-128">If your replication topology includes computers that are not in the same domain or are in domains that do not have trust relationships with each other, you can use Windows Authentication or [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication for the connections made by agents (For more information about domains, see the Windows documentation).</span></span> <span data-ttu-id="0e47d-129">Para obtener la máxima seguridad se recomienda que utilice Autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="0e47d-129">It is recommended as a security best practice that you use Windows Authentication.</span></span>  
  
-   <span data-ttu-id="0e47d-130">Para utilizar Autenticación de Windows:</span><span class="sxs-lookup"><span data-stu-id="0e47d-130">To use Windows Authentication:</span></span>  
  
    -   <span data-ttu-id="0e47d-131">Agregue una cuenta de Windows local (no una cuenta de dominio) para cada agente en los nodos adecuados (utilice el mismo nombre y contraseña en cada nodo).</span><span class="sxs-lookup"><span data-stu-id="0e47d-131">Add a local Windows account (not a domain account) for each agent at the appropriate nodes (use the same name and password at each node).</span></span> <span data-ttu-id="0e47d-132">Por ejemplo, el Agente de distribución para una suscripción de inserción se ejecuta en el distribuidor y realiza conexiones al distribuidor y suscriptor.</span><span class="sxs-lookup"><span data-stu-id="0e47d-132">For example, the Distribution Agent for a push subscription runs at the Distributor and makes connections to the Distributor and Subscriber.</span></span> <span data-ttu-id="0e47d-133">La cuenta de Windows para el Agente de distribución debe agregarse al distribuidor y suscriptor.</span><span class="sxs-lookup"><span data-stu-id="0e47d-133">The Windows account for the Distribution Agent should be added to the Distributor and Subscriber.</span></span>  
  
    -   <span data-ttu-id="0e47d-134">Asegúrese de que un determinado agente (por ejemplo, el Agente de distribución de una suscripción) se ejecuta con la misma cuenta en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="0e47d-134">Ensure that a given agent (for example the Distribution Agent for a subscription) runs under the same account at each computer.</span></span>  
  
-   <span data-ttu-id="0e47d-135">Para utilizar Autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="0e47d-135">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication:</span></span>  
  
    -   <span data-ttu-id="0e47d-136">Agregue una cuenta de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para cada agente en los nodos adecuados (utilice el mismo nombre y contraseña en cada nodo).</span><span class="sxs-lookup"><span data-stu-id="0e47d-136">Add a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] account for each agent at the appropriate nodes (use the same account name and password at each node).</span></span> <span data-ttu-id="0e47d-137">Por ejemplo, el Agente de distribución para una suscripción de inserción se ejecuta en el distribuidor y realiza conexiones al distribuidor y suscriptor.</span><span class="sxs-lookup"><span data-stu-id="0e47d-137">For example, the Distribution Agent for a push subscription runs at the Distributor and makes connections to the Distributor and Subscriber.</span></span> <span data-ttu-id="0e47d-138">La cuenta de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para el Agente de distribución debe agregarse al distribuidor y al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="0e47d-138">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] account for the Distribution Agent should be added to the Distributor and Subscriber.</span></span>  
  
    -   <span data-ttu-id="0e47d-139">Asegúrese de que un determinado agente (por ejemplo, el Agente de distribución de una suscripción) realiza conexiones con la misma cuenta en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="0e47d-139">Ensure that a given agent (for example the Distribution Agent for a subscription) makes connections under the same account at each computer.</span></span>  
  
    -   <span data-ttu-id="0e47d-140">En situaciones que requieren Autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , el acceso a recursos compartidos de instantáneas UNC normalmente no está disponible (por ejemplo, el acceso puede estar bloqueado por un firewall).</span><span class="sxs-lookup"><span data-stu-id="0e47d-140">In situations that require [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, access to UNC snapshot shares is often not available (for example access might be blocked by a firewall).</span></span> <span data-ttu-id="0e47d-141">En este caso, puede transferir la instantánea a los suscriptores a través del protocolo de transferencia de archivos (FTP).</span><span class="sxs-lookup"><span data-stu-id="0e47d-141">In this case, you can transfer the snapshot to Subscribers through file transfer protocol (FTP).</span></span> <span data-ttu-id="0e47d-142">Para obtener más información, vea [Transferir instantáneas mediante FTP](../transfer-snapshots-through-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="0e47d-142">For more information, see [Transfer Snapshots Through FTP](../transfer-snapshots-through-ftp.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e47d-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e47d-143">See Also</span></span>  
 <span data-ttu-id="0e47d-144">[Habilitar conexiones cifradas en el motor de base de datos &#40;Administrador de configuración de SQL Server&#41;](../../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="0e47d-144">[Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;](../../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md) </span></span>  
 <span data-ttu-id="0e47d-145">[Replicación a través de Internet](../replication-over-the-internet.md) </span><span class="sxs-lookup"><span data-stu-id="0e47d-145">[Replication over the Internet](../replication-over-the-internet.md) </span></span>  
 <span data-ttu-id="0e47d-146">[Proteger el suscriptor](secure-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="0e47d-146">[Secure the Subscriber](secure-the-subscriber.md) </span></span>  
 <span data-ttu-id="0e47d-147">[Proteger el distribuidor](secure-the-distributor.md) </span><span class="sxs-lookup"><span data-stu-id="0e47d-147">[Secure the Distributor](secure-the-distributor.md) </span></span>  
 <span data-ttu-id="0e47d-148">[Proteger el publicador](secure-the-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="0e47d-148">[Secure the Publisher](secure-the-publisher.md) </span></span>  
 [<span data-ttu-id="0e47d-149">Seguridad de Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0e47d-149">SQL Server Replication Security</span></span>](view-and-modify-replication-security-settings.md)  
  
  