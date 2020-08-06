---
title: Convenciones XML de ASSL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- whitespace [Analysis Services Scripting Language]
- trailing whitespace
- XSD data types [Analysis Services Scripting Language]
- inheritance [Analysis Services Scripting Language]
- cardinality [Analysis Services Scripting Language]
- white space [Analysis Services Scripting Language]
- ASSL, XML conventions
- defaults [Analysis Services Scripting Language]
- leading whitespace
- Analysis Services Scripting Language, XML conventions
- XML [Analysis Services Scripting Language]
- hierarchies [Analysis Services Scripting Language]
- inherited defaults [Analysis Services Scripting Language]
ms.assetid: bce4edad-4420-41ce-9672-8c00c5c0dec6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b70742b07fd6450b01cf205147a05f40c4b6121
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748320"
---
# <a name="assl-xml-conventions"></a><span data-ttu-id="ab355-102">Convenciones XML de ASSL</span><span class="sxs-lookup"><span data-stu-id="ab355-102">ASSL XML Conventions</span></span>
  <span data-ttu-id="ab355-103">Analysis Services Scripting Language (ASSL) representa la jerarquía de objetos como un conjunto de tipos de elemento, cada uno de los cuales define los elementos secundarios que puede contener.</span><span class="sxs-lookup"><span data-stu-id="ab355-103">Analysis Services Scripting Language (ASSL) represents the hierarchy of objects as a set of element types, each of which defines the child elements they can contain.</span></span>  
  
 <span data-ttu-id="ab355-104">Para representar la jerarquía de objetos, ASSL utiliza las siguientes convenciones XML:</span><span class="sxs-lookup"><span data-stu-id="ab355-104">To represent the object hierarchy, ASSL uses the following XML conventions:</span></span>  
  
-   <span data-ttu-id="ab355-105">Todos los objetos y propiedades se representan como elementos, excepto los atributos XML estándar como ' XML: lang '.</span><span class="sxs-lookup"><span data-stu-id="ab355-105">All objects and properties are represented as elements, except for standard XML attributes such as 'xml:lang'.</span></span>  
  
-   <span data-ttu-id="ab355-106">Tanto los nombres de elemento como los valores de enumeración siguen la convención de nomenclatura de Microsoft .NET Framework del método Pascal de mayúsculas y minúsculas sin caracteres de subrayado.</span><span class="sxs-lookup"><span data-stu-id="ab355-106">Both element names and enumeration values follow the Microsoft .NET Framework naming convention of Pascal casing with no underscores.</span></span>  
  
-   <span data-ttu-id="ab355-107">Se conserva el uso de mayúsculas o minúsculas de todos los valores.</span><span class="sxs-lookup"><span data-stu-id="ab355-107">The case of all values is preserved.</span></span> <span data-ttu-id="ab355-108">Los valores de las enumeraciones también distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ab355-108">Values for enumerations are also case-sensitive.</span></span>  
  
 <span data-ttu-id="ab355-109">Además de esta lista de convenciones, Analysis Services sigue también ciertas convenciones con respecto a la cardinalidad, la herencia, el espacio en blanco, los tipos de datos y los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="ab355-109">In addition to this list of conventions, Analysis Services also follows certain conventions regarding cardinality, inheritance, whitespace, data types, and default values.</span></span>  
  
