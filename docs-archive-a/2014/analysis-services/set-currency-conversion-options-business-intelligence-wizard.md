---
title: Establecer las opciones de conversión de moneda (Asistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.calculationsettings.f1
ms.assetid: a49d4e1f-bdda-4a83-ab4f-ce8c500e1d6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61877deb0bc422d65f977e3fc9de3e678f7d8477
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748299"
---
# <a name="set-currency-conversion-options-business-intelligence-wizard"></a><span data-ttu-id="cb9e8-102">Establecer las opciones de conversión de moneda (Asistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="cb9e8-102">Set Currency Conversion Options (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="cb9e8-103">Use la página **Definir la conversión de moneda** para definir los cálculos de conversión de moneda para un grupo de medida que incluye tasas de cambio.</span><span class="sxs-lookup"><span data-stu-id="cb9e8-103">Use the **Set Currency Conversion** page to define currency conversion calculations for a measure group that contains exchange rates.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb9e8-104">Esta página no aparece si se ha iniciado el Asistente de Business Intelligence desde el Diseñador de dimensiones o al hacer clic con el botón derecho en una dimensión del Explorador de soluciones de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb9e8-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="cb9e8-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="cb9e8-105">Options</span></span>  
 <span data-ttu-id="cb9e8-106">**Seleccione el grupo de medida que incluye las tasas de cambio**</span><span class="sxs-lookup"><span data-stu-id="cb9e8-106">**Select the measure group that contains exchange rates**</span></span>  
 <span data-ttu-id="cb9e8-107">Seleccione el grupo de medida que incluye las tasas de cambio a las que deben hacer referencia los cálculos de conversión de moneda.</span><span class="sxs-lookup"><span data-stu-id="cb9e8-107">Select the measure group that contains the exchange rates that the currency conversion calculations should reference.</span></span>  
  
 <span data-ttu-id="cb9e8-108">**Especifique la moneda dinámica**</span><span class="sxs-lookup"><span data-stu-id="cb9e8-108">**Specify the pivot currency**</span></span>  
 <span data-ttu-id="cb9e8-109">Seleccione el miembro que actuará como moneda dinámica para el grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="cb9e8-109">Select the member that serves as the pivot currency for the measure group.</span></span>  
  
 <span data-ttu-id="cb9e8-110">**Seleccione cómo especificó las tasas de cambio (seleccione una moneda de ejemplo)**</span><span class="sxs-lookup"><span data-stu-id="cb9e8-110">**Select how you entered your exchange rates (select a sample currency)**</span></span>  
 <span data-ttu-id="cb9e8-111">Seleccione un miembro que represente una moneda de ejemplo de la dimensión de moneda para cambiar el texto por las opciones X la moneda dinámica por 1 moneda de ejemplo y X la moneda de ejemplo por 1 moneda dinámica para hacer más evidente la dirección de la tasa de cambio.</span><span class="sxs-lookup"><span data-stu-id="cb9e8-111">Select a member representing a sample currency from the currency dimension to change the text for the X pivot currency per 1 sample currency and X sample currency per 1 pivot currency options to better display the exchange rate direction.</span></span>  
  
 <span data-ttu-id="cb9e8-112">**X la moneda dinámica por 1 moneda de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="cb9e8-112">**X pivot currency per 1 sample currency**</span></span>  
 <span data-ttu-id="cb9e8-113">Seleccione esta opción para indicar que las tasas de cambio del grupo de medida de tarifas representan un multiplicador para la moneda dinámica especificada.</span><span class="sxs-lookup"><span data-stu-id="cb9e8-113">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified pivot currency.</span></span>  
  
 <span data-ttu-id="cb9e8-114">**X la moneda de ejemplo por 1 moneda dinámica**</span><span class="sxs-lookup"><span data-stu-id="cb9e8-114">**X sample currency per 1 pivot currency**</span></span>  
 <span data-ttu-id="cb9e8-115">Seleccione esta opción para indicar que las tasas de cambio del grupo de medida de tarifas representan un multiplicador para la moneda de ejemplo especificada.</span><span class="sxs-lookup"><span data-stu-id="cb9e8-115">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified sample currency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb9e8-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb9e8-116">See Also</span></span>  
 <span data-ttu-id="cb9e8-117">[Asistente de Business Intelligence (ayuda F1)](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="cb9e8-117">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="cb9e8-118">[Diseñador de cubos &#40;Analysis Services de datos multidimensionales&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="cb9e8-118">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="cb9e8-119">Diseñador de dimensiones &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="cb9e8-119">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
