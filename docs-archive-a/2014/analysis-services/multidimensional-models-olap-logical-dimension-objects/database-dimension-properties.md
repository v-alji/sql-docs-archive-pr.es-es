---
title: Propiedades de dimensión de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- metadata [Analysis Services]
- dimensions [Analysis Services], characteristics
- properties [Analysis Services], dimensions
ms.assetid: 075548ef-08a3-413c-8ee0-4a074c276fcc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 504e190f4c513a8c999c4d7d7ab9eaabb83298c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675025"
---
# <a name="database-dimension-properties"></a><span data-ttu-id="84449-102">Propiedades de la dimensión de base de datos</span><span class="sxs-lookup"><span data-stu-id="84449-102">Database Dimension Properties</span></span>
  <span data-ttu-id="84449-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , las características de una dimensión se definen mediante los metadatos de la dimensión, en función de la configuración de varias propiedades de dimensión y de los atributos o las jerarquías que contiene la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the characteristics of a dimension are defined by the metadata for the dimension, based on the settings of various dimension properties, and on the attributes or hierarchies that are contained by the dimension.</span></span> <span data-ttu-id="84449-104">En la siguiente tabla se describen las propiedades de dimensión de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84449-104">The following table describes the dimension properties in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="84449-105">Propiedad</span><span class="sxs-lookup"><span data-stu-id="84449-105">Property</span></span>|<span data-ttu-id="84449-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="84449-106">Description</span></span>|  
|--------------|-----------------|  
|`AttributeAllMemberName`|<span data-ttu-id="84449-107">Especifica el nombre del miembro Todos de los atributos de una dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-107">Specifies the name of the All member for attributes in a dimension.</span></span>|  
|`Collation`|<span data-ttu-id="84449-108">Determina la intercalación utilizada por la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-108">Determines the collation used by the dimension.</span></span>|  
|`CurrentStorageMode`|<span data-ttu-id="84449-109">Contiene el modo de almacenamiento actual de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-109">Contains the current storage mode for the dimension.</span></span>|  
|`DependsOnDimension`|<span data-ttu-id="84449-110">Contiene el Id. de otra dimensión de la que depende la dimensión, si la hubiera.</span><span class="sxs-lookup"><span data-stu-id="84449-110">Contains the ID of another dimension on which the dimension depends, if any.</span></span>|  
|`Description`|<span data-ttu-id="84449-111">Contiene la descripción de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-111">Contains the description of the dimension.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="84449-112">Configuración de control de errores configurable para controlar las claves duplicadas, las claves no conocidas, los límites de error, las acciones tras la detección de errores, el archivo de registro de errores y el control de claves NULL.</span><span class="sxs-lookup"><span data-stu-id="84449-112">Configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`ID`|<span data-ttu-id="84449-113">Contiene el identificador (Id.) único de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-113">Contains the unique identifier (ID) of the dimension.</span></span>|  
|`Language`|<span data-ttu-id="84449-114">Especifica el idioma predeterminado de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-114">Specifies the default language for the dimension.</span></span>|  
|`MdxMissingMemberMode`|<span data-ttu-id="84449-115">Determina cómo se gestionan los miembros que faltan en las instrucciones MDX (Expresiones multidimensionales).</span><span class="sxs-lookup"><span data-stu-id="84449-115">Determines how missing members are handled for Multidimensional Expressions (MDX) statements.</span></span>|  
|`MiningModelID`|<span data-ttu-id="84449-116">Contiene el Id. del modelo de minería de datos al que se asocia la dimensión de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="84449-116">Contains the ID of the mining model with which the data mining dimension is associated.</span></span> <span data-ttu-id="84449-117">Esta propiedad solo se aplica si la dimensión es una dimensión de modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="84449-117">This property is applicable only if the dimension is a mining model dimension.</span></span>|  
|`Name`|<span data-ttu-id="84449-118">Especifica el nombre de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-118">Specifies the name of the dimension.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="84449-119">Define la configuración de almacenamiento en caché automático de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-119">Defines the proactive cache settings for the dimension.</span></span>|  
|`ProcessingGroup`|<span data-ttu-id="84449-120">Especifica el grupo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="84449-120">Specifies the processing group.</span></span> <span data-ttu-id="84449-121">Sus valores son ByAttribute o ByTable.</span><span class="sxs-lookup"><span data-stu-id="84449-121">Values are ByAttribute or ByTable.</span></span> <span data-ttu-id="84449-122">El valor predeterminado es `ByAttribute`.</span><span class="sxs-lookup"><span data-stu-id="84449-122">Default is `ByAttribute`.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="84449-123">Indica si [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] debe indizar y agregar durante o después del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="84449-123">Indicates whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should index and aggregate during or after processing.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="84449-124">Determina la prioridad de procesamiento de la dimensión durante operaciones en segundo plano como la agregación diferida, la indización o la agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="84449-124">Determines the processing priority of the dimension during background operations such as lazy aggregation, indexing, or clustering.</span></span>|  
|`Source`|<span data-ttu-id="84449-125">Identifica la vista del origen de datos a la que está enlazada la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-125">Identifies the data source view to which the dimension is bound.</span></span>|  
|`StorageMode`|<span data-ttu-id="84449-126">Determina el modo de almacenamiento de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-126">Determines the storage mode for the dimension.</span></span>|  
|`Type`|<span data-ttu-id="84449-127">Especifica el tipo de dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-127">Specifies the type of the dimension.</span></span>|  
|`UnknownMember`|<span data-ttu-id="84449-128">Indica si el miembro desconocido está visible.</span><span class="sxs-lookup"><span data-stu-id="84449-128">Indicates whether the unknown member is visible.</span></span>|  
|`UnknownMemberName`|<span data-ttu-id="84449-129">Especifica el título, en el idioma predeterminado de la dimensión, del miembro desconocido de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="84449-129">Specifies the caption, in the default language of the dimension, for the unknown member of the dimension.</span></span>|  
|`WriteEnabled`|<span data-ttu-id="84449-130">Indica si las reescrituras de dimensión están disponibles (sujetas a permisos de seguridad).</span><span class="sxs-lookup"><span data-stu-id="84449-130">Indicates whether dimension writebacks are available (subject to security permissions).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="84449-131">Para obtener más información acerca de cómo establecer los valores de las propiedades ErrorConfiguration y UnknownMember al trabajar con valores NULL y otros problemas de integridad de datos, vea [control de problemas de integridad de datos en Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="84449-131">For more information about setting values for the ErrorConfiguration and UnknownMember properties when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84449-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84449-132">See Also</span></span>  
 <span data-ttu-id="84449-133">[Atributos y jerarquías de atributos](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="84449-133">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="84449-134">[Jerarquías de usuario](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="84449-134">[User Hierarchies](user-hierarchies.md) </span></span>  
 <span data-ttu-id="84449-135">[Relaciones de dimensión](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="84449-135">[Dimension Relationships](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 [<span data-ttu-id="84449-136">Dimensiones &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="84449-136">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
