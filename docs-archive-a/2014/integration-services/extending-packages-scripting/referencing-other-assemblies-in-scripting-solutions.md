---
title: Hacer referencia a otros ensamblados en soluciones de scripting | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, .NET Framework
- Script task [Integration Services], adding references
- referencing custom assemblies
- SSIS Script task, VisualBasic namespace
- assemblies [Integration Services]
- VisualBasic namespace
- Script task [Integration Services], VisualBasic namespace
- Microsoft.VisualBasic namespace
- Script task [Integration Services], .NET Framework
- .NET Framework [Integration Services]
- referencing Web services
ms.assetid: 9b655bcd-19f6-43d8-9f89-1b4d299c6380
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 685bbaa62da88e84cd848eb49dcf5bedb03d5390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669755"
---
# <a name="referencing-other-assemblies-in-scripting-solutions"></a><span data-ttu-id="4fc17-102">Hacer referencia a otros ensamblados en soluciones de scripting</span><span class="sxs-lookup"><span data-stu-id="4fc17-102">Referencing Other Assemblies in Scripting Solutions</span></span>
  <span data-ttu-id="4fc17-103">La biblioteca de clases de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] proporciona al desarrollador de script un conjunto eficaz de herramientas para implementar una funcionalidad personalizada en los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fc17-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library provides the script developer with a powerful set of tools for implementing custom functionality in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="4fc17-104">Tanto la tarea como el componente Script también pueden usar ensamblados administrados personalizados.</span><span class="sxs-lookup"><span data-stu-id="4fc17-104">The Script task and the Script component can also use custom managed assemblies.</span></span>

> [!NOTE]
>  <span data-ttu-id="4fc17-105">Para permitir que los paquetes usen los objetos y métodos de un servicio web, use el comando **Agregar referencia web** disponible en [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="4fc17-105">To enable your packages to use the objects and methods from a Web service, use the **Add Web Reference** command available in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="4fc17-106">En versiones anteriores de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], tenía que generar una clase de proxy para utilizar un servicio web.</span><span class="sxs-lookup"><span data-stu-id="4fc17-106">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you had to generate a proxy class to use a Web service.</span></span>

## <a name="using-a-managed-assembly"></a><span data-ttu-id="4fc17-107">Utilizar un ensamblado administrado</span><span class="sxs-lookup"><span data-stu-id="4fc17-107">Using a Managed Assembly</span></span>
 <span data-ttu-id="4fc17-108">Para que [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] busque en tiempo de diseño un ensamblado administrado, debe efectuar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4fc17-108">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find a managed assembly at design time, you must do the following steps:</span></span>

1.  <span data-ttu-id="4fc17-109">Almacene el ensamblado administrado en una carpeta del equipo.</span><span class="sxs-lookup"><span data-stu-id="4fc17-109">Store the managed assembly in any folder on your computer.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="4fc17-110">En versiones anteriores de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], podría agregar solamente una referencia a un ensamblado administrado que estuviera almacenado en la carpeta %windir%\Microsoft.NET\Framework\vx.x.xxxxx o %ProgramFiles%\Microsoft SQL Server\100\SDK\Assemblies.</span><span class="sxs-lookup"><span data-stu-id="4fc17-110">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you could only add a reference to a managed assembly that was stored in the %windir%\Microsoft.NET\Framework\vx.x.xxxxx folder or the %ProgramFiles%\Microsoft SQL Server\100\SDK\Assemblies folder.</span></span>

2.  <span data-ttu-id="4fc17-111">Agregue una referencia al ensamblado administrado.</span><span class="sxs-lookup"><span data-stu-id="4fc17-111">Add a reference to the managed assembly.</span></span>

     <span data-ttu-id="4fc17-112">Para agregar la referencia, en VSTA, en el cuadro de diálogo **Agregar referencia**, en la pestaña **Examinar**, busque y agregue el ensamblado administrado.</span><span class="sxs-lookup"><span data-stu-id="4fc17-112">To add the reference, in VSTA, in the **Add Reference** dialog box, on the **Browse** tab, locate and add the managed assembly.</span></span>

 <span data-ttu-id="4fc17-113">Para que [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] busque en tiempo de ejecución el ensamblado administrado, debe efectuar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4fc17-113">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find the managed assembly at run time, you must do the following steps:</span></span>

