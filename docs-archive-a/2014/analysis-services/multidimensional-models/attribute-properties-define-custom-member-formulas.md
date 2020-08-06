---
title: Definir fórmulas de miembro personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- members [Analysis Services], custom
- custom rollup formulas [Analysis Services]
- MDX [Analysis Services], custom rollup formulas
- custom member formulas [Analysis Services]
ms.assetid: 258304e2-d900-4013-97e3-871f51dfdce2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51649bea0c4134971b342b779c778b857343e62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750341"
---
# <a name="define-custom-member-formulas"></a><span data-ttu-id="837a0-102">Definir fórmulas de miembro personalizado</span><span class="sxs-lookup"><span data-stu-id="837a0-102">Define Custom Member Formulas</span></span>
  <span data-ttu-id="837a0-103">Puede definir una expresión MDX (Expresiones multidimensionales), denominada fórmula de miembro personalizado, para suministrar los valores de los miembros de determinado atributo.</span><span class="sxs-lookup"><span data-stu-id="837a0-103">You can define a Multidimensional Expressions (MDX) expression, called a custom member formula, to supply the values for the members of a specified attribute.</span></span> <span data-ttu-id="837a0-104">Una columna de una tabla de una vista del origen de datos proporciona, para cada miembro de un atributo, la expresión utilizada para suministrar el valor para dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="837a0-104">A column in a table from a data source view provides, for each member in an attribute, the expression used to supply the value for that member.</span></span>  
  
 <span data-ttu-id="837a0-105">Las fórmulas de miembro personalizado determinan los valores de las celdas que se asocian a los miembros y reemplazan las funciones de agregado de medidas.</span><span class="sxs-lookup"><span data-stu-id="837a0-105">Custom member formulas determine the cell values that are associated with members and override the aggregate functions of measures.</span></span> <span data-ttu-id="837a0-106">Las fórmulas de miembro personalizado se escriben en MDX.</span><span class="sxs-lookup"><span data-stu-id="837a0-106">Custom member formulas are written in MDX.</span></span> <span data-ttu-id="837a0-107">Cada fórmula de miembro personalizado se aplica a un solo miembro.</span><span class="sxs-lookup"><span data-stu-id="837a0-107">Each custom member formula applies to a single member.</span></span> <span data-ttu-id="837a0-108">Las fórmulas de miembro personalizado se almacenan en la tabla de dimensión o en otra tabla que tenga una relación de clave externa con la tabla de dimensión.</span><span class="sxs-lookup"><span data-stu-id="837a0-108">Custom member formulas are stored in the dimension table or in another table that has a foreign key relationship with the dimension table.</span></span>  
  
 <span data-ttu-id="837a0-109">La propiedad `CustomRollupColumn` de un atributo especifica la columna que contiene las fórmulas de miembro personalizado para miembros del atributo.</span><span class="sxs-lookup"><span data-stu-id="837a0-109">The `CustomRollupColumn` property on an attribute specifies the column that contains custom member formulas for members of the attribute.</span></span> <span data-ttu-id="837a0-110">Si una fila de la columna está vacía, el valor de la celda para el miembro se devolverá con normalidad.</span><span class="sxs-lookup"><span data-stu-id="837a0-110">If a row in the column is empty, the cell value for the member is returned normally.</span></span> <span data-ttu-id="837a0-111">Si la fórmula de la columna no es válida, se producirá un error en tiempo de ejecución siempre que se recupere un valor de la celda que utilice el miembro.</span><span class="sxs-lookup"><span data-stu-id="837a0-111">If the formula in the column is not valid, a run-time error occurs whenever a cell value that uses the member is retrieved.</span></span>  
  
 <span data-ttu-id="837a0-112">Antes de especificar las fórmulas de miembro personalizado de un atributo, asegúrese de que la tabla de dimensiones que contiene el atributo, o una tabla directamente relacionada, tiene una columna de cadena para almacenar las fórmulas de miembro personalizado.</span><span class="sxs-lookup"><span data-stu-id="837a0-112">Before you can specify custom member formulas for an attribute, make sure that the dimension table that contains the attribute, or a directly related table, has a string column to store the custom member formulas.</span></span> <span data-ttu-id="837a0-113">En este caso, puede establecer la `CustomRollupColumn` propiedad en un atributo manualmente o utilizar la mejora de la fórmula de miembro personalizado del asistente de Business Intelligence para habilitar una fórmula de miembro personalizado en un atributo.</span><span class="sxs-lookup"><span data-stu-id="837a0-113">If this is the case, you can either set the `CustomRollupColumn` property on an attribute manually or use the Set Custom Member Formula enhancement of the Business Intelligence Wizard to enable a custom member formula on an attribute.</span></span> <span data-ttu-id="837a0-114">Para obtener más información sobre cómo usar esta mejora, vea [Configurar fórmulas de miembro personalizado para los atributos de una dimensión](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="837a0-114">For more information about how to use this enhancement, see [Set Custom Member Formulas for Attributes in a Dimension](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span></span>  
  
## <a name="evaluating-custom-member-formulas"></a><span data-ttu-id="837a0-115">Evaluar fórmulas de miembro personalizado</span><span class="sxs-lookup"><span data-stu-id="837a0-115">Evaluating Custom Member Formulas</span></span>  
 <span data-ttu-id="837a0-116">Las fórmulas de miembro personalizado son distintas de los miembros calculados.</span><span class="sxs-lookup"><span data-stu-id="837a0-116">Custom member formulas differ from calculated members.</span></span> <span data-ttu-id="837a0-117">Las fórmulas de miembro personalizado se aplican a los miembros que existen en las tablas de dimensión y solo proporcionan el valor del miembro.</span><span class="sxs-lookup"><span data-stu-id="837a0-117">Custom member formulas apply to members that exist in dimension tables, and only provide the value of the member.</span></span> <span data-ttu-id="837a0-118">En contraste, los miembros calculados no se almacenan en tablas de dimensiones y las expresiones de miembro calculado definen los datos y los metadatos para miembros adicionales incluidos en una jerarquía o dimensión.</span><span class="sxs-lookup"><span data-stu-id="837a0-118">In contrast, calculated members are not stored in dimension tables, and calculated member expressions define both data and metadata for additional members included in a dimension or hierarchy.</span></span>  
  
 <span data-ttu-id="837a0-119">Las fórmulas de miembro personalizado reemplazan las funciones de agregado asociadas a medidas.</span><span class="sxs-lookup"><span data-stu-id="837a0-119">Custom member formulas override the aggregate functions associated with measures.</span></span> <span data-ttu-id="837a0-120">Por ejemplo, antes de especificar una fórmula de miembro personalizado, una medida que utiliza la función de agregado `Sum` tiene los siguientes valores para los siguientes miembros de la dimensión Time:</span><span class="sxs-lookup"><span data-stu-id="837a0-120">For example, before a custom member formula is specified, a measure using the `Sum` aggregate function has the following values for the following members of the Time dimension:</span></span>  
  
-   <span data-ttu-id="837a0-121">2003: 2100</span><span class="sxs-lookup"><span data-stu-id="837a0-121">2003: 2100</span></span>  
  
    -   <span data-ttu-id="837a0-122">Quarter 1: 700</span><span class="sxs-lookup"><span data-stu-id="837a0-122">Quarter 1: 700</span></span>  
  
    -   <span data-ttu-id="837a0-123">Quarter 2: 500</span><span class="sxs-lookup"><span data-stu-id="837a0-123">Quarter 2: 500</span></span>  
  
    -   <span data-ttu-id="837a0-124">Quarter 3: 100</span><span class="sxs-lookup"><span data-stu-id="837a0-124">Quarter 3: 100</span></span>  
  
    -   <span data-ttu-id="837a0-125">Quarter 4: 800</span><span class="sxs-lookup"><span data-stu-id="837a0-125">Quarter 4: 800</span></span>  
  
-   <span data-ttu-id="837a0-126">2004: 1500</span><span class="sxs-lookup"><span data-stu-id="837a0-126">2004: 1500</span></span>  
  
    -   <span data-ttu-id="837a0-127">Quarter 1: 600</span><span class="sxs-lookup"><span data-stu-id="837a0-127">Quarter 1: 600</span></span>  
  
    -   <span data-ttu-id="837a0-128">Quarter 2: 200</span><span class="sxs-lookup"><span data-stu-id="837a0-128">Quarter 2: 200</span></span>  
  
    -   <span data-ttu-id="837a0-129">Quarter 3: 300</span><span class="sxs-lookup"><span data-stu-id="837a0-129">Quarter 3: 300</span></span>  
  
    -   <span data-ttu-id="837a0-130">Quarter 4: 400</span><span class="sxs-lookup"><span data-stu-id="837a0-130">Quarter 4: 400</span></span>  
  
 <span data-ttu-id="837a0-131">Con una fórmula de miembro personalizado, el valor del miembro es un su lugar suministrado por la fórmula de resumen personalizado.</span><span class="sxs-lookup"><span data-stu-id="837a0-131">With a custom member formula, the value of the member is instead supplied by the custom rollup formula.</span></span> <span data-ttu-id="837a0-132">Por ejemplo, la siguiente fórmula de miembro personalizado se puede utilizar para suministrar el valor del miembro secundario Quarter 4 del miembro 2004 en la dimensión Time como 450.</span><span class="sxs-lookup"><span data-stu-id="837a0-132">For example, the following custom member formula can be used to supply the value for the Quarter 4 child member of the 2004 member in the Time dimension as 450.</span></span>  
  
```  
Time.[Quarter 3] * 1.5  
```  
  
 <span data-ttu-id="837a0-133">Las fórmulas de miembro personalizado se almacenan en una columna de la tabla de dimensión.</span><span class="sxs-lookup"><span data-stu-id="837a0-133">Custom member formulas are stored in a column of the dimension table.</span></span> <span data-ttu-id="837a0-134">Puede habilitar fórmulas de resumen personalizado estableciendo la propiedad `CustomRollupColumn` en un atributo.</span><span class="sxs-lookup"><span data-stu-id="837a0-134">You enable custom rollup formulas by setting the `CustomRollupColumn` property on an attribute.</span></span>  
  
 <span data-ttu-id="837a0-135">Para aplicar una expresión MDX única a todos los miembros de un atributo, cree un cálculo con nombre en la tabla de dimensión que devuelva una expresión MDX como cadena literal.</span><span class="sxs-lookup"><span data-stu-id="837a0-135">To apply a single MDX expression to all members of an attribute, create a named calculation on the dimension table that returns an MDX expression as a literal string.</span></span> <span data-ttu-id="837a0-136">A continuación, especifique el cálculo con nombre con el valor de propiedad `CustomRollupColumn` en el atributo que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="837a0-136">Then, specify the named calculation with the `CustomRollupColumn` property setting on the attribute that you want to configure.</span></span> <span data-ttu-id="837a0-137">Un cálculo con nombres es una columna de una tabla de vista del origen de datos que devuelve valores de filas definidos por una expresión SQL.</span><span class="sxs-lookup"><span data-stu-id="837a0-137">A named calculation is a column in a data source view table that returns row values defined by a SQL expression.</span></span> <span data-ttu-id="837a0-138">Para obtener más información sobre cómo crear cálculos con nombre, vea [Definir cálculos con nombre en una vista del origen de datos &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="837a0-138">For more information about constructing named calculations, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="837a0-139">Para aplicar una expresión MDX a miembros de un nivel determinado, en lugar de a miembros de todos los niveles basados en un atributo concreto, puede definir la expresión como un script MDX en el nivel.</span><span class="sxs-lookup"><span data-stu-id="837a0-139">To apply an MDX expression to members of a particular level instead of to members of all levels based on a particular attribute, you can define the expression as an MDX script on the level.</span></span> <span data-ttu-id="837a0-140">Para más información, vea [Aspectos básicos de scripting MDX &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="837a0-140">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
 <span data-ttu-id="837a0-141">Si utiliza miembros calculados y fórmulas de resumen personalizado para los miembros de un atributo, debe tener en cuenta el orden de evaluación.</span><span class="sxs-lookup"><span data-stu-id="837a0-141">If you use both calculated members and custom rollup formulas for members of an attribute, you should be aware of the order of evaluation.</span></span> <span data-ttu-id="837a0-142">Los miembros calculados se resuelven antes que las fórmulas de resumen personalizado.</span><span class="sxs-lookup"><span data-stu-id="837a0-142">Calculated members are resolved before custom rollup formulas are resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="837a0-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="837a0-143">See Also</span></span>  
 <span data-ttu-id="837a0-144">[Atributos y jerarquías de atributos](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="837a0-144">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 [<span data-ttu-id="837a0-145">Configurar fórmulas de miembro personalizado para los atributos de una dimensión</span><span class="sxs-lookup"><span data-stu-id="837a0-145">Set Custom Member Formulas for Attributes in a Dimension</span></span>](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md)  
  
  
