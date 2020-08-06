---
title: Cuadro de diálogo Análisis de impacto (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.impactanalysisdialog.f1
ms.assetid: 208268eb-4e14-44db-9c64-6f74b776adb6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e47ab806b9bd10afc812113b69fe0849437068b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744422"
---
# <a name="impact-analysis-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="74cf8-102">Cuadro de diálogo Análisis de impacto (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="74cf8-102">Impact Analysis Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="74cf8-103">Use el cuadro de diálogo **Análisis de impacto** en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] y [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para identificar y, opcionalmente, procesar objetos dependientes que se ven afectados si se procesan los objetos enumerados en el cuadro de diálogo **Proceso** .</span><span class="sxs-lookup"><span data-stu-id="74cf8-103">Use the **Impact Analysis** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to identify and optionally process dependent objects that are affected if the objects listed in the **Process** dialog box are processed.</span></span> <span data-ttu-id="74cf8-104">Para mostrar el cuadro de diálogo **Análisis de impacto** , haga clic en **Análisis de impacto** en el cuadro de diálogo **Proceso** .</span><span class="sxs-lookup"><span data-stu-id="74cf8-104">You can display the **Impact Analysis** dialog box by clicking **Impact Analysis** from the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74cf8-105">Un objeto aparecerá más de una vez si se ve afectado de más de una forma.</span><span class="sxs-lookup"><span data-stu-id="74cf8-105">An object appears more than once if it is affected in more than one way.</span></span>  
  
## <a name="options"></a><span data-ttu-id="74cf8-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="74cf8-106">Options</span></span>  
 <span data-ttu-id="74cf8-107">**Lista de objetos**</span><span class="sxs-lookup"><span data-stu-id="74cf8-107">**Object list**</span></span>  
 <span data-ttu-id="74cf8-108">Muestra una lista de objetos dependientes en una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="74cf8-108">Displays a list of dependent objects in a grid.</span></span> <span data-ttu-id="74cf8-109">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="74cf8-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="74cf8-110">**Nombre de objeto**</span><span class="sxs-lookup"><span data-stu-id="74cf8-110">**Object Name**</span></span>  
 <span data-ttu-id="74cf8-111">Muestra el nombre del objeto dependiente que puede ser necesario procesar.</span><span class="sxs-lookup"><span data-stu-id="74cf8-111">Displays the name of the dependent object that may need to be processed.</span></span> <span data-ttu-id="74cf8-112">El icono que se muestra a la izquierda del nombre indica el tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="74cf8-112">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="74cf8-113">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="74cf8-113">**Type**</span></span>  
 <span data-ttu-id="74cf8-114">Muestra el tipo del objeto dependiente que puede ser necesario procesar.</span><span class="sxs-lookup"><span data-stu-id="74cf8-114">Displays the type of dependent object that may need to be processed.</span></span>  
  
 <span data-ttu-id="74cf8-115">**Tipo de impacto**</span><span class="sxs-lookup"><span data-stu-id="74cf8-115">**Impact Type**</span></span>  
 <span data-ttu-id="74cf8-116">Muestra el efecto que tiene sobre el objeto dependiente el procesamiento de los objetos del cuadro de diálogo **Proceso** .</span><span class="sxs-lookup"><span data-stu-id="74cf8-116">Displays the effect that processing the objects in the **Process** dialog box has on the dependent object.</span></span> <span data-ttu-id="74cf8-117">En la tabla siguiente se enumeran los posibles efectos del procesamiento y se indica si se origina una advertencia o un error.</span><span class="sxs-lookup"><span data-stu-id="74cf8-117">The following table lists the possible effects of processing and notes whether each one results in a warning or an error.</span></span>  
  
|<span data-ttu-id="74cf8-118">Impacto</span><span class="sxs-lookup"><span data-stu-id="74cf8-118">Impact</span></span>|<span data-ttu-id="74cf8-119">Message</span><span class="sxs-lookup"><span data-stu-id="74cf8-119">Message</span></span>|  
|------------|-------------|  
|<span data-ttu-id="74cf8-120">El objeto se desactivará (no se procesa)</span><span class="sxs-lookup"><span data-stu-id="74cf8-120">Object will be cleared (unprocessed)</span></span>|<span data-ttu-id="74cf8-121">Advertencia</span><span class="sxs-lookup"><span data-stu-id="74cf8-121">Warning</span></span>|  
|<span data-ttu-id="74cf8-122">El objeto podría no ser válido</span><span class="sxs-lookup"><span data-stu-id="74cf8-122">Object would be invalid</span></span>|<span data-ttu-id="74cf8-123">Error</span><span class="sxs-lookup"><span data-stu-id="74cf8-123">Error</span></span>|  
|<span data-ttu-id="74cf8-124">La agregación podría eliminarse</span><span class="sxs-lookup"><span data-stu-id="74cf8-124">Aggregation would be dropped</span></span>|<span data-ttu-id="74cf8-125">Advertencia</span><span class="sxs-lookup"><span data-stu-id="74cf8-125">Warning</span></span>|  
|<span data-ttu-id="74cf8-126">La agregación flexible podría eliminarse</span><span class="sxs-lookup"><span data-stu-id="74cf8-126">Flexible aggregation would be dropped</span></span>|<span data-ttu-id="74cf8-127">Advertencia</span><span class="sxs-lookup"><span data-stu-id="74cf8-127">Warning</span></span>|  
|<span data-ttu-id="74cf8-128">Los índices se eliminarán</span><span class="sxs-lookup"><span data-stu-id="74cf8-128">Indexes will be dropped</span></span>|<span data-ttu-id="74cf8-129">Advertencia</span><span class="sxs-lookup"><span data-stu-id="74cf8-129">Warning</span></span>|  
|<span data-ttu-id="74cf8-130">Los objetos que no son secundarios se procesarán</span><span class="sxs-lookup"><span data-stu-id="74cf8-130">Non-child object will be processed</span></span>|<span data-ttu-id="74cf8-131">Advertencia</span><span class="sxs-lookup"><span data-stu-id="74cf8-131">Warning</span></span>|  
  
 <span data-ttu-id="74cf8-132">**Objeto de proceso**</span><span class="sxs-lookup"><span data-stu-id="74cf8-132">**Process Object**</span></span>  
 <span data-ttu-id="74cf8-133">Seleccione los objetos dependientes que desea procesar en la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="74cf8-133">Select the dependent objects that you want to process with the processing operation.</span></span> <span data-ttu-id="74cf8-134">Los objetos dependientes que no se seleccionen deberán procesarse después de finalizar la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="74cf8-134">Dependent objects that are not selected must be processed after the processing operation is finished.</span></span> <span data-ttu-id="74cf8-135">En caso contrario, no se podrán utilizar.</span><span class="sxs-lookup"><span data-stu-id="74cf8-135">Otherwise, they cannot be used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74cf8-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74cf8-136">See Also</span></span>  
 <span data-ttu-id="74cf8-137">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="74cf8-137">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="74cf8-138">Cuadro de diálogo procesar &#40;Analysis Services-datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="74cf8-138">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
