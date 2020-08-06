---
title: SQL Server Service Broker | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SSBQUEUEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBREMSVCBINDPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBMSGTYPEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBROUTEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBCONTRACTPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBSERVICEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBPRIORITYPROPERTIES.GENERAL.F1
helpviewer_keywords:
- Broker See Service Broker
- SQL Server Service Broker
- Service Broker
ms.assetid: 8b8b3b57-fd46-44de-9a4e-e3a8e3999c1e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3d3877dd8311e0fe5b65bd4b1e7f9c40fbd84751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749458"
---
# <a name="sql-server-service-broker"></a><span data-ttu-id="d579d-102">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="d579d-102">SQL Server Service Broker</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="d579d-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)]proporciona compatibilidad nativa para las aplicaciones de mensajería y puesta en cola en [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d579d-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)] provides native support for messaging and queuing applications in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="d579d-104">De este modo, resulta más fácil para los desarrolladores crear aplicaciones complejas que usan los componentes de [!INCLUDE[ssDE](../../includes/ssde-md.md)] para la comunicación entre bases de datos distintas.</span><span class="sxs-lookup"><span data-stu-id="d579d-104">This makes it easier for developers to create sophisticated applications that use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] components to communicate between disparate databases.</span></span> <span data-ttu-id="d579d-105">Los desarrolladores pueden usar [!INCLUDE[ssSB](../../includes/sssb-md.md)] para crear con facilidad aplicaciones distribuidas y confiables.</span><span class="sxs-lookup"><span data-stu-id="d579d-105">Developers can use [!INCLUDE[ssSB](../../includes/sssb-md.md)] to easily build distributed and reliable applications.</span></span>  
  
 <span data-ttu-id="d579d-106">Los desarrolladores de aplicaciones que usan [!INCLUDE[ssSB](../../includes/sssb-md.md)] pueden distribuir las cargas de trabajo de datos en varias bases de datos sin tener que programar complejas funciones internas de comunicación y mensajería.</span><span class="sxs-lookup"><span data-stu-id="d579d-106">Application developers who use [!INCLUDE[ssSB](../../includes/sssb-md.md)] can distribute data workloads across several databases without programming complex communication and messaging internals.</span></span> <span data-ttu-id="d579d-107">Así se reduce el trabajo de programación y realización de pruebas, ya que [!INCLUDE[ssSB](../../includes/sssb-md.md)] controla las vías de comunicación del contexto de una conversación.</span><span class="sxs-lookup"><span data-stu-id="d579d-107">This reduces development and test work because [!INCLUDE[ssSB](../../includes/sssb-md.md)] handles the communication paths in the context of a conversation.</span></span> <span data-ttu-id="d579d-108">También aumenta el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d579d-108">It also improves performance.</span></span> <span data-ttu-id="d579d-109">Por ejemplo, las bases de datos front-end que admiten sitios web pueden grabar información y enviar tareas con muchos procesos a colas de bases de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="d579d-109">For example, front-end databases supporting Web sites can record information and send process intensive tasks to queue in back-end databases.</span></span> [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="d579d-110">asegura que todas las tareas se administran en el contexto de transacciones para garantizar confiabilidad y coherencia técnica.</span><span class="sxs-lookup"><span data-stu-id="d579d-110">ensures that all tasks are managed in the context of transactions to assure reliability and technical consistency.</span></span>  
  
## <a name="where-is-the-documentation-for-service-broker"></a><span data-ttu-id="d579d-111">¿Dónde está la documentación de Service Broker?</span><span class="sxs-lookup"><span data-stu-id="d579d-111">Where is the documentation for Service Broker?</span></span>  
 <span data-ttu-id="d579d-112">La documentación de referencia para [!INCLUDE[ssSB](../../includes/sssb-md.md)] se incluye en la documentación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d579d-112">The reference documentation for [!INCLUDE[ssSB](../../includes/sssb-md.md)] is included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation.</span></span> <span data-ttu-id="d579d-113">Esta documentación de referencia incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d579d-113">This reference documentation includes the following sections:</span></span>  
  
