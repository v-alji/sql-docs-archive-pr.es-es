---
title: Administrar roles de paquete mediante programación (servicio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, roles
- roles [Integration Services]
- packages [Integration Services], roles
ms.assetid: 2e0ca0d5-d4f5-421d-b17d-a48b37b923e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dff54f3f90d9e008ae21c83c2a8fdc3f7440a5c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749375"
---
# <a name="managing-package-roles-programmatically-ssis-service"></a><span data-ttu-id="27aed-102">Administrar roles de paquete mediante programación (servicio SSIS)</span><span class="sxs-lookup"><span data-stu-id="27aed-102">Managing Package Roles Programmatically (SSIS Service)</span></span>
  <span data-ttu-id="27aed-103">Cuando trabaja mediante programación con paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], puede determinar qué roles están disponibles para aplicar a los paquetes o bien determinar o establecer los roles que se aplican a un paquete individual.</span><span class="sxs-lookup"><span data-stu-id="27aed-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine which roles are available to apply to packages, or to determine or set the roles applied to an individual package.</span></span> <span data-ttu-id="27aed-104">La clase <xref:Microsoft.SqlServer.Dts.Runtime.Application> del espacio de nombres <xref:Microsoft.SqlServer.Dts.Runtime> proporciona diferentes métodos para satisfacer estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="27aed-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>

 <span data-ttu-id="27aed-105">Los roles se aplican solo a paquetes almacenados en la base de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb**.</span><span class="sxs-lookup"><span data-stu-id="27aed-105">Roles apply only to packages stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb** database.</span></span> <span data-ttu-id="27aed-106">Para obtener más información acerca de los roles de paquete, consulte [Integration Services Roles &#40;SSIS Service&#41; (Roles de Integration Services &#40;servicio SSIS&#41;)](../security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="27aed-106">For more information about package roles, see [Integration Services Roles &#40;SSIS Service&#41;](../security/integration-services-roles-ssis-service.md).</span></span>

 <span data-ttu-id="27aed-107">Todos los métodos descritos en este tema requieren una referencia al ensamblado `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="27aed-107">All the methods discussed in this topic require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="27aed-108">Después de agregar la referencia en un proyecto nuevo, importe el espacio de nombres <xref:Microsoft.SqlServer.Dts.Runtime> mediante una instrucción `using` o `Imports`.</span><span class="sxs-lookup"><span data-stu-id="27aed-108">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace by using a `using` or `Imports` statement.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="27aed-109">Los métodos de la clase <xref:Microsoft.SqlServer.Dts.Runtime.Application> para trabajar con el almacén de paquetes SSIS solamente admiten ".", localhost o el nombre del servidor local.</span><span class="sxs-lookup"><span data-stu-id="27aed-109">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="27aed-110">No puede utilizar "(local)".</span><span class="sxs-lookup"><span data-stu-id="27aed-110">You cannot use "(local)".</span></span>

## <a name="determining-which-roles-are-available"></a><span data-ttu-id="27aed-111">Determinar los roles disponibles</span><span class="sxs-lookup"><span data-stu-id="27aed-111">Determining Which Roles Are Available</span></span>
 <span data-ttu-id="27aed-112">Para determinar qué roles están disponibles para los paquetes almacenados en un servidor determinado, llame al método <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerRoles%2A> de la clase <xref:Microsoft.SqlServer.Dts.Runtime.Application>.</span><span class="sxs-lookup"><span data-stu-id="27aed-112">To determine which roles are available for the packages stored on a particular server, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerRoles%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class.</span></span>

## <a name="determining-which-roles-are-assigned"></a><span data-ttu-id="27aed-113">Determinar los roles asignados</span><span class="sxs-lookup"><span data-stu-id="27aed-113">Determining Which Roles Are Assigned</span></span>
 <span data-ttu-id="27aed-114">Para determinar qué roles se han asignado ya a un paquete determinado, llame al método <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageRoles%2A>.</span><span class="sxs-lookup"><span data-stu-id="27aed-114">To determine which roles have already been assigned to a particular package, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageRoles%2A> method.</span></span> <span data-ttu-id="27aed-115">Para asignar roles a un paquete, llame al método <xref:Microsoft.SqlServer.Dts.Runtime.Application.SetPackageRoles%2A>.</span><span class="sxs-lookup"><span data-stu-id="27aed-115">To assign roles to a package, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.SetPackageRoles%2A> method.</span></span>

<span data-ttu-id="27aed-116">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="27aed-116">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="27aed-117">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="27aed-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="27aed-118">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="27aed-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="27aed-119">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="27aed-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="27aed-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27aed-120">See Also</span></span>
 [<span data-ttu-id="27aed-121">Roles de Integration Services &#40;servicio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="27aed-121">Integration Services Roles &#40;SSIS Service&#41;</span></span>](../security/integration-services-roles-ssis-service.md)


