---
title: Aspectos básicos de scripting de MDX (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], scripts
- calculations [Analysis Services], scripts
- MDX [Analysis Services], scripts
- scripts [MDX]
- cubes [Analysis Services], calculations
- Multidimensional Expressions [Analysis Services], scripts
ms.assetid: fdecb3ce-7c87-4bab-8000-532ba7a29f96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2f7638339d8fc366ee384d453f6df683f3bd41f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675606"
---
# <a name="mdx-scripting-fundamentals-analysis-services"></a><span data-ttu-id="8f31d-102">Aspectos básicos de scripting MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="8f31d-102">MDX Scripting Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="8f31d-103">En [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , un script de expresiones multidimensionales (MDX) se compone de una o más expresiones o instrucciones MDX que rellenan un cubo con cálculos.</span><span class="sxs-lookup"><span data-stu-id="8f31d-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script is made up of one or more MDX expressions or statements that populate a cube with calculations.</span></span>  
  
 <span data-ttu-id="8f31d-104">Un script MDX define el proceso de cálculo del cubo.</span><span class="sxs-lookup"><span data-stu-id="8f31d-104">An MDX script defines the calculation process for a cube.</span></span> <span data-ttu-id="8f31d-105">Los scripts MDX también se consideran parte del cubo.</span><span class="sxs-lookup"><span data-stu-id="8f31d-105">An MDX script is also considered part of the cube itself.</span></span> <span data-ttu-id="8f31d-106">Por lo tanto, si se cambia un script MDX asociado a un cubo, también se cambia de forma inmediata el proceso de cálculo del cubo.</span><span class="sxs-lookup"><span data-stu-id="8f31d-106">Therefore, changing an MDX script associated with a cube immediately changes the calculation process for the cube.</span></span>  
  
 <span data-ttu-id="8f31d-107">Para crear scripts MDX, puede utilizar el Diseñador de cubos de [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f31d-107">To create MDX scripts, you can use Cube Designer in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="8f31d-108">Para más información, vea [Definir asignaciones y otros comandos de script](../define-assignments-and-other-script-commands.md) e [Introduction to MDX Scripting in Microsoft SQL Server 2005 (Introducción a la creación de scripts en Microsoft SQL Server 2005)](https://go.microsoft.com/fwlink/?LinkId=81892).</span><span class="sxs-lookup"><span data-stu-id="8f31d-108">For more information, see [Define Assignments and Other Script Commands](../define-assignments-and-other-script-commands.md) and [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span></span>  
  
 <span data-ttu-id="8f31d-109">Encontrará información acerca de los problemas de rendimiento relacionados con los cálculos y las consultas MDX en la sección dedicada a la optimización de MDX de la [guía de rendimiento de SQL Server Analysis Services](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span><span class="sxs-lookup"><span data-stu-id="8f31d-109">For performance issues related to MDX queries and calculations, see the MDX optimization section in the [SQL Server Analysis Services Performance Guide](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f31d-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8f31d-110">In This Section</span></span>  
  
|<span data-ttu-id="8f31d-111">Tema</span><span class="sxs-lookup"><span data-stu-id="8f31d-111">Topic</span></span>|<span data-ttu-id="8f31d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f31d-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8f31d-113">Script MDX básico &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8f31d-113">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)|<span data-ttu-id="8f31d-114">Incluye información detallada sobre el script MDX básico, incluido el script MDX predeterminado proporcionado en cada cubo, así como información sobre el funcionamiento general de los scripts MDX en los cubos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f31d-114">Details the basic MDX script, including the default MDX script provided in each cube, and how MDX scripts generally function within a cube in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="8f31d-115">Administrar el ámbito y el contexto &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8f31d-115">Managing Scope and Context &#40;MDX&#41;</span></span>](managing-scope-and-context-mdx.md)|<span data-ttu-id="8f31d-116">Describe cómo utilizar la instrucción [CALCULATE](/sql/mdx/mdx-scripting-calculate) , la instrucción [SCOPE](/sql/mdx/mdx-scripting-scope) y la función [This](/sql/mdx/this-mdx) para administrar el contexto y el ámbito de un script MDX.</span><span class="sxs-lookup"><span data-stu-id="8f31d-116">Describes how to use the [CALCULATE](/sql/mdx/mdx-scripting-calculate) statement, the [SCOPE](/sql/mdx/mdx-scripting-scope) statement, and the [This](/sql/mdx/this-mdx) function to manage context and scope within an MDX script.</span></span>|  
|[<span data-ttu-id="8f31d-117">Usar variables y parámetros &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8f31d-117">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="8f31d-118">Describe cómo utilizar las variables y los parámetros en un script MDX.</span><span class="sxs-lookup"><span data-stu-id="8f31d-118">Describes how to use variables and parameters in an MDX script.</span></span>|  
|[<span data-ttu-id="8f31d-119">Control de errores &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8f31d-119">Error Handling &#40;MDX&#41;</span></span>](error-handling-mdx.md)|<span data-ttu-id="8f31d-120">Explica cómo administrar los errores en un script MDX.</span><span class="sxs-lookup"><span data-stu-id="8f31d-120">Explains error handling within an MDX script.</span></span>|  
|[<span data-ttu-id="8f31d-121">Compatibilidad con MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8f31d-121">Supported MDX &#40;MDX&#41;</span></span>](supported-mdx-mdx.md)|<span data-ttu-id="8f31d-122">Proporciona una lista de operadores, instrucciones y funciones MDX admitidos en un script MDX.</span><span class="sxs-lookup"><span data-stu-id="8f31d-122">Provides a list of supported MDX operators, statements, and functions within an MDX script.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f31d-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f31d-123">See Also</span></span>  
 [<span data-ttu-id="8f31d-124">Referencia del lenguaje MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8f31d-124">MDX Language Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-language-reference-mdx)  
  
  
