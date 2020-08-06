---
title: Servicio desconocido (pestaña iniciar sesión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e9b35cb5-d8ae-42ea-b59e-deedc99c4823
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0bda49cd95475d4f922f41ebe1701a814c3f60fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663883"
---
# <a name="unknown-service-log-on-tab"></a><span data-ttu-id="c0a33-102">Servicio desconocido (pestaña Iniciar sesión)</span><span class="sxs-lookup"><span data-stu-id="c0a33-102">Unknown Service (Log On Tab)</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="c0a33-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager no puede identificar este servicio.</span><span class="sxs-lookup"><span data-stu-id="c0a33-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is unable to identify this service.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c0a33-104">recibe información de los servicios del proveedor WMI del equipo que ejecuta el servicio.</span><span class="sxs-lookup"><span data-stu-id="c0a33-104">Configuration Manager receives service information from the WMI provider on the computer running the service.</span></span> <span data-ttu-id="c0a33-105">Se ha producido un error al leer las propiedades del servicio o éstas no están completas.</span><span class="sxs-lookup"><span data-stu-id="c0a33-105">Either there was an error while reading the service properties, or the service properties are not complete.</span></span> <span data-ttu-id="c0a33-106">Para solucionar el problema, intente cerrar y volver a abrir el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o compruebe el proveedor WMI del equipo en el que se ejecuta el servicio.</span><span class="sxs-lookup"><span data-stu-id="c0a33-106">To resolve the problem, try closing and reopening [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or check the WMI provider on the computer running the service.</span></span>  
  
 <span data-ttu-id="c0a33-107">El proveedor WMI es un componente de Windows.</span><span class="sxs-lookup"><span data-stu-id="c0a33-107">The WMI provider is a Windows component.</span></span> <span data-ttu-id="c0a33-108">Para obtener información sobre cómo comprobar los permisos en el proveedor de WMI, vea "Cómo: Configure WMI para mostrar Estado del Servidor en herramientas SQL Server" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0a33-108">For information on how to check permissions on the WMI provider, see "How to: Configure WMI to Show Server Status in SQL Server Tools" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="c0a33-109">Si cree que está viendo el servicio correcto, utilice la pestaña **Iniciar sesión** del cuadro de diálogo **Propiedades de Servicio desconocido** para especificar la cuenta utilizada por este servicio, así como para iniciar y detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="c0a33-109">If you believe you are viewing the correct service, use the **Log On** tab of the **Unknown Service Properties** dialog box to specify the account used by this service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0a33-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="c0a33-110">Options</span></span>  
 <span data-ttu-id="c0a33-111">**Cuenta de sistema local**</span><span class="sxs-lookup"><span data-stu-id="c0a33-111">**Local System account**</span></span>  
 <span data-ttu-id="c0a33-112">Especifique una cuenta de sistema local, que no requiere una contraseña.</span><span class="sxs-lookup"><span data-stu-id="c0a33-112">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="c0a33-113">No obstante, la cuenta del sistema local puede impedir la interacción del servicio con otros servidores, en función de los privilegios que se hayan concedido a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c0a33-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="c0a33-114">**Esta cuenta**</span><span class="sxs-lookup"><span data-stu-id="c0a33-114">**This account**</span></span>  
 <span data-ttu-id="c0a33-115">Especifique una cuenta de usuario local o de dominio que utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c0a33-115">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="c0a33-116">Se recomienda utilizar una cuenta de usuario de dominio que tenga derechos mínimos para los servicios.</span><span class="sxs-lookup"><span data-stu-id="c0a33-116">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="c0a33-117">Para obtener información acerca de cómo seleccionar una cuenta, vea el tema sobre la configuración de cuentas de servicios de Windows en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0a33-117">For information about selecting an account, "Setting Up Windows Service Accounts" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="c0a33-118">**Nombre de cuenta**</span><span class="sxs-lookup"><span data-stu-id="c0a33-118">**Account Name**</span></span>  
 <span data-ttu-id="c0a33-119">Escriba el nombre de la cuenta de usuario local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="c0a33-119">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="c0a33-120">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="c0a33-120">**Password**</span></span>  
 <span data-ttu-id="c0a33-121">Escriba la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c0a33-121">Type the password of the account.</span></span>  
  
 <span data-ttu-id="c0a33-122">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="c0a33-122">**Confirm password**</span></span>  
 <span data-ttu-id="c0a33-123">Escriba de nuevo la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c0a33-123">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="c0a33-124">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="c0a33-124">**Start**</span></span>  
 <span data-ttu-id="c0a33-125">Inicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="c0a33-125">Start the service.</span></span>  
  
 <span data-ttu-id="c0a33-126">**Detención**</span><span class="sxs-lookup"><span data-stu-id="c0a33-126">**Stop**</span></span>  
 <span data-ttu-id="c0a33-127">Detenga el servicio.</span><span class="sxs-lookup"><span data-stu-id="c0a33-127">Stop the service.</span></span>  
  
 <span data-ttu-id="c0a33-128">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="c0a33-128">**Pause**</span></span>  
 <span data-ttu-id="c0a33-129">Pause el servicio.</span><span class="sxs-lookup"><span data-stu-id="c0a33-129">Pause the service.</span></span>  
  
 <span data-ttu-id="c0a33-130">**Reanudar**</span><span class="sxs-lookup"><span data-stu-id="c0a33-130">**Resume**</span></span>  
 <span data-ttu-id="c0a33-131">Reanude un servicio en pausa.</span><span class="sxs-lookup"><span data-stu-id="c0a33-131">Resume a paused service.</span></span>  
  
  
