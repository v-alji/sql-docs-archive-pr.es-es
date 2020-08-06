---
title: Configuración de filtro (Explorador de objetos y Explorador de Utilidad) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.filtersettings.f1
- sql12.swb.common.filtersettings.f1
ms.assetid: 4aab04bc-e1ab-4d4b-ab74-b287fc805bc2
author: stevestein
ms.author: sstein
ms.openlocfilehash: c31fbcbef9cbab86a7bd3ab7b2fae21e626aaa59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661767"
---
# <a name="filter-settings-object-explorer-and-utility-explorer"></a><span data-ttu-id="3afdd-102">Configuración de filtro (Explorador de objetos y Explorador de la utilidad)</span><span class="sxs-lookup"><span data-stu-id="3afdd-102">Filter Settings (Object Explorer and Utility Explorer)</span></span>
  <span data-ttu-id="3afdd-103">Utilice este cuadro de diálogo para especificar un filtro.</span><span class="sxs-lookup"><span data-stu-id="3afdd-103">Use this dialog box to specify a filter.</span></span> <span data-ttu-id="3afdd-104">Un filtro permite configurar el Explorador de objetos y el Explorador de la utilidad para mostrar únicamente los elementos que cumplen criterios específicos.</span><span class="sxs-lookup"><span data-stu-id="3afdd-104">A filter allows you to configure Object Explorer and Utility Explorer to display only items that meet specific criteria.</span></span> <span data-ttu-id="3afdd-105">Por ejemplo, puede utilizar un filtro para mostrar solo los trabajos con nombres que contienen la palabra "Mantenimiento".</span><span class="sxs-lookup"><span data-stu-id="3afdd-105">For example, you can use a filter to show only jobs with names that contain the word "Maintenance."</span></span> <span data-ttu-id="3afdd-106">El encabezado del cuadro de diálogo **Configuración del filtro** contiene el nombre del servidor y puede contener el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3afdd-106">The header for the **Filter Settings** dialog box contains the name of the server, and it may contain the name of the database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="3afdd-107">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3afdd-107">UI element list</span></span>  
 <span data-ttu-id="3afdd-108">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="3afdd-108">**Property**</span></span>  
 <span data-ttu-id="3afdd-109">Muestra la propiedad que se va filtrar.</span><span class="sxs-lookup"><span data-stu-id="3afdd-109">Displays the property to filter on.</span></span>  
  
 <span data-ttu-id="3afdd-110">**Operador**</span><span class="sxs-lookup"><span data-stu-id="3afdd-110">**Operator**</span></span>  
 <span data-ttu-id="3afdd-111">Seleccione la forma en que el filtro va a aplicar el valor a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3afdd-111">Select the way that the filter applies the value to the property.</span></span> <span data-ttu-id="3afdd-112">Existen las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3afdd-112">There are the following options:</span></span>  
  
-   <span data-ttu-id="3afdd-113">**Es igual a**</span><span class="sxs-lookup"><span data-stu-id="3afdd-113">**Equals**</span></span>  
  
     <span data-ttu-id="3afdd-114">El filtro muestra los elementos en los que la propiedad y el valor coinciden plenamente.</span><span class="sxs-lookup"><span data-stu-id="3afdd-114">The filter shows items where the property and the value are an exact match.</span></span>  
  
-   <span data-ttu-id="3afdd-115">**Contains**</span><span class="sxs-lookup"><span data-stu-id="3afdd-115">**Contains**</span></span>  
  
     <span data-ttu-id="3afdd-116">El filtro muestra los elementos en los que la propiedad contiene el valor.</span><span class="sxs-lookup"><span data-stu-id="3afdd-116">The filter shows items where the property contains the value.</span></span> <span data-ttu-id="3afdd-117">La propiedad puede contener otro texto.</span><span class="sxs-lookup"><span data-stu-id="3afdd-117">The property may contain other text.</span></span>  
  
-   <span data-ttu-id="3afdd-118">**No contiene**</span><span class="sxs-lookup"><span data-stu-id="3afdd-118">**Does not contain**</span></span>  
  
     <span data-ttu-id="3afdd-119">El filtro muestra los elementos en los que la propiedad no contiene el valor.</span><span class="sxs-lookup"><span data-stu-id="3afdd-119">The filter shows items that where the property does not contain the value.</span></span>  
  
