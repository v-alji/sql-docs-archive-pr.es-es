---
title: Propiedades de Agente SQL Server (pestaña Iniciar sesión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 01fc6329-5d6b-4186-9565-395f375477bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd899e8824adacd07fa1d8d7d51b2143d10cadd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672329"
---
# <a name="sql-server-agent-properties-log-on-tab"></a><span data-ttu-id="24dd8-102">Propiedades de Agente SQL Server (pestaña Iniciar sesión)</span><span class="sxs-lookup"><span data-stu-id="24dd8-102">SQL Server Agent Properties (Log On Tab)</span></span>
  <span data-ttu-id="24dd8-103">Utilice la pestaña **Iniciar sesión** del cuadro de diálogo **Propiedades de Agente SQL Server** para especificar la cuenta que utiliza el servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , así como para iniciar y detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="24dd8-103">Use the **Log On** tab of the **SQL Server Agent Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and to start and stop the service.</span></span> <span data-ttu-id="24dd8-104">Cambiar la contraseña de una cuenta surte efecto inmediato, sin necesidad de reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="24dd8-104">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24dd8-105">Cuando cambie el nombre de cuenta utilizado por un servicio en una instancia en clúster, la nueva cuenta debe formar parte del grupo de dominios que haya especificado durante la instalación para el servicio modificado, o bien debe tener permiso para agregar miembros a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="24dd8-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="24dd8-106">Si no tiene permisos para modificar la pertenencia al grupo, póngase en contacto con el administrador del dominio.</span><span class="sxs-lookup"><span data-stu-id="24dd8-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="24dd8-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="24dd8-107">Options</span></span>  
 <span data-ttu-id="24dd8-108">**Cuenta de sistema local**</span><span class="sxs-lookup"><span data-stu-id="24dd8-108">**Local System account**</span></span>  
 <span data-ttu-id="24dd8-109">Especifique una cuenta de sistema local, que no requiere una contraseña.</span><span class="sxs-lookup"><span data-stu-id="24dd8-109">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="24dd8-110">No obstante, la cuenta del sistema local puede restringir la interacción del servicio con otros servidores, en función de los privilegios que se le hayan concedido.</span><span class="sxs-lookup"><span data-stu-id="24dd8-110">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="24dd8-111">**Esta cuenta**</span><span class="sxs-lookup"><span data-stu-id="24dd8-111">**This account**</span></span>  
 <span data-ttu-id="24dd8-112">Especifique una cuenta de usuario local o de dominio que utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="24dd8-112">Specify a local or domain user account that uses Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="24dd8-113">recomienda utilizar una cuenta de usuario de dominio que tenga derechos mínimos para los servicios.</span><span class="sxs-lookup"><span data-stu-id="24dd8-113">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="24dd8-114">Para obtener información acerca de cómo seleccionar una cuenta, vea el tema sobre la configuración de cuentas de servicios de Windows en los Libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="24dd8-114">For information about selecting an account, search Books Online for "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="24dd8-115">**Nombre de cuenta**</span><span class="sxs-lookup"><span data-stu-id="24dd8-115">**Account Name**</span></span>  
 <span data-ttu-id="24dd8-116">Escriba el nombre de la cuenta de usuario local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="24dd8-116">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="24dd8-117">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="24dd8-117">**Password**</span></span>  
 <span data-ttu-id="24dd8-118">Escriba la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="24dd8-118">Type the password of the account.</span></span>  
  
 <span data-ttu-id="24dd8-119">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="24dd8-119">**Confirm password**</span></span>  
 <span data-ttu-id="24dd8-120">Escriba de nuevo la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="24dd8-120">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="24dd8-121">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="24dd8-121">**Start**</span></span>  
 <span data-ttu-id="24dd8-122">Inicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="24dd8-122">Start the service.</span></span>  
  
 <span data-ttu-id="24dd8-123">**Detención**</span><span class="sxs-lookup"><span data-stu-id="24dd8-123">**Stop**</span></span>  
 <span data-ttu-id="24dd8-124">Detenga el servicio.</span><span class="sxs-lookup"><span data-stu-id="24dd8-124">Stop the service.</span></span>  
  
 <span data-ttu-id="24dd8-125">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="24dd8-125">**Pause**</span></span>  
 <span data-ttu-id="24dd8-126">Pause el servicio.</span><span class="sxs-lookup"><span data-stu-id="24dd8-126">Pause the service.</span></span>  
  
 <span data-ttu-id="24dd8-127">**Reanudar**</span><span class="sxs-lookup"><span data-stu-id="24dd8-127">**Resume**</span></span>  
 <span data-ttu-id="24dd8-128">Reanude un servicio en pausa.</span><span class="sxs-lookup"><span data-stu-id="24dd8-128">Resume a paused service.</span></span>  
  
  
