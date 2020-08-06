---
title: Selector de demonio de filtro de texto completo de SQL (pestaña Servicio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 6aad7ebe-c4be-4d37-8536-61502f51faa2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f0d9c76d7d92947dd17fe2ed6e912e3d6baa6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676756"
---
# <a name="sql-full-text-filter-daemon-launcher-service-tab"></a><span data-ttu-id="3e3bd-102">Selector del demonio de filtro de texto completo de SQL (pestaña Servicio)</span><span class="sxs-lookup"><span data-stu-id="3e3bd-102">SQL Full-text Filter Daemon Launcher (Service Tab)</span></span>
  <span data-ttu-id="3e3bd-103">A partir de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], el Selector de demonio de filtro de texto completo de SQL (selector FDHOST) se usa en el texto completo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e3bd-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text.</span></span> <span data-ttu-id="3e3bd-104">Este servicio debe estar ejecutándose si se utiliza la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="3e3bd-105">Para obtener información sobre los procesos de host de demonio de filtro, vea "Arquitectura de la búsqueda de texto completo" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e3bd-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="3e3bd-106">Use la pestaña **Servicio**del cuadro de diálogo **Propiedades de Selector de demonio de filtro de texto completo de SQL** para ver o especificar las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-106">Use the **Service**tab on the **SQL Full-text Filter Daemon LauncherProperties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3e3bd-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="3e3bd-107">Options</span></span>  
 <span data-ttu-id="3e3bd-108">**Ruta de acceso binaria**</span><span class="sxs-lookup"><span data-stu-id="3e3bd-108">**Binary Path**</span></span>  
 <span data-ttu-id="3e3bd-109">Muestra la ubicación de los archivos de programa utilizados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-109">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="3e3bd-110">**Control de error**</span><span class="sxs-lookup"><span data-stu-id="3e3bd-110">**Error Control**</span></span>  
 <span data-ttu-id="3e3bd-111">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="3e3bd-112">Si el servicio no se inicia al iniciar el equipo, el programa de inicio registra el error y muestra un cuadro de mensaje emergente pero continúa con la operación de inicio.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="3e3bd-113">Este valor no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="3e3bd-114">**Código de salida**</span><span class="sxs-lookup"><span data-stu-id="3e3bd-114">**Exit Code**</span></span>  
 <span data-ttu-id="3e3bd-115">Si se produce un error, el número de error aparece en este cuadro.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="3e3bd-116">Utilice este número para solucionar errores buscando el número en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base o informe del mismo al personal de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="3e3bd-117">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="3e3bd-117">**Host Name**</span></span>  
 <span data-ttu-id="3e3bd-118">Muestra el nombre del equipo o clúster que ejecuta el servicio [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e3bd-118">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="3e3bd-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3e3bd-119">**Name**</span></span>  
 <span data-ttu-id="3e3bd-120">Indica el nombre para mostrar del servicio.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="3e3bd-121">**Id. del proceso**</span><span class="sxs-lookup"><span data-stu-id="3e3bd-121">**Process ID**</span></span>  
 <span data-ttu-id="3e3bd-122">Muestra el identificador de proceso de Windows.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="3e3bd-123">**Tipo de servicio de SQL**</span><span class="sxs-lookup"><span data-stu-id="3e3bd-123">**SQL Service Type**</span></span>  
 <span data-ttu-id="3e3bd-124">Muestra el tipo de servicio proporcionado a los procesos de llamada.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3e3bd-125">instala varios servicios.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-125">installs several services.</span></span>  
  
 <span data-ttu-id="3e3bd-126">**Modo de inicio**</span><span class="sxs-lookup"><span data-stu-id="3e3bd-126">**Start Mode**</span></span>  
 <span data-ttu-id="3e3bd-127">Para este servicio se pueden configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3e3bd-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="3e3bd-128">Manual: el servicio no se inicia automáticamente al iniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="3e3bd-129">Debe iniciarlo mediante el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] u otra herramienta.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="3e3bd-130">Automático: el servicio intenta iniciarse cuando se inicia el equipo.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="3e3bd-131">Deshabilitado: el servicio no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="3e3bd-132">**State**</span><span class="sxs-lookup"><span data-stu-id="3e3bd-132">**State**</span></span>  
 <span data-ttu-id="3e3bd-133">Indica si el servicio está en ejecución, detenido o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="3e3bd-134">" **…** " indica que hay un cambio de estado pendiente.</span><span class="sxs-lookup"><span data-stu-id="3e3bd-134">"**...**" indicates a state change is pending.</span></span>  
  
  
