---
title: Crear una dimensión de tipo moneda | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], currency
- currency [Analysis Services]
- converting currency
- currency dimensions [Analysis Services]
ms.assetid: b1f037d1-ce47-4e47-a1c2-5ec9e781cff6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91123fb5fda898e90056057114295335fbd1d32c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745456"
---
# <a name="create-a-currency-type-dimension"></a><span data-ttu-id="924e7-102">Crear una dimensión de tipo moneda</span><span class="sxs-lookup"><span data-stu-id="924e7-102">Create a Currency type Dimension</span></span>
  <span data-ttu-id="924e7-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , una dimensión de tipo moneda es una dimensión cuyos atributos representan una lista de monedas para la elaboración de informes financieros.</span><span class="sxs-lookup"><span data-stu-id="924e7-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a currency type dimension is a dimension whose attributes represent a list of currencies for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="924e7-104">Una dimensión de moneda permite agregar funciones de conversión de moneda a un cubo en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="924e7-104">A currency dimension lets you add currency conversion capabilities to a cube in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="924e7-105">Para agregar conversión de moneda a un cubo, se utiliza el Asistente de Business Intelligence para definir un script de expresiones multidimensionales (MDX) que convierte medidas de moneda en valores adecuados a la configuración regional de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="924e7-105">To add currency conversion to a cube, you use the Business Intelligence Wizard define a Multidimensional Expressions (MDX) script command that converts currency measures to values that are appropriate for the locale of the client application.</span></span> <span data-ttu-id="924e7-106">Para crear el script MDX, el Asistente de Business Intelligence necesita la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="924e7-106">To create this MDX script, the Business Intelligence Wizard needs the following information:</span></span>  
  
-   <span data-ttu-id="924e7-107">Una dimensión de moneda que representa las monedas de origen.</span><span class="sxs-lookup"><span data-stu-id="924e7-107">A currency dimension that represents source currencies.</span></span> <span data-ttu-id="924e7-108">(Esta dimensión es la dimensión de moneda de origen.)</span><span class="sxs-lookup"><span data-stu-id="924e7-108">(This dimension is the source currency dimension.)</span></span>  
  
