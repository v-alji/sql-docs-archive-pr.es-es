---
title: Propiedades de SQL Server (pestaña Iniciar sesión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 405073fc-eaa3-43c6-bf82-2cd58cacc1c3
author: stevestein
ms.author: sstein
ms.openlocfilehash: adec9ed7c69023218baa96ab8f8edbb6f2b365bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673404"
---
# <a name="sql-server-properties-log-on-tab"></a><span data-ttu-id="1d3ca-102">Propiedades de SQL Server (pestaña Iniciar sesión)</span><span class="sxs-lookup"><span data-stu-id="1d3ca-102">SQL Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="1d3ca-103">Utilice la pestaña **Iniciar sesión** del cuadro de diálogo **Propiedades de SQL Server** para especificar la cuenta que utiliza el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , cambiar la contraseña de una cuenta e iniciar y detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-103">Use the **Log On** tab of the **SQL Server Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="1d3ca-104">Cambiar la contraseña de una cuenta surte efecto inmediato.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-104">Changing the password of an account takes effect immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d3ca-105">Cuando cambie el nombre de cuenta utilizado por un servicio en una instancia en clúster, la nueva cuenta debe formar parte del grupo de dominios que haya especificado durante la instalación para el servicio modificado, o bien debe tener permiso para agregar miembros a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="1d3ca-106">Si no tiene permisos para modificar la pertenencia al grupo, póngase en contacto con el administrador del dominio.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="1d3ca-107">Para obtener información acerca de cómo seleccionar una cuenta para ejecutar el servicio, vea el tema sobre la configuración de cuentas de servicios de Windows en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d3ca-107">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1d3ca-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="1d3ca-108">Options</span></span>  
 <span data-ttu-id="1d3ca-109">**Cuenta integrada**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-109">**Built-in account**</span></span>  
 <span data-ttu-id="1d3ca-110">**Sistema local**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-110">**Local System**</span></span>  
 -   <span data-ttu-id="1d3ca-111">Especifique la cuenta de sistema local.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-111">Specify the local system account.</span></span> <span data-ttu-id="1d3ca-112">Esta cuenta no requiere ninguna contraseña.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-112">This account does not require a password.</span></span> <span data-ttu-id="1d3ca-113">No obstante, la cuenta del sistema local puede impedir la interacción del servicio con otros servidores, en función de los privilegios que se hayan concedido a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="1d3ca-114">**Servicio local**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-114">**Local Service**</span></span>  
 -   <span data-ttu-id="1d3ca-115">Especifique la cuenta de servicio local.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-115">Specify the local service account.</span></span> <span data-ttu-id="1d3ca-116">Esta cuenta no requiere ninguna contraseña.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-116">This account does not require a password.</span></span> <span data-ttu-id="1d3ca-117">No obstante, la cuenta de servicio local puede impedir la interacción del servicio con otros servidores, en función de los privilegios que se hayan concedido a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-117">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="1d3ca-118">**Servicio de red**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-118">**Network Service**</span></span>  
 -   <span data-ttu-id="1d3ca-119">Se recomienda no utilizar la cuenta de servicio de red para los servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d3ca-119">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="1d3ca-120">Las cuentas de usuario local o de usuario de dominio son más adecuadas para estos servicios.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-120">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="1d3ca-121">**Esta cuenta**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-121">**This account**</span></span>  
 <span data-ttu-id="1d3ca-122">Especifique una cuenta de usuario local o de dominio que utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-122">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="1d3ca-123">Se recomienda utilizar una cuenta de usuario de dominio que tenga derechos mínimos para los servicios.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-123">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="1d3ca-124">**Nombre de cuenta**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-124">**Account Name**</span></span>  
 <span data-ttu-id="1d3ca-125">Escriba el nombre de la cuenta de usuario local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-125">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="1d3ca-126">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-126">**Password**</span></span>  
 <span data-ttu-id="1d3ca-127">Escriba la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-127">Type the password of the account.</span></span>  
  
 <span data-ttu-id="1d3ca-128">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-128">**Confirm password**</span></span>  
 <span data-ttu-id="1d3ca-129">Escriba de nuevo la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-129">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="1d3ca-130">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-130">**Start**</span></span>  
 <span data-ttu-id="1d3ca-131">Inicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-131">Start the service.</span></span>  
  
 <span data-ttu-id="1d3ca-132">**Detención**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-132">**Stop**</span></span>  
 <span data-ttu-id="1d3ca-133">Detenga el servicio.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-133">Stop the service.</span></span>  
  
 <span data-ttu-id="1d3ca-134">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-134">**Pause**</span></span>  
 <span data-ttu-id="1d3ca-135">Pause el servicio.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-135">Pause the service.</span></span>  
  
 <span data-ttu-id="1d3ca-136">**Reanudar**</span><span class="sxs-lookup"><span data-stu-id="1d3ca-136">**Resume**</span></span>  
 <span data-ttu-id="1d3ca-137">Reanude un servicio en pausa.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-137">Resume a paused service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1d3ca-138">De forma predeterminada, solo los miembros del grupo local de administradores pueden iniciar, detener, pausar, reanudar o reiniciar un servicio.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-138">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="1d3ca-139">Para conceder la capacidad de administrar servicios a usuarios que no son administradores, vea [CÓMO: Conceder a los usuarios derechos para administrar servicios en la familia Windows Server 2003](https://support.microsoft.com/kb/325349).</span><span class="sxs-lookup"><span data-stu-id="1d3ca-139">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="1d3ca-140">El proceso es similar en las demás versiones de Windows.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-140">(The process is similar on other versions of Windows.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d3ca-141">Si al iniciar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], aparece el error de WMI "no implementado [0x80004001]", podría indicar que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no está instalado en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="1d3ca-141">When starting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a WMI error containing the phrase "not implemented [0x80004001]" may indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not installed on the target computer.</span></span>  
  
  
