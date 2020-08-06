---
title: Opciones de Solicitud de perfil de proporción de columnas nulas (tarea de generación de perfiles de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 157ef8e4-fd23-4f81-8194-eebf74e9fd86
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e47c09a9a19eae4aed21c0c518430bc19a45648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672229"
---
# <a name="column-null-ratio-profile-request-options-data-profiling-task"></a><span data-ttu-id="c01c5-102">Opciones de Solicitud de perfil de proporción de columnas nulas (tarea de generación de perfiles de datos)</span><span class="sxs-lookup"><span data-stu-id="c01c5-102">Column Null Ratio Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="c01c5-103">Utilice el panel **Propiedades de la solicitud** de la página **Solicitudes de perfil** para establecer las opciones de **Solicitud de perfil de proporción de columnas nulas** seleccionadas en el panel de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="c01c5-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Null Ratio Request** selected in the requests pane.</span></span> <span data-ttu-id="c01c5-104">Un perfil de proporción de columnas nulas indica el porcentaje de valores nulos de la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c01c5-104">A Column Null Ratio profile reports the percentage of null values in the selected column.</span></span> <span data-ttu-id="c01c5-105">Este perfil puede ayudarle a identificar problemas en los datos, por ejemplo una proporción inesperadamente alta de valores nulos en una columna.</span><span class="sxs-lookup"><span data-stu-id="c01c5-105">This profile can help you identify problems in your data such as an unexpectedly high ratio of null values in a column.</span></span> <span data-ttu-id="c01c5-106">Por ejemplo, un perfil de proporción de columnas nulas puede generar un perfil de una columna de códigos postales y detectar que falta un porcentaje inaceptablemente alto de códigos postales.</span><span class="sxs-lookup"><span data-stu-id="c01c5-106">For example, a Column Null Ratio profile can profile a ZIP Code/Postal Code column and discover an unacceptably high percentage of missing postal codes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c01c5-107">Las opciones que se describen en este tema aparecen en la página **Solicitudes de perfil** del **Editor de tareas de generación de perfiles de datos**.</span><span class="sxs-lookup"><span data-stu-id="c01c5-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="c01c5-108">Para obtener más información sobre esta página del editor, vea [Editor de tareas de generación de perfiles de datos &#40;página Solicitudes de perfil&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="c01c5-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="c01c5-109">Para más información sobre cómo usar la tarea de generación de perfiles de datos, vea [Configuración de la Tarea de generación de perfiles de datos](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="c01c5-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="c01c5-110">Para obtener más información sobre cómo usar el Visor de perfil de datos para analizar la salida de la tarea de generación de perfiles de datos, vea [Visor de perfil de datos](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="c01c5-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="c01c5-111">Opciones de Propiedades de la solicitud</span><span class="sxs-lookup"><span data-stu-id="c01c5-111">Request Properties Options</span></span>  
 <span data-ttu-id="c01c5-112">Para cada **Solicitud de perfil de proporción de columnas nulas**, el panel **Propiedades de la solicitud** muestra los grupos de opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c01c5-112">For a **Column Null Ratio Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="c01c5-113">**Data**, que incluye las opciones **TableOrView** y **Column**</span><span class="sxs-lookup"><span data-stu-id="c01c5-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="c01c5-114">**General**</span><span class="sxs-lookup"><span data-stu-id="c01c5-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="c01c5-115">Opciones de Data</span><span class="sxs-lookup"><span data-stu-id="c01c5-115">Data Options</span></span>  
 <span data-ttu-id="c01c5-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="c01c5-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="c01c5-117">Seleccione el administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existente que usa el proveedor de datos .NET para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) con el fin de conectarse a la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contiene la tabla o la vista con la que se va a generar el perfil.</span><span class="sxs-lookup"><span data-stu-id="c01c5-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the.NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="c01c5-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="c01c5-118">**TableOrView**</span></span>  
 <span data-ttu-id="c01c5-119">Seleccione la tabla o vista existente que contenga la columna de la que se va a generar un perfil.</span><span class="sxs-lookup"><span data-stu-id="c01c5-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="c01c5-120">Para obtener más información, vea la sección "Opciones de TableorView" en este tema.</span><span class="sxs-lookup"><span data-stu-id="c01c5-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="c01c5-121">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c01c5-121">**Column**</span></span>  
 <span data-ttu-id="c01c5-122">Seleccione la columna existente de la que se va a generar un perfil.</span><span class="sxs-lookup"><span data-stu-id="c01c5-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="c01c5-123">Seleccione **(\*)** para generar un perfil de todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="c01c5-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="c01c5-124">Para obtener más información, vea la sección "Opciones de Column" en este tema.</span><span class="sxs-lookup"><span data-stu-id="c01c5-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="c01c5-125">Opciones de TableOrView</span><span class="sxs-lookup"><span data-stu-id="c01c5-125">TableOrView Options</span></span>  
 <span data-ttu-id="c01c5-126">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="c01c5-126">**Schema**</span></span>  
 <span data-ttu-id="c01c5-127">Especifica el esquema al que pertenece la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c01c5-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="c01c5-128">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c01c5-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="c01c5-129">**Table**</span><span class="sxs-lookup"><span data-stu-id="c01c5-129">**Table**</span></span>  
 <span data-ttu-id="c01c5-130">Muestra el nombre de la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c01c5-130">Displays the name of the selected table.</span></span> <span data-ttu-id="c01c5-131">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c01c5-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="c01c5-132">Opciones de Column</span><span class="sxs-lookup"><span data-stu-id="c01c5-132">Column Options</span></span>  
 <span data-ttu-id="c01c5-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="c01c5-133">**IsWildCard**</span></span>  
 <span data-ttu-id="c01c5-134">Especifica si se ha seleccionado el carácter comodín **(\*)** .</span><span class="sxs-lookup"><span data-stu-id="c01c5-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="c01c5-135">Esta opción está establecida en **True** si ha seleccionado **(\*)** para generar un perfil de todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="c01c5-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="c01c5-136">Es **False** si ha seleccionado una columna individual para la que generar un perfil.</span><span class="sxs-lookup"><span data-stu-id="c01c5-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="c01c5-137">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c01c5-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="c01c5-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="c01c5-138">**ColumnName**</span></span>  
 <span data-ttu-id="c01c5-139">Muestra el nombre de la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c01c5-139">Displays the name of the selected column.</span></span> <span data-ttu-id="c01c5-140">Esta opción está en blanco si ha seleccionado **(\*)** para generar un perfil de todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="c01c5-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="c01c5-141">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c01c5-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="c01c5-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="c01c5-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="c01c5-143">Esta opción no se aplica al Perfil de proporción de columnas nulas.</span><span class="sxs-lookup"><span data-stu-id="c01c5-143">This option does not apply to the Column Null Ratio Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="c01c5-144">Opciones generales</span><span class="sxs-lookup"><span data-stu-id="c01c5-144">General Options</span></span>  
 <span data-ttu-id="c01c5-145">**IdSolicitud**</span><span class="sxs-lookup"><span data-stu-id="c01c5-145">**RequestID**</span></span>  
 <span data-ttu-id="c01c5-146">Escriba un nombre descriptivo para identificar esta solicitud de perfil.</span><span class="sxs-lookup"><span data-stu-id="c01c5-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="c01c5-147">Generalmente, no tiene que cambiar el valor generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c01c5-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c01c5-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c01c5-148">See Also</span></span>  
 <span data-ttu-id="c01c5-149">[Editor de tareas de generación de perfiles de datos &#40;página General&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="c01c5-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="c01c5-150">Formulario de perfil rápido de tabla única &#40;tarea de generación de perfiles de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c01c5-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
