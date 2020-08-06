---
title: Definir el comportamiento de suma parcial (Asistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.semiadditivememberdetection.f1
ms.assetid: e57080ba-ce96-40f8-bca7-6701d1725b3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5a3c46de038a7e45dcb39805e324260676a03228
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744434"
---
# <a name="define-semiadditive-behavior-business-intelligence-wizard"></a><span data-ttu-id="14a52-102">Definir el comportamiento de suma parcial (Asistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="14a52-102">Define Semiadditive Behavior (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="14a52-103">Use la página **Definir el comportamiento de suma parcial** para habilitar o deshabilitar el comportamiento de suma parcial en medidas.</span><span class="sxs-lookup"><span data-stu-id="14a52-103">Use the **Define Semiadditive Behavior** page to enable or disable semi-additive behavior on measures.</span></span> <span data-ttu-id="14a52-104">Este comportamiento determina cómo se agregan a una dimensión de tiempo las medidas que contiene un cubo.</span><span class="sxs-lookup"><span data-stu-id="14a52-104">Semi-additive behavior determines how measures that are contained by a cube are aggregated over a time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14a52-105">Excepto LastChild, que está disponible en la edición Standard, los comportamientos de suma parcial solo están disponibles en las ediciones Business Intelligence o Enterprise.</span><span class="sxs-lookup"><span data-stu-id="14a52-105">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span> <span data-ttu-id="14a52-106">Además, como el comportamiento de suma parcial solo se define en medidas y no en dimensiones, no verá esta página del Asistente de Business Intelligence si se ha iniciado desde el Diseñador de dimensiones o haciendo clic con el botón derecho en una dimensión en el Explorador de soluciones de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14a52-106">Furthermore, because semiadditive behavior is defined only on measures and not dimensions, you will not find this page in the Business Intelligence Wizard if it was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="14a52-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="14a52-107">Options</span></span>  
 <span data-ttu-id="14a52-108">**Desactivar el comportamiento de suma parcial**</span><span class="sxs-lookup"><span data-stu-id="14a52-108">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="14a52-109">Deshabilita el comportamiento de suma parcial en todas las medidas del cubo.</span><span class="sxs-lookup"><span data-stu-id="14a52-109">Disables semi-additive behavior in all measures contained by the cube.</span></span>  
  
 <span data-ttu-id="14a52-110">**El asistente ha detectado la \<dimension name> dimensión de cuenta, que contiene miembros de suma parcial. El servidor agregará los miembros de esta dimensión de acuerdo con el comportamiento de suma parcial especificado para cada tipo de cuenta.**</span><span class="sxs-lookup"><span data-stu-id="14a52-110">**The wizard has detected the \<dimension name> account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="14a52-111">Habilita el comportamiento de suma parcial para las dimensiones de cuentas que contienen miembros de suma parcial.</span><span class="sxs-lookup"><span data-stu-id="14a52-111">Enables semi-additive behavior for account dimensions that contain semi-additive members.</span></span> <span data-ttu-id="14a52-112">Al seleccionar esta opción, la función de agregación de todas las medidas de los grupos de medida que hacen referencia a la dimensión de cuentas se establece en `ByAccount`.</span><span class="sxs-lookup"><span data-stu-id="14a52-112">Selecting this option sets the aggregation function of all measures in measure groups that reference the account dimension to `ByAccount`.</span></span>  
  
 <span data-ttu-id="14a52-113">Para más información sobre las dimensiones de cuenta, vea [Crear una cuenta financiera de una dimensión de tipo primario-secundario](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span><span class="sxs-lookup"><span data-stu-id="14a52-113">For more information about account dimensions, see [Create a Finance Account of parent-child type Dimension](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span></span>  
  
 <span data-ttu-id="14a52-114">**Definir el comportamiento de suma parcial para miembros individuales**</span><span class="sxs-lookup"><span data-stu-id="14a52-114">**Define semiadditive behavior for individual members**</span></span>  
 <span data-ttu-id="14a52-115">Habilita el comportamiento de suma parcial y especifica la función de agregación de suma parcial para medidas específicas.</span><span class="sxs-lookup"><span data-stu-id="14a52-115">Enables semi-additive behavior and specifies the semi-additive aggregation function for specific measures.</span></span> <span data-ttu-id="14a52-116">La función de agregación se aplica a todas las dimensiones a las que se hace referencia en el grupo de medida que contiene la medida.</span><span class="sxs-lookup"><span data-stu-id="14a52-116">The aggregation function applies to all dimensions that are referenced by the measure group that contains the measure.</span></span>  
  
 <span data-ttu-id="14a52-117">**Cuantas**</span><span class="sxs-lookup"><span data-stu-id="14a52-117">**Measures**</span></span>  
 <span data-ttu-id="14a52-118">Muestra el nombre de la medida que contiene el cubo.</span><span class="sxs-lookup"><span data-stu-id="14a52-118">Displays the name of a measure contained by the cube.</span></span>  
  
 <span data-ttu-id="14a52-119">**Función de suma parcial**</span><span class="sxs-lookup"><span data-stu-id="14a52-119">**Semiadditive Function**</span></span>  
 <span data-ttu-id="14a52-120">Seleccione la función de agregación para la medida seleccionada.</span><span class="sxs-lookup"><span data-stu-id="14a52-120">Select the aggregation function for the selected measure.</span></span> <span data-ttu-id="14a52-121">En la tabla siguiente se enumeran las funciones de agregación disponibles.</span><span class="sxs-lookup"><span data-stu-id="14a52-121">The following table lists the aggregation functions that are available.</span></span>  
  
|<span data-ttu-id="14a52-122">Value</span><span class="sxs-lookup"><span data-stu-id="14a52-122">Value</span></span>|<span data-ttu-id="14a52-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="14a52-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14a52-124">**AverageOfChildren**</span><span class="sxs-lookup"><span data-stu-id="14a52-124">**AverageOfChildren**</span></span>|<span data-ttu-id="14a52-125">Se agrega devolviendo el promedio de los miembros secundarios de la medida.</span><span class="sxs-lookup"><span data-stu-id="14a52-125">Aggregated by returning the average of the measure's children.</span></span>|  
|`ByAccount`|<span data-ttu-id="14a52-126">Se agrega mediante la función de agregación asociada con el tipo de cuenta especificado de un atributo en una dimensión de cuentas.</span><span class="sxs-lookup"><span data-stu-id="14a52-126">Aggregated by the aggregation function associated with the specified account type of an attribute in an account dimension.</span></span>|  
|`Count`|<span data-ttu-id="14a52-127">Se agrega mediante la función `Count`.</span><span class="sxs-lookup"><span data-stu-id="14a52-127">Aggregated using the `Count` function.</span></span>|  
|`DistinctCount`|<span data-ttu-id="14a52-128">Se agrega mediante la función `DistinctCount`.</span><span class="sxs-lookup"><span data-stu-id="14a52-128">Aggregated using the `DistinctCount` function.</span></span>|  
|<span data-ttu-id="14a52-129">**FirstChild**</span><span class="sxs-lookup"><span data-stu-id="14a52-129">**FirstChild**</span></span>|<span data-ttu-id="14a52-130">Se agrega devolviendo el primer miembro secundario de la medida en una dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="14a52-130">Aggregated by returning the measure's first child member over a time dimension.</span></span>|  
|<span data-ttu-id="14a52-131">**FirstNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="14a52-131">**FirstNonEmpty**</span></span>|<span data-ttu-id="14a52-132">Se agrega devolviendo el primer miembro no vacío de la medida en una dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="14a52-132">Aggregated by returning the measure's first nonempty member over a time dimension.</span></span>|  
|<span data-ttu-id="14a52-133">**LastChild**</span><span class="sxs-lookup"><span data-stu-id="14a52-133">**LastChild**</span></span>|<span data-ttu-id="14a52-134">Se agrega devolviendo el último miembro secundario de la medida en una dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="14a52-134">Aggregated by returning the measure's last child member over a time dimension.</span></span>|  
|<span data-ttu-id="14a52-135">**LastNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="14a52-135">**LastNonEmpty**</span></span>|<span data-ttu-id="14a52-136">Se agrega devolviendo el último miembro no vacío de la medida en una dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="14a52-136">Aggregated by returning the measure's last nonempty member over a time dimension.</span></span>|  
|`Max`|<span data-ttu-id="14a52-137">Se agrega mediante la función `Max`.</span><span class="sxs-lookup"><span data-stu-id="14a52-137">Aggregated using the `Max` function.</span></span>|  
|`Min`|<span data-ttu-id="14a52-138">Se agrega mediante la función `Min`.</span><span class="sxs-lookup"><span data-stu-id="14a52-138">Aggregated using the `Min` function.</span></span>|  
|<span data-ttu-id="14a52-139">**None**</span><span class="sxs-lookup"><span data-stu-id="14a52-139">**None**</span></span>|<span data-ttu-id="14a52-140">No se realiza ningún tipo de agregación.</span><span class="sxs-lookup"><span data-stu-id="14a52-140">No aggregation performed.</span></span>|  
|`Sum`|<span data-ttu-id="14a52-141">Se agrega mediante la función `Sum`.</span><span class="sxs-lookup"><span data-stu-id="14a52-141">Aggregated using the `Sum` function.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="14a52-142">Las selecciones realizadas para esta opción solo se aplican si se ha seleccionado **Define semiadditive behavior for individual members (Definir el comportamiento de suma parcial para miembros individuales)** .</span><span class="sxs-lookup"><span data-stu-id="14a52-142">Selections made for this option apply only if **Define semiadditive behavior for individual members** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a52-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14a52-143">See Also</span></span>  
 <span data-ttu-id="14a52-144">[Asistente de Business Intelligence (ayuda F1)](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="14a52-144">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="14a52-145">[Diseñador de cubos &#40;Analysis Services de datos multidimensionales&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="14a52-145">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="14a52-146">Diseñador de dimensiones &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="14a52-146">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
