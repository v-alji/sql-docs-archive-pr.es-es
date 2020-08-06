---
title: Restricciones en las conexiones normales y de contexto | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: 0c6fe4cb-d846-40b5-8884-35a9c770f5e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 52f50347a27cdaffe83b252d86c56382b5ef4f31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674161"
---
# <a name="restrictions-on-regular-and-context-connections"></a><span data-ttu-id="7648d-102">Restricciones en las conexiones normales y de contexto</span><span class="sxs-lookup"><span data-stu-id="7648d-102">Restrictions on Regular and Context Connections</span></span>
  <span data-ttu-id="7648d-103">En este tema se describen las restricciones asociadas al código que se ejecuta en el [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] proceso a través de las conexiones de contexto y normales.</span><span class="sxs-lookup"><span data-stu-id="7648d-103">This topic discusses the restrictions associated with code executing in the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] process through context and regular connections.</span></span>  
  
## <a name="restrictions-on-context-connections"></a><span data-ttu-id="7648d-104">Restricciones en conexiones de contexto</span><span class="sxs-lookup"><span data-stu-id="7648d-104">Restrictions on Context Connections</span></span>  
 <span data-ttu-id="7648d-105">Al desarrollar su aplicación, tenga en cuenta las siguientes restricciones que se aplican a las conexiones de contexto:</span><span class="sxs-lookup"><span data-stu-id="7648d-105">When developing your application, take into account the following restrictions that apply to context connections:</span></span>  
  
-   <span data-ttu-id="7648d-106">Solo puede tener una conexión de contexto abierta a una hora determinada para una conexión determinada.</span><span class="sxs-lookup"><span data-stu-id="7648d-106">You can have only one context connection open at a given time for a given connection.</span></span> <span data-ttu-id="7648d-107">Si tiene varias instrucciones ejecutándose simultáneamente en conexiones independientes, cada una de ellas puede obtener su propia conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="7648d-107">If you have multiple statements running concurrently in separate connections, each one of them can get their own context connection.</span></span> <span data-ttu-id="7648d-108">La restricción no afecta a solicitudes simultáneas de conexiones distintas; solo afecta a una solicitud determinada en una conexión determinada.</span><span class="sxs-lookup"><span data-stu-id="7648d-108">The restriction does not affect concurrent requests from different connections; it only affects a given request on a given connection.</span></span>  
  
-   <span data-ttu-id="7648d-109">No se admiten conjuntos de resultados activos múltiples (MARS) en una conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="7648d-109">Multiple Active Result Sets (MARS) is not supported in a context connection.</span></span>  
  
-   <span data-ttu-id="7648d-110">La clase `SqlBulkCopy` no funciona en una conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="7648d-110">The `SqlBulkCopy` class does not operate in a context connection.</span></span>  
  
-   <span data-ttu-id="7648d-111">No se admite el procesamiento por lotes de actualizaciones en una conexión de contexto</span><span class="sxs-lookup"><span data-stu-id="7648d-111">Update batching in a context connection is not supported</span></span>  
  
-   <span data-ttu-id="7648d-112">`SqlNotificationRequest` no puede utilizarse con comandos que se ejecutan en una conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="7648d-112">`SqlNotificationRequest` cannot be used with commands that execute against a context connection.</span></span>  
  
-   <span data-ttu-id="7648d-113">No se admite la cancelación de comandos que están ejecutándose en la conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="7648d-113">Canceling commands that are running against the context connection is not supported.</span></span> <span data-ttu-id="7648d-114">El método `SqlCommand.Cancel` omite automáticamente la solicitud.</span><span class="sxs-lookup"><span data-stu-id="7648d-114">The `SqlCommand.Cancel` method silently ignores the request.</span></span>  
  
-   <span data-ttu-id="7648d-115">No puede usarse ninguna otra palabra clave de cadena de conexión cuando se utiliza "context connection=true".</span><span class="sxs-lookup"><span data-stu-id="7648d-115">No other connection string keywords can be used when you use "context connection=true".</span></span>  
  
-   <span data-ttu-id="7648d-116">La propiedad `SqlConnection.DataSource` devuelve NULL si la cadena de conexión para `SqlConnection` es "context connection=true", en lugar del nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7648d-116">The `SqlConnection.DataSource` property returns null if the connection string for the `SqlConnection` is "context connection=true", instead of the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="7648d-117">El establecimiento de la propiedad `SqlCommand.CommandTimeout` no tiene ningún efecto cuando el comando se ejecuta en una conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="7648d-117">Setting the `SqlCommand.CommandTimeout` property has no effect when the command is executed against a context connection.</span></span>  
  
## <a name="restrictions-on-regular-connections"></a><span data-ttu-id="7648d-118">Restricciones en conexiones normales</span><span class="sxs-lookup"><span data-stu-id="7648d-118">Restrictions on Regular Connections</span></span>  
 <span data-ttu-id="7648d-119">Al desarrollar su aplicación, tenga en cuenta las siguientes restricciones que se aplican a las conexiones normales:</span><span class="sxs-lookup"><span data-stu-id="7648d-119">When developing your application, take into account the following restrictions that apply to regular connections:</span></span>  
  
-   <span data-ttu-id="7648d-120">No se admite la ejecución de comandos asincrónica en servidores internos.</span><span class="sxs-lookup"><span data-stu-id="7648d-120">Asynchronous command execution against internal servers is not supported.</span></span> <span data-ttu-id="7648d-121">Si se incluye "async=true" en la cadena de conexión de un comando y después se ejecuta el comando, se inicia una excepción `System.NotSupportedException`.</span><span class="sxs-lookup"><span data-stu-id="7648d-121">Including "async=true" in the connection string of a command, and then executing the command, results in `System.NotSupportedException` being thrown.</span></span> <span data-ttu-id="7648d-122">Aparece este mensaje: "No se admite el procesamiento asincrónico  al ejecutar el proceso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]".</span><span class="sxs-lookup"><span data-stu-id="7648d-122">This message appears: "Asynchronous processing is not supported when running inside the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process."</span></span>  
  
-   <span data-ttu-id="7648d-123">No se admite el objeto `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="7648d-123">`SqlDependency` object is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7648d-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7648d-124">See Also</span></span>  
 [<span data-ttu-id="7648d-125">Conexión de contexto</span><span class="sxs-lookup"><span data-stu-id="7648d-125">Context Connection</span></span>](context-connection.md)  
  
  
