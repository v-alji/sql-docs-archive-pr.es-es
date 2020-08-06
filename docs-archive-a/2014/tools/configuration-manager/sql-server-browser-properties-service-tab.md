---
title: Propiedades de SQL Server Browser (pestaña Servicio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 98ace9b0-72d5-4b72-9b7b-11fbc490981a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 200e45648b94e26c5e808e9a817cfe01866e6a65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663261"
---
# <a name="sql-server-browser-properties-service-tab"></a><span data-ttu-id="23531-102">Propiedades de Explorador de SQL (pestaña Servicio)</span><span class="sxs-lookup"><span data-stu-id="23531-102">SQL Server Browser Properties (Service Tab)</span></span>
  <span data-ttu-id="23531-103">El programa Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecuta como un servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="23531-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> <span data-ttu-id="23531-104">El Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escucha las solicitudes entrantes de recursos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y proporciona información sobre las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="23531-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 <span data-ttu-id="23531-105">Use la pestaña **Servicio** del cuadro de diálogo **Propiedades de SQL Server Browser** para ver las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="23531-105">Use the **Service** tab on the **SQL Server Browser Properties** dialog box to view the following options.</span></span> <span data-ttu-id="23531-106">Todas las propiedades excepto **Modo de inicio** son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="23531-106">All properties except **Start Mode** are read-only.</span></span>  
  
## <a name="options"></a><span data-ttu-id="23531-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="23531-107">Options</span></span>  
 <span data-ttu-id="23531-108">**Ruta de acceso binaria**</span><span class="sxs-lookup"><span data-stu-id="23531-108">**Binary Path**</span></span>  
 <span data-ttu-id="23531-109">Muestra la ubicación de los archivos de programa utilizados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="23531-109">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="23531-110">**Control de error**</span><span class="sxs-lookup"><span data-stu-id="23531-110">**Error Control**</span></span>  
 <span data-ttu-id="23531-111">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="23531-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="23531-112">Si el servicio no se inicia al iniciar el equipo, el programa de inicio registra el error y muestra un cuadro de mensaje emergente pero continúa con la operación de inicio.</span><span class="sxs-lookup"><span data-stu-id="23531-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="23531-113">Este valor no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="23531-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="23531-114">**Código de salida**</span><span class="sxs-lookup"><span data-stu-id="23531-114">**Exit Code**</span></span>  
 <span data-ttu-id="23531-115">Si se produce un error, el número de error aparece en este cuadro.</span><span class="sxs-lookup"><span data-stu-id="23531-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="23531-116">Utilice este número para solucionar errores buscando el número en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base o informe del mismo al personal de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="23531-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="23531-117">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="23531-117">**Host Name**</span></span>  
 <span data-ttu-id="23531-118">Muestra el nombre del equipo o clúster que ejecuta el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23531-118">Displays the name of the computer or cluster running the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="23531-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="23531-119">**Name**</span></span>  
 <span data-ttu-id="23531-120">Indica el nombre para mostrar del servicio.</span><span class="sxs-lookup"><span data-stu-id="23531-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="23531-121">**Id. del proceso**</span><span class="sxs-lookup"><span data-stu-id="23531-121">**Process ID**</span></span>  
 <span data-ttu-id="23531-122">Muestra el identificador de proceso de Windows.</span><span class="sxs-lookup"><span data-stu-id="23531-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="23531-123">**Tipo de servicio**</span><span class="sxs-lookup"><span data-stu-id="23531-123">**Service Type**</span></span>  
 <span data-ttu-id="23531-124">Muestra el tipo de servicio proporcionado a los procesos de llamada.</span><span class="sxs-lookup"><span data-stu-id="23531-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="23531-125">instala varios servicios.</span><span class="sxs-lookup"><span data-stu-id="23531-125">installs several services.</span></span>  
  
 <span data-ttu-id="23531-126">**Modo de inicio**</span><span class="sxs-lookup"><span data-stu-id="23531-126">**Start Mode**</span></span>  
 <span data-ttu-id="23531-127">Para este servicio se pueden configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="23531-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="23531-128">Manual: el servicio no se inicia automáticamente al iniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="23531-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="23531-129">Debe iniciarlo mediante el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] u otra herramienta.</span><span class="sxs-lookup"><span data-stu-id="23531-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="23531-130">Automático: el servicio intenta iniciarse cuando se inicia el equipo.</span><span class="sxs-lookup"><span data-stu-id="23531-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="23531-131">Deshabilitado: el servicio no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="23531-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="23531-132">**State**</span><span class="sxs-lookup"><span data-stu-id="23531-132">**State**</span></span>  
 <span data-ttu-id="23531-133">Indica si el servicio está en ejecución, detenido o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="23531-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="23531-134">" **…** " indica que hay un cambio de estado pendiente.</span><span class="sxs-lookup"><span data-stu-id="23531-134">"**...**" indicates a state change is pending.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23531-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23531-135">See Also</span></span>  
 [<span data-ttu-id="23531-136">Servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="23531-136">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
