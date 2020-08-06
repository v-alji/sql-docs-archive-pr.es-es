---
title: Agregar elementos existentes a un proyecto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 084b3879-e96b-45a7-b421-6a4b0db2b92b
author: stevestein
ms.author: sstein
ms.openlocfilehash: cffa683bfa2a2c81c059d887231531f03d5c892b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677324"
---
# <a name="add-existing-items-to-a-project"></a><span data-ttu-id="1f34b-102">Agregar elementos existentes a un proyecto</span><span class="sxs-lookup"><span data-stu-id="1f34b-102">Add Existing Items to a Project</span></span>
  <span data-ttu-id="1f34b-103">Agregue elementos nuevos a un proyecto para ampliar la funcionalidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f34b-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="1f34b-104">Un elemento existente puede ser una consulta o un archivo del tipo varios.</span><span class="sxs-lookup"><span data-stu-id="1f34b-104">An existing item can be a query or a miscellaneous file.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1f34b-105">tiene dos tipos de proyectos: proyecto de script de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y proyecto de script de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1f34b-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="1f34b-106">El tipo de proyecto determina los archivos de consulta que se pueden agregar al proyecto.</span><span class="sxs-lookup"><span data-stu-id="1f34b-106">The project type determines the query files that you can add to the project.</span></span> <span data-ttu-id="1f34b-107">Por ejemplo, se puede agregar una consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] (un archivo con una extensión .sql) a un proyecto de script de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , pero no a un proyecto de script de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1f34b-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span> <span data-ttu-id="1f34b-108">Para asociar extensiones de archivo adicionales a un tipo de proyecto, vea [asociar extensiones de archivo a un editor de código](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span><span class="sxs-lookup"><span data-stu-id="1f34b-108">To associate additional file extensions to a project type, see [Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span></span>  
  
### <a name="to-add-an-existing-query-or-a-miscellaneous-file-to-a-project"></a><span data-ttu-id="1f34b-109">Para agregar una consulta existente o un archivo del tipo archivos varios a un proyecto</span><span class="sxs-lookup"><span data-stu-id="1f34b-109">To add an existing query or a miscellaneous file to a project</span></span>  
  
