---
title: Administrar Service Broker | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- Service Broker [SMO]
ms.assetid: b29d7432-d1e5-4bb6-b544-57b3a9430f95
author: stevestein
ms.author: sstein
ms.openlocfilehash: ce166825bb7adea241bac13defeca1a78b4f29cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744034"
---
# <a name="managing-service-broker"></a><span data-ttu-id="cf28c-102">Administrar Service Broker</span><span class="sxs-lookup"><span data-stu-id="cf28c-102">Managing Service Broker</span></span>
  <span data-ttu-id="cf28c-103">En SMO, los objetos [!INCLUDE[ssSB](../../../includes/sssb-md.md)] se encuntran en el espacio de nombres `Microsoft.SqlServer.Management.Smo.Broker`, que requiere una referencia a Microsoft.SqlServer.Smo.dll.</span><span class="sxs-lookup"><span data-stu-id="cf28c-103">In SMO, the [!INCLUDE[ssSB](../../../includes/sssb-md.md)] objects are found in the `Microsoft.SqlServer.Management.Smo.Broker` namespace, which requires a reference to the Microsoft.SqlServer.Smo.dll.</span></span> <span data-ttu-id="cf28c-104">También se requiere una referencia a Microsoft.SqlServer.ServiceBrokerEnum.dll para admitir la información de clase.</span><span class="sxs-lookup"><span data-stu-id="cf28c-104">A reference to the Microsoft.SqlServer.ServiceBrokerEnum.dll is also required for supporting class information.</span></span>  
  
 <span data-ttu-id="cf28c-105">SMO proporciona un conjunto de objetos [!INCLUDE[ssSB](../../../includes/sssb-md.md)] que permiten administrar mediante programación (DDL) la implementación [!INCLUDE[ssSB](../../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf28c-105">SMO provides a set of [!INCLUDE[ssSB](../../../includes/sssb-md.md)] objects that permit programmatic management (DDL) of the [!INCLUDE[ssSB](../../../includes/sssb-md.md)] implementation.</span></span> <span data-ttu-id="cf28c-106">Esto incluye definir los tipos de mensaje, los contratos, las colas y los servicios.</span><span class="sxs-lookup"><span data-stu-id="cf28c-106">This includes defining the message types, contracts, queues, and services.</span></span> <span data-ttu-id="cf28c-107">Dado que SMO es una herramienta de administración que no está diseñada para la manipulación de datos, SMO no admite el envío y la recepción de mensajes de [!INCLUDE[ssSB](../../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf28c-107">Because SMO is a management tool that is not intended for data manipulation, sending and receiving [!INCLUDE[ssSB](../../../includes/sssb-md.md)] messages is not supported by SMO.</span></span>  
  
 <span data-ttu-id="cf28c-108">En SMO, el objeto <xref:Microsoft.SqlServer.Management.Smo.Database.ServiceBroker%2A> es la clase de nivel superior bajo la que reside toda la funcionalidad de [!INCLUDE[ssSB](../../../includes/sssb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf28c-108">In SMO, the <xref:Microsoft.SqlServer.Management.Smo.Database.ServiceBroker%2A> object is the top-level class under which all the [!INCLUDE[ssSB](../../../includes/sssb-md.md)] functionality resides.</span></span> <span data-ttu-id="cf28c-109">Se requiere una implementación de [!INCLUDE[ssSB](../../../includes/sssb-md.md)] para cada base de datos que participa en la aplicación de mensajería distribuida.</span><span class="sxs-lookup"><span data-stu-id="cf28c-109">A [!INCLUDE[ssSB](../../../includes/sssb-md.md)] implementation is required for each database that is participating in the distributed messaging application.</span></span> <span data-ttu-id="cf28c-110">Por consiguiente, el objeto <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceBroker> es un elemento secundario del objeto <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="cf28c-110">Therefore, the <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceBroker> object is a child of the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
 <span data-ttu-id="cf28c-111">El objeto <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceBroker> contiene colecciones de los objetos siguientes que se utilizan para definir la implementación de [!INCLUDE[ssSB](../../../includes/sssb-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cf28c-111">The <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceBroker> object contains collections of the following objects that are used to define the [!INCLUDE[ssSB](../../../includes/sssb-md.md)] implementation:</span></span>  
  
-   <span data-ttu-id="cf28c-112">Los objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.MessageType> representan tipos de mensaje que definen el contenido de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="cf28c-112"><xref:Microsoft.SqlServer.Management.Smo.Broker.MessageType> objects represent message types that define the content of messages.</span></span>  
  
-   <span data-ttu-id="cf28c-113">Los objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.MessageTypeMapping> representan contratos que especifican la dirección y el tipo de mensajes de una conversación determinada.</span><span class="sxs-lookup"><span data-stu-id="cf28c-113"><xref:Microsoft.SqlServer.Management.Smo.Broker.MessageTypeMapping> objects represent contracts that specify the direction and type of messages in a given conversation.</span></span>  
  
-   <span data-ttu-id="cf28c-114">Los objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceQueue> almacenan los mensajes antes de realizar el envío y una vez recibidos.</span><span class="sxs-lookup"><span data-stu-id="cf28c-114"><xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceQueue> objects store messages prior to sending and after they are received.</span></span> <span data-ttu-id="cf28c-115">Proporcionan la comunicación asincrónica entre los servicios, así como otras ventajas, como bloquear automáticamente los mensajes del mismo grupo de conversación.</span><span class="sxs-lookup"><span data-stu-id="cf28c-115">They provide asynchronous communication between services, as well as other benefits, such as automatically locking messages in the same conversation group.</span></span>  
  
-   <span data-ttu-id="cf28c-116">Los objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.BrokerService> representan servicios de [!INCLUDE[ssSB](../../../includes/sssb-md.md)], que son extremos direccionables para las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="cf28c-116"><xref:Microsoft.SqlServer.Management.Smo.Broker.BrokerService> objects represent [!INCLUDE[ssSB](../../../includes/sssb-md.md)] services, which are the addressable endpoints for conversations.</span></span> <span data-ttu-id="cf28c-117">Los mensajes de [!INCLUDE[ssSB](../../../includes/sssb-md.md)] se envían desde un servicio hasta otro.</span><span class="sxs-lookup"><span data-stu-id="cf28c-117">[!INCLUDE[ssSB](../../../includes/sssb-md.md)] messages are sent from one service to another service.</span></span> <span data-ttu-id="cf28c-118">Un servicio especifica una cola para retener mensajes y los contratos en los que el servicio puede ser el destino.</span><span class="sxs-lookup"><span data-stu-id="cf28c-118">A service specifies a queue to hold messages, and specifies the contracts for which the service can be the target.</span></span>  
  
-   <span data-ttu-id="cf28c-119">Los objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.RemoteServiceBinding> representan los valores que [!INCLUDE[ssSB](../../../includes/sssb-md.md)] utiliza para la seguridad y autenticación al comunicar con un servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="cf28c-119"><xref:Microsoft.SqlServer.Management.Smo.Broker.RemoteServiceBinding> objects represent the settings that [!INCLUDE[ssSB](../../../includes/sssb-md.md)] uses for security and authentication when communicating with a remote service.</span></span>  
  
-   <span data-ttu-id="cf28c-120">Los objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceRoute> representan una ruta de [!INCLUDE[ssSB](../../../includes/sssb-md.md)], que contiene la información de ubicación para el servicio y la base de datos en las que se define.</span><span class="sxs-lookup"><span data-stu-id="cf28c-120"><xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceRoute> objects represents a [!INCLUDE[ssSB](../../../includes/sssb-md.md)] route, which contains the location information for the service and the database on which it is defined.</span></span> <span data-ttu-id="cf28c-121">Se requiere una ruta para la entrega del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cf28c-121">A route is required for message delivery.</span></span> <span data-ttu-id="cf28c-122">De forma predeterminada, cada base de datos contiene una ruta que especifica la ubicación como la instancia actual de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf28c-122">By default, each database contains a route that specifies the location as the current instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf28c-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf28c-123">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Broker>   
 [<span data-ttu-id="cf28c-124">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="cf28c-124">SQL Server Service Broker</span></span>](../../../database-engine/configure-windows/sql-server-service-broker.md)  
  
  