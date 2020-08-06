---
title: Miembros de atributos de grupo (discretización) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- NameColumn property
- discretization [Analysis Services]
- member groups [Analysis Services]
- grouping members
- DiscretizationNumber property
- sort orders [Analysis Services]
- DiscretizationMethod property
- adding members to member group
- number of member groups
- members [Analysis Services], groups
- names [Analysis Services], member groups
ms.assetid: 5cf2f407-accc-4baf-b54f-7703af338325
author: minewiskan
ms.author: owend
ms.openlocfilehash: bce2a72787d0b49c3f1fc60afe7b2177dcfdb351
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750337"
---
# <a name="group-attribute-members-discretization"></a><span data-ttu-id="5fbcb-102">Agrupar miembros de atributos (discretización)</span><span class="sxs-lookup"><span data-stu-id="5fbcb-102">Group Attribute Members (Discretization)</span></span>
  <span data-ttu-id="5fbcb-103">Un grupo de miembros es una colección de miembros de dimensión consecutivos generada por el sistema.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-103">A member group is a system-generated collection of consecutive dimension members.</span></span> <span data-ttu-id="5fbcb-104">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , los miembros de un atributo pueden agruparse en varios grupos de miembros a través de un proceso denominado discretización.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-104">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], members of an attribute can be grouped into a number of member groups through a process called discretization.</span></span> <span data-ttu-id="5fbcb-105">Un nivel de una jerarquía contiene miembros o grupos de miembro, pero no los dos.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-105">A level in a hierarchy contains either member groups or members, but not both.</span></span> <span data-ttu-id="5fbcb-106">Cuando los usuarios corporativos examinan un nivel que contiene grupos de miembros, ven los nombres y valores de celdas de estos grupos.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-106">When business users browse a level that contains member groups, they see the names and cell values of the member groups.</span></span> <span data-ttu-id="5fbcb-107">Los miembros que genera [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para admitir grupos de miembros se denominan miembros de agrupación y son similares a los miembros normales.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-107">The members generated by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to support member groups are called grouping members, and look like ordinary members.</span></span>  
  
 <span data-ttu-id="5fbcb-108">La propiedad `DiscretizationMethod` de un atributo controla cómo se agrupan los miembros.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-108">The `DiscretizationMethod` property on an attribute controls how the members are grouped.</span></span>  
  
|<span data-ttu-id="5fbcb-109">Configuración de `DiscretizationMethod`</span><span class="sxs-lookup"><span data-stu-id="5fbcb-109">`DiscretizationMethod` Setting</span></span>|<span data-ttu-id="5fbcb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fbcb-110">Description</span></span>|  
|--------------------------------------|-----------------|  
|`None`|<span data-ttu-id="5fbcb-111">Muestra los miembros.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-111">Displays the members.</span></span>|  
|`Automatic`|<span data-ttu-id="5fbcb-112">Selecciona el método que mejor representa los datos: `EqualAreas` o `Clusters`.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-112">Selects the method that best represents the data: either the `EqualAreas` method or the `Clusters` method.</span></span>|  
|`EqualAreas`|<span data-ttu-id="5fbcb-113">Intenta dividir los miembros del atributo en grupos que contengan el mismo número de miembros.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-113">Tries to divide the members in the attribute into groups that contain an equal number of members.</span></span>|  
|`Clusters`|<span data-ttu-id="5fbcb-114">Intenta dividir los miembros del atributo en grupos mediante el muestreo de los datos de entrenamiento, la inicialización en un número de puntos aleatorios y la ejecución de varias iteraciones del algoritmo de clústeres Expectation-Maximization (EM).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-114">Tries to divide the members in the attribute into groups by sampling the training data, initializing to a number of random points, and running several iterations of the Expectation-Maximization (EM) clustering algorithm.</span></span><br /><br /> <span data-ttu-id="5fbcb-115">Este método resulta útil porque funciona en cualquier curva de distribución, pero requiere más tiempo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-115">This method is useful because it works on any distribution curve, but is more expensive in terms of processing time.</span></span>|  
  
 <span data-ttu-id="5fbcb-116">La propiedad `DiscretizationNumber` de los atributos especifica el número de grupos que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-116">The `DiscretizationNumber` property on attributes specifies the number of groups to display.</span></span> <span data-ttu-id="5fbcb-117">Si esta propiedad se establece con el valor predeterminado, 0, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] determina el número de grupos mediante el muestreo o la lectura de los datos (según la configuración de `DiscretizationMethod`).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-117">If the property is set to the default value of 0, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] determines the number of groups by either sampling or reading the data, depending on the setting of the `DiscretizationMethod` property.</span></span>  
  
 <span data-ttu-id="5fbcb-118">El criterio de ordenación de los miembros del grupo de miembros se controla mediante la propiedad `OrderBy` del atributo.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-118">The sort order of members in the member groups is controlled by using the `OrderBy` property of the attribute.</span></span> <span data-ttu-id="5fbcb-119">Según este criterio de ordenación, los miembros de un grupo de miembros se ordenan consecutivamente.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-119">Based on this sort order, the members in a member group are ordered consecutively.</span></span>  
  
 <span data-ttu-id="5fbcb-120">El uso normal de los grupos de miembros consiste en obtener detalles de un nivel con pocos miembros en otro con muchos miembros.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-120">A common use for member groups is to drill down from a level with few members to a level with many members.</span></span> <span data-ttu-id="5fbcb-121">Para permitir al usuario obtener detalles de un nivel en otro, cambie la propiedad `DiscretizationMethod` del atributo en el nivel que contiene muchos miembros de `None` a uno de los métodos de discretización que se describen en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-121">To enable users to drill down between levels, change the `DiscretizationMethod` property on the attribute for the level that contains numerous members from `None` to one of the discretization methods described in the previous table.</span></span> <span data-ttu-id="5fbcb-122">Por ejemplo, una dimensión Client contiene una jerarquía de atributo Client Name con 500.000 miembros.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-122">For example, a Client dimension contains a Client Name attribute hierarchy with 500,000 members.</span></span> <span data-ttu-id="5fbcb-123">Puede cambiar el atributo Client Groups y establecer la propiedad `DiscretizationMethod` en `Automatic` para mostrar los grupos de miembro en el nivel de miembro de la jerarquía de atributos.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-123">You can rename this attribute Client Groups and set the `DiscretizationMethod` property to `Automatic` to display member groups on the attribute hierarchy member level.</span></span>  
  
 <span data-ttu-id="5fbcb-124">Para obtener detalles de clientes concretos de cada grupo, puede crear otra jerarquía de atributos Client Name enlazada a la misma columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-124">To drill down to individual clients in each group, you can create another Client Name attribute hierarchy bound to the same table column.</span></span> <span data-ttu-id="5fbcb-125">A continuación, cree una nueva jerarquía de usuario basada en los dos atributos.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-125">Then, create a new user hierarchy based on the two attributes.</span></span> <span data-ttu-id="5fbcb-126">El nivel superior se basa en el atributo Client Groups y el nivel inferior se basa en el atributo Client Name.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-126">The top level would be based on the Client Groups attribute and the lower level would be based on the Client Name attribute.</span></span> <span data-ttu-id="5fbcb-127">El valor de la propiedad `IsAggregatable` es `True` en ambos atributos.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-127">The `IsAggregatable` property would be `True` on both attributes.</span></span> <span data-ttu-id="5fbcb-128">El usuario puede expandir el nivel (All) de la jerarquía para ver los miembros del grupo y expandirlos para ver los miembros hoja de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-128">The user could then expand the (All) level on the hierarchy to view the group members, and expand the group members to view the leaf members of the hierarchy.</span></span> <span data-ttu-id="5fbcb-129">Para ocultar un nivel de grupo o cliente, puede establecer la propiedad `AttributeHierarchyVisible` en `False` en el atributo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-129">To hide either group or client level, you could set the `AttributeHierarchyVisible` property to `False` on the corresponding attribute.</span></span>  
  
