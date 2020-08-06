---
title: Especificar recuentos de objetos (Asistente para optimización basada en el uso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 306c7c25-ae24-4852-ab8c-c82f68a4bc1f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 862be19f12308def815a280dba04f42f0cbe6878
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675545"
---
# <a name="specify-object-counts-usage-based-optimization-wizard"></a><span data-ttu-id="8d111-102">Especificar recuentos de objetos (Asistente para optimización basada en el uso)</span><span class="sxs-lookup"><span data-stu-id="8d111-102">Specify Object Counts (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="8d111-103">Use la página **Especificar recuentos de objetos** para calcular automáticamente el recuento de objetos en el cubo o escribir manualmente los recuentos estimados.</span><span class="sxs-lookup"><span data-stu-id="8d111-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="8d111-104">El Asistente para optimización basada en el uso utiliza los recuentos de objetos para estimar los requisitos de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="8d111-104">The Usage-Based Optimization Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d111-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="8d111-105">Options</span></span>  
 <span data-ttu-id="8d111-106">**Objetos de cubo**</span><span class="sxs-lookup"><span data-stu-id="8d111-106">**Cube Objects**</span></span>  
 <span data-ttu-id="8d111-107">Muestra las dimensiones y los atributos del cubo.</span><span class="sxs-lookup"><span data-stu-id="8d111-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="8d111-108">Solo se muestran los atributos que no tienen la `AggregationUsage` propiedad establecida en None en la página **revisar el uso de agregaciones** del asistente, ya que son los únicos atributos que necesitan que se especifiquen los recuentos.</span><span class="sxs-lookup"><span data-stu-id="8d111-108">Only the attributes that do not have their `AggregationUsage` property set to None in the **Review Aggregation Usage** page of the wizard are shown because those are the only attributes that need counts specified.</span></span>  
  
 <span data-ttu-id="8d111-109">**Recuento estimado**</span><span class="sxs-lookup"><span data-stu-id="8d111-109">**Estimated count**</span></span>  
 <span data-ttu-id="8d111-110">Muestra el número estimado de filas en el grupo de medida y los recuentos estimados de miembros del atributo en las dimensiones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="8d111-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="8d111-111">Puede escribir un valor para utilizarlo como recuento estimado o calcular los valores estimados del recuento.</span><span class="sxs-lookup"><span data-stu-id="8d111-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="8d111-112">Para calcular los valores de recuento, escriba 0 en el campo y luego haga clic en **Recuento**.</span><span class="sxs-lookup"><span data-stu-id="8d111-112">To calculate the count values, type 0 in the field and then click **Count**.</span></span> <span data-ttu-id="8d111-113">Los campos que muestren un recuento no están actualizados.</span><span class="sxs-lookup"><span data-stu-id="8d111-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="8d111-114">**Número de particiones**</span><span class="sxs-lookup"><span data-stu-id="8d111-114">**Partition count**</span></span>  
 <span data-ttu-id="8d111-115">(Opcional) Escriba el número estimado de filas en el grupo de medida y los recuentos estimados de miembros del atributo en las particiones.</span><span class="sxs-lookup"><span data-stu-id="8d111-115">(Optional) Type the estimated number of rows in the measure group and the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="8d111-116">**Recuento**</span><span class="sxs-lookup"><span data-stu-id="8d111-116">**Count**</span></span>  
 <span data-ttu-id="8d111-117">Calcula y rellena los valores de la columna **Recuento estimado** para todos los campos vacíos.</span><span class="sxs-lookup"><span data-stu-id="8d111-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="8d111-118">Los campos que muestren un recuento no están actualizados.</span><span class="sxs-lookup"><span data-stu-id="8d111-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d111-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d111-119">See Also</span></span>  
 <span data-ttu-id="8d111-120">[Asistente para diseñar agregaciones (ayuda F1)](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="8d111-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="8d111-121">Analysis Services asistentes &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="8d111-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
