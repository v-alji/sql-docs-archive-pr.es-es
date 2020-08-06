---
title: Definir propiedades de jerarquía de cubos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], multilevel
- hierarchies [Analysis Services], cubes
ms.assetid: 819d0a4e-7815-4332-a605-b07ca2ade6ac
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8903a49754357aad9cf24ee63fffa45fbf120e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744402"
---
# <a name="define-cube-hierarchy-properties"></a><span data-ttu-id="63e30-102">Definir propiedades de las jerarquías de cubos</span><span class="sxs-lookup"><span data-stu-id="63e30-102">Define Cube Hierarchy Properties</span></span>
  <span data-ttu-id="63e30-103">Las propiedades de la jerarquía de cubo permiten especificar valores únicos para jerarquías definidas por el usuario en dimensiones de cubo basadas en la misma dimensión de base de datos.</span><span class="sxs-lookup"><span data-stu-id="63e30-103">Cube hierarchy properties enable you to specify unique settings for user-defined hierarchies in cube dimensions based on the same database dimension.</span></span> <span data-ttu-id="63e30-104">En la siguiente tabla se describen las propiedades de una jerarquía de cubo.</span><span class="sxs-lookup"><span data-stu-id="63e30-104">The following table describes the properties of a cube hierarchy.</span></span>  
  
|<span data-ttu-id="63e30-105">Propiedad</span><span class="sxs-lookup"><span data-stu-id="63e30-105">Property</span></span>|<span data-ttu-id="63e30-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="63e30-106">Description</span></span>|  
|--------------|-----------------|  
|`Enabled`|<span data-ttu-id="63e30-107">Determina si está habilitada la jerarquía para la dimensión de cubo.</span><span class="sxs-lookup"><span data-stu-id="63e30-107">Determines whether the hierarchy is enabled for the cube dimension.</span></span>|  
|`HierarchyID`|<span data-ttu-id="63e30-108">Contiene el identificador único de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="63e30-108">Contains the unique identifier (ID) of the hierarchy.</span></span>|  
|`OptimizedState`|<span data-ttu-id="63e30-109">Determina el nivel de optimización que se aplica a la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="63e30-109">Determines the level of optimization that is applied to the hierarchy.</span></span> <span data-ttu-id="63e30-110">Esta propiedad puede tener los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="63e30-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="63e30-111">`FullyOptimized`: La instancia genera índices para la jerarquía, para mejorar el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="63e30-111">`FullyOptimized`: The instance builds indexes for the hierarchy to improve query performance.</span></span> <span data-ttu-id="63e30-112">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="63e30-112">This is the default value.</span></span><br /><br /> <span data-ttu-id="63e30-113">`NotOptimized`: La instancia no genera otros índices.</span><span class="sxs-lookup"><span data-stu-id="63e30-113">`NotOptimized`: The instance does not build additional indexes.</span></span>|  
|`Visible`|<span data-ttu-id="63e30-114">Determina la visibilidad de la jerarquía de cubo.</span><span class="sxs-lookup"><span data-stu-id="63e30-114">Determines the visibility of the cube hierarchy.</span></span> <span data-ttu-id="63e30-115">El valor predeterminado es `True`.</span><span class="sxs-lookup"><span data-stu-id="63e30-115">The default value is `True`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63e30-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63e30-116">See Also</span></span>  
 [<span data-ttu-id="63e30-117">Jerarquías de usuario</span><span class="sxs-lookup"><span data-stu-id="63e30-117">User Hierarchies</span></span>](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md)  
  
  