## <a name="naming-template"></a><span data-ttu-id="5fbcb-130">Plantilla de asignación de nombres</span><span class="sxs-lookup"><span data-stu-id="5fbcb-130">Naming Template</span></span>  
 <span data-ttu-id="5fbcb-131">Los nombres de los grupos de miembro se generan automáticamente al crear grupos de miembro.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-131">Member group names are generated automatically when the member groups are created.</span></span> <span data-ttu-id="5fbcb-132">A menos que especifique una plantilla de asignación de nombres, se utilizará la plantilla de asignación de nombres predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-132">Unless you specify a naming template, the default naming template is used.</span></span> <span data-ttu-id="5fbcb-133">Para cambiar el método de asignación de nombres, especifique una plantilla de asignación de nombres en la opción `Format` para la propiedad `NameColumn` de un atributo.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-133">You can change this method of naming by specifying a naming template in the `Format` option for the `NameColumn` property of an attribute.</span></span> <span data-ttu-id="5fbcb-134">Pueden volver a definirse distintas plantillas de asignación de nombres para cada idioma especificado en la colección `Translations` del enlace de columna que se utiliza para la propiedad `NameColumn` del atributo.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-134">Different naming templates can be redefined for every language specified in the `Translations` collection of the column binding that was used for the `NameColumn` property of the attribute.</span></span>  
  
 <span data-ttu-id="5fbcb-135">La configuración `Format` utiliza la siguiente expresión de cadenas para definir la plantilla de asignación de nombres:</span><span class="sxs-lookup"><span data-stu-id="5fbcb-135">The `Format` setting uses the following string expression to define the naming template:</span></span>  
  
 `<Naming template> ::= <First definition> [;<Intermediate definition>;<Last definition>]`  
  
 `<First definition> ::= <Name expression>`  
  
 `<Intermediate definition> ::= <Name expression>`  
  
 `<Last definition> ::= <Name expression>`  
  
 <span data-ttu-id="5fbcb-136">El parámetro `<First definition>` solamente se aplica en el primer o único grupo de miembro generado por el método de discretización.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-136">The `<First definition>` parameter applies only to the first or only member group generated by the discretization method.</span></span> <span data-ttu-id="5fbcb-137">Si no se proporcionan los parámetros opcionales `<Intermediate definition>` y `<Last definition>` , se utiliza el parámetro `<First definition>` para todos los grupos de medida generados para dicho atributo.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-137">If the optional parameters `<Intermediate definition>` and `<Last definition>` are not provided, the `<First definition>` parameter is used for all measure groups generated for that attribute.</span></span>  
  
 <span data-ttu-id="5fbcb-138">El parámetro `<Last definition>` solamente se aplica en el último grupo de miembro generado con el método de discretización.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-138">The `<Last definition>` parameter applies only to the last member group generated by the discretization method.</span></span>  
  
 <span data-ttu-id="5fbcb-139">El parámetro `<Intermediate bucket name>` se aplica a cada grupo de miembro distinto del primer o último grupo de miembro generado con el método de discretización.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-139">The `<Intermediate bucket name>` parameter applies to every member group other than the first or last member group generated by the discretization method.</span></span> <span data-ttu-id="5fbcb-140">Si se generan dos o menos grupos de miembro, se omite este parámetro.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-140">If two or fewer member groups are generated, this parameter is ignored.</span></span>  
  
 <span data-ttu-id="5fbcb-141">El parámetro `<Bucket name>` es una expresión de cadenas que puede incorporar un conjunto de variables para representar la información del miembro o grupo de miembro como parte del nombre del grupo de miembro:</span><span class="sxs-lookup"><span data-stu-id="5fbcb-141">The `<Bucket name>` parameter is a string expression that can incorporate a set of variables to represent member or member group information as part of the name of the member group:</span></span>  
  
