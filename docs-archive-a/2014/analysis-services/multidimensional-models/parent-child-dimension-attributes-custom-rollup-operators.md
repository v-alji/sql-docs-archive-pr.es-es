---
title: Operadores de resúmenes personalizados en dimensiones de elementos primarios y secundarios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- child rollup operations
- UnaryOperatorColumn property
- custom rollup operators [Analysis Services]
- unary operators
- parent-child dimensions [Analysis Services]
ms.assetid: a3ddd9fc-5fa3-4227-9322-8c45a5b5c2c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: db12ccc6703ee4863dd3b6bd598d2317b54fce6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674402"
---
# <a name="custom-rollup-operators-in-parent-child-dimensions"></a><span data-ttu-id="00176-102">Operadores de resúmenes personalizados en dimensiones de elementos primarios y secundarios</span><span class="sxs-lookup"><span data-stu-id="00176-102">Custom Rollup Operators in Parent-Child Dimensions</span></span>
  <span data-ttu-id="00176-103">Los operadores de resúmenes personalizados constituyen una manera sencilla de controlar la forma en que los valores de los miembros se acumulan en los valores de sus elementos primarios en una jerarquía de elementos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="00176-103">Custom rollup operators provide a simple way to control how member values are rolled up into parent values in a parent-child hierarchy.</span></span> <span data-ttu-id="00176-104">En una dimensión que contiene una relación de elementos primarios y secundarios, se especifica una columna que contiene operadores unarios que especifican el resumen para todos los miembros no calculados del atributo primario.</span><span class="sxs-lookup"><span data-stu-id="00176-104">In a dimension containing a parent-child relationship, you specify a column that contains unary operators that specify rollup for all noncalculated members of the parent attribute.</span></span> <span data-ttu-id="00176-105">El operador unario se aplica a los miembros siempre que los valores de los miembros primarios se evalúan.</span><span class="sxs-lookup"><span data-stu-id="00176-105">The unary operator is applied to members whenever the values of the parent members are evaluated.</span></span>  
  
 <span data-ttu-id="00176-106">Los operadores unarios se almacenan en columnas definidas por la propiedad `UnaryOperatorColumn` del atributo primario y se aplican a cada miembro del atributo.</span><span class="sxs-lookup"><span data-stu-id="00176-106">The unary operators are stored in column defined by the `UnaryOperatorColumn` property of the parent attribute, and they are applied to each member of the attribute.</span></span> <span data-ttu-id="00176-107">La columna especificada por esta propiedad puede residir en la tabla de dimensiones o en una tabla relacionada con ella mediante una clave externa en la tabla de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="00176-107">The column specified by this property can reside either in the dimension table or in a table related to the dimension table by a foreign key in the dimension table.</span></span>  
  
 <span data-ttu-id="00176-108">Los operadores de resúmenes personalizados proporcionan una funcionalidad similar a la de fórmulas de miembro personalizado, pero simplificada.</span><span class="sxs-lookup"><span data-stu-id="00176-108">Custom rollup operators provide functionality similar to, but more simplified than, custom member formulas.</span></span> <span data-ttu-id="00176-109">Una fórmula de miembro personalizado usa expresiones multidimensionales (MDX) para determinar la manera en que se acumulan los miembros.</span><span class="sxs-lookup"><span data-stu-id="00176-109">A custom member formula uses Multidimensional Expressions (MDX) expressions to determine how the members are rolled up.</span></span> <span data-ttu-id="00176-110">En comparación, un operador de resúmenes personalizados usa un operador unario simple para determinar la manera en que el valor de un miembro afecta al elemento primario.</span><span class="sxs-lookup"><span data-stu-id="00176-110">In contrast, a custom rollup operator uses a simple unary operator to determine how the value of a member affects the parent.</span></span> <span data-ttu-id="00176-111">Las formulas de miembro personalizado del nivel precedente en una dimensión anulan al operador de resúmenes personalizados de un nivel.</span><span class="sxs-lookup"><span data-stu-id="00176-111">Custom member formulas of the preceding level in a dimension override a level's custom rollup operator.</span></span>  
  
## <a name="custom-rollup-precedence"></a><span data-ttu-id="00176-112">Prioridad de los resúmenes personalizados</span><span class="sxs-lookup"><span data-stu-id="00176-112">Custom Rollup Precedence</span></span>  
 <span data-ttu-id="00176-113">En términos de prioridad, los operadores de resúmenes personalizados del atributo de origen en un nivel de una jerarquía anulan las fórmulas de miembro personalizado del nivel anterior.</span><span class="sxs-lookup"><span data-stu-id="00176-113">In terms of precedence, the custom rollup operators of the source attribute for a level in a hierarchy override the custom member formulas of the previous level.</span></span> <span data-ttu-id="00176-114">Sin embargo, las fórmulas de miembro personalizado del nivel anterior anulan los operadores de resúmenes personalizados de un nivel.</span><span class="sxs-lookup"><span data-stu-id="00176-114">However, the custom member formulas of the preceding level override the custom rollup operators of a level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00176-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00176-115">See Also</span></span>  
 <span data-ttu-id="00176-116">[Definir fórmulas de miembro personalizado](attribute-properties-define-custom-member-formulas.md) </span><span class="sxs-lookup"><span data-stu-id="00176-116">[Define Custom Member Formulas](attribute-properties-define-custom-member-formulas.md) </span></span>  
 [<span data-ttu-id="00176-117">Operadores unarios en dimensiones de elementos primarios y secundarios</span><span class="sxs-lookup"><span data-stu-id="00176-117">Unary Operators in Parent-Child Dimensions</span></span>](parent-child-dimension-attributes-unary-operators.md)  
  
  
