---
title: Descripción de las diferencias entre la ejecución local y remota | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- packages [Integration Services], troubleshooting
ms.assetid: 610ee7d9-4fea-4aba-9395-57add826923b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 399584c790f4c5a5dd136121c58a5ff7743f4969
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745376"
---
# <a name="understanding-the-differences-between-local-and-remote-execution"></a><span data-ttu-id="b55e7-102">Descripción de las diferencias entre la ejecución local y remota</span><span class="sxs-lookup"><span data-stu-id="b55e7-102">Understanding the Differences between Local and Remote Execution</span></span>
  <span data-ttu-id="b55e7-103">Los desarrolladores y administradores de paquetes deben ser conscientes de que existen restricciones en cuanto a la ubicación donde se ejecuta un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b55e7-103">Package developers and administrators should be aware that there are restrictions related to where an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package runs.</span></span>  
  
-   <span data-ttu-id="b55e7-104">**Un paquete se ejecuta en el mismo equipo que el programa que lo inicia**.</span><span class="sxs-lookup"><span data-stu-id="b55e7-104">**A package runs on the same computer as the program that launches it**.</span></span> <span data-ttu-id="b55e7-105">El paquete se ejecuta en el equipo local aunque un programa cargue un paquete almacenado de forma remota en otro servidor.</span><span class="sxs-lookup"><span data-stu-id="b55e7-105">Even when a program loads a package that is stored remotely on another server, the package runs on the local computer.</span></span>  
  
-   <span data-ttu-id="b55e7-106">**Solo puede ejecutar un paquete fuera del entorno de desarrollo en un equipo con Integration Services instalado**.</span><span class="sxs-lookup"><span data-stu-id="b55e7-106">**You can only run a package outside the development environment on a computer that has Integration Services installed**.</span></span> <span data-ttu-id="b55e7-107">No puede ejecutar paquetes fuera de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en un equipo cliente que no tenga instalado [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], y puede que las condiciones de su licencia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no le permitan instalar [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en equipos adicionales.</span><span class="sxs-lookup"><span data-stu-id="b55e7-107">You cannot run packages outside of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing may not permit you to install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b55e7-108">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] es un componente de servidor y no se puede distribuir entre equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="b55e7-108">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is a server component and is not redistributable to client computers.</span></span> <span data-ttu-id="b55e7-109">Para ejecutar paquetes desde un equipo cliente, necesita iniciarlos de manera que se garantice que los paquetes se ejecutan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b55e7-109">To run packages from a client computer, you need to launch them in a manner that ensures that the packages run on the server.</span></span>  
  
 <span data-ttu-id="b55e7-110">Para obtener más información sobre la carga y ejecución de un paquete guardado, vea:</span><span class="sxs-lookup"><span data-stu-id="b55e7-110">For more information about loading and running a saved package, see:</span></span>  
  
-   [<span data-ttu-id="b55e7-111">Cargar y ejecutar un paquete local mediante programación</span><span class="sxs-lookup"><span data-stu-id="b55e7-111">Loading and Running a Local Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
  
-   [<span data-ttu-id="b55e7-112">Cargar y ejecutar un paquete remoto mediante programación</span><span class="sxs-lookup"><span data-stu-id="b55e7-112">Loading and Running a Remote Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
  
 <span data-ttu-id="b55e7-113">Para obtener más información sobre cómo ejecutar un paquete y cargar su salida en un programa personalizado, vea:</span><span class="sxs-lookup"><span data-stu-id="b55e7-113">For more information about running a package and loading its output into a custom program, see:</span></span>  
  
-   [<span data-ttu-id="b55e7-114">Cargar la salida de un paquete local</span><span class="sxs-lookup"><span data-stu-id="b55e7-114">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
<span data-ttu-id="b55e7-115">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b55e7-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b55e7-116">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="b55e7-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b55e7-117">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="b55e7-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b55e7-118">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="b55e7-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b55e7-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b55e7-119">See Also</span></span>  
 <span data-ttu-id="b55e7-120">[Cargar y ejecutar un paquete local mediante programación](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="b55e7-120">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 <span data-ttu-id="b55e7-121">[Cargar y ejecutar un paquete remoto mediante programación](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="b55e7-121">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="b55e7-122">Cargar la salida de un paquete local</span><span class="sxs-lookup"><span data-stu-id="b55e7-122">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