## <a name="cardinality"></a><span data-ttu-id="ab355-110">Cardinalidad</span><span class="sxs-lookup"><span data-stu-id="ab355-110">Cardinality</span></span>  
 <span data-ttu-id="ab355-111">Cuando la cardinalidad de un elemento es mayor que 1, existe una colección de elementos XML que encapsula este elemento.</span><span class="sxs-lookup"><span data-stu-id="ab355-111">When an element has a cardinality that is greater than 1, there is an XML element collection that encapsulates this element.</span></span> <span data-ttu-id="ab355-112">El nombre de colección utiliza la forma plural de los elementos incluidos en la colección.</span><span class="sxs-lookup"><span data-stu-id="ab355-112">The name of collection uses the plural form of the elements contained in the collection.</span></span> <span data-ttu-id="ab355-113">Por ejemplo, el fragmento XML siguiente representa la colección `Dimensions` dentro de un elemento `Database`:</span><span class="sxs-lookup"><span data-stu-id="ab355-113">For example, the following XML fragment represents the `Dimensions` collection within a `Database` element:</span></span>  
  
 `<Database>`  
  
 `...`  
  
 `<Dimensions>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `</Dimensions>`  
  
 `</Database>`  
  
 ``  
  
 <span data-ttu-id="ab355-114">El orden en que aparecen los elementos no es significativo.</span><span class="sxs-lookup"><span data-stu-id="ab355-114">The order in which elements appear is unimportant.</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="ab355-115">Herencia</span><span class="sxs-lookup"><span data-stu-id="ab355-115">Inheritance</span></span>  
 <span data-ttu-id="ab355-116">La herencia se utiliza cuando existen objetos distintos con conjuntos de propiedades que se superponen pero son notablemente diferentes.</span><span class="sxs-lookup"><span data-stu-id="ab355-116">Inheritance is used when there are distinct objects that have overlapping but significantly different sets of properties.</span></span> <span data-ttu-id="ab355-117">Entre los ejemplos de tales objetos superpuestos pero distintos se encuentran los cubos virtuales, los cubos vinculados y los cubos normales.</span><span class="sxs-lookup"><span data-stu-id="ab355-117">Examples of such overlapping but distinct objects are virtual cubes, linked cubes, and regular cubes.</span></span> <span data-ttu-id="ab355-118">Para los objetos superpuestos pero distintos, Analysis Services utiliza el atributo `type` estándar del espacio de nombres de la instancia XML a fin de indicar la herencia.</span><span class="sxs-lookup"><span data-stu-id="ab355-118">For overlapping but distinct object, Analysis Services uses the standard `type` attribute from the XML Instance Namespace to indicate the inheritance.</span></span> <span data-ttu-id="ab355-119">Por ejemplo, el fragmento XML siguiente muestra cómo el atributo `type` identifica si un elemento `Cube` hereda de un cubo normal o virtual:</span><span class="sxs-lookup"><span data-stu-id="ab355-119">For example, the following XML fragment shows how the `type` attribute identifies whether a `Cube` element inherits from a regular cube or from a virtual cube:</span></span>  
  
 `<Cubes>`  
  
 `<Cube xsi:type="RegularCube">`  
  
 `<Name>Sales</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `<Cube xsi:type="VirtualCube">`  
  
 `<Name>SalesAndInventory</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `</Cubes>`  
  
 ``  
  
 <span data-ttu-id="ab355-120">Generalmente, la herencia no se utiliza cuando varios tipos tienen una propiedad con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="ab355-120">Inheritance is generally not used when multiple types have a property of the same name.</span></span> <span data-ttu-id="ab355-121">Por ejemplo, las propiedades `Name` e `ID` aparecen en muchos elementos, pero dichas propiedades no se han ascendido a un tipo abstracto.</span><span class="sxs-lookup"><span data-stu-id="ab355-121">For example, the `Name` and `ID` properties appear on many elements, but these properties have not been promoted to an abstract type.</span></span>  
  
## <a name="whitespace"></a><span data-ttu-id="ab355-122">Espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="ab355-122">Whitespace</span></span>  
 <span data-ttu-id="ab355-123">El espacio en blanco dentro de un valor de elemento se conserva.</span><span class="sxs-lookup"><span data-stu-id="ab355-123">Whitespace within an element value is preserved.</span></span> <span data-ttu-id="ab355-124">Sin embargo, el espacio en blanco inicial y final siempre se recorta.</span><span class="sxs-lookup"><span data-stu-id="ab355-124">However, leading and trailing whitespace is always trimmed.</span></span> <span data-ttu-id="ab355-125">Por ejemplo, los elementos siguientes tienen el mismo texto pero cantidades distintas de espacio en blanco dentro de dicho texto, por lo tanto se tratan como si tuvieran valores distintos:</span><span class="sxs-lookup"><span data-stu-id="ab355-125">For example, the following elements have the same text but differing amounts of whitespace within that text, and are therefore treated as if they have different values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>My  text<Description>`  
  
 ``  
  
 <span data-ttu-id="ab355-126">Sin embargo, los elementos siguientes solo varían respecto al espacio en blanco inicial y final y, por lo tanto, se tratan como si sus valores fueran equivalentes:</span><span class="sxs-lookup"><span data-stu-id="ab355-126">However, the following elements vary only in leading and trailing whitespace, and are therefore treated as if they have equivalent values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>  My text  <Description>`  
  
 ``  
  
## <a name="data-types"></a><span data-ttu-id="ab355-127">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab355-127">Data Types</span></span>  
 <span data-ttu-id="ab355-128">Analysis Services utiliza los siguientes tipos de datos del lenguaje de definición de esquema XML (XSD) estándar:</span><span class="sxs-lookup"><span data-stu-id="ab355-128">Analysis Services uses the following standard XML Schema definition language (XSD) data types:</span></span>  
  
 `Int`  
 <span data-ttu-id="ab355-129">Un valor entero en el intervalo de-231 a 231-1.</span><span class="sxs-lookup"><span data-stu-id="ab355-129">An integer value in the range of -231 to 231 - 1.</span></span>  
  
 `Long`  
 <span data-ttu-id="ab355-130">Un valor entero comprendido entre-263 y 263-1.</span><span class="sxs-lookup"><span data-stu-id="ab355-130">An integer value in range of -263 to 263 - 1.</span></span>  
  
 `String`  
 <span data-ttu-id="ab355-131">Valor de cadena que se ajusta a las reglas globales siguientes:</span><span class="sxs-lookup"><span data-stu-id="ab355-131">A string value that conforms to the following global rules:</span></span>  
  
-   <span data-ttu-id="ab355-132">Se eliminan los caracteres de control.</span><span class="sxs-lookup"><span data-stu-id="ab355-132">Control characters are stripped out.</span></span>  
  
-   <span data-ttu-id="ab355-133">Se recorta el espacio en blanco inicial y final.</span><span class="sxs-lookup"><span data-stu-id="ab355-133">Leading and trailing white space is trimmed.</span></span>  
  
-   <span data-ttu-id="ab355-134">Se conserva el espacio en blanco interno.</span><span class="sxs-lookup"><span data-stu-id="ab355-134">Internal white space is preserved.</span></span>  
  
 <span data-ttu-id="ab355-135">Las propiedades `Name` e `ID` tienen limitaciones especiales respecto a los caracteres válidos en los elementos de cadena.</span><span class="sxs-lookup"><span data-stu-id="ab355-135">`Name` and `ID` properties have special limitations on valid characters in string elements.</span></span> <span data-ttu-id="ab355-136">Para obtener más información sobre las `Name` convenciones de y `ID` , consulte [objetos y características](assl-objects-and-object-characteristics.md)de objetos de ASSL.</span><span class="sxs-lookup"><span data-stu-id="ab355-136">For additional information about `Name` and `ID` conventions, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
 `DateTime`  
 <span data-ttu-id="ab355-137">`DateTime`Estructura del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ab355-137">A `DateTime` structure from the .NET Framework.</span></span> <span data-ttu-id="ab355-138">Un valor `DateTime` no puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="ab355-138">A `DateTime` value cannot be NULL.</span></span> <span data-ttu-id="ab355-139">La fecha más antigua que admite el tipo de datos `DataTime` es el 1 de enero de 1601, disponible para los programadores como `DateTime.MinValue`.</span><span class="sxs-lookup"><span data-stu-id="ab355-139">The lowest date supported by the `DataTime` data type is January 1, 1601, which is available to programmers as `DateTime.MinValue`.</span></span> <span data-ttu-id="ab355-140">La fecha más antigua admitida indica que falta un valor `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="ab355-140">The lowest supported date indicates that a `DateTime` value is missing.</span></span>  
  
 `Boolean`  
 <span data-ttu-id="ab355-141">Enumeración con solo dos valores, como {true, false} o {0, 1}.</span><span class="sxs-lookup"><span data-stu-id="ab355-141">An enumeration with only two values, such as {true, false} or {0, 1}.</span></span>  
  
