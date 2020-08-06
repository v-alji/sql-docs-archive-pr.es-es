---
title: Cuadro de diálogo enlaces de grupo de medida (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.dimensionusage.definerelationship.measuregroupbindings.f1
helpviewer_keywords:
- Measure Group Bindings dialog box
ms.assetid: ed642780-5350-438e-af73-b9ceab3f876d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 78693901a5898b140d6efeed16b6f0eaa7577e69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750362"
---
# <a name="measure-group-bindings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="d38f7-102">Cuadro de diálogo Enlaces de grupo de medida (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="d38f7-102">Measure Group Bindings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d38f7-103">Use el cuadro de diálogo **Enlaces de grupo de medida** para crear y modificar las relaciones directas entre los atributos que no son de granularidad de una dimensión de cubo y las columnas de un grupo de medida para una relación de dimensión regular, así como para especificar opciones de procesamiento de valores NULL para los atributos de una dimensión de cubo del cuadro de diálogo **Definir relación** .</span><span class="sxs-lookup"><span data-stu-id="d38f7-103">Use the **Measure Group Bindings** dialog box to create and modify direct relationships between non-granularity attributes in a cube dimension and columns in a measure group for a regular dimension relationship, as well as to specify null processing options for any attribute in a cube dimension, from the **Define Relationship** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d38f7-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="d38f7-104">Options</span></span>  
 <span data-ttu-id="d38f7-105">**Tabla de grupos de medida**</span><span class="sxs-lookup"><span data-stu-id="d38f7-105">**Measure group table**</span></span>  
 <span data-ttu-id="d38f7-106">Muestra el nombre de la tabla de hechos para el grupo de medida seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d38f7-106">Displays the name of the fact table for the selected measure group.</span></span>  
  
 <span data-ttu-id="d38f7-107">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="d38f7-107">**Attributes**</span></span>  
 <span data-ttu-id="d38f7-108">Muestra una cuadrícula de tablas de atributos y dimensiones.</span><span class="sxs-lookup"><span data-stu-id="d38f7-108">Displays a grid of attributes and dimension tables.</span></span> <span data-ttu-id="d38f7-109">Seleccione un atributo para crear o modificar las propiedades de **Relación** del mismo.</span><span class="sxs-lookup"><span data-stu-id="d38f7-109">Select an attribute to create or modify properties in **Relationship** for the selected attribute.</span></span> <span data-ttu-id="d38f7-110">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d38f7-110">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="d38f7-111">Opción</span><span class="sxs-lookup"><span data-stu-id="d38f7-111">Option</span></span>|<span data-ttu-id="d38f7-112">Definición</span><span class="sxs-lookup"><span data-stu-id="d38f7-112">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="d38f7-113">**Nombre del atributo**</span><span class="sxs-lookup"><span data-stu-id="d38f7-113">**Attribute Name**</span></span>|<span data-ttu-id="d38f7-114">Muestra el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="d38f7-114">Displays the name of the attribute.</span></span>|  
|<span data-ttu-id="d38f7-115">**Tabla de dimensiones**</span><span class="sxs-lookup"><span data-stu-id="d38f7-115">**Dimension Table**</span></span>|<span data-ttu-id="d38f7-116">Muestra el nombre de la tabla de dimensiones en la que se basa el atributo.</span><span class="sxs-lookup"><span data-stu-id="d38f7-116">Displays the name of the dimension table on which the attribute is based.</span></span>|  
  
 <span data-ttu-id="d38f7-117">**Relación**</span><span class="sxs-lookup"><span data-stu-id="d38f7-117">**Relationship**</span></span>  
 <span data-ttu-id="d38f7-118">Muestra una cuadrícula de las relaciones existentes entre las columnas de las tablas de dimensiones para el atributo seleccionado y las columnas de las tablas de hechos para el grupo de medida seleccionado, así como la opción de procesamiento de valores NULL para la relación.</span><span class="sxs-lookup"><span data-stu-id="d38f7-118">Displays a grid of relationships between dimension table columns for the selected attribute and fact table columns for the selected measure group as well as the null processing option for the relationship.</span></span> <span data-ttu-id="d38f7-119">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d38f7-119">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="d38f7-120">Opción</span><span class="sxs-lookup"><span data-stu-id="d38f7-120">Option</span></span>|<span data-ttu-id="d38f7-121">Definición</span><span class="sxs-lookup"><span data-stu-id="d38f7-121">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="d38f7-122">**Columnas de dimensión**</span><span class="sxs-lookup"><span data-stu-id="d38f7-122">**Dimension Columns**</span></span>|<span data-ttu-id="d38f7-123">Muestra las columnas de la tabla de dimensiones en la que se basa el atributo seleccionado en **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="d38f7-123">Displays the columns from the dimension table on which the attribute selected in **Attributes** is based.</span></span>|  
|<span data-ttu-id="d38f7-124">**Columnas de grupo de medida**</span><span class="sxs-lookup"><span data-stu-id="d38f7-124">**Measure Group Columns**</span></span>|<span data-ttu-id="d38f7-125">Seleccione **Heredado de la dimensión** para utilizar la relación de grupo de medida heredado de la dimensión o seleccione una columna de la tabla de hechos en la que se basa el grupo de medida para definir explícitamente una relación.</span><span class="sxs-lookup"><span data-stu-id="d38f7-125">Select either **Inherited from dimension** to use the measure group relationship inherited from the dimension, or select a column from the fact table on which the measure group is based to explicitly define a relationship.</span></span>|  
|<span data-ttu-id="d38f7-126">**Procesamiento de valores NULL**</span><span class="sxs-lookup"><span data-stu-id="d38f7-126">**Null Processing**</span></span>|<span data-ttu-id="d38f7-127">Seleccione una opción de procesamiento de valores NULL para el atributo.</span><span class="sxs-lookup"><span data-stu-id="d38f7-127">Select a null processing option for the attribute.</span></span> <span data-ttu-id="d38f7-128">Para más información sobre las opciones de procesamiento de valores NULL, vea [Elemento NullProcessing &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span><span class="sxs-lookup"><span data-stu-id="d38f7-128">For more information about null processing options, see [NullProcessing Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d38f7-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d38f7-129">See Also</span></span>  
 <span data-ttu-id="d38f7-130">[Cuadro de diálogo definir relación &#40;Analysis Services de datos multidimensionales&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d38f7-130">[Define Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="d38f7-131">Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="d38f7-131">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
