---
title: Opciones de Solicitud de perfil de distribución de longitud de columnas (tarea de generación de perfiles de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 1a4de41f-f38d-40ea-ba1b-6c0ef67ea52a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c0ebb6f1e0a6df2c0e47311f7b8217c5ce6f2df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672231"
---
# <a name="column-length-distribution-profile-request-options-data-profiling-task"></a><span data-ttu-id="4f8fb-102">Opciones de Solicitud de perfil de distribución de longitud de columnas (tarea de generación de perfiles de datos)</span><span class="sxs-lookup"><span data-stu-id="4f8fb-102">Column Length Distribution Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="4f8fb-103">Utilice el panel **Propiedades de la solicitud** de la página **Solicitudes de perfil** para establecer las opciones de **Solicitud de perfil de distribución de longitud de columna** seleccionadas en el panel de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Length Distribution Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="4f8fb-104">Un perfil de distribución de columnas nulas indica las diferentes longitudes de los valores de cadena de la columna seleccionada y el porcentaje de filas de la tabla que cada longitud representa.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-104">A Column Length Distribution profile reports all the distinct lengths of string values in the selected column and the percentage of rows in the table that each length represents.</span></span> <span data-ttu-id="4f8fb-105">Este perfil puede ayudarle a identificar los problemas de los datos, por ejemplo valores que no sean válidos.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-105">This profile can help you identify problems in your data such as invalid values.</span></span> <span data-ttu-id="4f8fb-106">Por ejemplo, genera un perfil de una columna de códigos de estados de Estados Unidos de dos caracteres y detecta valores menores de dos caracteres.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-106">For example, you profile a column of two-character United States state codes and discover values longer than two characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f8fb-107">Las opciones que se describen en este tema aparecen en la página **Solicitudes de perfil** del **Editor de tareas de generación de perfiles de datos**.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="4f8fb-108">Para obtener más información sobre esta página del editor, vea [Editor de tareas de generación de perfiles de datos &#40;página Solicitudes de perfil&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="4f8fb-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="4f8fb-109">Para más información sobre cómo usar la tarea de generación de perfiles de datos, vea [Configuración de la Tarea de generación de perfiles de datos](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="4f8fb-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="4f8fb-110">Para obtener más información sobre cómo usar el Visor de perfil de datos para analizar la salida de la tarea de generación de perfiles de datos, vea [Visor de perfil de datos](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="4f8fb-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="4f8fb-111">Opciones de Propiedades de la solicitud</span><span class="sxs-lookup"><span data-stu-id="4f8fb-111">Request Properties Options</span></span>  
 <span data-ttu-id="4f8fb-112">Para una **Solicitud de perfil de distribución de longitud de columnas**, el panel **Propiedades de la solicitud** muestra los grupos siguientes de opciones:</span><span class="sxs-lookup"><span data-stu-id="4f8fb-112">For a **Column Length Distribution Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="4f8fb-113">**Data**, que incluye las opciones **TableOrView** y **Column**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="4f8fb-114">**General**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-114">**General**</span></span>  
  
-   <span data-ttu-id="4f8fb-115">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-115">**Options**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="4f8fb-116">Opciones de Data</span><span class="sxs-lookup"><span data-stu-id="4f8fb-116">Data Options</span></span>  
 <span data-ttu-id="4f8fb-117">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-117">**ConnectionManager**</span></span>  
 <span data-ttu-id="4f8fb-118">Seleccione el administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existente que usa el proveedor de datos .NET para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) para conectarse a la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contiene la tabla o la vista con la que se generará el perfil.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-118">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="4f8fb-119">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-119">**TableOrView**</span></span>  
 <span data-ttu-id="4f8fb-120">Seleccione la tabla o vista existente que contenga la columna de la que se va a generar un perfil.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-120">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="4f8fb-121">Para obtener más información, vea la sección "Opciones de TableorView" en este tema.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-121">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="4f8fb-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-122">**Column**</span></span>  
 <span data-ttu-id="4f8fb-123">Seleccione la columna existente de la que se va a generar un perfil.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-123">Select the existing column to be profiled.</span></span> <span data-ttu-id="4f8fb-124">Seleccione **(\*)** para generar un perfil de todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-124">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="4f8fb-125">Para obtener más información, vea la sección "Opciones de Column" en este tema.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-125">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="4f8fb-126">Opciones de TableOrView</span><span class="sxs-lookup"><span data-stu-id="4f8fb-126">TableOrView Options</span></span>  
 <span data-ttu-id="4f8fb-127">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-127">**Schema**</span></span>  
 <span data-ttu-id="4f8fb-128">Especifique el esquema al que pertenece la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-128">Specify the schema to which the selected table belongs.</span></span> <span data-ttu-id="4f8fb-129">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-129">This option is read-only.</span></span>  
  
 <span data-ttu-id="4f8fb-130">**Table**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-130">**Table**</span></span>  
 <span data-ttu-id="4f8fb-131">Muestra el nombre de la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-131">Displays the name of the selected table.</span></span> <span data-ttu-id="4f8fb-132">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-132">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="4f8fb-133">Opciones de Column</span><span class="sxs-lookup"><span data-stu-id="4f8fb-133">Column Options</span></span>  
 <span data-ttu-id="4f8fb-134">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-134">**IsWildCard**</span></span>  
 <span data-ttu-id="4f8fb-135">Especifica si se ha seleccionado el carácter comodín **(\*)** .</span><span class="sxs-lookup"><span data-stu-id="4f8fb-135">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="4f8fb-136">Esta opción está establecida en **True** si ha seleccionado **(\*)** para generar un perfil de todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-136">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="4f8fb-137">Es **False** si ha seleccionado una columna individual para la que generar un perfil.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-137">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="4f8fb-138">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-138">This option is read-only.</span></span>  
  
 <span data-ttu-id="4f8fb-139">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-139">**ColumnName**</span></span>  
 <span data-ttu-id="4f8fb-140">Muestra el nombre de la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-140">Displays the name of the selected column.</span></span> <span data-ttu-id="4f8fb-141">Esta opción está en blanco si ha seleccionado **(\*)** para generar un perfil de todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-141">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="4f8fb-142">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-142">This option is read-only.</span></span>  
  
 <span data-ttu-id="4f8fb-143">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-143">**StringCompareOptions**</span></span>  
 <span data-ttu-id="4f8fb-144">Esta opción no se aplica al Perfil de distribución de longitud de columnas.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-144">This option does not apply to the Column Length Distribution Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="4f8fb-145">Opciones generales</span><span class="sxs-lookup"><span data-stu-id="4f8fb-145">General Options</span></span>  
 <span data-ttu-id="4f8fb-146">**IdSolicitud**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-146">**RequestID**</span></span>  
 <span data-ttu-id="4f8fb-147">Escriba un nombre descriptivo para identificar esta solicitud de perfil.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-147">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="4f8fb-148">Generalmente, no tiene que cambiar el valor generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-148">Typically, you do not have to change the autogenerated value.</span></span>  
  
