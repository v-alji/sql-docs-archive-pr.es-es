---
title: Aspectos básicos de las consultas MDX (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- statements [MDX]
- Multidimensional Expressions [Analysis Services], statements
- Multidimensional Expressions [Analysis Services], queries
- MDX [Analysis Services], statements
- MDX queries [Analysis Services]
- MDX [Analysis Services], queries
- queries [MDX]
ms.assetid: a560383b-bb58-472e-95f5-65d03d8ea08b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a2a9a4f564bc33cc7a1b41a1a4c766c7a76a2cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675609"
---
# <a name="mdx-query-fundamentals-analysis-services"></a><span data-ttu-id="b7d28-102">Aspectos básicos de las consultas MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b7d28-102">MDX Query Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="b7d28-103">Las expresiones multidimensionales (MDX) permiten consultar objetos multidimensionales, como los cubos, y devolver conjuntos de celdas multidimensionales que contengan los datos del cubo.</span><span class="sxs-lookup"><span data-stu-id="b7d28-103">Multidimensional Expressions (MDX) lets you query multidimensional objects, such as cubes, and return multidimensional cellsets that contain the cube's data.</span></span> <span data-ttu-id="b7d28-104">Este tema y los temas secundarios proporcionan información general sobre las consultas MDX.</span><span class="sxs-lookup"><span data-stu-id="b7d28-104">This topic and its subtopics provide an overview of MDX queries.</span></span>  
  
 <span data-ttu-id="b7d28-105">En los temas siguientes se describen las consultas MDX y los conjuntos de celdas que generan, y proporcionan información más detallada acerca de la sintaxis básica de MDX.</span><span class="sxs-lookup"><span data-stu-id="b7d28-105">The following topics describe MDX queries and the cellsets they produce, and provide more detailed information about basic MDX syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7d28-106">Para obtener más información acerca de los problemas de rendimiento relacionados con las consultas y los cálculos de MDX, vea la sección sobre escritura de MDX eficaz en la [Guía de rendimiento de SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="b7d28-106">For more information about performance issues related to MDX queries and calculations, see the section "Writing Efficient MDX" in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7d28-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b7d28-107">In This Section</span></span>  
  
|<span data-ttu-id="b7d28-108">Tema</span><span class="sxs-lookup"><span data-stu-id="b7d28-108">Topic</span></span>|<span data-ttu-id="b7d28-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7d28-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b7d28-110">Consulta de MDX básica &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-110">The Basic MDX Query &#40;MDX&#41;</span></span>](mdx-query-the-basic-query.md)|<span data-ttu-id="b7d28-111">Proporciona información sobre la sintaxis básica para la instrucción MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="b7d28-111">Provides basic syntax information for the MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="b7d28-112">Restringir la consulta con ejes de consulta y segmentador &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-112">Restricting the Query with Query and Slicer Axes &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-restricting-the-query.md)|<span data-ttu-id="b7d28-113">Describe los ejes de consulta y segmentador y cómo especificarlos.</span><span class="sxs-lookup"><span data-stu-id="b7d28-113">Describes what query and slicer axes are and how to specify them.</span></span>|  
|[<span data-ttu-id="b7d28-114">Establecer el contexto de cubo en una consulta &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-114">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)|<span data-ttu-id="b7d28-115">Proporciona una descripción del objetivo de la cláusula FROM en las instrucciones MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="b7d28-115">Provides a description of the purpose of the FROM clause in an MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="b7d28-116">Crear conjuntos con nombre en MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-116">Building Named Sets in MDX &#40;MDX&#41;</span></span>](mdx-named-sets-building-named-sets.md)|<span data-ttu-id="b7d28-117">Describe el objetivo de los conjuntos con nombre en MDX así como las técnicas necesarias para crearlos y utilizarlos en consultas MDX.</span><span class="sxs-lookup"><span data-stu-id="b7d28-117">Describes the purpose of named sets in MDX, and the techniques needed to create and use them in MDX queries.</span></span>|  
|[<span data-ttu-id="b7d28-118">Generar miembros calculados en MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-118">Building Calculated Members in MDX &#40;MDX&#41;</span></span>](mdx-calculated-members-building-calculated-members.md)|<span data-ttu-id="b7d28-119">Proporciona información acerca de los miembros calculados en MDX, incluidas las técnicas necesarias para crearlos y utilizarlos en expresiones MDX.</span><span class="sxs-lookup"><span data-stu-id="b7d28-119">Provides information about calculated members in MDX, including the techniques needed to create and use them in MDX expressions.</span></span>|  
|[<span data-ttu-id="b7d28-120">Generar cálculos de celdas en MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-120">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)|<span data-ttu-id="b7d28-121">Detalla el proceso de creación y uso de las celdas calculadas.</span><span class="sxs-lookup"><span data-stu-id="b7d28-121">Details the process of creating and using calculated cells.</span></span>|  
|[<span data-ttu-id="b7d28-122">Crear y usar los valores de propiedad &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-122">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)|<span data-ttu-id="b7d28-123">Detalla el proceso de creación y uso de las propiedades de dimensión, nivel, miembro y celda.</span><span class="sxs-lookup"><span data-stu-id="b7d28-123">Details the process of creating and using dimension, level, member, and cell properties.</span></span>|  
|[<span data-ttu-id="b7d28-124">Manipular datos &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-124">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)|<span data-ttu-id="b7d28-125">Describe los aspectos básicos para la manipulación de datos mediante la obtención de datos y resúmenes, además del orden de paso y resolución en MDX.</span><span class="sxs-lookup"><span data-stu-id="b7d28-125">Describes the basics behind manipulating data using drillthrough and rollup, and also describes pass order and solve order in MDX.</span></span>|  
|[<span data-ttu-id="b7d28-126">Modificar datos &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-126">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)|<span data-ttu-id="b7d28-127">Describe cómo utilizar las reescrituras para cambiar temporal o permanentemente datos multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="b7d28-127">Describes how to use writebacks to temporarily or permanently change multidimensional data.</span></span>|  
|[<span data-ttu-id="b7d28-128">Usar variables y parámetros &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-128">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="b7d28-129">Describe cómo utilizar las variables y los parámetros en consultas MDX.</span><span class="sxs-lookup"><span data-stu-id="b7d28-129">Describes how to use variables and parameters within MDX queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7d28-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7d28-130">See Also</span></span>  
 [<span data-ttu-id="b7d28-131">Referencia de expresiones multidimensionales &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d28-131">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
