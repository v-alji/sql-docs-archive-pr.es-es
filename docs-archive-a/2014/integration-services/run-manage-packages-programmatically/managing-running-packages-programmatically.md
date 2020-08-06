---
title: Administrar los paquetes en ejecución mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], managing
- running packages [Integration Services]
ms.assetid: 0e91f4ac-6f29-40d7-8c28-9b82e4802c35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95c5f9c28b407631764d64523b37a6295870542a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749376"
---
# <a name="managing-running-packages-programmatically"></a><span data-ttu-id="d1ebd-102">Administrar los paquetes en ejecución mediante programación</span><span class="sxs-lookup"><span data-stu-id="d1ebd-102">Managing Running Packages Programmatically</span></span>
  <span data-ttu-id="d1ebd-103">Cuando trabaja con paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] mediante programación, puede que desee determinar los paquetes que se están ejecutando en ese momento.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine which packages are currently running.</span></span> <span data-ttu-id="d1ebd-104">La clase <xref:Microsoft.SqlServer.Dts.Runtime.Application> del espacio de nombres <xref:Microsoft.SqlServer.Dts.Runtime> proporciona métodos y clases para satisfacer estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides methods and classes to satisfy these requirements.</span></span>  
  
 <span data-ttu-id="d1ebd-105">Para obtener más información sobre la supervisión de paquetes, consulte [Administración de paquetes &#40;servicio SSIS&#41;](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="d1ebd-105">For more information about monitoring packages, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="d1ebd-106">Todos los métodos descritos en este tema requieren una referencia al ensamblado `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-106">All the methods discussed in this topic require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="d1ebd-107">Después de agregar la referencia en un proyecto nuevo, importe el <xref:Microsoft.SqlServer.Dts.Runtime> espacio de nombres con una `using` `Imports` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-107">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d1ebd-108">Los métodos de la clase <xref:Microsoft.SqlServer.Dts.Runtime.Application> para trabajar con el almacén de paquetes SSIS solamente admiten ".", localhost o el nombre del servidor local.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-108">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="d1ebd-109">No puede utilizar "(local)".</span><span class="sxs-lookup"><span data-stu-id="d1ebd-109">You cannot use "(local)".</span></span>  
  
## <a name="determining-which-packages-are-currently-running"></a><span data-ttu-id="d1ebd-110">Determinar los paquetes que se están ejecutando</span><span class="sxs-lookup"><span data-stu-id="d1ebd-110">Determining Which Packages Are Currently Running</span></span>  
 <span data-ttu-id="d1ebd-111">Para determinar qué paquetes se están ejecutando actualmente en el servidor especificado, llame al método <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-111">To determine which packages are currently running on the specified server, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A> method.</span></span> <span data-ttu-id="d1ebd-112">Este método devuelve una colección <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> de objetos <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage>.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-112">This method returns a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection of <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d1ebd-113">Los administradores ven todos los paquetes que se están ejecutando actualmente en el equipo; el resto de usuarios solamente ve los paquetes que han iniciado ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-113">Administrators see all packages that are currently executing on the computer; other users see only those packages that they have launched.</span></span>  
  
## <a name="working-with-running-packages"></a><span data-ttu-id="d1ebd-114">Trabajar con paquetes en ejecución</span><span class="sxs-lookup"><span data-stu-id="d1ebd-114">Working with Running Packages</span></span>  
 <span data-ttu-id="d1ebd-115">Una vez determinados los paquetes que se están ejecutando actualmente, puede recuperar información sobre los paquetes y solicitar que se detenga un paquete.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-115">After you have determined which packages are currently running, you can retrieve information about the packages and request that a package be stopped.</span></span>  
  
### <a name="getting-information-about-a-running-package"></a><span data-ttu-id="d1ebd-116">Obtener información sobre un paquete en ejecución</span><span class="sxs-lookup"><span data-stu-id="d1ebd-116">Getting Information about a Running Package</span></span>  
 <span data-ttu-id="d1ebd-117">Al recorrer en iteración la colección <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages>, puede utilizar las propiedades del objeto <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> para buscar un paquete u obtener información adicional sobre los paquetes que se están ejecutando:</span><span class="sxs-lookup"><span data-stu-id="d1ebd-117">As you iterate through the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection, you can use the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to locate a package or to obtain additional information about the packages that are running:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionDuration%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionStartTime%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.InstanceID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageDescription%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageName%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.UserName%2A>  
  
### <a name="stopping-a-running-package"></a><span data-ttu-id="d1ebd-118">Detener un paquete en ejecución</span><span class="sxs-lookup"><span data-stu-id="d1ebd-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="d1ebd-119">Puede llamar al método <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> de un objeto <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> para solicitar que se detenga el paquete.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-119">You can call the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to request that the package be stopped.</span></span> <span data-ttu-id="d1ebd-120">Es posible que se produzca un retraso entre el momento en el que se emite una solicitud de detención y el momento en el que realmente se detiene el paquete.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-120">There may be a delay between the time that a stop request is issued and the time that the package actually stops.</span></span>  
  
<span data-ttu-id="d1ebd-121">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d1ebd-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d1ebd-122">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="d1ebd-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d1ebd-123">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="d1ebd-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d1ebd-124">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ebd-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1ebd-125">See Also</span></span>  
 <span data-ttu-id="d1ebd-126">[Administración de paquetes &#40;servicio SSIS&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="d1ebd-126">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="d1ebd-127">Enumerar los paquetes disponibles mediante programación</span><span class="sxs-lookup"><span data-stu-id="d1ebd-127">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
