---
title: MSSQLSERVER_17194 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "17194"
helpviewer_keywords:
- 17194 (Database Engine error)
ms.assetid: 0d03eb20-28a7-4ceb-8903-7f9420a620f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3f56a104841c4825bba1f60b3588fadd63555c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672076"
---
# <a name="mssqlserver_17194"></a><span data-ttu-id="ee576-102">MSSQLSERVER_17194</span><span class="sxs-lookup"><span data-stu-id="ee576-102">MSSQLSERVER_17194</span></span>
    
## <a name="details"></a><span data-ttu-id="ee576-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ee576-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee576-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="ee576-104">Product Name</span></span>|<span data-ttu-id="ee576-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ee576-105">SQL Server</span></span>|  
|<span data-ttu-id="ee576-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ee576-106">Event ID</span></span>|<span data-ttu-id="ee576-107">17194</span><span class="sxs-lookup"><span data-stu-id="ee576-107">17194</span></span>|  
|<span data-ttu-id="ee576-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="ee576-108">Event Source</span></span>|<span data-ttu-id="ee576-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ee576-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ee576-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ee576-110">Component</span></span>|<span data-ttu-id="ee576-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ee576-111">SQLEngine</span></span>|  
|<span data-ttu-id="ee576-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ee576-112">Symbolic Name</span></span>||  
|<span data-ttu-id="ee576-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ee576-113">Message Text</span></span>|<span data-ttu-id="ee576-114">El servidor no pudo cargar la biblioteca de proveedores SSL necesaria para el inicio de sesión; se cerró la conexión.</span><span class="sxs-lookup"><span data-stu-id="ee576-114">The server was unable to load the SSL provider library needed to log in; the connection has been closed.</span></span> <span data-ttu-id="ee576-115">SSL se utiliza para cifrar la secuencia de inicio de sesión o todas las comunicaciones, según el modo en que el administrador haya configurado el servidor.</span><span class="sxs-lookup"><span data-stu-id="ee576-115">SSL is used to encrypt either the login sequence or all communications, depending on how the administrator has configured the server.</span></span> <span data-ttu-id="ee576-116">Consulte los Libros en pantalla para obtener información sobre este mensaje de error:  0xXXXX.</span><span class="sxs-lookup"><span data-stu-id="ee576-116">See Books Online for information on this error message:  0xXXXX.</span></span> <span data-ttu-id="ee576-117">[CLIENTE: 11.11.11.11]</span><span class="sxs-lookup"><span data-stu-id="ee576-117">[CLIENT: 11.11.11.11]</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ee576-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="ee576-118">Explanation</span></span>  
 <span data-ttu-id="ee576-119">Este error indica que el cliente ha cerrado la conexión.</span><span class="sxs-lookup"><span data-stu-id="ee576-119">This error indicates that the client has closed the connection.</span></span> <span data-ttu-id="ee576-120">Este error se produce porque se ha agotado el tiempo de espera de la conexión.</span><span class="sxs-lookup"><span data-stu-id="ee576-120">This error could occur because the connection time-out has expired.</span></span> <span data-ttu-id="ee576-121">El mensaje de error muestra un valor del sistema operativo que describe el problema subyacente.</span><span class="sxs-lookup"><span data-stu-id="ee576-121">The error message displays a value from the operating system that describes the underlying problem.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ee576-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ee576-122">User Action</span></span>  
 <span data-ttu-id="ee576-123">Si el código de error incluido en el mensaje es 0x2746 (valor decimal 10054), significa que el cliente ha restablecido la conexión debido, normalmente, a que se ha agotado el tiempo de espera. Para solucionar el error, aumente el tiempo de espera de la conexión en el cliente o en el programa que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="ee576-123">If the error code in the message is 0x2746 (decimal value 10054), this means that the connection was reset by the client, typically because of a time-out. To resolve the error, increase the connection time-out on the client or calling program.</span></span>  
  
 <span data-ttu-id="ee576-124">Para determinar una posible solución para otros valores de mensaje de error, use el comando de sistema operativo **net helpmsg** y especifique el valor decimal del código de error.</span><span class="sxs-lookup"><span data-stu-id="ee576-124">To determine a possible solution for other error message values, use the operating system command **net helpmsg** and specify the decimal value of the error code.</span></span>  
  
 <span data-ttu-id="ee576-125">Para obtener más información sobre cómo conectarse a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Server Network Configuration](../../database-engine/configure-windows/server-network-configuration.md) (Configuración de red del servidor) y [Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) (Configuración de red del cliente).</span><span class="sxs-lookup"><span data-stu-id="ee576-125">For more information about how to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Server Network Configuration](../../database-engine/configure-windows/server-network-configuration.md) and [Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="ee576-126">Solo para uso interno</span><span class="sxs-lookup"><span data-stu-id="ee576-126">Internal-Only</span></span>  
  
