---
title: Crear, eliminar o modificar una carpeta (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing folders
- modifying folders
- deleting folders
- folders [Reporting Services], creating
- folders [Reporting Services], deleting
- folders [Reporting Services], modifying
ms.assetid: d62159a8-ec67-4e28-a9f1-05a9250065bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bd7d5ceebdb7b3a48ded66ed108bddda25d8a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674580"
---
# <a name="create-delete-or-modify-a-folder-report-manager"></a><span data-ttu-id="c524c-102">Crear, eliminar o modificar una carpeta (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="c524c-102">Create, Delete, or Modify a Folder (Report Manager)</span></span>
  <span data-ttu-id="c524c-103">Puede crear carpetas para organizar y administrar los elementos que publica en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c524c-103">You can create folders to organize and manage the items you publish to a report server.</span></span> <span data-ttu-id="c524c-104">La creación de carpetas puede ayudar a los usuarios a buscar informes de su interés.</span><span class="sxs-lookup"><span data-stu-id="c524c-104">Creating folders can help users find reports of interest to them.</span></span> <span data-ttu-id="c524c-105">Para administradores de contenido, las carpetas proporcionan un marco para aplicar permisos.</span><span class="sxs-lookup"><span data-stu-id="c524c-105">For content managers, folders provide a framework for applying permissions.</span></span> <span data-ttu-id="c524c-106">Puede crear asignaciones de roles en carpetas concretas para restringir el acceso a los informes que se están desarrollando o que no se deberían distribuir de manera amplia.</span><span class="sxs-lookup"><span data-stu-id="c524c-106">You can create role assignments on specific folders to restrict access to reports that are in development or that should not be widely distributed.</span></span>  
  
### <a name="to-create-a-folder"></a><span data-ttu-id="c524c-107">Para crear una carpeta</span><span class="sxs-lookup"><span data-stu-id="c524c-107">To create a folder</span></span>  
  
1.  <span data-ttu-id="c524c-108">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c524c-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="c524c-109">En el Administrador de informes, seleccione la carpeta Inicio y haga clic en **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="c524c-109">In Report Manager, select the Home folder and click **New Folder**.</span></span> <span data-ttu-id="c524c-110">O bien, para crear una carpeta en una carpeta existente, navegue hasta dicha carpeta en la página **Contenido** y haga clic en ella para abrirla.</span><span class="sxs-lookup"><span data-stu-id="c524c-110">Or, to create a folder under an existing folder, navigate to that folder in the **Contents** page and click the folder to open it.</span></span> <span data-ttu-id="c524c-111">A continuación, haga clic en **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="c524c-111">Then click **New Folder**.</span></span>  
  
     <span data-ttu-id="c524c-112">Se abre la página **Nueva carpeta** .</span><span class="sxs-lookup"><span data-stu-id="c524c-112">The **New Folder** page opens.</span></span>  
  
3.  <span data-ttu-id="c524c-113">Escriba el nombre de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="c524c-113">Type a folder name.</span></span> <span data-ttu-id="c524c-114">Puede incluir espacios, pero no caracteres reservados que se utilicen para la codificación de direcciones URL: ; ?</span><span class="sxs-lookup"><span data-stu-id="c524c-114">A folder name can include spaces, but cannot include reserved characters that are used for URL encoding: ; ?</span></span> <span data-ttu-id="c524c-115">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="c524c-115">: \@ & = + , $ / \* \< > |.</span></span> <span data-ttu-id="c524c-116">No se puede escribir una serie de nombres de carpetas para crear varias carpetas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c524c-116">You cannot type a series of folder names to create several folders at once.</span></span>  
  
4.  <span data-ttu-id="c524c-117">Si lo desea, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="c524c-117">Optionally type a description.</span></span>  
  
5.  <span data-ttu-id="c524c-118">Seleccione **Ocultar en la vista de lista** si no desea mostrar la carpeta en la vista predeterminada de la página **Contenido** .</span><span class="sxs-lookup"><span data-stu-id="c524c-118">Select **Hide in list view** if you do not want to display the folder in the default view of the **Contents** page.</span></span> <span data-ttu-id="c524c-119">La carpeta estará visible para los usuarios solo cuando hagan clic en **Mostrar detalles** en la página **Contenido** .</span><span class="sxs-lookup"><span data-stu-id="c524c-119">The folder will be visible to users only when they click **Show Details** on the **Contents** page.</span></span>  
  
6.  <span data-ttu-id="c524c-120">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="c524c-120">Click **OK**.</span></span>  
  
### <a name="to-delete-a-folder"></a><span data-ttu-id="c524c-121">Para eliminar una carpeta</span><span class="sxs-lookup"><span data-stu-id="c524c-121">To delete a folder</span></span>  
  
1.  <span data-ttu-id="c524c-122">En el Administrador de informes, navegue a la página **Contenido** y localice el elemento que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="c524c-122">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="c524c-123">Mantenga el mouse sobre el elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c524c-123">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c524c-124">En el menú desplegable, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c524c-124">In the drop-down menu, click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-modify-or-delete-a-folder"></a><span data-ttu-id="c524c-125">Para modificar o eliminar una carpeta</span><span class="sxs-lookup"><span data-stu-id="c524c-125">To modify or delete a folder</span></span>  
  
1.  <span data-ttu-id="c524c-126">En el Administrador de informes, navegue a la página **Contenido** y localice el elemento que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="c524c-126">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="c524c-127">Mantenga el mouse sobre el elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c524c-127">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c524c-128">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="c524c-128">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="c524c-129">Se abre la página de propiedades General.</span><span class="sxs-lookup"><span data-stu-id="c524c-129">The General Properties page opens.</span></span>  
  
4.  <span data-ttu-id="c524c-130">Para cambiar la ubicación de la carpeta, haga clic en **Mover**.</span><span class="sxs-lookup"><span data-stu-id="c524c-130">To change the folder location, click **Move**.</span></span> <span data-ttu-id="c524c-131">Escriba la ubicación de la carpeta de destino o elija la carpeta de destino desde el árbol y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c524c-131">Type the location of the destination folder, or choose the destination folder from the tree, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="c524c-132">O bien, modifique las propiedades de la carpeta de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="c524c-132">Or, modify folder properties in the following ways:</span></span>  
  
    -   <span data-ttu-id="c524c-133">Para modificar el texto que se muestra sobre la carpeta, escriba un nombre o una descripción.</span><span class="sxs-lookup"><span data-stu-id="c524c-133">To modify display text about the folder, type a name or description.</span></span>  
  
    -   <span data-ttu-id="c524c-134">Para mostrar la carpeta en la vista predeterminada en la página **Contenido** , desactive **Ocultar en la vista de lista**.</span><span class="sxs-lookup"><span data-stu-id="c524c-134">To display the folder in the default view on the **Contents** page, clear **Hide in list view**.</span></span>  
  
6.  <span data-ttu-id="c524c-135">O bien, haga clic en **Eliminar**para quitar la carpeta y su contenido.</span><span class="sxs-lookup"><span data-stu-id="c524c-135">Or, to remove the folder and its contents, click **Delete**.</span></span>  
  
7.  <span data-ttu-id="c524c-136">Haga clic en **Apply** (Aplicar) para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="c524c-136">Click **Apply** to save changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c524c-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c524c-137">See Also</span></span>  
 <span data-ttu-id="c524c-138">[Página nueva carpeta &#40;Administrador de informes&#41;](../new-folder-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c524c-138">[New Folder Page &#40;Report Manager&#41;](../new-folder-page-report-manager.md) </span></span>  
 <span data-ttu-id="c524c-139">[Administrador de informes de &#40;de página de contenido&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c524c-139">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 [<span data-ttu-id="c524c-140">Buscar, ver y administrar informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c524c-140">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