## <a name="default-values"></a><span data-ttu-id="ab355-142">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="ab355-142">Default Values</span></span>  
 <span data-ttu-id="ab355-143">Analysis Services usa los valores predeterminados que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab355-143">Analysis Services uses the defaults listed in the following table.</span></span>  
  
|<span data-ttu-id="ab355-144">Tipo de datos de XML</span><span class="sxs-lookup"><span data-stu-id="ab355-144">XML data type</span></span>|<span data-ttu-id="ab355-145">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="ab355-145">Default value</span></span>|  
|-------------------|-------------------|  
|`Boolean`|<span data-ttu-id="ab355-146">False</span><span class="sxs-lookup"><span data-stu-id="ab355-146">False</span></span>|  
|`String`|<span data-ttu-id="ab355-147">"" (cadena vacía)</span><span class="sxs-lookup"><span data-stu-id="ab355-147">"" (empty string)</span></span>|  
|<span data-ttu-id="ab355-148">`Integer` o `Long`</span><span class="sxs-lookup"><span data-stu-id="ab355-148">`Integer` or `Long`</span></span>|<span data-ttu-id="ab355-149">0 (cero)</span><span class="sxs-lookup"><span data-stu-id="ab355-149">0 (zero)</span></span>|  
|`Timestamp`|<span data-ttu-id="ab355-150">12:00:00 AM, 1/1/0001 (correspondiente a .NET Framework `System.DateTime` con 0 TICs)</span><span class="sxs-lookup"><span data-stu-id="ab355-150">12:00:00 AM, 1/1/0001 (corresponding to a the .NET Frameworks `System.DateTime` with 0 ticks)</span></span>|  
  
 <span data-ttu-id="ab355-151">Para un elemento que está presente pero vacío se interpreta que tiene un valor de cadena nula, no el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ab355-151">An element that is present but empty is interpreted as having a value of a null string, not the default value.</span></span>  
  
