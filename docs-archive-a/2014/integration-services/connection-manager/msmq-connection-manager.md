---
title: Administrador de conexiones MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], message queues
- connection managers [Integration Services], MSMQ
- MSMQ connection manager
- message queue connections [Integration Services]
ms.assetid: a86900e2-450e-479f-b207-e1b02361d395
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c51866eeef281f6587bf281461e4faa2278308d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676132"
---
# <a name="msmq-connection-manager"></a><span data-ttu-id="47238-102">MSMQ, administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="47238-102">MSMQ Connection Manager</span></span>
  <span data-ttu-id="47238-103">Un administrador de conexiones MSMQ permite a un paquete conectarse a una cola de mensajes que usa Message Queue Server (que también recibe el nombre de MSMQ).</span><span class="sxs-lookup"><span data-stu-id="47238-103">An MSMQ connection manager enables a package to connect to a message queue that uses Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="47238-104">La tarea Cola de mensajes que incluye [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa un administrador de conexiones MSMQ.</span><span class="sxs-lookup"><span data-stu-id="47238-104">The Message Queue task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an MSMQ connection manager.</span></span>  
  
 <span data-ttu-id="47238-105">Cuando agrega un administrador de conexiones MSMQ a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve como una conexión MSMQ en tiempo de ejecución, establece las propiedades del administrador de conexiones y agrega el administrador de conexiones a la colección `Connections` del paquete.</span><span class="sxs-lookup"><span data-stu-id="47238-105">When you add an MSMQ connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an MSMQ connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="47238-106">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `MSMQ`.</span><span class="sxs-lookup"><span data-stu-id="47238-106">The `ConnectionManagerType` property of the connection manager is set to `MSMQ`.</span></span>  
  
 <span data-ttu-id="47238-107">Puede configurar el administrador de conexiones MSMQ de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="47238-107">You can configure an MSMQ connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="47238-108">Proporcionar una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="47238-108">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="47238-109">Proporcionar la ruta de la cola de mensajes con la que se debe hacer la conexión.</span><span class="sxs-lookup"><span data-stu-id="47238-109">Provide the path of the message queue to connect to.</span></span>  
  
 <span data-ttu-id="47238-110">El formato de la ruta de acceso depende del tipo de cola, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="47238-110">The format of the path depends on the type of queue, as shown in the following table.</span></span>  
  
|<span data-ttu-id="47238-111">Tipo de cola</span><span class="sxs-lookup"><span data-stu-id="47238-111">Queue type</span></span>|<span data-ttu-id="47238-112">Ruta de acceso de ejemplo</span><span class="sxs-lookup"><span data-stu-id="47238-112">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="47238-113">Público</span><span class="sxs-lookup"><span data-stu-id="47238-113">Public</span></span>|<span data-ttu-id="47238-114">\<computer name>\\<queue name\></span><span class="sxs-lookup"><span data-stu-id="47238-114">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="47238-115">Privada</span><span class="sxs-lookup"><span data-stu-id="47238-115">Private</span></span>|<span data-ttu-id="47238-116">\<computer name>\Private$\\<queue name\></span><span class="sxs-lookup"><span data-stu-id="47238-116">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="47238-117">Puede usar un punto (.) para representar el equipo local.</span><span class="sxs-lookup"><span data-stu-id="47238-117">You can use a period (.) to represent the local computer.</span></span>  
  
## <a name="configuration-of-the-msmq-connection-manager"></a><span data-ttu-id="47238-118">Configuración del administrador de conexiones MSMQ</span><span class="sxs-lookup"><span data-stu-id="47238-118">Configuration of the MSMQ Connection Manager</span></span>  
 <span data-ttu-id="47238-119">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="47238-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="47238-120">Para más información sobre las propiedades que puede configurar en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vea [Editor del administrador de conexiones MSMQ](../msmq-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="47238-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [MSMQ Connection Manager Editor](../msmq-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="47238-121">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="47238-121">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47238-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47238-122">See Also</span></span>  
 <span data-ttu-id="47238-123">[Tarea Cola de mensajes](../control-flow/message-queue-task.md) </span><span class="sxs-lookup"><span data-stu-id="47238-123">[Message Queue Task](../control-flow/message-queue-task.md) </span></span>  
 [<span data-ttu-id="47238-124">Conexiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="47238-124">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
