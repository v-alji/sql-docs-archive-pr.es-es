---
title: Configurar propiedades de medidas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- additivity [Analysis Services]
- ID property
- ErrorConfiguration property
- AggregateFunction property
- DisplayFolder property
- IgnoreUnrelatedDimensions property
- FormatString property
- Description property
- semiadditive
- properties [Analysis Services], measure groups
- aggregate functions [Analysis Services]
- DataType property
- ProcessingMode property
- MeasureExpression property
- AggregationPrefix property
- Visible property
- properties [Analysis Services], measures
- StorageLocation property
- StorageMode property
- formats [Analysis Services], measures
- Source property
- aggregations [Analysis Services], measures
- measures [Analysis Services], properties
- nonadditive [Analysis Services]
- Name property
- measures [Analysis Services], display formats
- ProcessingPriority property
- measure groups [Analysis Services], properties
- Type property
- ProactiveCaching property
ms.assetid: e9031078-c4f5-4986-b0c9-4d064b622ab7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ca291a5181fdb3f7a88845431d61ffd7a1034eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748366"
---
# <a name="configure-measure-properties"></a><span data-ttu-id="1d5a7-102">Configurar propiedades de medidas</span><span class="sxs-lookup"><span data-stu-id="1d5a7-102">Configure Measure Properties</span></span>
  <span data-ttu-id="1d5a7-103">Las medidas tienen propiedades que permiten definir su funcionamiento, así como controlar cómo aparecen ante los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-103">Measures have properties that enable you to define how the measures function and to control how the measures appear to users.</span></span>  
  
 <span data-ttu-id="1d5a7-104">Puede establecer propiedades en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] al crear o editar un cubo o una medida.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-104">You can set properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] when creating or editing a cube or measure.</span></span> <span data-ttu-id="1d5a7-105">También puede establecerlas mediante programación, usando MDX o AMO.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-105">You can also set them programmatically, using MDX or AMO.</span></span> <span data-ttu-id="1d5a7-106">Vea [Crear medidas y grupos de medida en modelos multidimensionales](create-measures-and-measure-groups-in-multidimensional-models.md), [CREATE MEMBER &#40;instrucción MDX&#41;](/sql/mdx/mdx-data-definition-create-member) y [Programar objetos básicos OLAP en AMO](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-106">See [Create Measures and Measure Groups in Multidimensional Models](create-measures-and-measure-groups-in-multidimensional-models.md) or [CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) or [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects) for details.</span></span>  
  
## <a name="measure-properties"></a><span data-ttu-id="1d5a7-107">Propiedades de medidas</span><span class="sxs-lookup"><span data-stu-id="1d5a7-107">Measure Properties</span></span>  
 <span data-ttu-id="1d5a7-108">Las medidas heredan determinadas propiedades del grupo de medida del que son miembro, aunque estas propiedades se reemplazan en el nivel de medida.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-108">Measures inherit certain properties from the measure group of which they are a member, unless those properties are overridden at the measure level.</span></span> <span data-ttu-id="1d5a7-109">Las propiedades de medidas determinan cómo se agrega una medida, su tipo de datos, el nombre que se muestra al usuario, la carpeta para mostrar en la que aparecerá la medida, su cadena de formato, cualquier expresión de medida, la columna de origen subyacente y la visibilidad para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-109">Measure properties determine how a measure is aggregated, its data type, the name that is displayed to the user, the display folder in which the measure will appear, its format string, any measure expression, the underlying source column, and its visibility to users.</span></span>  
  
|<span data-ttu-id="1d5a7-110">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1d5a7-110">Property</span></span>|<span data-ttu-id="1d5a7-111">Definición</span><span class="sxs-lookup"><span data-stu-id="1d5a7-111">Definition</span></span>|  
|--------------|----------------|  
|`AggregateFunction`|<span data-ttu-id="1d5a7-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-112">Required.</span></span> <span data-ttu-id="1d5a7-113">Determina cómo se agregan las medidas.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-113">Determines how measures are aggregated.</span></span> <span data-ttu-id="1d5a7-114">`Sum` es la agregación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-114">`Sum` is the default aggregation.</span></span> <span data-ttu-id="1d5a7-115">Para más información, vea [Use Aggregate Functions](use-aggregate-functions.md) para obtener una descripción de cada función.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-115">For more information, see [Use Aggregate Functions](use-aggregate-functions.md) for a description of each function.</span></span>|  
|`DataType`|<span data-ttu-id="1d5a7-116">Necesario.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-116">Required.</span></span> <span data-ttu-id="1d5a7-117">Especifica el tipo de datos de la columna de la tabla de hechos subyacente a la que se enlaza la medida.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-117">Specifies the data type of the column in the underlying fact table to which the measure is bound.</span></span> <span data-ttu-id="1d5a7-118">Este valor se hereda de la columna de origen de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-118">This value is inherited from the source column by default.</span></span>|  
|`Description`|<span data-ttu-id="1d5a7-119">Ofrece una descripción de la medida, que se puede mostrar en aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-119">Provides a description of the measure, which may be exposed in client applications.</span></span>|  
|`DisplayFolder`|<span data-ttu-id="1d5a7-120">Especifica la carpeta en la que se mostrará la medida a los usuarios cuando se conecten al cubo.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-120">Specifies the folder in which the measure will appear when users connect to the cube.</span></span> <span data-ttu-id="1d5a7-121">Cuando un cubo tiene muchas medidas, se pueden utilizar carpetas para mostrar para categorizar las medidas y mejorar la exploración para el usuario.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-121">When a cube has many measures, you can use display folders to categorize the measures and improve the user browsing experience.</span></span>|  
|`FormatString`|<span data-ttu-id="1d5a7-122">Puede seleccionar el formato que se utiliza para mostrar los valores de las medidas a los usuarios mediante la propiedad `FormatString` de la medida.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-122">You can select the format that is used to display measure values to users by using the `FormatString` property of the measure.</span></span><br /><br /> <span data-ttu-id="1d5a7-123">Aunque se proporciona una lista de los formatos de visualización en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], se pueden especificar muchos otros formatos que no están en la lista.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-123">Although a list of display formats is provided in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can specify many additional formats that are not in the list.</span></span> <span data-ttu-id="1d5a7-124">Puede especificar cualquier formato con nombre o definido por el usuario que sea válido en Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-124">You can specify any named or user-defined format that is valid in Microsoft Visual Basic.</span></span>|  
|`ID`|<span data-ttu-id="1d5a7-125">Necesario.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-125">Required.</span></span> <span data-ttu-id="1d5a7-126">Muestra el identificador único (Id.) de la medida.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-126">Displays the unique identifier (ID) of the measure.</span></span> <span data-ttu-id="1d5a7-127">Esta propiedad es de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-127">This property is read-only.</span></span>|  
|`MeasureExpression`|<span data-ttu-id="1d5a7-128">Especifica una expresión MDX restringida que define el valor de la medida.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-128">Specifies a constrained MDX expression defining the value of the measure.</span></span> <span data-ttu-id="1d5a7-129">La expresión se evalúa en el nivel de hoja antes de agregarse, y permite la ponderación de un valor.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-129">The expression is evaluated at the leaf level before being aggregated, and allows for weighting of a value.</span></span> <span data-ttu-id="1d5a7-130">Por ejemplo, en la conversión de moneda en que la tasa de cambio pondera un importe de ventas.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-130">For example, in currency conversion where a sales amount is weighted by the exchange rate.</span></span>|  
|`Name`|<span data-ttu-id="1d5a7-131">Necesario.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-131">Required.</span></span> <span data-ttu-id="1d5a7-132">Especifica el nombre de la medida.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-132">Specifies the name of the measure.</span></span>|  
|`Source`|<span data-ttu-id="1d5a7-133">Necesario.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-133">Required.</span></span> <span data-ttu-id="1d5a7-134">Especifica la columna de la vista del origen de datos a la que se enlaza la medida.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-134">Specifies the column in the data source view to which the measure is bound.</span></span> <span data-ttu-id="1d5a7-135">Vea [Orígenes de datos y enlaces &#40;SSAS multidimensional&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="1d5a7-135">See [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span></span>|  
|`Visible`|<span data-ttu-id="1d5a7-136">Determina la visibilidad de la medida en las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-136">Determines the visibility of the measure in client applications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d5a7-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d5a7-137">See Also</span></span>  
 <span data-ttu-id="1d5a7-138">[Configurar propiedades de grupo de medida](configure-measure-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1d5a7-138">[Configure Measure Group Properties](configure-measure-group-properties.md) </span></span>  
 [<span data-ttu-id="1d5a7-139">Modificar medidas</span><span class="sxs-lookup"><span data-stu-id="1d5a7-139">Modifying Measures</span></span>](../lesson-3-1-modifying-measures.md)  
  
  
