---
title: Relaciones de atributo | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- member properties [Analysis Services], attribute relationships
- security [Analysis Services], properties
- PROPERTIES keyword
- storage [Analysis Services], attribute relationships
- natural hierarchies [Analysis Services]
- dimensions [Analysis Services], member properties
- queries [MDX], attribute relationships
- user-defined hierarchies [Analysis Services]
- attributes [Analysis Services], relationships
- member properties [Analysis Services]
- members [Analysis Services], attribute relationships
- storing data [Analysis Services], attribute relationships
- relationships [Analysis Services], attributes
ms.assetid: 2491422a-4cf5-4b23-b6ab-289222b22ce8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 122638a2728a8a85ee58661196797383da20eef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746571"
---
# <a name="attribute-relationships"></a><span data-ttu-id="45ca1-102">Relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="45ca1-102">Attribute Relationships</span></span>
  <span data-ttu-id="45ca1-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , los atributos de una dimensión siempre están relacionados directa o indirectamente con el atributo clave.</span><span class="sxs-lookup"><span data-stu-id="45ca1-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes within a dimension are always related either directly or indirectly to the key attribute.</span></span> <span data-ttu-id="45ca1-104">Al definir una dimensión basada en un esquema en estrella, donde todos los atributos de la dimensión se derivan de la misma tabla relacional, se define automáticamente una relación de atributo entre el atributo clave y cada atributo no clave de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="45ca1-104">When you define a dimension based on a star schema, which is where all dimension attributes are derived from the same relational table, an attribute relationship is automatically defined between the key attribute and each non-key attribute of the dimension.</span></span> <span data-ttu-id="45ca1-105">Al definir una dimensión basada en un esquema de copo de nieve, donde los atributos de la dimensión se derivan de varias tablas relacionadas, se define automáticamente una relación de atributo del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ca1-105">When you define a dimension based on a snowflake schema, which is where dimension attributes are derived from multiple related tables, an attribute relationship is automatically defined as follows:</span></span>  
  
-   <span data-ttu-id="45ca1-106">Entre el atributo clave y cada atributo sin clave enlazado a columnas de la tabla principal de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="45ca1-106">Between the key attribute and each non-key attribute bound to columns in the main dimension table.</span></span>  
  
-   <span data-ttu-id="45ca1-107">Entre el atributo clave y el atributo enlazado a la clave externa de la tabla secundaria que vincula las tablas de dimensiones subyacentes.</span><span class="sxs-lookup"><span data-stu-id="45ca1-107">Between the key attribute and the attribute bound to the foreign key in the secondary table that links the underlying dimension tables.</span></span>  
  
