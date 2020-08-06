---
title: Desproteger archivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- Visual Studio.SourceControl.CheckOutDialog
helpviewer_keywords:
- checking out files
ms.assetid: cc033727-51bb-4b58-a12b-8977ce61ff56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 151f554742bd6c381b27b58155d3f0e40e9eeb0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674359"
---
# <a name="check-out-files"></a><span data-ttu-id="63ae1-102">Desproteger archivos</span><span class="sxs-lookup"><span data-stu-id="63ae1-102">Check Out Files</span></span>
  <span data-ttu-id="63ae1-103">A menos que se haya configurado el entorno de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para que se permita modificar los archivos protegidos, es necesario desproteger un archivo antes de poder modificarlo.</span><span class="sxs-lookup"><span data-stu-id="63ae1-103">Unless you have configured the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment to permit checked-in files to be edited, you must check out a file before you can modify it.</span></span> <span data-ttu-id="63ae1-104">Al desproteger un archivo, una copia de la versión de ese archivo se copia en el disco local y se quita el atributo de solo lectura del mismo.</span><span class="sxs-lookup"><span data-stu-id="63ae1-104">When you check out a file, a copy of the file version is copied to your local disk, and the read-only attribute of the file is removed.</span></span>  
  
 <span data-ttu-id="63ae1-105">Es posible desproteger archivos en modo exclusivo o compartido.</span><span class="sxs-lookup"><span data-stu-id="63ae1-105">You can check files out either exclusively or in shared mode.</span></span> <span data-ttu-id="63ae1-106">Si desprotege un archivo en modo exclusivo, ningún otro usuario podrá desprotegerlo hasta que usted lo vuelva a proteger.</span><span class="sxs-lookup"><span data-stu-id="63ae1-106">When you check out a file exclusively, no other user can check out the file until you check it in.</span></span> <span data-ttu-id="63ae1-107">Si desprotege un archivo en modo compartido, otros usuarios pueden desprotegerlo y modificarlo, así que cuando vaya a protegerlo, puede que tenga que combinar la versión que ha desprotegido con las versiones creadas por los otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="63ae1-107">When you check out a file in shared mode, other users can check out and modify the file, and when you check it in, you may need to merge the version you have checked out with the versions created by other users.</span></span>  
  
 <span data-ttu-id="63ae1-108">Utilice el comando **Desproteger** para desproteger proyectos y archivos controlados por código fuente.</span><span class="sxs-lookup"><span data-stu-id="63ae1-108">Use the **Check Out** command to check out source-controlled projects and files.</span></span> <span data-ttu-id="63ae1-109">Si usa este comando para desproteger una solución o un proyecto, todos los archivos de la solución o el proyecto también se desprotegen. Sin embargo, la desprotección de un archivo de código fuente individual no da lugar a la desprotección del proyecto o la solución a la que pertenece.</span><span class="sxs-lookup"><span data-stu-id="63ae1-109">If you use this command to check out a solution or project, all the files in the solution or project are also checked out. However, checking out an individual source code file does not result in the check out of the project or solution to which it belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63ae1-110">Si la base de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe del proyecto está configurada para permitir varias desprotecciones y desea desproteger un archivo en modo exclusivo, debe desactivar la opción **Permitir varias desprotecciones** del cuadro de diálogo **Opciones avanzadas de desprotección** antes de desproteger el archivo.</span><span class="sxs-lookup"><span data-stu-id="63ae1-110">If the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database for your project is configured to allow multiple checkouts, and you want to check out a file exclusively, you must clear the **Allow multiple checkouts** option in the **Advanced Check Out Options** dialog box before checking out the file.</span></span> <span data-ttu-id="63ae1-111">Para que se aplique esta configuración, debe reiniciar [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63ae1-111">You must restart the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for this setting to take effect.</span></span>  
  
### <a name="to-check-out-a-file"></a><span data-ttu-id="63ae1-112">Para desproteger un archivo</span><span class="sxs-lookup"><span data-stu-id="63ae1-112">To check out a file</span></span>  
  
1.  <span data-ttu-id="63ae1-113">En el Explorador de soluciones, seleccione el proyecto o el archivo.</span><span class="sxs-lookup"><span data-stu-id="63ae1-113">In Solution Explorer, select the project or file.</span></span>  
  
2.  <span data-ttu-id="63ae1-114">En el menú **Archivo** , seleccione **Control de código fuente**y haga clic en **Desproteger para editar**.</span><span class="sxs-lookup"><span data-stu-id="63ae1-114">On the **File** menu, point to **Source Control**, and then click **Check Out for Edit**.</span></span>  
  
