---
title: Tipos de dimensión | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- time dimensions [Analysis Services]
- quantitative dimensions [Analysis Services]
- BillOfMaterials dimension [Analysis Services]
- geography dimensions
- utility dimensions [Analysis Services]
- channel dimensions
- dimensions [Analysis Services], types
- products dimensions [Analysis Services]
- account dimensions [Analysis Services]
- organization dimensions
- currency dimensions [Analysis Services]
- rates dimensions
- promotion dimensions
- scenario dimensions [Analysis Services]
- customers dimensions [Analysis Services]
- Type property
ms.assetid: bd3195da-e762-4c98-b643-34c76e842343
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5e0c16a57081aa1d9ed3cc6964d1f17fa7135986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677910"
---
# <a name="dimension-types"></a><span data-ttu-id="4262c-102">Tipos de dimensiones</span><span class="sxs-lookup"><span data-stu-id="4262c-102">Dimension Types</span></span>
  <span data-ttu-id="4262c-103">El valor de la propiedad `Type` proporciona información acerca del contenido de una dimensión al servidor y a las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="4262c-103">The `Type` property setting provides information about the contents of a dimension to server and client applications.</span></span> <span data-ttu-id="4262c-104">En algunos casos, el valor de `Type` solo constituye una guía para las aplicaciones cliente y es opcional.</span><span class="sxs-lookup"><span data-stu-id="4262c-104">In some cases, the `Type` setting only provides guidance for client applications and is optional.</span></span> <span data-ttu-id="4262c-105">En otros casos, como en las dimensiones `Accounts` o `Time`, la configuración de la propiedad `Type` para la dimensión y sus atributos determina comportamientos específicos basados en el servidor y puede que sea necesario implementar ciertos comportamientos en el cubo.</span><span class="sxs-lookup"><span data-stu-id="4262c-105">In other cases, such as `Accounts` or `Time` dimensions, the `Type` property settings for the dimension and its attributes determine specific server-based behaviors and may be required to implement certain behaviors in the cube.</span></span> <span data-ttu-id="4262c-106">Por ejemplo, la propiedad `Type` de una dimensión se puede establecer en `Accounts` para indicar a las aplicaciones cliente que la dimensión estándar contiene atributos de cuenta.</span><span class="sxs-lookup"><span data-stu-id="4262c-106">For example, the `Type` property of a dimension can be set to `Accounts` to indicate to client applications that the standard dimension contains account attributes.</span></span> <span data-ttu-id="4262c-107">Para obtener más información sobre las dimensiones de tiempo, cuenta y moneda, vea [crear una dimensión de tipo de fecha](../multidimensional-models/database-dimensions-create-a-date-type-dimension.md), [crear una cuenta de Finanzas de una dimensión de tipo primario-secundario](../multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md)y [crear una dimensión de tipo moneda](../multidimensional-models/database-dimensions-create-a-currency-type-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="4262c-107">For more information about time, account, and currency dimensions, see [Create a Date type Dimension](../multidimensional-models/database-dimensions-create-a-date-type-dimension.md), [Create a Finance Account of parent-child type Dimension](../multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md), and [Create a Currency type Dimension](../multidimensional-models/database-dimensions-create-a-currency-type-dimension.md).</span></span>  
  
 <span data-ttu-id="4262c-108">El valor predeterminado para el tipo de dimensión es `Regular`, que no realiza suposiciones acerca del contenido de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="4262c-108">The default setting for the dimension type is `Regular`, which makes no assumptions about the contents of the dimension.</span></span> <span data-ttu-id="4262c-109">Se trata del valor predeterminado para todas las dimensiones al definir inicialmente una dimensión, a menos que se especifique `Time` al definir la dimensión mediante el Asistente para Dimensiones.</span><span class="sxs-lookup"><span data-stu-id="4262c-109">This is the default setting for all dimensions when you initially define a dimension unless you specify `Time` when defining the dimension using the Dimension Wizard.</span></span> <span data-ttu-id="4262c-110">También se debe dejar `Regular` como tipo de dimensión si el Asistente para dimensiones no muestra un tipo adecuado para el tipo de dimensión.</span><span class="sxs-lookup"><span data-stu-id="4262c-110">You should also leave `Regular` as the dimension type if the Dimension Wizard does not list an appropriate type for Dimension type.</span></span>  
  
## <a name="available-dimension-types"></a><span data-ttu-id="4262c-111">Tipos de dimensiones disponibles</span><span class="sxs-lookup"><span data-stu-id="4262c-111">Available Dimension Types</span></span>  
 <span data-ttu-id="4262c-112">En la tabla siguiente se describen los tipos de dimensiones disponibles en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4262c-112">The following table describes the dimension types available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="4262c-113">Tipo de dimensión</span><span class="sxs-lookup"><span data-stu-id="4262c-113">Dimension type</span></span>|<span data-ttu-id="4262c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4262c-114">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4262c-115">Normal</span><span class="sxs-lookup"><span data-stu-id="4262c-115">Regular</span></span>|<span data-ttu-id="4262c-116">Dimensión cuyo tipo no se ha establecido en un tipo de dimensión especial.</span><span class="sxs-lookup"><span data-stu-id="4262c-116">A dimension whose type has not been set to a special dimension type.</span></span>|  
|<span data-ttu-id="4262c-117">Time</span><span class="sxs-lookup"><span data-stu-id="4262c-117">Time</span></span>|<span data-ttu-id="4262c-118">Dimensión cuyos atributos representan periodos de tiempo, como años, semestres, trimestres, meses y días.</span><span class="sxs-lookup"><span data-stu-id="4262c-118">A dimension whose attributes represent time periods, such as years, semesters, quarters, months, and days.</span></span>|  
|<span data-ttu-id="4262c-119">Organización</span><span class="sxs-lookup"><span data-stu-id="4262c-119">Organization</span></span>|<span data-ttu-id="4262c-120">Dimensión cuyos atributos representan información organizativa, como empleados o subsidiarias.</span><span class="sxs-lookup"><span data-stu-id="4262c-120">A dimension whose attributes represent organizational information, such as employees or subsidiaries.</span></span>|  
|<span data-ttu-id="4262c-121">Geography</span><span class="sxs-lookup"><span data-stu-id="4262c-121">Geography</span></span>|<span data-ttu-id="4262c-122">Dimensión cuyos atributos representan información geográfica, como ciudades o códigos postales.</span><span class="sxs-lookup"><span data-stu-id="4262c-122">A dimension whose attributes represent geographic information, such as cities or postal codes.</span></span>|  
|<span data-ttu-id="4262c-123">Lista de materiales</span><span class="sxs-lookup"><span data-stu-id="4262c-123">BillOfMaterials</span></span>|<span data-ttu-id="4262c-124">Dimensión cuyos atributos representan información de inventario o de fabricación, como listas de piezas para productos.</span><span class="sxs-lookup"><span data-stu-id="4262c-124">A dimension whose attributes represent inventory or manufacturing information, such as parts lists for products.</span></span>|  
|<span data-ttu-id="4262c-125">Cuentas</span><span class="sxs-lookup"><span data-stu-id="4262c-125">Accounts</span></span>|<span data-ttu-id="4262c-126">Dimensión cuyos atributos representan un gráfico de cuentas para la elaboración de informes financieros.</span><span class="sxs-lookup"><span data-stu-id="4262c-126">A dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>|  
|<span data-ttu-id="4262c-127">Clientes</span><span class="sxs-lookup"><span data-stu-id="4262c-127">Customers</span></span>|<span data-ttu-id="4262c-128">Dimensión cuyos atributos representan información de clientes o de contacto.</span><span class="sxs-lookup"><span data-stu-id="4262c-128">A dimension whose attributes represent customer or contact information.</span></span>|  
|<span data-ttu-id="4262c-129">Productos</span><span class="sxs-lookup"><span data-stu-id="4262c-129">Products</span></span>|<span data-ttu-id="4262c-130">Dimensión cuyos atributos representan información de productos.</span><span class="sxs-lookup"><span data-stu-id="4262c-130">A dimension whose attributes represent product information.</span></span>|  
|<span data-ttu-id="4262c-131">Escenario</span><span class="sxs-lookup"><span data-stu-id="4262c-131">Scenario</span></span>|<span data-ttu-id="4262c-132">Dimensión cuyos atributos representan información de planeación o análisis estratégico.</span><span class="sxs-lookup"><span data-stu-id="4262c-132">A dimension whose attributes represent planning or strategic analysis information.</span></span>|  
|<span data-ttu-id="4262c-133">Cuantitativo</span><span class="sxs-lookup"><span data-stu-id="4262c-133">Quantitative</span></span>|<span data-ttu-id="4262c-134">Dimensión cuyos atributos representan información cuantitativa.</span><span class="sxs-lookup"><span data-stu-id="4262c-134">A dimension whose attributes represent quantitative information.</span></span>|  
|<span data-ttu-id="4262c-135">Utilidad</span><span class="sxs-lookup"><span data-stu-id="4262c-135">Utility</span></span>|<span data-ttu-id="4262c-136">Dimensión cuyos atributos representan información diversa.</span><span class="sxs-lookup"><span data-stu-id="4262c-136">A dimension whose attributes represent miscellaneous information.</span></span>|  
|<span data-ttu-id="4262c-137">Moneda</span><span class="sxs-lookup"><span data-stu-id="4262c-137">Currency</span></span>|<span data-ttu-id="4262c-138">Este tipo de dimensión contiene datos de moneda y metadatos.</span><span class="sxs-lookup"><span data-stu-id="4262c-138">This type of dimension contains currency data and metadata.</span></span>|  
|<span data-ttu-id="4262c-139">Tarifas</span><span class="sxs-lookup"><span data-stu-id="4262c-139">Rates</span></span>|<span data-ttu-id="4262c-140">Dimensión cuyos atributos representan información de tasa de cambio.</span><span class="sxs-lookup"><span data-stu-id="4262c-140">A dimension whose attributes represent currency rate information.</span></span>|  
|<span data-ttu-id="4262c-141">Canal</span><span class="sxs-lookup"><span data-stu-id="4262c-141">Channel</span></span>|<span data-ttu-id="4262c-142">Dimensión cuyos atributos representan información de canal.</span><span class="sxs-lookup"><span data-stu-id="4262c-142">A dimension whose attributes represent channel information.</span></span>|  
|<span data-ttu-id="4262c-143">Promoción</span><span class="sxs-lookup"><span data-stu-id="4262c-143">Promotion</span></span>|<span data-ttu-id="4262c-144">Dimensión cuyos atributos representan información de promociones de marketing.</span><span class="sxs-lookup"><span data-stu-id="4262c-144">A dimension whose attributes represent marketing promotion information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4262c-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4262c-145">See Also</span></span>  
 <span data-ttu-id="4262c-146">[Crear una dimensión usando una tabla existente](../multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="4262c-146">[Create a Dimension by Using an Existing Table](../multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="4262c-147">Dimensiones &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="4262c-147">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
