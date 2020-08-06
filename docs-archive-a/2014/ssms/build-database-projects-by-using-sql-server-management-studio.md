---
title: Generar proyectos de bases de datos mediante SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], database projects
- database projects [SQL Server]
- projects [SQL Server Management Studio], about projects
- projects [SQL Server Management Studio]
ms.assetid: c2e80045-894d-44cf-b65c-e547ed738947
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3ddf3f61e69623716b2987c5c4d849398e822d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661798"
---
# <a name="build-database-projects-by-using-sql-server-management-studio"></a><span data-ttu-id="1092c-102">Generar proyectos de bases de datos mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1092c-102">Build Database Projects by Using SQL Server Management Studio</span></span>
  <span data-ttu-id="1092c-103">Un proyecto de scripts de base de datos es un conjunto organizado de scripts, información de conexión y plantillas asociado a una base de datos o a parte de ella.</span><span class="sxs-lookup"><span data-stu-id="1092c-103">A database script project is an organized set of scripts, connection information, and templates that are all associated with a database or one part of a database.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="1092c-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] proporciona [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para administrar y diseñar bases de datos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en el contexto de un proyecto de script.</span><span class="sxs-lookup"><span data-stu-id="1092c-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provides the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for administering and designing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] databases within the context of a script project.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1092c-105">incluye diseñadores, editores, guías y asistentes para ayudar a los usuarios a desarrollar, implementar y mantener bases de datos.</span><span class="sxs-lookup"><span data-stu-id="1092c-105">includes designers, editors, guides and wizards to assist users in developing, deploying and maintaining databases.</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="1092c-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1092c-106">SQL Server Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1092c-107">es un conjunto de herramientas administrativas que permite administrar los componentes que pertenecen a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1092c-107">is a suite of administrative tools for managing the components belonging to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1092c-108">Este entorno integrado permite a los usuarios realizar varias tareas, como realizar copias de seguridad de los datos, editar consultas y automatizar funciones comunes en una misma interfaz.</span><span class="sxs-lookup"><span data-stu-id="1092c-108">This integrated environment allows users to perform a variety of tasks, such as backing up data, editing queries, and automating common functions within a single interface.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1092c-109">incluye las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="1092c-109">includes the following tools:</span></span>  
  
-   <span data-ttu-id="1092c-110">El Editor de código es un editor de script completo que sirve para escribir y modificar scripts.</span><span class="sxs-lookup"><span data-stu-id="1092c-110">Code Editor is a rich script editor for writing and editing scripts.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1092c-111">proporciona cuatro versiones del Editor de código: el Editor de consultas del [!INCLUDE[ssDE](../includes/ssde-md.md)] para scripts [!INCLUDE[tsql](../includes/tsql-md.md)] , el Editor de consultas de MDX, el Editor de consultas de MDX y el Editor de consultas de XML/A.</span><span class="sxs-lookup"><span data-stu-id="1092c-111">provides four versions of the Code Editor; the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor for [!INCLUDE[tsql](../includes/tsql-md.md)] scripts, the DMX Query Editor, the MDX Query Editor, and the XML/A Query Editor.</span></span>  
  
-   <span data-ttu-id="1092c-112">El Explorador de objetos sirve para buscar, modificar e incluir en scripts objetos que pertenecen a instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]o ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="1092c-112">Object Explorer for locating, modifying, scripting or running objects belonging to instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1092c-113">El Explorador de plantillas sirve para buscar plantillas y crear scripts para ellas.</span><span class="sxs-lookup"><span data-stu-id="1092c-113">Template Explorer for locating and scripting templates.</span></span>  
  
-   <span data-ttu-id="1092c-114">El Explorador de soluciones sirve para organizar y almacenar scripts relacionados como partes de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="1092c-114">Solution Explorer for organizing and storing related scripts as parts of a project.</span></span>  
  
-   <span data-ttu-id="1092c-115">La Ventana Propiedades sirve para mostrar las propiedades actuales de los objetos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="1092c-115">Properties Window for displaying the current properties of selected objects.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1092c-116">permite desarrollar procesos de trabajo de manera eficaz al proporcionar:</span><span class="sxs-lookup"><span data-stu-id="1092c-116">supports efficient work processes by providing:</span></span>  
  
-   <span data-ttu-id="1092c-117">Acceso sin conexión.</span><span class="sxs-lookup"><span data-stu-id="1092c-117">Disconnected access.</span></span> <span data-ttu-id="1092c-118">Puede escribir y modificar scripts sin conectarse a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1092c-118">You can write and edit scripts without connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1092c-119">Creación de scripts desde cualquier cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1092c-119">Scripting from any dialog box.</span></span> <span data-ttu-id="1092c-120">Puede crear un script desde cualquier cuadro de diálogo para que pueda leer, modificar, almacenar y reutilizar los scripts después de crearlos.</span><span class="sxs-lookup"><span data-stu-id="1092c-120">You can create a script from any dialog box so that you can read, modify, store and reuse the scripts after you create them.</span></span>  
  
