---
title: Acceso al servicio de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- viewing packages while running
- displaying packacges while running
- security [Integration Services], running packages
- packages [Integration Services], security
- current packages running
- Integration Services packages, security
- SQL Server Integration Services packages, security
ms.assetid: 1088aafc-14c5-4e7d-9930-606a24c3049b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7dd6fbed4bedc285069306ab4c400f0f67f9f293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669818"
---
# <a name="access-to-the-integration-services-service"></a><span data-ttu-id="d4148-102">Acceso al servicio Integration Services</span><span class="sxs-lookup"><span data-stu-id="d4148-102">Access to the Integration Services Service</span></span>
  <span data-ttu-id="d4148-103">Los niveles de protección de paquetes pueden limitar quién puede editar y ejecutar un paquete.</span><span class="sxs-lookup"><span data-stu-id="d4148-103">Package protection levels can limit who is allowed to edit and execute a package.</span></span> <span data-ttu-id="d4148-104">Es necesaria protección adicional para limitar quién puede ver la lista de paquetes actualmente en ejecución en un servidor y quién puede detener dicha ejecución en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4148-104">Additional protection is needed to limit who can view the list of packages currently running on a server and who can stop currently executing packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="d4148-105">utiliza el servicio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para mostrar los paquetes que se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="d4148-105">uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service to list running packages.</span></span> <span data-ttu-id="d4148-106">Los miembros del grupo Administradores de Windows pueden ver y detener todos los paquetes en ejecución.</span><span class="sxs-lookup"><span data-stu-id="d4148-106">Members of the Windows Administrators group can view and stop all currently running packages.</span></span> <span data-ttu-id="d4148-107">Los usuarios que no sean miembros del grupo Administradores solo pueden ver y detener los paquetes que han iniciado ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="d4148-107">Users who are not members of the Administrators group can view and stop only packages that they started.</span></span>  
  
 <span data-ttu-id="d4148-108">Es importante restringir el acceso a los equipos que ejecutan un servicio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , especialmente un servicio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que puede mostrar carpetas remotas.</span><span class="sxs-lookup"><span data-stu-id="d4148-108">It is important to restrict access to computers that run an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service, especially an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service that can enumerate remote folders.</span></span> <span data-ttu-id="d4148-109">Cualquier usuario autenticado puede solicitar la enumeración de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="d4148-109">Any authenticated user can request the enumeration of packages.</span></span> <span data-ttu-id="d4148-110">Aunque el servicio no encuentre el servicio, el servicio enumera las carpetas.</span><span class="sxs-lookup"><span data-stu-id="d4148-110">Even if the service doesn not find the service, the service enumerates folders.</span></span> <span data-ttu-id="d4148-111">Estos nombres de carpeta pueden ser útiles para un usuario malintencionado.</span><span class="sxs-lookup"><span data-stu-id="d4148-111">These folder names may be useful to a malicious user.</span></span> <span data-ttu-id="d4148-112">Si un administrador configura el servicio para que enumere las carpetas en un equipo remoto, los usuarios también podrán ver los nombres de las carpetas que normalmente no podrían ver.</span><span class="sxs-lookup"><span data-stu-id="d4148-112">If an administrator has configured the service to enumerate folders on a remote machine, users may also be able to see folder names that they would normally not be able to see.</span></span>  
  
  
