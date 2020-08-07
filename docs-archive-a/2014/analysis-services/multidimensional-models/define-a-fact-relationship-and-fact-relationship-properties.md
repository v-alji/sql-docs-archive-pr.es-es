---
title: Definir una relación de hechos y propiedades de la relación de hechos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact dimensions [Analysis Services]
ms.assetid: d8e41724-da77-4ac1-bc42-956b5d91ea5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 15f67a4bdf699bbc6443fc76ce54bcfb35831827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745443"
---
# <a name="define-a-fact-relationship-and-fact-relationship-properties"></a><span data-ttu-id="c862a-102">Definir relaciones de hechos y propiedades de las relaciones de hechos</span><span class="sxs-lookup"><span data-stu-id="c862a-102">Define a Fact Relationship and Fact Relationship Properties</span></span>
  <span data-ttu-id="c862a-103">Al definir una nueva dimensión de cubo o un nuevo grupo de medida, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] intentará detectar si existe una relación de dimensión de hechos y, a continuación, establecerá la configuración de uso de la dimensión en `Fact`.</span><span class="sxs-lookup"><span data-stu-id="c862a-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a fact dimension relationship exists and then set the dimension usage setting to `Fact`.</span></span> <span data-ttu-id="c862a-104">Puede ver o modificar una relación de dimensión de hechos en la pestaña **Uso de dimensiones** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="c862a-104">You can view or edit a fact dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="c862a-105">La relación de hechos entre una dimensión y un grupo de medida presenta las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="c862a-105">The fact relationship between a dimension and a measure group has the following constraints:</span></span>  
  
-   <span data-ttu-id="c862a-106">Una dimensión de cubo solamente puede tener una relación de hechos para un determinado grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="c862a-106">A cube dimension can have only one fact relationship to a particular measure group.</span></span>  
  
-   <span data-ttu-id="c862a-107">Una dimensión de cubo puede tener relaciones de hechos independientes con varios grupos de medida.</span><span class="sxs-lookup"><span data-stu-id="c862a-107">A cube dimension can have separate fact relationships to multiple measure groups.</span></span>  
  
-   <span data-ttu-id="c862a-108">El atributo de granularidad de la relación debe ser el atributo clave (como Transaction Number) de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="c862a-108">The granularity attribute for the relationship must be the key attribute (such as Transaction Number) for the dimension.</span></span> <span data-ttu-id="c862a-109">De este modo se crea una relación de uno a uno entre la dimensión y los hechos de la tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="c862a-109">This creates a one-to-one relationship between the dimension and facts in the fact table.</span></span>  
  
  
