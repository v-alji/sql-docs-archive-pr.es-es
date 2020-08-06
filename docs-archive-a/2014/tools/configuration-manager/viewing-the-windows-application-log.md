---
title: Ver el registro de aplicación Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- application logs [SQL Server]
- Windows application logs [SQL Server]
- viewing Windows application logs
- errors [SQL Server], logs
- system logs [SQL Server]
- security logs [SQL Server]
- displaying Windows application logs
- logs [SQL Server], Windows application logs
ms.assetid: f9853b74-7db7-47cc-b957-e49ed5bc0a1a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22f900a0b203e652bbc9cc6e9638711d138756c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672323"
---
# <a name="viewing-the-windows-application-log"></a><span data-ttu-id="82ba4-102">Ver el registro de la aplicación Windows</span><span class="sxs-lookup"><span data-stu-id="82ba4-102">Viewing the Windows Application Log</span></span>
  <span data-ttu-id="82ba4-103">Cuando se configura [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para utilizar el registro de la aplicación de Microsoft Windows, cada sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escribe eventos nuevos en dicho registro.</span><span class="sxs-lookup"><span data-stu-id="82ba4-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Microsoft Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="82ba4-104">A diferencia del registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no se crea un nuevo registro de aplicación cada vez que se inicia una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82ba4-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="82ba4-105">Para ver y administrar el registro de la aplicación Windows, utilice el Visor de eventos de Windows o el Visor de registros de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82ba4-105">View and manage the Windows application log by using Windows Event Viewer or the Log Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="82ba4-106">Con el Visor de eventos se pueden ver tres registros.</span><span class="sxs-lookup"><span data-stu-id="82ba4-106">There are three logs that can be viewed with Event Viewer.</span></span>  
  
|<span data-ttu-id="82ba4-107">Tipo de registro de Windows</span><span class="sxs-lookup"><span data-stu-id="82ba4-107">Windows log type</span></span>|<span data-ttu-id="82ba4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="82ba4-108">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="82ba4-109">Registro del sistema</span><span class="sxs-lookup"><span data-stu-id="82ba4-109">System log</span></span>|<span data-ttu-id="82ba4-110">Registra los eventos registrados por los componentes del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="82ba4-110">Records events logged by the Windows operating system components.</span></span> <span data-ttu-id="82ba4-111">Por ejemplo, en el registro del sistema se registra el error de carga de un controlador o de otro componente del sistema durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="82ba4-111">For example, the failure of a driver or other system component to load during startup is recorded in the system log.</span></span>|  
|<span data-ttu-id="82ba4-112">Registro de seguridad</span><span class="sxs-lookup"><span data-stu-id="82ba4-112">Security log</span></span>|<span data-ttu-id="82ba4-113">Registra eventos de seguridad, como los errores en intentos de inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="82ba4-113">Records security events, such as failed login attempts.</span></span> <span data-ttu-id="82ba4-114">Esto ayuda a realizar un seguimiento de los cambios en el sistema de seguridad y a identificar las posibles infracciones en la seguridad.</span><span class="sxs-lookup"><span data-stu-id="82ba4-114">This helps track changes to the security system and identify possible breaches to security.</span></span> <span data-ttu-id="82ba4-115">Por ejemplo, los intentos de iniciar una sesión en el sistema se pueden grabar en este registro, según la configuración de auditorías del Administrador de usuarios.</span><span class="sxs-lookup"><span data-stu-id="82ba4-115">For example, attempts to log on to the system may be recorded in the security log, depending on the audit settings in the User Manager.</span></span><br /><br /> <span data-ttu-id="82ba4-116">Solo los miembros del rol fijo de servidor **sysadmin** pueden ver el registro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="82ba4-116">Only members of the **sysadmin** fixed server role can view the security log.</span></span>|  
|<span data-ttu-id="82ba4-117">Registro de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="82ba4-117">Application log</span></span>|<span data-ttu-id="82ba4-118">Graba los eventos registrados por las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="82ba4-118">Records events that are logged by applications.</span></span> <span data-ttu-id="82ba4-119">Por ejemplo, una aplicación de bases de datos puede registrar un error en un archivo en el registro de aplicación.</span><span class="sxs-lookup"><span data-stu-id="82ba4-119">For example, a database application might record a file error in the application log.</span></span>|  
  
 <span data-ttu-id="82ba4-120">Para obtener más información acerca de cómo utilizar el Visor de eventos, administrar el registro de la aplicación y entender la información que contiene, vea la documentación de Windows.</span><span class="sxs-lookup"><span data-stu-id="82ba4-120">For more information about using Event Viewer, managing the application log, and understanding the information it presents, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="82ba4-121">**Para ver el registro de aplicación Windows**</span><span class="sxs-lookup"><span data-stu-id="82ba4-121">**To view the Windows application log**</span></span>  
  
 [<span data-ttu-id="82ba4-122">Ver el registro de aplicación de Windows &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="82ba4-122">View the Windows Application Log &#40;Windows&#41;</span></span>](../../relational-databases/performance/view-the-windows-application-log-windows-10.md)  
  
  