-   <span data-ttu-id="45ca1-108">Entre el atributo enlazado a la clave externa de la tabla secundaria y cada atributo no clave enlazado a las columnas de la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="45ca1-108">Between the attribute bound to foreign key in the secondary table and each non-key attribute bound to columns from the secondary table.</span></span>  
  
 <span data-ttu-id="45ca1-109">Sin embargo, hay una serie de razones por las que puede que desee cambiar estas relaciones de atributo predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="45ca1-109">However, there are a number of reasons why you might want to change these default attribute relationships.</span></span> <span data-ttu-id="45ca1-110">Por ejemplo quizás desee definir una jerarquía natural, un orden personalizado o una granularidad de dimensión basados en un atributo no clave.</span><span class="sxs-lookup"><span data-stu-id="45ca1-110">For example, you might want to define a natural hierarchy, a custom sort order, or dimension granularity based on a non-key attribute.</span></span> <span data-ttu-id="45ca1-111">Para obtener más información, vea [referencia de propiedades de atributo de dimensión](../multidimensional-models/dimension-attribute-properties-reference.md).</span><span class="sxs-lookup"><span data-stu-id="45ca1-111">For more information, see [Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45ca1-112">Las relaciones de atributo se conocen como propiedades de miembros en las Expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="45ca1-112">Attribute relationships are known in Multidimensional Expressions (MDX) as member properties.</span></span>  
  
## <a name="natural-hierarchy-relationships"></a><span data-ttu-id="45ca1-113">Relaciones de jerarquías naturales</span><span class="sxs-lookup"><span data-stu-id="45ca1-113">Natural Hierarchy Relationships</span></span>  
 <span data-ttu-id="45ca1-114">Una jerarquía es natural cuando cada atributo incluido en la jerarquía definida por el usuario tiene una relación de uno a varios con el atributo situado inmediatamente debajo.</span><span class="sxs-lookup"><span data-stu-id="45ca1-114">A hierarchy is a natural hierarchy when each attribute included in the user-defined hierarchy has a one to many relationship with the attribute immediately below it.</span></span> <span data-ttu-id="45ca1-115">Por ejemplo imagine una dimensión de cliente basada en una tabla de origen relacional con ocho columnas:</span><span class="sxs-lookup"><span data-stu-id="45ca1-115">For example, consider a Customer dimension based on a relational source table with eight columns:</span></span>  
  
-   <span data-ttu-id="45ca1-116">CustomerKey</span><span class="sxs-lookup"><span data-stu-id="45ca1-116">CustomerKey</span></span>  
  
-   <span data-ttu-id="45ca1-117">CustomerName</span><span class="sxs-lookup"><span data-stu-id="45ca1-117">CustomerName</span></span>  
  
-   <span data-ttu-id="45ca1-118">Age</span><span class="sxs-lookup"><span data-stu-id="45ca1-118">Age</span></span>  
  
-   <span data-ttu-id="45ca1-119">Sexo</span><span class="sxs-lookup"><span data-stu-id="45ca1-119">Gender</span></span>  
  
-   <span data-ttu-id="45ca1-120">Email</span><span class="sxs-lookup"><span data-stu-id="45ca1-120">Email</span></span>  
  
-   <span data-ttu-id="45ca1-121">City</span><span class="sxs-lookup"><span data-stu-id="45ca1-121">City</span></span>  
  
-   <span data-ttu-id="45ca1-122">Country</span><span class="sxs-lookup"><span data-stu-id="45ca1-122">Country</span></span>  
  
-   <span data-ttu-id="45ca1-123">Region</span><span class="sxs-lookup"><span data-stu-id="45ca1-123">Region</span></span>  
  
 <span data-ttu-id="45ca1-124">La dimensión correspondiente de Analysis Services tiene siete atributos:</span><span class="sxs-lookup"><span data-stu-id="45ca1-124">The corresponding Analysis Services dimension has seven attributes:</span></span>  
  
-   <span data-ttu-id="45ca1-125">Customer (basado en CustomerKey; CustomerName proporciona los nombres de miembro)</span><span class="sxs-lookup"><span data-stu-id="45ca1-125">Customer (based on CustomerKey, with CustomerName supplying member names)</span></span>  
  
-   <span data-ttu-id="45ca1-126">Age, Gender, Email, City, Region, Country</span><span class="sxs-lookup"><span data-stu-id="45ca1-126">Age, Gender, Email, City, Region, Country</span></span>  
  
 <span data-ttu-id="45ca1-127">Las relaciones que representan jerarquías naturales se aplican al crear una relación de atributo entre el atributo de un nivel y el atributo del nivel situado debajo.</span><span class="sxs-lookup"><span data-stu-id="45ca1-127">Relationships representing natural hierarchies are enforced by creating an attribute relationship between the attribute for a level and the attribute for the level below it.</span></span> <span data-ttu-id="45ca1-128">Para [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], esto especifica una relación natural y una agregación potencial.</span><span class="sxs-lookup"><span data-stu-id="45ca1-128">For [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], this specifies a natural relationship and potential aggregation.</span></span> <span data-ttu-id="45ca1-129">En la dimensión de cliente, existe una jerarquía natural para los atributos Country, Region, City y Customer.</span><span class="sxs-lookup"><span data-stu-id="45ca1-129">In the Customer dimension, a natural hierarchy exists for the Country, Region, City, and Customer attributes.</span></span> <span data-ttu-id="45ca1-130">La jerarquía natural de `{Country, Region, City, Customer}` se describe al agregar las siguientes relaciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="45ca1-130">The natural hierarchy for `{Country, Region, City, Customer}` is described by adding the following attribute relationships:</span></span>  
  
-   <span data-ttu-id="45ca1-131">El atributo Country como una relación de atributo con el atributo Region.</span><span class="sxs-lookup"><span data-stu-id="45ca1-131">The Country attribute as an attribute relationship to the Region attribute.</span></span>  
  
-   <span data-ttu-id="45ca1-132">El atributo Region como una relación de atributo con el atributo City.</span><span class="sxs-lookup"><span data-stu-id="45ca1-132">The Region attribute as an attribute relationship to the City attribute.</span></span>  
  
-   <span data-ttu-id="45ca1-133">El atributo City como una relación de atributo con el atributo Customer.</span><span class="sxs-lookup"><span data-stu-id="45ca1-133">The City attribute as an attribute relationship to the Customer attribute.</span></span>  
  
 <span data-ttu-id="45ca1-134">Para navegar por los datos del cubo, también puede crear una jerarquía definida por el usuario que no represente una jerarquía natural en los datos (que se denomina una jerarquía *ad hoc* o de *informes* ).</span><span class="sxs-lookup"><span data-stu-id="45ca1-134">For navigating data in the cube, you can also create a user-defined hierarchy that does not represent a natural hierarchy in the data (which is called an *ad hoc* or *reporting* hierarchy).</span></span> <span data-ttu-id="45ca1-135">Por ejemplo, podría crear una jerarquía definida por el usuario basada en `{Age, Gender}`.</span><span class="sxs-lookup"><span data-stu-id="45ca1-135">For example, you could create a user-defined hierarchy based on `{Age, Gender}`.</span></span> <span data-ttu-id="45ca1-136">Los usuarios no ven ninguna diferencia en la forma en que se comportan las dos jerarquías, aunque la jerarquía natural se beneficia de las estructuras de agregación e indización (ocultas para el usuario) para las relaciones naturales en los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="45ca1-136">Users do not see any difference in how the two hierarchies behave, although the natural hierarchy benefits from aggregating and indexing structures - hidden from the user - that account for the natural relationships in the source data.</span></span>  
  
 <span data-ttu-id="45ca1-137">La propiedad `SourceAttribute` de un nivel determina qué atributo se utiliza para describir el nivel.</span><span class="sxs-lookup"><span data-stu-id="45ca1-137">The `SourceAttribute` property of a level determines which attribute is used to describe the level.</span></span> <span data-ttu-id="45ca1-138">La propiedad `KeyColumns` del atributo especifica la columna de la vista del origen de datos que proporciona los miembros.</span><span class="sxs-lookup"><span data-stu-id="45ca1-138">The `KeyColumns` property on the attribute specifies the column in the data source view that supplies the members.</span></span> <span data-ttu-id="45ca1-139">La propiedad `NameColumn` del atributo puede especificar una columna de nombre diferente para los miembros.</span><span class="sxs-lookup"><span data-stu-id="45ca1-139">The `NameColumn` property on the attribute can specify a different name column for the members.</span></span>  
  
 <span data-ttu-id="45ca1-140">Para definir un nivel en una jerarquía definida por el usuario mediante [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , el **Diseñador de dimensiones** permite seleccionar un atributo de dimensión, una columna de una tabla de dimensiones o una columna de una tabla relacionada incluida en la vista del origen de datos para el cubo.</span><span class="sxs-lookup"><span data-stu-id="45ca1-140">To define a level in a user-defined hierarchy using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the **Dimension Designer** allows you to select a dimension attribute, a column in a dimension table, or a column from a related table included in the data source view for the cube.</span></span> <span data-ttu-id="45ca1-141">Para obtener más información sobre la creación de jerarquías definidas por el usuario, vea [Crear jerarquías definidas por el usuario](../multidimensional-models/user-defined-hierarchies-create.md).</span><span class="sxs-lookup"><span data-stu-id="45ca1-141">For more information about creating user-defined hierarchies, see [Create User-Defined Hierarchies](../multidimensional-models/user-defined-hierarchies-create.md).</span></span>  
  
 <span data-ttu-id="45ca1-142">En Analysis Services, se suele hacer una suposición acerca del contenido de los miembros.</span><span class="sxs-lookup"><span data-stu-id="45ca1-142">In Analysis Services, an assumption is usually made about the content of members.</span></span> <span data-ttu-id="45ca1-143">Los miembros hoja no tienen descendientes y contienen datos derivados de los orígenes de datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="45ca1-143">Leaf members have no descendents and contain data derived from underlying data sources.</span></span> <span data-ttu-id="45ca1-144">Los miembros no hoja tienen descendientes y contienen datos derivados de agregaciones realizadas en miembros secundarios.</span><span class="sxs-lookup"><span data-stu-id="45ca1-144">Nonleaf members have descendents and contain data derived from aggregations performed on child members.</span></span> <span data-ttu-id="45ca1-145">En los niveles agregados, los miembros se basan en agregaciones de niveles subordinados.</span><span class="sxs-lookup"><span data-stu-id="45ca1-145">In aggregated levels, members are based on aggregations of subordinate levels.</span></span> <span data-ttu-id="45ca1-146">Por lo tanto, cuando la propiedad `IsAggregatable` está establecida en `False` en un atributo de origen de un nivel, no se deben agregar atributos agregables como niveles por encima de él.</span><span class="sxs-lookup"><span data-stu-id="45ca1-146">Therefore, when the `IsAggregatable` property is set to `False` on a source attribute for a level, no aggregatable attributes should be added as levels above it.</span></span>  
  
## <a name="defining-an-attribute-relationship"></a><span data-ttu-id="45ca1-147">Definir una relación de atributo</span><span class="sxs-lookup"><span data-stu-id="45ca1-147">Defining an Attribute Relationship</span></span>  
 <span data-ttu-id="45ca1-148">La principal restricción al crear una relación de atributo consiste en asegurarse de que el atributo al que la relación de atributo hace referencia no tenga más de un valor para ningún miembro en el atributo al que pertenece la relación de atributo.</span><span class="sxs-lookup"><span data-stu-id="45ca1-148">The main constraint when you create an attribute relationship is to make sure that the attribute referred to by the attribute relationship has no more than one value for any member in the attribute to which the attribute relationship belongs.</span></span> <span data-ttu-id="45ca1-149">Por ejemplo, si se define una relación entre un atributo City y uno State, cada ciudad solo puede relacionarse con un único estado.</span><span class="sxs-lookup"><span data-stu-id="45ca1-149">For example, if you define a relationship between a City attribute and a State attribute, each city can only relate to a single state.</span></span>  
  
## <a name="attribute-relationship-queries"></a><span data-ttu-id="45ca1-150">Consultas de las relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="45ca1-150">Attribute Relationship Queries</span></span>  
 <span data-ttu-id="45ca1-151">Puede usar las consultas MDX para recuperar datos de las relaciones de atributo, en formato de propiedades de miembro, por medio de la palabra clave `PROPERTIES` de la instrucción `SELECT` de MDX.</span><span class="sxs-lookup"><span data-stu-id="45ca1-151">You can use MDX queries to retrieve data from attribute relationships, in the form of member properties, with the `PROPERTIES` keyword of the MDX `SELECT` statement.</span></span> <span data-ttu-id="45ca1-152">Para obtener más información sobre cómo usar MDX para recuperar propiedades de miembro, vea [usar las propiedades de miembro &#40;&#41;MDX ](../multidimensional-models/mdx/mdx-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="45ca1-152">For more information about how to use MDX to retrieve member properties, see [Using Member Properties &#40;MDX&#41;](../multidimensional-models/mdx/mdx-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ca1-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45ca1-153">See Also</span></span>  
 <span data-ttu-id="45ca1-154">[Atributos y jerarquías de atributos](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="45ca1-154">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="45ca1-155">[Referencia de propiedades de atributo de dimensión](../multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="45ca1-155">[Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="45ca1-156">[Jerarquías de usuario](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="45ca1-156">[User Hierarchies](user-hierarchies.md) </span></span>  
 [<span data-ttu-id="45ca1-157">Propiedades de jerarquía de usuario</span><span class="sxs-lookup"><span data-stu-id="45ca1-157">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
