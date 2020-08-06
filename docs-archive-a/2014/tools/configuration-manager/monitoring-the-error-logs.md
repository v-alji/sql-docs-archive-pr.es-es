---
title: Supervisar los registros de errores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server]
- database performance [SQL Server], errors
- Windows application logs [SQL Server]
- monitoring performance [SQL Server], errors
- server performance [SQL Server], errors
- comparing error and application log output
- errors [SQL Server], logs
- tuning databases [SQL Server], errors
- database monitoring [SQL Server], errors
- SQL Server error log
- logs [SQL Server], SQL Server error logs
- error logs [SQL Server]
- logs [SQL Server], Windows application logs
ms.assetid: e250336b-0695-44f6-a42f-23222f94e377
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a47891599dbe735bd437f5239c73bfd34c422ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672333"
---
# <a name="monitoring-the-error-logs"></a><span data-ttu-id="d7476-102">Supervisar los registros de errores</span><span class="sxs-lookup"><span data-stu-id="d7476-102">Monitoring the Error Logs</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d7476-103">registra ciertos eventos del sistema y definidos por el usuario en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y en el registro de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="d7476-103">logs certain system events and user-defined events to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span> <span data-ttu-id="d7476-104">Ambos registros marcan automáticamente el tiempo de todos los eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="d7476-104">Both logs automatically timestamp all recorded events.</span></span> <span data-ttu-id="d7476-105">Utilice la información del registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para solucionar problemas relacionados con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7476-105">Use the information in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to troubleshoot problems related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d7476-106">El registro de aplicación Windows proporciona una visión global de los eventos que tienen lugar en el sistema operativo Windows, así como de los eventos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7476-106">The Windows application log provides an overall picture of events that occur on the Windows operating system, as well as events in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="d7476-107">Utilice el Visor de eventos de Windows para ver el registro de aplicación Windows y filtrar la información.</span><span class="sxs-lookup"><span data-stu-id="d7476-107">Use the Windows Event Viewer to view the Windows application log and to filter the information.</span></span> <span data-ttu-id="d7476-108">Por ejemplo, puede filtrar eventos, como información, advertencia, error, auditoría de éxito y auditoría de error.</span><span class="sxs-lookup"><span data-stu-id="d7476-108">For example, you can filter events, such as information, warning, error, success audit, and failure audit.</span></span>  
  
## <a name="comparing-error-and-application-log-output"></a><span data-ttu-id="d7476-109">comparar los resultados del registro de errores y del registro de aplicación</span><span class="sxs-lookup"><span data-stu-id="d7476-109">Comparing Error and Application Log Output</span></span>  
 <span data-ttu-id="d7476-110">Puede utilizar tanto el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como el registro de aplicación Windows para identificar la causa de los problemas.</span><span class="sxs-lookup"><span data-stu-id="d7476-110">You can use both the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the Windows application log to identify the cause of problems.</span></span> <span data-ttu-id="d7476-111">Por ejemplo, mientras supervisa el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , puede encontrar mensajes de error que no contienen información de la causa.</span><span class="sxs-lookup"><span data-stu-id="d7476-111">For example, while monitoring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, you may encounter error messages that do not contain cause information.</span></span> <span data-ttu-id="d7476-112">Se puede acotar la lista de causas probables si se comparan las fechas y horas de los eventos en ambos registros.</span><span class="sxs-lookup"><span data-stu-id="d7476-112">By comparing the dates and times for events between these logs, you can narrow the list of probable causes.</span></span> <span data-ttu-id="d7476-113">El Visor del archivo de registros de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] permite integrar los registros de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y Windows en una sola lista, facilitando así la comprensión de eventos de servidor y eventos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relacionados.</span><span class="sxs-lookup"><span data-stu-id="d7476-113">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Log File Viewer lets you integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, and the Windows logs into a single list, making it easy to understand related server events and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="d7476-114">Para obtener más información, consulte el tema "Visor del archivo de registros" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7476-114">For more information, see the topic "Log File Viewer" in SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7476-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d7476-115">In This Section</span></span>  
  
|<span data-ttu-id="d7476-116">Tema</span><span class="sxs-lookup"><span data-stu-id="d7476-116">Topic</span></span>|<span data-ttu-id="d7476-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7476-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d7476-118">Ver el registro de errores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7476-118">Viewing the SQL Server Error Log</span></span>](../../../2014/tools/configuration-manager/viewing-the-sql-server-error-log.md)|<span data-ttu-id="d7476-119">Contiene información acerca del registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y cómo verlo.</span><span class="sxs-lookup"><span data-stu-id="d7476-119">Contains information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and how to view it.</span></span>|  
|[<span data-ttu-id="d7476-120">Ver el registro de la aplicación Windows</span><span class="sxs-lookup"><span data-stu-id="d7476-120">Viewing the Windows Application Log</span></span>](viewing-the-windows-application-log.md)|<span data-ttu-id="d7476-121">Contiene información acerca del registro de aplicación Windows y cómo verlo.</span><span class="sxs-lookup"><span data-stu-id="d7476-121">Contains information about the Windows application log and how to view it.</span></span>|  
  
  
