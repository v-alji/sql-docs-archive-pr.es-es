---
title: Reglas de nomenclatura de objetos (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], naming
ms.assetid: b338a60d-4802-4b68-862a-6dc6a3f75e48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adfd4b23b6fe9129641271fc3c2381e161119ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675585"
---
# <a name="object-naming-rules-analysis-services"></a><span data-ttu-id="e6ea6-102">Normas de nomenclatura de objetos (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="e6ea6-102">Object Naming Rules (Analysis Services)</span></span>
  <span data-ttu-id="e6ea6-103">En este tema se describen las convenciones de nomenclatura de los objetos, así como las palabras y los caracteres reservados que no se pueden usar en ningún nombre de objeto, código o script en [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6ea6-103">This topic describes object naming conventions, as well as the reserved words and characters that cannot be used in any object name, in code or script in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
##  <a name="naming-conventions"></a><a name="bkmk_Names"></a><span data-ttu-id="e6ea6-104">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="e6ea6-104">Naming Conventions</span></span>  
 <span data-ttu-id="e6ea6-105">Cada objeto tiene una propiedad `Name` y `ID` que debe ser única dentro del ámbito de la colección primaria.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-105">Every object has a `Name` and `ID` property that must be unique within the scope of the parent collection.</span></span> <span data-ttu-id="e6ea6-106">Por ejemplo, dos dimensiones pueden tener el mismo nombre siempre y cuando cada una resida en una base de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-106">For example, two dimensions can have same name as long as each one resides in a different database.</span></span>  
  
 <span data-ttu-id="e6ea6-107">Aunque puede especificarla manualmente, la propiedad `ID` se suele generar automáticamente cuando se crea el objeto.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-107">Although you can specify it manually, the `ID` is typically auto-generated when the object is created.</span></span> <span data-ttu-id="e6ea6-108">Nunca debe cambiar el valor de `ID` después de haber empezado a crear un modelo.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-108">You should never change the `ID` once you have begun building a model.</span></span> <span data-ttu-id="e6ea6-109">Todas las referencias a objetos de un modelo se basan en el valor de `ID`.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-109">All object references throughout a model are based on the `ID`.</span></span> <span data-ttu-id="e6ea6-110">Por tanto, si se cambia un valor de `ID` el modelo puede resultar dañado fácilmente.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-110">Thus, changing an `ID` can easily result in model corruption.</span></span>  
  
 <span data-ttu-id="e6ea6-111">Los objetos `DataSource` y `DataSourceView` tienen excepciones destacadas a las convenciones de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-111">`DataSource` and `DataSourceView` objects have notable exceptions to naming conventions.</span></span> <span data-ttu-id="e6ea6-112">El valor de ID de un objeto `DataSource` se puede establecer en un solo punto (.), que no es único, como referencia a la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-112">`DataSource` ID can be set to a single dot (.), which is not unique, as a reference to the current database.</span></span> <span data-ttu-id="e6ea6-113">Una segunda excepción es `DataSourceView`, que se adhiere a las convenciones de nomenclatura definidas para los objetos `DataSet` en .NET Framework, donde `Name` se usa como identificador.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-113">A second exception is `DataSourceView`, which adheres to the naming conventions defined for `DataSet` objects in the .NET Framework, where the `Name` is used as the identifier.</span></span>  
  
 <span data-ttu-id="e6ea6-114">Las siguientes reglas se aplican a las propiedades `Name` e `ID`.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-114">The following rules apply to `Name` and `ID` properties.</span></span>  
  
-   <span data-ttu-id="e6ea6-115">Los nombres no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-115">Names are case insensitive.</span></span> <span data-ttu-id="e6ea6-116">No puede tener un cubo denominado "ventas" y otro denominado "ventas" en la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-116">You cannot have a cube named "sales" and another named "Sales" in the same database.</span></span>  
  
-   <span data-ttu-id="e6ea6-117">No se permiten espacios iniciales o finales en el nombre de un objeto, aunque sí se pueden incluir espacios dentro de un nombre.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-117">No leading or trailing spaces allowed in an object name, although you can embed spaces within a name.</span></span> <span data-ttu-id="e6ea6-118">Los espacios iniciales o finales se recortan implícitamente.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-118">Leading and trailing spaces are implicitly trimmed.</span></span> <span data-ttu-id="e6ea6-119">Esto se aplica a los valores de `Name` e `ID` de un objeto.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-119">This applies to both the `Name` and `ID` of an object.</span></span>  
  
-   <span data-ttu-id="e6ea6-120">El número máximo de caracteres es 100.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-120">The maximum number of characters is 100.</span></span>  
  
-   <span data-ttu-id="e6ea6-121">No hay ningún requisito especial para el primer carácter de un identificador.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-121">There is no special requirement for the first character of an identifier.</span></span> <span data-ttu-id="e6ea6-122">El primer carácter puede ser cualquier carácter válido.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-122">The first character may be any valid character.</span></span>  
  
##  <a name="reserved-words-and-characters"></a><a name="bkmk_reserved"></a><span data-ttu-id="e6ea6-123">Palabras y caracteres reservados</span><span class="sxs-lookup"><span data-stu-id="e6ea6-123">Reserved Words and Characters</span></span>  
 <span data-ttu-id="e6ea6-124">Las palabras reservadas están en inglés y se aplican a los nombres de objeto, no a los títulos.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-124">Reserved words are in English, and apply to object names, not Captions.</span></span> <span data-ttu-id="e6ea6-125">Si usa accidentalmente una palabra reservada en un nombre de objeto, se producirá un error de validación.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-125">If you inadvertently use a reserved word in an object name, a validation error will occur.</span></span> <span data-ttu-id="e6ea6-126">En los modelos multidimensionales y de minería de datos, las palabras reservadas que se describen a continuación no se pueden usar en ningún nombre de objeto en ningún momento.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-126">For multidimensional and data mining models, the reserved words described below cannot be used in any object name, at any time.</span></span>  
  
 <span data-ttu-id="e6ea6-127">En los modelos tabulares, donde la compatibilidad de la base de datos se establece en 1103, se han relajado las reglas de validación para ciertos objetos y no cumplen los requisitos de caracteres extendidos y las convenciones de nomenclatura de determinadas aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-127">For tabular models, where the database compatibility is set to 1103, validation rules have been relaxed for certain objects, out of compliance for the extended character requirements and naming conventions of certain client applications.</span></span> <span data-ttu-id="e6ea6-128">Las bases de datos que cumplen estos criterios están sujetas a reglas de validación menos estrictas.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-128">Databases that meet these criteria are subject to less stringent validation rules.</span></span> <span data-ttu-id="e6ea6-129">En este caso, es posible que un nombre de objeto incluya un carácter restringido y siga superando la validación.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-129">In this case, it's possible for an object name to include a restricted character and still pass validation.</span></span>  
  
 <span data-ttu-id="e6ea6-130">**Palabras reservadas**</span><span class="sxs-lookup"><span data-stu-id="e6ea6-130">**Reserved Words**</span></span>  
  
-   <span data-ttu-id="e6ea6-131">AUX</span><span class="sxs-lookup"><span data-stu-id="e6ea6-131">AUX</span></span>  
  
-   <span data-ttu-id="e6ea6-132">CLOCK$</span><span class="sxs-lookup"><span data-stu-id="e6ea6-132">CLOCK$</span></span>  
  
-   <span data-ttu-id="e6ea6-133">De COM1 a COM9 (COM1, COM2, COM3, etc.)</span><span class="sxs-lookup"><span data-stu-id="e6ea6-133">COM1 through COM9 (COM1, COM2, COM3, and so on)</span></span>  
  
-   <span data-ttu-id="e6ea6-134">CON</span><span class="sxs-lookup"><span data-stu-id="e6ea6-134">CON</span></span>  
  
-   <span data-ttu-id="e6ea6-135">De LPT1 a LPT9 (LPT1, LPT2, LPT3, etc.)</span><span class="sxs-lookup"><span data-stu-id="e6ea6-135">LPT1 through LPT9 (LPT1, LPT2, LPT3, and so on)</span></span>  
  
-   <span data-ttu-id="e6ea6-136">NUL</span><span class="sxs-lookup"><span data-stu-id="e6ea6-136">NUL</span></span>  
  
-   <span data-ttu-id="e6ea6-137">PRN</span><span class="sxs-lookup"><span data-stu-id="e6ea6-137">PRN</span></span>  
  
-   <span data-ttu-id="e6ea6-138">NULL no se permite como carácter en ninguna cadena dentro del XML.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-138">NULL is not allowed as a character in any string within the XML</span></span>  
  
 <span data-ttu-id="e6ea6-139">**Caracteres reservados**</span><span class="sxs-lookup"><span data-stu-id="e6ea6-139">**Reserved Characters**</span></span>  
  
 <span data-ttu-id="e6ea6-140">La tabla siguiente muestra caracteres no válidos para objetos especificados.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-140">The following table lists invalid characters for specific objects.</span></span>  
  
|<span data-ttu-id="e6ea6-141">Object</span><span class="sxs-lookup"><span data-stu-id="e6ea6-141">Object</span></span>|<span data-ttu-id="e6ea6-142">Caracteres no válidos</span><span class="sxs-lookup"><span data-stu-id="e6ea6-142">Invalid characters</span></span>|  
|------------|------------------------|  
|`Server`|<span data-ttu-id="e6ea6-143">Siga las convenciones de nomenclatura de servidores de Windows al asignar nombre a un objeto de servidor.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-143">Follow Windows server naming conventions when naming a server object.</span></span> <span data-ttu-id="e6ea6-144">Vea [Convenciones de nomenclatura (Windows)](/windows/desktop/DNS/naming-conventions) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-144">See [Naming Conventions (Windows)](/windows/desktop/DNS/naming-conventions) for details.</span></span>|  
|`DataSource`| `: / \ * \| ? " () [] {} <>` |  
|<span data-ttu-id="e6ea6-145">`Level` o `Attribute`</span><span class="sxs-lookup"><span data-stu-id="e6ea6-145">`Level` or `Attribute`</span></span>|````. , ; ' ` : / \ * & \| ? " & % $ ! + = [] {} < >````|  
|<span data-ttu-id="e6ea6-146">`Dimension` o `Hierarchy`</span><span class="sxs-lookup"><span data-stu-id="e6ea6-146">`Dimension` or `Hierarchy`</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} <,>````|  
|<span data-ttu-id="e6ea6-147">Todos los demás objetos</span><span class="sxs-lookup"><span data-stu-id="e6ea6-147">All other objects</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} < >````|  
  
 <span data-ttu-id="e6ea6-148">**Excepciones: cuándo se permiten caracteres reservados**</span><span class="sxs-lookup"><span data-stu-id="e6ea6-148">**Exceptions: When Reserved Characters are Allowed**</span></span>  
  
 <span data-ttu-id="e6ea6-149">Como se ha indicado, los nombres de las bases de datos de una modalidad y un nivel de compatibilidad determinados pueden incluir caracteres reservados.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-149">As noted, databases of a specific modality and compatibility level can have object names that include reserved characters.</span></span> <span data-ttu-id="e6ea6-150">Los nombres de objeto de atributo de dimensión, jerarquía, nivel, medida y KPI pueden incluir caracteres reservados para las bases de datos tabulares (1103 o superior) que permiten el uso de caracteres extendidos:</span><span class="sxs-lookup"><span data-stu-id="e6ea6-150">Dimension attribute, hierarchy, level, measure and KPI object names can include reserved characters, for tabular databases (1103 or higher) that allow the use of extended characters:</span></span>  
  