|<span data-ttu-id="5fbcb-142">Variable</span><span class="sxs-lookup"><span data-stu-id="5fbcb-142">Variable</span></span>|<span data-ttu-id="5fbcb-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fbcb-143">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="5fbcb-144">%{First bucket member}</span><span class="sxs-lookup"><span data-stu-id="5fbcb-144">%{First bucket member}</span></span>|<span data-ttu-id="5fbcb-145">Nombre del primer miembro que se incluirá en el grupo de miembro actual.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-145">The member name of the first member to be included in the current member group.</span></span>|  
|<span data-ttu-id="5fbcb-146">%{Last bucket member}</span><span class="sxs-lookup"><span data-stu-id="5fbcb-146">%{Last bucket member}</span></span>|<span data-ttu-id="5fbcb-147">Nombre del último miembro que se incluirá en el grupo de miembro actual.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-147">The member name of the last member to be included in the current member group.</span></span>|  
|<span data-ttu-id="5fbcb-148">%{Previous bucket last member}</span><span class="sxs-lookup"><span data-stu-id="5fbcb-148">%{Previous bucket last member}</span></span>|<span data-ttu-id="5fbcb-149">Nombre del último miembro que se asignará al grupo de miembro anterior.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-149">The member name of the last member assigned to the previous member group.</span></span>|  
|<span data-ttu-id="5fbcb-150">%{Next bucket first member}</span><span class="sxs-lookup"><span data-stu-id="5fbcb-150">%{Next bucket first member}</span></span>|<span data-ttu-id="5fbcb-151">Nombre del primer miembro que se asignará al siguiente grupo de miembro.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-151">The member name of the first member to be assigned to the next member group.</span></span>|  
|<span data-ttu-id="5fbcb-152">%{Bucket Min}</span><span class="sxs-lookup"><span data-stu-id="5fbcb-152">%{Bucket Min}</span></span>|<span data-ttu-id="5fbcb-153">Valor mínimo de los miembros que se asignará al grupo de miembro actual.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-153">The minimum value of the members to be assigned to the current member group.</span></span>|  
|<span data-ttu-id="5fbcb-154">%{Bucket Max}</span><span class="sxs-lookup"><span data-stu-id="5fbcb-154">%{Bucket Max}</span></span>|<span data-ttu-id="5fbcb-155">Valor máximo de los miembros que se asignará al grupo de miembro actual.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-155">The maximum value of the members to be assigned to the current member group.</span></span>|  
|<span data-ttu-id="5fbcb-156">%{Previous Bucket Max}</span><span class="sxs-lookup"><span data-stu-id="5fbcb-156">%{Previous Bucket Max}</span></span>|<span data-ttu-id="5fbcb-157">Valor máximo de los miembros que se asignará al grupo de miembro anterior.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-157">The maximum value of the members to be assigned to the previous member group.</span></span>|  
|<span data-ttu-id="5fbcb-158">%{Next Bucket Min}</span><span class="sxs-lookup"><span data-stu-id="5fbcb-158">%{Next Bucket Min}</span></span>|<span data-ttu-id="5fbcb-159">Valor mínimo de los miembros que se asignará al siguiente grupo de miembro.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-159">The minimum value of the members to be assigned to the next member group.</span></span>|  
  
 <span data-ttu-id="5fbcb-160">La plantilla de asignación de nombres predeterminada es `"%{First bucket member} - %{Last bucket member}"`y ofrece compatibilidad con versiones anteriores de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fbcb-160">The default naming template is `"%{First bucket member} - %{Last bucket member}"`, to provide compatibility with earlier versions of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5fbcb-161">Para incluir un punto y coma (;) como carácter literal en la plantilla de asignación de nombres, debe anteponer el carácter de símbolo de porcentaje (%).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-161">To include a semicolon (;) as a literal character in the naming template, prefix it with the percent (%) character.</span></span>  
  
