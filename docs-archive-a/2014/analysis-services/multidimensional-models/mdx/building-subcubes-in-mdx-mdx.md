---
title: Generar subcubos en MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], subcubes
- subcubes [MDX]
- filtered views [MDX]
- MDX [Analysis Services], subcubes
- Multidimensional Expressions [Analysis Services], subcubes
- CREATE SUBCUBE statement
ms.assetid: 5403a62b-99ac-4d83-b02a-89bf78bf0f46
author: minewiskan
ms.author: owend
ms.openlocfilehash: 653b4d30aa86f52179c7b13619ac4347aa65c339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674410"
---
# <a name="building-subcubes-in-mdx-mdx"></a><span data-ttu-id="e54d2-102">Generar subcubos en MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="e54d2-102">Building Subcubes in MDX (MDX)</span></span>
  <span data-ttu-id="e54d2-103">Un subcubo es un subconjunto de un cubo en la representación de una vista filtrada de los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="e54d2-103">A subcube is a subset of a cube on representing a filtered view of the underlying data.</span></span> <span data-ttu-id="e54d2-104">El hecho de limitar un cubo a un subcubo permite mejorar el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="e54d2-104">By limiting the cube to a subcube, you can improve query performance.</span></span>  
  
 <span data-ttu-id="e54d2-105">Para definir un subcubo se puede utilizar la instrucción [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) , tal como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="e54d2-105">To define a subcube, you use the [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) statement, as described in this topic.</span></span>  
  
## <a name="create-subcube-syntax"></a><span data-ttu-id="e54d2-106">Sintaxis de CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="e54d2-106">CREATE SUBCUBE Syntax</span></span>  
 <span data-ttu-id="e54d2-107">Utilice la siguiente sintaxis para crear un subcubo:</span><span class="sxs-lookup"><span data-stu-id="e54d2-107">Use the following syntax to create a subcube:</span></span>  
  
```  
CREATE SUBCUBE Subcube_Identifier AS Subcube_Expression  
```  
  
 <span data-ttu-id="e54d2-108">La sintaxis de CREATE SUBCUBE es relativamente sencilla.</span><span class="sxs-lookup"><span data-stu-id="e54d2-108">The CREATE SUBCUBE syntax is fairly simple.</span></span> <span data-ttu-id="e54d2-109">El parámetro *Subcube_Identifier* identifica el cubo en el que se basará el subcubo.</span><span class="sxs-lookup"><span data-stu-id="e54d2-109">The *Subcube_Identifier* parameter identifies the cube on which the subcube will be based.</span></span> <span data-ttu-id="e54d2-110">El parámetro *Subcube_Expression* selecciona la parte del cubo que se convertirá en el subcubo.</span><span class="sxs-lookup"><span data-stu-id="e54d2-110">The *Subcube_Expression* parameter selects the part of the cube that will become the subcube</span></span>  
  
 <span data-ttu-id="e54d2-111">Una vez creado el subcubo, éste se convierte en el contexto de todas las consultas MDX hasta que termine la sesión o hasta que se ejecute la instrucción [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) .</span><span class="sxs-lookup"><span data-stu-id="e54d2-111">After you create a subcube, that subcube becomes the context for all MDX queries until either the session closes or you run the [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) statement.</span></span>  
  
### <a name="what-a-subcube-contains"></a><span data-ttu-id="e54d2-112">Contenido de un subcubo</span><span class="sxs-lookup"><span data-stu-id="e54d2-112">What a Subcube Contains</span></span>  
 <span data-ttu-id="e54d2-113">Aunque la instrucción CREATE SUBCUBE resulte fácil de usar, la instrucción en sí no muestra explícitamente todos los miembros que pasarán a formar parte de un subcubo.</span><span class="sxs-lookup"><span data-stu-id="e54d2-113">Although the CREATE SUBCUBE statement is fairly simple to use, the statement itself does not explicitly show all the members that become part of a subcube.</span></span> <span data-ttu-id="e54d2-114">La definición de los subcubos se rige por las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="e54d2-114">In defining a subcube, the following rules apply:</span></span>  
  
-   <span data-ttu-id="e54d2-115">Si se incluye el miembro `(All)` de una jerarquía, se deben incluir todos los miembros de la misma.</span><span class="sxs-lookup"><span data-stu-id="e54d2-115">If you include the `(All)` member of a hierarchy, you include every member of that hierarchy.</span></span>  
  
-   <span data-ttu-id="e54d2-116">Cuando se incluye un miembro se deben incluir todos sus antecesores y descendientes.</span><span class="sxs-lookup"><span data-stu-id="e54d2-116">If you include any member, you include that member's ascendants and descendants.</span></span>  
  
-   <span data-ttu-id="e54d2-117">Si se incluyen todos los miembros de un nivel, se deben incluir todos los miembros de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="e54d2-117">If you include every member from a level, you include all members from the hierarchy.</span></span> <span data-ttu-id="e54d2-118">Los miembros de otras jerarquías quedan excluidos cuando no existen con miembros del nivel (por ejemplo, una jerarquía desequilibrada como puede ser una ciudad que no incluya clientes).</span><span class="sxs-lookup"><span data-stu-id="e54d2-118">Members from other hierarchies will be excluded if those members do not exist with members from the level (for example, an unbalanced hierarchy such as a city that does not contain customers).</span></span>  
  
