---
title: Conexiones regulares y de contexto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: a1dead02-be88-4b16-8cb2-db1284856764
author: rothja
ms.author: jroth
ms.openlocfilehash: ce531129099a8f4908bdc4b29920696d4ba3c505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677698"
---
# <a name="regular-vs-context-connections"></a><span data-ttu-id="7a7d1-102">Conexiones normales y conexiones de contexto</span><span class="sxs-lookup"><span data-stu-id="7a7d1-102">Regular vs. Context Connections</span></span>
  <span data-ttu-id="7a7d1-103">Si se conecta a un servidor remoto, utilice siempre conexiones normales en lugar de conexiones de contexto.</span><span class="sxs-lookup"><span data-stu-id="7a7d1-103">If you are connecting to a remote server, always use regular connections rather than context connections.</span></span> <span data-ttu-id="7a7d1-104">Si se debe conectar al mismo servidor donde se está ejecutando el procedimiento almacenado o la función, utilice la conexión de contexto en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="7a7d1-104">If you need to connect to the same server on which the stored procedure or function is running, use the context connection in most cases.</span></span> <span data-ttu-id="7a7d1-105">Entre las ventajas que esto presenta se encuentran la ejecución en el mismo espacio de la transacción y que no es necesario volver a autenticarse.</span><span class="sxs-lookup"><span data-stu-id="7a7d1-105">This has benefits such as running in the same transaction space and not having to reauthenticate.</span></span>  
  
 <span data-ttu-id="7a7d1-106">Además, la utilización de la conexión de contexto suele proporciona un mejor rendimiento y menos uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="7a7d1-106">Additionally, using the context connection typically results in better performance and less resource usage.</span></span> <span data-ttu-id="7a7d1-107">La conexión de contexto es una conexión solo en proceso, por lo que puede ponerse en contacto con el servidor "directamente" omitiendo el protocolo de red y los niveles de transporte para enviar instrucciones Transact-SQL y recibir resultados.</span><span class="sxs-lookup"><span data-stu-id="7a7d1-107">The context connection is an in-process-only connection, so it can contact the server "directly" by bypassing the network protocol and transport layers to send Transact-SQL statements and receive results.</span></span> <span data-ttu-id="7a7d1-108">También se omite el proceso de autenticación.</span><span class="sxs-lookup"><span data-stu-id="7a7d1-108">The authentication process is bypassed, as well.</span></span> <span data-ttu-id="7a7d1-109">En la figura siguiente se muestran los componentes principales del proveedor administrado de `SqlClient`, así como la forma en que interactúan los diferentes componentes entre sí al utilizar una conexión normal y al utilizar la conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="7a7d1-109">The following figure shows the primary components of the `SqlClient` managed provider, as well as how the different components interact with each other when using a regular connection, and when using the context connection.</span></span>  
  
 <span data-ttu-id="7a7d1-110">![Rutas de acceso al código de un contexto y una conexión normal.](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Rutas de acceso al código de un contexto y una conexión normal.")</span><span class="sxs-lookup"><span data-stu-id="7a7d1-110">![Code paths of a context and a regular connnection.](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Code paths of a context and a regular connnection.")</span></span>  
  
 <span data-ttu-id="7a7d1-111">La conexión de contexto sigue una ruta de acceso al código más corta e implica menos componentes, de modo que puede esperar que las solicitudes y los resultados se envíen al servidor y de éste más rápido que en una conexión normal.</span><span class="sxs-lookup"><span data-stu-id="7a7d1-111">The context connection follows a shorter code path and involves fewer components, so you can expect requests and results to get to and from the server faster than in a regular connection.</span></span> <span data-ttu-id="7a7d1-112">El tiempo de ejecución de consultas en el servidor es el mismo en las conexiones de contexto y normales.</span><span class="sxs-lookup"><span data-stu-id="7a7d1-112">Query execution time on the server is the same for context and regular connections.</span></span>  
  
 <span data-ttu-id="7a7d1-113">Hay algunos casos en los que puede necesitar abrir una conexión normal independiente al mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="7a7d1-113">There are some cases in which you may need to open a separate regular connection to the same server.</span></span> <span data-ttu-id="7a7d1-114">Por ejemplo, hay ciertas restricciones en el uso de la conexión de contexto, descrita en [restricciones de las conexiones normales y de contexto](context-connections-and-regular-connections-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="7a7d1-114">For example, there are certain restrictions on using the context connection, described in [Restrictions on Regular and Context Connections](context-connections-and-regular-connections-restrictions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a7d1-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a7d1-115">See Also</span></span>  
 [<span data-ttu-id="7a7d1-116">Conexión de contexto</span><span class="sxs-lookup"><span data-stu-id="7a7d1-116">Context Connection</span></span>](context-connection.md)  
  
  