-   <span data-ttu-id="3afdd-120">**Menor que**</span><span class="sxs-lookup"><span data-stu-id="3afdd-120">**Less than**</span></span>  
  
     <span data-ttu-id="3afdd-121">Disponible para fechas; este filtro muestra los elementos cuya fecha es anterior al valor proporcionado.</span><span class="sxs-lookup"><span data-stu-id="3afdd-121">Available for dates, this filter shows items whose date is before the value provided.</span></span>  
  
-   <span data-ttu-id="3afdd-122">**Menor que o igual a**</span><span class="sxs-lookup"><span data-stu-id="3afdd-122">**Less than or equal**</span></span>  
  
     <span data-ttu-id="3afdd-123">Disponible para fechas; este filtro muestra los elementos cuya fecha es igual o anterior al valor proporcionado.</span><span class="sxs-lookup"><span data-stu-id="3afdd-123">Available for dates, this filter shows items whose date contains or is before the value provided.</span></span>  
  
-   <span data-ttu-id="3afdd-124">**Mayor que**</span><span class="sxs-lookup"><span data-stu-id="3afdd-124">**Greater than**</span></span>  
  
     <span data-ttu-id="3afdd-125">Disponible para fechas; este filtro muestra los elementos cuya fecha es posterior al valor proporcionado.</span><span class="sxs-lookup"><span data-stu-id="3afdd-125">Available for dates, this filter shows items whose date is after the value provided.</span></span>  
  
-   <span data-ttu-id="3afdd-126">**Mayor que o igual a**</span><span class="sxs-lookup"><span data-stu-id="3afdd-126">**Greater than or equal**</span></span>  
  
     <span data-ttu-id="3afdd-127">Disponible para fechas; este filtro muestra los elementos cuya fecha es igual o posterior al valor proporcionado.</span><span class="sxs-lookup"><span data-stu-id="3afdd-127">Available for dates, this filter shows items whose date contains or is after the value provided.</span></span>  
  
-   <span data-ttu-id="3afdd-128">**Entre**</span><span class="sxs-lookup"><span data-stu-id="3afdd-128">**Between**</span></span>  
  
     <span data-ttu-id="3afdd-129">Disponible para fechas; este filtro muestra los elementos cuya fecha se encuentra entre dos fechas proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="3afdd-129">Available for dates, this filter shows items whose date is between two dates provided.</span></span> <span data-ttu-id="3afdd-130">Seleccione **Entre** y presione la tecla TAB para agregar otra fila a fin de escribir la segunda fecha.</span><span class="sxs-lookup"><span data-stu-id="3afdd-130">Select **Between** and press TAB to add another row allowing entry of the second date.</span></span>  
  
-   <span data-ttu-id="3afdd-131">**No entre**</span><span class="sxs-lookup"><span data-stu-id="3afdd-131">**Not between**</span></span>  
  
     <span data-ttu-id="3afdd-132">Disponible para fechas; este filtro muestra los elementos cuya fecha es anterior o posterior a dos fechas proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="3afdd-132">Available for dates, this filter shows items whose date is before or after two dates provided.</span></span> <span data-ttu-id="3afdd-133">Seleccione **No entre** y salga de la columna **Operador** para agregar otra fila a fin de escribir la segunda fecha.</span><span class="sxs-lookup"><span data-stu-id="3afdd-133">Select **Not Between** and tab out of the **Operator** column to add another row allowing entry of the second date.</span></span>  
  
 <span data-ttu-id="3afdd-134">**Valor**</span><span class="sxs-lookup"><span data-stu-id="3afdd-134">**Value**</span></span>  
 <span data-ttu-id="3afdd-135">Escriba el valor que va a compararse con la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3afdd-135">Type the value to compare to the property.</span></span> <span data-ttu-id="3afdd-136">Para seleccionar una fecha, haga clic en la flecha abajo para que aparezca un calendario donde seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="3afdd-136">For dates, click the down arrow to show a calendar for selecting the date.</span></span>  
  
 <span data-ttu-id="3afdd-137">**Borrar filtro**</span><span class="sxs-lookup"><span data-stu-id="3afdd-137">**Clear Filter**</span></span>  
 <span data-ttu-id="3afdd-138">Elimina toda la configuración actual del filtro.</span><span class="sxs-lookup"><span data-stu-id="3afdd-138">Removes all current filter settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3afdd-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3afdd-139">See Also</span></span>  
 <span data-ttu-id="3afdd-140">[Usar SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="3afdd-140">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="3afdd-141">Características y tareas de la utilidad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3afdd-141">SQL Server Utility Features and Tasks</span></span>](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)  
  
  
