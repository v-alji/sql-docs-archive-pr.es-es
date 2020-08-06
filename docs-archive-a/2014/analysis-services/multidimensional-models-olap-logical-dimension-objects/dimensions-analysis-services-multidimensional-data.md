---
title: Dimensiones (Analysis Services de datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- OLAP objects [Analysis Services], dimensions
- dimensions [Analysis Services]
- Analysis Services objects, dimensions
ms.assetid: 2b114135-2572-4479-8c81-3ccf0cfeb9f7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e0e15d4f74c2c6cec06edaf692199e48534c7e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748980"
---
# <a name="dimensions-analysis-services---multidimensional-data"></a><span data-ttu-id="599e7-102">Dimensiones (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="599e7-102">Dimensions (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="599e7-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , las dimensiones son un componente fundamental de los cubos.</span><span class="sxs-lookup"><span data-stu-id="599e7-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], dimensions are a fundamental component of cubes.</span></span> <span data-ttu-id="599e7-104">Las dimensiones organizan los datos en función de un área de interés para los usuarios, por ejemplo clientes, almacenes o empleados.</span><span class="sxs-lookup"><span data-stu-id="599e7-104">Dimensions organize data with relation to an area of interest, such as customers, stores, or employees, to users.</span></span> <span data-ttu-id="599e7-105">Las dimensiones en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contienen atributos que corresponden a columnas de tablas de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="599e7-105">Dimensions in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contain attributes that correspond to columns in dimension tables.</span></span> <span data-ttu-id="599e7-106">Estos atributos aparecen como jerarquías de atributo y se pueden organizar en jerarquías definidas por el usuario, o bien se pueden definir como jerarquías de elementos primarios y secundarios basadas en columnas en la tabla de dimensiones subyacente.</span><span class="sxs-lookup"><span data-stu-id="599e7-106">These attributes appear as attribute hierarchies and can be organized into user-defined hierarchies, or can be defined as parent-child hierarchies based on columns in the underlying dimension table.</span></span> <span data-ttu-id="599e7-107">Las jerarquías se utilizan para organizar las medidas incluidas en un cubo.</span><span class="sxs-lookup"><span data-stu-id="599e7-107">Hierarchies are used to organize measures that are contained in a cube.</span></span> <span data-ttu-id="599e7-108">En los siguientes temas se proporciona información general acerca de las dimensiones, los atributos y las jerarquías.</span><span class="sxs-lookup"><span data-stu-id="599e7-108">The following topics provide an overview of dimensions, attributes, and hierarchies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="599e7-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="599e7-109">In This Section</span></span>  
  
|<span data-ttu-id="599e7-110">Tema</span><span class="sxs-lookup"><span data-stu-id="599e7-110">Topic</span></span>|<span data-ttu-id="599e7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="599e7-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="599e7-112">Introducción a las dimensiones &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="599e7-112">Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="599e7-113">Proporciona información general acerca de los conceptos de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="599e7-113">Provides an overview of dimension concepts.</span></span>|  
|[<span data-ttu-id="599e7-114">Atributos y jerarquías de atributos</span><span class="sxs-lookup"><span data-stu-id="599e7-114">Attributes and Attribute Hierarchies</span></span>](attributes-and-attribute-hierarchies.md)|<span data-ttu-id="599e7-115">Describe los atributos y sus jerarquías.</span><span class="sxs-lookup"><span data-stu-id="599e7-115">Describes attributes and attribute hierarchies.</span></span>|  
|[<span data-ttu-id="599e7-116">Jerarquías de usuario</span><span class="sxs-lookup"><span data-stu-id="599e7-116">User Hierarchies</span></span>](user-hierarchies.md)|<span data-ttu-id="599e7-117">Describe las jerarquías definidas por el usuario de los atributos.</span><span class="sxs-lookup"><span data-stu-id="599e7-117">Describes user-defined hierarchies of attributes.</span></span>|  
|[<span data-ttu-id="599e7-118">Dimensiones habilitadas para escritura</span><span class="sxs-lookup"><span data-stu-id="599e7-118">Write-Enabled Dimensions</span></span>](write-enabled-dimensions.md)|<span data-ttu-id="599e7-119">Describe las dimensiones habilitadas para escritura.</span><span class="sxs-lookup"><span data-stu-id="599e7-119">Describes write-enabled dimensions.</span></span>|  
|[<span data-ttu-id="599e7-120">Traducciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="599e7-120">Dimension Translations</span></span>](dimension-translations.md)|<span data-ttu-id="599e7-121">Describe las traducciones de los metadatos de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="599e7-121">Describes translations of dimension meta data.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="599e7-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="599e7-122">See Also</span></span>  
 <span data-ttu-id="599e7-123">[Dimensiones en modelos multidimensionales](../multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="599e7-123">[Dimensions in Multidimensional Models](../multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="599e7-124">Objetos de cubo &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="599e7-124">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
  