1.  <span data-ttu-id="4fc17-114">Firme un ensamblado administrado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="4fc17-114">Sign the managed assembly with a strong name.</span></span>

2.  <span data-ttu-id="4fc17-115">Instale el ensamblado en la memoria caché de ensamblados global en el equipo en el que se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="4fc17-115">Install the assembly in the global assembly cache on the computer on which the package is run.</span></span>

     <span data-ttu-id="4fc17-116">Para obtener más información, consulte [Generar, implementar y depurar objetos personalizados](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="4fc17-116">For more information, see [Building, Deploying, and Debugging Custom Objects](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span></span>

## <a name="using-the-microsoft-net-framework-class-library"></a><span data-ttu-id="4fc17-117">Utilizar la Biblioteca de clases de Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4fc17-117">Using the Microsoft .NET Framework Class Library</span></span>
 <span data-ttu-id="4fc17-118">Tanto la tarea como el componente Script pueden aprovechar todos los demás objetos y la funcionalidad expuesta por la biblioteca de clases de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fc17-118">The Script task and the Script component can take advantage of all the other objects and functionality exposed by the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="4fc17-119">Por ejemplo, mediante [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], puede recuperar información acerca del entorno e interactuar con el equipo que está ejecutando el paquete.</span><span class="sxs-lookup"><span data-stu-id="4fc17-119">For example, by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can retrieve information about your environment and interact with the computer that is running the package.</span></span>

 <span data-ttu-id="4fc17-120">En esta lista se describen algunas de las clases más utilizadas de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4fc17-120">This list describes several of the more frequently used [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes:</span></span>

-   <span data-ttu-id="4fc17-121">`System.Data`Contiene la arquitectura ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="4fc17-121">`System.Data` Contains the ADO.NET architecture.</span></span>

-   <span data-ttu-id="4fc17-122">`System.IO`Proporciona una interfaz para el sistema de archivos y las secuencias.</span><span class="sxs-lookup"><span data-stu-id="4fc17-122">`System.IO` Provides an interface to the file system and streams.</span></span>

-   <span data-ttu-id="4fc17-123">`System.Windows.Forms`Proporciona la creación de formularios.</span><span class="sxs-lookup"><span data-stu-id="4fc17-123">`System.Windows.Forms` Provides form creation.</span></span>

-   <span data-ttu-id="4fc17-124">`System.Text.RegularExpressions`Proporciona clases para trabajar con expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="4fc17-124">`System.Text.RegularExpressions` Provides classes for working with regular expressions.</span></span>

-   <span data-ttu-id="4fc17-125">`System.Environment`Devuelve información acerca del equipo local, el usuario actual y la configuración del equipo y del usuario.</span><span class="sxs-lookup"><span data-stu-id="4fc17-125">`System.Environment` Returns information about the local computer, the current user, and computer and user settings.</span></span>

-   <span data-ttu-id="4fc17-126">`System.Net`Proporciona comunicaciones de red.</span><span class="sxs-lookup"><span data-stu-id="4fc17-126">`System.Net` Provides network communications.</span></span>

-   <span data-ttu-id="4fc17-127">`System.DirectoryServices`Expone Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4fc17-127">`System.DirectoryServices` Exposes Active Directory.</span></span>

-   <span data-ttu-id="4fc17-128">`System.Drawing`Proporciona bibliotecas de manipulación de imágenes extensas.</span><span class="sxs-lookup"><span data-stu-id="4fc17-128">`System.Drawing` Provides extensive image manipulation libraries.</span></span>

-   <span data-ttu-id="4fc17-129">`System.Threading`Habilita la programación multiproceso.</span><span class="sxs-lookup"><span data-stu-id="4fc17-129">`System.Threading` Enables multithreaded programming.</span></span>

 <span data-ttu-id="4fc17-130">Para obtener más información acerca de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], vea MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="4fc17-130">For more information about the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see the MSDN Library.</span></span>

<span data-ttu-id="4fc17-131">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4fc17-131">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4fc17-132">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="4fc17-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4fc17-133">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="4fc17-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4fc17-134">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="4fc17-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fc17-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4fc17-135">See Also</span></span>
 [<span data-ttu-id="4fc17-136">Ampliar paquetes con scripting</span><span class="sxs-lookup"><span data-stu-id="4fc17-136">Extending Packages with Scripting</span></span>](extending-packages-with-scripting.md)


