---
title: Propiedades de Agente SQL Server (página Sistema de trabajo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.job.f1
ms.assetid: e171d13e-1302-4f0e-88be-67d656aec8d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 743a8d558e97e9ad83cfc66e9ef1adf2e1bc0c2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676299"
---
# <a name="sql-server-agent-properties-job-system-page"></a><span data-ttu-id="7706f-102">Propiedades de Agente SQL Server (página Sistema de trabajo)</span><span class="sxs-lookup"><span data-stu-id="7706f-102">SQL Server Agent Properties (Job System Page)</span></span>
  <span data-ttu-id="7706f-103">Utilice esta página para ver y modificar la forma en que el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servicio del agente administra los trabajos.</span><span class="sxs-lookup"><span data-stu-id="7706f-103">Use this page to view and modify how the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service manages jobs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7706f-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="7706f-104">Options</span></span>  
 <span data-ttu-id="7706f-105">**Intervalo de tiempo de espera de cierre (en segundos)**</span><span class="sxs-lookup"><span data-stu-id="7706f-105">**Shutdown time-out interval (in seconds)**</span></span>  
 <span data-ttu-id="7706f-106">Especifica el número de segundos que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espera a que los trabajos finalicen antes del cierre.</span><span class="sxs-lookup"><span data-stu-id="7706f-106">Specifies the number of seconds that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for jobs to complete before shutting down.</span></span> <span data-ttu-id="7706f-107">Si el trabajo sigue en ejecución después del intervalo especificado, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] detendrá de manera obligatoria el trabajo.</span><span class="sxs-lookup"><span data-stu-id="7706f-107">If the job is still running after the interval specified, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent forcefully stops the job.</span></span>  
  
 <span data-ttu-id="7706f-108">**Usar una cuenta de proxy de usuarios que no sean administradores**</span><span class="sxs-lookup"><span data-stu-id="7706f-108">**Use a non-administrator proxy account**</span></span>  
 <span data-ttu-id="7706f-109">Establece una cuenta de proxy de usuarios que no sean administradores para el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7706f-109">Sets a non-administrator proxy account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="7706f-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]y las versiones posteriores admiten varios servidores proxy; por lo tanto, esta opción solo es aplicable al administrar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Versiones del agente anteriores a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7706f-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="7706f-111">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="7706f-111">**User name**</span></span>  
 <span data-ttu-id="7706f-112">Escriba el nombre del usuario de la cuenta proxy de usuarios que no sean administradores.</span><span class="sxs-lookup"><span data-stu-id="7706f-112">Type the name of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7706f-113">admite varios servidores proxy; por tanto, esta opción solo es aplicable al administrar versiones del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7706f-113">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="7706f-114">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="7706f-114">**Password**</span></span>  
 <span data-ttu-id="7706f-115">Escriba la contraseña del usuario de la cuenta proxy de usuarios que no sean administradores.</span><span class="sxs-lookup"><span data-stu-id="7706f-115">Type the password of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="7706f-116">y las versiones posteriores admiten varios servidores proxy; por tanto, esta opción solo es aplicable al administrar versiones del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7706f-116">and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="7706f-117">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="7706f-117">**Domain**</span></span>  
 <span data-ttu-id="7706f-118">Escriba el dominio del usuario de la cuenta proxy de usuarios que no sean administradores.</span><span class="sxs-lookup"><span data-stu-id="7706f-118">Type the domain of the user for the non-administrative proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7706f-119">admite varios servidores proxy; por tanto, esta opción solo es aplicable al administrar versiones del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7706f-119">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7706f-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7706f-120">See Also</span></span>  
 [<span data-ttu-id="7706f-121">Implementar trabajos</span><span class="sxs-lookup"><span data-stu-id="7706f-121">Implement Jobs</span></span>](implement-jobs.md)  
  
  
