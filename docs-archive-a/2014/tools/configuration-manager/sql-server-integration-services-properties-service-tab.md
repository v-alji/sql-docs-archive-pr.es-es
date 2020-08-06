---
title: Propiedades de SQL Server Integration Services (pestaña Servicio) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 37f0acd9-c96f-48fd-9b53-2ca0097af242
author: stevestein
ms.author: sstein
ms.openlocfilehash: a752bdeab3c99ac97445e3281d3165a2d8f79866
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676751"
---
# <a name="sql-server-integration-services-properties-service-tab"></a><span data-ttu-id="e473c-102">Propiedades de SQL Server Integration Services (pestaña Servicio)</span><span class="sxs-lookup"><span data-stu-id="e473c-102">SQL Server Integration Services Properties (Service Tab)</span></span>
  <span data-ttu-id="e473c-103">Use la pestaña **Servicio**del cuadro de diálogo [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** para ver o especificar las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="e473c-103">Use the **Service**tab on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e473c-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="e473c-104">Options</span></span>  
 <span data-ttu-id="e473c-105">**Ruta de acceso binaria**</span><span class="sxs-lookup"><span data-stu-id="e473c-105">**Binary Path**</span></span>  
 <span data-ttu-id="e473c-106">Muestra la ubicación de los archivos de programa utilizados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="e473c-106">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="e473c-107">**Control de error**</span><span class="sxs-lookup"><span data-stu-id="e473c-107">**Error Control**</span></span>  
 <span data-ttu-id="e473c-108">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="e473c-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="e473c-109">Si el servicio no se inicia al iniciar el equipo, el programa de inicio registra el error y muestra un cuadro de mensaje emergente pero continúa con la operación de inicio.</span><span class="sxs-lookup"><span data-stu-id="e473c-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="e473c-110">Este valor no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="e473c-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="e473c-111">**Código de salida**</span><span class="sxs-lookup"><span data-stu-id="e473c-111">**Exit Code**</span></span>  
 <span data-ttu-id="e473c-112">Código de error de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows que define los problemas encontrados al iniciar o detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="e473c-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows error code defining any problems encountered in starting or stopping the service.</span></span> <span data-ttu-id="e473c-113">Esta propiedad se establece en **ERROR_SERVICE_SPECIFIC_ERROR** (1066) si el error es exclusivo del servicio representado por esta clase y hay información disponible sobre el error en la propiedad **ServiceSpecificExitCode** .</span><span class="sxs-lookup"><span data-stu-id="e473c-113">This property is set to **ERROR_SERVICE_SPECIFIC_ERROR** (1066) when the error is unique to the service represented by this class, and information about the error is available in the **ServiceSpecificExitCode** property.</span></span> <span data-ttu-id="e473c-114">El servicio establece este valor en NO_ERROR (0) cuando se ejecuta, y de nuevo cuando finaliza normalmente.</span><span class="sxs-lookup"><span data-stu-id="e473c-114">The service sets this value to NO_ERROR (0) when running, and again upon normal termination.</span></span>  
  
 <span data-ttu-id="e473c-115">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="e473c-115">**Host Name**</span></span>  
 <span data-ttu-id="e473c-116">Muestra el nombre del equipo o clúster que ejecuta el servicio [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e473c-116">Displays the name of the computer or cluster running the [!INCLUDE[ssIS](../../includes/ssis-md.md)] service.</span></span>  
  
 <span data-ttu-id="e473c-117">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e473c-117">**Name**</span></span>  
 <span data-ttu-id="e473c-118">Indica el nombre para mostrar del servicio.</span><span class="sxs-lookup"><span data-stu-id="e473c-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="e473c-119">**Id. del proceso**</span><span class="sxs-lookup"><span data-stu-id="e473c-119">**Process ID**</span></span>  
 <span data-ttu-id="e473c-120">Muestra el identificador de proceso de Windows.</span><span class="sxs-lookup"><span data-stu-id="e473c-120">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="e473c-121">**Tipo de servicio de SQL**</span><span class="sxs-lookup"><span data-stu-id="e473c-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="e473c-122">Muestra el tipo de servicio proporcionado a los procesos de llamada.</span><span class="sxs-lookup"><span data-stu-id="e473c-122">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="e473c-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instala varios servicios.</span><span class="sxs-lookup"><span data-stu-id="e473c-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="e473c-124">**Modo de inicio**</span><span class="sxs-lookup"><span data-stu-id="e473c-124">**Start Mode**</span></span>  
 <span data-ttu-id="e473c-125">Para este servicio se pueden configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e473c-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="e473c-126">Manual: el servicio no se inicia automáticamente al iniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="e473c-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="e473c-127">Debe iniciarlo mediante el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] u otra herramienta.</span><span class="sxs-lookup"><span data-stu-id="e473c-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="e473c-128">Automático: el servicio intenta iniciarse cuando se inicia el equipo.</span><span class="sxs-lookup"><span data-stu-id="e473c-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="e473c-129">Deshabilitado: el servicio no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="e473c-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="e473c-130">**State**</span><span class="sxs-lookup"><span data-stu-id="e473c-130">**State**</span></span>  
 <span data-ttu-id="e473c-131">Indica si el servicio está en ejecución, detenido o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="e473c-131">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="e473c-132">" **…** " indica que hay un cambio de estado pendiente.</span><span class="sxs-lookup"><span data-stu-id="e473c-132">"**...**" indicates a state change is pending.</span></span>  
  
  
