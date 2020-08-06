---
title: Propiedades del cubo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Collation property
- ID property
- ErrorConfiguration property
- cubes [Analysis Services], properties
- Description property
- DefaultMeasure property
- ProcessingMode property
- AggregationPrefix property
- EstimatedRows property
- Visible property
- StorageLocation property
- StorageMode property
- ScriptErrorHandlingMode property
- Source property
- ScriptCacheProcessingMode property
- Language property
- Name property
- properties [Analysis Services], cubes
- ProcessingPriority property
- ProactiveCaching property
ms.assetid: 72ca3387-620d-4473-8e23-7fe1f2b3d5bf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 27d4202774107795eaddf76c27e21010d534d977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663776"
---
# <a name="cube-properties"></a><span data-ttu-id="22ea7-102">Propiedades del cubo</span><span class="sxs-lookup"><span data-stu-id="22ea7-102">Cube Properties</span></span>
  <span data-ttu-id="22ea7-103">Los cubos tienen varias propiedades que se pueden establecer para modificar el comportamiento del cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-103">Cubes have a number of properties that you can set to affect cube-wide behavior.</span></span> <span data-ttu-id="22ea7-104">Estas propiedades se resumen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="22ea7-104">These properties are summarized in the following table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22ea7-105">Algunas propiedades se establecen automáticamente cuando se crea el cubo y no se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="22ea7-105">Some properties are set automatically when the cube is created and cannot be changed.</span></span>  
  
 <span data-ttu-id="22ea7-106">Para obtener más información sobre cómo establecer las propiedades de un cubo, vea [Diseñador de cubos &#40;Analysis Services-&#41;de datos multidimensionales ](../cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="22ea7-106">For more information about how to set cube properties, see [Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](../cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
|<span data-ttu-id="22ea7-107">Propiedad</span><span class="sxs-lookup"><span data-stu-id="22ea7-107">Property</span></span>|<span data-ttu-id="22ea7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="22ea7-108">Description</span></span>|  
|--------------|-----------------|  
|`AggregationPrefix`|<span data-ttu-id="22ea7-109">Especifica el prefijo normal que se utiliza para los nombres de agregación.</span><span class="sxs-lookup"><span data-stu-id="22ea7-109">Specifies the common prefix that is used for aggregation names.</span></span>|  
|`Collation`|<span data-ttu-id="22ea7-110">Especifica el identificador de configuración regional (LCID) y la marca de comparación, separados por un carácter de subrayado. por ejemplo, Latin1_General_C1_AS.</span><span class="sxs-lookup"><span data-stu-id="22ea7-110">Specifies the locale identifier (LCID) and the comparison flag, separated by an underscore: for example, Latin1_General_C1_AS.</span></span>|  
|`DefaultMeasure`|<span data-ttu-id="22ea7-111">Contiene una expresión MDX (Expresiones multidimensionales) que define la medida predeterminada para el cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-111">Contains a Multidimensional Expressions (MDX) expression that defines the default measure for the cube.</span></span>|  
|`Description`|<span data-ttu-id="22ea7-112">Proporciona una descripción del cubo, que se puede mostrar en aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="22ea7-112">Provides a description of the cube, which may be exposed in client applications.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="22ea7-113">Contiene valores de control de errores configurables para controlar claves duplicadas, claves desconocidas, límites de error, acciones al detectar errores, archivos de registro de errores y control de claves nulas.</span><span class="sxs-lookup"><span data-stu-id="22ea7-113">Contains configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`EstimatedRows`|<span data-ttu-id="22ea7-114">Especifica el número de filas estimadas del cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-114">Specifies the number of estimated rows in the cube.</span></span>|  
|`ID`|<span data-ttu-id="22ea7-115">Contiene el identificador único (Id.) del cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-115">Contains the unique identifier (ID) of the cube.</span></span>|  
|`Language`|<span data-ttu-id="22ea7-116">Especifica el identificador de idioma predeterminado del cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-116">Specifies the default language identifier of the cube.</span></span>|  
|`Name`|<span data-ttu-id="22ea7-117">Especifica el nombre descriptivo del cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-117">Specifies the user-friendly name of the cube.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="22ea7-118">Define la configuración de almacenamiento en caché automático para el cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-118">Defines proactive cache settings for the cube.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="22ea7-119">Indica si la indización y la agregación se deben producir durante o después del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="22ea7-119">Indicates whether indexing and aggregating should occur during or after processing.</span></span> <span data-ttu-id="22ea7-120">Las opciones son **regular** o `lazy` .</span><span class="sxs-lookup"><span data-stu-id="22ea7-120">Options are **regular** or `lazy`.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="22ea7-121">Determina la prioridad de procesamiento del cubo durante las operaciones de fondo, como indizaciones y agregaciones diferidas.</span><span class="sxs-lookup"><span data-stu-id="22ea7-121">Determines the processing priority of the cube during background operations, such as lazy aggregations and indexing.</span></span> <span data-ttu-id="22ea7-122">El valor predeterminado es **0**.</span><span class="sxs-lookup"><span data-stu-id="22ea7-122">The default value is **0**.</span></span>|  
|`ScriptCacheProcessingMode`|<span data-ttu-id="22ea7-123">Indica si la caché de script se debe generar durante o después del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="22ea7-123">Indicates whether the script cache should be built during or after processing.</span></span> <span data-ttu-id="22ea7-124">Las opciones son **regular** y `lazy` .</span><span class="sxs-lookup"><span data-stu-id="22ea7-124">Options are **regular** and `lazy`.</span></span>|  
|`ScriptErrorHandlingMode`|<span data-ttu-id="22ea7-125">Determina el control de errores.</span><span class="sxs-lookup"><span data-stu-id="22ea7-125">Determines error handling.</span></span> <span data-ttu-id="22ea7-126">Las opciones son `IgnoreNone` o`IgnoreAll`</span><span class="sxs-lookup"><span data-stu-id="22ea7-126">Options are `IgnoreNone` or `IgnoreAll`</span></span>|  
|`Source`|<span data-ttu-id="22ea7-127">Muestra la vista del origen de datos utilizada para el cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-127">Displays the data source view used for the cube.</span></span>|  
|`StorageLocation`|<span data-ttu-id="22ea7-128">Especifica la ubicación de almacenamiento del sistema de archivos para el cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-128">Specifies the file system storage location for the cube.</span></span> <span data-ttu-id="22ea7-129">Si no se especifica ninguna ubicación, se hereda de la base de datos que contiene el objeto de cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-129">If none is specified, the location is inherited from the database that contains the cube object.</span></span>|  
|`StorageMode`|<span data-ttu-id="22ea7-130">Especifica el modo de almacenamiento del cubo.</span><span class="sxs-lookup"><span data-stu-id="22ea7-130">Specifies the storage mode for the cube.</span></span> <span data-ttu-id="22ea7-131">Los valores son `MOLAP` , `ROLAP` o`HOLAP``.`</span><span class="sxs-lookup"><span data-stu-id="22ea7-131">Values are `MOLAP`, `ROLAP`, or `HOLAP``.`</span></span>|  
|`Visible`|<span data-ttu-id="22ea7-132">Determina la visibilidad del cubo</span><span class="sxs-lookup"><span data-stu-id="22ea7-132">Determines the visibility of the cube.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="22ea7-133">Para obtener más información sobre cómo establecer los valores de la propiedad ErrorConfiguration cuando se trabaja con valores NULL y otros problemas de integridad de datos, vea [control de problemas de integridad de datos en Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="22ea7-133">For more information about setting values for the ErrorConfiguration property when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ea7-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22ea7-134">See Also</span></span>  
 [<span data-ttu-id="22ea7-135">Almacenamiento en caché automático &#40;particiones&#41;</span><span class="sxs-lookup"><span data-stu-id="22ea7-135">Proactive Caching &#40;Partitions&#41;</span></span>](partitions-proactive-caching.md)  
  
  
