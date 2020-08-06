---
title: Cancelar comandos (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- connections [XML for Analysis]
- associated connections [XML for Analysis]
- XML for Analysis, canceling
- associated sessions [XML for Analysis]
- canceling connections
- canceling commands
- canceling sessions
- SPID
- XMLA, canceling
- server process IDs [XML for Analysis]
- sessions [XML for Analysis]
ms.assetid: b59f8197-c33d-4e65-9022-848ccba540f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 003c70362c38ae1838b4679abf6485fa031a9143
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744408"
---
# <a name="canceling-commands-xmla"></a><span data-ttu-id="b211e-102">Cancelar comandos (XMLA)</span><span class="sxs-lookup"><span data-stu-id="b211e-102">Canceling Commands (XMLA)</span></span>
  <span data-ttu-id="b211e-103">En función de los permisos administrativos del usuario que emite el comando, el comando [Cancelar](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) en XML for Analysis (XMLA) puede cancelar un comando en una sesión, una sesión, una conexión, un proceso de servidor o una sesión o conexión asociada.</span><span class="sxs-lookup"><span data-stu-id="b211e-103">Depending on the administrative permissions of the user issuing the command, the [Cancel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) command in XML for Analysis (XMLA) can cancel a command on a session, a session, a connection, a server process, or an associated session or connection.</span></span>  
  
## <a name="canceling-commands"></a><span data-ttu-id="b211e-104">Cancelar comandos</span><span class="sxs-lookup"><span data-stu-id="b211e-104">Canceling Commands</span></span>  
 <span data-ttu-id="b211e-105">Un usuario puede cancelar el comando actualmente en ejecución en el contexto de la sesión explícita actual mediante el envío de un comando `Cancel` sin propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="b211e-105">A user can cancel the currently executing command within the context of the current explicit session by sending a `Cancel` command with no specified properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b211e-106">Un usuario no puede cancelar un comando que se ejecuta en una sesión implícita.</span><span class="sxs-lookup"><span data-stu-id="b211e-106">A command running in an implicit session cannot be canceled by a user.</span></span>  
  
### <a name="canceling-batch-commands"></a><span data-ttu-id="b211e-107">Cancelar comandos Batch</span><span class="sxs-lookup"><span data-stu-id="b211e-107">Canceling Batch Commands</span></span>  
 <span data-ttu-id="b211e-108">Si un usuario cancela un comando `Batch`, se cancelan todos los comandos restantes del comando `Batch` que no se hayan ejecutado aún.</span><span class="sxs-lookup"><span data-stu-id="b211e-108">If a user cancels a `Batch` command, then all remaining commands not yet executed within the `Batch` command are canceled.</span></span> <span data-ttu-id="b211e-109">Si el comando `Batch` es de tipo transaccional, se revierten los comandos ejecutados con anterioridad al comando `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="b211e-109">If the `Batch` command was transactional, any commands that were executed before the `Cancel` command runs are rolled back.</span></span>  
  
## <a name="canceling-sessions"></a><span data-ttu-id="b211e-110">Cancelar sesiones</span><span class="sxs-lookup"><span data-stu-id="b211e-110">Canceling Sessions</span></span>  
 <span data-ttu-id="b211e-111">Al especificar un identificador de sesión para una sesión explícita en la propiedad [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) del `Cancel` comando, un administrador de base de datos o un administrador del servidor puede cancelar una sesión, incluido el comando que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="b211e-111">By specifying a session identifier for an explicit session in the [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a database administrator or server administrator can cancel a session, including the currently executing command.</span></span> <span data-ttu-id="b211e-112">Un administrador de bases de datos solamente puede cancelar sesiones de las bases de datos en las que tiene permisos administrativos.</span><span class="sxs-lookup"><span data-stu-id="b211e-112">A database administrator can only cancel sessions for databases on which he or she has administrative permissions.</span></span>  
  
 <span data-ttu-id="b211e-113">Un administrador de bases de datos puede recuperar las sesiones activas de una base de datos especificada mediante la recuperación del conjunto de filas de esquema DISCOVER_SESSIONS.</span><span class="sxs-lookup"><span data-stu-id="b211e-113">A database administrator can retrieve the active sessions for a specified database by retrieving the DISCOVER_SESSIONS schema rowset.</span></span> <span data-ttu-id="b211e-114">Para recuperar el conjunto de filas de esquema DISCOVER_SESSIONS, el administrador de bases de datos utiliza el `Discover` método XMLA y especifica el identificador de base de datos adecuado para la columna de restricción SESSION_CURRENT_DATABASE en la propiedad [restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) del `Discover` método.</span><span class="sxs-lookup"><span data-stu-id="b211e-114">To retrieve the DISCOVER_SESSIONS schema rowset, the database administrator uses the XMLA `Discover` method and specifies the appropriate database identifier for the SESSION_CURRENT_DATABASE restriction column in the [Restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) property of the `Discover` method.</span></span>  
  
## <a name="canceling-connections"></a><span data-ttu-id="b211e-115">Cancelar conexiones</span><span class="sxs-lookup"><span data-stu-id="b211e-115">Canceling Connections</span></span>  
 <span data-ttu-id="b211e-116">Al especificar un identificador de conexión en la propiedad [ConnectionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) del `Cancel` comando, un administrador del servidor puede cancelar todas las sesiones asociadas a una conexión determinada, incluidos todos los comandos en ejecución, y cancelar la conexión.</span><span class="sxs-lookup"><span data-stu-id="b211e-116">By specifying a connection identifier in the [ConnectionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) property of the `Cancel` command, a server administrator can cancel all of the sessions associated with a given connection, including all running commands, and cancel the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b211e-117">Si la instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no puede localizar y cancelar las sesiones asociadas a una conexión, por ejemplo, cuando el bombeo de datos abre varias sesiones mientras proporciona conectividad http, la instancia no puede cancelar la conexión.</span><span class="sxs-lookup"><span data-stu-id="b211e-117">If the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cannot locate and cancel the sessions associated with a connection, such as when the data pump opens multiple sessions while providing HTTP connectivity, the instance cannot cancel the connection.</span></span> <span data-ttu-id="b211e-118">Si esto ocurriera durante la ejecución de un comando `Cancel`, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="b211e-118">If this case is encountered during the execution of a `Cancel` command, an error occurs.</span></span>  
  
 <span data-ttu-id="b211e-119">Un administrador de servidor puede recuperar las conexiones activas de una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] mediante la recuperación del conjunto de filas de esquema DISCOVER_CONNECTIONS con el método `Discover` de XMLA.</span><span class="sxs-lookup"><span data-stu-id="b211e-119">A server administrator can retrieve the active connections for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance by retrieving the DISCOVER_CONNECTIONS schema rowset using the XMLA `Discover` method.</span></span>  
  
## <a name="canceling-server-processes"></a><span data-ttu-id="b211e-120">Cancelar procesos de servidor</span><span class="sxs-lookup"><span data-stu-id="b211e-120">Canceling Server Processes</span></span>  
 <span data-ttu-id="b211e-121">Al especificar un identificador de proceso de servidor (SPID) en la propiedad [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) del `Cancel` comando, un administrador del servidor puede cancelar los comandos asociados a un SPID determinado.</span><span class="sxs-lookup"><span data-stu-id="b211e-121">By specifying a server process identifier (SPID) in the [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a server administrator can cancel the commands associated with a given SPID.</span></span>  
  
## <a name="canceling-associated-sessions-and-connections"></a><span data-ttu-id="b211e-122">Cancelar sesiones y conexiones asociadas</span><span class="sxs-lookup"><span data-stu-id="b211e-122">Canceling Associated Sessions and Connections</span></span>  
 <span data-ttu-id="b211e-123">Puede establecer la propiedad [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) en true para cancelar las conexiones, las sesiones y los comandos asociados a la conexión, la sesión o el SPID especificado en el `Cancel` comando.</span><span class="sxs-lookup"><span data-stu-id="b211e-123">You can set the [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) property to true to cancel the connections, sessions, and commands associated with the connection, session, or SPID specified in the `Cancel` command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b211e-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b211e-124">See Also</span></span>  
 <span data-ttu-id="b211e-125">[Método Discover &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span><span class="sxs-lookup"><span data-stu-id="b211e-125">[Discover Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span></span>  
 [<span data-ttu-id="b211e-126">Desarrollar con XMLA en Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b211e-126">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
