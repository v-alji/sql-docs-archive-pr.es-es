---
title: Seleccionar calendarios (Asistente para dimensiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.serverSpecialCalendars.f1
ms.assetid: 6e28a020-2586-4b13-9333-b499fb1b33af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2048ee20dd91c942f01982d02f3265a6bad670dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673917"
---
# <a name="select-calendars-dimension-wizard"></a><span data-ttu-id="54c8f-102">Seleccionar calendarios (Asistente para dimensiones)</span><span class="sxs-lookup"><span data-stu-id="54c8f-102">Select Calendars (Dimension Wizard)</span></span>
  <span data-ttu-id="54c8f-103">Use la página **Seleccionar calendarios** para crear jerarquías adicionales que representan calendarios fiscales, de generación de informes, de fabricación o International Standards Organization (ISO) 8601 para la dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="54c8f-103">Use the **Select Calendars** page to create additional hierarchies representing fiscal, reporting, manufacturing, or International Standards Organization (ISO) 8601 calendars for the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54c8f-104"> Esta página se muestra solo si se ha seleccionado la opción **Dimensión de tiempo de servidor** en la página **Seleccionar el tipo de dimensión** o se ha seleccionado la opción **Generar la dimensión sin un origen de datos** en la página **Seleccionar método de generación** y se ha seleccionado **Dimensión de tiempo** en la página **Seleccionar el tipo de dimensión** .</span><span class="sxs-lookup"><span data-stu-id="54c8f-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Dimension Definition** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="54c8f-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="54c8f-105">Options</span></span>  
 <span data-ttu-id="54c8f-106">**Calendario fiscal**</span><span class="sxs-lookup"><span data-stu-id="54c8f-106">**Fiscal calendar**</span></span>  
 <span data-ttu-id="54c8f-107">Seleccione esta opción para crear una jerarquía de tiempo basada en un calendario fiscal.</span><span class="sxs-lookup"><span data-stu-id="54c8f-107">Select to create a time hierarchy based on a fiscal calendar.</span></span>  
  
 <span data-ttu-id="54c8f-108">**Día y mes de inicio**</span><span class="sxs-lookup"><span data-stu-id="54c8f-108">**Start day and month**</span></span>  
 <span data-ttu-id="54c8f-109">Seleccione el día y el mes en el que comienza el calendario fiscal.</span><span class="sxs-lookup"><span data-stu-id="54c8f-109">Select the day and month on which the fiscal calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54c8f-110"> Esta opción solo está disponible si se ha seleccionado **Calendario fiscal** .</span><span class="sxs-lookup"><span data-stu-id="54c8f-110">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="54c8f-111">**Convención de nomenclatura del año fiscal**</span><span class="sxs-lookup"><span data-stu-id="54c8f-111">**Fiscal calendar naming convention**</span></span>  
 <span data-ttu-id="54c8f-112">Seleccione la convención de nomenclatura usada por el calendario fiscal.</span><span class="sxs-lookup"><span data-stu-id="54c8f-112">Select the naming convention used by the fiscal calendar.</span></span> <span data-ttu-id="54c8f-113">Seleccione **Nombre del año natural** o **Nombre del año natural +1**.</span><span class="sxs-lookup"><span data-stu-id="54c8f-113">Select either **Calendar year name** or **Calendar year name +1**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54c8f-114"> Esta opción solo está disponible si se ha seleccionado **Calendario fiscal** .</span><span class="sxs-lookup"><span data-stu-id="54c8f-114">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="54c8f-115">**Calendario de informe (o marketing)**</span><span class="sxs-lookup"><span data-stu-id="54c8f-115">**Reporting (or marketing) calendar**</span></span>  
 <span data-ttu-id="54c8f-116">Seleccione esta opción para crear una jerarquía de tiempo basada en un calendario de informe.</span><span class="sxs-lookup"><span data-stu-id="54c8f-116">Select to create a time hierarchy based on a reporting calendar.</span></span>  
  
 <span data-ttu-id="54c8f-117">**Semana y mes de inicio**</span><span class="sxs-lookup"><span data-stu-id="54c8f-117">**Start week and month**</span></span>  
 <span data-ttu-id="54c8f-118">Seleccione la semana y el mes en que comienza el calendario de informe.</span><span class="sxs-lookup"><span data-stu-id="54c8f-118">Select the week and month on which the reporting calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54c8f-119">Esta opción solo está disponible si se ha seleccionado **Calendario de informe (o marketing)** .</span><span class="sxs-lookup"><span data-stu-id="54c8f-119">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="54c8f-120">**Semana por patrón mensual**</span><span class="sxs-lookup"><span data-stu-id="54c8f-120">**Week by month pattern**</span></span>  
 <span data-ttu-id="54c8f-121">Seleccione la semana por patrón mensual usada por el calendario de informe.</span><span class="sxs-lookup"><span data-stu-id="54c8f-121">Select the week by month pattern used by the reporting calendar.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54c8f-122">Esta opción solo está disponible si se ha seleccionado **Calendario de informe (o marketing)** .</span><span class="sxs-lookup"><span data-stu-id="54c8f-122">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="54c8f-123">En la tabla siguiente se enumeran las opciones disponibles para la semana por patrón mensual.</span><span class="sxs-lookup"><span data-stu-id="54c8f-123">The following table lists the options available for the week by month pattern.</span></span>  
  
|<span data-ttu-id="54c8f-124">Value</span><span class="sxs-lookup"><span data-stu-id="54c8f-124">Value</span></span>|<span data-ttu-id="54c8f-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="54c8f-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="54c8f-126">**Week 445**</span><span class="sxs-lookup"><span data-stu-id="54c8f-126">**Week 445**</span></span>|<span data-ttu-id="54c8f-127">El primer mes del trimestre tiene 4 semanas, el segundo mes tiene 4 semanas y el tercero tiene 5 semanas.</span><span class="sxs-lookup"><span data-stu-id="54c8f-127">The first month in the quarter has 4 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 5 weeks.</span></span>|  
|<span data-ttu-id="54c8f-128">**Week 454**</span><span class="sxs-lookup"><span data-stu-id="54c8f-128">**Week 454**</span></span>|<span data-ttu-id="54c8f-129">El primer mes del trimestre tiene 4 semanas, el segundo mes tiene 5 semanas y el tercero tiene 4 semanas.</span><span class="sxs-lookup"><span data-stu-id="54c8f-129">The first month in the quarter has 4 weeks, the second month in the quarter has 5 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
|<span data-ttu-id="54c8f-130">**Semana 544**</span><span class="sxs-lookup"><span data-stu-id="54c8f-130">**Week 544**</span></span>|<span data-ttu-id="54c8f-131">El primer mes del trimestre tiene 5 semanas, el segundo mes tiene 4 semanas y el tercero tiene 4 semanas.</span><span class="sxs-lookup"><span data-stu-id="54c8f-131">The first month in the quarter has 5 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
  
 <span data-ttu-id="54c8f-132">**Calendario de fabricación**</span><span class="sxs-lookup"><span data-stu-id="54c8f-132">**Manufacturing calendar**</span></span>  
 <span data-ttu-id="54c8f-133">Seleccione esta opción para crear una jerarquía de tiempo basada en un calendario de fabricación.</span><span class="sxs-lookup"><span data-stu-id="54c8f-133">Select to create a time hierarchy based on a manufacturing calendar.</span></span>  
  
 <span data-ttu-id="54c8f-134">**Semana y mes de inicio**</span><span class="sxs-lookup"><span data-stu-id="54c8f-134">**Start week and month**</span></span>  
 <span data-ttu-id="54c8f-135">Seleccione la semana y el mes en que comienza el calendario de fabricación.</span><span class="sxs-lookup"><span data-stu-id="54c8f-135">Select the week and month on which the manufacturing calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54c8f-136"> Esta opción solo está disponible cuando si se ha seleccionado **Calendario de fabricación** .</span><span class="sxs-lookup"><span data-stu-id="54c8f-136">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="54c8f-137">**Trimestre con períodos adicionales**</span><span class="sxs-lookup"><span data-stu-id="54c8f-137">**Quarter with extra periods**</span></span>  
 <span data-ttu-id="54c8f-138">Seleccione o escriba el trimestre que contendrá los periodos adicionales.</span><span class="sxs-lookup"><span data-stu-id="54c8f-138">Select or type the quarter that will contain the extra periods.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54c8f-139"> Esta opción solo está disponible cuando si se ha seleccionado **Calendario de fabricación** .</span><span class="sxs-lookup"><span data-stu-id="54c8f-139">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="54c8f-140">**Calendario ISO 8601**</span><span class="sxs-lookup"><span data-stu-id="54c8f-140">**ISO 8601 calendar**</span></span>  
 <span data-ttu-id="54c8f-141">Seleccione esta opción para crear una jerarquía de tiempo basada en el calendario ISO 8601.</span><span class="sxs-lookup"><span data-stu-id="54c8f-141">Select to create a hierarchy based on the ISO 8601 calendar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c8f-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54c8f-142">See Also</span></span>  
 <span data-ttu-id="54c8f-143">[Asistente para dimensiones (ayuda F1)](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="54c8f-143">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="54c8f-144">[Dimensiones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="54c8f-144">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="54c8f-145">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="54c8f-145">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
