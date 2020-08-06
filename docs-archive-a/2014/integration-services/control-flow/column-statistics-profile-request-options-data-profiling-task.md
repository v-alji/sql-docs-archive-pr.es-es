---
title: Opciones de Solicitud de perfil de estadísticas de columnas (tarea de generación de perfiles de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 87205984-507a-49f3-b27c-36a0075c234d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce5c062a12e38d147f3cef95ea09b4c80f7c256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672226"
---
# <a name="column-statistics-profile-request-options-data-profiling-task"></a><span data-ttu-id="8f7e0-102">Opciones de Solicitud de perfil de estadísticas de columnas (tarea de generación de perfiles de datos)</span><span class="sxs-lookup"><span data-stu-id="8f7e0-102">Column Statistics Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="8f7e0-103">Utilice el panel **Propiedades de la solicitud** de la página **Solicitudes de perfil** para establecer las opciones de **Solicitud de perfil de estadísticas de columnas** seleccionadas en el panel de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Statistics Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="8f7e0-104">Un perfil de estadísticas de columnas notifica estadísticas, como los valores mínimo, máximo y promedio, y la desviación estándar para las columnas numéricas, y los valores mínimo y máximo para las columnas `datetime`.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-104">A Column Statistics profile reports statistics such as minimum, maximum, average, and standard deviation for numeric columns, and minimum and maximum for `datetime` columns.</span></span> <span data-ttu-id="8f7e0-105">Este perfil puede ayudarle a identificar problemas de los datos, por ejemplo fechas que no sean válidas.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-105">This profile can help you identify problems in your data such as invalid dates.</span></span> <span data-ttu-id="8f7e0-106">Por ejemplo, genera un perfil de una columna de fechas históricas y detecta una fecha máxima futura.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-106">For example, you profile a column of historical dates and discover a maximum date that is in the future.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f7e0-107">Las opciones que se describen en este tema aparecen en la página **Solicitudes de perfil** del **Editor de tareas de generación de perfiles de datos**.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="8f7e0-108">Para obtener más información sobre esta página del editor, vea [Editor de tareas de generación de perfiles de datos &#40;página Solicitudes de perfil&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="8f7e0-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="8f7e0-109">Para más información sobre cómo usar la tarea de generación de perfiles de datos, vea [Configuración de la Tarea de generación de perfiles de datos](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="8f7e0-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="8f7e0-110">Para obtener más información sobre cómo usar el Visor de perfil de datos para analizar la salida de la tarea de generación de perfiles de datos, vea [Visor de perfil de datos](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="8f7e0-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="8f7e0-111">Opciones de Propiedades de la solicitud</span><span class="sxs-lookup"><span data-stu-id="8f7e0-111">Request Properties Options</span></span>  
 <span data-ttu-id="8f7e0-112">Para cada **Solicitud de perfil de estadísticas de columnas**, el panel **Propiedades de la solicitud** muestra los grupos siguientes de opciones:</span><span class="sxs-lookup"><span data-stu-id="8f7e0-112">For a **Column Statistics Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="8f7e0-113">**Data**, que incluye las opciones **TableOrView** y **Column**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="8f7e0-114">**General**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="8f7e0-115">Opciones de Data</span><span class="sxs-lookup"><span data-stu-id="8f7e0-115">Data Options</span></span>  
 <span data-ttu-id="8f7e0-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="8f7e0-117">Seleccione el administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existente que usa el proveedor de datos .NET para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) para conectarse a la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contiene la tabla o la vista con la que se generará el perfil.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="8f7e0-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-118">**TableOrView**</span></span>  
 <span data-ttu-id="8f7e0-119">Seleccione la tabla o vista existente que contenga la columna de la que se va a generar un perfil.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="8f7e0-120">Para obtener más información, vea la sección "Opciones de TableorView" en este tema.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="8f7e0-121">**Columna**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-121">**Column**</span></span>  
 <span data-ttu-id="8f7e0-122">Seleccione la columna existente de la que se va a generar un perfil.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="8f7e0-123">Seleccione **(\*)** para generar un perfil de todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="8f7e0-124">Para obtener más información, vea la sección "Opciones de Column" en este tema.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="8f7e0-125">Opciones de TableOrView</span><span class="sxs-lookup"><span data-stu-id="8f7e0-125">TableOrView Options</span></span>  
 <span data-ttu-id="8f7e0-126">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-126">**Schema**</span></span>  
 <span data-ttu-id="8f7e0-127">Especifica el esquema al que pertenece la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="8f7e0-128">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="8f7e0-129">**Table**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-129">**Table**</span></span>  
 <span data-ttu-id="8f7e0-130">Muestra el nombre de la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-130">Displays the name of the selected table.</span></span> <span data-ttu-id="8f7e0-131">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="8f7e0-132">Opciones de Column</span><span class="sxs-lookup"><span data-stu-id="8f7e0-132">Column Options</span></span>  
 <span data-ttu-id="8f7e0-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-133">**IsWildCard**</span></span>  
 <span data-ttu-id="8f7e0-134">Especifica si se ha seleccionado el carácter comodín **(\*)** .</span><span class="sxs-lookup"><span data-stu-id="8f7e0-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="8f7e0-135">Esta opción está establecida en **True** si ha seleccionado **(\*)** para generar un perfil de todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="8f7e0-136">Es **False** si ha seleccionado una columna individual para la que generar un perfil.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="8f7e0-137">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="8f7e0-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-138">**ColumnName**</span></span>  
 <span data-ttu-id="8f7e0-139">Muestra el nombre de la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-139">Displays the name of the selected column.</span></span> <span data-ttu-id="8f7e0-140">Esta opción está en blanco si ha seleccionado **(\*)** para generar un perfil de todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="8f7e0-141">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="8f7e0-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="8f7e0-143">Esta opción no se aplica al perfil de estadísticas de columnas.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-143">This option does not apply to the Column Statistics Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="8f7e0-144">Opciones generales</span><span class="sxs-lookup"><span data-stu-id="8f7e0-144">General Options</span></span>  
 <span data-ttu-id="8f7e0-145">**IdSolicitud**</span><span class="sxs-lookup"><span data-stu-id="8f7e0-145">**RequestID**</span></span>  
 <span data-ttu-id="8f7e0-146">Escriba un nombre descriptivo para identificar esta solicitud de perfil.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="8f7e0-147">Generalmente, no tiene que cambiar el valor generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8f7e0-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7e0-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f7e0-148">See Also</span></span>  
 <span data-ttu-id="8f7e0-149">[Editor de tareas de generación de perfiles de datos &#40;página General&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="8f7e0-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="8f7e0-150">Formulario de perfil rápido de tabla única &#40;tarea de generación de perfiles de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="8f7e0-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