-   <span data-ttu-id="1092c-121">Cuadros de diálogo no modales.</span><span class="sxs-lookup"><span data-stu-id="1092c-121">Nonmodal dialog boxes.</span></span> <span data-ttu-id="1092c-122">Al obtener acceso a un cuadro de diálogo de interfaz de usuario, puede examinar otros recursos en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] sin cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1092c-122">When you access a UI dialog box you can browse other resources in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] without closing the dialog box.</span></span>  
  
## <a name="solutions-and-script-projects"></a><span data-ttu-id="1092c-123">Soluciones y proyectos de scripts</span><span class="sxs-lookup"><span data-stu-id="1092c-123">Solutions and Script Projects</span></span>  
 <span data-ttu-id="1092c-124">El Explorador de soluciones es una utilidad que sirve para almacenar y volver a abrir soluciones de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="1092c-124">Solution Explorer is a utility to store and reopen database solutions.</span></span> <span data-ttu-id="1092c-125">Las soluciones organizan proyectos de scripts y archivos relacionados.</span><span class="sxs-lookup"><span data-stu-id="1092c-125">Solutions organize related script projects and files.</span></span> <span data-ttu-id="1092c-126">Los proyectos de script almacenan archivos de scripts de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , plantillas SQL, información de conexión y otros archivos varios.</span><span class="sxs-lookup"><span data-stu-id="1092c-126">Script projects store [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] script files, SQL templates, connection information and other miscellaneous files.</span></span> <span data-ttu-id="1092c-127">Cuando se guarda un script en un proyecto de scripts, los usuarios pueden:</span><span class="sxs-lookup"><span data-stu-id="1092c-127">When a script is saved in a script project, users are able to:</span></span>  
  
-   <span data-ttu-id="1092c-128">Mantener un control de versiones de los scripts.</span><span class="sxs-lookup"><span data-stu-id="1092c-128">Maintain version control on scripts.</span></span>  
  
-   <span data-ttu-id="1092c-129">Almacenar opciones de resultados con un script.</span><span class="sxs-lookup"><span data-stu-id="1092c-129">Store results options with a script.</span></span>  
  
-   <span data-ttu-id="1092c-130">Organizar los scripts relacionados en un solo proyecto de script.</span><span class="sxs-lookup"><span data-stu-id="1092c-130">Organize related scripts in a single script project.</span></span>  
  
-   <span data-ttu-id="1092c-131">Guardar información de conexión con scripts.</span><span class="sxs-lookup"><span data-stu-id="1092c-131">Save connection information with scripts.</span></span>  
  
 <span data-ttu-id="1092c-132">El Explorador de soluciones es una herramienta para los programadores que crean y reutilizan scripts relacionados con el mismo proyecto.</span><span class="sxs-lookup"><span data-stu-id="1092c-132">Solution Explorer is a tool for developers who are creating and reusing scripts that are related to the same project.</span></span> <span data-ttu-id="1092c-133">Si se requiere realizar una tarea similar posteriormente, puede utilizar el grupo de scripts que se almacenó en un proyecto.</span><span class="sxs-lookup"><span data-stu-id="1092c-133">If a similar task is required later, you can use group of scripts that were stored in a project.</span></span> <span data-ttu-id="1092c-134">Si creó aplicaciones mediante [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], el Explorador de soluciones le resultará muy familiar.</span><span class="sxs-lookup"><span data-stu-id="1092c-134">If you have created applications by using [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], you will find Solution Explorer very familiar.</span></span>  
  
 <span data-ttu-id="1092c-135">Una solución consta de uno o más proyectos de script.</span><span class="sxs-lookup"><span data-stu-id="1092c-135">A solution consists of one or more script projects.</span></span> <span data-ttu-id="1092c-136">Un proyecto está formado por uno o más scripts o conexiones.</span><span class="sxs-lookup"><span data-stu-id="1092c-136">A project consists of one or more scripts or connections.</span></span> <span data-ttu-id="1092c-137">Un proyecto también puede incluir archivos que no sean scripts.</span><span class="sxs-lookup"><span data-stu-id="1092c-137">A project may also include nonscript files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1092c-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1092c-138">See Also</span></span>  
 <span data-ttu-id="1092c-139">[Usar SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1092c-139">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="1092c-140">[Editores de consultas y texto &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1092c-140">[Query and Text Editors &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="1092c-141">Soluciones &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1092c-141">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solution/solutions-sql-server-management-studio.md)  
  
  
