---
title: Propiedades de SQL Server Browser (pestaña Iniciar sesión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c77871ec-c2f4-4e4a-9a10-5aeb4ae70507
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c1f7d0cfd9e9b05a2a04f3c3e9efba687522298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743807"
---
# <a name="sql-server-browser-properties-log-on-tab"></a><span data-ttu-id="73199-102">Propiedades de SQL Server Browser (pestaña Iniciar sesión)</span><span class="sxs-lookup"><span data-stu-id="73199-102">SQL Server Browser Properties (Log On Tab)</span></span>
  <span data-ttu-id="73199-103">El programa Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecuta como un servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="73199-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> <span data-ttu-id="73199-104">El Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escucha las solicitudes entrantes de recursos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y proporciona información sobre las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="73199-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73199-105">El Explorador escucha en un puerto UDP y acepta solicitudes no autenticadas que usan el protocolo de resolución de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SSRP).</span><span class="sxs-lookup"><span data-stu-id="73199-105">Browser listens on a UDP port and accepts unauthenticated requests using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resolution Protocol (SSRP).</span></span>  
  
 <span data-ttu-id="73199-106">Cambiar la contraseña de una cuenta surte efecto inmediato, sin necesidad de reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="73199-106">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="73199-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="73199-107">Options</span></span>  
 <span data-ttu-id="73199-108">**Cuenta de sistema local**</span><span class="sxs-lookup"><span data-stu-id="73199-108">**Local System account**</span></span>  
 <span data-ttu-id="73199-109">Ejecute el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el contexto de seguridad de la cuenta Sistema local.</span><span class="sxs-lookup"><span data-stu-id="73199-109">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service in the security context of the Local System account.</span></span> <span data-ttu-id="73199-110">Si es posible, utilice en su lugar una cuenta con permisos limitados.</span><span class="sxs-lookup"><span data-stu-id="73199-110">When possible, use a low-permission account instead.</span></span>  
  
 <span data-ttu-id="73199-111">**Esta cuenta**</span><span class="sxs-lookup"><span data-stu-id="73199-111">**This account**</span></span>  
 <span data-ttu-id="73199-112">Especifique una cuenta de usuario local o de dominio que utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="73199-112">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="73199-113">Se recomienda utilizar una cuenta de usuario de dominio que tenga derechos mínimos para los servicios.</span><span class="sxs-lookup"><span data-stu-id="73199-113">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="73199-114">Para obtener información acerca de cómo seleccionar una cuenta, vea el tema sobre la configuración de cuentas de servicios de Windows en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73199-114">For information about selecting an account, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="73199-115">**Browse**</span><span class="sxs-lookup"><span data-stu-id="73199-115">**Browse**</span></span>  
 <span data-ttu-id="73199-116">Busque un usuario o una entidad de seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="73199-116">Browse for a user or built-in security principal.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="73199-117">Utilice una cuenta con permisos limitados.</span><span class="sxs-lookup"><span data-stu-id="73199-117">Use a low-permission account.</span></span> <span data-ttu-id="73199-118">Para obtener información sobre los permisos necesarios para el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea la sección sobre seguridad del [Servicio SQL Server Browser](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="73199-118">For information about the permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service, see the Security section of [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="73199-119">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="73199-119">**Password**</span></span>  
 <span data-ttu-id="73199-120">Escriba la contraseña de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="73199-120">Enter the password of the security principal.</span></span>  
  
 <span data-ttu-id="73199-121">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="73199-121">**Confirm password**</span></span>  
 <span data-ttu-id="73199-122">Confirme la contraseña de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="73199-122">Confirm the password of the security principal.</span></span>  
  
 <span data-ttu-id="73199-123">**Estado del servicio**</span><span class="sxs-lookup"><span data-stu-id="73199-123">**Service status**</span></span>  
 <span data-ttu-id="73199-124">Indica si el servicio está en ejecución, detenido o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="73199-124">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="73199-125">" **…** " indica que hay un cambio de estado pendiente.</span><span class="sxs-lookup"><span data-stu-id="73199-125">"**...**" indicates a state change is pending.</span></span>  
  
 <span data-ttu-id="73199-126">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="73199-126">**Start**</span></span>  
 <span data-ttu-id="73199-127">Inicie el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73199-127">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="73199-128">**Detención**</span><span class="sxs-lookup"><span data-stu-id="73199-128">**Stop**</span></span>  
 <span data-ttu-id="73199-129">Detenga el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73199-129">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="73199-130">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="73199-130">**Pause**</span></span>  
 <span data-ttu-id="73199-131">Pause el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73199-131">Pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="73199-132">**Reanudar**</span><span class="sxs-lookup"><span data-stu-id="73199-132">**Resume**</span></span>  
 <span data-ttu-id="73199-133">Reanude un servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pausado.</span><span class="sxs-lookup"><span data-stu-id="73199-133">Resume a paused [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73199-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73199-134">See Also</span></span>  
 [<span data-ttu-id="73199-135">Servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="73199-135">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
