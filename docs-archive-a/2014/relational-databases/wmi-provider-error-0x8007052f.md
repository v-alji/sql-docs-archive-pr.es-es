---
title: Error de WMI 0x8007052f | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- 0x8007052f (WMI error)
ms.assetid: a33f12bd-15c4-42a8-b343-de44c3e87729
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d6e857e0ccaad9b6f34bbdc9b88aea2e6d7291d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752014"
---
# <a name="wmi-error-0x8007052f"></a><span data-ttu-id="4b839-102">Error de WMI 0x8007052f</span><span class="sxs-lookup"><span data-stu-id="4b839-102">WMI Error 0x8007052f</span></span>
    
## <a name="details"></a><span data-ttu-id="4b839-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4b839-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b839-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="4b839-104">Product Name</span></span>|<span data-ttu-id="4b839-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b839-105">SQL Server</span></span>|  
|<span data-ttu-id="4b839-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4b839-106">Event ID</span></span>|<span data-ttu-id="4b839-107">0x8007052f</span><span class="sxs-lookup"><span data-stu-id="4b839-107">0x8007052f</span></span>|  
|<span data-ttu-id="4b839-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="4b839-108">Event Source</span></span>|<span data-ttu-id="4b839-109">Error de proveedor WMI</span><span class="sxs-lookup"><span data-stu-id="4b839-109">WMI Provider Error</span></span>|  
|<span data-ttu-id="4b839-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4b839-110">Component</span></span>|<span data-ttu-id="4b839-111">Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b839-111">SQL Server Configuration Manager</span></span>|  
|<span data-ttu-id="4b839-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4b839-112">Symbolic Name</span></span>|<span data-ttu-id="4b839-113">N/D</span><span class="sxs-lookup"><span data-stu-id="4b839-113">NA</span></span>|  
|<span data-ttu-id="4b839-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4b839-114">Message Text</span></span>|<span data-ttu-id="4b839-115">Error de inicio de sesión: restricción de cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="4b839-115">Logon failure: user account restriction.</span></span> <span data-ttu-id="4b839-116">Razones posibles: no se admiten contraseñas en blanco, restricciones en las horas de inicio de sesión, o se ha aplicado una restricción de directiva.</span><span class="sxs-lookup"><span data-stu-id="4b839-116">Possible reasons are blank passwords not allowed, login hour restrictions, or a policy restriction has been enforced.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4b839-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="4b839-117">Explanation</span></span>  
 <span data-ttu-id="4b839-118">Este error puede producirse al usar el Administrador de configuración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para pasar a las cuentas integradas (Servicio de red, Servicio local o Sistema local) cuando [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se ejecuta en un clúster de Windows Server o un controlador de dominio de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4b839-118">This error can occur when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager to switch to the built-in accounts (Network Service, Local Service, or Local System) when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is running on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="4b839-119">No ejecute servicios en cuentas integradas en un clúster de Windows Server o un controlador de dominio de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4b839-119">Do not run services under built-in accounts on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="4b839-120">Para obtener recomendaciones sobre cuentas de servicio, vea el tema Configurar cuentas de servicio de Windows en los Libros en pantalla de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b839-120">For recommendations on service accounts, see the topic Setting Up Windows Service Accounts in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b839-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4b839-121">User Action</span></span>  
 <span data-ttu-id="4b839-122">Configure [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para usar una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="4b839-122">Configure [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use a domain account.</span></span>  
  
  
