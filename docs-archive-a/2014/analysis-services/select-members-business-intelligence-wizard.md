---
title: Seleccionar miembros (Asistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.memberconversion.f1
ms.assetid: 1a147461-d594-41e7-a41d-09d2d003e1e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd5f184e0d9670725609531b6d0a101f8e7f8647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670622"
---
# <a name="select-members-business-intelligence-wizard"></a><span data-ttu-id="65221-102">Seleccionar miembros (Asistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="65221-102">Select Members (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="65221-103">Utilice la página **Seleccionar miembros** para determinar a qué miembros del Asistente de Business Intelligence se debe aplicar la función de conversión de moneda especificada en la página **Establecer las opciones de conversión de moneda** .</span><span class="sxs-lookup"><span data-stu-id="65221-103">Use the **Select Members** page to determine to which members the Business Intelligence Wizard should apply the currency conversion functionality specified on the **Set Currency Conversion Options** page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65221-104">Esta página no aparece si se ha iniciado el Asistente de Business Intelligence desde el Diseñador de dimensiones o al hacer clic con el botón derecho en una dimensión del Explorador de soluciones de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65221-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="65221-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="65221-105">Options</span></span>  
 <span data-ttu-id="65221-106">**Dimensión de medidas**</span><span class="sxs-lookup"><span data-stu-id="65221-106">**Measures dimension**</span></span>  
 <span data-ttu-id="65221-107">Seleccione esta opción para aplicar la función de conversión de moneda a una o varias medidas del cubo.</span><span class="sxs-lookup"><span data-stu-id="65221-107">Select to apply the currency conversion functionality to one or more measures in the cube.</span></span>  
  
 <span data-ttu-id="65221-108">Si está seleccionada, la cuadrícula muestra las opciones enumeradas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="65221-108">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="65221-109">Opción</span><span class="sxs-lookup"><span data-stu-id="65221-109">Option</span></span>|<span data-ttu-id="65221-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="65221-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="65221-111">**Seleccionar miembros**</span><span class="sxs-lookup"><span data-stu-id="65221-111">**Built-in Measure Types**</span></span>|<span data-ttu-id="65221-112">Seleccione esta opción para incluir la función de conversión de moneda correspondiente a la medida especificada.</span><span class="sxs-lookup"><span data-stu-id="65221-112">Select to include currency conversion functionality for the specified measure.</span></span>|  
|<span data-ttu-id="65221-113">**Cuantas**</span><span class="sxs-lookup"><span data-stu-id="65221-113">**Measures**</span></span>|<span data-ttu-id="65221-114">Seleccione la medida del grupo de medida de tarifas que contiene la tasa de cambio que se va a usar cuando se convierta la medida seleccionada en **Tipos de medida integrados** .</span><span class="sxs-lookup"><span data-stu-id="65221-114">Select the measure from the rate measure group that contains the exchange rate to use when the measure selected in **Built-in Measure Types** is converted.</span></span>|  
  
 <span data-ttu-id="65221-115">**Jerarquía de cuentas**</span><span class="sxs-lookup"><span data-stu-id="65221-115">**Account hierarchy**</span></span>  
 <span data-ttu-id="65221-116">Seleccione esta opción para aplicar la función de conversión de moneda a uno o varios miembros de la jerarquía de cuentas correspondiente a la dimensión de cuenta incluida en el cubo.</span><span class="sxs-lookup"><span data-stu-id="65221-116">Select to apply the currency conversion functionality to one or more members in the account hierarchy of the account dimension included in the cube.</span></span> <span data-ttu-id="65221-117">La jerarquía de cuentas es la jerarquía dentro de la dimensión de cuenta cuya `Type` propiedad se establece en *account*.</span><span class="sxs-lookup"><span data-stu-id="65221-117">The account hierarchy is the hierarchy within the account dimension whose `Type` property is set to *Account*.</span></span>  
  
 <span data-ttu-id="65221-118">Si está seleccionada, la cuadrícula muestra las opciones enumeradas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="65221-118">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="65221-119">Opción</span><span class="sxs-lookup"><span data-stu-id="65221-119">Option</span></span>|<span data-ttu-id="65221-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="65221-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="65221-121">**Miembro de la cuenta**</span><span class="sxs-lookup"><span data-stu-id="65221-121">**Account Member**</span></span>|<span data-ttu-id="65221-122">Seleccione esta opción para incluir la función de conversión de moneda correspondiente al miembro especificado de la jerarquía de cuentas.</span><span class="sxs-lookup"><span data-stu-id="65221-122">Select to include currency conversion functionality for the specified member of the account hierarchy.</span></span>|  
|<span data-ttu-id="65221-123">**Cuantas**</span><span class="sxs-lookup"><span data-stu-id="65221-123">**Measures**</span></span>|<span data-ttu-id="65221-124">Seleccione la medida del grupo de medida de tarifas que contiene la tasa de cambio que se va a utilizar cuando se conviertan las medidas correspondientes al miembro seleccionado en **Miembro de la cuenta** .</span><span class="sxs-lookup"><span data-stu-id="65221-124">Select the measure from the rate measure group that contains the exchange rate to use when the measures for the member selected in **Account Member** are converted.</span></span>|  
  
 <span data-ttu-id="65221-125">**Jerarquía de cuentas basada en el tipo**</span><span class="sxs-lookup"><span data-stu-id="65221-125">**Account hierarchy based on type**</span></span>  
 <span data-ttu-id="65221-126">Seleccione esta opción para aplicar la función de conversión de moneda a todos los miembros de los atributos de la jerarquía de cuentas, cuya propiedad `Type` esté establecida en un tipo de cuenta especificado.</span><span class="sxs-lookup"><span data-stu-id="65221-126">Select to apply the currency conversion functionality to all members of attributes in the account hierarchy whose `Type` property is set to a specified account type.</span></span>  
  
 <span data-ttu-id="65221-127">Si está seleccionada, la cuadrícula muestra las opciones enumeradas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="65221-127">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="65221-128">Opción</span><span class="sxs-lookup"><span data-stu-id="65221-128">Option</span></span>|<span data-ttu-id="65221-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="65221-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="65221-130">**Tipo de cuenta**</span><span class="sxs-lookup"><span data-stu-id="65221-130">**Account Type**</span></span>|<span data-ttu-id="65221-131">Seleccione esta opción para incluir la función de conversión de moneda correspondiente al tipo de cuenta especificado.</span><span class="sxs-lookup"><span data-stu-id="65221-131">Select to include currency conversion functionality for the specified account type.</span></span>|  
|<span data-ttu-id="65221-132">**Cuantas**</span><span class="sxs-lookup"><span data-stu-id="65221-132">**Measures**</span></span>|<span data-ttu-id="65221-133">Seleccione la medida del grupo de medida de tarifas que contiene la tasa de cambio que se va a utilizar cuando se conviertan los miembros de los atributos utilizando el tipo de cuenta seleccionado en **Tipo de cuenta** .</span><span class="sxs-lookup"><span data-stu-id="65221-133">Select the measure from the rate measure group that contains the exchange rate to use when measures for the members of attributes using the account type selected in **Account Type** are converted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65221-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65221-134">See Also</span></span>  
 <span data-ttu-id="65221-135">[Asistente de Business Intelligence (ayuda F1)](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="65221-135">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="65221-136">[Diseñador de cubos &#40;Analysis Services de datos multidimensionales&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="65221-136">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="65221-137">Diseñador de dimensiones &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="65221-137">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