-   <span data-ttu-id="924e7-109">Se utilizará un grupo de medida que representa las tasas de cambio.</span><span class="sxs-lookup"><span data-stu-id="924e7-109">A measure group that represents the exchange rates that will be used.</span></span>  
  
 <span data-ttu-id="924e7-110">A partir de esta información, el Asistente de Business Intelligence diseña un proceso de conversión de moneda que identifica la dimensión de moneda de destino adecuada (la dimensión de moneda que representa las monedas de destino).</span><span class="sxs-lookup"><span data-stu-id="924e7-110">From this information, the Business Intelligence Wizard will design a currency conversion process that identifies the appropriate destination currency dimension (the currency dimension that represents destination currencies).</span></span> <span data-ttu-id="924e7-111">En función del número de conversiones de moneda que necesite la solución de Business Intelligence, el Asistente de Business Intelligence puede definir varias dimensiones de moneda de destino.</span><span class="sxs-lookup"><span data-stu-id="924e7-111">Depending on the number of currency conversions that your business intelligence solution requires, the Business Intelligence Wizard can define multiple destination currency dimensions.</span></span> <span data-ttu-id="924e7-112">Para más información sobre cómo definir conversiones de moneda, vea [Conversiones de moneda &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="924e7-112">For more information about defining currency conversions, see [Currency Conversions &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span></span>  
  
 <span data-ttu-id="924e7-113">Para identificar una dimensión como dimensión de moneda, establezca la propiedad `Type` de la dimensión en `Currency`.</span><span class="sxs-lookup"><span data-stu-id="924e7-113">To identify a dimension as a currency dimension, set the `Type` property of the dimension to `Currency`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="924e7-114">Estructura de dimensión</span><span class="sxs-lookup"><span data-stu-id="924e7-114">Dimension Structure</span></span>  
 <span data-ttu-id="924e7-115">Una dimensión de moneda contiene como mínimo un atributo clave que identifica monedas específicas en la tabla de dimensión para la dimensión de moneda.</span><span class="sxs-lookup"><span data-stu-id="924e7-115">A currency dimension contains, at least, a key attribute identifying individual currencies in the dimension table for the currency dimension.</span></span> <span data-ttu-id="924e7-116">El valor del atributo clave es diferente en las dimensiones de moneda de origen y de destino:</span><span class="sxs-lookup"><span data-stu-id="924e7-116">The value of the key attribute is different in both source and destination currency dimensions:</span></span>  
  
-   <span data-ttu-id="924e7-117">Para identificar un atributo como atributo clave de una dimensión de moneda de origen, establezca la propiedad `Type` del atributo en `CurrencySource`.</span><span class="sxs-lookup"><span data-stu-id="924e7-117">To identify an attribute as the key attribute of a source currency dimension, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="924e7-118">Para identificar un atributo como atributo de clave de una dimensión de moneda de destino, establezca la propiedad `Type` del atributo en `CurrencyDestination`.</span><span class="sxs-lookup"><span data-stu-id="924e7-118">To identify an attribute as the destination currency dimension, set the `Type` property of the attribute to `CurrencyDestination`.</span></span>  
  
 <span data-ttu-id="924e7-119">Para fines de elaboración de informes, tanto las dimensiones de moneda de origen como de destino pueden incluir también los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="924e7-119">For reporting purposes, both source and destination currency dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="924e7-120">Un atributo de nombre de moneda</span><span class="sxs-lookup"><span data-stu-id="924e7-120">A currency name attribute.</span></span>  
  
     <span data-ttu-id="924e7-121">Para identificar un atributo como atributo de nombre de moneda, establezca la propiedad `Type` del atributo en `CurrencyName`.</span><span class="sxs-lookup"><span data-stu-id="924e7-121">To identify an attribute as a currency name attribute, set the `Type` property of the attribute to `CurrencyName`.</span></span>  
  
-   <span data-ttu-id="924e7-122">Un atributo de origen de moneda</span><span class="sxs-lookup"><span data-stu-id="924e7-122">A currency source attribute.</span></span>  
  
     <span data-ttu-id="924e7-123">Para identificar un atributo como atributo de origen de moneda, establezca la propiedad `Type` del atributo en `CurrencySource`.</span><span class="sxs-lookup"><span data-stu-id="924e7-123">To identify an attribute as a currency source attribute, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="924e7-124">Un código de moneda ISO (International Standards Organization)</span><span class="sxs-lookup"><span data-stu-id="924e7-124">A currency International Standards Organization (ISO) code.</span></span>  
  
     <span data-ttu-id="924e7-125">Para identificar un atributo como atributo de código ISO de moneda, establezca la propiedad `Type` del atributo en `CurrencyIsoCode`.</span><span class="sxs-lookup"><span data-stu-id="924e7-125">To identify an attribute as a currency ISO code attribute, set the `Type` property of the attribute to `CurrencyIsoCode`.</span></span>  
  
 <span data-ttu-id="924e7-126">Para obtener más información sobre tipos de atributo, vea [Configurar tipos de atributos](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="924e7-126">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="defining-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="924e7-127">Definir la inteligencia de cuentas mediante el Asistente de Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="924e7-127">Defining Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="924e7-128">Tras definir una dimensión de cuenta y agregar dicha dimensión a un cubo, puede utilizar el Asistente de Business Intelligence para agregar a la dimensión características de inteligencia de cuentas, como la identificación y asignación de tipos de cuentas.</span><span class="sxs-lookup"><span data-stu-id="924e7-128">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to add account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="924e7-129">Para obtener más información, vea [Agregar inteligencia de cuentas a una dimensión](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="924e7-129">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="924e7-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="924e7-130">See Also</span></span>  
 <span data-ttu-id="924e7-131">[Atributos y jerarquías de atributos](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="924e7-131">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="924e7-132">[Asistente de Business Intelligence (ayuda F1)](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="924e7-132">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="924e7-133">Tipos de dimensiones</span><span class="sxs-lookup"><span data-stu-id="924e7-133">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