### <a name="options"></a><span data-ttu-id="4f8fb-149">Opciones</span><span class="sxs-lookup"><span data-stu-id="4f8fb-149">Options</span></span>  
 <span data-ttu-id="4f8fb-150">**IgnoreLeadingSpaces**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-150">**IgnoreLeadingSpaces**</span></span>  
 <span data-ttu-id="4f8fb-151">Indique si omitir los espacios iniciales cuando el perfil compara valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-151">Indicate whether to ignore leading spaces when the profile compares string values.</span></span> <span data-ttu-id="4f8fb-152">El valor predeterminado de esta opción es **False**.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-152">The default value of this option is **False**.</span></span>  
  
 <span data-ttu-id="4f8fb-153">**IgnoreTrailingSpaces**</span><span class="sxs-lookup"><span data-stu-id="4f8fb-153">**IgnoreTrailingSpaces**</span></span>  
 <span data-ttu-id="4f8fb-154">Indique si omitir los espacios finales cuando el perfil compara valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-154">Indicate whether to ignore trailing spaces when the profile compares string values.</span></span> <span data-ttu-id="4f8fb-155">El valor predeterminado de esta opción es **True**.</span><span class="sxs-lookup"><span data-stu-id="4f8fb-155">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8fb-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f8fb-156">See Also</span></span>  
 <span data-ttu-id="4f8fb-157">[Editor de tareas de generación de perfiles de datos &#40;página General&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="4f8fb-157">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="4f8fb-158">Formulario de perfil rápido de tabla única &#40;tarea de generación de perfiles de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="4f8fb-158">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
