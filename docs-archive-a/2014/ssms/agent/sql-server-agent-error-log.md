---
title: Registro de errores del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- messages [SQL Server], SQL Server Agent
- errors [SQL Server], logs
- SQL Server Agent, errors
ms.assetid: 0b2d6e6e-cd2d-4b8b-9fa2-2bbd2fc0da41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea9a723695c6993f4f07897f49d8014a86ce78b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745617"
---
# <a name="sql-server-agent-error-log"></a><span data-ttu-id="a0ca8-102">Registro de errores del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="a0ca8-102">SQL Server Agent Error Log</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a0ca8-103">El Agente crea un registro de errores que, de manera predeterminada, registra las advertencias y los errores.</span><span class="sxs-lookup"><span data-stu-id="a0ca8-103">Agent creates an error log that records warnings and errors by default.</span></span> <span data-ttu-id="a0ca8-104">En el registro se visualizan los siguientes errores y advertencias:</span><span class="sxs-lookup"><span data-stu-id="a0ca8-104">The following warnings and errors are displayed in the log:</span></span>  
  
-   <span data-ttu-id="a0ca8-105">Mensajes de advertencia que proporcionan información acerca de posibles problemas, como "el trabajo \<*job_name*> se eliminó mientras se estaba ejecutando".</span><span class="sxs-lookup"><span data-stu-id="a0ca8-105">Warning messages that provide information about potential problems, such as "Job \<*job_name*> was deleted while it was running."</span></span>  
  
-   <span data-ttu-id="a0ca8-106">Mensajes de error que normalmente requieren la intervención de un administrador del sistema, como "No se puede iniciar la sesión de correo".</span><span class="sxs-lookup"><span data-stu-id="a0ca8-106">Error messages that usually require intervention by a system administrator, such as "Unable to start mail session."</span></span> <span data-ttu-id="a0ca8-107">Los mensajes de error se pueden enviar a un usuario o equipo específicos mediante **net send**.</span><span class="sxs-lookup"><span data-stu-id="a0ca8-107">Error messages can be sent to a specific user or computer by **net send**.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a0ca8-108">puede mantener hasta nueve registros de errores del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0ca8-108">maintains up to nine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs.</span></span> <span data-ttu-id="a0ca8-109">Cada registro archivado tiene una extensión que indica la antigüedad relativa del registro de errores.</span><span class="sxs-lookup"><span data-stu-id="a0ca8-109">Each archived log has an extension that indicates the relative age of the log.</span></span> <span data-ttu-id="a0ca8-110">Por ejemplo, una extensión de .1 indica que es el archivo de registro de errores más reciente y una extensión de .9 indica que es el archivo de registro de errores más antiguo.</span><span class="sxs-lookup"><span data-stu-id="a0ca8-110">For example, an extension of .1 indicates the newest archived error log and an extension of .9 indicates the oldest archived error log.</span></span>  
  
 <span data-ttu-id="a0ca8-111">De forma predeterminada, los mensajes de seguimiento de ejecución no se escriben en el registro de errores del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] porque lo pueden llenar,</span><span class="sxs-lookup"><span data-stu-id="a0ca8-111">By default, execution trace messages are not written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log, because they can fill it.</span></span> <span data-ttu-id="a0ca8-112">reduciendo así la posibilidad de seleccionar y analizar los errores más difíciles.</span><span class="sxs-lookup"><span data-stu-id="a0ca8-112">When the error log is full, your ability to select and analyze more difficult errors is reduced.</span></span> <span data-ttu-id="a0ca8-113">Puesto que el registro de errores agrega una carga de proceso adicional al servidor, es importante considerar las ventajas que se obtienen al capturar los mensajes de seguimiento de ejecución en este registro de errores.</span><span class="sxs-lookup"><span data-stu-id="a0ca8-113">Because the log adds to the server's processing load, it is important to consider carefully what value you obtain by capturing execution trace messages to the error log.</span></span> <span data-ttu-id="a0ca8-114">Generalmente, es mejor capturar todos los mensajes solo cuando se está depurando un problema específico.</span><span class="sxs-lookup"><span data-stu-id="a0ca8-114">Generally, it is best to capture all messages only when you are debugging a specific problem.</span></span>  
  
 <span data-ttu-id="a0ca8-115">Cuando se detiene el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se puede modificar la ubicación del registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0ca8-115">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is stopped, you can modify the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log.</span></span> <span data-ttu-id="a0ca8-116">Cuando el registro de errores está vacío, no se puede abrir.</span><span class="sxs-lookup"><span data-stu-id="a0ca8-116">When the error log is empty, the log cannot be opened.</span></span> <span data-ttu-id="a0ca8-117">Se puede reciclar el registro del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en cualquier momento, sin necesidad de detener el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0ca8-117">You can cycle the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent log at any time without stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="a0ca8-118">**Para ver el registro de errores del Agente SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a0ca8-118">**To view the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="a0ca8-119">Ver registro de errores del Agente SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ca8-119">View SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](view-sql-server-agent-error-log-sql-server-management-studio.md) 
  
 <span data-ttu-id="a0ca8-120">**Para cambiar el nombre del registro de errores del Agente SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a0ca8-120">**To rename a SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="a0ca8-121">Cambiar el nombre del registro de errores del Agente SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ca8-121">Rename a SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](rename-a-sql-server-agent-error-log-sql-server-management-studio.md)  
  
 <span data-ttu-id="a0ca8-122">**Para enviar mensajes de error del Agente SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a0ca8-122">**To send SQL Server Agent error messages**</span></span>  
  
-   [<span data-ttu-id="a0ca8-123">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="a0ca8-123">Send SQL Server Agent Error Messages</span></span>](send-sql-server-agent-error-messages.md)  
  
 <span data-ttu-id="a0ca8-124">**Para escribir mensajes de seguimiento de ejecución en el registro de errores del Agente SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a0ca8-124">**To write execution trace messages to the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="a0ca8-125">Escribir mensajes de seguimiento de ejecución en el registro de errores del Agente SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ca8-125">Write Execution Trace Messages to the SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](write-execution-trace-messages-to-sql-server-agent-log-ssms.md)  
  
  