1.  <span data-ttu-id="1f34b-110">En el Explorador de soluciones, seleccione el proyecto de destino.</span><span class="sxs-lookup"><span data-stu-id="1f34b-110">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="1f34b-111">En el menú **Proyecto** , haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="1f34b-111">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
     <span data-ttu-id="1f34b-112">**Look in**</span><span class="sxs-lookup"><span data-stu-id="1f34b-112">**Look in**</span></span>  
     <span data-ttu-id="1f34b-113">Busque en esta lista los archivos o las carpetas que se agregarán al proyecto.</span><span class="sxs-lookup"><span data-stu-id="1f34b-113">Locate the files or folders to add to your project from this list.</span></span> <span data-ttu-id="1f34b-114">En el caso de servicios web XML y aplicaciones Web ASP.NET, los archivos se encuentran en el servidor web.</span><span class="sxs-lookup"><span data-stu-id="1f34b-114">For XML Web services and ASP.NET Web applications, the files are located on the Web server.</span></span>  
  
     <span data-ttu-id="1f34b-115">**Escritorio**</span><span class="sxs-lookup"><span data-stu-id="1f34b-115">**Desktop**</span></span>  
     <span data-ttu-id="1f34b-116">Muestra los archivos y las carpetas del escritorio.</span><span class="sxs-lookup"><span data-stu-id="1f34b-116">Displays the files and folders located on the desktop.</span></span>  
  
     <span data-ttu-id="1f34b-117">**Mis proyectos**</span><span class="sxs-lookup"><span data-stu-id="1f34b-117">**My Projects**</span></span>  
     <span data-ttu-id="1f34b-118">Muestra los archivos y las carpetas de la ubicación predeterminada **Mis proyectos** .</span><span class="sxs-lookup"><span data-stu-id="1f34b-118">Displays the files and folders at the default **My Projects** location.</span></span>  
  
     <span data-ttu-id="1f34b-119">**Mi PC**</span><span class="sxs-lookup"><span data-stu-id="1f34b-119">**My Computer**</span></span>  
     <span data-ttu-id="1f34b-120">Muestra el contenido de la carpeta **Mi PC** .</span><span class="sxs-lookup"><span data-stu-id="1f34b-120">Displays the contents of your **My Computer** folder.</span></span>  
  
     <span data-ttu-id="1f34b-121">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="1f34b-121">**File name**</span></span>  
     <span data-ttu-id="1f34b-122">Utilice esta opción para filtrar los archivos y las carpetas mostrados.</span><span class="sxs-lookup"><span data-stu-id="1f34b-122">Use this option to filter the files and folders that are displayed.</span></span> <span data-ttu-id="1f34b-123">Especifique el nombre de archivo completo o parcial que se filtrará, utilice un asterisco (`*`) como comodín.</span><span class="sxs-lookup"><span data-stu-id="1f34b-123">Enter the full or partial file name on which to filter; use an asterisk (`*`) as a wildcard.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1f34b-124">Navegue a las ubicaciones web o de red especificando la dirección URL o la ruta de red en el cuadro **Nombre de archivo** .</span><span class="sxs-lookup"><span data-stu-id="1f34b-124">Navigate to Web and network locations by entering the URL or network path in the **File name** box.</span></span> <span data-ttu-id="1f34b-125">Por ejemplo, **http://mywebsite** muestra los archivos disponibles en la ubicación web miSitioWeb y **\\\miServidor\miRecursoCompartido** muestra los archivos disponibles en la ubicación miRecursoCompartido en miServidor.</span><span class="sxs-lookup"><span data-stu-id="1f34b-125">For example, **http://mywebsite** displays the files available at the mywebsite Web location, and **\\\myserver\myshare** displays the files available at the myshare location on myserver.</span></span>  
  
     <span data-ttu-id="1f34b-126">**Archivos de tipo**</span><span class="sxs-lookup"><span data-stu-id="1f34b-126">**Files of type**</span></span>  
     <span data-ttu-id="1f34b-127">Utilice esta opción para filtrar archivos según la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="1f34b-127">Use this option to filter files based on file extension.</span></span> <span data-ttu-id="1f34b-128">Cada producto muestra los filtros predeterminados de los tipos de archivo más comunes.</span><span class="sxs-lookup"><span data-stu-id="1f34b-128">Each product lists default filters of the most common file types.</span></span>  
  
     <span data-ttu-id="1f34b-129">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="1f34b-129">**Add**</span></span>  
     <span data-ttu-id="1f34b-130">Utilice este botón desplegable para agregar el elemento al proyecto y abrirlo en el editor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1f34b-130">Use this drop-down button to add the item to the project and open the item in its default editor.</span></span>  
  
    -   <span data-ttu-id="1f34b-131">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="1f34b-131">**Add**</span></span>  
  
         <span data-ttu-id="1f34b-132">Copia el elemento existente en la carpeta de proyecto del disco y agrega el elemento del proyecto seleccionado en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="1f34b-132">Copies the existing item to your project folder on disk and adds the item under the selected project in Solution Explorer.</span></span> <span data-ttu-id="1f34b-133">Los cambios realizados en el elemento no se reflejarán en el elemento de la ubicación original.</span><span class="sxs-lookup"><span data-stu-id="1f34b-133">Any changes made to the item are not reflected in the item at the original location.</span></span> <span data-ttu-id="1f34b-134">Es el editor predeterminado para el tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="1f34b-134">This is the default editor for the file type.</span></span>  
  
    -   <span data-ttu-id="1f34b-135">**Agregar como vínculo**</span><span class="sxs-lookup"><span data-stu-id="1f34b-135">**Add As Link**</span></span>  
  
         <span data-ttu-id="1f34b-136">Agrega el archivo seleccionado al proyecto y lo abre con el editor predeterminado para el tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="1f34b-136">Adds the selected file to the project and opens it with the default editor for the file type.</span></span> <span data-ttu-id="1f34b-137">Con esta opción se abre el archivo seleccionado inicialmente y no se copia en la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1f34b-137">This option opens the originally selected file and does not copy the file to the project folder.</span></span>  
  
3.  <span data-ttu-id="1f34b-138">Si va a agregar archivos de consulta, el cuadro de diálogo de conexión le pedirá que especifique una conexión para la consulta.</span><span class="sxs-lookup"><span data-stu-id="1f34b-138">If you are adding query files, the connection dialog will prompt you to specify a connection for the query.</span></span> <span data-ttu-id="1f34b-139">Si no desea asociar una conexión a la consulta, puede hacer clic en **Cancelar** en el cuadro de diálogo de conexión.</span><span class="sxs-lookup"><span data-stu-id="1f34b-139">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the query.</span></span>  
  
4.  <span data-ttu-id="1f34b-140">El archivo se agregará a la carpeta **Consultas** o **Archivos varios** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1f34b-140">The file will be added to the **Queries** or **Miscellaneous Files** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f34b-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f34b-141">See Also</span></span>  
 <span data-ttu-id="1f34b-142">[Explorador de soluciones](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="1f34b-142">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="1f34b-143">[Agregar nuevos elementos a un proyecto](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="1f34b-143">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="1f34b-144">Quitar o eliminar un elemento o un proyecto</span><span class="sxs-lookup"><span data-stu-id="1f34b-144">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