-   <span data-ttu-id="e54d2-119">Un subcubo siempre contiene todos los miembros `(All)` del cubo.</span><span class="sxs-lookup"><span data-stu-id="e54d2-119">A subcube will always contain every `(All)` member from the cube.</span></span>  
  
 <span data-ttu-id="e54d2-120">Otra característica es el cálculo visual del total de los valores agregados del subcubo.</span><span class="sxs-lookup"><span data-stu-id="e54d2-120">Additionally, aggregate values within the subcube are visually totaled.</span></span> <span data-ttu-id="e54d2-121">Por ejemplo, imaginemos un subcubo que incluya `USA`, `WA`y `OR`.</span><span class="sxs-lookup"><span data-stu-id="e54d2-121">For example, a subcube contains `USA`, `WA`, and `OR`.</span></span> <span data-ttu-id="e54d2-122">El valor agregado de `USA` será la suma de `{WA,OR}` puesto que `WA` y `OR` son los únicos estados definidos por el subcubo.</span><span class="sxs-lookup"><span data-stu-id="e54d2-122">The aggregate value for `USA` will be the sum of `{WA,OR}` because `WA` and `OR` are the only states defined by the subcube.</span></span> <span data-ttu-id="e54d2-123">El resto de los estados se ignoran.</span><span class="sxs-lookup"><span data-stu-id="e54d2-123">All other states will be ignored.</span></span>  
  
 <span data-ttu-id="e54d2-124">Las referencias explícitas a las celdas externas al subcubo devuelven valores de celda cuya evaluación se efectúa en el contexto del cubo completo.</span><span class="sxs-lookup"><span data-stu-id="e54d2-124">Also, explicit references to cells outside the subcube return cell values that are evaluated in the context of the whole cube.</span></span> <span data-ttu-id="e54d2-125">Por ejemplo, imagine un subcubo limitado al año en curso.</span><span class="sxs-lookup"><span data-stu-id="e54d2-125">For example, you create a subcube that is limited to the current year.</span></span> <span data-ttu-id="e54d2-126">Utiliza la función [ParallelPeriod](/sql/mdx/parallelperiod-mdx) para comparar el año actual con el anterior.</span><span class="sxs-lookup"><span data-stu-id="e54d2-126">You then use the [ParallelPeriod](/sql/mdx/parallelperiod-mdx) function to compare the current year to the previous year.</span></span> <span data-ttu-id="e54d2-127">La diferencia en los valores se devolverá aunque el valor del año anterior se encuentre fuera del subcubo.</span><span class="sxs-lookup"><span data-stu-id="e54d2-127">The difference in values will be returned even though the previous year's value lies outside the subcube.</span></span>  
  
 <span data-ttu-id="e54d2-128">Por último, si no se sobrescribe el contexto original, las funciones de conjuntos evaluadas en una subselección se evalúan en el contexto de dicha subselección.</span><span class="sxs-lookup"><span data-stu-id="e54d2-128">Finally, if the original context is not overwritten, set functions evaluated in a subselect are evaluated in the context of the subselect.</span></span> <span data-ttu-id="e54d2-129">En caso de que se sobrescriba el contexto, las funciones de conjunto se evalúan en el contexto del cubo completo.</span><span class="sxs-lookup"><span data-stu-id="e54d2-129">If the context is overwritten, set functions are evaluated in the context of the whole cube.</span></span>  
  
## <a name="create-subcube-example"></a><span data-ttu-id="e54d2-130">Ejemplo de CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="e54d2-130">CREATE SUBCUBE Example</span></span>  
 <span data-ttu-id="e54d2-131">En el siguiente ejemplo se crea un subcubo que restringe el cubo Budget a las cuentas 4200 y 4300:</span><span class="sxs-lookup"><span data-stu-id="e54d2-131">The following example creates a subcube that restricts the Budget cube to only accounts 4200 and 4300:</span></span>  
  
 `CREATE SUBCUBE Budget AS SELECT {[Account].[Account].&[4200], [Account].[Account].&[4300] } ON 0 FROM Budget`  
  
 <span data-ttu-id="e54d2-132">Al haber creado un subcubo para la sesión, las consultas que se realicen a partir de ahora se efectuarán en el subcubo, no en el cubo completo.</span><span class="sxs-lookup"><span data-stu-id="e54d2-132">Having created a subcube for the session, any subsequent queries will be against the subcube, not the whole cube.</span></span> <span data-ttu-id="e54d2-133">Por ejemplo, ejecute la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="e54d2-133">For example, you run the following query.</span></span> <span data-ttu-id="e54d2-134">La consulta solo devolverá los miembros de las cuentas 4200 y 4300.</span><span class="sxs-lookup"><span data-stu-id="e54d2-134">This query will only return members from accounts 4200 and 4300.</span></span>  
  
 `SELECT [Account].[Account].Members ON 0, Measures.Members ON 1 FROM Budget`  
  
## <a name="see-also"></a><span data-ttu-id="e54d2-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e54d2-135">See Also</span></span>  
 <span data-ttu-id="e54d2-136">[Establecer el contexto de cubo en una consulta &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="e54d2-136">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 [<span data-ttu-id="e54d2-137">Aspectos básicos de las consultas MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e54d2-137">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
