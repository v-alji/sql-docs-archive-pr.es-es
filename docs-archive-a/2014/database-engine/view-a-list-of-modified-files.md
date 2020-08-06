---
title: Ver una lista de archivos modificados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckinWindow
helpviewer_keywords:
- listing modified files
- modified files list [SQL Server]
- checking in files
ms.assetid: 1b053719-8500-4300-a169-fffca5801dd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a2899ab9889908089d17b3c929e7bf4b2dfe2185
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675499"
---
# <a name="view-a-list-of-modified-files"></a><span data-ttu-id="0c474-102">Ver una lista de archivos modificados</span><span class="sxs-lookup"><span data-stu-id="0c474-102">View a List of Modified Files</span></span>
  <span data-ttu-id="0c474-103">Puede usar la ventana **protecciones pendientes** para mostrar en todo momento una lista de los archivos desprotegidos de la solución actual y para proteger estos archivos con un solo clic de botón.</span><span class="sxs-lookup"><span data-stu-id="0c474-103">You can use the **Pending Checkins** window to display at all times a list of the checked-out files in the current solution, and to check in these files with a single button click.</span></span>  
  
### <a name="to-view-a-list-of-modified-files"></a><span data-ttu-id="0c474-104">Para ver una lista de los archivos modificados</span><span class="sxs-lookup"><span data-stu-id="0c474-104">To view a list of modified files</span></span>  
  
1.  <span data-ttu-id="0c474-105">En el menú **Ver** , haga clic en **protecciones pendientes**.</span><span class="sxs-lookup"><span data-stu-id="0c474-105">On the **View** menu, click **Pending Checkins**.</span></span>  
  
