---
title: Crear conjuntos con nombre de ámbito de sesión (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE SET statement
- session-scoped named sets [MDX]
ms.assetid: b751e1e4-6d4c-4d36-a28d-ffdaaee0f1c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d35bd61dcc59eca8bcb920ed99f2e791631047c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747208"
---
# <a name="creating-session-scoped-named-sets-mdx"></a><span data-ttu-id="beead-102">Crear conjuntos con nombre de ámbito de sesión (MDX)</span><span class="sxs-lookup"><span data-stu-id="beead-102">Creating Session-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="beead-103">Para crear un conjunto con nombre que esté disponible en una sesión de expresiones multidimensionales (MDX), se usa la instrucción [CREATE SET](/sql/mdx/mdx-data-definition-create-set) .</span><span class="sxs-lookup"><span data-stu-id="beead-103">To create a named set that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE SET](/sql/mdx/mdx-data-definition-create-set) statement.</span></span> <span data-ttu-id="beead-104">Un conjunto con nombre creado mediante la instrucción CREATE SET no se quitará hasta que se cierre la sesión MDX.</span><span class="sxs-lookup"><span data-stu-id="beead-104">A named set that is created by using the CREATE SET statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="beead-105">Como se indica en este tema, la sintaxis de la palabra clave WITH es muy simple y fácil de usar.</span><span class="sxs-lookup"><span data-stu-id="beead-105">As discussed in this topic, the syntax of the WITH keyword is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="beead-106">Para obtener más información sobre los conjuntos con nombre, vea [Crear conjuntos con nombre en MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="beead-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="create-set-syntax"></a><span data-ttu-id="beead-107">Sintaxis de CREATE SET</span><span class="sxs-lookup"><span data-stu-id="beead-107">CREATE SET Syntax</span></span>  
 <span data-ttu-id="beead-108">Utilice la siguiente sintaxis para la instrucción CREATE SET:</span><span class="sxs-lookup"><span data-stu-id="beead-108">Use the following syntax for the CREATE SET statement:</span></span>  
  
```  
CREATE SESSION SET [CURRENTCUBE. | <cube name>.]<Set Identifier> AS <Set Expression>  
```  
  
 <span data-ttu-id="beead-109">En la sintaxis de CREATE SET, el parámetro `cube name` contiene el nombre del cubo que incluye los miembros del conjunto con nombre.</span><span class="sxs-lookup"><span data-stu-id="beead-109">In the CREATE SET syntax, the `cube name` parameter contains the name of the cube that contains the members for the named set.</span></span> <span data-ttu-id="beead-110">Si no se especifica el parámetro `cube name` , se utilizará el cubo actual como el cubo que contiene el miembro del conjunto con nombre.</span><span class="sxs-lookup"><span data-stu-id="beead-110">If the `cube name` parameter is not specified, the current cube will be used as the cube that contains the member for the named set.</span></span> <span data-ttu-id="beead-111">Por otra parte, el parámetro `Set_Identifier` incluye el alias del conjunto con nombre; el parámetro `Set_Expression` , por su parte, contiene la expresión de conjunto a la que hará referencia el alias del conjunto con nombre.</span><span class="sxs-lookup"><span data-stu-id="beead-111">Also, the `Set_Identifier` parameter contains the alias for the named set, and the `Set_Expression` parameter contains the set expression to which the named set alias will refer.</span></span>  
  
## <a name="create-set-example"></a><span data-ttu-id="beead-112">Ejemplo de CREATE SET</span><span class="sxs-lookup"><span data-stu-id="beead-112">CREATE SET Example</span></span>  
 <span data-ttu-id="beead-113">En el siguiente ejemplo se utiliza la instrucción CREATE SET para crear el conjunto con nombre `SetCities_2_3` basado en el cubo Store.</span><span class="sxs-lookup"><span data-stu-id="beead-113">The following example uses the CREATE SET statement to create the `SetCities_2_3` named set based on the Store cube.</span></span> <span data-ttu-id="beead-114">Los miembros del conjunto con nombre `SetCities_2_3` son los almacenes de City 2 y City 3.</span><span class="sxs-lookup"><span data-stu-id="beead-114">The members of the `SetCities_2_3` named set are the stores within City 2 and City 3.</span></span>  
  
```  
create Session set [Store].[SetCities_2_3] as  
{[Data Stores].[ByLocation].[State].&[CA].&[City 02],  
[Data Stores].[ByLocation].[State].&[NH].&[City 03]}  
```  
  
 <span data-ttu-id="beead-115">El uso de la instrucción CREATE SET para definir el conjunto con nombre `SetCities_2_3` hace que este conjunto con nombre permanezca disponible mientras esté activa la sesión MDX actual.</span><span class="sxs-lookup"><span data-stu-id="beead-115">By using the CREATE SET statement to define the `SetCities_2_3` named set, this named set remains available for the length of the current MDX session.</span></span> <span data-ttu-id="beead-116">El siguiente ejemplo es una consulta válida que devuelve los miembros City 2 y City 3 y que puede ejecutarse en cualquier momento una vez creado el conjunto con nombre `SetCities_2_3` y antes de que se cierre la sesión.</span><span class="sxs-lookup"><span data-stu-id="beead-116">The following example is a valid query that would return City 2 and City 3 members, and that could be run anytime after you create the `SetCities_2_3` named set and before the session closes.</span></span>  
  
```  
select SetCities_2_3 on 0 from [Store]  
```  
  
## <a name="see-also"></a><span data-ttu-id="beead-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="beead-117">See Also</span></span>  
 [<span data-ttu-id="beead-118">Crear conjuntos con nombre del ámbito de consulta &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="beead-118">Creating Query-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-query-scoped-named-sets.md)  
  
  
