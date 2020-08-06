---
title: Crear una cadena de conexión válida con el protocolo de memoria compartida | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], shared memory
- aliases [SQL Server], shared memory
ms.assetid: 5fff42e8-377f-4b40-b0c8-b02393f8a1af
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca97332a09a33fcfc15a3dbb2599af27dbe0e1db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743806"
---
# <a name="creating-a-valid-connection-string-using-shared-memory-protocol"></a><span data-ttu-id="3824c-102">Crear una cadena de conexión válida con el protocolo de memoria compartida</span><span class="sxs-lookup"><span data-stu-id="3824c-102">Creating a Valid Connection String Using Shared Memory Protocol</span></span>
  <span data-ttu-id="3824c-103">Las conexiones a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde un cliente que se ejecuta en el mismo equipo utilizan el protocolo de memoria compartida.</span><span class="sxs-lookup"><span data-stu-id="3824c-103">Connections to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client running on the same computer use the shared memory protocol.</span></span> <span data-ttu-id="3824c-104">La memoria compartida no tiene propiedades que se puedan configurar.</span><span class="sxs-lookup"><span data-stu-id="3824c-104">Shared memory has no configurable properties.</span></span> <span data-ttu-id="3824c-105">Memoria compartida es el protocolo que se intenta utilizar en primer lugar y no se puede desplazar de la posición prioritaria de la lista **Protocolos habilitados** de la lista **Propiedades de los protocolos de cliente** .</span><span class="sxs-lookup"><span data-stu-id="3824c-105">Shared memory is always tried first, and cannot be moved from the top position of the **Enabled Protocols** list in the **Client Protocols Properties** list.</span></span> <span data-ttu-id="3824c-106">El protocolo de memoria compartida se puede deshabilitar, lo que resulta útil para solucionar problemas con los demás protocolos.</span><span class="sxs-lookup"><span data-stu-id="3824c-106">The Shared Memory protocol can be disabled, which is useful when troubleshooting one of the other protocols.</span></span>  
  
 <span data-ttu-id="3824c-107">No es posible crear un alias con el protocolo de memoria compartida, pero si el protocolo está habilitado, al conectarse al [!INCLUDE[ssDE](../../includes/ssde-md.md)] por nombre se crea una conexión de memoria compartida.</span><span class="sxs-lookup"><span data-stu-id="3824c-107">You cannot create an alias using the shared memory protocol, but if shared memory is enabled, then connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by name, creates a shared memory connection.</span></span> <span data-ttu-id="3824c-108">Una cadena de conexión de memoria compartida usa el formato `lpc:<servername>[\instancename]`.</span><span class="sxs-lookup"><span data-stu-id="3824c-108">A shared memory connection string uses the format `lpc:<servername>[\instancename]`.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="3824c-109">Conectarse al servidor local</span><span class="sxs-lookup"><span data-stu-id="3824c-109">Connecting to the Local Server</span></span>  
 <span data-ttu-id="3824c-110">Al conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuando se ejecuta en el mismo equipo que el cliente, puede usar **(local)** como nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="3824c-110">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use **(local)** as the server name.</span></span> <span data-ttu-id="3824c-111">Esta posibilidad no se recomienda ya que genera ambigüedad, pero puede ser útil cuando se sabe que el cliente se ejecuta en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="3824c-111">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="3824c-112">Por ejemplo, al crear una aplicación para usuarios desconectados móviles, como puede ser el personal de ventas, en la que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecutará en equipos portátiles y se almacenarán datos de proyectos, un cliente que se conecte a **(local)** siempre se conectará al servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecuta en el equipo portátil.</span><span class="sxs-lookup"><span data-stu-id="3824c-112">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to **(local)** would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="3824c-113">En lugar de **(local)** , se puede usar la palabra**localhost**o un punto ( **.** ).</span><span class="sxs-lookup"><span data-stu-id="3824c-113">The word **localhost** or a period (**.**) can be used in place of **(local)**.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="3824c-114">Comprobar el protocolo de conexión</span><span class="sxs-lookup"><span data-stu-id="3824c-114">Verifying your Connection Protocol</span></span>  
 <span data-ttu-id="3824c-115">La siguiente consulta devolverá el protocolo utilizado para la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="3824c-115">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="3824c-116">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="3824c-116">Examples:</span></span>  
 <span data-ttu-id="3824c-117">Los siguientes nombres se conectarán al equipo local con el protocolo de memoria compartida si está habilitado:</span><span class="sxs-lookup"><span data-stu-id="3824c-117">The following names will connect to the local computer with the shared memory protocol if it is enabled:</span></span>  
  
 `<servername>`  
  
 `<servername>\<instancename>`  
  
 `(local)`  
  
 `localhost`  
  
 <span data-ttu-id="3824c-118">No se puede crear un alias para una conexión de memoria compartida.</span><span class="sxs-lookup"><span data-stu-id="3824c-118">You cannot create an alias for a shared memory connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3824c-119">Si se especifica una dirección IP en el cuadro **Servidor** , se establecerá una conexión TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="3824c-119">Specifying an IP Address in the **Server** box will result in a TCP/IP connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3824c-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3824c-120">See Also</span></span>  
 <span data-ttu-id="3824c-121">[Crear una cadena de conexión válida con TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="3824c-121">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 <span data-ttu-id="3824c-122">[Crear una cadena de conexión válida con canalizaciones con nombre](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="3824c-122">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="3824c-123">Elegir un protocolo de red</span><span class="sxs-lookup"><span data-stu-id="3824c-123">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
