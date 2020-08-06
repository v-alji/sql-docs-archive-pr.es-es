---
title: Propiedades de SQL Server (pestaña Servicio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e4ae0c6b-6fd8-4325-b54e-1758fc659958
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5822a02d5631e0d0e9318b20a1dcee87b8a4ded1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749540"
---
# <a name="sql-server-properties-service-tab"></a><span data-ttu-id="2d4d5-102">Propiedades de SQL Server (pestaña Servicio)</span><span class="sxs-lookup"><span data-stu-id="2d4d5-102">SQL Server Properties (Service Tab)</span></span>
  <span data-ttu-id="2d4d5-103">Utilice la pestaña **Servicio**del cuadro de diálogo **Propiedades de MSSQLSERVER** para ver o especificar las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-103">Use the **Service**tab on the **MSSQLSERVER Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2d4d5-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="2d4d5-104">Options</span></span>  
 <span data-ttu-id="2d4d5-105">**Ruta de acceso binaria**</span><span class="sxs-lookup"><span data-stu-id="2d4d5-105">**Binary Path**</span></span>  
 <span data-ttu-id="2d4d5-106">Muestra la ubicación de los archivos de programa utilizados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-106">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="2d4d5-107">**Control de error**</span><span class="sxs-lookup"><span data-stu-id="2d4d5-107">**Error Control**</span></span>  
 <span data-ttu-id="2d4d5-108">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="2d4d5-109">Si el servicio no se inicia al iniciar el equipo, el programa de inicio registra el error y muestra un cuadro de mensaje emergente pero continúa con la operación de inicio.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="2d4d5-110">Este valor no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="2d4d5-111">**Código de salida**</span><span class="sxs-lookup"><span data-stu-id="2d4d5-111">**Exit Code**</span></span>  
 <span data-ttu-id="2d4d5-112">Si se produce un error, el número de error aparece en este cuadro.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-112">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="2d4d5-113">Utilice este número para solucionar errores buscando el número en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base o informe del mismo al personal de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-113">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="2d4d5-114">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2d4d5-114">**Host Name**</span></span>  
 <span data-ttu-id="2d4d5-115">Muestra el nombre del equipo o clúster que ejecuta el servicio [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d4d5-115">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="2d4d5-116">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2d4d5-116">**Name**</span></span>  
 <span data-ttu-id="2d4d5-117">Indica el nombre para mostrar del servicio.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-117">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="2d4d5-118">**Id. del proceso**</span><span class="sxs-lookup"><span data-stu-id="2d4d5-118">**Process ID**</span></span>  
 <span data-ttu-id="2d4d5-119">Muestra el identificador de proceso de Windows.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-119">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="2d4d5-120">**Tipo de servicio**</span><span class="sxs-lookup"><span data-stu-id="2d4d5-120">**Service Type**</span></span>  
 <span data-ttu-id="2d4d5-121">Muestra el tipo de servicio proporcionado a los procesos de llamada.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-121">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2d4d5-122">instala varios servicios.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-122">installs several services.</span></span>  
  
 <span data-ttu-id="2d4d5-123">**Modo de inicio**</span><span class="sxs-lookup"><span data-stu-id="2d4d5-123">**Start Mode**</span></span>  
 <span data-ttu-id="2d4d5-124">Para este servicio se pueden configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2d4d5-124">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="2d4d5-125">Manual: el servicio no se inicia automáticamente al iniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-125">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="2d4d5-126">Debe iniciarlo mediante el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] u otra herramienta.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-126">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="2d4d5-127">Automático: el servicio intenta iniciarse cuando se inicia el equipo.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-127">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="2d4d5-128">Deshabilitado: el servicio no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-128">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="2d4d5-129">**State**</span><span class="sxs-lookup"><span data-stu-id="2d4d5-129">**State**</span></span>  
 <span data-ttu-id="2d4d5-130">Indica si el servicio está en ejecución, detenido o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-130">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="2d4d5-131">" **…** " indica que hay un cambio de estado pendiente.</span><span class="sxs-lookup"><span data-stu-id="2d4d5-131">"**...**" indicates a state change is pending.</span></span>  
  
  