### <a name="inherited-defaults"></a><span data-ttu-id="ab355-152">Valores predeterminados heredados</span><span class="sxs-lookup"><span data-stu-id="ab355-152">Inherited Defaults</span></span>  
 <span data-ttu-id="ab355-153">Algunas propiedades especificadas en un objeto proporcionan valores predeterminados para la misma propiedad en los objetos secundarios o descendientes.</span><span class="sxs-lookup"><span data-stu-id="ab355-153">Some properties that are specified on an object provide default values for the same property on child or descendant objects.</span></span> <span data-ttu-id="ab355-154">Por ejemplo, `Cube.StorageMode` proporciona el valor predeterminado de `Partition.StorageMode`.</span><span class="sxs-lookup"><span data-stu-id="ab355-154">For example, `Cube.StorageMode` provides the default value for `Partition.StorageMode`.</span></span> <span data-ttu-id="ab355-155">Las reglas que Analysis Services aplica para los valores predeterminados heredados son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="ab355-155">The rules that Analysis Services applies for inherited default values are as follows:</span></span>  
  
-   <span data-ttu-id="ab355-156">Cuando la propiedad del objeto secundario tiene el valor NULL en XML, su valor predeterminado es el valor heredado.</span><span class="sxs-lookup"><span data-stu-id="ab355-156">When the property for the child object is null in the XML, its value defaults to the inherited value.</span></span> <span data-ttu-id="ab355-157">Sin embargo, si consulta el valor en el servidor, éste devuelve el valor NULL del elemento XML.</span><span class="sxs-lookup"><span data-stu-id="ab355-157">However, if you query the value from the server, the server returns the null value of the XML element.</span></span>  
  
-   <span data-ttu-id="ab355-158">No es posible determinar mediante programación si la propiedad de un objeto secundario se ha establecido directamente en el objeto secundario o se ha heredado.</span><span class="sxs-lookup"><span data-stu-id="ab355-158">It is not possible to determine programmatically whether the property of a child object has been set directly on the child object or inherited.</span></span>  
  
 <span data-ttu-id="ab355-159">Algunos elementos tienen valores predeterminados definidos que se aplican cuando falta el elemento.</span><span class="sxs-lookup"><span data-stu-id="ab355-159">Some elements have defined defaults that apply when the element is missing.</span></span> <span data-ttu-id="ab355-160">Por ejemplo, los elementos `Dimension` del fragmento XML siguiente son equivalentes aunque un elemento `Dimension` contiene un elemento `Visible`, pero no así el otro elemento `Dimension`.</span><span class="sxs-lookup"><span data-stu-id="ab355-160">For example, the `Dimension` elements in the following XML fragment are equivalent even though one `Dimension` element contains a `Visible` element, but the other `Dimension` element does not.</span></span>  
  
 `<Dimension>`  
  
 `<Name>Product</Name>`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `<Name>Product</ Name>`  
  
 `<Visible>true</Visible>`  
  
 `</Dimension>`  
  
 <span data-ttu-id="ab355-161">Para obtener más información sobre los valores predeterminados heredados, vea [objetos y características](assl-objects-and-object-characteristics.md)de objetos de ASSL.</span><span class="sxs-lookup"><span data-stu-id="ab355-161">For more information on inherited defaults, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
  
