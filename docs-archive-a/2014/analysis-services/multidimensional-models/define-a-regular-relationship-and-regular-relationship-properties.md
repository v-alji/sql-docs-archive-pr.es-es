---
title: Definir una relación normal y propiedades de relación normal | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- granularity attribute
- relationships [Analysis Services], regular relationships
ms.assetid: 840280d8-20c3-46c0-99ea-62479469c36b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b4f49e219a85d5577fb1acddfe14e7afd3b105d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676693"
---
# <a name="define-a-regular-relationship-and-regular-relationship-properties"></a><span data-ttu-id="b9cdd-102">Definir relaciones normales y propiedades de las relaciones normales</span><span class="sxs-lookup"><span data-stu-id="b9cdd-102">Define a Regular Relationship and Regular Relationship Properties</span></span>
  <span data-ttu-id="b9cdd-103">Al definir una nueva dimensión de cubo o un nuevo grupo de medida, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] intentará detectar si existe una relación normal y, a continuación, establecerá la configuración de uso de la dimensión en `Regular`.</span><span class="sxs-lookup"><span data-stu-id="b9cdd-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a regular relationship exists and then set the dimension usage setting to `Regular`.</span></span> <span data-ttu-id="b9cdd-104">Puede ver o modificar una relación de dimensión normal en la pestaña **Uso de dimensiones** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="b9cdd-104">You can view or edit a regular dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span>  
  
 <span data-ttu-id="b9cdd-105">Al definir la relación de una dimensión de cubo con un grupo de medida, también se especifica el atributo de granularidad de esa relación.</span><span class="sxs-lookup"><span data-stu-id="b9cdd-105">When you define the relationship of a cube dimension to a measure group, you also specify the granularity attribute for that relationship.</span></span> <span data-ttu-id="b9cdd-106">El atributo de granularidad define el nivel mínimo de detalle disponible en el cubo para dicha dimensión, que suele ser el atributo clave de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="b9cdd-106">The granularity attribute defines the lowest level of detail available in the cube for that dimension, which is generally the key attribute for the dimension.</span></span> <span data-ttu-id="b9cdd-107">Sin embargo, en algunos casos, quizás desee establecer la granularidad de determinada dimensión de cubo de determinado grupo de medida en otra granularidad.</span><span class="sxs-lookup"><span data-stu-id="b9cdd-107">However, sometimes you may want to set the granularity of a particular cube dimension in a particular measure group to a different grain.</span></span> <span data-ttu-id="b9cdd-108">Por ejemplo, si utiliza un grupo de medida Sales Quotas o Budget, quizás desee establecer el atributo de granularidad de la dimensión Time en el atributo Month, no en el atributo Day.</span><span class="sxs-lookup"><span data-stu-id="b9cdd-108">For example, you may want to set the granularity attribute for the Time dimension to the Month attribute instead of to the Day attribute, if you are using a Sales Quotas or a Budget measure group.</span></span> <span data-ttu-id="b9cdd-109">Al especificar que el atributo de granularidad sea distinto del atributo clave, se debe garantizar que los demás atributos de la dimensión estén directa o indirectamente vinculados a este otro atributo por medio de relaciones de atributo.</span><span class="sxs-lookup"><span data-stu-id="b9cdd-109">When you specify the granularity attribute to be an attribute other than the key attribute, you must guarantee that all other attributes in the dimension are directly or indirectly linked to this other attribute through attribute relationships.</span></span> <span data-ttu-id="b9cdd-110">De lo contrario, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no podrá agregar los datos correctamente.</span><span class="sxs-lookup"><span data-stu-id="b9cdd-110">If not, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will be unable to aggregate data correctly.</span></span>  
  
  
