---
title: Crear conjuntos con nombre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculations [Analysis Services], named sets
- named sets [Analysis Services]
- members [Analysis Services], named sets
ms.assetid: 03cf97a4-1a18-45f3-acb0-35123bd619be
author: minewiskan
ms.author: owend
ms.openlocfilehash: e92984102ceb8ad0ac049c15870e9f1efd6090fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744405"
---
# <a name="create-named-sets"></a><span data-ttu-id="40727-102">Crear conjuntos con nombre</span><span class="sxs-lookup"><span data-stu-id="40727-102">Create Named Sets</span></span>
  <span data-ttu-id="40727-103">Un conjunto con nombre es un conjunto de miembros de dimensión o una expresión de conjunto que se crea para volver a usarse en, por ejemplo, consultas de expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="40727-103">A named set is a set of dimension members or a set expression that is created for reuse, for example in Multidimensional Expressions (MDX) queries.</span></span> <span data-ttu-id="40727-104">Puede crear conjuntos con nombre combinando datos del cubo, operadores aritméticos, números y funciones.</span><span class="sxs-lookup"><span data-stu-id="40727-104">You can create named sets by combining cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="40727-105">Por ejemplo, puede crear un conjunto con nombre llamado Top Ten Factories, que contenga los diez miembros de la dimensión Factories con los valores superiores de la medida Production.</span><span class="sxs-lookup"><span data-stu-id="40727-105">For example, you can create a named set called Top Ten Factories that contains the ten members of the Factories dimension that have the highest values for the Production measure.</span></span> <span data-ttu-id="40727-106">Acto seguido, puede utilizar Top Ten Factories en las consultas de los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="40727-106">Top Ten Factories can then be used in queries by end users.</span></span> <span data-ttu-id="40727-107">Por ejemplo, un usuario final puede colocar Top Ten Factories en un eje y la dimensión Measures, incluyendo a Production, en otro.</span><span class="sxs-lookup"><span data-stu-id="40727-107">For example, an end user can place Top Ten Factories on one axis and the Measures dimension, including Production, on another axis.</span></span> <span data-ttu-id="40727-108">Para más información, vea [Cálculos en modelos multidimensionales](calculations-in-multidimensional-models.md) y [Crear conjuntos con nombre en MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="40727-108">For more information, see [Calculations in Multidimensional Models](calculations-in-multidimensional-models.md), and [Building Named Sets in MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="40727-109">Para crear un conjunto con nombre, utilice el comando **Nuevo conjunto con nombre** en la pestaña **Cálculos** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="40727-109">To create a named set, use the **New Named Set** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="40727-110">Este comando se puede invocar en el menú **Cubo** de la barra de herramientas de la pestaña **Cálculos** .</span><span class="sxs-lookup"><span data-stu-id="40727-110">This command can be invoked on the **Cube** menu on the **Calculations** tab toolbar.</span></span> <span data-ttu-id="40727-111">Este comando muestra un formulario para especificar las siguientes opciones para el conjunto con nombre:</span><span class="sxs-lookup"><span data-stu-id="40727-111">This command displays a form to specify the following options for the named set:</span></span>  
  
 <span data-ttu-id="40727-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="40727-112">**Name**</span></span>  
 <span data-ttu-id="40727-113">Seleccione el nombre del conjunto con nombre.</span><span class="sxs-lookup"><span data-stu-id="40727-113">Select the name of the named set.</span></span> <span data-ttu-id="40727-114">Éste es el nombre que ven los usuarios finales cuando examinan el cubo.</span><span class="sxs-lookup"><span data-stu-id="40727-114">This name appears to end users when they browse the cube.</span></span>  
  
 <span data-ttu-id="40727-115">**Expression**</span><span class="sxs-lookup"><span data-stu-id="40727-115">**Expression**</span></span>  
 <span data-ttu-id="40727-116">Especifique la expresión que crea el conjunto con nombre.</span><span class="sxs-lookup"><span data-stu-id="40727-116">Specify the expression that produces the named set.</span></span> <span data-ttu-id="40727-117">Esta expresión puede escribirse en MDX.</span><span class="sxs-lookup"><span data-stu-id="40727-117">This expression can be written in MDX.</span></span> <span data-ttu-id="40727-118">La expresión puede contener cualquiera de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="40727-118">The expression can contain any of the following:</span></span>  
  
-   <span data-ttu-id="40727-119">Expresiones de datos que representan los componentes del cubo como dimensiones, niveles, medidas, etc.</span><span class="sxs-lookup"><span data-stu-id="40727-119">Data expressions that represent cube components such as dimensions, levels, measures, and so on.</span></span>  
  
-   <span data-ttu-id="40727-120">Operadores aritméticos.</span><span class="sxs-lookup"><span data-stu-id="40727-120">Arithmetic operators.</span></span>  
  
-   <span data-ttu-id="40727-121">Números.</span><span class="sxs-lookup"><span data-stu-id="40727-121">Numbers.</span></span>  
  
-   <span data-ttu-id="40727-122">Funciones.</span><span class="sxs-lookup"><span data-stu-id="40727-122">Functions.</span></span>  
  
 <span data-ttu-id="40727-123">Puede copiar o arrastrar los componentes del cubo desde la pestaña **Metadatos** del panel **Herramientas de cálculo** hasta el cuadro **Expresión** del panel **Editor de Formulario de conjuntos con nombres** .</span><span class="sxs-lookup"><span data-stu-id="40727-123">You can copy or drag cube components from the **Metadata** tab of the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span> <span data-ttu-id="40727-124">Puede copiar o arrastrar funciones desde la pestaña **Funciones** del panel **Herramientas de cálculo** al cuadro **Expresión** del panel **Editor de Formulario de conjuntos con nombres** .</span><span class="sxs-lookup"><span data-stu-id="40727-124">You can copy or drag functions from the **Functions** tab in the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="40727-125">Si crea la expresión de conjunto mediante el nombre explícito de los miembros del conjunto, incluya la lista de miembros en un par de llaves ( {} ).</span><span class="sxs-lookup"><span data-stu-id="40727-125">If you create the set expression by explicitly naming the members in the set, enclose the list of members in a pair of braces ({}).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40727-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40727-126">See Also</span></span>  
 [<span data-ttu-id="40727-127">Cálculos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="40727-127">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)  
  
  
