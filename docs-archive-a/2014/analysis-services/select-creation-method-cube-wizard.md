---
title: Seleccionar método de creación (Asistente para cubos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubewizard.cubedefinition.f1
ms.assetid: 985d3b5b-7891-465b-862d-f7e75431b342
author: minewiskan
ms.author: owend
ms.openlocfilehash: c8c4d611e00a2b3f5d115ea5749b1e494a44bf57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676187"
---
# <a name="select-creation-method-cube-wizard"></a><span data-ttu-id="8d38b-102">Seleccionar método de creación (Asistente para cubos)</span><span class="sxs-lookup"><span data-stu-id="8d38b-102">Select Creation Method (Cube Wizard)</span></span>
  <span data-ttu-id="8d38b-103">Use la página **Seleccionar método de creación** para especificar cómo se crea el cubo.</span><span class="sxs-lookup"><span data-stu-id="8d38b-103">Use the **Select Creation Method** page to specify how to create the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d38b-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="8d38b-104">Options</span></span>  
 <span data-ttu-id="8d38b-105">**Usar tablas existentes**</span><span class="sxs-lookup"><span data-stu-id="8d38b-105">**Use existing tables**</span></span>  
 <span data-ttu-id="8d38b-106">Seleccione esta opción para crear un cubo utilizando tablas existentes en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8d38b-106">Select to create a cube by using existing tables in a data source.</span></span> <span data-ttu-id="8d38b-107">El asistente le guiará a través del proceso de selección y definición de grupos y dimensiones de medida basados en tablas existentes para generar el nuevo cubo.</span><span class="sxs-lookup"><span data-stu-id="8d38b-107">The wizard will guide you through the process of selecting and defining measure groups and dimensions based on existing tables to build your new cube.</span></span>  
  
 <span data-ttu-id="8d38b-108">**Crear un cubo vacío**</span><span class="sxs-lookup"><span data-stu-id="8d38b-108">**Create an empty cube**</span></span>  
 <span data-ttu-id="8d38b-109">Seleccione esta opción para crear un cubo vacío.</span><span class="sxs-lookup"><span data-stu-id="8d38b-109">Select to create an empty cube.</span></span> <span data-ttu-id="8d38b-110">Esta opción resulta útil cuando desee crear todo de forma manual o cuando todos los grupos de medida en el cubo son grupos de medida vinculados.</span><span class="sxs-lookup"><span data-stu-id="8d38b-110">This option is useful when you want to create everything manually, or when all measure groups in the cube are linked measure groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d38b-111">Esta opción solo está disponible cuando trabaja con un proyecto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y no está disponible cuando está conectado directamente a una base de datos [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d38b-111">This option is only available when you are working with an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and not when you are connected directly to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="8d38b-112">**Generar tablas en el origen de datos**</span><span class="sxs-lookup"><span data-stu-id="8d38b-112">**Generate tables in the data source**</span></span>  
 <span data-ttu-id="8d38b-113">Seleccione esta opción para crear en primer lugar un cubo primero y, a continuación, generar nuevas tablas en el origen de datos basado\*\* en la definición de cubo.</span><span class="sxs-lookup"><span data-stu-id="8d38b-113">Select to create a cube first and then generate new tables in the data source based on the cube definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d38b-114">Para usar esta opción, debe tener permiso para crear objetos en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="8d38b-114">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="8d38b-115">Si selecciona esta opción, se habilitará la opción **Plantilla** .</span><span class="sxs-lookup"><span data-stu-id="8d38b-115">Selecting this option will make the **Template** option available.</span></span>  
  
 <span data-ttu-id="8d38b-116">**Plantilla**</span><span class="sxs-lookup"><span data-stu-id="8d38b-116">**Template**</span></span>  
 <span data-ttu-id="8d38b-117">Seleccione la plantilla que desea usar para crear el cubo.</span><span class="sxs-lookup"><span data-stu-id="8d38b-117">Select the template that you want to use to create the cube.</span></span> <span data-ttu-id="8d38b-118">Las plantillas proporcionan un conjunto de definiciones orientadas para un motivo\*\* profesional específico.</span><span class="sxs-lookup"><span data-stu-id="8d38b-118">Templates provide a set of definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d38b-119">Esta opción solo está disponible cuando se ha activado la opción **Generar tablas en el origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="8d38b-119">This option is only available when the **Generate tables in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d38b-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d38b-120">See Also</span></span>  
 <span data-ttu-id="8d38b-121">[Objetos de cubo &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8d38b-121">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="8d38b-122">[Cubos en modelos multidimensionales](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="8d38b-122">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="8d38b-123">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="8d38b-123">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
