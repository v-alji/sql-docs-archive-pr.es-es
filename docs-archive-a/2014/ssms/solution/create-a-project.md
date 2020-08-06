---
title: Crear un proyecto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], creating
ms.assetid: 7897be19-365b-4b06-bcf0-8a669f67a673
author: stevestein
ms.author: sstein
ms.openlocfilehash: 269feee7225ceb09b1c2ed86419b19ec4001c1f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674516"
---
# <a name="create-a-project"></a><span data-ttu-id="1c43a-102">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="1c43a-102">Create a Project</span></span>
  <span data-ttu-id="1c43a-103">Puede crear uno o varios proyectos nuevos en una solución existente.</span><span class="sxs-lookup"><span data-stu-id="1c43a-103">You can create one or more projects within an existing solution.</span></span>  
  
### <a name="to-create-a-new-project-and-add-it-to-a-solution"></a><span data-ttu-id="1c43a-104">Para crear un proyecto nuevo y agregarlo a una solución</span><span class="sxs-lookup"><span data-stu-id="1c43a-104">To create a new project and add it to a solution</span></span>  
  
1.  <span data-ttu-id="1c43a-105">En el Explorador de soluciones, seleccione la solución.</span><span class="sxs-lookup"><span data-stu-id="1c43a-105">In Solution Explorer, select the solution.</span></span>  
  
2.  <span data-ttu-id="1c43a-106">En el menú **Archivo** , seleccione **Agregar**y haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="1c43a-106">On the **File** menu, point to **Add**, and click **New Project**.</span></span>  
  