2.  <span data-ttu-id="0c474-106">Para proteger los archivos seleccionados, haga clic en **proteger**.</span><span class="sxs-lookup"><span data-stu-id="0c474-106">To check in the selected files, click **Check In**.</span></span> <span data-ttu-id="0c474-107">También puede acoplar la ventana **protecciones pendientes** en el lado derecho del [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] entorno para que pueda proteger los archivos cuando termine de trabajar.</span><span class="sxs-lookup"><span data-stu-id="0c474-107">Alternatively, you can dock the **Pending Checkins** window on the right side of the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment so that you can check in the files when you are finished working.</span></span>  
  
     <span data-ttu-id="0c474-108">**Check-in**</span><span class="sxs-lookup"><span data-stu-id="0c474-108">**Check In**</span></span>  
     <span data-ttu-id="0c474-109">Protege la solución.</span><span class="sxs-lookup"><span data-stu-id="0c474-109">Checks in the solution.</span></span>  
  
     <span data-ttu-id="0c474-110">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="0c474-110">**Comments**</span></span>  
     <span data-ttu-id="0c474-111">Asocia un comentario de texto simple a la protección pendiente.</span><span class="sxs-lookup"><span data-stu-id="0c474-111">Associates a plain text comment with the pending check in.</span></span> <span data-ttu-id="0c474-112">Con cada versión del proyecto se crea un comentario, que se almacena en la base de datos de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="0c474-112">A comment is created and associated with each version of a project, and stored in the source control database.</span></span>  
  
     <span data-ttu-id="0c474-113">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="0c474-113">**Options**</span></span>  
     <span data-ttu-id="0c474-114">Especifica las acciones que debe realizar el control de código fuente al hacer clic en el botón **proteger** .</span><span class="sxs-lookup"><span data-stu-id="0c474-114">Specifies the actions that source control should take when you click the **Check In** button.</span></span>  
  
    -   <span data-ttu-id="0c474-115">**Mantener todo desprotegido**</span><span class="sxs-lookup"><span data-stu-id="0c474-115">**Keep All Checked Out**</span></span>  
  
         <span data-ttu-id="0c474-116">Especifica que los cambios deben escribirse en el proveedor de control de código fuente, pero los archivos deben permanecer desprotegidos.</span><span class="sxs-lookup"><span data-stu-id="0c474-116">Specifies that your changes should be written to the source control provider but that the files should remain checked out.</span></span>  
  
     <span data-ttu-id="0c474-117">**Sort**</span><span class="sxs-lookup"><span data-stu-id="0c474-117">**Sort**</span></span>  
     <span data-ttu-id="0c474-118">Especifica el orden de las columnas que aparecen en la lista Elementos.</span><span class="sxs-lookup"><span data-stu-id="0c474-118">Specifies the sort order for the columns displayed in the Items list.</span></span>  
  
     <span data-ttu-id="0c474-119">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="0c474-119">**Columns**</span></span>  
     <span data-ttu-id="0c474-120">Muestra una lista de las columnas que puede agregar a la lista Elementos de la ventana.</span><span class="sxs-lookup"><span data-stu-id="0c474-120">Displays a list of the columns you can add to the window's Items list.</span></span>  
  
     <span data-ttu-id="0c474-121">**Vista de árbol**</span><span class="sxs-lookup"><span data-stu-id="0c474-121">**Tree View**</span></span>  
     <span data-ttu-id="0c474-122">Muestra la carpeta y la jerarquía de archivos de la solución o del proyecto que se protege.</span><span class="sxs-lookup"><span data-stu-id="0c474-122">Displays the folder and file hierarchy for the solution or project you are checking in.</span></span>  
  
     <span data-ttu-id="0c474-123">**Vista plana**</span><span class="sxs-lookup"><span data-stu-id="0c474-123">**Flat View**</span></span>  
     <span data-ttu-id="0c474-124">Muestra los archivos que se protegen como listas planas, bajo su conexión de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="0c474-124">Displays the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="0c474-125">**Comparar versiones**</span><span class="sxs-lookup"><span data-stu-id="0c474-125">**Compare Versions**</span></span>  
     <span data-ttu-id="0c474-126">Abre el cuadro de diálogo **Opciones de diferencia** de Visual SourceSafe, que compara un archivo seleccionado en el proyecto del entorno de desarrollo con cualquier otro archivo seleccionado y muestra las diferencias, si existen.</span><span class="sxs-lookup"><span data-stu-id="0c474-126">Opens the Visual SourceSafe **Difference Options** dialog box, which compares a selected file in your development environment project to any other selected file and shows you the differences, if any.</span></span>  
  
     <span data-ttu-id="0c474-127">**Deshacer desprotección**</span><span class="sxs-lookup"><span data-stu-id="0c474-127">**Undo checkout**</span></span>  
     <span data-ttu-id="0c474-128">Invierte la desprotección de todos los elementos seleccionados en la ventana **protecciones pendientes** .</span><span class="sxs-lookup"><span data-stu-id="0c474-128">Reverses the checkout of all items selected in the **Pending Checkins** window.</span></span>  
  
     <span data-ttu-id="0c474-129">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="0c474-129">**Name**</span></span>  
     <span data-ttu-id="0c474-130">Muestra una lista de elementos disponibles para la protección.</span><span class="sxs-lookup"><span data-stu-id="0c474-130">Displays a list of the items available for check in.</span></span> <span data-ttu-id="0c474-131">Los elementos aparecen con la casilla que se encuentra junto a ellos activada.</span><span class="sxs-lookup"><span data-stu-id="0c474-131">Items appear with the check box next to them selected.</span></span> <span data-ttu-id="0c474-132">Si no desea proteger un elemento determinado, desactive la casilla adyacente.</span><span class="sxs-lookup"><span data-stu-id="0c474-132">If you do not want to check in a particular item, clear the check box next to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c474-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c474-133">See Also</span></span>  
 <span data-ttu-id="0c474-134">[Administrar protecciones](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="0c474-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="0c474-135">Administrar desprotecciones</span><span class="sxs-lookup"><span data-stu-id="0c474-135">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
