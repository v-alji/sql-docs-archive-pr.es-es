---
title: remote admin connections (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- administrator connections [SQL Server]
- DAC
- connections [SQL Server], dedicated administrator
- remote admin connections option
- dedicated administrator connections [SQL Server]
ms.assetid: bf32b60a-7a48-401f-b6be-b5e2e46c413f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c17cf278d18444c5b93d4f4b7e0a3da8dbfb671e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676169"
---
# <a name="remote-admin-connections-server-configuration-option"></a><span data-ttu-id="bb999-102">remote admin connections (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="bb999-102">remote admin connections Server Configuration Option</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bb999-103">proporciona una conexión de administrador dedicada (DAC).</span><span class="sxs-lookup"><span data-stu-id="bb999-103">provides a dedicated administrator connection (DAC).</span></span> <span data-ttu-id="bb999-104">La conexión DAC permite a los administradores tener acceso al servidor en ejecución a fin de realizar funciones de diagnóstico o ejecutar instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] , o para solucionar problemas del servidor incluso cuando está bloqueado o se ejecuta en un estado anormal, y no responde a ninguna conexión de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb999-104">The DAC lets an administrator access a running server to execute diagnostic functions or [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or to troubleshoot problems on the server, even when the server is locked or running in an abnormal state and not responding to a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] connection.</span></span> <span data-ttu-id="bb999-105">De forma predeterminada, la conexión DAC solo está disponible en un cliente del servidor.</span><span class="sxs-lookup"><span data-stu-id="bb999-105">By default, the DAC is only available from a client on the server.</span></span> <span data-ttu-id="bb999-106">Para habilitar las aplicaciones cliente en equipos remotos de modo que usen la DAC, utilice la opción remote admin connections de sp_configure.</span><span class="sxs-lookup"><span data-stu-id="bb999-106">To enable client applications on remote computers to use the DAC, use the remote admin connections option of sp_configure.</span></span>  
  
 <span data-ttu-id="bb999-107">De forma predeterminada, la DAC solo escucha en la dirección IP de bucle invertido (127.0.0.1) a través del puerto 1434.</span><span class="sxs-lookup"><span data-stu-id="bb999-107">By default, the DAC only listens on the loop-back IP address (127.0.0.1), port 1434.</span></span> <span data-ttu-id="bb999-108">Si el puerto TCP 1434 no está disponible, se asigna dinámicamente un puerto TCP al iniciarse [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb999-108">If TCP port 1434 is not available, a TCP port is dynamically assigned when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] starts up.</span></span> <span data-ttu-id="bb999-109">Cuando haya más de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalada en un equipo, compruebe en el registro de errores el número de puerto TCP.</span><span class="sxs-lookup"><span data-stu-id="bb999-109">When more than one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a computer, check the error log for the TCP port number.</span></span>  
  
 <span data-ttu-id="bb999-110">En la siguiente tabla se muestran los posibles valores para la opción remote admin connections.</span><span class="sxs-lookup"><span data-stu-id="bb999-110">The following table lists the possible values for the remote admin connections option.</span></span>  
  
|<span data-ttu-id="bb999-111">Value</span><span class="sxs-lookup"><span data-stu-id="bb999-111">Value</span></span>|<span data-ttu-id="bb999-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb999-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb999-113">0</span><span class="sxs-lookup"><span data-stu-id="bb999-113">0</span></span>|<span data-ttu-id="bb999-114">Indica que solo se permiten conexiones locales mediante la DAC.</span><span class="sxs-lookup"><span data-stu-id="bb999-114">Indicates only local connections are allowed by using the DAC.</span></span>|  
|<span data-ttu-id="bb999-115">1</span><span class="sxs-lookup"><span data-stu-id="bb999-115">1</span></span>|<span data-ttu-id="bb999-116">Indica que la DAC permite las conexiones remotas.</span><span class="sxs-lookup"><span data-stu-id="bb999-116">Indicates remote connections are allowed by using the DAC.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bb999-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb999-117">Example</span></span>  
 <span data-ttu-id="bb999-118">El siguiente ejemplo permite utilizar una DAC desde un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="bb999-118">The following example enables the DAC from a remote computer.</span></span>  
  
```  
sp_configure 'remote admin connections', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb999-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb999-119">See Also</span></span>  
 [<span data-ttu-id="bb999-120">Conexión de diagnóstico para administradores de bases de datos</span><span class="sxs-lookup"><span data-stu-id="bb999-120">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
