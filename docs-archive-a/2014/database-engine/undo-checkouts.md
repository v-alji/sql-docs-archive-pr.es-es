---
title: Deshacer desprotecciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourcControl.UndoCheckDialog
helpviewer_keywords:
- checking out files
- checkout source controls [SQL Server]
- undoing checkouts
ms.assetid: a6596b20-3aa5-4dc4-a4c5-3649f1f5a20e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ff6e6041b59caa75bf7f8530d915db48e0379338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663065"
---
# <a name="undo-checkouts"></a><span data-ttu-id="b1d77-102">Deshacer desprotecciones</span><span class="sxs-lookup"><span data-stu-id="b1d77-102">Undo Checkouts</span></span>
  <span data-ttu-id="b1d77-103">El comando **Deshacer desprotección** se puede utilizar para cancelar una desprotección existente.</span><span class="sxs-lookup"><span data-stu-id="b1d77-103">You can use the **Undo Checkout** command to cancel an existing checkout.</span></span> <span data-ttu-id="b1d77-104">Resulta muy útil cuando se ha modificado y guardado un archivo y, posteriormente, es necesario revertir los cambios.</span><span class="sxs-lookup"><span data-stu-id="b1d77-104">This is particularly useful when you have modified and saved a file, and then later need to roll back your changes.</span></span>  
  
 <span data-ttu-id="b1d77-105">Según las opciones establecidas en el cuadro de diálogo **Opciones avanzadas de Deshacer desprotección** , el entorno de Studio deja la copia de trabajo del elemento en el disco local o la reemplaza por la última versión controlada por código fuente.</span><span class="sxs-lookup"><span data-stu-id="b1d77-105">Depending on the options you set in the **Undo Checkout Advanced Options** dialog box, the Studio environment either leaves the working copy of the item on your local disk or replaces it with the latest source-controlled version.</span></span> <span data-ttu-id="b1d77-106">Si alguien ha modificado el elemento fuera del contexto del sistema de control de código fuente, puede que la versión recuperada no sea la más reciente.</span><span class="sxs-lookup"><span data-stu-id="b1d77-106">If someone has modified the item outside the context of the source control system, the retrieved version may not be the latest one.</span></span>  
  
### <a name="to-undo-a-checkout"></a><span data-ttu-id="b1d77-107">Para deshacer una desprotección</span><span class="sxs-lookup"><span data-stu-id="b1d77-107">To undo a checkout</span></span>  
  
1.  <span data-ttu-id="b1d77-108">En el Explorador de soluciones, seleccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b1d77-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="b1d77-109">En el menú **Archivo** , seleccione **Control de código fuente**y haga clic en **Deshacer desprotección**.</span><span class="sxs-lookup"><span data-stu-id="b1d77-109">On the **File** menu, point to **Source Control**, and then click **Undo Checkout**.</span></span>  
  
3.  <span data-ttu-id="b1d77-110">En el cuadro de diálogo **Deshacer desprotección** , seleccione las opciones adecuadas y haga clic en el botón **Deshacer desprotección** .</span><span class="sxs-lookup"><span data-stu-id="b1d77-110">In the **Undo Checkout** dialog box, select the appropriate options, and then click the **Undo Checkout** button.</span></span>  
  
     <span data-ttu-id="b1d77-111">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="b1d77-111">**Columns**</span></span>  
     <span data-ttu-id="b1d77-112">Identifique las columnas que se van a mostrar y el orden en que lo hacen.</span><span class="sxs-lookup"><span data-stu-id="b1d77-112">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="b1d77-113">**Vista plana**</span><span class="sxs-lookup"><span data-stu-id="b1d77-113">**Flat View**</span></span>  
     <span data-ttu-id="b1d77-114">Muestra los elementos como listas planas en su conexión de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="b1d77-114">Display the items as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="b1d77-115">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="b1d77-115">**Name**</span></span>  
     <span data-ttu-id="b1d77-116">Muestra los nombres de los elementos en los que se deshará la desprotección.</span><span class="sxs-lookup"><span data-stu-id="b1d77-116">Displays the names of the items for which to undo the checkout.</span></span> <span data-ttu-id="b1d77-117">Los elementos aparecen con las casillas que se encuentran junto a ellos activadas.</span><span class="sxs-lookup"><span data-stu-id="b1d77-117">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="b1d77-118">Si no desea deshacer la desprotección de un elemento, desactive su casilla.</span><span class="sxs-lookup"><span data-stu-id="b1d77-118">If you do not want to undo the checkout of an item, clear its check box.</span></span>  
  
     <span data-ttu-id="b1d77-119">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="b1d77-119">**Options**</span></span>  
     <span data-ttu-id="b1d77-120">Si hace clic en la flecha situada a la derecha del botón, se mostrarán opciones de deshacer desprotección específicas del complemento de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="b1d77-120">Displays source control plug-in-specific undo checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="b1d77-121">**Sort**</span><span class="sxs-lookup"><span data-stu-id="b1d77-121">**Sort**</span></span>  
     <span data-ttu-id="b1d77-122">Ordena la visualización de columnas.</span><span class="sxs-lookup"><span data-stu-id="b1d77-122">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="b1d77-123">**Vista de árbol**</span><span class="sxs-lookup"><span data-stu-id="b1d77-123">**Tree View**</span></span>  
     <span data-ttu-id="b1d77-124">Muestra la jerarquía de elementos y carpetas de los objetos en los que se anula la desprotección.</span><span class="sxs-lookup"><span data-stu-id="b1d77-124">Display the folder and item hierarchy for items on which you are reversing the checkout.</span></span>  
  
     <span data-ttu-id="b1d77-125">**Deshacer desprotección**</span><span class="sxs-lookup"><span data-stu-id="b1d77-125">**Undo Checkout**</span></span>  
     <span data-ttu-id="b1d77-126">Anula la desprotección y descarta los cambios en el archivo desprotegido.</span><span class="sxs-lookup"><span data-stu-id="b1d77-126">Revert the checkout, discarding any changes to the checked-out file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d77-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1d77-127">See Also</span></span>  
 <span data-ttu-id="b1d77-128">[Desproteger archivos](../../2014/database-engine/check-out-files.md) </span><span class="sxs-lookup"><span data-stu-id="b1d77-128">[Check Out Files](../../2014/database-engine/check-out-files.md) </span></span>  
 [<span data-ttu-id="b1d77-129">Administrar desprotecciones</span><span class="sxs-lookup"><span data-stu-id="b1d77-129">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
