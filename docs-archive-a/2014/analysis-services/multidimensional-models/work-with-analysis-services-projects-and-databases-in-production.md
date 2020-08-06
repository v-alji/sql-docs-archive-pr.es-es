---
title: Trabajar con proyectos de Analysis Services y bases de datos en un entorno de producción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, projects
ms.assetid: c589097f-ad29-4b97-8c7e-b8a910909c1a
author: minewiskan
ms.author: owend
ms.openlocfilehash: e9a2555511c422e5553662e2fcd292a5a2ec7c67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673343"
---
# <a name="working-with-analysis-services-projects-and-databases-in-a-production-environment"></a><span data-ttu-id="f7f54-102">Trabajar con bases de datos de proyectos de Analysis Services en un entorno de producción</span><span class="sxs-lookup"><span data-stu-id="f7f54-102">Working with Analysis Services Projects and Databases in a Production Environment</span></span>
  <span data-ttu-id="f7f54-103">Una vez que haya desarrollado e implementado la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] del proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , debe decidir cómo desea realizar cambios en los objetos de la base de datos implementada.</span><span class="sxs-lookup"><span data-stu-id="f7f54-103">After you have developed and deployed your [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database from your [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, you must decide how you wish to make changes to objects in the deployed database.</span></span> <span data-ttu-id="f7f54-104">Ciertos cambios, como los relacionados con los roles de seguridad, las particiones y la configuración del almacenamiento, se pueden hacer con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7f54-104">Certain changes, such changes related to security roles, partitioning, and storage settings, can be made using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="f7f54-105">Otros cambios, como la adición de atributos o jerarquías definidas por el usuario, solo se pueden hacer con [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]en el modo de proyecto o en el modo en línea.</span><span class="sxs-lookup"><span data-stu-id="f7f54-105">Other changes can only be made using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], either in project mode or in online mode (such as adding attributes or user-defined hierarchies).</span></span>  
  
 <span data-ttu-id="f7f54-106">Tan pronto como haga un cambio en una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] implementada mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en el modo en línea, el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que se usó para la implementación queda desusado.</span><span class="sxs-lookup"><span data-stu-id="f7f54-106">As soon as you make a change to a deployed [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project that was used for deployment becomes out of date.</span></span> <span data-ttu-id="f7f54-107">Si un programador hace cambios en el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y trata de implementar el proyecto modificado, se le solicitará que sobrescriba la base de datos completa.</span><span class="sxs-lookup"><span data-stu-id="f7f54-107">If a developer makes any changes within the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and attempts to deploy the modified project, the developer will be prompted to overwrite the entire database.</span></span> <span data-ttu-id="f7f54-108">Si el programador sobrescribe toda la base de datos, también tiene que procesarla.</span><span class="sxs-lookup"><span data-stu-id="f7f54-108">If the developer overwrites the entire database, it must also be processed.</span></span> <span data-ttu-id="f7f54-109">Todo esto se puede complicar si los cambios realizados directamente en la base de datos implementada por el personal de producción no han sido comunicados al equipo de desarrollo, ya que este último no comprenderá por qué sus cambios ya no aparecen en la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7f54-109">This issue becomes compounded if the changes made directly to the deployed database by the production staff were not communicated to the development team because they will not understand why their changes no longer appear in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="f7f54-110">Las herramientas de SQL Server 2005 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se pueden usar de varias maneras para evitar los problemas que conlleva esta situación.</span><span class="sxs-lookup"><span data-stu-id="f7f54-110">There are several ways in which you can use SQL Server [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tools to avoid the problems inherent in this situation.</span></span>  
  
-   <span data-ttu-id="f7f54-111">Método 1: siempre que se haga un cambio en una versión de producción de una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , use [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para crear un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] basado en la versión modificada de la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7f54-111">Method 1: Whenever a change is made to a production version of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, use [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to create a new [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project based on the modified version of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="f7f54-112">Este nuevo proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se puede registrar en el sistema de control de origen como copia maestra del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7f54-112">This new [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project can be checked into the source control system as the master copy of the project.</span></span> <span data-ttu-id="f7f54-113">Este método funcionará aunque el cambio se haya realizado en la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en el modo en línea.</span><span class="sxs-lookup"><span data-stu-id="f7f54-113">This method will work regardless of whether the change was made to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span>  
  
-   <span data-ttu-id="f7f54-114">Método 2: realice los cambios únicamente en una versión de producción de una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en el modo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7f54-114">Method 2: Only make changes to the production version of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in project mode.</span></span> <span data-ttu-id="f7f54-115">Con este método, puede usar las opciones disponibles en el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a fin de conservar los cambios realizados por [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], por ejemplo los roles de seguridad y la configuración del almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="f7f54-115">With this method, you can use options available to you in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard to preserve changes made by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], such as security roles and storage settings.</span></span> <span data-ttu-id="f7f54-116">Así se garantiza que la configuración relacionada con el diseño se conserva en el archivo del proyecto (la configuración del almacenamiento y los roles de seguridad se pueden omitir) y se usa el servidor en línea para la configuración del almacenamiento y los roles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f7f54-116">This ensures that the design-related settings are kept in the project file (storage settings and security roles can be ignored) and the online server is used for storage settings and security roles.</span></span>  
  
-   <span data-ttu-id="f7f54-117">Método 3: realice los cambios únicamente en una versión de producción de una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en el modo en línea.</span><span class="sxs-lookup"><span data-stu-id="f7f54-117">Method 3: Only make changes to the production version of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="f7f54-118">Puesto que las dos herramientas solo trabajan con el mismo servidor en línea, no hay posibilidad de obtener versiones diferentes no sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="f7f54-118">Since both tools are only working with the same online server, there are no possibilities of getting different version out of sync.</span></span>  
  
  