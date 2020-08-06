---
title: Propiedades de Analysis Server (pestaña Iniciar sesión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: a82e0c98-efaa-4b0b-9582-3c879ee42444
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8db5576e48e7f12ef1733175875d2cd065e376fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750413"
---
# <a name="analysis-server-properties-log-on-tab"></a><span data-ttu-id="99221-102">Propiedades de Analysis Server (pestaña Iniciar sesión)</span><span class="sxs-lookup"><span data-stu-id="99221-102">Analysis Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="99221-103">Utilice la pestaña **Iniciar sesión** del cuadro de diálogo **Propiedades de Analysis Server** para especificar la cuenta que utiliza el servicio [!INCLUDE[ssAS](../../includes/ssas-md.md)] así como para iniciar y detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="99221-103">Use the **Log On** tab of the **Analysis Server Properties** dialog box to specify the account used by the [!INCLUDE[ssAS](../../includes/ssas-md.md)] service, and to start and stop the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99221-104">Cuando cambie el **Nombre de cuenta** utilizado por un servicio en una instancia en clúster, la nueva cuenta debe formar parte del grupo de dominios que haya especificado durante la instalación del servicio modificado, o bien debe tener permiso para agregar miembros a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="99221-104">When changing the **Account Name** used by a service on a clustered instance, the new account must either be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="99221-105">Si no tiene permisos para modificar la pertenencia al grupo, póngase en contacto con el administrador del dominio.</span><span class="sxs-lookup"><span data-stu-id="99221-105">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="99221-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="99221-106">Options</span></span>  
 <span data-ttu-id="99221-107">**Cuenta de sistema local**</span><span class="sxs-lookup"><span data-stu-id="99221-107">**Local System account**</span></span>  
 <span data-ttu-id="99221-108">Especifique una cuenta de sistema local, que no requiere una contraseña.</span><span class="sxs-lookup"><span data-stu-id="99221-108">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="99221-109">No obstante, la cuenta del sistema local puede restringir la interacción del servicio con otros servidores, en función de los privilegios que se le hayan concedido.</span><span class="sxs-lookup"><span data-stu-id="99221-109">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="99221-110">**Esta cuenta**</span><span class="sxs-lookup"><span data-stu-id="99221-110">**This account**</span></span>  
 <span data-ttu-id="99221-111">Especifique una cuenta de usuario local o de dominio que utilice la autenticación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="99221-111">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="99221-112">recomienda utilizar una cuenta de usuario de dominio que tenga derechos mínimos para los servicios.</span><span class="sxs-lookup"><span data-stu-id="99221-112">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="99221-113">Para obtener información acerca de cómo seleccionar una cuenta, busque el tema sobre cómo configurar cuentas de servicios de Windows en los Libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="99221-113">For information about selecting an account, search Books Online for the topic Setting Up Windows Service Accounts.</span></span>  
  
 <span data-ttu-id="99221-114">**Nombre de cuenta**</span><span class="sxs-lookup"><span data-stu-id="99221-114">**Account Name**</span></span>  
 <span data-ttu-id="99221-115">Escriba el nombre de la cuenta de usuario local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="99221-115">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="99221-116">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="99221-116">**Password**</span></span>  
 <span data-ttu-id="99221-117">Escriba la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="99221-117">Type the password of the account.</span></span>  
  
 <span data-ttu-id="99221-118">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="99221-118">**Confirm password**</span></span>  
 <span data-ttu-id="99221-119">Escriba de nuevo la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="99221-119">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="99221-120">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="99221-120">**Start**</span></span>  
 <span data-ttu-id="99221-121">Inicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="99221-121">Start the service.</span></span>  
  
 <span data-ttu-id="99221-122">**Detención**</span><span class="sxs-lookup"><span data-stu-id="99221-122">**Stop**</span></span>  
 <span data-ttu-id="99221-123">Detenga el servicio.</span><span class="sxs-lookup"><span data-stu-id="99221-123">Stop the service.</span></span>  
  
 <span data-ttu-id="99221-124">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="99221-124">**Pause**</span></span>  
 <span data-ttu-id="99221-125">Pause el servicio.</span><span class="sxs-lookup"><span data-stu-id="99221-125">Pause the service.</span></span>  
  
 <span data-ttu-id="99221-126">**Reanudar**</span><span class="sxs-lookup"><span data-stu-id="99221-126">**Resume**</span></span>  
 <span data-ttu-id="99221-127">Reanude un servicio en pausa.</span><span class="sxs-lookup"><span data-stu-id="99221-127">Resume a paused service.</span></span>  
  
  
