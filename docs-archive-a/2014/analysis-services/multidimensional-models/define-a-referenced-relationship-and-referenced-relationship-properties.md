---
title: Definir una relación referenciada y las propiedades de la relación referenciada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- referenced dimension relationship
- relationships [Analysis Services], referenced dimensions
ms.assetid: 5bb44b41-635b-4398-8fe9-0bfbb142553e
author: minewiskan
ms.author: owend
ms.openlocfilehash: a84cf2ed95ab3660c5a6b3c039dc58351dc43264
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746022"
---
# <a name="define-a-referenced-relationship-and-referenced-relationship-properties"></a><span data-ttu-id="1bc3a-102">Definir relaciones referenciadas y propiedades de las relaciones referenciadas</span><span class="sxs-lookup"><span data-stu-id="1bc3a-102">Define a Referenced Relationship and Referenced Relationship Properties</span></span>
  <span data-ttu-id="1bc3a-103">Una relación de dimensión de referencia se define en la pestaña **Uso de dimensiones** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-103">A reference dimension relationship is defined on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="1bc3a-104">La relación de dimensión de referencia se define al especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1bc3a-104">The reference dimension relationship is defined by specifying the following:</span></span>  
  
-   <span data-ttu-id="1bc3a-105">La dimensión intermedia con la que se va a combinar.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-105">The intermediate dimension to which to join.</span></span> <span data-ttu-id="1bc3a-106">Puede ser una dimensión normal u otra dimensión de referencia.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-106">This can be a regular dimension or another reference dimension.</span></span>  
  
-   <span data-ttu-id="1bc3a-107">Un atributo de dimensión de referencia que defina el nivel mínimo en el que la dimensión está disponible para la agregación con respecto al grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-107">A reference dimension attribute that defines the lowest level that the dimension is available for aggregation with regard to the measure group.</span></span>  
  
-   <span data-ttu-id="1bc3a-108">El atributo (clave externa) de la dimensión intermedia que corresponde al atributo de dimensión de referencia.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-108">The (foreign key) attribute in the intermediate dimension that corresponds to the reference dimension attribute.</span></span>  
  
 <span data-ttu-id="1bc3a-109">Tenga en cuenta que la columna que vincula la dimensión de referencia con la tabla de hechos, que suele ser el atributo clave de la dimensión de referencia, también debe ser definida como un atributo en la dimensión intermedia.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-109">Notice that the column that links the reference dimension to the fact table, which is generally the key attribute in the reference dimension, must also be defined as an attribute in the intermediate dimension.</span></span> <span data-ttu-id="1bc3a-110">Cuando cree una cadena de dimensiones de referencia, comience por crear la relación normal entre la primera dimensión de la cadena y el grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-110">When you create a chain of reference dimensions, start by creating the regular relationship between the first dimension in the chain and the measure group.</span></span> <span data-ttu-id="1bc3a-111">A continuación, cree cada relación referenciada adicional en orden.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-111">Then create each additional referenced relationship in order.</span></span> <span data-ttu-id="1bc3a-112">Una relación referenciada solo se puede realizar para una dimensión que tenga una relación existente con el grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-112">A referenced relationship can only be made to a dimension that has an existing relationship to the measure group.</span></span>  
  
 <span data-ttu-id="1bc3a-113">Cuando se crea una relación de dimensión de referencia, el vínculo del atributo de dimensión se materializa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-113">When you create a reference dimension relationship, the dimension attribute link is materialized by default.</span></span> <span data-ttu-id="1bc3a-114">El materializar un vínculo del atributo de dimensión hace que, durante el procesamiento, el valor del vínculo entre la tabla de hechos y la dimensión de referencia de cada fila se materialice, o almacene, en la estructura MOLAP de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-114">Materializing a dimension attribute link causes the value of the link between the fact table and the reference dimension for each row to be materialized, or stored, in the MOLAP structure for the dimension during processing.</span></span> <span data-ttu-id="1bc3a-115">Esto tendrá un efecto poco importante en el rendimiento del proceso y en los requisitos de almacenamiento, pero mejorará el rendimiento de la consulta.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-115">This will have a minor effect on processing performance and storage requirements, but will improve query performance.</span></span>  
  
 <span data-ttu-id="1bc3a-116">En una dimensión de referencia, la granularidad se especifica mediante la identificación del atributo que define la relación entre una dimensión de referencia y el grupo de medida correspondiente a la tabla principal de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-116">In a reference dimension, granularity is specified by identifying the attribute that defines the relationship between a reference dimension and the measure group corresponding to the main table of the dimension.</span></span> <span data-ttu-id="1bc3a-117">Cuando se encadenan varias dimensiones de referencia, las referencias definen la relación de la dimensión más externa al grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="1bc3a-117">When multiple reference dimensions are chained together, the references define the relationship from the outermost dimension to the measure group.</span></span>  
  
  
