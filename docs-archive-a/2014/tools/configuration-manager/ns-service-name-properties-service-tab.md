---
title: Propiedades de NS $ &lt; nombre de servicio &gt; (pestaña servicio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 57c6b791-1663-4a01-9de2-cf1bdd8adb2c
author: stevestein
ms.author: sstein
ms.openlocfilehash: ddd80cf1c84e3fe7acc538e6aa65230b45870219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748428"
---
# <a name="nsltservice-namegt-properties-service-tab"></a><span data-ttu-id="6c938-102">Propiedades de NS$&lt;nombre de servicio&gt; (pestaña Servicio)</span><span class="sxs-lookup"><span data-stu-id="6c938-102">NS$&lt;service name&gt; Properties (Service Tab)</span></span>
  <span data-ttu-id="6c938-103">Este es el servicio [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNS](../../includes/ssns-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c938-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNS](../../includes/ssns-md.md)] service.</span></span> <span data-ttu-id="6c938-104">Los valores de propiedades en color gris claro no se pueden modificar con esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="6c938-104">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6c938-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="6c938-105">Options</span></span>  
 <span data-ttu-id="6c938-106">**Ruta de acceso binaria**</span><span class="sxs-lookup"><span data-stu-id="6c938-106">**Binary Path**</span></span>  
 <span data-ttu-id="6c938-107">Muestra la ubicación de los archivos de programa utilizados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="6c938-107">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="6c938-108">**Control de error**</span><span class="sxs-lookup"><span data-stu-id="6c938-108">**Error Control**</span></span>  
 <span data-ttu-id="6c938-109">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="6c938-109">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="6c938-110">Si el servicio no se inicia al iniciar el equipo, el programa de inicio registra el error y muestra un cuadro de mensaje emergente pero continúa con la operación de inicio.</span><span class="sxs-lookup"><span data-stu-id="6c938-110">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="6c938-111">Este valor no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="6c938-111">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="6c938-112">**Código de salida**</span><span class="sxs-lookup"><span data-stu-id="6c938-112">**Exit Code**</span></span>  
 <span data-ttu-id="6c938-113">Si se produce un error, el número de error aparece en este cuadro.</span><span class="sxs-lookup"><span data-stu-id="6c938-113">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="6c938-114">Utilice este número para solucionar errores buscando el número en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base o informe del mismo al personal de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="6c938-114">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="6c938-115">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="6c938-115">**Host Name**</span></span>  
 <span data-ttu-id="6c938-116">Muestra el nombre del equipo o clúster que ejecuta la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="6c938-116">Displays the name of the computer or cluster running the full text search.</span></span>  
  
 <span data-ttu-id="6c938-117">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6c938-117">**Name**</span></span>  
 <span data-ttu-id="6c938-118">Indica el nombre para mostrar del servicio.</span><span class="sxs-lookup"><span data-stu-id="6c938-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="6c938-119">**Id. del proceso**</span><span class="sxs-lookup"><span data-stu-id="6c938-119">**Process ID**</span></span>  
 <span data-ttu-id="6c938-120">Muestra el Id. de proceso de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="6c938-120">Displays the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows process ID.</span></span>  
  
 <span data-ttu-id="6c938-121">**Tipo de servicio de SQL**</span><span class="sxs-lookup"><span data-stu-id="6c938-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="6c938-122">Tipo de servicio proporcionado a los procesos de llamada.</span><span class="sxs-lookup"><span data-stu-id="6c938-122">Type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6c938-123">instala varios servicios.</span><span class="sxs-lookup"><span data-stu-id="6c938-123">installs several services.</span></span>  
  
 <span data-ttu-id="6c938-124">**Modo de inicio**</span><span class="sxs-lookup"><span data-stu-id="6c938-124">**Start Mode**</span></span>  
 <span data-ttu-id="6c938-125">Para este servicio se pueden configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6c938-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="6c938-126">Manual: el servicio no se inicia automáticamente al iniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="6c938-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="6c938-127">Debe iniciarlo mediante el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] u otra herramienta.</span><span class="sxs-lookup"><span data-stu-id="6c938-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="6c938-128">Automático: el servicio intenta iniciarse cuando se inicia el equipo.</span><span class="sxs-lookup"><span data-stu-id="6c938-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="6c938-129">Deshabilitado: el servicio no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="6c938-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="6c938-130">**State**</span><span class="sxs-lookup"><span data-stu-id="6c938-130">**State**</span></span>  
 <span data-ttu-id="6c938-131">Indica si el servicio está en ejecución, detenido o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6c938-131">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
  
