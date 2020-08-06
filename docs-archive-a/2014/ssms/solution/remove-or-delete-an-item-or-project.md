---
title: Quitar o eliminar un elemento o un proyecto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting project items
- projects [SQL Server Management Studio], item removal
- removing project items
ms.assetid: 3fd92434-70f5-466e-bef0-7e0fd73ddb1c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 679911f15d6c47f4274180602a5376c4ec03c77b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671308"
---
# <a name="remove-or-delete-an-item-or-project"></a><span data-ttu-id="f31a1-102">Quitar o eliminar un elemento o un proyecto</span><span class="sxs-lookup"><span data-stu-id="f31a1-102">Remove or Delete an Item or Project</span></span>
  <span data-ttu-id="f31a1-103">Los elementos de proyecto en los proyectos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] son las consultas, las conexiones y los archivos varios.</span><span class="sxs-lookup"><span data-stu-id="f31a1-103">Project items in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] projects are Queries, Connections, and Miscellaneous files.</span></span> <span data-ttu-id="f31a1-104">Se pueden quitar consultas y archivos varios del proyecto de una solución sin borrar los archivos almacenados.</span><span class="sxs-lookup"><span data-stu-id="f31a1-104">You can remove project queries and miscellaneous files from your solution without erasing the files from storage.</span></span> <span data-ttu-id="f31a1-105">Quite un proyecto o un elemento que no sea útil para la solución actual, pero que desee incluir en otra solución.</span><span class="sxs-lookup"><span data-stu-id="f31a1-105">Remove a project or item when it is not useful in the current solution but you want to include it in another solution.</span></span>  
  
### <a name="to-remove-a-project-item"></a><span data-ttu-id="f31a1-106">Para quitar un elemento de un proyecto</span><span class="sxs-lookup"><span data-stu-id="f31a1-106">To remove a project item</span></span>  
  
1.  <span data-ttu-id="f31a1-107">En el Explorador de soluciones, seleccione el elemento del proyecto que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="f31a1-107">In Solution Explorer, select the project item you want to remove.</span></span>  
  
2.  <span data-ttu-id="f31a1-108">En el menú **Editar** , haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="f31a1-108">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="f31a1-109">En el cuadro de diálogo de confirmación, haga clic en **Quitar** para quitar el elemento del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f31a1-109">On the confirmation dialog, click **Remove** to remove the item from the project.</span></span>  
  
 <span data-ttu-id="f31a1-110">Un elemento quitado aún se encuentra en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="f31a1-110">A removed item still exists on the file system.</span></span> <span data-ttu-id="f31a1-111">Por lo tanto, puede agregar ese elemento quitado a la solución original o a otra solución.</span><span class="sxs-lookup"><span data-stu-id="f31a1-111">Therefore, you can add a removed item to its original solution or to another solution.</span></span>  
  
#### <a name="to-remove-a-project"></a><span data-ttu-id="f31a1-112">Para quitar un proyecto</span><span class="sxs-lookup"><span data-stu-id="f31a1-112">To remove a project</span></span>  
  
1.  <span data-ttu-id="f31a1-113">En el Explorador de soluciones, seleccione el proyecto que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="f31a1-113">In Solution Explorer, select the project you want to remove.</span></span>  
  
2.  <span data-ttu-id="f31a1-114">En el menú **Editar** , haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="f31a1-114">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="f31a1-115">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**para quitar el proyecto de la solución.</span><span class="sxs-lookup"><span data-stu-id="f31a1-115">On the confirmation dialog, click **OK**, to remove the project from the solution.</span></span>  
  
 <span data-ttu-id="f31a1-116">Un proyecto se puede eliminar de forma permanente, pero primero es necesario quitar todas las referencias al mismo de las soluciones de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y, a continuación, utilizar el Explorador de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows para eliminar de forma permanente los archivos asociados almacenados.</span><span class="sxs-lookup"><span data-stu-id="f31a1-116">You can delete a project permanently, but you first need to remove any references to the project from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solutions, and then use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Explorer to permanently delete the associated files from storage.</span></span>  
  
#### <a name="to-delete-a-project"></a><span data-ttu-id="f31a1-117">Para eliminar un proyecto</span><span class="sxs-lookup"><span data-stu-id="f31a1-117">To delete a project</span></span>  
  
1.  <span data-ttu-id="f31a1-118">En el Explorador de soluciones, quite el proyecto que desea eliminar de la solución.</span><span class="sxs-lookup"><span data-stu-id="f31a1-118">In Solution Explorer, remove the project you want to delete from the solution.</span></span>  
  
2.  <span data-ttu-id="f31a1-119">En el Explorador de Windows, busque y seleccione los archivos asociados al proyecto o elemento que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="f31a1-119">In Windows Explorer, locate and select the files associated with the project or item you want to delete.</span></span>  
  
3.  <span data-ttu-id="f31a1-120">En el menú **Archivo** , haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f31a1-120">On the **File** menu, click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f31a1-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f31a1-121">See Also</span></span>  
 <span data-ttu-id="f31a1-122">[Explorador de soluciones](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="f31a1-122">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="f31a1-123">[Agregar nuevos elementos a un proyecto](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="f31a1-123">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="f31a1-124">Agregar elementos existentes a un proyecto</span><span class="sxs-lookup"><span data-stu-id="f31a1-124">Add Existing Items to a Project</span></span>](add-existing-items-to-a-project.md)  
  
  
