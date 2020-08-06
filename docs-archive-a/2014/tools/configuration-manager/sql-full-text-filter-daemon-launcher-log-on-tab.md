---
title: Selector de demonio de filtro de texto completo de SQL (pestaña Iniciar sesión) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 13e260f9-a75f-430b-88a3-959ddcead8fe
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb3f23907e96214929617bf2923e46148c0ab1f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676758"
---
# <a name="sql-full-text-filter-daemon-launcher-log-on-tab"></a><span data-ttu-id="791f6-102">Selector del demonio de filtro de texto completo de SQL (pestaña Iniciar sesión)</span><span class="sxs-lookup"><span data-stu-id="791f6-102">SQL Full-text Filter Daemon Launcher (Log On Tab)</span></span>
  <span data-ttu-id="791f6-103">Desde [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], la búsqueda de texto completo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliza el servicio Selector de demonio de filtro de texto completo de SQL (iniciador FDHOST).</span><span class="sxs-lookup"><span data-stu-id="791f6-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text search.</span></span> <span data-ttu-id="791f6-104">Este servicio debe estar ejecutándose si se utiliza la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="791f6-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="791f6-105">Para obtener información sobre los procesos de host de demonio de filtro, vea "Arquitectura de la búsqueda de texto completo" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="791f6-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="791f6-106">Utilice la pestaña **Iniciar sesión** del cuadro de diálogo **Propiedades de Selector del demonio de filtro de texto completo de SQL** para especificar la cuenta que utiliza el servicio de búsqueda en texto completo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , cambiar la contraseña de una cuenta e iniciar y detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="791f6-106">Use the **Log On** tab of the **SQL Full-text Filter Daemon Launcher  Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="791f6-107">El cambio de la contraseña de una cuenta surte efecto después de reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="791f6-107">Changing the password of an account takes affect after restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="791f6-108">Cuando cambie el nombre de cuenta utilizado por un servicio en una instancia en clúster, la nueva cuenta debe formar parte del grupo de dominios que haya especificado durante la instalación del servicio, o bien debe tener permiso para agregar miembros a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="791f6-108">When changing the account name used by a service on a clustered instance, either the new account must be a member of the domain group specified during setup for the service, or you must have permission to add members to that group.</span></span> <span data-ttu-id="791f6-109">Si no tiene permisos para modificar la pertenencia al grupo, póngase en contacto con el administrador del dominio.</span><span class="sxs-lookup"><span data-stu-id="791f6-109">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="791f6-110">Para obtener información acerca de cómo seleccionar una cuenta para ejecutar el servicio, vea el tema sobre la configuración de cuentas de servicios de Windows en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="791f6-110">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="791f6-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="791f6-111">Options</span></span>  
 <span data-ttu-id="791f6-112">**Cuenta integrada**</span><span class="sxs-lookup"><span data-stu-id="791f6-112">**Built-in account**</span></span>  
 <span data-ttu-id="791f6-113">**Sistema local**</span><span class="sxs-lookup"><span data-stu-id="791f6-113">**Local System**</span></span>  
 <span data-ttu-id="791f6-114">Especifique la cuenta de sistema local.</span><span class="sxs-lookup"><span data-stu-id="791f6-114">Specify the local system account.</span></span> <span data-ttu-id="791f6-115">Esta cuenta no requiere ninguna contraseña.</span><span class="sxs-lookup"><span data-stu-id="791f6-115">This account does not require a password.</span></span> <span data-ttu-id="791f6-116">No obstante, la cuenta del sistema local puede impedir la interacción del servicio con otros servidores, en función de los privilegios que se hayan concedido a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="791f6-116">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="791f6-117">**Servicio local**</span><span class="sxs-lookup"><span data-stu-id="791f6-117">**Local Service**</span></span>  
 <span data-ttu-id="791f6-118">Especifique la cuenta de servicio local.</span><span class="sxs-lookup"><span data-stu-id="791f6-118">Specify the local service account.</span></span> <span data-ttu-id="791f6-119">Esta cuenta no requiere ninguna contraseña.</span><span class="sxs-lookup"><span data-stu-id="791f6-119">This account does not require a password.</span></span> <span data-ttu-id="791f6-120">No obstante, la cuenta de servicio local puede impedir la interacción del servicio con otros servidores, en función de los privilegios que se hayan concedido a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="791f6-120">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="791f6-121">**Servicio de red**</span><span class="sxs-lookup"><span data-stu-id="791f6-121">**Network Service**</span></span>  
 <span data-ttu-id="791f6-122">Se recomienda no utilizar la cuenta de servicio de red para los servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="791f6-122">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="791f6-123">Las cuentas de usuario local o de usuario de dominio son más adecuadas para estos servicios.</span><span class="sxs-lookup"><span data-stu-id="791f6-123">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="791f6-124">**Esta cuenta**</span><span class="sxs-lookup"><span data-stu-id="791f6-124">**This account**</span></span>  
 <span data-ttu-id="791f6-125">Especifique una cuenta de usuario local o de dominio que utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="791f6-125">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="791f6-126">Se recomienda utilizar una cuenta de usuario de dominio que tenga derechos mínimos para los servicios.</span><span class="sxs-lookup"><span data-stu-id="791f6-126">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="791f6-127">**Nombre de cuenta**</span><span class="sxs-lookup"><span data-stu-id="791f6-127">**Account Name**</span></span>  
 <span data-ttu-id="791f6-128">Escriba el nombre de la cuenta de usuario local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="791f6-128">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="791f6-129">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="791f6-129">**Password**</span></span>  
 <span data-ttu-id="791f6-130">Escriba la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="791f6-130">Type the password of the account.</span></span>  
  
 <span data-ttu-id="791f6-131">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="791f6-131">**Confirm password**</span></span>  
 <span data-ttu-id="791f6-132">Escriba de nuevo la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="791f6-132">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="791f6-133">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="791f6-133">**Start**</span></span>  
 <span data-ttu-id="791f6-134">Inicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="791f6-134">Start the service.</span></span>  
  
 <span data-ttu-id="791f6-135">**Detención**</span><span class="sxs-lookup"><span data-stu-id="791f6-135">**Stop**</span></span>  
 <span data-ttu-id="791f6-136">Detenga el servicio.</span><span class="sxs-lookup"><span data-stu-id="791f6-136">Stop the service.</span></span>  
  
 <span data-ttu-id="791f6-137">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="791f6-137">**Pause**</span></span>  
 <span data-ttu-id="791f6-138">Pause el servicio.</span><span class="sxs-lookup"><span data-stu-id="791f6-138">Pause the service.</span></span> <span data-ttu-id="791f6-139">No disponible para este servicio.</span><span class="sxs-lookup"><span data-stu-id="791f6-139">Not available for this service.</span></span>  
  
 <span data-ttu-id="791f6-140">**Reanudar**</span><span class="sxs-lookup"><span data-stu-id="791f6-140">**Resume**</span></span>  
 <span data-ttu-id="791f6-141">Reanude un servicio en pausa.</span><span class="sxs-lookup"><span data-stu-id="791f6-141">Resume a paused service.</span></span>  
  
  