3.  <span data-ttu-id="63ae1-115">Si aparece el cuadro **de diálogo desproteger para editar** , seleccione los elementos que desee y haga clic en **Desproteger**. Si ha configurado el [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] entorno para que no muestre el cuadro de diálogo **Desproteger** , los elementos seleccionados en explorador de soluciones y los elementos secundarios que puedan tener se desprotegen inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="63ae1-115">If the **Check Out for Edit** dialog box is displayed, select the items you want, and click **Check Out**. If you have configured the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment not to display the **Check Out** dialog box, the items selected in Solution Explorer and any children they might have are checked out immediately.</span></span>  
  
     <span data-ttu-id="63ae1-116">**Check-out**</span><span class="sxs-lookup"><span data-stu-id="63ae1-116">**Check Out**</span></span>  
     <span data-ttu-id="63ae1-117">Desprotege todos los elementos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="63ae1-117">Check out all the selected items.</span></span>  
  
     <span data-ttu-id="63ae1-118">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="63ae1-118">**Columns**</span></span>  
     <span data-ttu-id="63ae1-119">Identifique las columnas que se van a mostrar y el orden en que lo hacen.</span><span class="sxs-lookup"><span data-stu-id="63ae1-119">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="63ae1-120">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="63ae1-120">**Comments**</span></span>  
     <span data-ttu-id="63ae1-121">Especifique un comentario que se asociará a la operación de desprotección.</span><span class="sxs-lookup"><span data-stu-id="63ae1-121">Specify a comment to associate with the checkout operation.</span></span>  
  
     <span data-ttu-id="63ae1-122">**No mostrar el cuadro de diálogo Desproteger al desproteger elementos**</span><span class="sxs-lookup"><span data-stu-id="63ae1-122">**Don't Show Check Out dialog box when checking out items**</span></span>  
     <span data-ttu-id="63ae1-123">Suprime el cuadro de diálogo durante las operaciones de desprotección.</span><span class="sxs-lookup"><span data-stu-id="63ae1-123">Suppress the dialog box during checkout operations.</span></span>  
  
     <span data-ttu-id="63ae1-124">**Vista plana**</span><span class="sxs-lookup"><span data-stu-id="63ae1-124">**Flat View**</span></span>  
     <span data-ttu-id="63ae1-125">Muestra los elementos que va a desproteger como listas planas en su conexión de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="63ae1-125">Display the items you are checking out as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="63ae1-126">**Edición**</span><span class="sxs-lookup"><span data-stu-id="63ae1-126">**Edit**</span></span>  
     <span data-ttu-id="63ae1-127">Modifique un elemento sin desprotegerlo. El botón **Editar** solo aparece si ha [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configurado para admitir la edición de archivos protegidos.</span><span class="sxs-lookup"><span data-stu-id="63ae1-127">Modify an item without checking it out. The **Edit** button appears only if you have [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configured to support the editing of checked-in files.</span></span>  
  
     <span data-ttu-id="63ae1-128">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="63ae1-128">**Name**</span></span>  
     <span data-ttu-id="63ae1-129">Muestra los nombres de los elementos disponibles para su desprotección.</span><span class="sxs-lookup"><span data-stu-id="63ae1-129">Displays the names of the items available for checkout.</span></span> <span data-ttu-id="63ae1-130">Los elementos seleccionados aparecen con casillas junto a ellos.</span><span class="sxs-lookup"><span data-stu-id="63ae1-130">Items that are selected appear with check boxes next to them.</span></span> <span data-ttu-id="63ae1-131">Si no desea desproteger un elemento determinado, desactive su casilla.</span><span class="sxs-lookup"><span data-stu-id="63ae1-131">If you do not want to check out a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="63ae1-132">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="63ae1-132">**Options**</span></span>  
     <span data-ttu-id="63ae1-133">Si hace clic en la flecha situada a la derecha del botón, se mostrarán opciones de desprotección específicas del complemento de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="63ae1-133">Displays source control plug-in-specific checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="63ae1-134">**Sort**</span><span class="sxs-lookup"><span data-stu-id="63ae1-134">**Sort**</span></span>  
     <span data-ttu-id="63ae1-135">Ordena las columnas mostradas.</span><span class="sxs-lookup"><span data-stu-id="63ae1-135">Sort the order of the displayed columns.</span></span>  
  
     <span data-ttu-id="63ae1-136">**Vista de árbol**</span><span class="sxs-lookup"><span data-stu-id="63ae1-136">**Tree View**</span></span>  
     <span data-ttu-id="63ae1-137">Muestra la jerarquía de carpetas y archivos del elemento que va a desproteger.</span><span class="sxs-lookup"><span data-stu-id="63ae1-137">Display the folder and file hierarchy for the item you are checking out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ae1-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63ae1-138">See Also</span></span>  
 <span data-ttu-id="63ae1-139">[Editar archivos protegidos](../../2014/database-engine/edit-checked-in-files.md) </span><span class="sxs-lookup"><span data-stu-id="63ae1-139">[Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md) </span></span>  
 <span data-ttu-id="63ae1-140">[Desproteger archivos automáticamente al editarlos](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span><span class="sxs-lookup"><span data-stu-id="63ae1-140">[Automatically Check Out Files Upon Edit](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span></span>  
 <span data-ttu-id="63ae1-141">[Deshacer desprotecciones](../../2014/database-engine/undo-checkouts.md) </span><span class="sxs-lookup"><span data-stu-id="63ae1-141">[Undo Checkouts](../../2014/database-engine/undo-checkouts.md) </span></span>  
 [<span data-ttu-id="63ae1-142">Administrar desprotecciones</span><span class="sxs-lookup"><span data-stu-id="63ae1-142">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