-   <span data-ttu-id="d579d-114">[Instrucciones de lenguaje de definición de datos &#40;DDL&#41; &#40;Transact-SQL&#41;](/sql/odbc/reference/develop-app/ddl-statements) para las instrucciones CREATE, ALTER y DROP</span><span class="sxs-lookup"><span data-stu-id="d579d-114">[Data Definition Language &#40;DDL&#41; Statements &#40;Transact-SQL&#41;](/sql/odbc/reference/develop-app/ddl-statements) for CREATE, ALTER, and DROP statements</span></span>  
  
-   [<span data-ttu-id="d579d-115">Vistas de catálogo de Service Broker &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d579d-115">Service Broker Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/service-broker-catalog-views-transact-sql)  
  
-   [<span data-ttu-id="d579d-116">Vistas de administración dinámica relacionadas con Service Broker &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d579d-116">Service Broker Related Dynamic Management Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/service-broker-related-dynamic-management-views-transact-sql)  
  
-   [<span data-ttu-id="d579d-117">Utilidad ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="d579d-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](../../tools/ssbdiagnose/ssbdiagnose-utility-service-broker.md)  
  
 <span data-ttu-id="d579d-118">Vea la [documentación publicada previamente](https://go.microsoft.com/fwlink/?LinkId=231312) para conocer los conceptos de [!INCLUDE[ssSB](../../includes/sssb-md.md)] y las tareas de desarrollo y administración.</span><span class="sxs-lookup"><span data-stu-id="d579d-118">See the [previously published documentation](https://go.microsoft.com/fwlink/?LinkId=231312) for [!INCLUDE[ssSB](../../includes/sssb-md.md)] concepts and for development and management tasks.</span></span> <span data-ttu-id="d579d-119">Esta documentación no se reproduce en la documentación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] debido al pequeño número de cambios realizados en [!INCLUDE[ssSB](../../includes/sssb-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d579d-119">This documentation is not reproduced in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation due to the small number of changes in [!INCLUDE[ssSB](../../includes/sssb-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="whats-new-in-service-broker"></a><span data-ttu-id="d579d-120">Novedades de Service Broker</span><span class="sxs-lookup"><span data-stu-id="d579d-120">What's new in Service Broker</span></span>  
 <span data-ttu-id="d579d-121">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]no se introducen cambios significativos.</span><span class="sxs-lookup"><span data-stu-id="d579d-121">No significant changes are introduced in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  <span data-ttu-id="d579d-122">Los siguientes cambios se incluyeron por primera vez en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d579d-122">The following changes were introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
### <a name="messages-can-be-sent-to-multiple-target-services-multicast"></a><span data-ttu-id="d579d-123">Se pueden enviar mensajes a varios servicios de destino (multidifusión)</span><span class="sxs-lookup"><span data-stu-id="d579d-123">Messages can be sent to multiple target services (multicast)</span></span>  
 <span data-ttu-id="d579d-124">La sintaxis de la instrucción de [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql) se ha ampliado para habilitar la multidifusión admitiendo varios identificadores de conversación.</span><span class="sxs-lookup"><span data-stu-id="d579d-124">The syntax of the [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql) statement has been extended to enable multicast by supporting multiple conversation handles.</span></span>  
  
### <a name="queues-expose-the-message-enqueued-time"></a><span data-ttu-id="d579d-125">Las colas exponen la hora de puesta en cola del mensaje</span><span class="sxs-lookup"><span data-stu-id="d579d-125">Queues expose the message enqueued time</span></span>  
 <span data-ttu-id="d579d-126">Las colas tienen una nueva columna, **message_enqueue_time**, que muestra el tiempo que un mensaje ha estado en la cola.</span><span class="sxs-lookup"><span data-stu-id="d579d-126">Queues have a new column, **message_enqueue_time**, that shows how long a message has been in the queue.</span></span>  
  
### <a name="poison-message-handling-can-be-disabled"></a><span data-ttu-id="d579d-127">El control de mensajes dudosos se puede deshabilitar</span><span class="sxs-lookup"><span data-stu-id="d579d-127">Poison message handling can be disabled</span></span>  
 <span data-ttu-id="d579d-128">Las instrucciones [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) y [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) ahora pueden habilitar o deshabilitar el control de mensajes dudosos agregando la cláusula `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span><span class="sxs-lookup"><span data-stu-id="d579d-128">The [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) and [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) statements now have the ability to enable or disable poison message handling by adding the clause, `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span></span> <span data-ttu-id="d579d-129">La vista de catálogo **sys.service_queues** tiene ahora la columna **is_poison_message_handling_enabled** para indicar si el control de mensajes dudosos está habilitado o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="d579d-129">The catalog view **sys.service_queues** now has the column **is_poison_message_handling_enabled** to indicate whether poison message is enabled or disabled.</span></span>  
  
### <a name="alwayson-support-in-service-broker"></a><span data-ttu-id="d579d-130">Compatibilidad con AlwaysOn de Service Broker</span><span class="sxs-lookup"><span data-stu-id="d579d-130">AlwaysOn support in Service Broker</span></span>  
 <span data-ttu-id="d579d-131">Para obtener más información, vea [Service Broker con grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d579d-131">For more information, see [Service Broker with AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span></span>  
  
  
