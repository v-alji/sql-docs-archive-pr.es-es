---
title: Revisar el uso de agregaciones (Asistente para optimización basado en el uso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.reviewaggregationusage.f1
ms.assetid: 49ce2094-c4dc-4e46-8cef-c17c5db084ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ef9f900e64858515db226d1f9b864874a4ba827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669924"
---
# <a name="review-aggregation-usage-usage-based-optimiation-wizard"></a><span data-ttu-id="d1e88-102">Revisar el uso de agregaciones (Asistente para optimización basada en el uso)</span><span class="sxs-lookup"><span data-stu-id="d1e88-102">Review Aggregation Usage (Usage-Based Optimiation Wizard)</span></span>
  <span data-ttu-id="d1e88-103">Utilice la página **Revisar el uso de agregaciones** para configurar el uso de agregaciones.</span><span class="sxs-lookup"><span data-stu-id="d1e88-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d1e88-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="d1e88-104">Options</span></span>  
 <span data-ttu-id="d1e88-105">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="d1e88-105">**Default**</span></span>  
 <span data-ttu-id="d1e88-106">Seleccione esta opción para establecer como predeterminada la configuración del uso de agregaciones del atributo.</span><span class="sxs-lookup"><span data-stu-id="d1e88-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="d1e88-107">Esta configuración permite que el diseñador aplique una regla predeterminada basada en el tipo de atributo y dimensión.</span><span class="sxs-lookup"><span data-stu-id="d1e88-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 <span data-ttu-id="d1e88-108">**Completa**</span><span class="sxs-lookup"><span data-stu-id="d1e88-108">**Full**</span></span>  
 <span data-ttu-id="d1e88-109">Seleccione esta opción para establecer la configuración del uso de agregaciones del atributo en Full.</span><span class="sxs-lookup"><span data-stu-id="d1e88-109">Select to set the aggregation usage setting for the attribute to Full.</span></span> <span data-ttu-id="d1e88-110">Con esta configuración es necesario que cada agregación del cubo incluya ese atributo o un atributo relacionado que tenga un valor inferior en la cadena de atributos.</span><span class="sxs-lookup"><span data-stu-id="d1e88-110">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="d1e88-111">Se recomienda no establecer la configuración del uso de agregaciones en Full cuando un atributo contiene muchos miembros.</span><span class="sxs-lookup"><span data-stu-id="d1e88-111">The Full aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="d1e88-112">Cuando la configuración se ha especificado para varios atributos o atributos con varios miembros, es posible que esta configuración impida que se diseñen las agregaciones debido a un tamaño excesivo.</span><span class="sxs-lookup"><span data-stu-id="d1e88-112">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="d1e88-113">**None**</span><span class="sxs-lookup"><span data-stu-id="d1e88-113">**None**</span></span>  
 <span data-ttu-id="d1e88-114">Seleccione esta opción para establecer la configuración del uso de agregaciones del atributo en None.</span><span class="sxs-lookup"><span data-stu-id="d1e88-114">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="d1e88-115">Con esta configuración ninguna agregación del cubo puede incluir el atributo.</span><span class="sxs-lookup"><span data-stu-id="d1e88-115">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 <span data-ttu-id="d1e88-116">**Sin restricciones**</span><span class="sxs-lookup"><span data-stu-id="d1e88-116">**Unrestricted**</span></span>  
 <span data-ttu-id="d1e88-117">Seleccione esta opción para establecer la configuración del uso de agregaciones del atributo en Unrestricted.</span><span class="sxs-lookup"><span data-stu-id="d1e88-117">Select to set the aggregation usage setting for the attribute to Unrestricted.</span></span> <span data-ttu-id="d1e88-118">Esta configuración impide que se coloquen las restricciones en el diseñador de agregaciones.</span><span class="sxs-lookup"><span data-stu-id="d1e88-118">By using this setting, no restrictions are put on the aggregation designer.</span></span> <span data-ttu-id="d1e88-119">Sin embargo, el atributo todavía se tiene que evaluar para determinar si es un candidato importante de la agregación.</span><span class="sxs-lookup"><span data-stu-id="d1e88-119">However, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="d1e88-120">**Set All to Default**</span><span class="sxs-lookup"><span data-stu-id="d1e88-120">**Set All to Default**</span></span>  
 <span data-ttu-id="d1e88-121">Seleccione esta opción para establecer como predeterminada la configuración del uso de agregaciones de todos atributos.</span><span class="sxs-lookup"><span data-stu-id="d1e88-121">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e88-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1e88-122">See Also</span></span>  
 <span data-ttu-id="d1e88-123">[Asistente para diseñar agregaciones (ayuda F1)](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="d1e88-123">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="d1e88-124">Analysis Services asistentes &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="d1e88-124">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
