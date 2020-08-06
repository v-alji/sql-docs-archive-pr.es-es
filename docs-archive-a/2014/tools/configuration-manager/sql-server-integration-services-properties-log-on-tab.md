---
title: Propiedades de SQL Server Integration Services (pestaña Iniciar sesión) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c0eb1b87-6bb0-475e-8492-0fd3c3f910ea
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfef02a82872ea1df25e7ccb8526e488aaa5f406
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748432"
---
# <a name="sql-server-integration-services-properties-log-on-tab"></a><span data-ttu-id="bbd26-102">Propiedades de SQL Server Integration Services (pestaña Iniciar sesión)</span><span class="sxs-lookup"><span data-stu-id="bbd26-102">SQL Server Integration Services Properties (Log On Tab)</span></span>
  <span data-ttu-id="bbd26-103">Use la pestaña **Iniciar sesión** del cuadro de diálogo [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]**Propiedades** para especificar la cuenta que usa el servicio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], así como para iniciar y detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="bbd26-103">Use the **Log On** tab of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** dialog box to specify the account used by the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bbd26-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="bbd26-104">Options</span></span>  
 <span data-ttu-id="bbd26-105">**Cuenta de sistema local**</span><span class="sxs-lookup"><span data-stu-id="bbd26-105">**Local System account**</span></span>  
 <span data-ttu-id="bbd26-106">Especifique una cuenta de sistema local, que no requiere una contraseña.</span><span class="sxs-lookup"><span data-stu-id="bbd26-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="bbd26-107">No obstante, la cuenta del sistema local puede restringir la interacción del servicio con otros servidores, en función de los privilegios que se le hayan concedido.</span><span class="sxs-lookup"><span data-stu-id="bbd26-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="bbd26-108">**Esta cuenta**</span><span class="sxs-lookup"><span data-stu-id="bbd26-108">**This account**</span></span>  
 <span data-ttu-id="bbd26-109">Especifique una cuenta de usuario local o de dominio que utilice la autenticación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="bbd26-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="bbd26-110">recomienda utilizar una cuenta de usuario de dominio que tenga derechos mínimos para los servicios.</span><span class="sxs-lookup"><span data-stu-id="bbd26-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="bbd26-111">Para obtener información acerca de cómo seleccionar una cuenta, busque el tema sobre cómo configurar cuentas de servicios de Windows en los Libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="bbd26-111">For information about selecting an account, search Books Online for the topic, "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="bbd26-112">**Nombre de cuenta**</span><span class="sxs-lookup"><span data-stu-id="bbd26-112">**Account Name**</span></span>  
 <span data-ttu-id="bbd26-113">Escriba el nombre de la cuenta de usuario local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="bbd26-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="bbd26-114">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="bbd26-114">**Password**</span></span>  
 <span data-ttu-id="bbd26-115">Escriba la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="bbd26-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="bbd26-116">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="bbd26-116">**Confirm password**</span></span>  
 <span data-ttu-id="bbd26-117">Escriba de nuevo la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="bbd26-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="bbd26-118">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="bbd26-118">**Start**</span></span>  
 <span data-ttu-id="bbd26-119">Inicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="bbd26-119">Start the service.</span></span>  
  
 <span data-ttu-id="bbd26-120">**Detención**</span><span class="sxs-lookup"><span data-stu-id="bbd26-120">**Stop**</span></span>  
 <span data-ttu-id="bbd26-121">Detenga el servicio.</span><span class="sxs-lookup"><span data-stu-id="bbd26-121">Stop the service.</span></span>  
  
 <span data-ttu-id="bbd26-122">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="bbd26-122">**Pause**</span></span>  
 <span data-ttu-id="bbd26-123">Pause el servicio.</span><span class="sxs-lookup"><span data-stu-id="bbd26-123">Pause the service.</span></span>  
  
 <span data-ttu-id="bbd26-124">**Reanudar**</span><span class="sxs-lookup"><span data-stu-id="bbd26-124">**Resume**</span></span>  
 <span data-ttu-id="bbd26-125">Reanude un servicio en pausa.</span><span class="sxs-lookup"><span data-stu-id="bbd26-125">Resume a paused service.</span></span>  
  
  
