---
title: Aplicación sqlagent90 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- starting SQL Server Agent
- sqlagent90 application
- SQL Server Agent, starting
- command prompt utilities [SQL Server], sqlagent90
ms.assetid: e8b80e8d-d0c9-4500-a868-0ce08233da08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 290cb69f39aa3b08bb290c210b2d37977614a1ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670719"
---
# <a name="sqlagent90-application"></a><span data-ttu-id="d649f-102">sqlagent90, aplicación</span><span class="sxs-lookup"><span data-stu-id="d649f-102">sqlagent90 Application</span></span>
  <span data-ttu-id="d649f-103">La aplicación **sqlagent90** inicia el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d649f-103">The **sqlagent90** application starts [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent from the command prompt.</span></span> <span data-ttu-id="d649f-104">Normalmente, el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] debe ejecutarse desde [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o utilizando métodos de SQL-SMO en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="d649f-104">Usually, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should be run from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or by using SQL-SMO methods in an application.</span></span> <span data-ttu-id="d649f-105">Ejecute **sqlagent90** solo desde el símbolo del sistema cuando esté diagnosticando el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o cuando el proveedor principal de asistencia técnica le redirija a él.</span><span class="sxs-lookup"><span data-stu-id="d649f-105">Only run **sqlagent90** from the command prompt when you are diagnosing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, or when you are directed to it by your primary support provider.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d649f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d649f-106">Syntax</span></span>  
  
```  
  
sqlagent90  
-c [-v] [-iinstance_name]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d649f-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d649f-107">Arguments</span></span>  
 <span data-ttu-id="d649f-108">**-c**</span><span class="sxs-lookup"><span data-stu-id="d649f-108">**-c**</span></span>  
 <span data-ttu-id="d649f-109">Indica que el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se ejecuta desde el símbolo del sistema y es independiente del Administrador de control de servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="d649f-109">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent is running from the command prompt and is independent of the Microsoft Windows Services Control Manager.</span></span> <span data-ttu-id="d649f-110">Cuando se usa **-c** , el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no se puede controlar desde la aplicación Servicios de las Herramientas administrativas ni desde el Administrador de configuración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d649f-110">When **-c** is used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent cannot be controlled from either the Services application in Administrative Tools or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="d649f-111">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d649f-111">This argument is mandatory.</span></span>  
  
 <span data-ttu-id="d649f-112">**-v**</span><span class="sxs-lookup"><span data-stu-id="d649f-112">**-v**</span></span>  
 <span data-ttu-id="d649f-113">Indica que el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se ejecuta en modo detallado y escribe información de diagnóstico en la ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d649f-113">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent runs in verbose mode and writes diagnostic information to the command-prompt window.</span></span> <span data-ttu-id="d649f-114">La información de diagnóstico es la misma que la que se escribe en el registro de errores del Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d649f-114">The diagnostic information is the same as the information written to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error log.</span></span>  
  
 <span data-ttu-id="d649f-115">**-i** *instance_name*</span><span class="sxs-lookup"><span data-stu-id="d649f-115">**-i** *instance_name*</span></span>  
 <span data-ttu-id="d649f-116">Indica que el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se conecta a la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] con nombre especificada por *instance_name*.</span><span class="sxs-lookup"><span data-stu-id="d649f-116">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent connects to the named [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance specified by *instance_name*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d649f-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d649f-117">Remarks</span></span>  
 <span data-ttu-id="d649f-118">Después de mostrar un mensaje de copyright, **sqlagent90** muestra la salida en la ventana del símbolo del sistema solo si se especificó el modificador **-v** .</span><span class="sxs-lookup"><span data-stu-id="d649f-118">After displaying a copyright message, **sqlagent90** displays output in the command prompt window only when the **-v** switch is specified.</span></span> <span data-ttu-id="d649f-119">Para detener **sqlagent90**, pulse Crtl+C en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d649f-119">To stop **sqlagent90**, press CTRL+C at the command prompt.</span></span> <span data-ttu-id="d649f-120">No cierre la ventana del símbolo del sistema antes de detener **sqlagent90**.</span><span class="sxs-lookup"><span data-stu-id="d649f-120">Do not close the command-prompt window before stopping **sqlagent90**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d649f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d649f-121">See Also</span></span>  
 [<span data-ttu-id="d649f-122">Tareas administrativas automatizadas &#40;Agente SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d649f-122">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../ssms/agent/automated-administration-tasks-sql-server-agent.md)  
  
  
