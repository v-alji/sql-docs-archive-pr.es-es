---
title: Propiedades de Analysis Server (pestaña Servicio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 8dbe4bc5-6aa9-48ee-857e-0b4ea764b9cb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91200120d87224c8e7733b0ff41ed423d3086c34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750409"
---
# <a name="analysis-server-properties-service-tab"></a><span data-ttu-id="89395-102">Propiedades de Analysis Server (pestaña Servicio)</span><span class="sxs-lookup"><span data-stu-id="89395-102">Analysis Server Properties (Service Tab)</span></span>
  <span data-ttu-id="89395-103">Este es el servicio [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89395-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="89395-104">Este servicio debe estar en ejecución para que [!INCLUDE[ssAS](../../includes/ssas-md.md)] funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="89395-104">This service must be running for [!INCLUDE[ssAS](../../includes/ssas-md.md)] to work properly.</span></span> <span data-ttu-id="89395-105">Los valores de propiedades en color gris claro no se pueden modificar con esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="89395-105">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="89395-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="89395-106">Options</span></span>  
 <span data-ttu-id="89395-107">**Ruta de acceso binaria**</span><span class="sxs-lookup"><span data-stu-id="89395-107">**Binary Path**</span></span>  
 <span data-ttu-id="89395-108">Muestra la ubicación de los archivos de programa utilizados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="89395-108">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="89395-109">**Control de error**</span><span class="sxs-lookup"><span data-stu-id="89395-109">**Error Control**</span></span>  
 <span data-ttu-id="89395-110">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="89395-110">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="89395-111">Si el servicio no se inicia al iniciar el equipo, el programa de inicio registra el error y muestra un cuadro de mensaje emergente pero continúa con la operación de inicio.</span><span class="sxs-lookup"><span data-stu-id="89395-111">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="89395-112">Este valor no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="89395-112">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="89395-113">**Código de salida**</span><span class="sxs-lookup"><span data-stu-id="89395-113">**Exit Code**</span></span>  
 <span data-ttu-id="89395-114">Si se produce un error, el número de error aparece en este cuadro.</span><span class="sxs-lookup"><span data-stu-id="89395-114">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="89395-115">Utilice este número para solucionar errores buscando el número en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base o informe del mismo al personal de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="89395-115">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="89395-116">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="89395-116">**Host Name**</span></span>  
 <span data-ttu-id="89395-117">Muestra el nombre del equipo o clúster que ejecuta [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89395-117">Displays the name of the computer or cluster running [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span></span>  
  
 <span data-ttu-id="89395-118">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="89395-118">**Name**</span></span>  
 <span data-ttu-id="89395-119">Indica el nombre para mostrar del servicio.</span><span class="sxs-lookup"><span data-stu-id="89395-119">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="89395-120">**Id. del proceso**</span><span class="sxs-lookup"><span data-stu-id="89395-120">**Process ID**</span></span>  
 <span data-ttu-id="89395-121">Muestra el número que usa [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows para realizar el seguimiento de los procesos de este programa.</span><span class="sxs-lookup"><span data-stu-id="89395-121">Displays the number used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows to keep track of this program's processes.</span></span>  
  
 <span data-ttu-id="89395-122">**Tipo de servicio de SQL**</span><span class="sxs-lookup"><span data-stu-id="89395-122">**SQL Service Type**</span></span>  
 <span data-ttu-id="89395-123">Muestra el tipo de servicio proporcionado a los procesos de llamada.</span><span class="sxs-lookup"><span data-stu-id="89395-123">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="89395-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instala varios servicios.</span><span class="sxs-lookup"><span data-stu-id="89395-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="89395-125">**Modo de inicio**</span><span class="sxs-lookup"><span data-stu-id="89395-125">**Start Mode**</span></span>  
 <span data-ttu-id="89395-126">Para este servicio se pueden configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="89395-126">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="89395-127">Manual: el servicio no se inicia automáticamente al iniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="89395-127">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="89395-128">Debe iniciarlo mediante el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] u otra herramienta.</span><span class="sxs-lookup"><span data-stu-id="89395-128">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="89395-129">Automático: el servicio intenta iniciarse cuando se inicia el equipo.</span><span class="sxs-lookup"><span data-stu-id="89395-129">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="89395-130">Deshabilitado: el servicio no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="89395-130">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="89395-131">**State**</span><span class="sxs-lookup"><span data-stu-id="89395-131">**State**</span></span>  
 <span data-ttu-id="89395-132">Indica si el servicio está en ejecución, detenido o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="89395-132">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
  
