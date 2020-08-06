---
title: Especificar recuentos de objetos (Asistente para diseñar agregaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 305d9d79-d1ab-4704-a7b5-3283842b3996
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66b972395f86746b2d08df234db8aa0c71d03fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674378"
---
# <a name="specify-object-counts-aggregation-design-wizard"></a><span data-ttu-id="6a25e-102">Especificar recuentos de objetos (Asistente para diseñar agregaciones)</span><span class="sxs-lookup"><span data-stu-id="6a25e-102">Specify Object Counts (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="6a25e-103">Use la página **Especificar recuentos de objetos** para calcular automáticamente el recuento de objetos en el cubo o escribir manualmente los recuentos estimados.</span><span class="sxs-lookup"><span data-stu-id="6a25e-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="6a25e-104">El Asistente para diseñar agregaciones utiliza los recuentos de objetos para estimar los requisitos de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6a25e-104">The Aggregation Design Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6a25e-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="6a25e-105">Options</span></span>  
 <span data-ttu-id="6a25e-106">**Objetos de cubo**</span><span class="sxs-lookup"><span data-stu-id="6a25e-106">**Cube Objects**</span></span>  
 <span data-ttu-id="6a25e-107">Muestra las dimensiones y los atributos del cubo.</span><span class="sxs-lookup"><span data-stu-id="6a25e-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="6a25e-108">Solo se muestran los atributos que no tienen la `AggregationUsage` propiedad establecida `None` en en la página **revisar el uso de agregaciones** del asistente, ya que son los únicos atributos que requieren que se especifiquen los recuentos.</span><span class="sxs-lookup"><span data-stu-id="6a25e-108">Only the attributes that do not have their `AggregationUsage` property set to `None` in the **Review Aggregation Usage** page of the wizard are shown, because those are the only attributes that require the counts to be specified.</span></span>  
  
 <span data-ttu-id="6a25e-109">**Recuento estimado**</span><span class="sxs-lookup"><span data-stu-id="6a25e-109">**Estimated count**</span></span>  
 <span data-ttu-id="6a25e-110">Muestra el número estimado de filas en el grupo de medida y los recuentos estimados de miembros del atributo en las dimensiones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="6a25e-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="6a25e-111">Puede escribir un valor para utilizarlo como recuento estimado o calcular los valores estimados del recuento.</span><span class="sxs-lookup"><span data-stu-id="6a25e-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="6a25e-112">Para calcular los valores de recuento, escriba `0` en el campo y, a continuación, haga clic en **recuento**.</span><span class="sxs-lookup"><span data-stu-id="6a25e-112">To calculate the count values, type `0` in the field and then click **Count**.</span></span> <span data-ttu-id="6a25e-113">Los campos que muestren un recuento no están actualizados.</span><span class="sxs-lookup"><span data-stu-id="6a25e-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="6a25e-114">**Número de particiones**</span><span class="sxs-lookup"><span data-stu-id="6a25e-114">**Partition count**</span></span>  
 <span data-ttu-id="6a25e-115">(Opcional) Escriba el número estimado de filas en el grupo de medida y el tipo de los recuentos estimados de miembros del atributo en las particiones.</span><span class="sxs-lookup"><span data-stu-id="6a25e-115">(Optional) Type the estimated number of rows in the measure group and type the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="6a25e-116">**Recuento**</span><span class="sxs-lookup"><span data-stu-id="6a25e-116">**Count**</span></span>  
 <span data-ttu-id="6a25e-117">Calcula y rellena los valores de la columna **Recuento estimado** para todos los campos vacíos.</span><span class="sxs-lookup"><span data-stu-id="6a25e-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="6a25e-118">Los campos que muestren un recuento no están actualizados.</span><span class="sxs-lookup"><span data-stu-id="6a25e-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a25e-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a25e-119">See Also</span></span>  
 <span data-ttu-id="6a25e-120">[Asistente para diseñar agregaciones (ayuda F1)](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="6a25e-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="6a25e-121">Analysis Services asistentes &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="6a25e-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
