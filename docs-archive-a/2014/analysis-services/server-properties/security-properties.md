---
title: Propiedades de seguridad | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], properties
- SecurityPackageList property
- BuiltinAdminsAreServerAdmins property
- DisableClientImpersonation property
- ErrorMessageMode property
- RequiredProtectionLevel property
- ServiceAccountIsServerAdmin property
- RequireClientAuthentication property
ms.assetid: 2fc7fe10-0cbb-49ac-aa8c-8ec3f7a7705f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 20133554835803908a340c5369eb66e86b119d72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672298"
---
# <a name="security-properties"></a><span data-ttu-id="a6485-102">Propiedades de seguridad</span><span class="sxs-lookup"><span data-stu-id="a6485-102">Security Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="a6485-103">admite las propiedades de servidor de seguridad que aparecen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a6485-103">supports the security server properties listed in the following table.</span></span> <span data-ttu-id="a6485-104">Para obtener más información sobre las propiedades de servidor adicionales y cómo establecerlas, vea [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="a6485-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="a6485-105">**Se aplica a:** modo de servidor multidimensional y tabular</span><span class="sxs-lookup"><span data-stu-id="a6485-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a6485-106">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a6485-106">Properties</span></span>  
 `RequireClientAuthentication`  
 <span data-ttu-id="a6485-107">Propiedad booleana que indica si se necesita la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="a6485-107">A Boolean property that indicates whether client authentication is required.</span></span>  
  
 <span data-ttu-id="a6485-108">El valor predeterminado de esta propiedad es True, lo que indica que se necesita la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="a6485-108">The default value for this property is True, which indicates that client authentication is required.</span></span>  
  
 `SecurityPackageList`  
 <span data-ttu-id="a6485-109">Propiedad de cadena que contiene una lista separada por comas de los paquetes SSPI utilizados por el servidor para la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="a6485-109">A string property that contains a comma-separated list of SSPI packages used by server for client authentication.</span></span>  
  
 `DisableClientImpersonation`  
 <span data-ttu-id="a6485-110">Propiedad booleana que indica si la suplantación del cliente (por ejemplo desde los procedimientos almacenados) está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a6485-110">A Boolean property that indicates whether client impersonation (for example, from stored procedures) is disabled.</span></span>  
  
 <span data-ttu-id="a6485-111">El valor predeterminado de esta propiedad es False, lo que indica que la suplantación del cliente está habilitada.</span><span class="sxs-lookup"><span data-stu-id="a6485-111">The default value for this property is False, which indicates that client impersonation is enabled.</span></span>  
  
 `BuiltinAdminsAreServerAdmins`  
 <span data-ttu-id="a6485-112">Propiedad booleana que indica si los miembros del grupo de administradores del equipo local son administradores de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6485-112">A Boolean property that indicates whether members of the local machine administrators group are [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrators.</span></span>  
  
 `ServiceAccountIsServerAdmin`  
 <span data-ttu-id="a6485-113">Propiedad booleana que indica si la cuenta de servicio es un administrador de servidor.</span><span class="sxs-lookup"><span data-stu-id="a6485-113">A Boolean property that indicates whether the service account is a server administrator.</span></span>  
  
 <span data-ttu-id="a6485-114">El valor predeterminado de esta propiedad es True, lo que indica que la cuenta de servicio es un administrador de servidor.</span><span class="sxs-lookup"><span data-stu-id="a6485-114">The default value for this property is True, which indicates that the service account is a server administrator.</span></span>  
  
 `ErrorMessageMode`  
 <span data-ttu-id="a6485-115">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6485-115">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="a6485-116">Propiedad de entero de 32 bits con firma que define el nivel de protección necesario para todas las solicitudes de cliente.</span><span class="sxs-lookup"><span data-stu-id="a6485-116">A signed 32-bit integer property that defines the required protection level for all client requests.</span></span> <span data-ttu-id="a6485-117">Esta propiedad tiene uno de los valores indicados en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="a6485-117">This property has one of the values listed in the following table.</span></span>  
  
|<span data-ttu-id="a6485-118">Value</span><span class="sxs-lookup"><span data-stu-id="a6485-118">Value</span></span>|<span data-ttu-id="a6485-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6485-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6485-120">*0*</span><span class="sxs-lookup"><span data-stu-id="a6485-120">*0*</span></span>|<span data-ttu-id="a6485-121">Ninguno, se permite texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="a6485-121">None, clear text allowed.</span></span>|  
|<span data-ttu-id="a6485-122">*1*</span><span class="sxs-lookup"><span data-stu-id="a6485-122">*1*</span></span>|<span data-ttu-id="a6485-123">(Valor predeterminado) Se exige cifrado, no se permite iniciar sesión con texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="a6485-123">(Default) Encryption required, no clear-text logging.</span></span>|  
|<span data-ttu-id="a6485-124">*2*</span><span class="sxs-lookup"><span data-stu-id="a6485-124">*2*</span></span>|<span data-ttu-id="a6485-125">Se permiten las solicitudes con texto no cifrado, pero solo con firma (protección más débil que el cifrado).</span><span class="sxs-lookup"><span data-stu-id="a6485-125">Clear-text requests allowed but only with signatures (weaker protection than encryption).</span></span>|  
  
 `AdministrativeDataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="a6485-126">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6485-126">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6485-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6485-127">See Also</span></span>  
 <span data-ttu-id="a6485-128">[Configurar las propiedades del servidor en Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="a6485-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="a6485-129">Determinar el modo de servidor de una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a6485-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
