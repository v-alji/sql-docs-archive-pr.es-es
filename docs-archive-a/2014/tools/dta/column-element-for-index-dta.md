---
title: Column (DTA, elemento de index) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Column element
ms.assetid: ba9fac20-26bd-4333-940e-842c15241b46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67853dc7d1193d3a0f80e56023846bc55a20bdaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743799"
---
# <a name="column-element-for-index-dta"></a><span data-ttu-id="0dd17-102">Column (DTA, elemento de Index)</span><span class="sxs-lookup"><span data-stu-id="0dd17-102">Column Element for Index (DTA)</span></span>
  <span data-ttu-id="0dd17-103">Establece las columnas de una configuración especificada por el usuario en las que se va a crear el índice.</span><span class="sxs-lookup"><span data-stu-id="0dd17-103">Specifies the columns on which the index is created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd17-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0dd17-104">Syntax</span></span>  
  
```  
  
<Create>  
  <Index>  
    <Name>...</Name>  
    <Column [Type | SortOrder]>  
     ...code removed here...  
     </Column>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="0dd17-105">Atributos del elemento</span><span class="sxs-lookup"><span data-stu-id="0dd17-105">Element Attributes</span></span>  
  
|<span data-ttu-id="0dd17-106">Atributo Column</span><span class="sxs-lookup"><span data-stu-id="0dd17-106">Column Attribute</span></span>|<span data-ttu-id="0dd17-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0dd17-107">Description</span></span>|  
|----------------------|-----------------|  
|`Type`|<span data-ttu-id="0dd17-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0dd17-108">Optional.</span></span> <span data-ttu-id="0dd17-109">Especifica el tipo de columna de índice.</span><span class="sxs-lookup"><span data-stu-id="0dd17-109">Specifies the index column type.</span></span> <span data-ttu-id="0dd17-110">Utilice un tipo de datos **string** para especificar este atributo mediante uno de los siguientes valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="0dd17-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="0dd17-111">`KeyColumn`:</span><span class="sxs-lookup"><span data-stu-id="0dd17-111">`KeyColumn`:</span></span><br />                  <span data-ttu-id="0dd17-112">Especifica que una clave de índice hace referencia a la columna.</span><span class="sxs-lookup"><span data-stu-id="0dd17-112">Specifies that the column is referenced by an index key.</span></span> <span data-ttu-id="0dd17-113">Utilice la siguiente sintaxis para establecer este atributo:</span><span class="sxs-lookup"><span data-stu-id="0dd17-113">Use the following syntax to set this attribute:</span></span><br />`<Column Type="KeyColumn">`<br /><span data-ttu-id="0dd17-114">Para obtener más información sobre las columnas de claves, vea [Índices agrupados y no agrupados descritos](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="0dd17-114">For more information about key columns, see [Clustered and Nonclustered Indexes Described](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span></span><br /><br /> <span data-ttu-id="0dd17-115">`IncludedColumn`: Especifica que la columna es una columna incluida (en lugar de una columna de clave).</span><span class="sxs-lookup"><span data-stu-id="0dd17-115">`IncludedColumn`: Specifies that the column is an included column (instead of a key column).</span></span> <span data-ttu-id="0dd17-116">Utilice la siguiente sintaxis para establecer este atributo:</span><span class="sxs-lookup"><span data-stu-id="0dd17-116">Use the following syntax to set this attribute:</span></span><br />`<Column Type="IncludedColumn">`<br /><span data-ttu-id="0dd17-117">Para obtener más información sobre las columnas incluidas, vea [Crear índices con columnas incluidas](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="0dd17-117">For more information about included columns, see [Create Indexes with Included Columns](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span></span>|  
|`SortOrder`|<span data-ttu-id="0dd17-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0dd17-118">Optional.</span></span> <span data-ttu-id="0dd17-119">Especifica el orden de la columna.</span><span class="sxs-lookup"><span data-stu-id="0dd17-119">Specifies the sorting order of the column.</span></span> <span data-ttu-id="0dd17-120">Utilice un tipo de datos **string** para especificar un orden **"Ascending"** (ascendente) o **"Descending"** (descendente), como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="0dd17-120">Use a **string** data type to specify either an **"Ascending"** or **"Descending"** sorting order as follows:</span></span><br /><br /> `<Column SortOrder="Ascending">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="0dd17-121">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="0dd17-121">Element Characteristics</span></span>  
  
|<span data-ttu-id="0dd17-122">Característica</span><span class="sxs-lookup"><span data-stu-id="0dd17-122">Characteristic</span></span>|<span data-ttu-id="0dd17-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="0dd17-123">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0dd17-124">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="0dd17-124">**Data type and length**</span></span>|<span data-ttu-id="0dd17-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0dd17-125">None.</span></span>|  
|<span data-ttu-id="0dd17-126">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="0dd17-126">**Default value**</span></span>|<span data-ttu-id="0dd17-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0dd17-127">None.</span></span>|  
|<span data-ttu-id="0dd17-128">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="0dd17-128">**Occurrence**</span></span>|<span data-ttu-id="0dd17-129">Puede especificar hasta 1.024 columnas para el elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="0dd17-129">Can specify up to 1024 columns for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="0dd17-130">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="0dd17-130">Element Relationships</span></span>  
  
|<span data-ttu-id="0dd17-131">Relación</span><span class="sxs-lookup"><span data-stu-id="0dd17-131">Relationship</span></span>|<span data-ttu-id="0dd17-132">Elementos</span><span class="sxs-lookup"><span data-stu-id="0dd17-132">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="0dd17-133">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="0dd17-133">**Parent element**</span></span>|[<span data-ttu-id="0dd17-134">Index &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="0dd17-134">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="0dd17-135">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="0dd17-135">**Child elements**</span></span>|[<span data-ttu-id="0dd17-136">Elemento Name de Column &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="0dd17-136">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="0dd17-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0dd17-137">Example</span></span>  
 <span data-ttu-id="0dd17-138">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML con configuración especificada por el usuario &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="0dd17-138">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd17-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0dd17-139">See Also</span></span>  
 [<span data-ttu-id="0dd17-140">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="0dd17-140">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
