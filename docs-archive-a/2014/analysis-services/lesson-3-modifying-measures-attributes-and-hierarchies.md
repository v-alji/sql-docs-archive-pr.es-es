---
title: 'Lección 3: modificar medidas, atributos y jerarquías | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 17d243cb-9bfb-43d7-8e6f-4d601fd62150
author: minewiskan
ms.author: owend
ms.openlocfilehash: c410136540a0ba85d50fbabc8b2d3c52be1823f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674422"
---
# <a name="lesson-3-modifying-measures-attributes-and-hierarchies"></a><span data-ttu-id="84700-102">Lección 3: Modificar medidas, atributos y jerarquías</span><span class="sxs-lookup"><span data-stu-id="84700-102">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>
  <span data-ttu-id="84700-103">Una vez definido el cubo inicial, estará listo para mejorar la utilidad y la facilidad de uso del cubo.</span><span class="sxs-lookup"><span data-stu-id="84700-103">After defining your initial cube, you are ready to improve the usefulness and friendliness of the cube.</span></span> <span data-ttu-id="84700-104">Puede hacerlo agregando jerarquías que admitan navegación y agregación en varios niveles, aplicando formatos a la medida específica, y definiendo cálculos y relaciones.</span><span class="sxs-lookup"><span data-stu-id="84700-104">You can do this by adding hierarchies that support navigation and aggregation at various levels, by applying formats to specific measure, and by defining calculations and relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84700-105">Los proyectos completos para todas las lecciones de este tutorial están disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="84700-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="84700-106">Puede saltar a continuación a cualquier lección con el proyecto completado de la lección anterior como punto de partida.</span><span class="sxs-lookup"><span data-stu-id="84700-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="84700-107">[Haga clic aquí](https://go.microsoft.com/fwlink/?LinkID=221866) para descargar los proyectos de ejemplo que tienen que ver con este tutorial.</span><span class="sxs-lookup"><span data-stu-id="84700-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="84700-108">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="84700-108">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="84700-109">Modificar medidas</span><span class="sxs-lookup"><span data-stu-id="84700-109">Modifying Measures</span></span>](lesson-3-1-modifying-measures.md)  
 <span data-ttu-id="84700-110">En esta tarea, debe especificar las propiedades de formato para las medidas de moneda y porcentaje del cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="84700-110">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
 [<span data-ttu-id="84700-111">Modificar la dimensión Customer</span><span class="sxs-lookup"><span data-stu-id="84700-111">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
 <span data-ttu-id="84700-112">En esta tarea, debe crear una jerarquía de usuario, crear cálculos con nombre, modificar atributos para utilizarlos en cálculos con nombre, y agrupar atributos de grupo y jerarquías de usuario en carpetas para mostrar.</span><span class="sxs-lookup"><span data-stu-id="84700-112">In this task, you define a user hierarchy, create named calculations, modify attributes to use named calculations, and group attributes and user hierarchies into display folders.</span></span>  
  
 [<span data-ttu-id="84700-113">Modificar la dimensión Product</span><span class="sxs-lookup"><span data-stu-id="84700-113">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
 <span data-ttu-id="84700-114">En esta tarea, debe definir una jerarquía de usuarios, crear cálculos con nombre, definir el nombre de miembro Todos y definir carpetas para mostrar.</span><span class="sxs-lookup"><span data-stu-id="84700-114">In this task, you define a user hierarchy, create named calculations, define the All member name, and define display folders.</span></span>  
  
 [<span data-ttu-id="84700-115">Modificar la dimensión Date</span><span class="sxs-lookup"><span data-stu-id="84700-115">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
 <span data-ttu-id="84700-116">En esta tarea, debe definir una jerarquía de usuario, modificar nombres de miembros de atributo y utilizar claves compuestas para especificar miembros de atributo únicos.</span><span class="sxs-lookup"><span data-stu-id="84700-116">In this task, you define a user hierarchy, modify attribute member names, and use composite keys to specify unique attribute members.</span></span>  
  
 [<span data-ttu-id="84700-117">Examinar el cubo implementado</span><span class="sxs-lookup"><span data-stu-id="84700-117">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
 <span data-ttu-id="84700-118">En esta tarea, debe explorar los datos del cubo usando el explorador del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="84700-118">In this task, you browse cube data by using the browser in Cube Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84700-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84700-119">See Also</span></span>  
 <span data-ttu-id="84700-120">[Escenario de Analysis Services tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="84700-120">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="84700-121">Creación de modelos multidimensionales &#40;tutorial de Adventure Works&#41;</span><span class="sxs-lookup"><span data-stu-id="84700-121">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
