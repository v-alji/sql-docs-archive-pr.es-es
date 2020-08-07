---
title: Ejemplos de expresión de grupo (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data [Reporting Services], grouping
- grouping data
- expressions [Reporting Services], adding
- groups [Reporting Services], expressions
ms.assetid: 34cd0249-fc74-4cf2-ba11-7b072992bfd2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128e3fa7aed189fd00072c2c3e961b80f8137c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743946"
---
# <a name="group-expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="0cf1b-102">Ejemplos de expresión de grupo (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="0cf1b-102">Group Expression Examples (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0cf1b-103">En una región de datos, puede agrupar los datos por un solo campo o crear expresiones más complejas que identifiquen los datos por los que se debe realizar la agrupación.</span><span class="sxs-lookup"><span data-stu-id="0cf1b-103">In a data region, you can group data by a single field, or create more complex expressions that identify the data on which to group.</span></span> <span data-ttu-id="0cf1b-104">Las expresiones complejas incluyen referencias a varios campos o parámetros, instrucciones condicionales o código personalizado.</span><span class="sxs-lookup"><span data-stu-id="0cf1b-104">Complex expressions include references to multiple fields or parameters, conditional statements, or custom code.</span></span> <span data-ttu-id="0cf1b-105">Al definir un grupo para una región de datos, debe agregar estas expresiones a las propiedades del **Grupo** .</span><span class="sxs-lookup"><span data-stu-id="0cf1b-105">When you define a group for a data region, you add these expressions to the **Group** properties.</span></span> <span data-ttu-id="0cf1b-106">Para más información, vea [Agregar o eliminar un grupo en una región de datos &#40;Generador de informes y SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0cf1b-106">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="0cf1b-107">Para combinar dos o más grupos basados en expresiones de campo simples, agregue cada campo a la lista de expresiones de grupo en la definición de grupo.</span><span class="sxs-lookup"><span data-stu-id="0cf1b-107">To merge two or more groups that are based on simple field expressions, add each field to the group expressions list in the group definition.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="examples-of-group-expressions"></a><span data-ttu-id="0cf1b-108">Ejemplos de expresiones de grupo</span><span class="sxs-lookup"><span data-stu-id="0cf1b-108">Examples of Group Expressions</span></span>  
 <span data-ttu-id="0cf1b-109">En la siguiente tabla, se incluyen ejemplos de expresiones de grupo que se pueden usar para definir un grupo.</span><span class="sxs-lookup"><span data-stu-id="0cf1b-109">The following table provides examples of group expressions that you can use to define a group.</span></span>  
  
|<span data-ttu-id="0cf1b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cf1b-110">Description</span></span>|<span data-ttu-id="0cf1b-111">Expression</span><span class="sxs-lookup"><span data-stu-id="0cf1b-111">Expression</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="0cf1b-112">Agrupar por el campo `Region` .</span><span class="sxs-lookup"><span data-stu-id="0cf1b-112">Group by the `Region` field.</span></span>|`=Fields!Region.Value`|  
|<span data-ttu-id="0cf1b-113">Agrupar por apellidos y nombre.</span><span class="sxs-lookup"><span data-stu-id="0cf1b-113">Group by last name and first name.</span></span>|`=Fields!LastName.Value`<br /><br /> `=Fields!FirstName.Value`|  
|<span data-ttu-id="0cf1b-114">Agrupar por la primera letra del apellido.</span><span class="sxs-lookup"><span data-stu-id="0cf1b-114">Group by the first letter of the last name.</span></span>|`=Fields!LastName.Value.Substring(0,1)`|  
|<span data-ttu-id="0cf1b-115">Agrupar por parámetro, en función de la selección del usuario.</span><span class="sxs-lookup"><span data-stu-id="0cf1b-115">Group by parameter, based on user selection.</span></span><br /><br /> <span data-ttu-id="0cf1b-116">En este ejemplo, el parámetro `GroupBy` debe estar basado en una lista de valores disponibles que proporcione una opción válida por la que agrupar.</span><span class="sxs-lookup"><span data-stu-id="0cf1b-116">In this example, the parameter `GroupBy` must be based on an available values list that provides a valid choice to group on.</span></span>|`=Fields(Parameters!GroupBy.Value).Value`|  
|<span data-ttu-id="0cf1b-117">Agrupar por tres intervalos de edad independientes:</span><span class="sxs-lookup"><span data-stu-id="0cf1b-117">Group by three separate age ranges:</span></span><br /><br /> <span data-ttu-id="0cf1b-118">"Under 21", "Between 21 and 50" y "Over 50".</span><span class="sxs-lookup"><span data-stu-id="0cf1b-118">"Under 21", "Between 21 and 50", and "Over 50".</span></span>|`=IIF(First(Fields!Age.Value)<21,"Under 21",(IIF(First(Fields!Age.Value)>=21 AND First(Fields!Age.Value)<=50,"Between 21 and 50","Over 50")))`|  
|<span data-ttu-id="0cf1b-119">Agrupar por varios intervalos de edad.</span><span class="sxs-lookup"><span data-stu-id="0cf1b-119">Group by many age ranges.</span></span> <span data-ttu-id="0cf1b-120">En este ejemplo se muestra código personalizado, escrito en .NET [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] , que devuelve una cadena para los intervalos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0cf1b-120">This example shows custom code, written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, that returns a string for the following ranges:</span></span><br /><br /> <span data-ttu-id="0cf1b-121">25 or Under</span><span class="sxs-lookup"><span data-stu-id="0cf1b-121">25 or Under</span></span><br /><br /> <span data-ttu-id="0cf1b-122">26 to 50</span><span class="sxs-lookup"><span data-stu-id="0cf1b-122">26 to 50</span></span><br /><br /> <span data-ttu-id="0cf1b-123">51 to 75</span><span class="sxs-lookup"><span data-stu-id="0cf1b-123">51 to 75</span></span><br /><br /> <span data-ttu-id="0cf1b-124">Over 75</span><span class="sxs-lookup"><span data-stu-id="0cf1b-124">Over 75</span></span>|`=Code.GetRangeValueByAge(Fields!Age.Value)`<br /><br /> <span data-ttu-id="0cf1b-125">Código personalizado:</span><span class="sxs-lookup"><span data-stu-id="0cf1b-125">Custom code:</span></span><br /><br /> `Function GetRangeValueByAge(ByVal age As Integer) As String`<br /><br /> `Select Case age`<br /><br /> `Case 0 To 25`<br /><br /> `GetRangeValueByByAge = "25 or Under"`<br /><br /> `Case 26 To 50`<br /><br /> `GetRangeValueByByAge = "26 to 50"`<br /><br /> `Case 51 to 75`<br /><br /> `GetRangeValueByByAge = "51 to 75"`<br /><br /> `Case Else`<br /><br /> `GetRangeValueByByAge = "Over 75"`<br /><br /> `End Select`<br /><br /> `Return GetRangeValueByByAge`<br /><br /> `End Function`|  
  
## <a name="see-also"></a><span data-ttu-id="0cf1b-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0cf1b-126">See Also</span></span>  
 <span data-ttu-id="0cf1b-127">[Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0cf1b-127">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0cf1b-128">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0cf1b-128">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0cf1b-129">Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf1b-129">Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;</span></span>](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)  
  
  
