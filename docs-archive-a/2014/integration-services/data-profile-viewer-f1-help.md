---
title: Visor de perfil de datos ayuda de F1 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dataprofileviewer.f1
helpviewer_keywords:
- Data Profile Viewer [Integration Services]
- Data Profiling task [Integration Services], viewer
ms.assetid: 3469c60a-8f4f-46ba-999a-cb9070197fea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7003e1299938bd53a6d16a5597d4566ba5c46579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669770"
---
# <a name="data-profile-viewer-f1-help"></a><span data-ttu-id="7bf56-102">Visor de perfiles de datos (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="7bf56-102">Data Profile Viewer F1 Help</span></span>
  <span data-ttu-id="7bf56-103">Utilice el Visor de perfil de datos para ver la salida de la Tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="7bf56-103">Use the Data Profile Viewer to view the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="7bf56-104">Para más información sobre cómo usar el Visor de perfil de datos, vea [Visor de perfil de datos](control-flow/data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="7bf56-104">For more information about how to use the Data Profile Viewer, see [Data Profile Viewer](control-flow/data-profile-viewer.md).</span></span> <span data-ttu-id="7bf56-105">Para más información sobre cómo usar la Tarea de generación de perfiles de datos, que crea la salida del perfil que se analiza en el Visor de perfil de datos, vea [Configuración de la Tarea de generación de perfiles de datos](control-flow/data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="7bf56-105">For more information about how to use the Data Profiling task, which creates the profile output that you analyze in the Data Profile Viewer, see [Setup of the Data Profiling Task](control-flow/data-profiling-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="7bf56-106">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="7bf56-106">Static Options</span></span>  
 <span data-ttu-id="7bf56-107">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="7bf56-107">**Open**</span></span>  
 <span data-ttu-id="7bf56-108">Haga clic para buscar el archivo guardado que contiene la salida de la Tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="7bf56-108">Click to browse for the saved file that contains the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="7bf56-109">Panel**Perfiles**</span><span class="sxs-lookup"><span data-stu-id="7bf56-109">**Profiles** pane</span></span>  
 <span data-ttu-id="7bf56-110">Expanda el árbol del panel **Perfiles** para ver los perfiles que están incluidos en la salida.</span><span class="sxs-lookup"><span data-stu-id="7bf56-110">Expand the tree in the **Profiles** pane to see the profiles that are included in the output.</span></span> <span data-ttu-id="7bf56-111">Seleccione un perfil para ver los resultados de ese perfil.</span><span class="sxs-lookup"><span data-stu-id="7bf56-111">Select a profile to view the results for that profile.</span></span>  
  
 <span data-ttu-id="7bf56-112">Panel**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="7bf56-112">**Message** pane</span></span>  
 <span data-ttu-id="7bf56-113">Muestra mensajes de estado.</span><span class="sxs-lookup"><span data-stu-id="7bf56-113">Displays status messages.</span></span>  
  
 <span data-ttu-id="7bf56-114">Panel**Obtención de detalles**</span><span class="sxs-lookup"><span data-stu-id="7bf56-114">**Drilldown** pane</span></span>  
 <span data-ttu-id="7bf56-115">Muestra las filas de datos que coinciden con un valor en la salida, si el origen de datos que usa la Tarea de generación de perfiles de datos está disponible.</span><span class="sxs-lookup"><span data-stu-id="7bf56-115">Displays the rows of data that match a value in the output, if the data source that is used by the Data Profiling task is available.</span></span>  
  
 <span data-ttu-id="7bf56-116">Por ejemplo, si está viendo la salida de un perfil Distribución de valores de columna de una columna de estados americanos, el panel **Distribución de valor detallado** podría contener una fila para "WA".</span><span class="sxs-lookup"><span data-stu-id="7bf56-116">For example, if you are viewing the output of a Column Value Distribution profile for a US State column, the **Detailed Value Distribution** pane might contain a row for "WA".</span></span> <span data-ttu-id="7bf56-117">Haga doble clic en la fila en el panel **Distribución de valores detallados** para ver las filas de datos en las que el valor de la columna de estado sea "WA" en el panel de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="7bf56-117">Double-click the row in the **Detailed Value Distribution** pane to see the rows of data where the value of the state column is "WA" in the drilldown pane.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="7bf56-118">Opciones dinámicas</span><span class="sxs-lookup"><span data-stu-id="7bf56-118">Dynamic Options</span></span>  
  
### <a name="profile-type--column-length-distribution-profile"></a><span data-ttu-id="7bf56-119">Tipo de perfil = Perfil de distribución de longitud de columnas</span><span class="sxs-lookup"><span data-stu-id="7bf56-119">Profile Type = Column Length Distribution Profile</span></span>  
  
#### <a name="column-length-distribution-profile---column-pane"></a><span data-ttu-id="7bf56-120">Panel Perfil de distribución de longitud de columnas- \<column></span><span class="sxs-lookup"><span data-stu-id="7bf56-120">Column Length Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="7bf56-121">**Longitud mínima**</span><span class="sxs-lookup"><span data-stu-id="7bf56-121">**Minimum Length**</span></span>  
 <span data-ttu-id="7bf56-122">Muestra la longitud mínima de los valores de esta columna.</span><span class="sxs-lookup"><span data-stu-id="7bf56-122">Displays the minimum length of values in this column.</span></span>  
  
 <span data-ttu-id="7bf56-123">**Longitud máxima**</span><span class="sxs-lookup"><span data-stu-id="7bf56-123">**Maximum Length**</span></span>  
 <span data-ttu-id="7bf56-124">Muestra la longitud máxima de los valores de esta columna.</span><span class="sxs-lookup"><span data-stu-id="7bf56-124">Displays the maximum length of values in this column.</span></span>  
  
 <span data-ttu-id="7bf56-125">**Omitir espacios iniciales**</span><span class="sxs-lookup"><span data-stu-id="7bf56-125">**Ignore Leading Spaces**</span></span>  
 <span data-ttu-id="7bf56-126">Muestra si este perfil se calculó con un valor de `IgnoreLeadingSpaces` True o False.</span><span class="sxs-lookup"><span data-stu-id="7bf56-126">Displays whether this profile was computed with an `IgnoreLeadingSpaces` value of True or False.</span></span> <span data-ttu-id="7bf56-127">Esta propiedad se estableció en la página **Solicitudes de perfil** del Editor de tareas de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="7bf56-127">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="7bf56-128">**Omitir espacios finales**</span><span class="sxs-lookup"><span data-stu-id="7bf56-128">**Ignore Trailing Spaces**</span></span>  
 <span data-ttu-id="7bf56-129">Muestra si este perfil se calculó con un valor de `IgnoreTrailingSpaces` True o False.</span><span class="sxs-lookup"><span data-stu-id="7bf56-129">Displays whether this profile was computed with an `IgnoreTrailingSpaces` value of True or False.</span></span> <span data-ttu-id="7bf56-130">Esta propiedad se estableció en la página **Solicitudes de perfil** del Editor de tareas de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="7bf56-130">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="7bf56-131">**Recuento de filas**</span><span class="sxs-lookup"><span data-stu-id="7bf56-131">**Row Count**</span></span>  
 <span data-ttu-id="7bf56-132">Muestra el número de filas de la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="7bf56-132">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-length-distribution-pane"></a><span data-ttu-id="7bf56-133">Panel Distribución de longitud detallado</span><span class="sxs-lookup"><span data-stu-id="7bf56-133">Detailed Length Distribution pane</span></span>  
 <span data-ttu-id="7bf56-134">**Longitud**</span><span class="sxs-lookup"><span data-stu-id="7bf56-134">**Length**</span></span>  
 <span data-ttu-id="7bf56-135">Muestra las longitudes de columna encontradas en la columna de perfiles.</span><span class="sxs-lookup"><span data-stu-id="7bf56-135">Displays the column lengths found in the profiled column.</span></span>  
  
 <span data-ttu-id="7bf56-136">**Recuento**</span><span class="sxs-lookup"><span data-stu-id="7bf56-136">**Count**</span></span>  
 <span data-ttu-id="7bf56-137">Muestra el número de filas en las que el valor de la columna de perfiles tiene la longitud que se muestra en la columna **Longitud** .</span><span class="sxs-lookup"><span data-stu-id="7bf56-137">Displays the number of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
 <span data-ttu-id="7bf56-138">**Porcentaje**</span><span class="sxs-lookup"><span data-stu-id="7bf56-138">**Percentage**</span></span>  
 <span data-ttu-id="7bf56-139">Muestra el porcentaje de filas en las que el valor de la columna de perfiles tiene la longitud que se muestra en la columna **Longitud** .</span><span class="sxs-lookup"><span data-stu-id="7bf56-139">Displays the percentage of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
### <a name="profile-type--column-null-ratio-profile"></a><span data-ttu-id="7bf56-140">Tipo de perfil = Perfil de proporción de columnas nulas</span><span class="sxs-lookup"><span data-stu-id="7bf56-140">Profile Type = Column Null Ratio Profile</span></span>  
  
#### <a name="column-null-ratio-profile---column-pane"></a><span data-ttu-id="7bf56-141">Panel Perfil de proporción de columnas nulas - \<column></span><span class="sxs-lookup"><span data-stu-id="7bf56-141">Column Null Ratio Profile - \<column> pane</span></span>  
 <span data-ttu-id="7bf56-142">**Recuento nulo**</span><span class="sxs-lookup"><span data-stu-id="7bf56-142">**Null Count**</span></span>  
 <span data-ttu-id="7bf56-143">Muestra el número de filas en las que la columna de perfiles tiene el valor null.</span><span class="sxs-lookup"><span data-stu-id="7bf56-143">Displays the number of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="7bf56-144">**Porcentaje nulo**</span><span class="sxs-lookup"><span data-stu-id="7bf56-144">**Null Percentage**</span></span>  
 <span data-ttu-id="7bf56-145">Muestra el porcentaje de filas en las que la columna de perfiles tiene el valor null.</span><span class="sxs-lookup"><span data-stu-id="7bf56-145">Displays the percentage of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="7bf56-146">**Recuento de filas**</span><span class="sxs-lookup"><span data-stu-id="7bf56-146">**Row Count**</span></span>  
 <span data-ttu-id="7bf56-147">Muestra el número de filas de la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="7bf56-147">Displays the number of rows in the table or view.</span></span>  
  
### <a name="profile-type--column-pattern-profile"></a><span data-ttu-id="7bf56-148">Tipo de perfil = Perfil de patrón de columnas</span><span class="sxs-lookup"><span data-stu-id="7bf56-148">Profile Type = Column Pattern Profile</span></span>  
  
#### <a name="column-pattern-profile---column-pane"></a><span data-ttu-id="7bf56-149">Panel Perfil de patrón de columnas - \<column></span><span class="sxs-lookup"><span data-stu-id="7bf56-149">Column Pattern Profile - \<column> pane</span></span>  
 <span data-ttu-id="7bf56-150">**Recuento de filas**</span><span class="sxs-lookup"><span data-stu-id="7bf56-150">**Row Count**</span></span>  
 <span data-ttu-id="7bf56-151">Muestra el número de filas de la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="7bf56-151">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="pattern-distribution-pane"></a><span data-ttu-id="7bf56-152">Panel Distribución del patrón</span><span class="sxs-lookup"><span data-stu-id="7bf56-152">Pattern Distribution pane</span></span>  
 <span data-ttu-id="7bf56-153">**Patrón**</span><span class="sxs-lookup"><span data-stu-id="7bf56-153">**Pattern**</span></span>  
 <span data-ttu-id="7bf56-154">Muestra los patrones calculados para la columna de perfiles.</span><span class="sxs-lookup"><span data-stu-id="7bf56-154">Displays the patterns computed for the profiled column.</span></span>  
  
 <span data-ttu-id="7bf56-155">**Porcentaje**</span><span class="sxs-lookup"><span data-stu-id="7bf56-155">**Percentage**</span></span>  
 <span data-ttu-id="7bf56-156">Muestra el porcentaje de filas cuyos valores coinciden con el patrón que se muestra en la columna **Patrón** .</span><span class="sxs-lookup"><span data-stu-id="7bf56-156">Displays the percentage of rows whose values match the pattern displayed in the **Pattern** column.</span></span>  
  
### <a name="profile-type--column-statistics-profile"></a><span data-ttu-id="7bf56-157">Tipo de perfil = Perfil de estadísticas de columnas</span><span class="sxs-lookup"><span data-stu-id="7bf56-157">Profile Type = Column Statistics Profile</span></span>  
  
#### <a name="column-statistics-profile---column-pane"></a><span data-ttu-id="7bf56-158">Panel Perfil de estadísticas de columnas - \<column></span><span class="sxs-lookup"><span data-stu-id="7bf56-158">Column Statistics Profile - \<column> pane</span></span>  
 <span data-ttu-id="7bf56-159">**Mínimo**</span><span class="sxs-lookup"><span data-stu-id="7bf56-159">**Minimum**</span></span>  
 <span data-ttu-id="7bf56-160">Muestra el valor mínimo situado en la columna de perfiles.</span><span class="sxs-lookup"><span data-stu-id="7bf56-160">Displays the minimum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="7bf56-161">**Máximo**</span><span class="sxs-lookup"><span data-stu-id="7bf56-161">**Maximum**</span></span>  
 <span data-ttu-id="7bf56-162">Muestra el valor máximo situado en la columna de perfiles.</span><span class="sxs-lookup"><span data-stu-id="7bf56-162">Displays the maximum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="7bf56-163">**Promedio**</span><span class="sxs-lookup"><span data-stu-id="7bf56-163">**Mean**</span></span>  
 <span data-ttu-id="7bf56-164">Muestra el promedio de los valores que se encuentran en la columna de perfiles.</span><span class="sxs-lookup"><span data-stu-id="7bf56-164">Displays the mean of the values found in the profiled column.</span></span>  
  
 <span data-ttu-id="7bf56-165">**Desviación estándar**</span><span class="sxs-lookup"><span data-stu-id="7bf56-165">**Standard Deviation**</span></span>  
 <span data-ttu-id="7bf56-166">Muestra la desviación estándar de los valores que se encuentran en la columna de perfiles.</span><span class="sxs-lookup"><span data-stu-id="7bf56-166">Displays the standard deviation of the values found in the profiled column.</span></span>  
  
### <a name="profile-type--column-value-distribution-profile"></a><span data-ttu-id="7bf56-167">Tipo de perfil = Perfil de distribución de valores de columna</span><span class="sxs-lookup"><span data-stu-id="7bf56-167">Profile Type = Column Value Distribution Profile</span></span>  
  
#### <a name="column-value-distribution-profile---column-pane"></a><span data-ttu-id="7bf56-168">Panel Perfil de distribución de valores de columna - \<column></span><span class="sxs-lookup"><span data-stu-id="7bf56-168">Column Value Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="7bf56-169">**Número de valores distintos**</span><span class="sxs-lookup"><span data-stu-id="7bf56-169">**Number of Distinct Values**</span></span>  
 <span data-ttu-id="7bf56-170">Muestra el recuento de valores distintos que se encuentran en la columna de perfiles.</span><span class="sxs-lookup"><span data-stu-id="7bf56-170">Displays the count of distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="7bf56-171">**Recuento de filas**</span><span class="sxs-lookup"><span data-stu-id="7bf56-171">**Row Count**</span></span>  
 <span data-ttu-id="7bf56-172">Muestra el número de filas de la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="7bf56-172">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-value-distribution-pane"></a><span data-ttu-id="7bf56-173">Panel Distribución de valores detallado</span><span class="sxs-lookup"><span data-stu-id="7bf56-173">Detailed Value Distribution pane</span></span>  
 <span data-ttu-id="7bf56-174">**Valor**</span><span class="sxs-lookup"><span data-stu-id="7bf56-174">**Value**</span></span>  
 <span data-ttu-id="7bf56-175">Muestra los distintos valores que se encuentran en la columna de perfiles.</span><span class="sxs-lookup"><span data-stu-id="7bf56-175">Displays the distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="7bf56-176">**Recuento**</span><span class="sxs-lookup"><span data-stu-id="7bf56-176">**Count**</span></span>  
 <span data-ttu-id="7bf56-177">Muestra el número de filas en las que la columna de perfiles tiene el valor que se muestra en la columna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="7bf56-177">Displays the number of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
 <span data-ttu-id="7bf56-178">**Porcentaje**</span><span class="sxs-lookup"><span data-stu-id="7bf56-178">**Percentage**</span></span>  
 <span data-ttu-id="7bf56-179">Muestra el porcentaje de filas en las que la columna de perfiles tiene el valor que se muestra en la columna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="7bf56-179">Displays the percentage of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
### <a name="profile-type--candidate-key-profile"></a><span data-ttu-id="7bf56-180">Tipo de perfil = Perfil de claves candidatas</span><span class="sxs-lookup"><span data-stu-id="7bf56-180">Profile Type = Candidate Key Profile</span></span>  
  
#### <a name="candidate-key-profile---table-pane"></a><span data-ttu-id="7bf56-181">Panel Perfil de claves candidatas - \<table></span><span class="sxs-lookup"><span data-stu-id="7bf56-181">Candidate Key Profile - \<table> pane</span></span>  
 <span data-ttu-id="7bf56-182">**Columnas de clave**</span><span class="sxs-lookup"><span data-stu-id="7bf56-182">**Key Columns**</span></span>  
 <span data-ttu-id="7bf56-183">Muestra las columnas que se seleccionaron para los perfiles como clave candidata.</span><span class="sxs-lookup"><span data-stu-id="7bf56-183">Displays the columns that were selected for profiling as a candidate key.</span></span>  
  
 <span data-ttu-id="7bf56-184">**Nivel de clave**</span><span class="sxs-lookup"><span data-stu-id="7bf56-184">**Key Strength**</span></span>  
 <span data-ttu-id="7bf56-185">Muestra el nivel (como porcentaje) de la columna de clave candidata o de una combinación de columnas.</span><span class="sxs-lookup"><span data-stu-id="7bf56-185">Displays the strength (as a percentage) of the candidate key column or combination of columns.</span></span> <span data-ttu-id="7bf56-186">Un nivel de clave menor del 100% indica que hay valores duplicados.</span><span class="sxs-lookup"><span data-stu-id="7bf56-186">A key strength of less than 100% indicates that duplicate values exist.</span></span>  
  
#### <a name="key-violations-pane"></a><span data-ttu-id="7bf56-187">Panel Infracciones de clave</span><span class="sxs-lookup"><span data-stu-id="7bf56-187">Key Violations pane</span></span>  
 <span data-ttu-id="7bf56-188">**\<column1>, \<column2>, etc.**</span><span class="sxs-lookup"><span data-stu-id="7bf56-188">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="7bf56-189">Muestra los valores duplicados que se encontraron en la columna de perfiles.</span><span class="sxs-lookup"><span data-stu-id="7bf56-189">Displays the duplicate values that were found in the profiled column.</span></span>  
  
 <span data-ttu-id="7bf56-190">**Recuento**</span><span class="sxs-lookup"><span data-stu-id="7bf56-190">**Count**</span></span>  
 <span data-ttu-id="7bf56-191">Muestra el número de filas en las que la columna especificada tiene el valor que se muestra en la primera columna.</span><span class="sxs-lookup"><span data-stu-id="7bf56-191">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
### <a name="profile-type--functional-dependency-profile"></a><span data-ttu-id="7bf56-192">Tipo de perfil = Perfil de dependencia funcional</span><span class="sxs-lookup"><span data-stu-id="7bf56-192">Profile Type = Functional Dependency Profile</span></span>  
  
#### <a name="functional-dependency-profile-pane"></a><span data-ttu-id="7bf56-193">Panel Perfil de dependencia funcional</span><span class="sxs-lookup"><span data-stu-id="7bf56-193">Functional Dependency Profile pane</span></span>  
 <span data-ttu-id="7bf56-194">**Columnas determinantes**</span><span class="sxs-lookup"><span data-stu-id="7bf56-194">**Determinant Columns**</span></span>  
 <span data-ttu-id="7bf56-195">Muestra la columna o columnas seleccionadas como columna determinante.</span><span class="sxs-lookup"><span data-stu-id="7bf56-195">Displays the column or columns selected as the determinant column.</span></span> <span data-ttu-id="7bf56-196">En el ejemplo en el que el mismo código postal de Estados Unidos siempre debería tener el mismo estado, el código postal es la columna determinante.</span><span class="sxs-lookup"><span data-stu-id="7bf56-196">In the example where the same United States Zip Code should always have the same state, the Zip Code is the determinant column.</span></span>  
  
 <span data-ttu-id="7bf56-197">**Columnas dependientes**</span><span class="sxs-lookup"><span data-stu-id="7bf56-197">**Dependent Columns**</span></span>  
 <span data-ttu-id="7bf56-198">Muestra la columna o columnas seleccionadas como columna dependiente.</span><span class="sxs-lookup"><span data-stu-id="7bf56-198">Displays the column or columns selected as the dependent column.</span></span> <span data-ttu-id="7bf56-199">En el ejemplo en el que el mismo código postal de Estados Unidos siempre debería tener el mismo estado, el estado es la columna dependiente.</span><span class="sxs-lookup"><span data-stu-id="7bf56-199">In the example where the same United States Zip Code should always have the same state, the state is the dependent column.</span></span>  
  
 <span data-ttu-id="7bf56-200">**Nivel de dependencia funcional**</span><span class="sxs-lookup"><span data-stu-id="7bf56-200">**Functional Dependency Strength**</span></span>  
 <span data-ttu-id="7bf56-201">Muestra el nivel (como porcentaje) de la dependencia funcional entre las columnas.</span><span class="sxs-lookup"><span data-stu-id="7bf56-201">Displays the strength (as a percentage) of the functional dependency between columns.</span></span> <span data-ttu-id="7bf56-202">Un nivel de clave menor del 100% indica que hay casos en los que el valor determinante no determina el valor dependiente.</span><span class="sxs-lookup"><span data-stu-id="7bf56-202">A key strength of less than 100% indicates that there are cases where the determinant value does not determine the dependent value.</span></span> <span data-ttu-id="7bf56-203">En el ejemplo en el que el mismo código postal de Estados Unidos siempre debería tener el mismo estado, esto probablemente indica que algunos valores de estado no son válidos.</span><span class="sxs-lookup"><span data-stu-id="7bf56-203">In the example where the same United States Zip Code should always have the same state, this probably indicates some state values are not valid.</span></span>  
  
#### <a name="functional-dependency-violations-pane"></a><span data-ttu-id="7bf56-204">Panel Infracciones de dependencia funcional</span><span class="sxs-lookup"><span data-stu-id="7bf56-204">Functional Dependency Violations pane</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bf56-205">Un porcentaje alto de valores erróneos en los datos podría provocar resultados inesperados en un perfil Dependencia funcional.</span><span class="sxs-lookup"><span data-stu-id="7bf56-205">A high percentage of erroneous values in the data could lead to unexpected results from a Functional Dependency profile.</span></span> <span data-ttu-id="7bf56-206">Por ejemplo, el 90% de las filas tienen el valor "WI" como estado para el valor "98052" de código postal.</span><span class="sxs-lookup"><span data-stu-id="7bf56-206">For example, 90% of the rows have a State value of "WI" for a Postal Code value of "98052."</span></span> <span data-ttu-id="7bf56-207">El perfil notifica filas que contienen valor de estado correcto de "WA" como infracciones.</span><span class="sxs-lookup"><span data-stu-id="7bf56-207">The profile reports rows that contain the correct state value of "WA" as violations.</span></span>  
  
 **\<determinant column name>**  
 <span data-ttu-id="7bf56-208">Muestra el valor de la columna determinante o la combinación de columnas en esta infracción de la dependencia funcional.</span><span class="sxs-lookup"><span data-stu-id="7bf56-208">Displays the value of the determinant column or combination of columns in this instance of a functional dependency violation.</span></span>  
  
 **\<dependent column name>**  
 <span data-ttu-id="7bf56-209">Muestra el valor de la columna dependiente en esta infracción de la dependencia funcional.</span><span class="sxs-lookup"><span data-stu-id="7bf56-209">Displays the value of the dependent column in this instance of a functional dependency violation.</span></span>  
  
 <span data-ttu-id="7bf56-210">**Recuento de soporte**</span><span class="sxs-lookup"><span data-stu-id="7bf56-210">**Support Count**</span></span>  
 <span data-ttu-id="7bf56-211">Muestra el número de filas en las que el valor de columna determinante determina la columna dependiente.</span><span class="sxs-lookup"><span data-stu-id="7bf56-211">Displays the number of rows in which the determinant column value determines the dependent column.</span></span>  
  
 <span data-ttu-id="7bf56-212">**Recuento de infracciones**</span><span class="sxs-lookup"><span data-stu-id="7bf56-212">**Violation Count**</span></span>  
 <span data-ttu-id="7bf56-213">Muestra el número de filas en las que el valor de columna determinante no determina la columna dependiente.</span><span class="sxs-lookup"><span data-stu-id="7bf56-213">Displays the number of rows in which the determinant column value does not determine the dependent column.</span></span> <span data-ttu-id="7bf56-214">(Estas son las filas en las que el valor dependiente es el que se muestra en la columna **\<dependent column name>** ).</span><span class="sxs-lookup"><span data-stu-id="7bf56-214">(These are the rows where the dependent value is the value shown in the **\<dependent column name>** column.)</span></span>  
  
 <span data-ttu-id="7bf56-215">**Porcentaje admitido**</span><span class="sxs-lookup"><span data-stu-id="7bf56-215">**Support Percentage**</span></span>  
 <span data-ttu-id="7bf56-216">Muestra el porcentaje de filas en las que el valor de columna determinante determina la columna dependiente.</span><span class="sxs-lookup"><span data-stu-id="7bf56-216">Displays the percentage of rows in which the determinant column determines the dependent column.</span></span>  
  
### <a name="profile-type--value-inclusion-profile"></a><span data-ttu-id="7bf56-217">Tipo de perfil = Perfil de inclusión de valores</span><span class="sxs-lookup"><span data-stu-id="7bf56-217">Profile Type = Value Inclusion Profile</span></span>  
  
#### <a name="value-inclusion-profile-pane"></a><span data-ttu-id="7bf56-218">Panel Perfil de inclusión de valores</span><span class="sxs-lookup"><span data-stu-id="7bf56-218">Value Inclusion Profile pane</span></span>  
 <span data-ttu-id="7bf56-219">**Columnas de subconjunto**</span><span class="sxs-lookup"><span data-stu-id="7bf56-219">**Subset Side Columns**</span></span>  
 <span data-ttu-id="7bf56-220">Muestra la columna o combinación de columnas que se incluyeron en el perfil para determinar si están en las columnas de superconjunto.</span><span class="sxs-lookup"><span data-stu-id="7bf56-220">Displays the column or combination of columns that were profiled to determine whether they are in the superset columns.</span></span>  
  
 <span data-ttu-id="7bf56-221">**Columnas de superconjunto**</span><span class="sxs-lookup"><span data-stu-id="7bf56-221">**Superset Side Columns**</span></span>  
 <span data-ttu-id="7bf56-222">Muestra la columna o combinación de columnas que se incluyeron en el perfil para determinar si incluyen los valores en las columnas de subconjunto.</span><span class="sxs-lookup"><span data-stu-id="7bf56-222">Displays the column or combination of columns that were profiled to determine whether they include the values in the subset columns.</span></span>  
  
 <span data-ttu-id="7bf56-223">**Nivel de inclusión**</span><span class="sxs-lookup"><span data-stu-id="7bf56-223">**Inclusion Strength**</span></span>  
 <span data-ttu-id="7bf56-224">Muestra el nivel (como porcentaje) de la superposición entre las columnas.</span><span class="sxs-lookup"><span data-stu-id="7bf56-224">Displays the strength (as a percentage) of the overlap between columns.</span></span> <span data-ttu-id="7bf56-225">Un nivel de clave menor que 100% indica que hay casos en los que el valor de subconjunto no se encuentra entre los valores del superconjunto.</span><span class="sxs-lookup"><span data-stu-id="7bf56-225">A key strength of less than 100% indicates that there are cases where the subset value is not found among the superset values.</span></span>  
  
#### <a name="inclusion-violations-pane"></a><span data-ttu-id="7bf56-226">Panel Infracciones de inclusión</span><span class="sxs-lookup"><span data-stu-id="7bf56-226">Inclusion Violations pane</span></span>  
 <span data-ttu-id="7bf56-227">**\<column1>, \<column2>, etc.**</span><span class="sxs-lookup"><span data-stu-id="7bf56-227">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="7bf56-228">Muestra los valores en la columna o columnas del subconjunto que no se encontraban en la columna o columnas del superconjunto.</span><span class="sxs-lookup"><span data-stu-id="7bf56-228">Displays the values in the subset column or columns that were not found in the superset column or columns.</span></span>  
  
 <span data-ttu-id="7bf56-229">**Recuento**</span><span class="sxs-lookup"><span data-stu-id="7bf56-229">**Count**</span></span>  
 <span data-ttu-id="7bf56-230">Muestra el número de filas en las que la columna especificada tiene el valor que se muestra en la primera columna.</span><span class="sxs-lookup"><span data-stu-id="7bf56-230">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf56-231">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7bf56-231">See Also</span></span>  
 <span data-ttu-id="7bf56-232">[Visor de perfil de datos](control-flow/data-profile-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="7bf56-232">[Data Profile Viewer](control-flow/data-profile-viewer.md) </span></span>  
 [<span data-ttu-id="7bf56-233">Visor y tarea de generación de perfiles de datos</span><span class="sxs-lookup"><span data-stu-id="7bf56-233">Data Profiling Task and Viewer</span></span>](control-flow/data-profiling-task-and-viewer.md)  
  
  
