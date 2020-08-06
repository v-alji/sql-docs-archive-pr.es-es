---
title: Perspectivas en modelos multidimensionales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default members
- hiding objects from perspective
- renaming perspectives
- attributes [Analysis Services], default members
- removing perspectives
- perspectives [Analysis Services]
- names [Analysis Services], perspectives
- cubes [Analysis Services], perspectives
- deleting perspectives
ms.assetid: 5a3d6577-6833-4c24-820c-b65bb856157b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2d4be87ddbd691710b361d8b07d225bce37659fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670645"
---
# <a name="perspectives-in-multidimensional-models"></a><span data-ttu-id="516ce-102">Perspectivas de modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="516ce-102">Perspectives in Multidimensional Models</span></span>
  <span data-ttu-id="516ce-103">Una perspectiva es un subconjunto de un cubo creado para una aplicación o grupo de usuarios específico.</span><span class="sxs-lookup"><span data-stu-id="516ce-103">A perspective is a subset of a cube created for a particular application or group of users.</span></span> <span data-ttu-id="516ce-104">El cubo es la perspectiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="516ce-104">The cube itself is the default perspective.</span></span> <span data-ttu-id="516ce-105">Una perspectiva se muestra al cliente como un cubo.</span><span class="sxs-lookup"><span data-stu-id="516ce-105">A perspective is exposed to a client as a cube.</span></span> <span data-ttu-id="516ce-106">Cuando el usuario ve una perspectiva, se muestra como otro cubo.</span><span class="sxs-lookup"><span data-stu-id="516ce-106">When a user views a perspective, it appears like another cube.</span></span> <span data-ttu-id="516ce-107">Los cambios realizados en los datos del cubo mediante la reescritura en la perspectiva se realizan en el cubo original.</span><span class="sxs-lookup"><span data-stu-id="516ce-107">Any changes made to cube data through writeback in the perspective are to the original cube.</span></span> <span data-ttu-id="516ce-108">Para obtener más información sobre las vistas de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vea [Perspectivas](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="516ce-108">For more information about the views in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], see [Perspectives](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span></span>  
  
 <span data-ttu-id="516ce-109">Puede usar la pestaña **Perspectivas** del Diseñador de cubos para crear y modificar las perspectivas de un cubo.</span><span class="sxs-lookup"><span data-stu-id="516ce-109">Use the **Perspectives** tab in Cube Designer to create or modify perspectives in a cube.</span></span> <span data-ttu-id="516ce-110">La primera columna de la pestaña **Perspectivas** es la columna **Objetos de cubo** , que muestra todos los objetos del cubo.</span><span class="sxs-lookup"><span data-stu-id="516ce-110">The first column of the **Perspectives** tab is the **Cube Objects** column, which lists all the objects in the cube.</span></span> <span data-ttu-id="516ce-111">Se corresponde con la perspectiva predeterminada del cubo, que es el propio cubo.</span><span class="sxs-lookup"><span data-stu-id="516ce-111">This corresponds to the default perspective for the cube, which is the cube itself.</span></span>  
  
## <a name="creating-or-deleting-perspectives"></a><span data-ttu-id="516ce-112">Crear o eliminar perspectivas</span><span class="sxs-lookup"><span data-stu-id="516ce-112">Creating or Deleting Perspectives</span></span>  
 <span data-ttu-id="516ce-113">Para agregar una perspectiva a la pestaña **Perspectivas** , haga clic en **Nueva perspectiva** en el menú **Cubo** .</span><span class="sxs-lookup"><span data-stu-id="516ce-113">You can add a perspective to the **Perspectives** tab by clicking **New Perspective** on the **Cube** menu.</span></span> <span data-ttu-id="516ce-114">También puede hacer clic en el botón **Nueva perspectiva** de la barra de herramientas o hacer clic con el botón derecho en el panel y hacer clic en **Nueva perspectiva** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="516ce-114">You can also click the **New Perspective** button on the toolbar, or right-click anywhere in the pane and click **New Perspective** on the shortcut menu.</span></span> <span data-ttu-id="516ce-115">Puede agregar cualquier cantidad de perspectivas al cubo.</span><span class="sxs-lookup"><span data-stu-id="516ce-115">You can add any number of perspectives to a cube.</span></span>  
  
 <span data-ttu-id="516ce-116">Para quitar una perspectiva, haga clic en una celda de la columna de la perspectiva que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="516ce-116">To remove a perspective, first click any cell in the column for the perspective that you want to delete.</span></span> <span data-ttu-id="516ce-117">A continuación, en el menú **Cubo** , haga clic en **Eliminar perspectiva**.</span><span class="sxs-lookup"><span data-stu-id="516ce-117">Then, on the **Cube** menu, click **Delete Perspective**.</span></span> <span data-ttu-id="516ce-118">También puede hacer clic en el botón **Eliminar perspectiva** en la barra de herramientas, o bien hacer clic con el botón derecho en la perspectiva que quiera eliminar y, después, hacer clic en **Eliminar perspectiva** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="516ce-118">You can also click the **Delete Perspective** button on the toolbar, or right-click any cell in the perspective you want to delete, and then click **Delete Perspective** on the shortcut menu.</span></span>  
  
## <a name="renaming-perspectives"></a><span data-ttu-id="516ce-119">perspectivas, cambiar nombre</span><span class="sxs-lookup"><span data-stu-id="516ce-119">Renaming Perspectives</span></span>  
 <span data-ttu-id="516ce-120">La primera fila de cada perspectiva muestra el nombre.</span><span class="sxs-lookup"><span data-stu-id="516ce-120">The first row of each perspective shows its name.</span></span> <span data-ttu-id="516ce-121">Al crear una perspectiva, el nombre inicial es Perspectiva (seguido de un número ordinal, comenzando por 1, si ya existiese una perspectiva denominada Perspectiva).</span><span class="sxs-lookup"><span data-stu-id="516ce-121">When you create a perspective, the name is initially Perspective (followed by an ordinal number, starting with 1, if there is already a perspective called Perspective).</span></span> <span data-ttu-id="516ce-122">Para editar el nombre de una perspectiva, haga clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="516ce-122">You can click the name to edit it.</span></span>  
  
## <a name="hiding-objects-from-a-perspective"></a><span data-ttu-id="516ce-123">Ocultar objetos de una perspectiva</span><span class="sxs-lookup"><span data-stu-id="516ce-123">Hiding Objects from a Perspective</span></span>  
 <span data-ttu-id="516ce-124">Para ocultar un objeto de una perspectiva, desactive la casilla de la fila correspondiente al objeto de la columna de la perspectiva.</span><span class="sxs-lookup"><span data-stu-id="516ce-124">To hide an object from a perspective, clear the check box in the row that corresponds to the object in the column for the perspective.</span></span> <span data-ttu-id="516ce-125">Entre los objetos del cubo que pueden ocultarse de una perspectiva se encuentran:</span><span class="sxs-lookup"><span data-stu-id="516ce-125">The cube objects that can be hidden from a perspective are:</span></span>  
  
-   <span data-ttu-id="516ce-126">Grupos de medida</span><span class="sxs-lookup"><span data-stu-id="516ce-126">Measure groups</span></span>  
  
-   <span data-ttu-id="516ce-127">Medidas</span><span class="sxs-lookup"><span data-stu-id="516ce-127">Measures</span></span>  
  
-   <span data-ttu-id="516ce-128">Dimensions</span><span class="sxs-lookup"><span data-stu-id="516ce-128">Dimensions</span></span>  
  
-   <span data-ttu-id="516ce-129">Jerarquías</span><span class="sxs-lookup"><span data-stu-id="516ce-129">Hierarchies</span></span>  
  
-   <span data-ttu-id="516ce-130">Conjuntos con nombre</span><span class="sxs-lookup"><span data-stu-id="516ce-130">Named sets</span></span>  
  
-   <span data-ttu-id="516ce-131">KPI</span><span class="sxs-lookup"><span data-stu-id="516ce-131">KPIs</span></span>  
  
-   <span data-ttu-id="516ce-132">Acciones</span><span class="sxs-lookup"><span data-stu-id="516ce-132">Actions</span></span>  
  
-   <span data-ttu-id="516ce-133">Miembros calculados</span><span class="sxs-lookup"><span data-stu-id="516ce-133">Calculated members</span></span>  
  
 <span data-ttu-id="516ce-134">Para ver un objeto, expanda la categoría (**Grupos de medida**, **Dimensiones**, **KPI**, **Cálculos**o **Acciones**) para cualquier tipo de objeto en **Objetos de cubo**.</span><span class="sxs-lookup"><span data-stu-id="516ce-134">To view any object, expand the category (**Measure Groups**, **Dimensions**, **KPIs**, **Calculations**, or **Actions**) for any object type under **Cube Objects**.</span></span> <span data-ttu-id="516ce-135">Para ver las jerarquías o los atributos de una dimensión, expanda primero una dimensión y, a continuación, la fila **Jerarquías** o **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="516ce-135">To view hierarchies or attributes in a dimension, first expand a dimension, and then expand the **Hierarchies** or **Attributes** row.</span></span> <span data-ttu-id="516ce-136">Para ver las medidas de un grupo de medida, expanda el grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="516ce-136">To view measures in a measure group, expand the measure group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="516ce-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="516ce-137">See Also</span></span>  
 [<span data-ttu-id="516ce-138">Cubos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="516ce-138">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
