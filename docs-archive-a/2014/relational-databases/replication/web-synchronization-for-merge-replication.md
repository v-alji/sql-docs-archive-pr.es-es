---
title: Sincronización web para la replicación de mezcla | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication synchronization [SQL Server replication]
- Internet [SQL Server replication], synchronization
- synchronization [SQL Server replication], Web Synchronization
- Web publishing [SQL Server replication], synchronization
- Web synchronization, about
- Web synchronization
ms.assetid: 84785aba-b2c1-4821-9e9d-a363c73dcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7bf5a6f77d593a90508a0b69d02f8c0db04407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676466"
---
# <a name="web-synchronization-for-merge-replication"></a><span data-ttu-id="db5ae-102">Sincronización web para la replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="db5ae-102">Web Synchronization for Merge Replication</span></span>
  <span data-ttu-id="db5ae-103">La sincronización web para la replicación de mezcla permite replicar datos utilizando el protocolo HTTPS y es útil en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="db5ae-103">Web synchronization for merge replication lets you replicate data by using the HTTPS protocol, and is useful for the following scenarios:</span></span>

-   <span data-ttu-id="db5ae-104">Sincronizar datos de usuarios móviles a través de Internet</span><span class="sxs-lookup"><span data-stu-id="db5ae-104">Synchronizing data from mobile users over the Internet.</span></span>

