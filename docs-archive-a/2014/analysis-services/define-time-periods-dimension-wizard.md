---
title: Definir períodos de tiempo (Asistente para dimensiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.timefrequency.f1
ms.assetid: 6bda6b7e-d306-4e68-9acb-84de8f44d1b4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88b69eaa265b7a98f7d32063b602897d02016fa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676724"
---
# <a name="define-time-periods-dimension-wizard"></a><span data-ttu-id="9bcfb-102">Definir períodos de tiempo (Asistente para dimensiones)</span><span class="sxs-lookup"><span data-stu-id="9bcfb-102">Define Time Periods (Dimension Wizard)</span></span>
  <span data-ttu-id="9bcfb-103">Use la página **Definir períodos de tiempo** para definir la información del año natural y las frecuencias de tiempo que se deben incluir en la dimensión de tiempo o en la dimensión de tiempo de servidor.</span><span class="sxs-lookup"><span data-stu-id="9bcfb-103">Use the **Define Time Periods** page to define the calendar year information and time frequencies to include in the time dimension or server time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9bcfb-104"> Esta página se muestra solo si se ha seleccionado la opción **Dimensión de tiempo de servidor** en la página **Seleccionar el tipo de dimensión** o se ha seleccionado la opción **Generar la dimensión sin un origen de datos** en la página **Seleccionar método de generación** y se ha seleccionado **Dimensión de tiempo** en la página **Seleccionar el tipo de dimensión** .</span><span class="sxs-lookup"><span data-stu-id="9bcfb-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Select Build Method** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9bcfb-105">Esta página se usa para definir el año natural de una dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="9bcfb-105">This page is for defining the calendar year of a time dimension.</span></span> <span data-ttu-id="9bcfb-106">Para definir un año fiscal, de fabricación, de informe u 8601 ISO (Organización Internacional de Normalización) para la dimensión de tiempo, use la página **Seleccionar calendarios** .</span><span class="sxs-lookup"><span data-stu-id="9bcfb-106">To define a fiscal, manufacturing, reporting, or International Standards Organization (ISO) 8601 year for the time dimension, use the **Select Calendars** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9bcfb-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="9bcfb-107">Options</span></span>  
 <span data-ttu-id="9bcfb-108">**Primer día natural**</span><span class="sxs-lookup"><span data-stu-id="9bcfb-108">**First calendar day**</span></span>  
 <span data-ttu-id="9bcfb-109">Escriba o seleccione el día en el que se inicia el año actual.</span><span class="sxs-lookup"><span data-stu-id="9bcfb-109">Type or select the day that begins the current year.</span></span>  
  
 <span data-ttu-id="9bcfb-110">**Último día natural**</span><span class="sxs-lookup"><span data-stu-id="9bcfb-110">**Last calendar day**</span></span>  
 <span data-ttu-id="9bcfb-111">Escriba o seleccione el día en el que finaliza el año actual.</span><span class="sxs-lookup"><span data-stu-id="9bcfb-111">Type or select the day that ends the current year.</span></span>  
  
 <span data-ttu-id="9bcfb-112">**Primer día de la semana**</span><span class="sxs-lookup"><span data-stu-id="9bcfb-112">**First day of the week**</span></span>  
 <span data-ttu-id="9bcfb-113">Seleccione el día en el que se inicia una semana.</span><span class="sxs-lookup"><span data-stu-id="9bcfb-113">Select the day that begins a week.</span></span>  
  
 <span data-ttu-id="9bcfb-114">**Períodos de tiempo**</span><span class="sxs-lookup"><span data-stu-id="9bcfb-114">**Time periods**</span></span>  
 <span data-ttu-id="9bcfb-115">Seleccione los períodos de tiempo para el año natural de la dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="9bcfb-115">Select the time periods for the calendar year of the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9bcfb-116">El período de tiempo `Date` es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9bcfb-116">The `Date` time period is required.</span></span>  
  
 <span data-ttu-id="9bcfb-117">**Idioma de los nombres de miembros de tiempo**</span><span class="sxs-lookup"><span data-stu-id="9bcfb-117">**Language for time member names**</span></span>  
 <span data-ttu-id="9bcfb-118">Seleccione el idioma de los miembros de dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="9bcfb-118">Select the language for the members in the time dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bcfb-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9bcfb-119">See Also</span></span>  
 <span data-ttu-id="9bcfb-120">[Asistente para dimensiones (ayuda F1)](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="9bcfb-120">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="9bcfb-121">[Dimensiones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="9bcfb-121">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="9bcfb-122">[Dimensiones en modelos multidimensionales](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="9bcfb-122">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="9bcfb-123">Seleccionar calendarios &#40;Asistente para dimensiones&#41;</span><span class="sxs-lookup"><span data-stu-id="9bcfb-123">Select Calendars &#40;Dimension Wizard&#41;</span></span>](select-calendars-dimension-wizard.md)  
  
  