3.  <span data-ttu-id="1c43a-107">En el cuadro de diálogo  **Nuevo proyecto** , haga clic en un tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c43a-107">In the  **New Project** dialog box, click a type of project.</span></span>  
  
     <span data-ttu-id="1c43a-108">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="1c43a-108">**Templates**</span></span>  
     <span data-ttu-id="1c43a-109">En el cuadro **Plantillas** , seleccione una plantilla.</span><span class="sxs-lookup"><span data-stu-id="1c43a-109">In the **Templates** box, select a template.</span></span> <span data-ttu-id="1c43a-110">Aparecerá una breve descripción de la plantilla del proyecto seleccionado debajo del cuadro **Plantillas** .</span><span class="sxs-lookup"><span data-stu-id="1c43a-110">A brief description of the selected project template appears beneath the **Templates** box.</span></span>  
  
     <span data-ttu-id="1c43a-111">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1c43a-111">**Name**</span></span>  
     <span data-ttu-id="1c43a-112">Escriba el nombre del proyecto de scripts que desea crear.</span><span class="sxs-lookup"><span data-stu-id="1c43a-112">Enter the name of the script project you want to create.</span></span> <span data-ttu-id="1c43a-113">También se creará una carpeta con el mismo nombre que el proyecto en la ubicación que aparece en el campo **Ubicación** .</span><span class="sxs-lookup"><span data-stu-id="1c43a-113">A folder with the same name as the project is also created in the location displayed in the **Location** field.</span></span> <span data-ttu-id="1c43a-114">En algunos proyectos, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] crea archivos de origen y otros archivos de compatibilidad, y los agrega a la nueva carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c43a-114">For some projects, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates source and other supporting files and adds them to the new project folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1c43a-115">En algunos tipos de proyecto, el cuadro de texto **Nombre** no está disponible porque al especificar la ubicación se establece el nombre.</span><span class="sxs-lookup"><span data-stu-id="1c43a-115">For some project types, the **Name** text box is unavailable because specifying the location sets the name.</span></span> <span data-ttu-id="1c43a-116">Por ejemplo, las aplicaciones y los servicios web se ubican en un servidor web y obtienen su nombre del directorio virtual especificado en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="1c43a-116">For example, Web applications and Web services are located on a Web server and derive their name from the virtual directory specified on that server.</span></span>  
  
     <span data-ttu-id="1c43a-117">Los nombres no pueden contener los siguientes caracteres:</span><span class="sxs-lookup"><span data-stu-id="1c43a-117">Names cannot contain the following characters:</span></span>  
  
    -   <span data-ttu-id="1c43a-118">Número (#)</span><span class="sxs-lookup"><span data-stu-id="1c43a-118">Pound (#)</span></span>  
  
    -   <span data-ttu-id="1c43a-119">Porcentaje (%)</span><span class="sxs-lookup"><span data-stu-id="1c43a-119">Percent (%)</span></span>  
  
    -   <span data-ttu-id="1c43a-120">Símbolo de y comercial (&)</span><span class="sxs-lookup"><span data-stu-id="1c43a-120">Ampersand (&)</span></span>  
  
    -   <span data-ttu-id="1c43a-121">Asterisco (\*)</span><span class="sxs-lookup"><span data-stu-id="1c43a-121">Asterisk (\*)</span></span>  
  
    -   <span data-ttu-id="1c43a-122">Barra vertical (|)</span><span class="sxs-lookup"><span data-stu-id="1c43a-122">Vertical bar (|)</span></span>  
  
    -   <span data-ttu-id="1c43a-123">Barra diagonal inversa (\\)</span><span class="sxs-lookup"><span data-stu-id="1c43a-123">Backslash (\\)</span></span>  
  
    -   <span data-ttu-id="1c43a-124">Dos puntos (:)</span><span class="sxs-lookup"><span data-stu-id="1c43a-124">Colon (:)</span></span>  
  
    -   <span data-ttu-id="1c43a-125">Comillas (")</span><span class="sxs-lookup"><span data-stu-id="1c43a-125">Quotation mark (")</span></span>  
  
    -   <span data-ttu-id="1c43a-126">Menor que (\<)</span><span class="sxs-lookup"><span data-stu-id="1c43a-126">Less than (\<)</span></span>  
  
    -   <span data-ttu-id="1c43a-127">Mayor que (>)</span><span class="sxs-lookup"><span data-stu-id="1c43a-127">Greater than (>)</span></span>  
  
    -   <span data-ttu-id="1c43a-128">Signo de interrogación (?)</span><span class="sxs-lookup"><span data-stu-id="1c43a-128">Question mark (?)</span></span>  
  
    -   <span data-ttu-id="1c43a-129">Barra diagonal (/)</span><span class="sxs-lookup"><span data-stu-id="1c43a-129">Forward slash (/)</span></span>  
  
    -   <span data-ttu-id="1c43a-130">Espacios iniciales y finales (' ')</span><span class="sxs-lookup"><span data-stu-id="1c43a-130">Leading or trailing spaces (' ')</span></span>  
  
    -   <span data-ttu-id="1c43a-131">Nombres reservados para Microsoft Windows o MS-DOS, como ("nul", "aux", "con", "com1", "lpt1", etc.)</span><span class="sxs-lookup"><span data-stu-id="1c43a-131">Names reserved for Microsoft Windows or MS-DOS, such as ("nul", "aux", "con", "com1", "lpt1", and so on)</span></span>  
  
     <span data-ttu-id="1c43a-132">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="1c43a-132">**Location**</span></span>  
     <span data-ttu-id="1c43a-133">Escriba la ubicación donde desea crear el proyecto o elija una en la lista.</span><span class="sxs-lookup"><span data-stu-id="1c43a-133">Enter the location where you want to create your project, or choose one from the list.</span></span>  
  
     <span data-ttu-id="1c43a-134">**Browse**</span><span class="sxs-lookup"><span data-stu-id="1c43a-134">**Browse**</span></span>  
     <span data-ttu-id="1c43a-135">Muestra el cuadro de diálogo **Ubicación del proyecto** , que le permite navegar a un nuevo directorio en el que guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c43a-135">Displays the **Project Location** dialog box, allowing you to navigate to a new directory in which to save the project.</span></span>  
  
     <span data-ttu-id="1c43a-136">**Solución**</span><span class="sxs-lookup"><span data-stu-id="1c43a-136">**Solution**</span></span>  
     <span data-ttu-id="1c43a-137">Seleccione **Crear nueva solución** para crear una solución en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="1c43a-137">Select **Create new Solution** to create a solution in Solution Explorer.</span></span> <span data-ttu-id="1c43a-138">Seleccione **Agregar a solución** para agregar el nuevo proyecto a la solución actualmente abierta en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="1c43a-138">Select **Add to Solution** to add the new project to the solution currently open in Solution Explorer.</span></span>  
  
     <span data-ttu-id="1c43a-139">**Crear directorio para la solución**</span><span class="sxs-lookup"><span data-stu-id="1c43a-139">**Create directory for Solution**</span></span>  
     <span data-ttu-id="1c43a-140">Seleccione habilitar el cuadro de texto **Nombre (solución)** .</span><span class="sxs-lookup"><span data-stu-id="1c43a-140">Select to enable the **(Solution) Name** text box.</span></span> <span data-ttu-id="1c43a-141">Esta opción crea un nuevo directorio del nombre elegido para el proyecto y la solución.</span><span class="sxs-lookup"><span data-stu-id="1c43a-141">This option creates a new directory of the name you choose for your project and solution.</span></span>  
  
     <span data-ttu-id="1c43a-142">**Nombre de solución**</span><span class="sxs-lookup"><span data-stu-id="1c43a-142">**Solution Name**</span></span>  
     <span data-ttu-id="1c43a-143">Especifique el nombre de la nueva solución en la que desea crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c43a-143">Enter the name of the new solution in which you want your project to be created.</span></span> <span data-ttu-id="1c43a-144">De manera predeterminada, este campo utiliza el mismo nombre que el especificado en el campo **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="1c43a-144">By default, this field uses the same name as entered in the **Name** field.</span></span>  
  
     <span data-ttu-id="1c43a-145">**Nota** Para tener acceso a esta opción, deberá seleccionar **Crear nueva solución** en las casillas **Solución** y **Crear directorio para la solución** .</span><span class="sxs-lookup"><span data-stu-id="1c43a-145">**Note** To access this option, you must select both the **Create New Solution** in the **Solution** and the **Create directory for Solution** check boxes.</span></span> <span data-ttu-id="1c43a-146">Algunas plantillas de proyecto no admiten esta opción, como las aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="1c43a-146">Some project templates do not support this option, such as Web applications.</span></span>  
  
     <span data-ttu-id="1c43a-147">**Agregar al control de código fuente**</span><span class="sxs-lookup"><span data-stu-id="1c43a-147">**Add to Source Control**</span></span>  
     <span data-ttu-id="1c43a-148">Cuando esta casilla está seleccionada, la aplicación de control de código fuente se abre al hacer clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1c43a-148">When this check box is selected, your source control application opens when you click **OK**.</span></span> <span data-ttu-id="1c43a-149">Complete la información que necesite la aplicación de control de código fuente para continuar.</span><span class="sxs-lookup"><span data-stu-id="1c43a-149">Complete any information required by your source control application to continue.</span></span> <span data-ttu-id="1c43a-150">Para utilizar esta opción, deberá tener una aplicación cliente de control de código fuente instalada.</span><span class="sxs-lookup"><span data-stu-id="1c43a-150">You must have a source control client application installed to use this option.</span></span>  
  
4.  <span data-ttu-id="1c43a-151">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c43a-151">Click **OK**.</span></span>  
  
 <span data-ttu-id="1c43a-152">Puede establecer un nombre para el proyecto de script, aunque [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] establece los nombres de las carpetas y no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="1c43a-152">You can set a name for the script project, but the folder names are established by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and cannot be changed.</span></span> <span data-ttu-id="1c43a-153">Puede configurar la unidad y la especificación de la ruta de acceso de los conjuntos comunes de carpetas mediante el cuadro de diálogo **Agregar nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="1c43a-153">You can configure the drive and path specification for the common set of folders by using the **Add New Project** dialog box.</span></span> <span data-ttu-id="1c43a-154">Haga clic con el botón derecho en el icono de soluciones del **Explorador de soluciones**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1c43a-154">Right-click the solution icon in **Solution Explorer**, and then click **Add**.</span></span> <span data-ttu-id="1c43a-155">La ubicación predeterminada de las carpetas de los proyectos de script es: C:\Documents and Settings\\*NombreDeUsuario*\Mis documentos\SQL Server Management Studio\Projects\\.</span><span class="sxs-lookup"><span data-stu-id="1c43a-155">The default location for script project folders is: C:\Documents and Settings\\*username*\My Documents\SQL Server Management Studio\Projects\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c43a-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c43a-156">See Also</span></span>  
 <span data-ttu-id="1c43a-157">[Explorador de soluciones](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="1c43a-157">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="1c43a-158">[Agregar un proyecto existente a una solución](add-an-existing-project-to-a-solution.md) </span><span class="sxs-lookup"><span data-stu-id="1c43a-158">[Add an Existing Project to a Solution](add-an-existing-project-to-a-solution.md) </span></span>  
 <span data-ttu-id="1c43a-159">[Agregar nuevos elementos a un proyecto](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="1c43a-159">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 <span data-ttu-id="1c43a-160">[Agregar elementos existentes a un proyecto](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="1c43a-160">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 <span data-ttu-id="1c43a-161">[Cambiar la ubicación predeterminada de los proyectos](change-the-default-location-for-projects.md) </span><span class="sxs-lookup"><span data-stu-id="1c43a-161">[Change the Default Location for Projects](change-the-default-location-for-projects.md) </span></span>  
 <span data-ttu-id="1c43a-162">[Quitar o eliminar un elemento o un proyecto](remove-or-delete-an-item-or-project.md) </span><span class="sxs-lookup"><span data-stu-id="1c43a-162">[Remove or Delete an Item or Project](remove-or-delete-an-item-or-project.md) </span></span>  
 [<span data-ttu-id="1c43a-163">Eliminar una solución</span><span class="sxs-lookup"><span data-stu-id="1c43a-163">Delete a Solution</span></span>](delete-a-solution.md)  
  
  