|<span data-ttu-id="e6ea6-151">Modo de servidor y nivel de compatibilidad de base de datos</span><span class="sxs-lookup"><span data-stu-id="e6ea6-151">Server mode and database compatibility level</span></span>|<span data-ttu-id="e6ea6-152">¿Se permiten caracteres reservados?</span><span class="sxs-lookup"><span data-stu-id="e6ea6-152">Reserved characters allowed?</span></span>|  
|--------------------------------------------------|----------------------------------|  
|<span data-ttu-id="e6ea6-153">MOLAP (todas las versiones)</span><span class="sxs-lookup"><span data-stu-id="e6ea6-153">MOLAP (all versions)</span></span>|<span data-ttu-id="e6ea6-154">No</span><span class="sxs-lookup"><span data-stu-id="e6ea6-154">No</span></span>|  
|<span data-ttu-id="e6ea6-155">Tabular - 1050</span><span class="sxs-lookup"><span data-stu-id="e6ea6-155">Tabular - 1050</span></span>|<span data-ttu-id="e6ea6-156">No</span><span class="sxs-lookup"><span data-stu-id="e6ea6-156">No</span></span>|  
|<span data-ttu-id="e6ea6-157">Tabular - 1100</span><span class="sxs-lookup"><span data-stu-id="e6ea6-157">Tabular - 1100</span></span>|<span data-ttu-id="e6ea6-158">No</span><span class="sxs-lookup"><span data-stu-id="e6ea6-158">No</span></span>|  
|<span data-ttu-id="e6ea6-159">Tabular: 1130 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="e6ea6-159">Tabular - 1130 and higher</span></span>|<span data-ttu-id="e6ea6-160">Sí</span><span class="sxs-lookup"><span data-stu-id="e6ea6-160">Yes</span></span>|  
  
 <span data-ttu-id="e6ea6-161">Las bases de datos pueden tener un ModelType predeterminado (default).</span><span class="sxs-lookup"><span data-stu-id="e6ea6-161">Databases can have a ModelType of default.</span></span> <span data-ttu-id="e6ea6-162">Default es equivalente a multidimensional y por tanto no admite el uso de caracteres reservados en los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="e6ea6-162">Default is equivalent to multidimensional, and thus does not support the use of reserved characters in column names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6ea6-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6ea6-163">See Also</span></span>  
 <span data-ttu-id="e6ea6-164">[Palabras reservadas de MDX](/sql/mdx/mdx-reserved-words) </span><span class="sxs-lookup"><span data-stu-id="e6ea6-164">[MDX Reserved Words](/sql/mdx/mdx-reserved-words) </span></span>  
 <span data-ttu-id="e6ea6-165">[Traducciones &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span><span class="sxs-lookup"><span data-stu-id="e6ea6-165">[Translations &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span></span>  
 [<span data-ttu-id="e6ea6-166">Compatibilidad con XML for Analysis &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="e6ea6-166">XML for Analysis Compliance &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-compliance-xmla)  
  
  
