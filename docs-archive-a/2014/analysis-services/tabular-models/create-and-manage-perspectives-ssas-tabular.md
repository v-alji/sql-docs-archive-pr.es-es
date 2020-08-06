---
title: Crear y administrar perspectivas (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.perspectivedb.f1
ms.assetid: 2a411c2b-2820-4086-ad7f-ce6a941fefc7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6d0029ff61aa05e2e83f34833c3d0af17ddb3beb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663763"
---
# <a name="create-and-manage-perspectives-ssas-tabular"></a><span data-ttu-id="74494-102">Crear y administrar perspectivas (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="74494-102">Create and Manage Perspectives (SSAS Tabular)</span></span>
  <span data-ttu-id="74494-103">Las perspectivas definen subconjuntos visibles de un modelo que ofrecen puntos de vista centrados, específicos del negocio o específicos de la aplicación del modelo.</span><span class="sxs-lookup"><span data-stu-id="74494-103">Perspectives define viewable subsets of a model that provide focused, business-specific, or application-specific viewpoints of the model.</span></span> <span data-ttu-id="74494-104">Las tareas de este tema explican cómo crear y administrar perspectivas mediante el cuadro de diálogo **Perspectivas** del diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="74494-104">The tasks in this topic describe how to create and manage perspectives by using the **Perspectives** dialog box in the model designer.</span></span>  
  
 <span data-ttu-id="74494-105">En este tema se incluyen las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="74494-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="74494-106">Para agregar una perspectiva</span><span class="sxs-lookup"><span data-stu-id="74494-106">To add a perspective</span></span>](#bkmk_add)  
  
-   [<span data-ttu-id="74494-107">Para editar una perspectiva</span><span class="sxs-lookup"><span data-stu-id="74494-107">To edit a perspective</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="74494-108">Para cambiar el nombre de una perspectiva</span><span class="sxs-lookup"><span data-stu-id="74494-108">To rename a perspective</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="74494-109">Para eliminar una perspectiva</span><span class="sxs-lookup"><span data-stu-id="74494-109">To delete a perspective</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="74494-110">Para copiar una perspectiva</span><span class="sxs-lookup"><span data-stu-id="74494-110">To copy a perspective</span></span>](#bkmk_copy)  
  
## <a name="tasks"></a><span data-ttu-id="74494-111">Tareas</span><span class="sxs-lookup"><span data-stu-id="74494-111">Tasks</span></span>  
 <span data-ttu-id="74494-112">Para crear las perspectivas, use el cuadro de diálogo **Perspectivas** , donde podrá agregar, editar, eliminar, copiar y ver las perspectivas.</span><span class="sxs-lookup"><span data-stu-id="74494-112">To create perspectives, you will use the **Perspectives** dialog box, where you can add, edit, delete, copy, and view perspectives.</span></span> <span data-ttu-id="74494-113">Para ver el cuadro de diálogo **Perspectivas** , en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic en el menú **Modelo** y en **Perspectivas**.</span><span class="sxs-lookup"><span data-stu-id="74494-113">To view the **Perspectives** dialog box, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click on the **Model** menu, and then click **Perspectives**.</span></span>  
  
###  <a name="to-add-a-perspective"></a><a name="bkmk_add"></a> <span data-ttu-id="74494-114">Para agregar una perspectiva</span><span class="sxs-lookup"><span data-stu-id="74494-114">To add a perspective</span></span>  
  
-   <span data-ttu-id="74494-115">Para agregar una perspectiva nueva, haga clic en **Nueva perspectiva**.</span><span class="sxs-lookup"><span data-stu-id="74494-115">To add a new perspective, click **New Perspective**.</span></span> <span data-ttu-id="74494-116">A continuación puede activar y desactivar los objetos de campo que se van a incluir, así como especificar un nombre para la nueva perspectiva.</span><span class="sxs-lookup"><span data-stu-id="74494-116">You can then check and uncheck field objects to be included and provide a name for the new perspective.</span></span>  
  
     <span data-ttu-id="74494-117">Si crea una perspectiva vacía con todos los objetos de campo, un usuario que use esta perspectiva verá una lista de campos vacía.</span><span class="sxs-lookup"><span data-stu-id="74494-117">If you create an empty perspective with all of the field object fields, then a user using this perspective will see an empty Field List.</span></span> <span data-ttu-id="74494-118">Las perspectivas deben contener al menos una tabla y una columna.</span><span class="sxs-lookup"><span data-stu-id="74494-118">Perspectives should contain at least one table and column.</span></span>  
  
###  <a name="to-edit-a-perspective"></a><a name="bkmk_edit"></a> <span data-ttu-id="74494-119">Para editar una perspectiva</span><span class="sxs-lookup"><span data-stu-id="74494-119">To edit a perspective</span></span>  
  
-   <span data-ttu-id="74494-120">Para modificar una perspectiva, Active y desactive los campos en la columna de la perspectiva, que agrega y quita objetos de campo de la perspectiva.</span><span class="sxs-lookup"><span data-stu-id="74494-120">To modify a perspective, check and uncheck fields in the perspective's column, which adds and removes field objects from the perspective.</span></span>  
  
###  <a name="to-rename-a-perspective"></a><a name="bkmk_rename"></a><span data-ttu-id="74494-121">Para cambiar el nombre de una perspectiva</span><span class="sxs-lookup"><span data-stu-id="74494-121">To rename a perspective</span></span>  
  
-   <span data-ttu-id="74494-122">Al mantener el mouse sobre el encabezado de columna de una perspectiva (el nombre de la perspectiva), aparece el botón **cambiar nombre** .</span><span class="sxs-lookup"><span data-stu-id="74494-122">When you hover over a perspective's column header (the name of the perspective), the **Rename** button appears.</span></span> <span data-ttu-id="74494-123">Para cambiar el nombre de la perspectiva, haga clic en **Cambiar nombre**y, a continuación, escriba un nuevo nombre o edite el nombre existente.</span><span class="sxs-lookup"><span data-stu-id="74494-123">To rename the perspective, click **Rename**, and then enter a new name or edit the existing name.</span></span>  
  
###  <a name="to-delete-a-perspective"></a><a name="bkmk_delete"></a><span data-ttu-id="74494-124">Para eliminar una perspectiva</span><span class="sxs-lookup"><span data-stu-id="74494-124">To delete a perspective</span></span>  
  
-   <span data-ttu-id="74494-125">Al mantener el mouse sobre el encabezado de columna de una perspectiva (el nombre de la perspectiva), aparece el botón **eliminar** .</span><span class="sxs-lookup"><span data-stu-id="74494-125">When you hover over a perspective's column header (the name of the perspective), the **Delete** button appears.</span></span> <span data-ttu-id="74494-126">Para eliminar la perspectiva, haga clic en el botón **Eliminar** y, a continuación, haga clic en **Sí** en la ventana de confirmación.</span><span class="sxs-lookup"><span data-stu-id="74494-126">To delete the perspective, click the **Delete** button, and then click **Yes** in the confirmation window.</span></span>  
  
###  <a name="to-copy-a-perspective"></a><a name="bkmk_copy"></a> <span data-ttu-id="74494-127">Para copiar una perspectiva</span><span class="sxs-lookup"><span data-stu-id="74494-127">To copy a perspective</span></span>  
  
-   <span data-ttu-id="74494-128">Al mantener el mouse sobre el encabezado de columna de una perspectiva, aparece el botón **copiar** .</span><span class="sxs-lookup"><span data-stu-id="74494-128">When you hover over a perspective's column header, the **Copy** button appears.</span></span> <span data-ttu-id="74494-129">Para crear una copia de esa perspectiva, haga clic en el botón **Copiar** .</span><span class="sxs-lookup"><span data-stu-id="74494-129">To create a copy of that perspective, click the **Copy** button.</span></span> <span data-ttu-id="74494-130">Se agregará una copia de la perspectiva seleccionada como una perspectiva nueva a la derecha de las perspectivas existentes.</span><span class="sxs-lookup"><span data-stu-id="74494-130">A copy of the selected perspective is added as a new perspective to the right of existing perspectives.</span></span> <span data-ttu-id="74494-131">La nueva perspectiva hereda el nombre de la perspectiva copiada y se anexa una anotación *-Copia* al final del nombre.</span><span class="sxs-lookup"><span data-stu-id="74494-131">The new perspective inherits the name of the copied perspective and a *- Copy* annotation is appended to the end of the name.</span></span> <span data-ttu-id="74494-132">Por ejemplo, si se crea una copia de la perspectiva *sales* , la nueva perspectiva se denomina *sales-Copy*.</span><span class="sxs-lookup"><span data-stu-id="74494-132">For example, if a copy of the *Sales* perspective is created, the new perspective is called *Sales - Copy*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74494-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74494-133">See Also</span></span>  
 <span data-ttu-id="74494-134">[Perspectivas &#40;SSAS tabular&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="74494-134">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="74494-135">Jerarquías &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="74494-135">Hierarchies &#40;SSAS Tabular&#41;</span></span>](hierarchies-ssas-tabular.md)  
  
  
