---
title: Especificar clave y tipo de dimensión (Asistente para dimensiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionkeyandtype.f1
ms.assetid: d7d5db55-36c3-45f6-ade3-29aa516589c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc08584ed12de8597b8289fd223cc47945d7d087
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675558"
---
# <a name="specify-dimension-key-and-type-dimension-wizard"></a><span data-ttu-id="57d8c-102">Especificar clave y tipo de dimensión (Asistente para dimensiones)</span><span class="sxs-lookup"><span data-stu-id="57d8c-102">Specify Dimension Key and Type (Dimension Wizard)</span></span>
  <span data-ttu-id="57d8c-103">Use la página **Especificar clave y tipo de dimensión** para definir el atributo clave de la dimensión y para indicar si es una dimensión variable lenta (SCD).</span><span class="sxs-lookup"><span data-stu-id="57d8c-103">Use the **Specify Dimension Key and Type** page to define the key attribute of the dimension and to indicate whether the dimension is a slowly changing dimension (SCD).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="57d8c-104"> Esta página se muestra solo si ha seleccionado **Generar la dimensión sin un origen de datos** en la página **Seleccionar método de generación** y si ha seleccionado **Dimensión estándar** en la página **Seleccionar el tipo de dimensión** .</span><span class="sxs-lookup"><span data-stu-id="57d8c-104">This page is displayed only if you selected **Build the dimension without using a data source** on the **Select Build Method** page and if you selected **Standard dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="57d8c-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="57d8c-105">Options</span></span>  
 <span data-ttu-id="57d8c-106">**Atributo clave**</span><span class="sxs-lookup"><span data-stu-id="57d8c-106">**Key attribute**</span></span>  
 <span data-ttu-id="57d8c-107">Seleccione el atributo que será el atributo clave para la dimensión.</span><span class="sxs-lookup"><span data-stu-id="57d8c-107">Select the attribute that will be the key attribute for the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="57d8c-108">Si no se ha definido ningún atributo para la dimensión, el único valor disponible para esta opción es **Crear atributo clave automáticamente.**</span><span class="sxs-lookup"><span data-stu-id="57d8c-108">If no attributes have been defined for the dimension, the only value available for this option is **Create key attribute automatically.**</span></span> <span data-ttu-id="57d8c-109">Este valor no está disponible si se define algún atributo para la dimensión.</span><span class="sxs-lookup"><span data-stu-id="57d8c-109">This value is not available if any attributes are defined for the dimension.</span></span>  
  
 <span data-ttu-id="57d8c-110">**Es una dimensión variable**</span><span class="sxs-lookup"><span data-stu-id="57d8c-110">**This is a changing dimension**</span></span>  
 <span data-ttu-id="57d8c-111">Seleccione para indicar que la dimensión es una dimensión variable lenta.</span><span class="sxs-lookup"><span data-stu-id="57d8c-111">Select to indicate that the dimension is a slowly changing dimension.</span></span> <span data-ttu-id="57d8c-112">Al seleccionar esta opción se crean columnas y atributos adicionales que se pueden utilizar para realizar un seguimiento del movimiento de los miembros dentro de las jerarquías de la dimensión a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="57d8c-112">Selecting this option will create additional columns and attributes that can be used to track the movement of members within the hierarchies of the dimension over time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d8c-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57d8c-113">See Also</span></span>  
 <span data-ttu-id="57d8c-114">[Asistente para dimensiones (ayuda F1)](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="57d8c-114">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="57d8c-115">[Dimensiones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="57d8c-115">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="57d8c-116">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="57d8c-116">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
