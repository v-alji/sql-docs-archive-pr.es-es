---
title: Visor de archivos de registro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer
ms.assetid: a4ea7fc8-1cb2-4c98-bc86-8991c5e748b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5139a32838070b817fce3bccf22b9fe08b5012e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671532"
---
# <a name="log-file-viewer"></a><span data-ttu-id="c1e4c-102">Visor de archivos de registro</span><span class="sxs-lookup"><span data-stu-id="c1e4c-102">Log File Viewer</span></span>
  <span data-ttu-id="c1e4c-103">El Visor del archivo de registros de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] se usa para obtener acceso a la información sobre los errores y eventos capturados en los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="c1e4c-103">Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is used to access information about errors and events that are captured in log files.</span></span>  
  
## <a name="benefits-of-using-log-file-viewer"></a><span data-ttu-id="c1e4c-104">Ventajas de usar el visor del archivo de registro</span><span class="sxs-lookup"><span data-stu-id="c1e4c-104">Benefits of using Log File Viewer</span></span>  
 <span data-ttu-id="c1e4c-105">Puede ver los archivos de registro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde una instancia local o remota de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuando la instancia de destino está sin conexión o no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="c1e4c-105">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span> <span data-ttu-id="c1e4c-106">Puede tener acceso a los archivos de registro sin conexión de servidores registrados o mediante programación a través de consultas WMI y WQL (Lenguaje de la consulta de WMI).</span><span class="sxs-lookup"><span data-stu-id="c1e4c-106">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span> <span data-ttu-id="c1e4c-107">Para obtener más información, vea [Ver sin conexión archivos de registro](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="c1e4c-107">For more information, see [View Offline Log Files](view-offline-log-files.md).</span></span> <span data-ttu-id="c1e4c-108">Estos son los tipos de archivos de registro a que se puede tener acceso con el visor del archivo de registro:</span><span class="sxs-lookup"><span data-stu-id="c1e4c-108">Following are the types of log files you can access using Log File Viewer:</span></span>  
  
-   <span data-ttu-id="c1e4c-109">Recopilación de auditoría</span><span class="sxs-lookup"><span data-stu-id="c1e4c-109">Audit Collection</span></span>  
  
-   <span data-ttu-id="c1e4c-110">Recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="c1e4c-110">Data Collection</span></span>  
  
-   <span data-ttu-id="c1e4c-111">Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="c1e4c-111">Database Mail</span></span>  
  
-   <span data-ttu-id="c1e4c-112">Historial de trabajos</span><span class="sxs-lookup"><span data-stu-id="c1e4c-112">Job History</span></span>  
  
-   <span data-ttu-id="c1e4c-113">Planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c1e4c-113">Maintenance Plans</span></span>  
  
-   <span data-ttu-id="c1e4c-114">Planes de mantenimiento remoto</span><span class="sxs-lookup"><span data-stu-id="c1e4c-114">Remote Maintenance Plans</span></span>  
  
-   <span data-ttu-id="c1e4c-115">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c1e4c-115">SQL Server</span></span>  
  
-   <span data-ttu-id="c1e4c-116">Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="c1e4c-116">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="c1e4c-117">Windows NT (se puede tener acceso a estos eventos de Windows también desde el Visor de eventos).</span><span class="sxs-lookup"><span data-stu-id="c1e4c-117">Windows NT (These are Windows events that can also be accessed from Event Viewer.)</span></span>  
  
## <a name="log-file-viewer-tasks"></a><span data-ttu-id="c1e4c-118">Tareas del visor del archivo de registros</span><span class="sxs-lookup"><span data-stu-id="c1e4c-118">Log File Viewer Tasks</span></span>  
  
|<span data-ttu-id="c1e4c-119">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="c1e4c-119">Task Description</span></span>|<span data-ttu-id="c1e4c-120">Tema</span><span class="sxs-lookup"><span data-stu-id="c1e4c-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="c1e4c-121">Describe cómo abrir el visor del archivo de registros dependiendo de la información que se desee ver.</span><span class="sxs-lookup"><span data-stu-id="c1e4c-121">Describes how to open Log File Viewer depending on the information that you want to view.</span></span>|[<span data-ttu-id="c1e4c-122">Abrir el Visor de archivos de registro</span><span class="sxs-lookup"><span data-stu-id="c1e4c-122">Open Log File Viewer</span></span>](open-log-file-viewer.md)|  
|<span data-ttu-id="c1e4c-123">Describe cómo ver los archivos de registro sin conexión a través de servidores registrados y cómo comprobar los permisos de WMI.</span><span class="sxs-lookup"><span data-stu-id="c1e4c-123">Describes how to view offline log files through registered servers and how to verify WMI permissions.</span></span>|[<span data-ttu-id="c1e4c-124">Ver archivos del registro sin conexión</span><span class="sxs-lookup"><span data-stu-id="c1e4c-124">View Offline Log Files</span></span>](view-offline-log-files.md)|  
|<span data-ttu-id="c1e4c-125">Proporciona la Ayuda F1 del visor del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="c1e4c-125">Provides Log File Viewer F1 Help.</span></span>|[<span data-ttu-id="c1e4c-126">Ayuda F1 del Visor de archivos de registro</span><span class="sxs-lookup"><span data-stu-id="c1e4c-126">Log File Viewer F1 Help</span></span>](log-file-viewer-f1-help.md)|  
  
## <a name="see-also"></a><span data-ttu-id="c1e4c-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1e4c-127">See Also</span></span>  
 <span data-ttu-id="c1e4c-128">[SQL Server Audit &#40;motor de base de datos&#41;](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="c1e4c-128">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="c1e4c-129">Registro de errores del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="c1e4c-129">SQL Server Agent Error Log</span></span>](../../ssms/agent/sql-server-agent-error-log.md)  
  
  
