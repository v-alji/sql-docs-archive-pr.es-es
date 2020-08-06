---
title: Explorador de soluciones control de código fuente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Visual SourceSafe
- SQL Server Management Studio [SQL Server], source control services
- source-controlled files [SQL Server]
- source controls [SQL Server Management Studio], services
- version control services [SQL Server]
- file source control services [SQL Server]
- VSS [Visual SourceSafe]
ms.assetid: 6373adb8-3d81-4945-a9fc-1d0d5799d29a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 46471ba8149c26f80e78006bc3a8befc2e81b416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674980"
---
# <a name="solution-explorer-source-control"></a><span data-ttu-id="fd68b-102">Control de código fuente del Explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="fd68b-102">Solution Explorer Source Control</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="fd68b-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]Explorador de soluciones puede integrarse en un sistema de control de código fuente independiente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Solution Explorer can be integrated into a separate source control system.</span></span> <span data-ttu-id="fd68b-104">Una vez que una solución o un proyecto se integra en un sistema de control de código fuente, se pueden controlar el acceso de archivos y las versiones de los scripts y las consultas en los proyectos.</span><span class="sxs-lookup"><span data-stu-id="fd68b-104">Once a solution or project is integrated into a source control system, you can control file access and versioning for the scripts and queries in your projects.</span></span>  
  
## <a name="solution-and-project-source-control"></a><span data-ttu-id="fd68b-105">Control de código fuente de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="fd68b-105">Solution and Project Source Control</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="fd68b-106">El control de código fuente hace referencia a un sistema en el que una pieza central de software del servidor almacena y realiza un seguimiento de las versiones de los archivos, además de controlar el acceso a esos archivos.</span><span class="sxs-lookup"><span data-stu-id="fd68b-106">Source control refers to a system in which a central piece of server software stores and tracks file versions, and also controls access to files.</span></span> <span data-ttu-id="fd68b-107">Un sistema típico de control de código fuente incluye un proveedor de control de código fuente y dos o más clientes de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-107">A typical source control system includes a source control provider and two or more source control clients.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="fd68b-108">se puede integrar con un servicio de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-108">can be integrated with a source control service.</span></span> <span data-ttu-id="fd68b-109">Esto significa que puede usar la herramienta como cliente del proveedor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-109">This means you can use the tool as a client for your source control provider.</span></span> <span data-ttu-id="fd68b-110">Es posible administrar fácilmente los proyectos individuales y de equipo sin salir del entorno.</span><span class="sxs-lookup"><span data-stu-id="fd68b-110">Without leaving the environment, you can manage your individual and team projects easily.</span></span> <span data-ttu-id="fd68b-111">El proveedor de control de código fuente no se incluye con [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd68b-111">The source control provider is not included with [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
#### <a name="to-select-a-source-control-provider"></a><span data-ttu-id="fd68b-112">Para seleccionar un proveedor de control de código fuente</span><span class="sxs-lookup"><span data-stu-id="fd68b-112">To select a source control provider</span></span>  
  
1.  <span data-ttu-id="fd68b-113">Instale la parte de cliente del proveedor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-113">Install the client portion of your source control provider.</span></span>  
  
2.  <span data-ttu-id="fd68b-114">En [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], en el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="fd68b-114">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="fd68b-115">En el cuadro de diálogo **Opciones** , expanda **control de código fuente**y, a continuación, haga clic en la página **selección de complemento** .</span><span class="sxs-lookup"><span data-stu-id="fd68b-115">In the **Options** dialog box, expand **Source Control**, and then click the **Plug-in Selection** page.</span></span>  
  
4.  <span data-ttu-id="fd68b-116">En el cuadro **complemento de control de código fuente actual** , seleccione el complemento de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-116">In the **Current source control plug-in** box, select the source control plug-in.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fd68b-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fd68b-117">In This Section</span></span>  
  
|<span data-ttu-id="fd68b-118">Tema</span><span class="sxs-lookup"><span data-stu-id="fd68b-118">Topic</span></span>|<span data-ttu-id="fd68b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd68b-119">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fd68b-120">Fundamentos del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="fd68b-120">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)|<span data-ttu-id="fd68b-121">Define la terminología básica de control de código fuente y explica los beneficios que supone para un proyecto el uso de los servicios de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-121">Defines basic source control terminology, and explains how your project can benefit from using source control services.</span></span>|  
|[<span data-ttu-id="fd68b-122">Agregar soluciones y proyectos al control de código fuente</span><span class="sxs-lookup"><span data-stu-id="fd68b-122">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)|<span data-ttu-id="fd68b-123">Explica cómo utilizar el entorno de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para agregar soluciones y proyectos al control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-123">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to add solutions and projects to source control.</span></span>|  
|[<span data-ttu-id="fd68b-124">Abrir soluciones y proyectos desde el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="fd68b-124">Open Solutions and Projects from Source Control</span></span>](../../2014/database-engine/open-solutions-and-projects-from-source-control.md)|<span data-ttu-id="fd68b-125">Explica cómo utilizar el entorno de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para abrir soluciones y proyectos controlados por código fuente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-125">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to open source-controlled solutions and projects.</span></span>|  
|[<span data-ttu-id="fd68b-126">Administrar desprotecciones</span><span class="sxs-lookup"><span data-stu-id="fd68b-126">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)|<span data-ttu-id="fd68b-127">Explica cómo desproteger soluciones y archivos desde el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-127">Explains how to check out solutions and files from source control.</span></span>|  
|[<span data-ttu-id="fd68b-128">Administrar protecciones</span><span class="sxs-lookup"><span data-stu-id="fd68b-128">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)|<span data-ttu-id="fd68b-129">Explica cómo proteger soluciones y archivos en el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fd68b-129">Explains how to check solutions and files into source control.</span></span>|  
|[<span data-ttu-id="fd68b-130">Establecer y recuperar información de versión</span><span class="sxs-lookup"><span data-stu-id="fd68b-130">Set and Retrieve Version Information</span></span>](../../2014/database-engine/set-and-retrieve-version-information.md)|<span data-ttu-id="fd68b-131">Explica cómo recuperar el historial de un proyecto o elemento, cómo recuperar una copia local de un elemento o cómo comparar dos versiones de un elemento.</span><span class="sxs-lookup"><span data-stu-id="fd68b-131">Explains how to retrieve the history of a project or item, retrieve a local copy of an item, or compare two item versions.</span></span>|  
|||  
  
## <a name="see-also"></a><span data-ttu-id="fd68b-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd68b-132">See Also</span></span>  
 <span data-ttu-id="fd68b-133">[Explorador de soluciones](../ssms/solution/solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="fd68b-133">[Solution Explorer](../ssms/solution/solution-explorer.md) </span></span>  
 <span data-ttu-id="fd68b-134">[Soluciones &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="fd68b-134">[Solutions &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span></span>  
 <span data-ttu-id="fd68b-135">[Proyectos &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="fd68b-135">[Projects &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="fd68b-136">Archivos que administran soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="fd68b-136">Files That Manage Solutions and Projects</span></span>](../ssms/solution/files-that-manage-solutions-and-projects.md)  
  
  