-   <span data-ttu-id="db5ae-105">Sincronización de datos entre bases de datos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a través de un firewall corporativo.</span><span class="sxs-lookup"><span data-stu-id="db5ae-105">Synchronizing data between [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases across a corporate firewall.</span></span>

 <span data-ttu-id="db5ae-106">Por ejemplo, un representante de ventas puede utilizar la sincronización web durante sus viajes.</span><span class="sxs-lookup"><span data-stu-id="db5ae-106">For example, a traveling sales representative can use Web synchronization.</span></span> <span data-ttu-id="db5ae-107">La empresa [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)]tiene representantes de ventas que viajan para visitar varias tiendas y proveedores de su región.</span><span class="sxs-lookup"><span data-stu-id="db5ae-107">The company, [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], has sales representatives that travel to various stores and suppliers throughout their regions.</span></span> <span data-ttu-id="db5ae-108">En viajes más largos, los representantes se hospedan en hoteles y necesitan una manera cómoda de cargar datos de ventas y descargar cualquier actualización de productos al final de cada día.</span><span class="sxs-lookup"><span data-stu-id="db5ae-108">On longer trips the representatives stay in hotels and need a convenient way to upload sales data and download any product updates at the end of each day.</span></span>

 <span data-ttu-id="db5ae-109">El departamento de TI de [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] ha configurado cada equipo portátil con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y ha habilitado la replicación de mezcla para que utilice la sincronización web.</span><span class="sxs-lookup"><span data-stu-id="db5ae-109">The [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] IT department has configured each portable computer with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and has enabled merge replication to use Web synchronization.</span></span> <span data-ttu-id="db5ae-110">El Agente de mezcla de cada equipo portátil tiene una dirección URL de Internet que apunta a los componentes de replicación instalados en un equipo en el que se ejecuta [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="db5ae-110">The Merge Agent on each portable computer has an Internet URL that points to the replication components that are installed on a computer that is running [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS).</span></span> <span data-ttu-id="db5ae-111">Estos componentes sincronizan el suscriptor con el publicador.</span><span class="sxs-lookup"><span data-stu-id="db5ae-111">These components synchronize the Subscriber with the Publisher.</span></span> <span data-ttu-id="db5ae-112">Ahora cada representante se puede conectar a través de cualquier conexión de Internet disponible sin utilizar una conexión remota de acceso telefónico y puede cargar y descargar los datos que desee.</span><span class="sxs-lookup"><span data-stu-id="db5ae-112">Each representative can now connect through any available Internet connection without using a remote dial-up connection, and can upload and download the appropriate data.</span></span> <span data-ttu-id="db5ae-113">La conexión de Internet utiliza SSL (Capa de sockets seguros), por lo que no es necesaria una red privada virtual (VPN).</span><span class="sxs-lookup"><span data-stu-id="db5ae-113">The Internet connection uses Secure Sockets Layer (SSL); therefore, a virtual private network (VPN) is not required.</span></span>

 <span data-ttu-id="db5ae-114">Para obtener información sobre cómo configurar los componentes necesarios para la sincronización web, consulte [Configurar sincronización web](configure-web-synchronization.md), [Configurar IIS para la sincronización web](configure-iis-for-web-synchronization.md) y [Configurar IIS 7 para la sincronización web](configure-iis-7-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="db5ae-114">For information about how to configure the components that are required for Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md), [Configure IIS for Web Synchronization](configure-iis-for-web-synchronization.md), and [Configure IIS 7 for Web Synchronization](configure-iis-7-for-web-synchronization.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="db5ae-115">La sincronización web está diseñada para sincronizar datos con equipos portátiles, dispositivos de mano y otros clientes.</span><span class="sxs-lookup"><span data-stu-id="db5ae-115">Web synchronization is designed for synchronizing data with portable computers, handheld devices, and other clients.</span></span> <span data-ttu-id="db5ae-116">La sincronización web no está concebida para aplicaciones de servidor a servidor con grandes volúmenes de datos.</span><span class="sxs-lookup"><span data-stu-id="db5ae-116">Web synchronization is not intended for high-volume server-to-server applications.</span></span>

## <a name="overview-of-how-web-synchronization-works"></a><span data-ttu-id="db5ae-117">Información general sobre el funcionamiento de la sincronización web</span><span class="sxs-lookup"><span data-stu-id="db5ae-117">Overview of How Web Synchronization Works</span></span>
 <span data-ttu-id="db5ae-118">Cuando se utiliza la sincronización web, las actualizaciones en el suscriptor se empaquetan y envían como un mensaje XML al equipo en el que se ejecuta IIS mediante el protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="db5ae-118">When Web synchronization is used, updates at the Subscriber are packaged and sent as an XML message to the computer that is running IIS by using the HTTPS protocol.</span></span> <span data-ttu-id="db5ae-119">El equipo en el que se ejecuta IIS envía los comandos al publicador en formato binario (normalmente mediante TCP/IP).</span><span class="sxs-lookup"><span data-stu-id="db5ae-119">The computer that is running IIS then sends the commands to the Publisher in a binary format, typically by using TCP/IP.</span></span> <span data-ttu-id="db5ae-120">Las actualizaciones en el publicador se envían al equipo en el que se ejecuta IIS y después se empaquetan como un mensaje XML para su envío al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="db5ae-120">Updates at the Publisher are sent to the computer that is running IIS and then packaged as an XML message for delivery to the Subscriber.</span></span>

 <span data-ttu-id="db5ae-121">En la siguiente ilustración se muestran algunos de los componentes que participan en la sincronización web para la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="db5ae-121">The following illustration shows some of the components that are involved in Web synchronization for merge replication.</span></span>

 <span data-ttu-id="db5ae-122">![Componentes y flujo de datos de sincronización web](media/web-sync01.gif "Componentes y flujo de datos de sincronización web")</span><span class="sxs-lookup"><span data-stu-id="db5ae-122">![Web synchronization components and data flow](media/web-sync01.gif "Web synchronization components and data flow")</span></span>

 <span data-ttu-id="db5ae-123">La sincronización web es una opción exclusiva de las suscripciones de extracción, por lo que un Agente de mezcla se ejecutará siempre en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="db5ae-123">Web synchronization is an option only for pull subscriptions; therefore, a Merge Agent will always run on the Subscriber.</span></span> <span data-ttu-id="db5ae-124">Este Agente de mezcla puede ser el Agente de mezcla estándar, el control ActiveX del Agente de mezcla o de una aplicación que proporcione sincronización a través de Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="db5ae-124">This Merge Agent can be the standard Merge Agent, the Merge Agent ActiveX control, or an application that provides synchronization through Replication Management Objects (RMO).</span></span> <span data-ttu-id="db5ae-125">Para especificar la ubicación del equipo en el que se ejecuta IIS, utilice el parámetro **-InternetUrl** para el agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="db5ae-125">To specify the location of the computer that is running IIS, use the **-InternetUrl** parameter for the Merge Agent.</span></span>

 <span data-ttu-id="db5ae-126">La Escucha de replicación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (Replisapi.dll) se configura en el equipo en el que se ejecuta IIS y es responsable de controlar los mensajes que se envían al servidor desde el publicador y los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="db5ae-126">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener (Replisapi.dll) is configured on the computer that is running IIS and is responsible for handling messages that are sent to the server from the Publisher and Subscribers.</span></span> <span data-ttu-id="db5ae-127">Cada nodo de la topología controla el flujo de datos XML con el Reconciliador de replicación de mezcla (Replrec.dll).</span><span class="sxs-lookup"><span data-stu-id="db5ae-127">Each node in the topology handles the XML data stream by using the Merge Replication Reconciler (Replrec.dll).</span></span>

 <span data-ttu-id="db5ae-128">Se requiere[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o una versión posterior para todos los equipos que participen en la sincronización web.</span><span class="sxs-lookup"><span data-stu-id="db5ae-128">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version is required for all computers that participate in Web synchronization.</span></span>

### <a name="synchronization-process"></a><span data-ttu-id="db5ae-129">Proceso de sincronización</span><span class="sxs-lookup"><span data-stu-id="db5ae-129">Synchronization Process</span></span>
 <span data-ttu-id="db5ae-130">Durante la sincronización se llevan a cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="db5ae-130">The following steps occur during synchronization:</span></span>

1.  <span data-ttu-id="db5ae-131">El Agente de mezcla se inicia en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="db5ae-131">The Merge Agent is started at the Subscriber.</span></span> <span data-ttu-id="db5ae-132">El agente realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="db5ae-132">The agent does the following:</span></span>

    1.  <span data-ttu-id="db5ae-133">Establece una conexión SQL con la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="db5ae-133">Makes an SQL connection to the subscription database.</span></span>

    2.  <span data-ttu-id="db5ae-134">Extrae cualquier cambio de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="db5ae-134">Extracts any changes from the database.</span></span>

    3.  <span data-ttu-id="db5ae-135">Realiza una solicitud HTTPS al equipo en el que se ejecuta IIS.</span><span class="sxs-lookup"><span data-stu-id="db5ae-135">Makes an HTTPS request to the computer that is running IIS.</span></span>

    4.  <span data-ttu-id="db5ae-136">Carga los cambios en los datos como un mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="db5ae-136">Uploads data changes as an XML message.</span></span>

2.  <span data-ttu-id="db5ae-137">El Reconciliador de replicación de mezcla y la Escucha de replicación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hospedados en el equipo en el que se ejecuta IIS realizan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db5ae-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener and Merge Replication Reconciler that are hosted on the computer that is running IIS do the following:</span></span>

    1.  <span data-ttu-id="db5ae-138">Responden a la solicitud HTTPS.</span><span class="sxs-lookup"><span data-stu-id="db5ae-138">Respond to the HTTPS request.</span></span>

    2.  <span data-ttu-id="db5ae-139">Establecen una conexión SQL con la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="db5ae-139">Make an SQL connection to the publication database.</span></span>

    3.  <span data-ttu-id="db5ae-140">Aplican los cambios de carga en la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="db5ae-140">Apply the upload changes to the publication database.</span></span>

    4.  <span data-ttu-id="db5ae-141">Extraen los cambios de descarga para el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="db5ae-141">Extract the download changes for the Subscriber.</span></span>

    5.  <span data-ttu-id="db5ae-142">Devuelven una respuesta HTTPS al Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="db5ae-142">Send an HTTPS response back to the Merge Agent.</span></span>

3.  <span data-ttu-id="db5ae-143">A continuación, el Agente de mezcla en el suscriptor acepta la respuesta HTTPS y aplica los cambios de descarga a la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="db5ae-143">The Merge Agent at the Subscriber then accepts the HTTPS response and applies the download changes to the subscription database.</span></span>

## <a name="see-also"></a><span data-ttu-id="db5ae-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db5ae-144">See Also</span></span>
 <span data-ttu-id="db5ae-145">[Configurar](configure-web-synchronization.md) [topologías de sincronización web para la sincronización web](topologies-for-web-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="db5ae-145">[Configure Web Synchronization](configure-web-synchronization.md) [Topologies for Web Synchronization](topologies-for-web-synchronization.md)</span></span>


