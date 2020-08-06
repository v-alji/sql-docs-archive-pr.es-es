---
title: Iniciar SQL Server con la configuración mínima | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- minimal configuration [SQL Server]
- starting SQL Server, minimal configuration
ms.assetid: 4d733c99-28b3-42d8-b7f6-7b943b548173
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c78fc10be584803b438b2cd125a77400ff369b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663098"
---
# <a name="start-sql-server-with-minimal-configuration"></a><span data-ttu-id="6262b-102">Iniciar SQL Server con la configuración mínima</span><span class="sxs-lookup"><span data-stu-id="6262b-102">Start SQL Server with Minimal Configuration</span></span>
  <span data-ttu-id="6262b-103">Si tiene problemas de configuración que evitan el inicio del servidor, puede iniciar una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante la opción de inicio con configuración mínima.</span><span class="sxs-lookup"><span data-stu-id="6262b-103">If you have configuration problems that prevent the server from starting, you can start an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the minimal configuration startup option.</span></span> <span data-ttu-id="6262b-104">Esta es la opción de inicio **-f**.</span><span class="sxs-lookup"><span data-stu-id="6262b-104">This is the startup option **-f**.</span></span> <span data-ttu-id="6262b-105">Al iniciar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la configuración mínima, el servidor utilizará automáticamente el modo de usuario único.</span><span class="sxs-lookup"><span data-stu-id="6262b-105">Starting an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with minimal configuration automatically puts the server in single-user mode.</span></span>  
  
 <span data-ttu-id="6262b-106">Tenga en cuenta los siguientes aspectos cuando inicie una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en modo de configuración mínima:</span><span class="sxs-lookup"><span data-stu-id="6262b-106">When you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode, note the following:</span></span>  
  
-   <span data-ttu-id="6262b-107">Solo se podrá conectar un usuario y no se ejecutará el proceso CHECKPOINT.</span><span class="sxs-lookup"><span data-stu-id="6262b-107">Only a single user can connect, and the CHECKPOINT process is not executed.</span></span>  
  
-   <span data-ttu-id="6262b-108">El acceso remoto y la lectura anticipada quedan deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="6262b-108">Remote access and read-ahead are disabled.</span></span>  
  
-   <span data-ttu-id="6262b-109">No se ejecutan los procedimientos almacenados de inicio.</span><span class="sxs-lookup"><span data-stu-id="6262b-109">Startup stored procedures do not run.</span></span>  
  
 <span data-ttu-id="6262b-110">Después de iniciar el servidor con la configuración mínima, debe modificar los valores que haga falta del servidor, detenerlo y después reiniciarlo.</span><span class="sxs-lookup"><span data-stu-id="6262b-110">After the server has been started with minimal configuration, you should change the appropriate server option value or values, stop, and then restart the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6262b-111">Use la utilidad **sqlcmd** y la conexión de administrador dedicada (DAC) para conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6262b-111">Use the **sqlcmd** utility and the dedicated administrator connection (DAC) to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6262b-112">Si utiliza una conexión típica, detenga el servicio del Agente SQL Server antes de conectarse a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en modo de configuración mínima.</span><span class="sxs-lookup"><span data-stu-id="6262b-112">If you use a typical connection, stop the SQL Server Agent service before connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode.</span></span> <span data-ttu-id="6262b-113">En caso contrario, el servicio Agente SQL Server utilizará la conexión y, por tanto, la bloqueará.</span><span class="sxs-lookup"><span data-stu-id="6262b-113">Otherwise, the SQL Server Agent service uses the connection, thereby blocking it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6262b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6262b-114">See Also</span></span>  
 <span data-ttu-id="6262b-115">[Iniciar, detener o pausar el servicio del Agente SQL Server](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span><span class="sxs-lookup"><span data-stu-id="6262b-115">[Start, Stop, or Pause the SQL Server Agent Service](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span></span>  
 <span data-ttu-id="6262b-116">[Conexión de diagnóstico para administradores de bases de datos](diagnostic-connection-for-database-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="6262b-116">[Diagnostic Connection for Database Administrators](diagnostic-connection-for-database-administrators.md) </span></span>  
 <span data-ttu-id="6262b-117">[sqlcmd (utilidad)](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="6262b-117">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="6262b-118">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6262b-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="6262b-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6262b-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="6262b-120">Opciones de inicio del servicio de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="6262b-120">Database Engine Service Startup Options</span></span>](database-engine-service-startup-options.md)  
  
  
