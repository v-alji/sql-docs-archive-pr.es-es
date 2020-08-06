---
title: Almacenamiento de dimensiones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- dimensions [Analysis Services], storage
- storing data [Analysis Services]
- storage [Analysis Services], dimensions
- relational OLAP
- multidimensional OLAP
- MOLAP
- storing data [Analysis Services], dimensions
- ROLAP
ms.assetid: 8d74b932-2174-4e1f-8414-636455880b6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa68ebcfa8f4136bcd4a131842c852665ee9851
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744414"
---
# <a name="dimension-storage"></a><span data-ttu-id="d261f-102">Almacenamiento de dimensiones</span><span class="sxs-lookup"><span data-stu-id="d261f-102">Dimension Storage</span></span>
  <span data-ttu-id="d261f-103">Las dimensiones de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] admiten dos modos de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="d261f-103">Dimensions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support two storage modes:</span></span>  
  
-   <span data-ttu-id="d261f-104">OLAP relacional (ROLAP)</span><span class="sxs-lookup"><span data-stu-id="d261f-104">Relational OLAP (ROLAP)</span></span>  
  
-   <span data-ttu-id="d261f-105">OLAP multidimensional (MOLAP)</span><span class="sxs-lookup"><span data-stu-id="d261f-105">Multidimensional OLAP (MOLAP)</span></span>  
  
 <span data-ttu-id="d261f-106">El modo de almacenamiento determina la ubicación y la forma de los datos de una dimensión.</span><span class="sxs-lookup"><span data-stu-id="d261f-106">The storage mode determines the location and form of a dimension's data.</span></span> <span data-ttu-id="d261f-107">El modo de almacenamiento predeterminado para las dimensiones es MOLAP.</span><span class="sxs-lookup"><span data-stu-id="d261f-107">MOLAP is the default storage mode for dimensions.</span></span> <span data-ttu-id="d261f-108">**Temas relacionados:**[procesamiento y modos de almacenamiento de particiones](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span><span class="sxs-lookup"><span data-stu-id="d261f-108">**Related topics:**[Partition Storage Modes and Processing](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span></span>  
  
## <a name="molap"></a><span data-ttu-id="d261f-109">MOLAP</span><span class="sxs-lookup"><span data-stu-id="d261f-109">MOLAP</span></span>  
 <span data-ttu-id="d261f-110">Los datos de una dimensión que utiliza MOLAP se almacenan en una estructura multidimensional en la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d261f-110">Data for a dimension that uses MOLAP is stored in a multidimensional structure in the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d261f-111">Esta estructura multidimensional se crea y se llena al procesarse la dimensión.</span><span class="sxs-lookup"><span data-stu-id="d261f-111">This multidimensional structure is created and populated when the dimension is processed.</span></span> <span data-ttu-id="d261f-112">Las dimensiones MOLAP proporcionan un mejor rendimiento de las consultas que las dimensiones ROLAP.</span><span class="sxs-lookup"><span data-stu-id="d261f-112">MOLAP dimensions provide better query performance than ROLAP dimensions.</span></span>  
  
## <a name="rolap"></a><span data-ttu-id="d261f-113">ROLAP</span><span class="sxs-lookup"><span data-stu-id="d261f-113">ROLAP</span></span>  
 <span data-ttu-id="d261f-114">Los datos de una dimensión que utiliza ROLAP se almacenan en las tablas utilizadas para definir la dimensión.</span><span class="sxs-lookup"><span data-stu-id="d261f-114">Data for a dimension that uses ROLAP is actually stored in the tables used to define the dimension.</span></span> <span data-ttu-id="d261f-115">Se puede utilizar el modo de almacenamiento ROLAP para admitir grandes dimensiones sin duplicar grandes cantidades de datos, pero a expensas del rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="d261f-115">The ROLAP storage mode can be used to support large dimensions without duplicating large amounts of data, but at the expense of query performance.</span></span> <span data-ttu-id="d261f-116">Puesto que la dimensión depende directamente de las tablas de la vista del origen de datos utilizadas para definir la dimensión, el modo de almacenamiento ROLAP también admite OLAP en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="d261f-116">Because the dimension relies directly on the tables in the data source view used to define the dimension, the ROLAP storage mode also supports real-time OLAP.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d261f-117">Si una dimensión utiliza el modo de almacenamiento ROLAP y la dimensión se incluye en un cubo que use el almacenamiento MOLAP, el cubo deberá procesarse de inmediato si se realiza algún cambio en el esquema de su tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="d261f-117">If a dimension uses the ROLAP storage mode and the dimension is included in a cube that uses MOLAP storage, any schema changes to its source table must be followed by immediate processing of the cube.</span></span> <span data-ttu-id="d261f-118">Si no se hace de esta manera, pueden producirse resultados incoherentes al realizar consultas al cubo.</span><span class="sxs-lookup"><span data-stu-id="d261f-118">Failure to do this may result in inconsistent results when querying the cube.</span></span> <span data-ttu-id="d261f-119">**Tema relacionado:**[automatizar Analysis Services tareas administrativas con SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="d261f-119">**Related topic:**[Automate Analysis Services Administrative Tasks with SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d261f-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d261f-120">See Also</span></span>  
 [<span data-ttu-id="d261f-121">Procesamiento y modos de almacenamiento de particiones</span><span class="sxs-lookup"><span data-stu-id="d261f-121">Partition Storage Modes and Processing</span></span>](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)  
  
  
