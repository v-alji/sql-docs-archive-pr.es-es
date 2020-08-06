---
title: Agregar o eliminar una jerarquía definida por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], adding
- removing hierarchies
- adding hierarchies
- deleting hierarchies
- hierarchies [Analysis Services], removing
ms.assetid: 953818b4-9543-4c01-bb20-1d45ec6dfb91
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20404a1d93d57221eb830366392eb90600f26c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674387"
---
# <a name="add-or-delete-a-user-defined-hierarchy"></a><span data-ttu-id="e0042-102">Agregar o eliminar una jerarquía definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="e0042-102">Add or Delete a User-Defined Hierarchy</span></span>
  <span data-ttu-id="e0042-103">Las jerarquías definidas por el usuario se pueden agregar a una dimensión o quitar de ella en la pestaña **Estructura de dimensión** del Diseñador de dimensiones de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0042-103">You add a user-defined hierarchy to or remove a user-defined hierarchy from a dimension on the **Dimension Structure** tab in Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e0042-104">Al agregar una jerarquía definida por el usuario, no está a disposición de los usuarios hasta que se crea una instancia de ella en una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y se procesa la dimensión.</span><span class="sxs-lookup"><span data-stu-id="e0042-104">When you add a user-defined hierarchy, it is not available to users until it is instantiated in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the dimension is processed.</span></span> <span data-ttu-id="e0042-105">Para obtener más información, vea bases de datos de [modelos multidimensionales &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) y [procesamiento de objetos de modelo multidimensional](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="e0042-105">For more information, see [Multidimensional Model Databases &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) and [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-add-a-user-defined-hierarchy-to-a-dimension"></a><span data-ttu-id="e0042-106">Para agregar una jerarquía definida por el usuario a una dimensión</span><span class="sxs-lookup"><span data-stu-id="e0042-106">To add a user-defined hierarchy to a dimension</span></span>  
  
1.  <span data-ttu-id="e0042-107">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] correspondiente y a continuación, abra la dimensión con la que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="e0042-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the appropriate [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then open the dimension with which you want to work.</span></span>  
  
     <span data-ttu-id="e0042-108">La dimensión se abre en la pestaña **Estructura de dimensión** del Diseñador de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="e0042-108">The dimension opens in Dimension Designer on the **Dimension Structure** tab.</span></span>  
  
2.  <span data-ttu-id="e0042-109">Arrastre el atributo que quiera usar de la jerarquía definida por el usuario desde el panel **Atributos** hasta el panel **Jerarquías** .</span><span class="sxs-lookup"><span data-stu-id="e0042-109">From the **Attributes** pane, drag an attribute that you want to use in the user-defined hierarchy to the **Hierarchies** pane.</span></span>  
  
3.  <span data-ttu-id="e0042-110">Arrastre atributos adicionales para formar niveles en la jerarquía definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e0042-110">Drag additional attributes to form levels in the user-defined hierarchy.</span></span>  
  
     <span data-ttu-id="e0042-111">El orden en que se muestran los atributos en la jerarquía es importante.</span><span class="sxs-lookup"><span data-stu-id="e0042-111">The order in which attributes are listed in the hierarchy is important.</span></span> <span data-ttu-id="e0042-112">Por ejemplo, en una jerarquía de tiempo, los años deberían aparecer por encima de los días.</span><span class="sxs-lookup"><span data-stu-id="e0042-112">For example, in a time hierarchy, years should appear higher in the hierarchy list than days.</span></span>  
  
4.  <span data-ttu-id="e0042-113">Opcionalmente, vuelva a ordenar los niveles de la jerarquía definida por el usuario arrastrándolos a las posiciones correctas.</span><span class="sxs-lookup"><span data-stu-id="e0042-113">Optionally, rearrange the levels in the user-defined hierarchy by dragging them to the correct positions.</span></span>  
  
5.  <span data-ttu-id="e0042-114">Si lo desea, puede modificar las propiedades de la jerarquía definida por el usuario o sus niveles.</span><span class="sxs-lookup"><span data-stu-id="e0042-114">Optionally, modify properties of the user-defined hierarchy or its levels.</span></span>  
  
     <span data-ttu-id="e0042-115">Por ejemplo, quizá quiera especificar un nombre para la jerarquía definida por el usuario, cambiar el nombre de alguno de sus niveles y definir un nombre personalizado para el nivel Todos.</span><span class="sxs-lookup"><span data-stu-id="e0042-115">For example, you might want to specify a name for the user-defined hierarchy, rename one or more of its levels, and define a custom name for the All level.</span></span> <span data-ttu-id="e0042-116">Para obtener más información, vea [propiedades de jerarquía de usuario](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md)y propiedades de [nivel &#91;Paved sobre&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e0042-116">For more information, see [User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md), and [Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0042-117">De forma predeterminada, una jerarquía definida por el usuario simplemente es una ruta de acceso que permite a los usuarios profundizar para obtener información.</span><span class="sxs-lookup"><span data-stu-id="e0042-117">By default, a user-defined hierarchy is just a path that enables users to drill down for information.</span></span> <span data-ttu-id="e0042-118">Sin embargo, si hay relaciones entre los niveles, puede mejorar el rendimiento de las consultas configurando relaciones de atributo entre los niveles.</span><span class="sxs-lookup"><span data-stu-id="e0042-118">However, if relationships exist between levels, you can increase query performance by configuring attribute relationships between levels.</span></span> <span data-ttu-id="e0042-119">Para obtener más información, vea [Relaciones de atributo](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) y [Definir relaciones de atributo](attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="e0042-119">For more information, see [Attribute Relationships](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) and [Define Attribute Relationships](attribute-relationships-define.md).</span></span>  
  
### <a name="to-remove-a-user-defined-hierarchy-from-a-dimension"></a><span data-ttu-id="e0042-120">Para quitar una jerarquía definida por el usuario de una dimensión</span><span class="sxs-lookup"><span data-stu-id="e0042-120">To remove a user-defined hierarchy from a dimension</span></span>  
  
-   <span data-ttu-id="e0042-121">En la pestaña **Estructura de dimensión** , haga clic en la jerarquía definida por el usuario que quiera quitar en el panel **Jerarquías** .</span><span class="sxs-lookup"><span data-stu-id="e0042-121">On the **Dimension Structure** tab, click the user-defined hierarchy that you want to remove in the **Hierarchies** pane.</span></span> <span data-ttu-id="e0042-122">En la barra de herramientas, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e0042-122">On the toolbar, click **Delete**.</span></span>  
  
     - <span data-ttu-id="e0042-123">O</span><span class="sxs-lookup"><span data-stu-id="e0042-123">or -</span></span>  
  
-   <span data-ttu-id="e0042-124">Haga clic con el botón derecho en la jerarquía definida por el usuario que quiera quitar en el panel **Jerarquías** y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e0042-124">Right-click the user-defined hierarchy that you want to remove in the **Hierarchies** pane and then click **Delete**.</span></span>  
  
     - <span data-ttu-id="e0042-125">O</span><span class="sxs-lookup"><span data-stu-id="e0042-125">or -</span></span>  
  
-   <span data-ttu-id="e0042-126">Arrastre la jerarquía definida por el usuario fuera de de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="e0042-126">Drag the user-defined hierarchy off of the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0042-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0042-127">See Also</span></span>  
 <span data-ttu-id="e0042-128">[Jerarquías de usuario](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="e0042-128">[User Hierarchies](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span></span>  
 [<span data-ttu-id="e0042-129">Crear jerarquías definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="e0042-129">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
  
  