### <a name="example"></a><span data-ttu-id="5fbcb-162">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5fbcb-162">Example</span></span>  
 <span data-ttu-id="5fbcb-163">La siguiente expresión de cadenas puede usarse para clasificar el atributo Yearly Income de la dimensión Customer de la base de datos de ejemplo [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , donde el atributo Yearly Income usa la agrupación de miembros:</span><span class="sxs-lookup"><span data-stu-id="5fbcb-163">The following string expression could be used to classify the Yearly Income attribute of the Customer dimension in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, where the Yearly Income attribute uses member grouping:</span></span>  
  
 <span data-ttu-id="5fbcb-164">"Less than %{Next Bucket Min};Between %{First bucket member} and %{Last bucket member};Greater than %{Previous Bucket Max}"</span><span class="sxs-lookup"><span data-stu-id="5fbcb-164">"Less than %{Next Bucket Min};Between %{First bucket member} and %{Last bucket member};Greater than %{Previous Bucket Max}"</span></span>  
  
## <a name="adding-new-members-to-existing-member-groups"></a><span data-ttu-id="5fbcb-165">Agregar nuevos miembros a grupos de miembro existentes</span><span class="sxs-lookup"><span data-stu-id="5fbcb-165">Adding New Members to Existing Member Groups</span></span>  
 <span data-ttu-id="5fbcb-166">Si se agregan nuevos miembros a la dimensión, se asignan a los grupos de miembro adecuados mediante la comparación del valor del miembro con el diseño del grupo de miembro actual.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-166">If new members are added to the dimension, they are assigned to the appropriate member groups by comparing the value of the member against the current member group layout.</span></span>  
  
 <span data-ttu-id="5fbcb-167">Si se inserta un miembro entre el último miembro del grupo de miembro anterior y el primer miembro del siguiente grupo de miembro, el nuevo miembro se convertirá en el último miembro del anterior grupo de miembro.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-167">If a member is inserted between the last member of the previous member group and the first member of the next member group, the new member becomes the last member of the previous member group.</span></span>  
  
## <a name="updating-a-dimension-with-discretized-attributes"></a><span data-ttu-id="5fbcb-168">Actualizar una dimensión con atributos de datos discretos</span><span class="sxs-lookup"><span data-stu-id="5fbcb-168">Updating a Dimension with Discretized Attributes</span></span>  
 <span data-ttu-id="5fbcb-169">Al procesar una dimensión, un atributo de datos discretos se rediscretiza solamente con una actualización completa (ProcessFull).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-169">When you process a dimension, a discretized attribute is rediscretized only with a full update (ProcessFull).</span></span> <span data-ttu-id="5fbcb-170">Para rediscretizar un atributo, debe realizar una actualización completa de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-170">To rediscretize an attribute, you must perform a full update of the dimension.</span></span> <span data-ttu-id="5fbcb-171">Si la tabla de dimensiones de un atributo de datos discretos se actualiza y si se procesa la dimensión con una actualización incremental (ProcessAdd), el atributo de datos discretos no se rediscretiza.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-171">If the dimension table of a discretized attribute is updated and you process the dimension with an incremental update (ProcessAdd), the discretized attribute is not rediscretized.</span></span> <span data-ttu-id="5fbcb-172">Los nombres y los elementos secundarios de los nuevos depósitos siguen siendo los mismos.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-172">The names and children of the new buckets remain the same.</span></span> <span data-ttu-id="5fbcb-173">Para más información sobre el procesamiento de dimensiones, vea [Procesar objetos de Analysis Services](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-173">For more information about processing dimensions, see [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
## <a name="usage-limitations"></a><span data-ttu-id="5fbcb-174">Limitaciones de uso</span><span class="sxs-lookup"><span data-stu-id="5fbcb-174">Usage Limitations</span></span>  
  
-   <span data-ttu-id="5fbcb-175">No pueden crearse grupos de miembros en el nivel más alto o más bajo de una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-175">You cannot create member groups in the topmost or bottommost level of a hierarchy.</span></span> <span data-ttu-id="5fbcb-176">No obstante, si es necesario, puede agregar un nivel para que el nivel en donde desea crear grupos de miembros deje de ser el más alto o el más bajo.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-176">However, if you need to do this, you can add a level in such a way that the level in which you want to create member groups is no longer the top or bottom level.</span></span> <span data-ttu-id="5fbcb-177">Puede ocultar el nivel agregado si establece su propiedad `Visible` en `False`.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-177">You can hide the added level by setting its `Visible` property to `False`.</span></span>  
  
-   <span data-ttu-id="5fbcb-178">No se pueden crear grupos de miembro en dos niveles consecutivos de una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-178">You cannot create member groups in two consecutive levels of a hierarchy.</span></span>  
  
-   <span data-ttu-id="5fbcb-179">No se admiten grupos de miembros en las dimensiones que utilizan el modo de almacenamiento ROLAP.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-179">Member groups are not supported for dimensions that use the ROLAP storage mode.</span></span>  
  
-   <span data-ttu-id="5fbcb-180">Si se actualiza la tabla de dimensión de una dimensión que contiene grupos de miembro y la dimensión se procesa después, se genera un nuevo grupo de miembro.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-180">If the dimension table of a dimension that contains member groups is updated, and the dimension is subsequently fully processed, a new set of member groups is generated.</span></span> <span data-ttu-id="5fbcb-181">Los nombres y elementos secundarios de los nuevos grupos de miembro pueden ser diferentes de los grupos de miembro anteriores.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-181">The names and children of the new member groups may be different from the old member groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fbcb-182">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5fbcb-182">See Also</span></span>  
 [<span data-ttu-id="5fbcb-183">Atributos y jerarquías de atributos</span><span class="sxs-lookup"><span data-stu-id="5fbcb-183">Attributes and Attribute Hierarchies</span></span>](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md)  
  
  